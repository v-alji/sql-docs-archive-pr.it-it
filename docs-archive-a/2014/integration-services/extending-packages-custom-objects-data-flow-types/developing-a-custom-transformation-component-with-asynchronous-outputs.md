---
title: Sviluppo di un componente di trasformazione personalizzato con output asincroni | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom data flow components [Integration Services], transformation components
- asynchronous outputs [Integration Services]
- ProcessInput method
- cache [Integration Services]
- buffer allocations [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], transformation components
ms.assetid: 1c3e92c7-a4fa-4fdd-b9ca-ac3069536274
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41e2ecdf9f90765e75ff2b8c9c0681a25366e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721636"
---
# <a name="developing-a-custom-transformation-component-with-asynchronous-outputs"></a><span data-ttu-id="63467-102">Sviluppo di un componente di trasformazione personalizzato con output asincroni</span><span class="sxs-lookup"><span data-stu-id="63467-102">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>
  <span data-ttu-id="63467-103">Utilizzare un componente con output asincroni quando una trasformazione non può inviare righe all'output prima che il componente non abbia ricevuto tutte le righe di input oppure quando la trasformazione non produce esattamente una riga di output per ogni riga ricevuta come input.</span><span class="sxs-lookup"><span data-stu-id="63467-103">You use a component with asynchronous outputs when a transform cannot output rows until the component has received all its input rows, or when the transformation does not produce exactly one output row for each row received as input.</span></span> <span data-ttu-id="63467-104">La trasformazione Aggregazione, ad esempio, non può calcolare una somma tra righe prima di aver letto tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="63467-104">The Aggregate transformation, for example, cannot calculate a sum across rows until it has read all the rows.</span></span> <span data-ttu-id="63467-105">Viceversa, è possibile utilizzare un componente con output sincroni quando si modifica ogni riga di dati passata.</span><span class="sxs-lookup"><span data-stu-id="63467-105">In contrast, you can use a component with synchronous outputs any time when you modify each row of data as it passes through.</span></span> <span data-ttu-id="63467-106">È possibile modificare i dati per ogni riga sul posto oppure creare una o più nuove colonne aggiuntive, ognuna delle quali con un valore per ogni riga di input.</span><span class="sxs-lookup"><span data-stu-id="63467-106">You can modify the data for each row in place, or you can create one or more new columns, each of which has a value for every one of the input rows.</span></span> <span data-ttu-id="63467-107">Per altre informazioni sulla differenza tra componenti sincroni e asincroni, vedere [Informazioni sulle trasformazioni sincrone e asincrone](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="63467-107">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>

 <span data-ttu-id="63467-108">I componenti di trasformazione con output asincroni sono univoci, perché agiscono contemporaneamente da componenti di destinazione e di origine.</span><span class="sxs-lookup"><span data-stu-id="63467-108">Transformation components with asynchronous outputs are unique because they act as both destination and source components.</span></span> <span data-ttu-id="63467-109">Questo tipo di componente riceve righe dai componenti a monte e aggiunge righe che vengono utilizzate dai componenti a valle.</span><span class="sxs-lookup"><span data-stu-id="63467-109">This kind of component receives rows from upstream components, and adds rows that are consumed by downstream components.</span></span> <span data-ttu-id="63467-110">Nessun altro componente del flusso di dati esegue entrambe queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="63467-110">No other data flow component performs both of these operations.</span></span>

 <span data-ttu-id="63467-111">Le colonne dei componenti a monte che sono disponibili per un componente con output sincroni sono automaticamente disponibili per i componenti a valle del componente.</span><span class="sxs-lookup"><span data-stu-id="63467-111">The columns from upstream components that are available to a component with synchronous outputs are automatically available to components downstream from the component.</span></span> <span data-ttu-id="63467-112">Pertanto, un componente con output sincroni non deve necessariamente definire colonne di output per fornire colonne e righe al componente successivo.</span><span class="sxs-lookup"><span data-stu-id="63467-112">Therefore, a component with synchronous outputs does not have to define any output columns to provide columns and rows to the next component.</span></span> <span data-ttu-id="63467-113">I componenti con output asincroni, al contrario, devono definire colonne di output e fornire righe ai componenti a valle.</span><span class="sxs-lookup"><span data-stu-id="63467-113">Components with asynchronous outputs, on the other hand, must define output columns and provide rows to downstream components.</span></span> <span data-ttu-id="63467-114">Pertanto, un componente con output asincroni deve eseguire più attività durante la fase di progettazione e di esecuzione, mentre lo sviluppatore deve implementare più codice.</span><span class="sxs-lookup"><span data-stu-id="63467-114">Therefore a component with asynchronous outputs has more tasks to perform during both design and execution time, and the component developer has more code to implement.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="63467-115">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include diverse trasformazioni con output asincroni.</span><span class="sxs-lookup"><span data-stu-id="63467-115">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contains several transformations with asynchronous outputs.</span></span> <span data-ttu-id="63467-116">La trasformazione Ordinamento, ad esempio, richiede che tutte le righe siano presenti al fine di poter essere ordinate e ottiene tale risultato tramite output asincroni.</span><span class="sxs-lookup"><span data-stu-id="63467-116">For example, the Sort transformation requires all its rows before it can sort them, and achieves this by using asynchronous outputs.</span></span> <span data-ttu-id="63467-117">Dopo aver ricevuto tutte le righe, la trasformazione le ordina e le aggiunge all'output.</span><span class="sxs-lookup"><span data-stu-id="63467-117">After it has received all its rows, it sorts them and adds them to its output.</span></span>

 <span data-ttu-id="63467-118">In questa sezione viene illustrato in dettaglio come sviluppare trasformazioni con output asincroni.</span><span class="sxs-lookup"><span data-stu-id="63467-118">This section explains in detail how to develop transformations with asynchronous outputs.</span></span> <span data-ttu-id="63467-119">Per altre informazioni sullo sviluppo di componenti di origine, vedere [Sviluppo di un componente di origine personalizzato](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="63467-119">For more information about source component development, see [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="63467-120">Fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="63467-120">Design Time</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="63467-121">Creazione del componente</span><span class="sxs-lookup"><span data-stu-id="63467-121">Creating the Component</span></span>
 <span data-ttu-id="63467-122">La proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> sull'oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> identifica se un output è sincrono o asincrono.</span><span class="sxs-lookup"><span data-stu-id="63467-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property on the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object identifies whether an output is synchronous or asynchronous.</span></span> <span data-ttu-id="63467-123">Per creare un output asincrono, aggiungere l'output al componente e impostare <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> su zero.</span><span class="sxs-lookup"><span data-stu-id="63467-123">To create an asynchronous output, add the output to the component and set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> to zero.</span></span> <span data-ttu-id="63467-124">L'impostazione di questa proprietà determina anche se l'attività Flusso di dati alloca oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> sia per l'input che per l'output del componente o se viene allocato un singolo buffer condiviso tra i due oggetti.</span><span class="sxs-lookup"><span data-stu-id="63467-124">Setting this property also determines whether the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects for both the input and output of the component, or whether a single buffer is allocated and shared between the two objects.</span></span>

 <span data-ttu-id="63467-125">Nel codice di esempio seguente è illustrato un componente che crea un output asincrono nell'implementazione di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="63467-125">The following sample code shows a component that creates an asynchronous output in its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> implementation.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "AsyncComponent",ComponentType = ComponentType.Transform)]
    public class AsyncComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Call the base class, which adds a synchronous input
            // and output.
            base.ProvideComponentProperties();

            // Make the output asynchronous.
            IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
            output.SynchronousInputID = 0;
        }
    }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

