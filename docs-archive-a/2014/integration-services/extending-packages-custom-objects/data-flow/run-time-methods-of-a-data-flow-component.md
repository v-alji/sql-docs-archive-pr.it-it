---
title: Metodi di runtime di un componente flusso di dati | Microsoft Docs
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
- run-time [Integration Services]
- data flow components [Integration Services], run-time methods
ms.assetid: fd9e4317-18dd-43af-bbdc-79db32183ac4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df0afe4c29044541c5a57aa3a466283ab4fe4fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718593"
---
# <a name="run-time-methods-of-a-data-flow-component"></a><span data-ttu-id="a9c95-102">Metodi di runtime di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="a9c95-102">Run-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="a9c95-103">In fase di esecuzione l'attività Flusso di dati esamina la sequenza di componenti, prepara un piano di esecuzione e gestisce un pool di thread di lavoro che eseguono il piano di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a9c95-103">At run time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="a9c95-104">L'attività carica righe di dati dalle origini, li elabora tramite trasformazioni, quindi li salva nelle destinazioni.</span><span class="sxs-lookup"><span data-stu-id="a9c95-104">The task loads rows of data from sources, processes them through transformations, then saves them to destinations.</span></span>  
  
## <a name="sequence-of-method-execution"></a><span data-ttu-id="a9c95-105">Sequenza di esecuzione dei metodi</span><span class="sxs-lookup"><span data-stu-id="a9c95-105">Sequence of Method Execution</span></span>  
 <span data-ttu-id="a9c95-106">Durante l'esecuzione di un componente del flusso di dati, viene chiamato un subset dei metodi nella classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-106">During the execution of a data flow component, a subset of the methods in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is called.</span></span> <span data-ttu-id="a9c95-107">I metodi, così come la sequenza con cui vengono chiamati, sono sempre gli stessi, ad eccezione dei metodi <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-107">The methods, and the sequence in which they are called, are always the same, with the exception of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="a9c95-108">Questi due metodi vengono chiamati in base all'esistenza e alla configurazione degli oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> e <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> di un componente.</span><span class="sxs-lookup"><span data-stu-id="a9c95-108">These two methods are called based on the existence and configuration of a component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects.</span></span>  
  
 <span data-ttu-id="a9c95-109">Nell'elenco seguente sono illustrati i metodi nell'ordine in cui vengono chiamati durante l'esecuzione del componente.</span><span class="sxs-lookup"><span data-stu-id="a9c95-109">The following list shows the methods in the order in which they are called during component execution.</span></span> <span data-ttu-id="a9c95-110">Si noti che <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, se chiamato, viene sempre chiamato prima di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-110">Note that <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, when called, is always called before <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrepareForExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PostExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Cleanup%2A>  
  
### <a name="primeoutput-method"></a><span data-ttu-id="a9c95-111">Metodo PrimeOutput</span><span class="sxs-lookup"><span data-stu-id="a9c95-111">PrimeOutput Method</span></span>  
 <span data-ttu-id="a9c95-112">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> viene chiamato quando un componente include almeno un output, connesso a un componente a valle tramite un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>, la cui proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> è zero.</span><span class="sxs-lookup"><span data-stu-id="a9c95-112">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called when a component has at least one output, attached to a downstream component through an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, and the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property of the output is zero.</span></span> <span data-ttu-id="a9c95-113">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> viene chiamato per i componenti di origine e per le trasformazioni con output asincroni.</span><span class="sxs-lookup"><span data-stu-id="a9c95-113">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called for source components and for transformations with asynchronous outputs.</span></span> <span data-ttu-id="a9c95-114">A differenza del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> descritto di seguito, il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> viene chiamato una sola volta per ogni componente che lo richiede.</span><span class="sxs-lookup"><span data-stu-id="a9c95-114">Unlike the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method described below, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is only called once for each component that requires it.</span></span>  
  
### <a name="processinput-method"></a><span data-ttu-id="a9c95-115">Metodo ProcessInput</span><span class="sxs-lookup"><span data-stu-id="a9c95-115">ProcessInput Method</span></span>  
 <span data-ttu-id="a9c95-116">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> viene chiamato per i componenti che includono almeno un input connesso a un componente a monte tramite un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for components that have at least one input attached to an upstream component by an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object.</span></span> <span data-ttu-id="a9c95-117">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> viene chiamato per i componenti di destinazione e per le trasformazioni con output sincroni.</span><span class="sxs-lookup"><span data-stu-id="a9c95-117">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for destination components and for transformations with synchronous outputs.</span></span> <span data-ttu-id="a9c95-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> viene chiamato ripetutamente finché non sono più disponibili righe da elaborare dei componenti a monte.</span><span class="sxs-lookup"><span data-stu-id="a9c95-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> is called repeatedly until there are no more rows to process from upstream components.</span></span>  
  
