---
title: 'Lezione 3: elaborazione della struttura e dei modelli della serie temporale | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 16e27b57-eae1-47a7-a02c-47b6ed487d87
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 493d27c9836eb765c655eba5bbb004e4d48cde40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717088"
---
# <a name="lesson-3-processing-the-time-series-structure-and-models"></a><span data-ttu-id="0a4f7-102">Lezione 3: Elaborazione di strutture e modelli Time Series</span><span class="sxs-lookup"><span data-stu-id="0a4f7-102">Lesson 3: Processing the Time Series Structure and Models</span></span>
  <span data-ttu-id="0a4f7-103">In questa lezione verrà utilizzata l'istruzione [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) per elaborare le strutture di data mining e i modelli di data mining di serie temporali creati.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement to process the time series mining structures and mining models that you created.</span></span>  
  
 <span data-ttu-id="0a4f7-104">Quando si elabora una struttura di data mining, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] legge i dati di origine e compila le strutture che supportano i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="0a4f7-105">È sempre necessario elaborare i modelli e le strutture di data mining al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-105">You always have to process a mining model and structure when you first create it.</span></span> <span data-ttu-id="0a4f7-106">Se si specifica una struttura di data mining utilizzando INSERT INTO, l'istruzione elabora la struttura e tutti i modelli di data mining associati.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-106">If you specify the mining structure when using INSERT INTO, the statement processes the mining structure and all its associated mining models.</span></span>  
  
 <span data-ttu-id="0a4f7-107">Quando si aggiunge un modello di data mining a una struttura di data mining già elaborata, è possibile utilizzare l'istruzione `INSERT INTO MINING MODEL` per elaborare solo il nuovo modello di data mining utilizzando i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-107">When you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to process just the new mining model by using the existing data.</span></span>  
  
 <span data-ttu-id="0a4f7-108">Per ulteriori informazioni sull'elaborazione dei modelli di data mining, vedere [requisiti e considerazioni sull'elaborazione &#40;&#41;di data mining ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="0a4f7-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="0a4f7-109">Istruzione INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="0a4f7-109">INSERT INTO Statement</span></span>  
 <span data-ttu-id="0a4f7-110">Per eseguire il training della struttura di data mining Time Series e di tutti i modelli di data mining associati, utilizzare l'istruzione [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="0a4f7-110">In order to train the time series mining structure and all its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="0a4f7-111">Il codice nell'istruzione può essere suddiviso nelle parti seguenti.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-111">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="0a4f7-112">Identificazione della struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="0a4f7-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="0a4f7-113">Creazione di un elenco delle colonne nella struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="0a4f7-113">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="0a4f7-114">Definizione dei dati di training</span><span class="sxs-lookup"><span data-stu-id="0a4f7-114">Defining the training data</span></span>  
  
 <span data-ttu-id="0a4f7-115">Di seguito è riportato un esempio generico di istruzione `INSERT INTO`:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-115">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="0a4f7-116">La prima riga del codice identifica la struttura di data mining di cui si eseguirà il training:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-116">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="0a4f7-117">Le successive righe del codice specificano le colonne definite dalla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-117">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="0a4f7-118">È necessario che siano elencate tutte le colonne nella struttura di data mining e ogni colonna deve essere associata a una colonna nei dati della query di origine.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-118">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="0a4f7-119">Le ultime righe del codice definiscono i dati che verranno utilizzati per il training della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-119">The final lines of the code define the data that will be used to train the mining structure.</span></span>  
  
```  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="0a4f7-120">In questa lezione si utilizzerà `OPENQUERY` per definire i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-120">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="0a4f7-121">Per altre informazioni sugli altri metodi di definizione di una query sui dati di origine, vedere [&#60;query sui dati di origine&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="0a4f7-121">For more information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="0a4f7-122">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="0a4f7-122">Lesson Tasks</span></span>  
 <span data-ttu-id="0a4f7-123">In questa lezione verrà eseguita l'attività seguente:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-123">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="0a4f7-124">Elaborare la struttura di data mining Forecasting_MIXED_Structure</span><span class="sxs-lookup"><span data-stu-id="0a4f7-124">Process the mining structure Forecasting_MIXED_Structure</span></span>  
  
-   <span data-ttu-id="0a4f7-125">Elaborare i modelli di data mining correlati Forecasting_MIXED, Forecasting_ARIMA e Forecasting_ARTXP</span><span class="sxs-lookup"><span data-stu-id="0a4f7-125">Process the related mining models Forecasting_MIXED, Forecasting_ARIMA, and Forecasting_ARTXP</span></span>  
  
## <a name="processing-the-time-series-mining-structure"></a><span data-ttu-id="0a4f7-126">Elaborazione della struttura di data mining di serie temporali</span><span class="sxs-lookup"><span data-stu-id="0a4f7-126">Processing the Time Series Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-and-related-mining-models-by-using-insert-into"></a><span data-ttu-id="0a4f7-127">Per elaborare la struttura e i relativi modelli di data mining utilizzando INSERT INTO.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-127">To process the mining structure and related mining models by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="0a4f7-128">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-128">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="0a4f7-129">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-129">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="0a4f7-130">Copiare l'esempio generico dell'istruzione INSERT INTO nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-130">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="0a4f7-131">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-131">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="0a4f7-132">con:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-132">with:</span></span>  
  
    ```  
    Forecasting_MIXED_Structure  
    ```  
  
4.  <span data-ttu-id="0a4f7-133">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-133">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="0a4f7-134">con:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-134">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]   
    ```  
  
