---
title: Sviluppo di un componente di origine personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [Integration Services], components
- external data sources [Integration Services]
- data flow components [Integration Services], source components
- output columns [Integration Services]
- custom data flow components [Integration Services], source components
- custom sources [Integration Services]
- source components [Integration Services]
ms.assetid: 4dc0f631-8fd6-4007-b573-ca67f58ca068
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6679b28463a09efe069235a5aef9dca54a381d62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721643"
---
# <a name="developing-a-custom-source-component"></a><span data-ttu-id="d33d9-102">Sviluppo di un componente di origine personalizzato</span><span class="sxs-lookup"><span data-stu-id="d33d9-102">Developing a Custom Source Component</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d33d9-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] offre agli sviluppatori la possibilità di scrivere componenti di origine in grado di connettersi a origini dati personalizzate e di fornire dati da tali origini ad altri componenti in un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="d33d9-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write source components that can connect to custom data sources and supply data from those sources to other components in a data flow task.</span></span> <span data-ttu-id="d33d9-104">La possibilità per creare origini personalizzate si rivela utile quando è necessario connettersi a origini dati non accessibili tramite una delle origini di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] esistenti.</span><span class="sxs-lookup"><span data-stu-id="d33d9-104">The ability to create custom sources is valuable when you must connect to data sources that cannot be accessed by using one of the existing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources.</span></span>

 <span data-ttu-id="d33d9-105">I componenti di origine includono uno o più output e nessun input.</span><span class="sxs-lookup"><span data-stu-id="d33d9-105">Source components have one or more outputs and zero inputs.</span></span> <span data-ttu-id="d33d9-106">In fase di progettazione tali componenti vengono utilizzati per creare e configurare connessioni, leggere metadati di colonne dall'origine dati esterna e configurare le colonne di output dell'origine in base all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="d33d9-106">At design time, source components are used to create and configure connections, read column metadata from the external data source, and configure the source's output columns based on the external data source.</span></span> <span data-ttu-id="d33d9-107">Durante l'esecuzione, si connettono all'origine dati esterna e aggiungono righe a un buffer di output.</span><span class="sxs-lookup"><span data-stu-id="d33d9-107">During execution they connect to the external data source and add rows to an output buffer.</span></span> <span data-ttu-id="d33d9-108">L'attività Flusso di dati fornisce quindi questo buffer di righe di dati ai componenti a valle.</span><span class="sxs-lookup"><span data-stu-id="d33d9-108">The data flow task then provides this buffer of data rows to downstream components.</span></span>

 <span data-ttu-id="d33d9-109">Per una panoramica generale sullo sviluppo di componenti flusso dati, vedere [Sviluppo di un componente flusso di dati personalizzato](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d33d9-109">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="d33d9-110">Fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="d33d9-110">Design Time</span></span>
 <span data-ttu-id="d33d9-111">L'implementazione della funzionalità in fase di progettazione di un componente di origine implica la specifica di una connessione a un'origine dati esterna, l'aggiunta e la configurazione delle colonne di output che riflettono l'origine dati e la verifica che il componente sia pronto per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d33d9-111">Implementing the design-time functionality of a source component involves specifying a connection to an external data source, adding and configuring output columns that reflect the data source, and validating that the component is ready to execute.</span></span> <span data-ttu-id="d33d9-112">Per definizione, un componente di origine include uno o più output asincroni e nessun input.</span><span class="sxs-lookup"><span data-stu-id="d33d9-112">By definition, a source component has zero inputs and one or more asynchronous outputs.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="d33d9-113">Creazione del componente</span><span class="sxs-lookup"><span data-stu-id="d33d9-113">Creating the Component</span></span>
 <span data-ttu-id="d33d9-114">I componenti di origine si connettono a origini dati esterne tramite gli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> definiti in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d33d9-114">Source components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="d33d9-115">Indicano il requisito di una gestione connessione con l'aggiunta di un elemento alla raccolta <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-115">They indicate their requirement for a connection manager by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="d33d9-116">Questa raccolta ha due scopi: contenere i riferimenti alle gestioni connessioni nel pacchetto usato dal componente e segnalare la necessità di una gestione connessione alla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d33d9-116">This collection serves two purposes-to hold references to connection managers in the package used by the component, and to advertise the need for a connection manager to the designer.</span></span> <span data-ttu-id="d33d9-117">Dopo che un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> è stato aggiunto alla raccolta, in **Editor avanzato** viene visualizzata la scheda **Proprietà connessione**, che consente agli utenti di selezionare o creare una connessione nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d33d9-117">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> has been added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, which lets users select or create a connection in the package.</span></span>

 <span data-ttu-id="d33d9-118">Nell'esempio di codice seguente è illustrata un'implementazione di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> che aggiunge un output, quindi aggiunge un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an output, and adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using System.Collections;
using System.Data;
using System.Data.SqlClient;
using System.Data.OleDb;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "MySourceComponent",ComponentType = ComponentType.SourceAdapter)]
    public class MyComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
            output.Name = "Output";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.NET";
        }