<DtsPipelineComponent(DisplayName:="AsyncComponent", ComponentType:=ComponentType.Transform)> _
Public Class AsyncComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Call the base class, which adds a synchronous input
        ' and output.
        Me.ProvideComponentProperties()

        ' Make the output asynchronous.
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
        output.SynchronousInputID = 0

    End Sub

End Class
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="63467-126">Creazione e configurazione di colonne di output</span><span class="sxs-lookup"><span data-stu-id="63467-126">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="63467-127">Come accennato in precedenza, un componente asincrono aggiunge colonne alla propria raccolta di colonne di output per fornire colonne ai componenti a valle.</span><span class="sxs-lookup"><span data-stu-id="63467-127">As mentioned earlier, an asynchronous component adds columns to its output column collection to provide columns to downstream components.</span></span> <span data-ttu-id="63467-128">Sono disponibili diversi metodi della fase di progettazione tra cui scegliere, a seconda dei requisiti del componente.</span><span class="sxs-lookup"><span data-stu-id="63467-128">There are several design-time methods to choose from, depending on the needs of the component.</span></span> <span data-ttu-id="63467-129">Se ad esempio si desidera passare tutte le colonne dai componenti a monte ai componenti a valle, è necessario eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> per aggiungere le colonne, perché si tratta del primo metodo in cui le colonne di input sono disponibili per il componente.</span><span class="sxs-lookup"><span data-stu-id="63467-129">For example, if you want to pass all the columns from the upstream components to the downstream components, you would override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> method to add the columns, because this is the first method in which the input columns are available to the component.</span></span>

 <span data-ttu-id="63467-130">Se il componente crea colonne di output in base alle colonne selezionate per il proprio input, eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> per selezionare le colonne di output e indicare come verranno utilizzate.</span><span class="sxs-lookup"><span data-stu-id="63467-130">If the component creates output columns based on the columns selected for its input, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> method to select the output columns and to indicate how they will be used.</span></span>

 <span data-ttu-id="63467-131">Se un componente con output asincroni crea colonne di output in base alle colonne dei componenti a monte e le colonne disponibili a valle cambiano, il componente deve aggiornare la propria raccolta di colonne di output.</span><span class="sxs-lookup"><span data-stu-id="63467-131">If a component with asynchronous outputs creates output columns based on the columns from upstream components, and the available upstream columns change, the component should update its output column collection.</span></span> <span data-ttu-id="63467-132">Queste modifiche devono essere rilevate dal componente durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> e corrette durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="63467-132">These changes should be detected by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and fixed during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span></span>