5.  <span data-ttu-id="0a4f7-135">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-135">Replace the following:</span></span>  
  
    ```  
    OPENQUERY(<source data definition>)  
    ```  
  
     <span data-ttu-id="0a4f7-136">con:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-136">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2008R2],'SELECT [ReportingDate], [ModelRegion], [Quantity], [Amount]  
    FROM vTimeSeries ORDER BY [ReportingDate]')  
    ```  
  
     <span data-ttu-id="0a4f7-137">La query di origine fa riferimento all' [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] origine dati definita nel progetto di esempio IntermediateTutorial.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-137">The source query references the  [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the IntermediateTutorial sample project.</span></span> <span data-ttu-id="0a4f7-138">Utilizza tale origine dati per accedere alla vista vTimeSeries</span><span class="sxs-lookup"><span data-stu-id="0a4f7-138">It uses this data source to access the view vTimeSeries.</span></span> <span data-ttu-id="0a4f7-139">contenente i dati di origine che verranno utilizzati per il training del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-139">This view contains the source data that will be used to train the mining model.</span></span> <span data-ttu-id="0a4f7-140">Se non si ha familiarità con questo progetto o con queste viste, vedere[lezione 2: compilazione di uno scenario di previsione &#40;esercitazione intermedia sul Data Mining&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="0a4f7-140">If you are not familiar with this project or this views, see[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="0a4f7-141">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0a4f7-141">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Forecasting_MIXED_Structure]  
    (  
       [ReportingDate],[ModelRegion],[Quantity],[Amount])  
    )  
    OPENQUERY(  
    [Adventure Works DW 2008R2],  
    'SELECT [ReportingDate],[ModelRegion],[Quantity],[Amount] FROM vTimeSeries ORDER BY [ReportingDate]'  
    )   
    ```  
  
6.  <span data-ttu-id="0a4f7-142">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="0a4f7-142">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="0a4f7-143">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `ProcessForecastingAll.dmx` .</span><span class="sxs-lookup"><span data-stu-id="0a4f7-143">In the **Save As** dialog box, browse to the appropriate folder, and name the file `ProcessForecastingAll.dmx`.</span></span>  
  
8.  <span data-ttu-id="0a4f7-144">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="0a4f7-144">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="0a4f7-145">Al termine dell'esecuzione della query, è possibile creare stime utilizzando i modelli di data mining elaborati.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-145">After the query has finished running, you can create predictions by using the processed mining models.</span></span> <span data-ttu-id="0a4f7-146">Nella lezione successiva verranno create diverse stime basate sui modelli di data mining creati.</span><span class="sxs-lookup"><span data-stu-id="0a4f7-146">In the next lesson, you will create several predictions based on the mining models that you created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0a4f7-147">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="0a4f7-147">Next Lesson</span></span>  
 [<span data-ttu-id="0a4f7-148">Lezione 4: Creazione di stime basate su serie temporali con DMX</span><span class="sxs-lookup"><span data-stu-id="0a4f7-148">Lesson 4: Creating Time Series Predictions Using DMX</span></span>](../../2014/tutorials/lesson-4-creating-time-series-predictions-using-dmx.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a4f7-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a4f7-149">See Also</span></span>  
 <span data-ttu-id="0a4f7-150">[Requisiti e considerazioni sull'elaborazione &#40;&#41;di data mining](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="0a4f7-150">[Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span></span>  
 <span data-ttu-id="0a4f7-151">[&#60;query sui dati di origine&#62;](/sql/dmx/source-data-query) </span><span class="sxs-lookup"><span data-stu-id="0a4f7-151">[&#60;source data query&#62;](/sql/dmx/source-data-query) </span></span>  
 [<span data-ttu-id="0a4f7-152">OPENQUERY &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="0a4f7-152">OPENQUERY &#40;DMX&#41;</span></span>](/sql/dmx/source-data-query-openquery)  
  
  
