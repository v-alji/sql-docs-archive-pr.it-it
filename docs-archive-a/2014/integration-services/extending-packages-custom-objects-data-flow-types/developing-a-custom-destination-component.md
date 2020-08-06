---
title: Sviluppo di un componente di destinazione personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [Integration Services], components
- destinations [Integration Services], components
- ProcessInput method
- external data sources [Integration Services]
- custom data flow components [Integration Services], destination components
- data flow components [Integration Services], destination components
ms.assetid: 24619363-9535-4c0e-8b62-1d22c6630e40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6979d14afa0490638162c35bb660f15506803484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710976"
---
# <a name="developing-a-custom-destination-component"></a><span data-ttu-id="ce17d-102">Sviluppo di un componente di destinazione personalizzato</span><span class="sxs-lookup"><span data-stu-id="ce17d-102">Developing a Custom Destination Component</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="ce17d-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] offre agli sviluppatori la possibilità di scrivere componenti di destinazione personalizzati in grado di connettersi a un'origine dati personalizzata e archiviarvi i dati.</span><span class="sxs-lookup"><span data-stu-id="ce17d-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write custom destination components that can connect to and store data in any custom data source.</span></span> <span data-ttu-id="ce17d-104">I componenti di destinazione personalizzati risultano utili quando è necessario connettersi a origini dati che non sono accessibili tramite uno dei componenti di destinazione disponibili in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce17d-104">Custom destination components are useful when you need to connect to data sources that cannot be accessed by using one of the existing source components included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="ce17d-105">I componenti di destinazione includono uno o più input e nessun output.</span><span class="sxs-lookup"><span data-stu-id="ce17d-105">Destination components have one or more inputs and zero outputs.</span></span> <span data-ttu-id="ce17d-106">In fase di progettazione creano e configurano connessioni e leggono metadati di colonne dall'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ce17d-106">At design time, they create and configure connections and read column metadata from the external data source.</span></span> <span data-ttu-id="ce17d-107">Durante l'esecuzione si connettono all'origine dati esterna e vi aggiungono le righe ricevute dai componenti a monte nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="ce17d-107">During execution, they connect to their external data source and add rows that are received from the components upstream in the data flow to the external data source.</span></span> <span data-ttu-id="ce17d-108">Se l'origine dati esterna esiste prima dell'esecuzione del componente, il componente di destinazione deve anche assicurarsi che i tipi di dati delle colonne ricevute corrispondano ai tipi di dati delle colonne presenti nell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ce17d-108">If the external data source exists prior to execution of the component, the destination component must also ensure that the data types of the columns that the component receives match the data types of the columns at the external data source.</span></span>

 <span data-ttu-id="ce17d-109">In questa sezione viene descritto come sviluppare componenti di destinazione e vengono forniti esempi di codice per chiarire i concetti importanti.</span><span class="sxs-lookup"><span data-stu-id="ce17d-109">This section discusses the details of how to develop destination components, and provides code examples to clarify important concepts.</span></span> <span data-ttu-id="ce17d-110">Per una panoramica generale sullo sviluppo di componenti flusso dati, vedere [Sviluppo di un componente flusso di dati personalizzato](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ce17d-110">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="ce17d-111">Fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="ce17d-111">Design Time</span></span>
 <span data-ttu-id="ce17d-112">L'implementazione della funzionalità in fase di progettazione di un componente di destinazione implica la specifica di una connessione a un'origine dati esterna e la verifica che il componente sia correttamente configurato.</span><span class="sxs-lookup"><span data-stu-id="ce17d-112">Implementing the design-time functionality of a destination component involves specifying a connection to an external data source and validating that the component has been correctly configured.</span></span> <span data-ttu-id="ce17d-113">Per definizione, un componente di destinazione include un input e possibilmente un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="ce17d-113">By definition, a destination component has one input and possibly one error output.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="ce17d-114">Creazione del componente</span><span class="sxs-lookup"><span data-stu-id="ce17d-114">Creating the Component</span></span>
 <span data-ttu-id="ce17d-115">I componenti di destinazione si connettono a origini dati esterne tramite gli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> definiti in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ce17d-115">Destination components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="ce17d-116">Il componente di destinazione indica il proprio requisito di una gestione connessione a Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] e agli utenti del componente aggiungendo un elemento alla raccolta <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-116">The destination component indicates its requirement for a connection manager to the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, and to users of the component, by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span></span> <span data-ttu-id="ce17d-117">Questa raccolta svolge due funzioni: indica innanzitutto a Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] la necessità di una gestione connessione, quindi, dopo che l'utente ha selezionato o creato una gestione connessione, mantiene un riferimento alla gestione connessione nel pacchetto utilizzato dal componente.</span><span class="sxs-lookup"><span data-stu-id="ce17d-117">This collection serves two purposes: first, it advertises the need for a connection manager to [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer; then, after the user has selected or created a connection manager, it holds a reference to the connection manager in the package that is being used by the component.</span></span> <span data-ttu-id="ce17d-118">Quando un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> viene aggiunto alla raccolta, in **Editor avanzato** viene visualizzata la scheda **Proprietà connessione**, in cui si richiede di selezionare o creare nel pacchetto una connessione che verrà usata dal componente.</span><span class="sxs-lookup"><span data-stu-id="ce17d-118">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> is added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, to prompt the user to select or create a connection in the package for use by the component.</span></span>

 <span data-ttu-id="ce17d-119">Nell'esempio di codice seguente è illustrata un'implementazione di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> che aggiunge un input, quindi aggiunge un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-119">The following code sample shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an input, and then adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "Destination Component",ComponentType =ComponentType.DestinationAdapter)]
    public class DestinationComponent : PipelineComponent 
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSInput100 input = ComponentMetaData.InputCollection.New();
            input.Name = "Input";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.net";
        }
    }
}
```

```vb
Imports System
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="Destination Component", ComponentType:=ComponentType.DestinationAdapter)> _
    Public Class DestinationComponent
        Inherits PipelineComponent

        Public Overrides Sub ProvideComponentProperties()

            ' Reset the component.
            Me.RemoveAllInputsOutputsAndCustomProperties()
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()
            input.Name = "Input"

            Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
            connection.Name = "ADO.net"

        End Sub
    End Class