> [!NOTE]
>  <span data-ttu-id="63467-133">Quando una colonna di output viene rimossa dalla raccolta di colonne di output, i componenti a valle del flusso di dati che fanno riferimento a tale colonna possono essere influenzati negativamente.</span><span class="sxs-lookup"><span data-stu-id="63467-133">When an output column is removed from the output column collection, downstream components in the data flow that reference the column are adversely affected.</span></span> <span data-ttu-id="63467-134">È necessario correggere la colonna di output senza rimuoverla e ricrearla per evitare l'interruzione dei componenti a valle.</span><span class="sxs-lookup"><span data-stu-id="63467-134">The output column must be repaired without removing and recreating the column to prevent breaking the downstream components.</span></span> <span data-ttu-id="63467-135">Se ad esempio il tipo di dati della colonna è stato modificato, è necessario aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="63467-135">For example, if the data type of the column has changed, you must update the data type.</span></span>

 <span data-ttu-id="63467-136">Nell'esempio di codice seguente è illustrato un componente che aggiunge una colonna di output alla propria raccolta di colonne di output per ogni colonna disponibile del componente a monte.</span><span class="sxs-lookup"><span data-stu-id="63467-136">The following code example shows a component that adds an output column to its output column collection for each column available from the upstream component.</span></span>

```csharp
public override void OnInputPathAttached(int inputID)
{
   IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);
   IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
   IDTSVirtualInput100 vInput = input.GetVirtualInput();

   foreach (IDTSVirtualInputColumn100 vCol in vInput.VirtualInputColumnCollection)
   {
      IDTSOutputColumn100 outCol = output.OutputColumnCollection.New();
      outCol.Name = vCol.Name;
      outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage);
   }
}
```

```vb
Public Overrides Sub OnInputPathAttached(ByVal inputID As Integer)

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput()

    For Each vCol As IDTSVirtualInputColumn100 In vInput.VirtualInputColumnCollection

        Dim outCol As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        outCol.Name = vCol.Name
        outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage)

    Next
End Sub
```

## <a name="run-time"></a><span data-ttu-id="63467-137">Fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="63467-137">Run Time</span></span>
 <span data-ttu-id="63467-138">I componenti con output asincroni eseguono anche una sequenza di metodi della fase di esecuzione diversa rispetto agli altri tipi di componenti.</span><span class="sxs-lookup"><span data-stu-id="63467-138">Components with asynchronous outputs also execute a different sequence of methods at run time than other types of components.</span></span> <span data-ttu-id="63467-139">Innanzitutto, si tratta degli unici componenti che ricevono una chiamata ai metodi <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="63467-139">First, they are the only components that receive a call to both the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="63467-140">I componenti con output asincroni richiedono inoltre l'accesso a tutte le righe in ingresso prima che possano iniziare l'elaborazione. Pertanto, devono memorizzare le righe di input nella cache interna finché non sono state lette tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="63467-140">Components with asynchronous outputs also require access to all the incoming rows before they can start processing; therefore, they must cache the input rows internally until all rows have been read.</span></span> <span data-ttu-id="63467-141">Infine, a differenza di altri componenti, i componenti con output asincroni ricevono sia un buffer di input che un buffer di output.</span><span class="sxs-lookup"><span data-stu-id="63467-141">Finally, unlike other components, components with asynchronous outputs receive both an input buffer and an output buffer.</span></span>

