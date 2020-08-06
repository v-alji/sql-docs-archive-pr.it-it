---
title: Piano di esecuzione e allocazione di buffer | Microsoft Docs
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
- custom data flow components [Integration Services], buffer allocations
- custom data flow components [Integration Services], execution plans
- buffer allocations [Integration Services]
- data flow components [Integration Services], buffer allocations
- data flow components [Integration Services], execution plans
- execution plans [Integration Services]
ms.assetid: 679d9ff0-641e-47c3-abb8-d1a7dcb279dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03b8bb22988ccf77f8920252ac2d600478c92f3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713347"
---
# <a name="execution-plan-and-buffer-allocation"></a><span data-ttu-id="cea68-102">Piano di esecuzione e allocazione di buffer</span><span class="sxs-lookup"><span data-stu-id="cea68-102">Execution Plan and Buffer Allocation</span></span>
  <span data-ttu-id="cea68-103">Prima dell'esecuzione, l'attività Flusso di dati esamina i propri componenti e genera un piano di esecuzione per ogni sequenza di componenti.</span><span class="sxs-lookup"><span data-stu-id="cea68-103">Before execution, the data flow task examines its components and generates an execution plan for each sequence of components.</span></span> <span data-ttu-id="cea68-104">In questa sezione vengono fornite informazioni sul piano di esecuzione, su come visualizzarlo e su come influisce sull'allocazione dei buffer di input e output.</span><span class="sxs-lookup"><span data-stu-id="cea68-104">This section provides details about the execution plan, how to view the plan, and how input and output buffers are allocated based on the execution plan.</span></span>  
  
## <a name="understanding-the-execution-plan"></a><span data-ttu-id="cea68-105">Informazioni sul piano di esecuzione</span><span class="sxs-lookup"><span data-stu-id="cea68-105">Understanding the Execution Plan</span></span>  
 <span data-ttu-id="cea68-106">Un piano di esecuzione contiene thread di origine e thread di lavoro. Ogni thread contiene elenchi di operazioni che specificano elenchi di operazioni di output per i thread di origine oppure elenchi di operazioni di input e output per i thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cea68-106">An execution plan contains source threads and work threads, and each thread contains work lists that specify output work lists for source threads or input and output work lists for work threads.</span></span> <span data-ttu-id="cea68-107">I thread di origine in un piano di esecuzione rappresentano i componenti di origine nel flusso di dati e sono identificati da *SourceThread\*\*n*, dove *n* è il numero in base zero del thread di origine.</span><span class="sxs-lookup"><span data-stu-id="cea68-107">The source threads in an execution plan represent the source components in the data flow and are identified in the execution plan by *SourceThread\*\*n*, where *n* is the zero-based number of the source thread.</span></span>  
  
 <span data-ttu-id="cea68-108">Ogni thread di origine crea un buffer, imposta un listener e chiama il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> sul componente di origine.</span><span class="sxs-lookup"><span data-stu-id="cea68-108">Each source thread creates a buffer, sets a listener, and calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method on the source component.</span></span> <span data-ttu-id="cea68-109">Si tratta del punto in cui viene avviata l'esecuzione e hanno origine i dati, quando il componente di origine inizia ad aggiungere righe nei buffer di output forniti dall'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="cea68-109">This is where execution starts and data originates, as the source component starts adding rows to the output buffers that are provided to it by the data flow task.</span></span> <span data-ttu-id="cea68-110">Dopo l'inizio dell'esecuzione dei thread di origine, il lavoro viene bilanciato tra thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cea68-110">After the source threads are running, the balance of work is distributed among work threads.</span></span>  
  
 <span data-ttu-id="cea68-111">Un thread di lavoro può contenere sia elenchi di lavoro di input che di output e viene identificato nel piano di esecuzione come *WorkThread\*\*n*, dove *n* è il numero in base zero del thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cea68-111">A work thread may contain both input and output work lists and is identified in the execution plan as *WorkThread\*\*n*, where *n* is the zero-based number of the work thread.</span></span> <span data-ttu-id="cea68-112">Questi thread contengono elenchi di operazioni di output quando il grafico contiene un componente con output asincroni.</span><span class="sxs-lookup"><span data-stu-id="cea68-112">These threads contain output work lists when the graph contains a component with asynchronous outputs.</span></span>  
  
 <span data-ttu-id="cea68-113">Nel piano di esecuzione di esempio seguente viene rappresentato un flusso di dati che contiene un componente di origine connesso a una trasformazione con un output asincrono connesso a un componente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cea68-113">The following sample execution plan represents a data flow that contains a source component connected to a transformation with an asynchronous output connected to a destination component.</span></span> <span data-ttu-id="cea68-114">Nell'esempio WorkThread0 contiene un elenco di operazioni di output perché il componente di trasformazione ha un output asincrono.</span><span class="sxs-lookup"><span data-stu-id="cea68-114">In this example, WorkThread0 contains an output work list because the transformation component has an asynchronous output.</span></span>  
  