End Namespace
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="ce17d-120">Connessione a un'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="ce17d-120">Connecting to an External Data Source</span></span>
 <span data-ttu-id="ce17d-121">Dopo che una connessione viene aggiunta a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> per stabilire una connessione all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ce17d-121">After a connection is added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="ce17d-122">Questo metodo viene chiamato in fase di progettazione e in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ce17d-122">This method is called at design time and at run time.</span></span> <span data-ttu-id="ce17d-123">Il componente deve stabilire una connessione alla gestione connessione specificata dalla connessione di runtime e, successivamente, all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ce17d-123">The component must establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span> <span data-ttu-id="ce17d-124">Una volta stabilita, la connessione deve essere memorizzata nella cache interna dal componente e rilasciata quando viene chiamato il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-124">Once established, the component should cache the connection internally and release it when <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> is called.</span></span> <span data-ttu-id="ce17d-125">Gli sviluppatori eseguono l'override di questo metodo e rilasciano la connessione stabilita dal componente durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="ce17d-126">Entrambi questi metodi, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, vengono chiamati in fase di progettazione e in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ce17d-126">Both of these methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, are called at design time and at run time.</span></span>

 <span data-ttu-id="ce17d-127">Nell'esempio di codice seguente è illustrato un componente che si connette a una connessione ADO.NET nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, quindi chiude la connessione in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-127">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method, and then closes the connection in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

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
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) = False Then

        Dim cm As ConnectionManager = DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject,ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If IsNothing(sqlConnection) = False And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="ce17d-128">Convalida del componente</span><span class="sxs-lookup"><span data-stu-id="ce17d-128">Validating the Component</span></span>
 <span data-ttu-id="ce17d-129">Gli sviluppatori di componenti di destinazione devono eseguire la convalida come descritto in [Convalida del componente](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ce17d-129">Destination component developers should perform validation as described in [Component Validation](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span> <span data-ttu-id="ce17d-130">Devono inoltre verificare che le proprietà del tipo di dati delle colonne definite nella raccolta di colonne di input del componente corrispondano alle colonne nell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ce17d-130">In addition, they should verify that the data type properties of the columns defined in the component's input column collection match the columns at the external data source.</span></span> <span data-ttu-id="ce17d-131">A volte, la verifica delle colonne di input rispetto all'origine dati esterna può essere impossibile o indesiderata, ad esempio quando il componente o Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] è in uno stato disconnesso o quando i round trip al server non sono accettabili.</span><span class="sxs-lookup"><span data-stu-id="ce17d-131">At times, verifying the input columns against the external data source can be impossible or undesirable, such as when the component or the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is in a disconnected state, or when round trips to the server are not acceptable.</span></span> <span data-ttu-id="ce17d-132">In queste situazioni, le colonne nella raccolta di colonne di input possono comunque essere convalidate tramite <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> dell'oggetto di output.</span><span class="sxs-lookup"><span data-stu-id="ce17d-132">In these situations, the columns in the input column collection can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> of the input object.</span></span>

 <span data-ttu-id="ce17d-133">Questa raccolta esiste sia negli oggetti di input che di output e deve essere popolata dallo sviluppatore di componenti dalle colonne dell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ce17d-133">This collection exists on both input and output objects and must be populated by the component developer from the columns at the external data source.</span></span> <span data-ttu-id="ce17d-134">È possibile utilizzare questa raccolta per convalidare le colonne di input quando Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] è offline, quando il componente è disconnesso o quando la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="ce17d-134">This collection can be used to validate the input columns when the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>

 <span data-ttu-id="ce17d-135">Nel codice di esempio seguente viene aggiunta una colonna di metadati esterna basata su una colonna di input esistente.</span><span class="sxs-lookup"><span data-stu-id="ce17d-135">The following sample code adds an external metadata column based on an existing input column.</span></span>