## <a name="working-with-inputs-and-outputs"></a><span data-ttu-id="a9c95-119">Utilizzo di input e output</span><span class="sxs-lookup"><span data-stu-id="a9c95-119">Working with Inputs and Outputs</span></span>  
 <span data-ttu-id="a9c95-120">In fase di esecuzione i componenti del flusso di dati eseguono le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9c95-120">At run time, data flow components perform the following tasks:</span></span>  
  
-   <span data-ttu-id="a9c95-121">I componenti di origine aggiungono righe.</span><span class="sxs-lookup"><span data-stu-id="a9c95-121">Source components add rows.</span></span>  
  
-   <span data-ttu-id="a9c95-122">I componenti di trasformazione con output sincroni ricevono le righe fornite dai componenti di origine.</span><span class="sxs-lookup"><span data-stu-id="a9c95-122">Transformation components with synchronous outputs receive rows provided by source components.</span></span>  
  
-   <span data-ttu-id="a9c95-123">I componenti di trasformazione con output asincroni ricevono e aggiungono righe.</span><span class="sxs-lookup"><span data-stu-id="a9c95-123">Transformation components with asynchronous outputs receive rows and add rows.</span></span>  
  
-   <span data-ttu-id="a9c95-124">I componenti di destinazione ricevono righe e quindi le caricano in una destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9c95-124">Destination components receive rows and then load them into a destination.</span></span>  
  
 <span data-ttu-id="a9c95-125">Durante l'esecuzione, l'attività Flusso di dati alloca oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> che contengono tutte le colonne definite nelle raccolte di colonne di output di una sequenza di componenti.</span><span class="sxs-lookup"><span data-stu-id="a9c95-125">During execution, the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain all the columns defined in the output column collections of a sequence of components.</span></span> <span data-ttu-id="a9c95-126">Ad esempio, se ognuno dei quattro componenti in una sequenza del flusso di dati aggiunge una colonna di output alla raccolta di colonne di output, il buffer fornito a ogni componente contiene quattro colonne, una per ogni colonna di output per componente.</span><span class="sxs-lookup"><span data-stu-id="a9c95-126">For example, if each of four components in a data flow sequence adds one output column to its output column collection,the buffer that is provided to each component contains four columns, one for each output column per component.</span></span> <span data-ttu-id="a9c95-127">A causa di questo comportamento, un componente a volte riceve buffer contenenti colonne che non utilizza.</span><span class="sxs-lookup"><span data-stu-id="a9c95-127">Because of this behavior, a component sometimes receives buffers that contain columns it does not use.</span></span>  
  
 <span data-ttu-id="a9c95-128">Poiché i buffer ricevuti dal componente possono contenere colonne che il componente non utilizzerà, è necessario individuare le colonne che si desidera utilizzare nelle raccolte di colonne di input e output del componente nel buffer fornito al componente dall'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="a9c95-128">Since the buffers received by your component may contain columns that the component will not use, you must locate the columns that you want to use in your component's input and output column collections in the buffer provided to the component by the data flow task.</span></span> <span data-ttu-id="a9c95-129">A tale scopo, utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-129">You do this by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property.</span></span> <span data-ttu-id="a9c95-130">Per motivi di prestazioni, questa attività viene in genere eseguita durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, anziché in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-130">For performance reasons, this task is ordinarily performed during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, rather than in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
 <span data-ttu-id="a9c95-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> viene chiamato prima dei metodi <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> e rappresenta la prima opportunità per un componente di eseguire questa operazione dopo che <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> diventa disponibile per il componente.</span><span class="sxs-lookup"><span data-stu-id="a9c95-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods, and is the first opportunity for a component to perform this work after the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> becomes available to the component.</span></span> <span data-ttu-id="a9c95-132">Durante questo metodo, il componente deve individuare le proprie colonne nei buffer e archiviare questa informazione internamente affinché le colonne possano essere utilizzate nei metodi <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> o <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-132">During this method, the component should locate its columns in the buffers and store this information internally so the columns can be used in either the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span>  
  
 <span data-ttu-id="a9c95-133">Nell'esempio di codice seguente viene illustrata la modalità con cui un componente di trasformazione con output sincroni individua le proprie colonne di input nel buffer durante <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-133">The following code example demonstrates how a transformation component with a synchronous output locates its input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span>  
  
