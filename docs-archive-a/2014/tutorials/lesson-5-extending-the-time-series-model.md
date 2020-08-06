---
title: 'Lezione 5: estensione del modello Time Series | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7aad4946-c903-4e25-88b9-b087c20cb67d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2716e985897f8115d189d9410b7cdb13fb1af291
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626424"
---
# <a name="lesson-5-extending-the-time-series-model"></a><span data-ttu-id="d562f-102">Lezione 5: Estensione del modello Time Series</span><span class="sxs-lookup"><span data-stu-id="d562f-102">Lesson 5: Extending the Time Series Model</span></span>
  <span data-ttu-id="d562f-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise è possibile aggiungere nuovi dati a un modello Time Series e incorporarli automaticamente nel modello.</span><span class="sxs-lookup"><span data-stu-id="d562f-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, you can add new data to a time series model and automatically incorporate the new data into the model.</span></span> <span data-ttu-id="d562f-104">I nuovi dati possono essere aggiunti a un modello di data mining Time Series in uno dei due modi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="d562f-104">You add new data to a time series mining model in one of two ways:</span></span>  
  
-   <span data-ttu-id="d562f-105">Utilizzando PREDICTION JOIN per unire in join i dati in un'origine esterna ai dati di training.</span><span class="sxs-lookup"><span data-stu-id="d562f-105">Use a PREDICTION JOIN to join data in an external source to the training data.</span></span>  
  
-   <span data-ttu-id="d562f-106">Usando una query di stima singleton per specificare i dati un intervallo alla volta.</span><span class="sxs-lookup"><span data-stu-id="d562f-106">Use a singleton prediction query to provide data one slice at a time.</span></span>  
  
 <span data-ttu-id="d562f-107">Si supponga ad esempio di avere eseguito il training del modello di data mining sui dati di vendita esistenti, alcuni mesi fa.</span><span class="sxs-lookup"><span data-stu-id="d562f-107">For example, assume that you trained the mining model on existing sales data some months ago.</span></span> <span data-ttu-id="d562f-108">Una volta ottenuti i dati delle nuove vendite, è necessario aggiornare le stime di vendita per incorporare i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="d562f-108">When you get new sales, you might want to update the sales predictions to incorporate the new data.</span></span> <span data-ttu-id="d562f-109">È possibile eseguire questa operazione in un unico passaggio, fornendo le cifre relative alle nuove vendite come dati di input e generando le nuove stime in base al set di dati composto.</span><span class="sxs-lookup"><span data-stu-id="d562f-109">You can do this in one step, by supplying the new sales figures as input data and generating new predictions based on the composite data set.</span></span>  
  
## <a name="making-predictions-with-extend_model_cases"></a><span data-ttu-id="d562f-110">Esecuzione di stime con EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d562f-110">Making Predictions with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="d562f-111">Di seguito sono riportati esempi generici di una stima basata su serie temporali che utilizza EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="d562f-111">The following are generic examples of a time series prediction using EXTEND_MODEL_CASES.</span></span> <span data-ttu-id="d562f-112">Il primo esempio consente di specificare il numero di stime a partire dall'ultimo intervallo temporale del modello originale:</span><span class="sxs-lookup"><span data-stu-id="d562f-112">The first example enables you to specify the number of predictions starting from the last time step of the original model:</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>]  
```  
  
 <span data-ttu-id="d562f-113">Il secondo esempio consente di specificare l'intervallo temporale di inizio e di fine delle stime.</span><span class="sxs-lookup"><span data-stu-id="d562f-113">The second example enables you to specify the time step where predictions should start, and where they should end.</span></span> <span data-ttu-id="d562f-114">Questa opzione è importante quando si estendono i case del modello poiché, per impostazione predefinita, gli intervalli temporali utilizzati per le query di stima iniziano sempre dalla fine della serie originale.</span><span class="sxs-lookup"><span data-stu-id="d562f-114">This option is important when you extend the model cases because, by default, the time steps used for prediction queries always start at the end of the original series.</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n-start, n-end, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>}  
```  
  
 <span data-ttu-id="d562f-115">In questa esercitazione verranno creati entrambi i tipi di query.</span><span class="sxs-lookup"><span data-stu-id="d562f-115">In this tutorial, you will create both kinds of queries.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query-on-a-time-series-model"></a><span data-ttu-id="d562f-116">Per creare una query di stima singleton in un modello Time Series</span><span class="sxs-lookup"><span data-stu-id="d562f-116">To create a singleton prediction query on a time series model</span></span>  
  
