---
title: 'Lezione 4: creazione di stime basate su serie temporali tramite DMX | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6b883e43-209d-489a-8dc3-9349f88acae8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 772e5f5f71ca82dd18fec48730522c80e907414f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711176"
---
# <a name="lesson-4-creating-time-series-predictions-using-dmx"></a><span data-ttu-id="115d1-102">Lezione 4: Creazione di stime basate su serie temporali con DMX</span><span class="sxs-lookup"><span data-stu-id="115d1-102">Lesson 4: Creating Time Series Predictions Using DMX</span></span>
  <span data-ttu-id="115d1-103">In questa lezione e nella lezione seguente si utilizzerà DMX (Data Mining Extensions) per creare diversi tipi di stime in base ai modelli Time Series creati nella [lezione 1: creazione di un modello di data mining Time Series e della struttura](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) di data mining e [lezione 2: aggiunta di modelli di data mining alla struttura di data mining Time Series](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="115d1-103">In this lesson and the following lesson, you will use Data Mining Extensions (DMX) to create different types of predictions based on the time series models that you created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) and [Lesson 2: Adding Mining Models to the Time Series Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span></span>  
  
 <span data-ttu-id="115d1-104">Con un modello Time Series si dispone di numerose opzioni per l'esecuzione di stime:</span><span class="sxs-lookup"><span data-stu-id="115d1-104">With a time series model, you have many options for making predictions:</span></span>  
  
-   <span data-ttu-id="115d1-105">Utilizzare gli schemi e i dati esistenti nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="115d1-105">Use the existing patterns and data in the mining model</span></span>  
  
-   <span data-ttu-id="115d1-106">Utilizzare gli schemi esistenti nel modello di data mining, ma fornire nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="115d1-106">Use the existing patterns in the mining model but supply new data</span></span>  
  
-   <span data-ttu-id="115d1-107">Aggiungere nuovi dati al modello o aggiornare il modello.</span><span class="sxs-lookup"><span data-stu-id="115d1-107">Add new data to the model or update the model.</span></span>  
  
 <span data-ttu-id="115d1-108">La sintassi per effettuare questi tipi di stima è riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="115d1-108">The syntax for making these prediction types is summarized below:</span></span>  
  
 <span data-ttu-id="115d1-109">Stima basata su serie temporali predefinita</span><span class="sxs-lookup"><span data-stu-id="115d1-109">Default time series prediction</span></span>  
 <span data-ttu-id="115d1-110">Utilizzare [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) per restituire il numero specificato di stime dal modello di data mining sottoposto a training.</span><span class="sxs-lookup"><span data-stu-id="115d1-110">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) to return the specified number of predictions from the trained mining model.</span></span>  
  
 <span data-ttu-id="115d1-111">Vedere ad esempio [PredictTimeSeries &#40;&#41;DMX](/sql/dmx/predicttimeseries-dmx) o [esempi di query sul modello Time Series](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="115d1-111">For example, see [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) or [Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span></span>  
  
 <span data-ttu-id="115d1-112">EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="115d1-112">EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="115d1-113">Utilizzare [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) con l'argomento EXTEND_MODEL_CASES per aggiungere nuovi dati, estendere la serie e creare stime basate sul modello di data mining aggiornato.</span><span class="sxs-lookup"><span data-stu-id="115d1-113">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the EXTEND_MODEL_CASES argument to add new data, extend the series, and create predictions based on the updated mining model.</span></span>  
  
 <span data-ttu-id="115d1-114">Questa esercitazione contiene un esempio dell'utilizzo di EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="115d1-114">This tutorial contains an example of how to use EXTEND_MODEL_CASES.</span></span>  
  
 <span data-ttu-id="115d1-115">REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="115d1-115">REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="115d1-116">Utilizzare [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) con l'argomento REPLACE_MODEL_CASES per sostituire i dati originali con una nuova serie di dati, quindi creare stime basate sull'applicazione dei modelli nel modello di data mining alla nuova serie di dati.</span><span class="sxs-lookup"><span data-stu-id="115d1-116">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the REPLACE_MODEL_CASES argument to replace the original data with a new data series, and then create predictions based on applying the patterns in the mining model to the new data series.</span></span>  
  
 <span data-ttu-id="115d1-117">Per un esempio di come utilizzare REPLACE_MODEL_CASES, vedere [lezione 2: compilazione di uno scenario di previsione &#40;esercitazione intermedia sul Data Mining&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="115d1-117">For an example of how to use REPLACE_MODEL_CASES, see [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="115d1-118">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="115d1-118">Lesson Tasks</span></span>  
 <span data-ttu-id="115d1-119">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="115d1-119">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="115d1-120">Creare una query per ottenere le stime predefinite sulla base dei dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="115d1-120">Create a query to get the default predictions based on existing data.</span></span>  
  
 <span data-ttu-id="115d1-121">Nella lezione successiva verranno eseguite le attività correlate seguenti:</span><span class="sxs-lookup"><span data-stu-id="115d1-121">In the following lesson you will perform the following related tasks:</span></span>  
  
-   <span data-ttu-id="115d1-122">Creare una query per fornire nuovi dati e ottenere stime aggiornate.</span><span class="sxs-lookup"><span data-stu-id="115d1-122">Create a query to supply new data and get updated predictions.</span></span>  
  
 <span data-ttu-id="115d1-123">Oltre a creare manualmente le query tramite DMX, è anche possibile creare stime tramite il generatore delle query di stima in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="115d1-123">In addition to creating queries manually by using DMX, you can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="simple-time-series-prediction-query"></a><span data-ttu-id="115d1-124">Semplice query di stima basata su serie temporali</span><span class="sxs-lookup"><span data-stu-id="115d1-124">Simple Time Series Prediction Query</span></span>  
 <span data-ttu-id="115d1-125">Il primo passaggio consiste nell'utilizzare l'istruzione `SELECT FROM` insieme alla funzione `PredictTimeSeries` per creare stime basate su serie temporali.</span><span class="sxs-lookup"><span data-stu-id="115d1-125">The first step is to use the `SELECT FROM` statement together with the `PredictTimeSeries` function to create time series predictions.</span></span> <span data-ttu-id="115d1-126">I modelli Time Series supportano una sintassi semplificata per la creazione di stime: non è necessario fornire alcun input, ma è sufficiente specificare il numero di stime da creare.</span><span class="sxs-lookup"><span data-stu-id="115d1-126">Time series models support a simplified syntax for creating predictions: you do not need to supply any inputs, but only have to specify the number of predictions to create.</span></span> <span data-ttu-id="115d1-127">Di seguito è riportato un esempio generico dell'istruzione da utilizzare:</span><span class="sxs-lookup"><span data-stu-id="115d1-127">The following is a generic example of the statement you will use:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model name>]   
WHERE [<criteria>]  
```  
  
 <span data-ttu-id="115d1-128">L'elenco di selezione può contenere colonne del modello, ad esempio il nome della linea di prodotti per cui si stanno creando le stime, o funzioni di stima, ad esempio [Lag &#40;dmx&#41;](/sql/dmx/lag-dmx) o [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), che sono specifici per i modelli di data mining Time Series.</span><span class="sxs-lookup"><span data-stu-id="115d1-128">The select list can contain columns from the model, such as the name of the product line that you are creating the predictions for, or prediction functions, such as [Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) or [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), which are specifically for time series mining models.</span></span>  
  
#### <a name="to-create-a-simple-time-series-prediction-query"></a><span data-ttu-id="115d1-129">Per creare una semplice query di stima basata su serie temporali</span><span class="sxs-lookup"><span data-stu-id="115d1-129">To create a simple time series prediction query</span></span>  
  
1.  <span data-ttu-id="115d1-130">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="115d1-130">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="115d1-131">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="115d1-131">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="115d1-132">Copiare l'esempio generico dell'istruzione nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="115d1-132">Copy the generic example of the statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="115d1-133">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="115d1-133">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="115d1-134">con:</span><span class="sxs-lookup"><span data-stu-id="115d1-134">with:</span></span>  
  
    ```  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    ```  
  
     <span data-ttu-id="115d1-135">La prima riga consente di recuperare il valore del modello di data mining che identifica la serie.</span><span class="sxs-lookup"><span data-stu-id="115d1-135">The first line retrieves a value from the mining model that identifies the series.</span></span>  
  
     <span data-ttu-id="115d1-136">La seconda e terza riga utilizzano la funzione `PredictTimeSeries`.</span><span class="sxs-lookup"><span data-stu-id="115d1-136">The second and third lines use the `PredictTimeSeries` function.</span></span> <span data-ttu-id="115d1-137">Ogni riga stima un attributo diverso, `[Quantity]` o `[Amount]`.</span><span class="sxs-lookup"><span data-stu-id="115d1-137">Each line predicts a different attribute, `[Quantity]` or `[Amount]`.</span></span> <span data-ttu-id="115d1-138">I numeri dopo i nomi degli attributi stimabili specificano il numero di intervalli temporali da stimare.</span><span class="sxs-lookup"><span data-stu-id="115d1-138">The numbers after the names of the predictable attributes specify the number of time steps to predict.</span></span>  
  
     <span data-ttu-id="115d1-139">La clausola `AS` viene utilizzata per fornire un nome per la colonna restituita da ogni funzione di stima.</span><span class="sxs-lookup"><span data-stu-id="115d1-139">The `AS` clause is used to provide a name for the column that is returned by each prediction function.</span></span> <span data-ttu-id="115d1-140">Se non si fornisce un alias, per impostazione predefinita entrambe le colonne vengono restituite con l'etichetta `Expression`.</span><span class="sxs-lookup"><span data-stu-id="115d1-140">If you do not supply an alias, by default both columns are returned with the label, `Expression`.</span></span>  
  
4.  <span data-ttu-id="115d1-141">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="115d1-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="115d1-142">con:</span><span class="sxs-lookup"><span data-stu-id="115d1-142">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="115d1-143">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="115d1-143">Replace the following:</span></span>  
  
    ```  
    WHERE [criteria>]   
    ```  
  
     <span data-ttu-id="115d1-144">con:</span><span class="sxs-lookup"><span data-stu-id="115d1-144">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="115d1-145">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="115d1-145">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    FROM   
    [Forecasting_MIXED]  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
6.  <span data-ttu-id="115d1-146">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="115d1-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="115d1-147">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `SimpleTimeSeriesPrediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="115d1-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SimpleTimeSeriesPrediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="115d1-148">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="115d1-148">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="115d1-149">La query restituisce sei stime per ognuna delle due combinazioni di prodotto e area specificate nella clausola `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="115d1-149">The query returns 6 predictions for each of the two combinations of product and region that are specified in the `WHERE` clause.</span></span>  
  
 <span data-ttu-id="115d1-150">Nella lezione successiva verrà creata una query che fornisce nuovi dati al modello e confronta i risultati di tale stima con quella appena creata.</span><span class="sxs-lookup"><span data-stu-id="115d1-150">In the next lesson, you will create a query that supplies new data to the model, and compare the results of that prediction with the one you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="115d1-151">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="115d1-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="115d1-152">Lezione 5: Estensione del modello Time Series</span><span class="sxs-lookup"><span data-stu-id="115d1-152">Lesson 5: Extending the Time Series Model</span></span>](../../2014/tutorials/lesson-5-extending-the-time-series-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="115d1-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="115d1-153">See Also</span></span>  
 <span data-ttu-id="115d1-154">[PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) </span><span class="sxs-lookup"><span data-stu-id="115d1-154">[PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) </span></span>  
 <span data-ttu-id="115d1-155">[Ritardo &#40;DMX&#41;](/sql/dmx/lag-dmx) </span><span class="sxs-lookup"><span data-stu-id="115d1-155">[Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) </span></span>  
 <span data-ttu-id="115d1-156">[Esempi di query sul modello Time Series](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="115d1-156">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="115d1-157">Lezione 2: compilazione di uno scenario di previsione &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="115d1-157">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
  