```

```vb
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Runtime
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper

<DtsPipelineComponent(DisplayName:="MySourceComponent", ComponentType:=ComponentType.SourceAdapter)> _
Public Class MySourceComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Allow for resetting the component.
        RemoveAllInputsOutputsAndCustomProperties()
        ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()
        output.Name = "Output"

        Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
        connection.Name = "ADO.NET"

    End Sub
End Class
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="d33d9-119">Connessione a un'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="d33d9-119">Connecting to an External Data Source</span></span>
 <span data-ttu-id="d33d9-120">Dopo che una connessione è stata aggiunta a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> per stabilire una connessione all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="d33d9-120">After a connection has been added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="d33d9-121">Questo metodo viene chiamato sia durante la fase di progettazione che di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d33d9-121">This method is called during both design and execution time.</span></span> <span data-ttu-id="d33d9-122">Il componente deve stabilire una connessione alla gestione connessione specificata dalla connessione di run-time e, successivamente, all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="d33d9-122">The component should establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span>

 <span data-ttu-id="d33d9-123">Una volta stabilita, la connessione deve essere memorizzata nella cache interna dal componente e rilasciata quando viene chiamato il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-123">After the connection is established, it should be cached internally by the component and released when the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called.</span></span> <span data-ttu-id="d33d9-124">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> viene chiamato in fase di progettazione e di esecuzione, analogamente al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-124">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method is called at design and execution time, like the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method.</span></span> <span data-ttu-id="d33d9-125">Gli sviluppatori eseguono l'override di questo metodo e rilasciano la connessione stabilita dal componente durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span>

 <span data-ttu-id="d33d9-126">Nell'esempio di codice seguente è illustrato un componente che si connette a una connessione ADO.NET nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> e chiude la connessione nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-126">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method and closes the connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> method.</span></span>

```csharp
private SqlConnection sqlConnection;

public override void AcquireConnections(object transaction)
{
    if (ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager != null)
    {
        ConnectionManager cm = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager);
        ConnectionManagerAdoNet cmado = cm.InnerObject as ConnectionManagerAdoNet;

        if (cmado == null)
            throw new Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.");

        sqlConnection = cmado.AcquireConnection(transaction) as SqlConnection;
        sqlConnection.Open();
    }
}

public override void ReleaseConnections()
{
    if (sqlConnection != null && sqlConnection.State != ConnectionState.Closed)
        sqlConnection.Close();
}
```