1.  <span data-ttu-id="d562f-117">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="d562f-117">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="d562f-118">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="d562f-118">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="d562f-119">Copiare l'esempio generico dell'istruzione singleton nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="d562f-119">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="d562f-120">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d562f-120">Replace the following:</span></span>  
  
    ```  
    SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
    ```  
  
     <span data-ttu-id="d562f-121">con:</span><span class="sxs-lookup"><span data-stu-id="d562f-121">with:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    ```  
  
     <span data-ttu-id="d562f-122">La prima riga consente di recuperare il valore del modello che identifica la serie.</span><span class="sxs-lookup"><span data-stu-id="d562f-122">The first line retrieves a value from the model that identifies the series.</span></span>  
  
     <span data-ttu-id="d562f-123">La seconda riga contiene la funzione di stima, che ottiene 6 stime per Quantity.</span><span class="sxs-lookup"><span data-stu-id="d562f-123">The second line contains the prediction function, which gets 6 predictions for Quantity.</span></span> <span data-ttu-id="d562f-124">L'alias `PredictQty` viene assegnato alla colonna del risultato della stima per semplificare la comprensione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="d562f-124">An alias, `PredictQty`, is assigned to the prediction result column to make it easier to understand the results.</span></span>  
  
4.  <span data-ttu-id="d562f-125">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d562f-125">Replace the following:</span></span>  
  
    ```  
    FROM <mining model>  
    ```  
  
     <span data-ttu-id="d562f-126">con:</span><span class="sxs-lookup"><span data-stu-id="d562f-126">with:</span></span>  
  
    ```  
    FROM [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="d562f-127">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d562f-127">Replace the following:</span></span>  
  
    ```  
    PREDICTION JOIN <source query>  
    ```  
  
     <span data-ttu-id="d562f-128">con:</span><span class="sxs-lookup"><span data-stu-id="d562f-128">with:</span></span>  
  
    ```  
    NATURAL PREDICTION JOIN   
    (  
       SELECT 1 AS [Reporting Date],  
       '10' AS [Quantity],  
       'M200 Europe' AS [Model Region]  
       UNION SELECT  
       2 AS [Reporting Date],  
       15 AS [Quantity]),  
       'M200 Europe' AS [Model Region]  
    ) AS t  
    ```  
  
6.  <span data-ttu-id="d562f-129">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d562f-129">Replace the following:</span></span>  
  
    ```  
    [WHERE <criteria>]  
    ```  
  
     <span data-ttu-id="d562f-130">con:</span><span class="sxs-lookup"><span data-stu-id="d562f-130">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="d562f-131">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="d562f-131">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    FROM  
       [Forecasting_MIXED]  
    NATURAL PREDICTION JOIN   
       SELECT 1 AS [ReportingDate],  
      '10' AS [Quantity],  
      'M200 Europe' AS [ModelRegion]  
    UNION SELECT  
      2 AS [ReportingDate],  
      15 AS [Quantity]),  
      'M200 Europe' AS [ModelRegion]  
    ) AS t  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