```csharp
private void AddExternalMetaDataColumn(IDTSInput100 input,IDTSInputColumn100 inputColumn)
{
    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = input.ExternalMetadataColumnCollection.New();
    externalColumn.Name = inputColumn.Name;
    externalColumn.Precision = inputColumn.Precision;
    externalColumn.Length = inputColumn.Length;
    externalColumn.DataType = inputColumn.DataType;
    externalColumn.Scale = inputColumn.Scale;

    // Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID;
}
```

```vb
Private Sub AddExternalMetaDataColumn(ByVal input As IDTSInput100, ByVal inputColumn As IDTSInputColumn100)

    ' Set the properties of the external metadata column.
    Dim externalColumn As IDTSExternalMetadataColumn100 = input.ExternalMetadataColumnCollection.New()
    externalColumn.Name = inputColumn.Name
    externalColumn.Precision = inputColumn.Precision
    externalColumn.Length = inputColumn.Length
    externalColumn.DataType = inputColumn.DataType
    externalColumn.Scale = inputColumn.Scale

    ' Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID

End Sub
```

## <a name="run-time"></a><span data-ttu-id="ce17d-136">Fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="ce17d-136">Run Time</span></span>
 <span data-ttu-id="ce17d-137">Durante l'esecuzione il componente di destinazione riceve una chiamata al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> ogni volta che il componente a monte rende disponibile un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> pieno.</span><span class="sxs-lookup"><span data-stu-id="ce17d-137">During execution, the destination component receives a call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method each time a full <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> is available from the upstream component.</span></span> <span data-ttu-id="ce17d-138">Questo metodo viene chiamato più volte finché non sono più disponibili buffer e la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="ce17d-138">This method is called repeatedly until there are no more buffers available and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="ce17d-139">Durante questo metodo, i componenti di destinazione leggono le colonne e le righe nel buffer e le aggiungono all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ce17d-139">During this method, destination components read columns and rows in the buffer, and add them to the external data source.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="ce17d-140">Individuazione di colonne nel buffer</span><span class="sxs-lookup"><span data-stu-id="ce17d-140">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="ce17d-141">Il buffer di input per un componente contiene tutte le colonne definite nelle raccolte di colonne di output dei componenti a monte del componente nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="ce17d-141">The input buffer for a component contains all the columns defined in the output column collections of the components upstream from the component in the data flow.</span></span> <span data-ttu-id="ce17d-142">Se ad esempio un componente di origine prevede tre colonne nel relativo output e il componente successivo aggiunge un'altra colonna di output, il buffer fornito al componente di destinazione contiene quattro colonne, anche se quest'ultimo ne scriverà solo due.</span><span class="sxs-lookup"><span data-stu-id="ce17d-142">For example, if a source component provides three columns in its output, and the next component adds an additional output column, the buffer provided to the destination component contains four columns, even if the destination component will write only two columns.</span></span>

 <span data-ttu-id="ce17d-143">L'ordine delle colonne nel buffer di input non è definito dall'indice della colonna di output nella raccolta di colonne di input del componente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ce17d-143">The order of the columns in the input buffer is not defined by the index of the column in the input column collection of the destination component.</span></span> <span data-ttu-id="ce17d-144">Le colonne possono essere individuate in modo affidabile in una riga del buffer solo tramite il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-144">Columns can be reliably located in a buffer row only by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="ce17d-145">Questo metodo individua la colonna con l'ID di derivazione specificato nel buffer specificato, quindi restituisce la relativa posizione nella riga.</span><span class="sxs-lookup"><span data-stu-id="ce17d-145">This method locates the column that has the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="ce17d-146">Gli indici delle colonne di input vengono in genere individuati durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> e vengono memorizzati nella cache dallo sviluppatore per un utilizzo successivo durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-146">The indexes of the input columns are typically located during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and cached by the developer for use later during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>

 <span data-ttu-id="ce17d-147">Nell'esempio di codice seguente viene individuata la posizione delle colonne di input nel buffer di output durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> e tali colonne vengono archiviate in una matrice.</span><span class="sxs-lookup"><span data-stu-id="ce17d-147">The following code example finds the location of the input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> and stores them in an array.</span></span> <span data-ttu-id="ce17d-148">La matrice viene in seguito utilizzata durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> per leggere i valori delle colonne nel buffer.</span><span class="sxs-lookup"><span data-stu-id="ce17d-148">The array is subsequently used during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> to read the values of the columns in the buffer.</span></span>