### <a name="understanding-the-buffers"></a><span data-ttu-id="63467-142">Informazioni sui buffer</span><span class="sxs-lookup"><span data-stu-id="63467-142">Understanding the Buffers</span></span>
 <span data-ttu-id="63467-143">Il componente riceve il buffer di input durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="63467-143">The input buffer is received by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="63467-144">Questo buffer contiene le righe aggiunte dai componenti a monte.</span><span class="sxs-lookup"><span data-stu-id="63467-144">This buffer contains the rows added to the buffer by upstream components.</span></span> <span data-ttu-id="63467-145">Contiene inoltre le colonne dell'input del componente, oltre alle colonne fornite nell'output di un componente a monte ma che non sono state aggiunte alla raccolta di input del componente asincrono.</span><span class="sxs-lookup"><span data-stu-id="63467-145">The buffer also contains the columns of the component's input, in addition to the columns that were provided in the output of an upstream component but were not added to the asynchronous component's input collection.</span></span>

 <span data-ttu-id="63467-146">Il buffer di output, fornito al componente in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, inizialmente non contiene righe.</span><span class="sxs-lookup"><span data-stu-id="63467-146">The output buffer, which is provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, does not initially contain rows.</span></span> <span data-ttu-id="63467-147">Il componente aggiunge righe a questo buffer e lo fornisce ai componenti a valle quando è pieno.</span><span class="sxs-lookup"><span data-stu-id="63467-147">The component adds rows to this buffer and provides the buffer to downstream components when it is full.</span></span> <span data-ttu-id="63467-148">Il buffer di output contiene le colonne definite nella raccolta di colonne di output del componente, oltre alle eventuali colonne aggiunte da altri componenti a valle ai propri output.</span><span class="sxs-lookup"><span data-stu-id="63467-148">The output buffer contains the columns defined in the component's output column collection, in addition to any columns that other downstream components have added to their outputs.</span></span>

 <span data-ttu-id="63467-149">Questo comportamento è diverso da quello dei componenti con output sincroni, che ricevono un singolo buffer condiviso.</span><span class="sxs-lookup"><span data-stu-id="63467-149">This is different behavior from that of components with synchronous outputs, which receive a single shared buffer.</span></span> <span data-ttu-id="63467-150">Il buffer condiviso di un componente con output sincroni contiene sia le colonne di input che di output del componente, oltre alle colonne aggiunte agli output dei componenti a monte e a valle.</span><span class="sxs-lookup"><span data-stu-id="63467-150">The shared buffer of a component with synchronous outputs contains both the input and output columns of the component, in addition to columns added to the outputs of upstream and downstream components.</span></span>

### <a name="processing-rows"></a><span data-ttu-id="63467-151">Elaborazione di righe</span><span class="sxs-lookup"><span data-stu-id="63467-151">Processing Rows</span></span>

#### <a name="caching-input-rows"></a><span data-ttu-id="63467-152">Memorizzazione nella cache di righe di input</span><span class="sxs-lookup"><span data-stu-id="63467-152">Caching Input Rows</span></span>
 <span data-ttu-id="63467-153">Quando si scrive un componente con output asincroni, è possibile scegliere tra tre diversi modi per aggiungere righe al buffer di output.</span><span class="sxs-lookup"><span data-stu-id="63467-153">When you write a component with asynchronous outputs, you have three options for adding rows to the output buffer.</span></span> <span data-ttu-id="63467-154">È possibile aggiungerle non appena vengono ricevute righe di input, memorizzarle nella cache finché il componente non ha ricevuto tutte le righe dal componente a monte oppure aggiungerle quando è appropriato per il componente.</span><span class="sxs-lookup"><span data-stu-id="63467-154">You can add them as input rows are received, you can cache them until the component has received all the rows from the upstream component, or you can add them when it is appropriate to do so for the component.</span></span> <span data-ttu-id="63467-155">Il metodo scelto dipende dai requisiti del componente.</span><span class="sxs-lookup"><span data-stu-id="63467-155">The method that you choose depends on the requirements of the component.</span></span> <span data-ttu-id="63467-156">Ad esempio, il componente Ordinamento richiede che tutte le righe a monte vengano ricevute prima che sia possibile ordinarle.</span><span class="sxs-lookup"><span data-stu-id="63467-156">For example, the Sort component requires that all the upstream rows be received before they can be sorted.</span></span> <span data-ttu-id="63467-157">Pertanto, attende che vengano lette tutte le righe prima di aggiungere righe al buffer di output.</span><span class="sxs-lookup"><span data-stu-id="63467-157">Therefore, it waits until all rows have been read before adding rows to the output buffer.</span></span>

 <span data-ttu-id="63467-158">Il componente deve memorizzare nella cache interna le righe ricevute nel buffer di input finché non è pronto a elaborarle.</span><span class="sxs-lookup"><span data-stu-id="63467-158">The rows that are received in the input buffer must be cached internally by the component until it is ready to process them.</span></span> <span data-ttu-id="63467-159">Le righe del buffer in ingresso possono essere memorizzate nella cache in una tabella di dati, una matrice multidimensionale o qualsiasi altra struttura interna.</span><span class="sxs-lookup"><span data-stu-id="63467-159">The incoming buffer rows can be cached in a data table, a multidimensional array, or any other internal structure.</span></span>