7.  <span data-ttu-id="d562f-132">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="d562f-132">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="d562f-133">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Singleton_TimeSeries_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="d562f-133">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_TimeSeries_Query.dmx`.</span></span>  
  
9. <span data-ttu-id="d562f-134">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="d562f-134">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="d562f-135">La query restituirà le stime delle quantità di vendita relative alla bicicletta M200 in Europa e nell'area del Pacifico.</span><span class="sxs-lookup"><span data-stu-id="d562f-135">The query returns predictions of sales quantity for the M200 bicycle in the Europe and Pacific regions.</span></span>  
  
## <a name="understanding-prediction-start-with-extend_model_cases"></a><span data-ttu-id="d562f-136">Informazioni sull'avvio della stima con EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d562f-136">Understanding Prediction Start with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="d562f-137">Una volta create le stime in base al modello originale e ai nuovi dati, è possibile confrontare i risultati per stabilire in che modo l'aggiornamento dei dati di vendita influisce sulle stime.</span><span class="sxs-lookup"><span data-stu-id="d562f-137">Now that you have created predictions based on the original model, and with new data, you can compare the results to see how updating the sales data affects the predictions.</span></span> <span data-ttu-id="d562f-138">Prima di eseguire questa operazione, rivedere il codice appena creato e notare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d562f-138">Before you do so, review the code that you just created, and notice the following:</span></span>  
  
-   <span data-ttu-id="d562f-139">Sono stati forniti nuovi dati solo per l'Europa.</span><span class="sxs-lookup"><span data-stu-id="d562f-139">You supplied new data for only the Europe region.</span></span>  
  
-   <span data-ttu-id="d562f-140">I nuovi dati forniti riguardano solo due mesi.</span><span class="sxs-lookup"><span data-stu-id="d562f-140">You supplied only two months' worth of new data.</span></span>  
  
 <span data-ttu-id="d562f-141">Nella tabella seguente viene illustrato come i nuovi valori forniti per il prodotto M200 Europe influiscono sulle stime.</span><span class="sxs-lookup"><span data-stu-id="d562f-141">The following table shows how the new values supplied for M200 Europe affect predictions.</span></span> <span data-ttu-id="d562f-142">Per il prodotto M200 nell'area del Pacifico non sono stati forniti nuovi dati, tuttavia viene ugualmente eseguito il confronto tra le due serie:</span><span class="sxs-lookup"><span data-stu-id="d562f-142">You did not provide any new data for the M200 product in the Pacific region, but this series is presented for comparison:</span></span>  
  
 <span data-ttu-id="d562f-143">**Prodotto e area geografica: M200 Europe**</span><span class="sxs-lookup"><span data-stu-id="d562f-143">**Product and Region: M200 Europe**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="d562f-144">Modello esistente (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="d562f-144">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="d562f-145">Modello con dati di vendita aggiornati (`PredictTimeSeries` con `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="d562f-145">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="d562f-146">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-146">M200 Europe</span></span>|<span data-ttu-id="d562f-147">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-147">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-148">77</span><span class="sxs-lookup"><span data-stu-id="d562f-148">77</span></span>|<span data-ttu-id="d562f-149">10</span><span class="sxs-lookup"><span data-stu-id="d562f-149">10</span></span>|  