```vb
Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If Not IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) Then

        Dim cm As ConnectionManager = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject, ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If Not IsNothing(sqlConnection) And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="d33d9-127">Creazione e configurazione di colonne di output</span><span class="sxs-lookup"><span data-stu-id="d33d9-127">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="d33d9-128">Le colonne di output di un componente di origine riflettono le colonne dell'origine dati esterna aggiunte dal componente al flusso di dati durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d33d9-128">The output columns of a source component reflect the columns from the external data source that the component adds to the data flow during execution.</span></span> <span data-ttu-id="d33d9-129">In fase di progettazione le colonne di output vengono aggiunte dopo che il componente è stato configurato per la connessione a un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="d33d9-129">At design time, you add output columns after the component has been configured to connect to an external data source.</span></span> <span data-ttu-id="d33d9-130">Il metodo della fase di progettazione utilizzato da un componente per aggiungere le colonne alla propria raccolta di output varia in base ai requisiti del componente, anche se questa aggiunta non deve essere eseguita durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-130">The design-time method that a component uses to add the columns to its output collection can vary based on the needs of the component, although they should not be added during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="d33d9-131">Ad esempio, un componente che contiene un'istruzione SQL in una proprietà personalizzata che controlla il set di dati per il componente può aggiungere le proprie colonne di output durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-131">For example, a component that contains a SQL statement in a custom property that controls the data set for the component may add its output columns during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetComponentProperty%2A> method.</span></span> <span data-ttu-id="d33d9-132">Il componente verifica se è disponibile una connessione memorizzata nella cache e, in caso affermativo, si connette all'origine dati e genera le proprie colonne di output.</span><span class="sxs-lookup"><span data-stu-id="d33d9-132">The component checks to see whether it has a cached connection, and, if it does, connects to the data source and generates its output columns.</span></span>

 <span data-ttu-id="d33d9-133">Dopo la creazione di una colonna di output, impostare le relative proprietà del tipo di dati chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-133">After an output column has been created, set its data type properties by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="d33d9-134">Questo metodo è necessario perché le proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> sono di sola lettura e ogni proprietà dipende dalle impostazioni dell'altra.</span><span class="sxs-lookup"><span data-stu-id="d33d9-134">This method is necessary because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are read-only and each property is dependent on the settings of the other.</span></span> <span data-ttu-id="d33d9-135">Questo metodo impone la necessità di impostare questi valori in modo consistente e l'attività Flusso di dati verifica se sono stati impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="d33d9-135">This method enforces the need for these values to be set consistently, and the data flow task validates that they are set correctly.</span></span>

 <span data-ttu-id="d33d9-136">L'oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> della colonna determina i valori impostati per le altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="d33d9-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="d33d9-137">Nella tabella seguente sono illustrati i requisiti delle proprietà dipendenti per ogni oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-137">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="d33d9-138">Le proprietà dipendenti dei tipi di dati non elencati sono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="d33d9-138">The data types not listed have their dependent properties set to zero.</span></span>

|<span data-ttu-id="d33d9-139">DataType</span><span class="sxs-lookup"><span data-stu-id="d33d9-139">DataType</span></span>|<span data-ttu-id="d33d9-140">Length</span><span class="sxs-lookup"><span data-stu-id="d33d9-140">Length</span></span>|<span data-ttu-id="d33d9-141">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="d33d9-141">Scale</span></span>|<span data-ttu-id="d33d9-142">Precision</span><span class="sxs-lookup"><span data-stu-id="d33d9-142">Precision</span></span>|<span data-ttu-id="d33d9-143">CodePage</span><span class="sxs-lookup"><span data-stu-id="d33d9-143">CodePage</span></span>|
|--------------|------------|-----------|---------------|--------------|
|<span data-ttu-id="d33d9-144">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="d33d9-144">DT_DECIMAL</span></span>|<span data-ttu-id="d33d9-145">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-145">0</span></span>|<span data-ttu-id="d33d9-146">Maggiore di 0 e minore o uguale a 28.</span><span class="sxs-lookup"><span data-stu-id="d33d9-146">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="d33d9-147">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-147">0</span></span>|<span data-ttu-id="d33d9-148">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-148">0</span></span>|
|<span data-ttu-id="d33d9-149">DT_CY</span><span class="sxs-lookup"><span data-stu-id="d33d9-149">DT_CY</span></span>|<span data-ttu-id="d33d9-150">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-150">0</span></span>|<span data-ttu-id="d33d9-151">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-151">0</span></span>|<span data-ttu-id="d33d9-152">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-152">0</span></span>|<span data-ttu-id="d33d9-153">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-153">0</span></span>|
|<span data-ttu-id="d33d9-154">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="d33d9-154">DT_NUMERIC</span></span>|<span data-ttu-id="d33d9-155">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-155">0</span></span>|<span data-ttu-id="d33d9-156">Maggiore di 0 e minore o uguale a 28, nonché minore di Precision.</span><span class="sxs-lookup"><span data-stu-id="d33d9-156">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="d33d9-157">Maggiore o uguale a 1 e minore o uguale a 38.</span><span class="sxs-lookup"><span data-stu-id="d33d9-157">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="d33d9-158">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-158">0</span></span>|
|<span data-ttu-id="d33d9-159">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="d33d9-159">DT_BYTES</span></span>|<span data-ttu-id="d33d9-160">Maggiore di 0.</span><span class="sxs-lookup"><span data-stu-id="d33d9-160">Greater than 0.</span></span>|<span data-ttu-id="d33d9-161">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-161">0</span></span>|<span data-ttu-id="d33d9-162">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-162">0</span></span>|<span data-ttu-id="d33d9-163">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-163">0</span></span>|
|<span data-ttu-id="d33d9-164">DT_STR</span><span class="sxs-lookup"><span data-stu-id="d33d9-164">DT_STR</span></span>|<span data-ttu-id="d33d9-165">Maggiore di 0 e minore di 8000.</span><span class="sxs-lookup"><span data-stu-id="d33d9-165">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="d33d9-166">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-166">0</span></span>|<span data-ttu-id="d33d9-167">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-167">0</span></span>|<span data-ttu-id="d33d9-168">Diverso da 0 e tabella codici valida.</span><span class="sxs-lookup"><span data-stu-id="d33d9-168">Not 0, and a valid code page.</span></span>|
|<span data-ttu-id="d33d9-169">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="d33d9-169">DT_WSTR</span></span>|<span data-ttu-id="d33d9-170">Maggiore di 0 e minore di 4000.</span><span class="sxs-lookup"><span data-stu-id="d33d9-170">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="d33d9-171">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-171">0</span></span>|<span data-ttu-id="d33d9-172">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-172">0</span></span>|<span data-ttu-id="d33d9-173">0</span><span class="sxs-lookup"><span data-stu-id="d33d9-173">0</span></span>|

 <span data-ttu-id="d33d9-174">Poiché le restrizioni sulle proprietà del tipo di dati sono basate sul tipo di dati della colonna di output, è necessario scegliere il tipo di dati di [!INCLUDE[ssIS](../../includes/ssis-md.md)] corretto quando si utilizzano tipi gestiti.</span><span class="sxs-lookup"><span data-stu-id="d33d9-174">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="d33d9-175">La classe di base fornisce tre metodi di supporto, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, per assistere gli sviluppatori di componenti gestiti nella selezione di un tipo di dati di [!INCLUDE[ssIS](../../includes/ssis-md.md)] dato un tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="d33d9-175">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A>, to assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="d33d9-176">Questi metodi convertono i tipi di dati gestiti nei tipi di dati di [!INCLUDE[ssIS](../../includes/ssis-md.md)] e viceversa.</span><span class="sxs-lookup"><span data-stu-id="d33d9-176">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>

 <span data-ttu-id="d33d9-177">Nell'esempio di codice seguente viene illustrato il popolamento della raccolta di colonne di output di un componente in base allo schema di una tabella.</span><span class="sxs-lookup"><span data-stu-id="d33d9-177">The following code example shows how the output column collection of a component is populated based on the schema of a table.</span></span> <span data-ttu-id="d33d9-178">I metodi di supporto della classe di base vengono utilizzati per impostare il tipo di dati della colonna, mentre le proprietà dipendenti vengono impostate in base al tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d33d9-178">The helper methods of the base class are used to set the data type of the column, and the dependent properties are set based on the data type.</span></span>

```csharp
SqlCommand sqlCommand;