```csharp
int[] cols;

public override void PreExecute()
{
    IDTSInput100 input = ComponentMetaData.InputCollection[0];

    cols = new int[input.InputColumnCollection.Count];

    for (int x = 0; x < input.InputColumnCollection.Count; x++)
    {
        cols[x] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[x].LineageID);
    }
}
```

```vb
Private cols As Integer()

Public Overrides Sub PreExecute()

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)

    ReDim cols(input.InputColumnCollection.Count)

    For x As Integer = 0 To input.InputColumnCollection.Count

        cols(x) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(x).LineageID)
    Next x

End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="ce17d-149">Elaborazione di righe</span><span class="sxs-lookup"><span data-stu-id="ce17d-149">Processing Rows</span></span>
 <span data-ttu-id="ce17d-150">Una volta individuate nel buffer, le colonne di input possono essere lette e scritte nell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ce17d-150">Once the input columns have been located in the buffer, they can be read and written to the external data source.</span></span>

 <span data-ttu-id="ce17d-151">Mentre il componente di destinazione scrive le righe nell'origine dati esterna, è possibile aggiornare i contatori delle prestazioni "Righe lette" o "Byte BLOB letti" chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-151">While the destination component writes rows to the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="ce17d-152">Per altre informazioni, vedere [i contatori delle prestazioni](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="ce17d-152">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="ce17d-153">Nell'esempio di codice seguente è illustrato un componente che legge righe dal buffer fornito in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce17d-153">The following example shows a component that reads rows from the buffer provided in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="ce17d-154">Gli indici delle colonne nel buffer sono stati individuati durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> nell'esempio di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="ce17d-154">The indexes of the columns in the buffer were located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the preceding code example.</span></span>

```csharp
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
        while (buffer.NextRow())
        {
            foreach (int col in cols)
            {
                if (!buffer.IsNull(col))
                {
                    //  TODO: Read the column data.
                }
            }
        }
}
```

```vb
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

        While (buffer.NextRow())

            For Each col As Integer In cols

                If buffer.IsNull(col) = False Then

                    '  TODO: Read the column data.
                End If

            Next col
        End While