#### <a name="adding-output-rows"></a><span data-ttu-id="63467-160">Aggiunta di righe di output</span><span class="sxs-lookup"><span data-stu-id="63467-160">Adding Output Rows</span></span>
 <span data-ttu-id="63467-161">Sia che le righe vengano aggiunte al buffer di output non appena vengono ricevute o dopo la ricezione di tutte, questa operazione viene eseguita chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> sul buffer di output.</span><span class="sxs-lookup"><span data-stu-id="63467-161">Whether you add rows to the output buffer as they are received or after receiving all of the rows, you do so by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method on the output buffer.</span></span> <span data-ttu-id="63467-162">Dopo aver aggiunto la nuova riga, impostare i valori di ogni colonna al suo interno.</span><span class="sxs-lookup"><span data-stu-id="63467-162">After you have added the row, you set the values of each column in the new row.</span></span>

 <span data-ttu-id="63467-163">Poiché a volte il buffer di output contiene più colonne rispetto alla raccolta di colonne di output del componente, è necessario individuare l'indice della colonna appropriata nel buffer prima di impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="63467-163">Because there are sometimes more columns in the output buffer than in the output column collection of the component, you must locate the index of the appropriate column in the buffer before you can set its value.</span></span> <span data-ttu-id="63467-164">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> restituisce l'indice della colonna nella riga del buffer con l'ID di derivazione specificato, che viene quindi utilizzato per assegnare il valore alla colonna di buffer.</span><span class="sxs-lookup"><span data-stu-id="63467-164">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property returns the index of the column in the buffer row with the specified lineage ID, which is then used to assign the value to the buffer column.</span></span>

 <span data-ttu-id="63467-165">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, chiamato prima del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> o del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, è il primo metodo in cui è disponibile la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> e rappresenta la prima opportunità per individuare gli indici delle colonne dei buffer di input e di output.</span><span class="sxs-lookup"><span data-stu-id="63467-165">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, which is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method or the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, is the first method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property is available, and the first opportunity to locate the indexes of the columns in the input and output buffers.</span></span>