private void CreateColumnsFromDataTable()
{
    // Get the output.
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    // Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll();
    output.ExternalMetadataColumnCollection.RemoveAll();

    this.sqlCommand = sqlConnection.CreateCommand();
    this.sqlCommand.CommandType = CommandType.Text;
    this.sqlCommand.CommandText = (string)ComponentMetaData.CustomPropertyCollection["SqlStatement"].Value;
    SqlDataReader schemaReader = this.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly);
    DataTable dataTable = schemaReader.GetSchemaTable();

    // Walk the columns in the schema, 
    // and for each data column create an output column and an external metadata column.
    foreach (DataRow row in dataTable.Rows)
    {
        IDTSOutputColumn100 outColumn = output.OutputColumnCollection.New();
        IDTSExternalMetadataColumn100 exColumn = output.ExternalMetadataColumnCollection.New();

        // Set column data type properties.
        bool isLong = false;
        DataType dt = DataRecordTypeToBufferType((Type)row["DataType"]);
        dt = ConvertBufferDataTypeToFitManaged(dt, ref isLong);
        int length = 0;
        int precision = (short)row["NumericPrecision"];
        int scale = (short)row["NumericScale"];
        int codepage = dataTable.Locale.TextInfo.ANSICodePage;

        switch (dt)
        {
            // The length cannot be zero, and the code page property must contain a valid code page.
            case DataType.DT_STR:
            case DataType.DT_TEXT:
                length = precision;
                precision = 0;
                scale = 0;
                break;

            case DataType.DT_WSTR:
                length = precision;
                codepage = 0;
                scale = 0;
                precision = 0;
                break;

            case DataType.DT_BYTES:
                precision = 0;
                scale = 0;
                codepage = 0;
                break;

            case DataType.DT_NUMERIC:
                length = 0;
                codepage = 0;

                if (precision > 38)
                    precision = 38;

                if (scale > 6)
                    scale = 6;
                break;

            case DataType.DT_DECIMAL:
                length = 0;
                precision = 0;
                codepage = 0;
                break;

            default:
                length = 0;
                precision = 0;
                codepage = 0;
                scale = 0;
                break;

        }

        // Set the properties of the output column.
        outColumn.Name = (string)row["ColumnName"];
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage);
    }
}
```

```vb
Private sqlCommand As SqlCommand