|<span data-ttu-id="d562f-150">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-150">M200 Europe</span></span>|<span data-ttu-id="d562f-151">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-151">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-152">64</span><span class="sxs-lookup"><span data-stu-id="d562f-152">64</span></span>|<span data-ttu-id="d562f-153">15</span><span class="sxs-lookup"><span data-stu-id="d562f-153">15</span></span>|  
|<span data-ttu-id="d562f-154">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-154">M200 Europe</span></span>|<span data-ttu-id="d562f-155">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-155">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-156">59</span><span class="sxs-lookup"><span data-stu-id="d562f-156">59</span></span>|<span data-ttu-id="d562f-157">72</span><span class="sxs-lookup"><span data-stu-id="d562f-157">72</span></span>|  
|<span data-ttu-id="d562f-158">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-158">M200 Europe</span></span>|<span data-ttu-id="d562f-159">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-159">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-160">56</span><span class="sxs-lookup"><span data-stu-id="d562f-160">56</span></span>|<span data-ttu-id="d562f-161">69</span><span class="sxs-lookup"><span data-stu-id="d562f-161">69</span></span>|  
|<span data-ttu-id="d562f-162">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-162">M200 Europe</span></span>|<span data-ttu-id="d562f-163">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-163">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-164">56</span><span class="sxs-lookup"><span data-stu-id="d562f-164">56</span></span>|<span data-ttu-id="d562f-165">68</span><span class="sxs-lookup"><span data-stu-id="d562f-165">68</span></span>|  
|<span data-ttu-id="d562f-166">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-166">M200 Europe</span></span>|<span data-ttu-id="d562f-167">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-167">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-168">74</span><span class="sxs-lookup"><span data-stu-id="d562f-168">74</span></span>|<span data-ttu-id="d562f-169">89</span><span class="sxs-lookup"><span data-stu-id="d562f-169">89</span></span>|  
  
 <span data-ttu-id="d562f-170">**Prodotto e regione: M200 Pacific**</span><span class="sxs-lookup"><span data-stu-id="d562f-170">**Product and Region: M200 Pacific**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="d562f-171">Modello esistente (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="d562f-171">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="d562f-172">Modello con dati di vendita aggiornati (`PredictTimeSeries` con `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="d562f-172">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="d562f-173">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d562f-173">M200 Pacific</span></span>|<span data-ttu-id="d562f-174">7/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-174">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-175">41</span><span class="sxs-lookup"><span data-stu-id="d562f-175">41</span></span>|<span data-ttu-id="d562f-176">41</span><span class="sxs-lookup"><span data-stu-id="d562f-176">41</span></span>|  
|<span data-ttu-id="d562f-177">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d562f-177">M200 Pacific</span></span>|<span data-ttu-id="d562f-178">8/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-178">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-179">44</span><span class="sxs-lookup"><span data-stu-id="d562f-179">44</span></span>|<span data-ttu-id="d562f-180">44</span><span class="sxs-lookup"><span data-stu-id="d562f-180">44</span></span>|  
|<span data-ttu-id="d562f-181">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d562f-181">M200 Pacific</span></span>|<span data-ttu-id="d562f-182">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-182">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-183">38</span><span class="sxs-lookup"><span data-stu-id="d562f-183">38</span></span>|<span data-ttu-id="d562f-184">38</span><span class="sxs-lookup"><span data-stu-id="d562f-184">38</span></span>|  
|<span data-ttu-id="d562f-185">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d562f-185">M200 Pacific</span></span>|<span data-ttu-id="d562f-186">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-186">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-187">41</span><span class="sxs-lookup"><span data-stu-id="d562f-187">41</span></span>|<span data-ttu-id="d562f-188">41</span><span class="sxs-lookup"><span data-stu-id="d562f-188">41</span></span>|  
|<span data-ttu-id="d562f-189">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d562f-189">M200 Pacific</span></span>|<span data-ttu-id="d562f-190">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-190">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-191">36</span><span class="sxs-lookup"><span data-stu-id="d562f-191">36</span></span>|<span data-ttu-id="d562f-192">36</span><span class="sxs-lookup"><span data-stu-id="d562f-192">36</span></span>|  
|<span data-ttu-id="d562f-193">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="d562f-193">M200 Pacific</span></span>|<span data-ttu-id="d562f-194">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-194">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-195">39</span><span class="sxs-lookup"><span data-stu-id="d562f-195">39</span></span>|<span data-ttu-id="d562f-196">39</span><span class="sxs-lookup"><span data-stu-id="d562f-196">39</span></span>|  
  
 <span data-ttu-id="d562f-197">Da questi risultati è possibile dedurre quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d562f-197">From these results, you can see two things:</span></span>  
  
-   <span data-ttu-id="d562f-198">Le prime due stime per la serie M200 Europe corrispondono esattamente ai nuovi dati forniti.</span><span class="sxs-lookup"><span data-stu-id="d562f-198">The first two predictions for the M200 Europe series are exactly the same as the new data you supplied.</span></span> <span data-ttu-id="d562f-199">In base alle caratteristiche di progettazione, Analysis Services restituisce i nuovi punti dati effettivi anziché eseguire una stima.</span><span class="sxs-lookup"><span data-stu-id="d562f-199">By design, Analysis Services returns the actual new data points instead of making a prediction.</span></span> <span data-ttu-id="d562f-200">Quando infatti si estendono i case del modello, gli intervalli temporali utilizzati per le query di stima iniziano sempre dalla fine della serie originale.</span><span class="sxs-lookup"><span data-stu-id="d562f-200">That is because when you extend the model cases, the time steps used for prediction queries always start at the end of the original series.</span></span> <span data-ttu-id="d562f-201">Se si aggiungono pertanto due nuovi punti dati, le prime due stime restituite si sovrappongono ai nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="d562f-201">Therefore, if you add two new data points, the first two predictions returned overlap with the new data.</span></span>  
  
-   <span data-ttu-id="d562f-202">Una volta utilizzati tutti i nuovi punti dati, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] esegue stime in base al modello aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d562f-202">After all the new data points are used up, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] makes predictions based on the updated model.</span></span> <span data-ttu-id="d562f-203">Pertanto, a partire da settembre 2005, è possibile vedere la differenza tra le stime per la serie M200 Europe nel modello originale, nella colonna a sinistra, e nel modello che utilizza EXTEND_MODEL_CASES, nella colonna a destra.</span><span class="sxs-lookup"><span data-stu-id="d562f-203">Therefore, starting in September 2005, you can see the difference between predictions for M200 Europe from the original model, in the left-hand column, and the model that uses EXTEND_MODEL_CASES, in the right-hand column.</span></span> <span data-ttu-id="d562f-204">Le stime sono diverse perché il modello è stato aggiornato con i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="d562f-204">The predictions are different because the model has been updated with the new data.</span></span>  
  
## <a name="using-start-and-end-time-steps-to-control-predictions"></a><span data-ttu-id="d562f-205">Utilizzo degli intervalli temporali di inizio e di fine per controllare le stime</span><span class="sxs-lookup"><span data-stu-id="d562f-205">Using Start and End Time Steps to Control Predictions</span></span>  
 <span data-ttu-id="d562f-206">Se si estende un modello, i nuovi dati vengono sempre aggiunti alla fine della serie.</span><span class="sxs-lookup"><span data-stu-id="d562f-206">When you extend a model, the new data is always attached to the end of the series.</span></span> <span data-ttu-id="d562f-207">Per l'esecuzione delle stime, tuttavia, gli intervalli di tempo utilizzati per le query di stima iniziano alla fine della serie originale.</span><span class="sxs-lookup"><span data-stu-id="d562f-207">However, for the purpose of prediction, the time slices used for prediction queries start at the end of the original series.</span></span> <span data-ttu-id="d562f-208">Se si desidera ottenere solo le nuove stime quando si aggiungono i nuovi dati, è necessario specificare il punto iniziale come numero di intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="d562f-208">If you want to obtain only the new predictions when you add the new data, you must specify the starting point as a number of time slices.</span></span> <span data-ttu-id="d562f-209">Per aggiungere due nuovi punti dati ed eseguire quattro nuove stime, è ad esempio necessario effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="d562f-209">For example, if you are adding two new data points and want to make four new predictions, you would do the following:</span></span>  
  
-   <span data-ttu-id="d562f-210">Creare un'istruzione PREDICTION JOIN in un modello Time Series e specificare nuovi dati relativi a due mesi.</span><span class="sxs-lookup"><span data-stu-id="d562f-210">Create a PREDICTION JOIN on a time series model, and specify two months of new data.</span></span>  
  
-   <span data-ttu-id="d562f-211">Richiedere stime per quattro intervalli di tempo, dove il punto iniziale è l'intervallo di tempo 3 e il punto finale è l'intervallo di tempo 6.</span><span class="sxs-lookup"><span data-stu-id="d562f-211">Request predictions for four time slices, where the starting point is 3, and the ending point is time slice 6.</span></span>  
  
 <span data-ttu-id="d562f-212">In altre parole, se i nuovi dati contengono n intervalli di tempo e si richiedono stime per gli intervalli temporali da 1 a n, le stime coincideranno con lo stesso periodo dei nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="d562f-212">In other words, if your new data contains n time slices, and you request predictions for time steps 1 through n, the predictions will coincide with the same period as the new data.</span></span> <span data-ttu-id="d562f-213">Per ottenere nuove stime per periodi di tempo non previsti dai dati, è necessario avviare le stime nell'intervallo di tempo n+1 dopo la nuova serie dei dati oppure verificare di aver effettuato la richiesta di ulteriori intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="d562f-213">To get new predictions for a time periods not covered by your data, you must either start predictions at the time slice n+1 after the new data series, or make sure that you request additional time slices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d562f-214">Non è possibile eseguire stime cronologiche quando si aggiungono nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="d562f-214">You cannot make historical predictions when you add new data.</span></span>  
  
 <span data-ttu-id="d562f-215">Nell'esempio seguente viene illustrata l'istruzione DMX che consente di ottenere solo le nuove stime per le due serie dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="d562f-215">The following example shows the DMX statement that lets you get only the new predictions for the two series in the previous example.</span></span>  
  
```  
SELECT [Model Region],  
PredictTimeSeries([Quantity],3,6, EXTEND_MODEL_CASES) AS PredictQty  
FROM  
   [Forecasting_MIXED]  
NATURAL PREDICTION JOIN   
   SELECT 1 AS [ReportingDate],  
  '10' AS [Quantity],  
  'M200 Europe' AS [ModelRegion]  
UNION SELECT  
  2 AS [ReportingDate],  
  15 AS [Quantity]),  
  'M200 Europe' AS [ModelRegion]  
) AS t  
WHERE [ModelRegion] = 'M200 Europe'  
```  
  
 <span data-ttu-id="d562f-216">I risultati della stima iniziano dall'intervallo di tempo 3, che è successivo ai 2 mesi dei nuovi dati forniti.</span><span class="sxs-lookup"><span data-stu-id="d562f-216">The prediction results start at time slice 3, which is after the 2 months of new data that you supplied.</span></span>  
  
 <span data-ttu-id="d562f-217">**Prodotto e area geografica: M200 Europe**</span><span class="sxs-lookup"><span data-stu-id="d562f-217">**Product and Region: M200 Europe**</span></span>  
  
 <span data-ttu-id="d562f-218">Modello con dati aggiornati (PredictTimeSeries con EXTEND_MODEL_CASES)</span><span class="sxs-lookup"><span data-stu-id="d562f-218">Model with updated data (PredictTimeSeries with EXTEND_MODEL_CASES)</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="d562f-219">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-219">M200 Europe</span></span>|<span data-ttu-id="d562f-220">9/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-220">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-221">72</span><span class="sxs-lookup"><span data-stu-id="d562f-221">72</span></span>|  
|<span data-ttu-id="d562f-222">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-222">M200 Europe</span></span>|<span data-ttu-id="d562f-223">10/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-223">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-224">69</span><span class="sxs-lookup"><span data-stu-id="d562f-224">69</span></span>|  
|<span data-ttu-id="d562f-225">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-225">M200 Europe</span></span>|<span data-ttu-id="d562f-226">11/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-226">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-227">68</span><span class="sxs-lookup"><span data-stu-id="d562f-227">68</span></span>|  
|<span data-ttu-id="d562f-228">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="d562f-228">M200 Europe</span></span>|<span data-ttu-id="d562f-229">12/25/2008 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="d562f-229">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="d562f-230">89</span><span class="sxs-lookup"><span data-stu-id="d562f-230">89</span></span>|  
  
## <a name="making-predictions-with-replace_model_cases"></a><span data-ttu-id="d562f-231">Esecuzione di stime con REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="d562f-231">Making Predictions with REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="d562f-232">La sostituzione dei case del modello risulta utile qualora si desideri eseguire il training per un modello in un case set, quindi applicare il modello a una serie di dati diversa.</span><span class="sxs-lookup"><span data-stu-id="d562f-232">Replacing the model cases is useful when you want to train a model on one set of cases and then apply that model to a different data series.</span></span> <span data-ttu-id="d562f-233">Una procedura dettagliata di questo scenario è illustrata nella [lezione 2: compilazione di uno scenario di previsione &#40;esercitazione intermedia sul Data Mining&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d562f-233">A detailed walkthrough of this scenario is presented in [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d562f-234">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d562f-234">See Also</span></span>  
 <span data-ttu-id="d562f-235">[Esempi di query sul modello Time Series](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="d562f-235">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="d562f-236">PredictTimeSeries &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="d562f-236">PredictTimeSeries &#40;DMX&#41;</span></span>](/sql/dmx/predicttimeseries-dmx)  
  
  