```csharp  
private int []bufferColumnIndex;  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    bufferColumnIndex = new int[input.InputColumnCollection.Count];  
  
    for( int x=0; x < input.InputColumnCollection.Count; x++)  
    {  
        IDTSInputColumn100 column = input.InputColumnCollection[x];  
        bufferColumnIndex[x] = BufferManager.FindColumnByLineageID( input.Buffer, column.LineageID);  
    }  
}  
```  
  
```vb  
Dim bufferColumnIndex As Integer()  
  
    Public Overrides Sub PreExecute()  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
  
        ReDim bufferColumnIndex(input.InputColumnCollection.Count)  
  
        For x As Integer = 0 To input.InputColumnCollection.Count  
  
            Dim column As IDTSInputColumn100 = input.InputColumnCollection(x)  
            bufferColumnIndex(x) = BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID)  
  
        Next  
  
    End Sub  
```  
  
### <a name="adding-rows"></a><span data-ttu-id="a9c95-134">Aggiunta di righe</span><span class="sxs-lookup"><span data-stu-id="a9c95-134">Adding Rows</span></span>  
 <span data-ttu-id="a9c95-135">I componenti forniscono righe ai componenti a valle tramite l'aggiunta di righe agli oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-135">Components supply rows to downstream components by adding rows to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="a9c95-136">L'attività Flusso di dati fornisce una matrice di buffer di output, uno per ogni oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> connesso a un componente a valle, come parametro per il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-136">The data flow task provides an array of output buffers - one for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that is connected to a downstream component - as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="a9c95-137">I componenti di origine e i componenti di trasformazione con output asincroni aggiungono righe ai buffer e quando hanno terminato chiamano il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-137">Source components and transformation components with asynchronous outputs add rows to the buffers and call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method when they are finished adding rows.</span></span> <span data-ttu-id="a9c95-138">L'attività Flusso di dati gestisce i buffer di output che fornisce ai componenti e, quando un buffer diventa pieno, sposta automaticamente le righe presenti al suo interno nel componente successivo.</span><span class="sxs-lookup"><span data-stu-id="a9c95-138">The data flow task manages the output buffers that it supplies to components and, as a buffer becomes full, automatically moves the rows in the buffer to the next component.</span></span> <span data-ttu-id="a9c95-139">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> viene chiamato una sola volta per ogni componente, a differenza del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> che viene chiamato ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="a9c95-139">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is called one time per component, unlike  the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, which is called repeatedly.</span></span>  
  
 <span data-ttu-id="a9c95-140">Nell'esempio di codice seguente viene illustrata la modalità con cui un componente aggiunge righe ai propri buffer di output durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, quindi chiama il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-140">The following code example demonstrates how a component adds rows to its output buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method, then calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method.</span></span>  
  
```csharp  
public override void PrimeOutput( int outputs, int []outputIDs,PipelineBuffer []buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        IDTSOutput100 output = ComponentMetaData.OutputCollection.GetObjectByID( outputIDs[x]);  
        PipelineBuffer buffer = buffers[x];  
  
        // TODO: Add rows to the output buffer.  
    }  
    foreach( PipelineBuffer buffer in buffers )  
    {  
        /// Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset();  
    }  
}  
```  
  