Private Sub CreateColumnsFromDataTable()

    ' Get the output.
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    ' Start clean, and remove the columns from both collections.
    output.OutputColumnCollection.RemoveAll()
    output.ExternalMetadataColumnCollection.RemoveAll()

    Me.sqlCommand = sqlConnection.CreateCommand()
    Me.sqlCommand.CommandType = CommandType.Text
    Me.sqlCommand.CommandText = CStr(ComponentMetaData.CustomPropertyCollection("SqlStatement").Value)

    Dim schemaReader As SqlDataReader = Me.sqlCommand.ExecuteReader(CommandBehavior.SchemaOnly)
    Dim dataTable As DataTable = schemaReader.GetSchemaTable()

    ' Walk the columns in the schema, 
    ' and for each data column create an output column and an external metadata column.
    For Each row As DataRow In dataTable.Rows

        Dim outColumn As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        Dim exColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()

        ' Set column data type properties.
        Dim isLong As Boolean = False
        Dim dt As DataType = DataRecordTypeToBufferType(CType(row("DataType"), Type))
        dt = ConvertBufferDataTypeToFitManaged(dt, isLong)
        Dim length As Integer = 0
        Dim precision As Integer = CType(row("NumericPrecision"), Short)
        Dim scale As Integer = CType(row("NumericScale"), Short)
        Dim codepage As Integer = dataTable.Locale.TextInfo.ANSICodePage

        Select Case dt

            ' The length cannot be zero, and the code page property must contain a valid code page.
            Case DataType.DT_STR
            Case DataType.DT_TEXT
                length = precision
                precision = 0
                scale = 0

            Case DataType.DT_WSTR
                length = precision
                codepage = 0
                scale = 0
                precision = 0

            Case DataType.DT_BYTES
                precision = 0
                scale = 0
                codepage = 0

            Case DataType.DT_NUMERIC
                length = 0
                codepage = 0

                If precision > 38 Then
                    precision = 38
                End If

                If scale > 6 Then
                    scale = 6
                End If

            Case DataType.DT_DECIMAL
                length = 0
                precision = 0
                codepage = 0

            Case Else
                length = 0
                precision = 0
                codepage = 0
                scale = 0
        End Select

        ' Set the properties of the output column.
        outColumn.Name = CStr(row("ColumnName"))
        outColumn.SetDataTypeProperties(dt, length, precision, scale, codepage)
    Next