```  
SourceThread0   
    Influences: 72 158   
    Output Work List   
        CreatePrimeBuffer of type 1 for output id 10   
        SetBufferListener: "WorkThread0" for input ID 73   
        CallPrimeOutput on component "OLE DB Source" (1)   
    End Output Work List   
    This thread drives 0 distributors   
End SourceThread0   
WorkThread0   
    Influences: 72 158   
    Input Work list, input ID 73   
        CallProcessInput on input ID 73 on component "Sort" (72) for view type 2   
    End Input Work list for input 73   
    Output Work List   
        CreatePrimeBuffer of type 3 for output id 74   
        SetBufferListener: "WorkThread1" for input ID 171with internal handoff   
        CallPrimeOutput on component "Sort" (72)   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread0   
WorkThread1   
    Influences: 158   
    Input Work list, input ID 171  
        CallProcessInput on input ID 171 on component "OLE DB Destination" (158) for view type 4  
    End Input Work list for input 171   
    Output Work List   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="cea68-115">Il piano di esecuzione viene generato ogni volta che un pacchetto viene eseguito e può essere acquisito con l'aggiunta di un provider di log al pacchetto, l'abilitazione della registrazione e la selezione dell'evento **PipelineExecutionPlan**.</span><span class="sxs-lookup"><span data-stu-id="cea68-115">The execution plan is generated every time a package is executed, and can be captured by adding a log provider to the package, enabling logging, and selecting the **PipelineExecutionPlan** event.</span></span>  
  
## <a name="understanding-buffer-allocation"></a><span data-ttu-id="cea68-116">Informazioni sull'allocazione di buffer</span><span class="sxs-lookup"><span data-stu-id="cea68-116">Understanding Buffer Allocation</span></span>  
 <span data-ttu-id="cea68-117">In base al piano di esecuzione, l'attività Flusso di dati crea buffer che contengono le colonne definite negli output dei componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="cea68-117">Based on the execution plan, the data flow task creates buffers that contain the columns defined in the outputs of the data flow components.</span></span> <span data-ttu-id="cea68-118">Il buffer viene riutilizzato durante il flusso dei dati attraverso la sequenza dei componenti, finché non viene rilevato un componente con output asincroni.</span><span class="sxs-lookup"><span data-stu-id="cea68-118">The buffer is reused as the data flows through the sequence of components, until a component with asynchronous outputs is encountered.</span></span> <span data-ttu-id="cea68-119">A questo punto viene creato un nuovo buffer, che contiene le colonne di output dell'output asincrono e le colonne di output dei componenti a valle.</span><span class="sxs-lookup"><span data-stu-id="cea68-119">Then, a new buffer is created, which contains the output columns of the asynchronous output and the output columns of downstream components.</span></span>  
  
 <span data-ttu-id="cea68-120">Durante l'esecuzione, i componenti hanno accesso al buffer nell'origine o nel thread di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="cea68-120">During execution, components have access to the buffer in the current source or work thread.</span></span> <span data-ttu-id="cea68-121">Il buffer è un buffer di input, fornito dal metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, o un buffer di output, fornito dal metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cea68-121">The buffer is either an input buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, or an output buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="cea68-122">Anche la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> identifica ogni buffer come buffer di input o di output.</span><span class="sxs-lookup"><span data-stu-id="cea68-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> also identifies each buffer as an input or output buffer.</span></span>  
  
 <span data-ttu-id="cea68-123">I componenti di trasformazione con output asincroni ricevono il buffer di input esistente dal metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> e il nuovo buffer di output dal metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cea68-123">Transformation components with asynchronous outputs receive the existing input buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, and receive the new output buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="cea68-124">Un componente di trasformazione con output asincroni è il solo tipo di componente del flusso di dati che riceve un buffer sia di input che di output.</span><span class="sxs-lookup"><span data-stu-id="cea68-124">A transformation component with asynchronous outputs is the only type of data flow component that receives both an input and an output buffer.</span></span>  
  
 <span data-ttu-id="cea68-125">Poiché il buffer fornito a un componente contiene probabilmente più colonne di quelle presenti nelle raccolte di colonne di output o di input del componente, gli sviluppatori di componenti possono chiamare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> per individuare una colonna nel buffer specificando `LineageID`.</span><span class="sxs-lookup"><span data-stu-id="cea68-125">Because the buffer provided to a component is likely to contain more columns than the component has in its input or output column collections, component developers can call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method to locate a column in the buffer by specifying its `LineageID`.</span></span>  
  
<span data-ttu-id="cea68-126">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cea68-126">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cea68-127">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="cea68-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cea68-128">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="cea68-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cea68-129">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="cea68-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