```vb  
public overrides sub PrimeOutput( outputs as Integer , outputIDs() as Integer ,buffers() as PipelineBuffer buffers)  
  
    For x As Integer = 0 To outputs.MaxValue  
  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.GetObjectByID(outputIDs(x))  
        Dim buffer As PipelineBuffer = buffers(x)  
  
        ' TODO: Add rows to the output buffer.  
  
    Next  
  
    For Each buffer As PipelineBuffer In buffers  
  
        ' Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset()  
  
    Next  
  
End Sub  
```  
  
 <span data-ttu-id="a9c95-141">Per altre informazioni sullo sviluppo di componenti che aggiungono righe ai buffer di output, vedere [Sviluppo di un componente di origine personalizzato](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) e [Sviluppo di un componente di trasformazione personalizzato con output asincroni](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="a9c95-141">For more information about developing components that add rows to output buffers, see [Developing a Custom Source Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) and [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span>  
  
### <a name="receiving-rows"></a><span data-ttu-id="a9c95-142">Ricezione di righe</span><span class="sxs-lookup"><span data-stu-id="a9c95-142">Receiving Rows</span></span>  
 <span data-ttu-id="a9c95-143">I componenti ricevono righe dai componenti a monte in oggetti <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-143">Components receive rows from upstream components in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="a9c95-144">L'attività Flusso di dati fornisce un oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> che contiene le righe aggiunte al flusso di dati dai componenti a monte come parametro per il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-144">The data flow task provides a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> object that contains the rows added to the data flow by upstream components as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="a9c95-145">Questo buffer di input può essere utilizzato per esaminare e modificare le righe e le colonne nel buffer, ma non può essere utilizzato per aggiungere o rimuovere righe.</span><span class="sxs-lookup"><span data-stu-id="a9c95-145">This input buffer can be used to examine and modify the rows and columns in the buffer, but cannot be used to add or remove rows.</span></span> <span data-ttu-id="a9c95-146">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> viene chiamato ripetutamente finché non sono più disponibili buffer.</span><span class="sxs-lookup"><span data-stu-id="a9c95-146">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method is called repeatedly until there are no more available buffers.</span></span> <span data-ttu-id="a9c95-147">L'ultima volta che viene chiamato, la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> è `true`.</span><span class="sxs-lookup"><span data-stu-id="a9c95-147">The last time it is called, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="a9c95-148">È possibile scorrere la raccolta di righe nel buffer tramite il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A>, che fa avanzare il buffer alla riga successiva.</span><span class="sxs-lookup"><span data-stu-id="a9c95-148">You can iterate over the collection of rows in the buffer by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method, which advances the buffer to the next row.</span></span> <span data-ttu-id="a9c95-149">Questo metodo restituisce `false` quando il buffer si trova nell'ultima riga della raccolta.</span><span class="sxs-lookup"><span data-stu-id="a9c95-149">This method returns `false` when the buffer is on the last row in the collection.</span></span> <span data-ttu-id="a9c95-150">Non è necessario controllare la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> a meno che non occorra eseguire un'azione aggiuntiva dopo l'elaborazione delle ultime righe di dati.</span><span class="sxs-lookup"><span data-stu-id="a9c95-150">You do not have to check the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property unless you have to perform an additional action after the last rows of data have been processed.</span></span>  
  
 <span data-ttu-id="a9c95-151">Nel testo riportato di seguito viene illustrato l'utilizzo corretto del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> e della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A>:</span><span class="sxs-lookup"><span data-stu-id="a9c95-151">The following text shows the correct pattern for using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property:</span></span>  
  
 `while (buffer.NextRow())`  
  
 `{`  
  
 `// Do something with each row.`  
  
 `}`  
  
 `if (buffer.EndOfRowset)`  
  
 `{`  
  
 `// Optionally, do something after all rows have been processed.`  
  
 `}`  
  
 <span data-ttu-id="a9c95-152">Nell'esempio di codice seguente viene illustrata la modalità con cui un componente elabora le righe nei buffer di input durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9c95-152">The following code example demonstrates how a component processes the rows in input buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput( int inputID, PipelineBuffer buffer )  
{  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
        while( buffer.NextRow())  
        {  
            // TODO: Examine the columns in the current row.  
        }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)  
        While buffer.NextRow() = True  
  
            ' TODO: Examine the columns in the current row.  
        End While  
  
End Sub  
```  
  
 <span data-ttu-id="a9c95-153">Per altre informazioni sullo sviluppo di componenti che ricevono righe nei buffer di input, vedere [Sviluppo di un componente di destinazione personalizzato](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) e [Sviluppo di un componente di trasformazione personalizzato con output sincroni](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="a9c95-153">For more information about developing components that receive rows in input buffers, see [Developing a Custom Destination Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) and [Developing a Custom Transformation Component with Synchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span></span>  
  
<span data-ttu-id="a9c95-154">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a9c95-154">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a9c95-155">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="a9c95-155">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a9c95-156">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="a9c95-156">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a9c95-157">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="a9c95-157">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c95-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9c95-158">See Also</span></span>  
 [<span data-ttu-id="a9c95-159">Metodi della fase di progettazione di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="a9c95-159">Design-time Methods of a Data Flow Component</span></span>](design-time-methods-of-a-data-flow-component.md)  
  
  