End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="d33d9-179">Convalida del componente</span><span class="sxs-lookup"><span data-stu-id="d33d9-179">Validating the Component</span></span>
 <span data-ttu-id="d33d9-180">È necessario convalidare un componente di origine e verificare che le colonne definite nelle relative raccolte di colonne di output corrispondano alle colonne nell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="d33d9-180">You should validate a source component and verify that the columns defined in its output column collections match the columns at the external data source.</span></span> <span data-ttu-id="d33d9-181">Talvolta, può essere impossibile verificare le colonne di output rispetto all'origine dati esterna, ad esempio in uno stato disconnesso oppure quando è preferibile evitare lunghi round trip al server.</span><span class="sxs-lookup"><span data-stu-id="d33d9-181">Sometimes, verifying the output columns against the external data source can be impossible, such as in a disconnected state, or when it is preferable to avoid lengthy round trips to the server.</span></span> <span data-ttu-id="d33d9-182">In queste situazioni, le colonne nell'output possono comunque essere convalidate tramite <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> dell'oggetto di output.</span><span class="sxs-lookup"><span data-stu-id="d33d9-182">In these situations, the columns in the output can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExternalMetadataColumnCollection%2A> of the output object.</span></span> <span data-ttu-id="d33d9-183">Per altre informazioni, vedere [Convalida di un componente del flusso di dati](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d33d9-183">For more information, see [Validating a Data Flow Component](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span>

 <span data-ttu-id="d33d9-184">Questa raccolta esiste sia negli oggetti di input che di output ed è possibile popolarla con le colonne dell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="d33d9-184">This collection exists on both input and output objects and you can populate it with the columns from the external data source.</span></span> <span data-ttu-id="d33d9-185">È possibile utilizzare questa raccolta per convalidare le colonne di output quando Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] è offline, quando il componente è disconnesso o quando la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="d33d9-185">You can use this collection to validate the output columns when [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span> <span data-ttu-id="d33d9-186">La raccolta deve essere popolata per la prima volta contemporaneamente alla creazione delle colonne di output.</span><span class="sxs-lookup"><span data-stu-id="d33d9-186">The collection should be first populated at the same time that the output columns are created.</span></span> <span data-ttu-id="d33d9-187">L'aggiunta di colonne di metadati esterne alla raccolta è relativamente semplice, perché la colonna di metadati esterna deve inizialmente corrispondere alla colonna di output.</span><span class="sxs-lookup"><span data-stu-id="d33d9-187">Adding external metadata columns to the collection is relatively easy because the external metadata column should initially match the output column.</span></span> <span data-ttu-id="d33d9-188">Le proprietà del tipo di dati della colonna devono essere già state impostate correttamente e possono essere copiate direttamente nell'oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-188">The data type properties of the column should have already been set correctly, and the properties can be copied directly to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumn100> object.</span></span>

 <span data-ttu-id="d33d9-189">Nel codice di esempio seguente viene aggiunta una colonna di metadati esterna basata su una colonna di output appena creata.</span><span class="sxs-lookup"><span data-stu-id="d33d9-189">The following sample code adds an external metadata column that is based on a newly created output column.</span></span> <span data-ttu-id="d33d9-190">Si presuppone che la colonna di output sia già stata creata.</span><span class="sxs-lookup"><span data-stu-id="d33d9-190">It assumes that the output column has already been created.</span></span>

```csharp
private void CreateExternalMetaDataColumn(IDTSOutput100 output, IDTSOutputColumn100 outputColumn)
{

    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = output.ExternalMetadataColumnCollection.New();
    externalColumn.Name = outputColumn.Name;
    externalColumn.Precision = outputColumn.Precision;
    externalColumn.Length = outputColumn.Length;
    externalColumn.DataType = outputColumn.DataType;
    externalColumn.Scale = outputColumn.Scale;

    // Map the external column to the output column.
    outputColumn.ExternalMetadataColumnID = externalColumn.ID;

}
```

```vb
Private Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumn As IDTSOutputColumn100)

        ' Set the properties of the external metadata column.
        Dim externalColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New()
        externalColumn.Name = outputColumn.Name
        externalColumn.Precision = outputColumn.Precision
        externalColumn.Length = outputColumn.Length
        externalColumn.DataType = outputColumn.DataType
        externalColumn.Scale = outputColumn.Scale

        ' Map the external column to the output column.
        outputColumn.ExternalMetadataColumnID = externalColumn.ID

    End Sub
```

## <a name="run-time"></a><span data-ttu-id="d33d9-191">Fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="d33d9-191">Run Time</span></span>
 <span data-ttu-id="d33d9-192">Durante l'esecuzione i componenti aggiungono righe ai buffer di output creati dall'attività Flusso di dati e forniti al componente in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-192">During execution, components add rows to output buffers that are created by the data flow task and provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="d33d9-193">Chiamato una volta per i componenti di origine, il metodo riceve un buffer di output per ogni <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> del componente connesso a un componente a valle.</span><span class="sxs-lookup"><span data-stu-id="d33d9-193">Called once for source components, the method receives an output buffer for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the component that is connected to a downstream component.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="d33d9-194">Individuazione di colonne nel buffer</span><span class="sxs-lookup"><span data-stu-id="d33d9-194">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="d33d9-195">Il buffer di output per un componente contiene le colonne definite dal componente ed eventuali altre colonne aggiunte all'output di un componente a valle.</span><span class="sxs-lookup"><span data-stu-id="d33d9-195">The output buffer for a component contains the columns defined by the component and any columns added to the output of a downstream component.</span></span> <span data-ttu-id="d33d9-196">Se ad esempio un componente di origine prevede tre colonne nel relativo output e il componente successivo aggiunge una quarta colonna di output, il buffer di output fornito per l'utilizzo da parte del componente di origine contiene queste quattro colonne.</span><span class="sxs-lookup"><span data-stu-id="d33d9-196">For example, if a source component provides three columns in its output, and the next component adds a fourth output column, the output buffer provided for use by the source component contains these four columns.</span></span>

 <span data-ttu-id="d33d9-197">L'ordine delle colonne in una riga del buffer non è definito dall'indice della colonna di output nella raccolta di colonne di output.</span><span class="sxs-lookup"><span data-stu-id="d33d9-197">The order of the columns in a buffer row is not defined by the index of the output column in the output column collection.</span></span> <span data-ttu-id="d33d9-198">È possibile individuare in modo accurato una colonna di output in una riga del buffer solo tramite il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-198">An output column can only be accurately located in a buffer row by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSBufferManagerClass.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="d33d9-199">Questo metodo individua la colonna con l'ID di derivazione specificato nel buffer specificato, quindi restituisce la relativa posizione nella riga.</span><span class="sxs-lookup"><span data-stu-id="d33d9-199">This method locates the column with the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="d33d9-200">Gli indici delle colonne di output vengono in genere individuati nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> e vengono archiviati per l'utilizzo durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-200">The indexes of the output columns are typically located in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and stored for use during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span>

 <span data-ttu-id="d33d9-201">Nell'esempio di codice seguente viene individuata la posizione delle colonne di output nel buffer di output durante una chiamata a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> e tali colonne vengono archiviate in una struttura interna.</span><span class="sxs-lookup"><span data-stu-id="d33d9-201">The following code example finds the location of the output columns in the output buffer during a call to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, and stores them in an internal structure.</span></span> <span data-ttu-id="d33d9-202">Anche il nome della colonna viene archiviato nella struttura e viene utilizzato nell'esempio di codice per il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> nella sezione successiva di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d33d9-202">The name of the column is also stored in the structure and is used in the code example for the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method in the next section of this topic.</span></span>

```csharp
ArrayList columnInformation;

private struct ColumnInfo
{
    public int BufferColumnIndex;
    public string ColumnName;
}

public override void PreExecute()
{
    this.columnInformation = new ArrayList();
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

    foreach (IDTSOutputColumn100 col in output.OutputColumnCollection)
    {
        ColumnInfo ci = new ColumnInfo();
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID);
        ci.ColumnName = col.Name;
        columnInformation.Add(ci);
    }
}
```

```vb
Public Overrides Sub PreExecute()

    Me.columnInformation = New ArrayList()
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

    For Each col As IDTSOutputColumn100 In output.OutputColumnCollection

        Dim ci As ColumnInfo = New ColumnInfo()
        ci.BufferColumnIndex = BufferManager.FindColumnByLineageID(output.Buffer, col.LineageID)
        ci.ColumnName = col.Name
        columnInformation.Add(ci)
    Next
End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="d33d9-203">Elaborazione di righe</span><span class="sxs-lookup"><span data-stu-id="d33d9-203">Processing Rows</span></span>
 <span data-ttu-id="d33d9-204">Le righe vengono aggiunte al buffer di output chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A>, che crea una nuova riga del buffer con valori vuoti nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="d33d9-204">Rows are added to the output buffer by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method, which creates a new buffer row with empty values in its columns.</span></span> <span data-ttu-id="d33d9-205">Il componente assegna quindi i valori alle singole colonne.</span><span class="sxs-lookup"><span data-stu-id="d33d9-205">The component then assigns values to the individual columns.</span></span> <span data-ttu-id="d33d9-206">I buffer di output forniti a un componente vengono creati e monitorati dall'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="d33d9-206">The output buffers provided to a component are created and monitored by the data flow task.</span></span> <span data-ttu-id="d33d9-207">Quando diventano pieni, le righe nel buffer vengono spostate nel componente successivo.</span><span class="sxs-lookup"><span data-stu-id="d33d9-207">As they become full, the rows in the buffer are moved to the next component.</span></span> <span data-ttu-id="d33d9-208">Non è possibile determinare quando un batch di righe è stato inviato al componente successivo, in quanto lo spostamento di righe da parte dell'attività Flusso di dati è trasparente per lo sviluppatore di componenti e la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> è sempre zero sui buffer di output.</span><span class="sxs-lookup"><span data-stu-id="d33d9-208">There is no way to determine when a batch of rows has been sent to the next component because the movement of rows by the data flow task is transparent to the component developer, and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RowCount%2A> property is always zero on output buffers.</span></span> <span data-ttu-id="d33d9-209">Quando un componente di origine termina l'aggiunta di righe al proprio buffer di output, notifica l'attività Flusso di dati con una chiamata al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, quindi le righe rimanenti nel buffer vengono passate al componente successivo.</span><span class="sxs-lookup"><span data-stu-id="d33d9-209">When a source component is finished adding rows to its output buffer, it notifies the data flow task by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>, and the remaining rows in the buffer are passed to the next component.</span></span>

 <span data-ttu-id="d33d9-210">Mentre il componente di origine legge le righe dall'origine dati esterna, è possibile aggiornare i contatori delle prestazioni "Righe lette" o "Byte BLOB letti" chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-210">While the source component reads rows from the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="d33d9-211">Per altre informazioni, vedere [i contatori delle prestazioni](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="d33d9-211">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="d33d9-212">Nell'esempio di codice seguente è illustrato un componente che aggiunge righe in un buffer di output in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d33d9-212">The following code example shows a component that adds rows to an output buffer in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span></span> <span data-ttu-id="d33d9-213">Gli indici delle colonne di output nel buffer sono stati individuati utilizzando <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> nell'esempio di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="d33d9-213">The indexes of the output columns in the buffer were located using <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the previous code example.</span></span>

```csharp
public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
{
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
    PipelineBuffer buffer = buffers[0];

    SqlDataReader dataReader = sqlCommand.ExecuteReader();

    // Loop over the rows in the DataReader, 
    // and add them to the output buffer.
    while (dataReader.Read())
    {
        // Add a row to the output buffer.
        buffer.AddRow();

        for (int x = 0; x < columnInformation.Count; x++)
        {
            ColumnInfo ci = (ColumnInfo)columnInformation[x];
            int ordinal = dataReader.GetOrdinal(ci.ColumnName);

            if (dataReader.IsDBNull(ordinal))
                buffer.SetNull(ci.BufferColumnIndex);
            else
            {
                buffer[ci.BufferColumnIndex] = dataReader[ci.ColumnName];
            }
        }
    }
    buffer.SetEndOfRowset();
}
```

```vb
Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim buffer As PipelineBuffer = buffers(0)

    Dim dataReader As SqlDataReader = sqlCommand.ExecuteReader()

    ' Loop over the rows in the DataReader, 
    ' and add them to the output buffer.
    While (dataReader.Read())

        ' Add a row to the output buffer.
        buffer.AddRow()

        For x As Integer = 0 To columnInformation.Count

            Dim ci As ColumnInfo = CType(columnInformation(x), ColumnInfo)

            Dim ordinal As Integer = dataReader.GetOrdinal(ci.ColumnName)

            If (dataReader.IsDBNull(ordinal)) Then
                buffer.SetNull(ci.BufferColumnIndex)
            Else
                buffer(ci.BufferColumnIndex) = dataReader(ci.ColumnName)

            End If
        Next

    End While

    buffer.SetEndOfRowset()
End Sub
```

## <a name="sample"></a><span data-ttu-id="d33d9-214">Esempio</span><span class="sxs-lookup"><span data-stu-id="d33d9-214">Sample</span></span>
 <span data-ttu-id="d33d9-215">Nell'esempio seguente è illustrato un componente di origine semplice che utilizza una gestione connessione file per caricare il contenuto binario dei file nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="d33d9-215">The following sample shows a simple source component that uses a File connection manager to load the binary contents of files into the data flow.</span></span> <span data-ttu-id="d33d9-216">Nell'esempio non vengono dimostrati tutti i metodi e le funzionalità descritti nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="d33d9-216">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="d33d9-217">Vengono descritti i metodi importanti di cui ogni componente di origine personalizzato deve eseguire l'override, ma non è incluso codice per la convalida in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d33d9-217">It demonstrates the important methods that every custom source component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace BlobSrc
{
  [DtsPipelineComponent(DisplayName = "BLOB Inserter Source", Description = "Inserts files into the data flow as BLOBs")]
  public class BlobSrc : PipelineComponent
  {
    IDTSConnectionManager100 m_ConnMgr;
    int m_FileNameColumnIndex = -1;
    int m_FileBlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection.New();
      output.Name = "BLOB File Inserter Output";

      IDTSOutputColumn100 column = output.OutputColumnCollection.New();
      column.Name = "FileName";
      column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0);

      column = output.OutputColumnCollection.New();
      column.Name = "FileBLOB";
      column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0);

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_ConnMgr = conn.ConnectionManager;
    }

    public override void ReleaseConnections()
    {
      m_ConnMgr = null;
    }

    public override void PreExecute()
    {
      IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

      m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[0].LineageID);
      m_FileBlobColumnIndex = (int)BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[1].LineageID);
    }

    public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
    {
      string strFileName = (string)m_ConnMgr.AcquireConnection(null);

      while (strFileName != null)
      {
        buffers[0].AddRow();

        buffers[0].SetString(m_FileNameColumnIndex, strFileName);

        FileInfo fileInfo = new FileInfo(strFileName);
        byte[] fileData = new byte[fileInfo.Length];
        FileStream fs = new FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read);
        fs.Read(fileData, 0, fileData.Length);

        buffers[0].AddBlobData(m_FileBlobColumnIndex, fileData);

        strFileName = (string)m_ConnMgr.AcquireConnection(null);
      }

      buffers[0].SetEndOfRowset();
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper 
Namespace BlobSrc 

 <DtsPipelineComponent(DisplayName="BLOB Inserter Source", Description="Inserts files into the data flow as BLOBs")> _ 
 Public Class BlobSrc 
 Inherits PipelineComponent 
   Private m_ConnMgr As IDTSConnectionManager100 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_FileBlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New 
     output.Name = "BLOB File Inserter Output" 
     Dim column As IDTSOutputColumn100 = output.OutputColumnCollection.New 
     column.Name = "FileName" 
     column.SetDataTypeProperties(DataType.DT_WSTR, 256, 0, 0, 0) 
     column = output.OutputColumnCollection.New 
     column.Name = "FileBLOB" 
     column.SetDataTypeProperties(DataType.DT_IMAGE, 0, 0, 0, 0) 
     Dim conn As IDTSRuntimeConnection90 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_ConnMgr = conn.ConnectionManager 
   End Sub 

   Public  Overrides Sub ReleaseConnections() 
     m_ConnMgr = Nothing 
   End Sub 

   Public  Overrides Sub PreExecute() 
     Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0) 
     m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(0).LineageID), Integer) 
     m_FileBlobColumnIndex = CType(BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(1).LineageID), Integer) 
   End Sub 

   Public  Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer()) 
     Dim strFileName As String = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     While Not (strFileName Is Nothing) 
       buffers(0).AddRow 
       buffers(0).SetString(m_FileNameColumnIndex, strFileName) 
       Dim fileInfo As FileInfo = New FileInfo(strFileName) 
       Dim fileData(fileInfo.Length) As Byte 
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Open, FileAccess.Read, FileShare.Read) 
       fs.Read(fileData, 0, fileData.Length) 
       buffers(0).AddBlobData(m_FileBlobColumnIndex, fileData) 
       strFileName = CType(m_ConnMgr.AcquireConnection(Nothing), String) 
     End While 
     buffers(0).SetEndOfRowset 
   End Sub 
 End Class 
End Namespace
```

<span data-ttu-id="d33d9-218">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d33d9-218">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d33d9-219">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="d33d9-219">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d33d9-220">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="d33d9-220">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d33d9-221">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="d33d9-221">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d33d9-222">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d33d9-222">See Also</span></span>
 <span data-ttu-id="d33d9-223">[Sviluppo di un componente di destinazione personalizzato](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [creazione di un'origine con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="d33d9-223">[Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) [Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md)</span></span>