## <a name="sample"></a><span data-ttu-id="63467-166">Esempio</span><span class="sxs-lookup"><span data-stu-id="63467-166">Sample</span></span>
 <span data-ttu-id="63467-167">Nell'esempio seguente è illustrato un componente di trasformazione semplice con output asincroni che aggiunge righe al buffer di output non appena vengono ricevute.</span><span class="sxs-lookup"><span data-stu-id="63467-167">The following sample shows a simple transformation component with asynchronous outputs that adds rows to the output buffer as they are received.</span></span> <span data-ttu-id="63467-168">Nell'esempio non vengono dimostrati tutti i metodi e le funzionalità descritti nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="63467-168">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="63467-169">Vengono descritti i metodi importanti di cui ogni componente di trasformazione personalizzato con output asincroni deve eseguire l'override, ma non è incluso codice per la convalida in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="63467-169">It demonstrates the important methods that every custom transformation component with asynchronous outputs must override, but does not contain code for design-time validation.</span></span> <span data-ttu-id="63467-170">Inoltre, nel codice del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> si presuppone che nella raccolta di colonne di output sia inclusa un'unica colonna per ogni colonna presente nella raccolta di colonne di input.</span><span class="sxs-lookup"><span data-stu-id="63467-170">Also, the code in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> assumes that the output column collection has one column for each column in the input column collection.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
   [DtsPipelineComponent(DisplayName = "AsynchronousOutput")]
   public class AsynchronousOutput : PipelineComponent
   {
      PipelineBuffer outputBuffer;
      int[] inputColumnBufferIndexes;
      int[] outputColumnBufferIndexes;

      public override void ProvideComponentProperties()
      {
         // Let the base class add the input and output objects.
         base.ProvideComponentProperties();

         // Name the input and output, and make the
         // output asynchronous.
         ComponentMetaData.InputCollection[0].Name = "Input";
         ComponentMetaData.OutputCollection[0].Name = "AsyncOutput";
         ComponentMetaData.OutputCollection[0].SynchronousInputID = 0;
      }
      public override void PreExecute()
      {
         IDTSInput100 input = ComponentMetaData.InputCollection[0];
         IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

         inputColumnBufferIndexes = new int[input.InputColumnCollection.Count];
         outputColumnBufferIndexes = new int[output.OutputColumnCollection.Count];

         for (int col = 0; col < input.InputColumnCollection.Count; col++)
            inputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[col].LineageID);

         for (int col = 0; col < output.OutputColumnCollection.Count; col++)
            outputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[col].LineageID);

      }

      public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
      {
         if (buffers.Length != 0)
            outputBuffer = buffers[0];
      }
      public override void ProcessInput(int inputID, PipelineBuffer buffer)
      {
            // Advance the buffer to the next row.
            while (buffer.NextRow())
            {
               // Add a row to the output buffer.
               outputBuffer.AddRow();
               for (int x = 0; x < inputColumnBufferIndexes.Length; x++)
               {
                  // Copy the data from the input buffer column to the output buffer column.
                  outputBuffer[outputColumnBufferIndexes[x]] = buffer[inputColumnBufferIndexes[x]];
               }
            }
         if (buffer.EndOfRowset)
         {
            // EndOfRowset on the input buffer is true.
            // Set EndOfRowset on the output buffer.
            outputBuffer.SetEndOfRowset();
         }
      }
   }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="AsynchronousOutput")> _
    Public Class AsynchronousOutput

        Inherits PipelineComponent

        Private outputBuffer As PipelineBuffer
        Private inputColumnBufferIndexes As Integer()
        Private outputColumnBufferIndexes As Integer()

        Public Overrides Sub ProvideComponentProperties()

            ' Let the base class add the input and output objects.
            Me.ProvideComponentProperties()

            ' Name the input and output, and make the
            ' output asynchronous.
            ComponentMetaData.InputCollection(0).Name = "Input"
            ComponentMetaData.OutputCollection(0).Name = "AsyncOutput"
            ComponentMetaData.OutputCollection(0).SynchronousInputID = 0
        End Sub

        Public Overrides Sub PreExecute()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)
            Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

            ReDim inputColumnBufferIndexes(input.InputColumnCollection.Count)
            ReDim outputColumnBufferIndexes(output.OutputColumnCollection.Count)

            For col As Integer = 0 To input.InputColumnCollection.Count
                inputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(col).LineageID)
            Next

            For col As Integer = 0 To output.OutputColumnCollection.Count
                outputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(col).LineageID)
            Next

        End Sub
        Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

            If buffers.Length <> 0 Then
                outputBuffer = buffers(0)
            End If

        End Sub

        Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

                ' Advance the buffer to the next row.
                While (buffer.NextRow())

                    ' Add a row to the output buffer.
                    outputBuffer.AddRow()
                    For x As Integer = 0 To inputColumnBufferIndexes.Length

                        ' Copy the data from the input buffer column to the output buffer column.
                        outputBuffer(outputColumnBufferIndexes(x)) = buffer(inputColumnBufferIndexes(x))

                    Next
                End While

            If buffer.EndOfRowset = True Then
                ' EndOfRowset on the input buffer is true.
                ' Set the end of row set on the output buffer.
                outputBuffer.SetEndOfRowset()
            End If
        End Sub
    End Class
End Namespace
```

<span data-ttu-id="63467-171">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="63467-171">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="63467-172">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="63467-172">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="63467-173">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="63467-173">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="63467-174">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="63467-174">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="63467-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63467-175">See Also</span></span>
 <span data-ttu-id="63467-176">[Sviluppo di un componente di trasformazione personalizzato con output sincroni](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [informazioni sulle trasformazioni sincrone e asincrone](../understanding-synchronous-and-asynchronous-transformations.md) [creazione di una trasformazione asincrona con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="63467-176">[Developing a Custom Transformation Component with Synchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span></span>