End Sub
```

## <a name="sample"></a><span data-ttu-id="ce17d-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce17d-155">Sample</span></span>
 <span data-ttu-id="ce17d-156">Nell'esempio seguente è illustrato un componente di destinazione semplice che utilizza una gestione connessione file per salvare dati binari dal flusso di dati in file.</span><span class="sxs-lookup"><span data-stu-id="ce17d-156">The following sample shows a simple destination component that uses a File connection manager to save binary data from the data flow into files.</span></span> <span data-ttu-id="ce17d-157">Nell'esempio non vengono dimostrati tutti i metodi e le funzionalità descritti nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="ce17d-157">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="ce17d-158">Vengono descritti i metodi importanti di cui ogni componente di destinazione personalizzato deve eseguire l'override, ma non è incluso codice per la convalida in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ce17d-158">It demonstrates the important methods that every custom destination component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace BlobDst
{
  [DtsPipelineComponent(DisplayName = "BLOB Extractor Destination", Description = "Writes values of BLOB columns to files")]
  public class BlobDst : PipelineComponent
  {
    string m_DestDir;
    int m_FileNameColumnIndex = -1;
    int m_BlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection.New();
      input.Name = "BLOB Extractor Destination Input";
      input.HasSideEffects = true;

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_DestDir = (string)conn.ConnectionManager.AcquireConnection(null);

      if (m_DestDir.Length > 0 && m_DestDir[m_DestDir.Length - 1] != '\\')
        m_DestDir += "\\";
    }

    public override IDTSInputColumn100 SetUsageType(int inputID, IDTSVirtualInput100 virtualInput, int lineageID, DTSUsageType usageType)
    {
      IDTSInputColumn100 inputColumn = base.SetUsageType(inputID, virtualInput, lineageID, usageType);
      IDTSCustomProperty100 custProp;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsFileName";
      custProp.Value = (object)false;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsBLOB";
      custProp.Value = (object)false;

      return inputColumn;
    }

    public override void PreExecute()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection[0];
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;
      IDTSCustomProperty100 custProp;

      foreach (IDTSInputColumn100 column in inputColumns)
      {
        custProp = column.CustomPropertyCollection["IsFileName"];
        if ((bool)custProp.Value == true)
        {
          m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }

        custProp = column.CustomPropertyCollection["IsBLOB"];
        if ((bool)custProp.Value == true)
        {
          m_BlobColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }
      }
    }

    public override void ProcessInput(int inputID, PipelineBuffer buffer)
    {
      while (buffer.NextRow())
      {
        string strFileName = buffer.GetString(m_FileNameColumnIndex);
        int blobLength = (int)buffer.GetBlobLength(m_BlobColumnIndex);
        byte[] blobData = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength);

        strFileName = TranslateFileName(strFileName);

        // Make sure directory exists before creating file.
        FileInfo fi = new FileInfo(strFileName);
        if (!fi.Directory.Exists)
          fi.Directory.Create();

        // Write the data to the file.
        FileStream fs = new FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None);
        fs.Write(blobData, 0, blobLength);
        fs.Close();
      }
    }

    private string TranslateFileName(string fileName)
    {
      if (fileName.Length > 2 && fileName[1] == ':')
        return m_DestDir + fileName.Substring(3, fileName.Length - 3);
      else
        return m_DestDir + fileName;
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Namespace BlobDst 

 <DtsPipelineComponent(DisplayName="BLOB Extractor Destination", Description="Writes values of BLOB columns to files")> _ 
 Public Class BlobDst 
 Inherits PipelineComponent 
   Private m_DestDir As String 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_BlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New 
     input.Name = "BLOB Extractor Destination Input" 
     input.HasSideEffects = True 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_DestDir = CType(conn.ConnectionManager.AcquireConnection(Nothing), String) 
     If m_DestDir.Length > 0 AndAlso Not (m_DestDir(m_DestDir.Length - 1) = "\"C) Then 
       m_DestDir += "\" 
     End If 
   End Sub 

   Public  Overrides Function SetUsageType(ByVal inputID As Integer, ByVal virtualInput As IDTSVirtualInput100, ByVal lineageID As Integer, ByVal usageType As DTSUsageType) As IDTSInputColumn100 
     Dim inputColumn As IDTSInputColumn100 = MyBase.SetUsageType(inputID, virtualInput, lineageID, usageType) 
     Dim custProp As IDTSCustomProperty100 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsFileName" 
     custProp.Value = CType(False, Object) 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsBLOB" 
     custProp.Value = CType(False, Object) 
     Return inputColumn 
   End Function 

   Public  Overrides Sub PreExecute() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0) 
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection 
     Dim custProp As IDTSCustomProperty100 
     For Each column As IDTSInputColumn100 In inputColumns 
       custProp = column.CustomPropertyCollection("IsFileName") 
       If CType(custProp.Value, Boolean) = True Then 
         m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
       custProp = column.CustomPropertyCollection("IsBLOB") 
       If CType(custProp.Value, Boolean) = True Then 
         m_BlobColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
     Next 
   End Sub 

   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
     While buffer.NextRow 
       Dim strFileName As String = buffer.GetString(m_FileNameColumnIndex) 
       Dim blobLength As Integer = CType(buffer.GetBlobLength(m_BlobColumnIndex), Integer) 
       Dim blobData As Byte() = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength) 
       strFileName = TranslateFileName(strFileName) 
       Dim fi As FileInfo = New FileInfo(strFileName) 
       ' Make sure directory exists before creating file.
       If Not fi.Directory.Exists Then 
         fi.Directory.Create 
       End If 
       ' Write the data to the file.
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None) 
       fs.Write(blobData, 0, blobLength) 
       fs.Close 
     End While 
   End Sub 

   Private Function TranslateFileName(ByVal fileName As String) As String 
     If fileName.Length > 2 AndAlso fileName(1) = ":"C Then 
       Return m_DestDir + fileName.Substring(3, fileName.Length - 3) 
     Else 
       Return m_DestDir + fileName 
     End If 
   End Function 
 End Class 
End Namespace
```

<span data-ttu-id="ce17d-159">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ce17d-159">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ce17d-160">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="ce17d-160">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ce17d-161">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="ce17d-161">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ce17d-162">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="ce17d-162">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce17d-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce17d-163">See Also</span></span>
 <span data-ttu-id="ce17d-164">[Sviluppo di un componente di origine personalizzato](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [creazione di una destinazione con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="ce17d-164">[Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span></span>


