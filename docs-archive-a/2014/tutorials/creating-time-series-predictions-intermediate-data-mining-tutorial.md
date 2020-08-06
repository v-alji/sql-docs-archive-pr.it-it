---
title: Creazione di stime basate su serie temporali (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: fb22cffa-ac99-4d34-ac4a-9c93068e33e8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1175cdffd1512e0cb876b9565dd0727a9f094c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625949"
---
# <a name="creating-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="86a2a-102">Creazione di stime basate su serie temporali (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="86a2a-102">Creating Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="86a2a-103">Nelle attività precedenti di questa lezione è stato creato un modello Time Series e sono stati esplorati i risultati.</span><span class="sxs-lookup"><span data-stu-id="86a2a-103">In the previous tasks in this lesson, you created a time series model and explored the results.</span></span> <span data-ttu-id="86a2a-104">Per impostazione predefinita, in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] viene sempre creato un set di cinque (5) stime per un modello Time Series e i valori stimati vengono visualizzati come parte del grafico di previsione.</span><span class="sxs-lookup"><span data-stu-id="86a2a-104">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] always creates a set of five (5) predictions for a time series model and displays the predicted values as part of the forecasting chart.</span></span> <span data-ttu-id="86a2a-105">È tuttavia possibile creare previsioni compilando query di stima DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="86a2a-105">However, you can also create forecasts by building Data Mining Extensions (DMX) prediction queries.</span></span>  
  
 <span data-ttu-id="86a2a-106">In questa attività verrà creata una query di stima che genera le stesse stime esaminate in precedenza nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="86a2a-106">In this task, you will create a prediction query that generates the same predictions that you saw in the viewer.</span></span> <span data-ttu-id="86a2a-107">Questa attività presuppone che siano già state completate le lezioni dell'Esercitazione di base sul data mining e che si abbia familiarità con l'utilizzo del generatore delle query di stima.</span><span class="sxs-lookup"><span data-stu-id="86a2a-107">This task assumes that you have already completed the lessons in the Basic Data Mining Tutorial and are familiar with how to use Prediction Query Builder.</span></span> <span data-ttu-id="86a2a-108">Verrà ora illustrato come creare query specifiche per i modelli Time Series.</span><span class="sxs-lookup"><span data-stu-id="86a2a-108">You will now learn how to create queries specific to time series models.</span></span>  
  
## <a name="creating-time-series-predictions"></a><span data-ttu-id="86a2a-109">Creazione di stime basate su serie temporali</span><span class="sxs-lookup"><span data-stu-id="86a2a-109">Creating Time Series Predictions</span></span>  
 <span data-ttu-id="86a2a-110">In genere il primo passaggio per creare una query di stima consiste nel selezionare un modello di data mining e una tabella di input.</span><span class="sxs-lookup"><span data-stu-id="86a2a-110">Typically, the first step in creating a prediction query is to select a mining model and input table.</span></span> <span data-ttu-id="86a2a-111">Tuttavia, un modello Time Series non richiede input aggiuntivi per una stima normale.</span><span class="sxs-lookup"><span data-stu-id="86a2a-111">However, a time series model does not require additional input for a regular prediction.</span></span> <span data-ttu-id="86a2a-112">Non è pertanto necessario specificare una nuova origine dati durante l'esecuzione di stime, a meno che non si aggiungano o sostituiscano dati nel modello.</span><span class="sxs-lookup"><span data-stu-id="86a2a-112">Therefore, you do not need to specify a new source of data when making predictions, unless you are adding data to the model or replacing the data.</span></span>  
  
 <span data-ttu-id="86a2a-113">Ai fini di questa lezione è necessario specificare il numero di intervalli per la stima.</span><span class="sxs-lookup"><span data-stu-id="86a2a-113">For this lesson, you must specify the number of prediction steps.</span></span> <span data-ttu-id="86a2a-114">È inoltre possibile specificare il nome della serie per ottenere una stima per una determinata combinazione di prodotto e area.</span><span class="sxs-lookup"><span data-stu-id="86a2a-114">You can specify the series name, to get a prediction for a particular combination of a product and a region.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="86a2a-115">Per selezionare un modello e una tabella di input</span><span class="sxs-lookup"><span data-stu-id="86a2a-115">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="86a2a-116">Nella scheda **Stima modello** di data mining di progettazione modelli di data mining fare clic su **Seleziona modello**nella casella **modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="86a2a-116">On the **Mining Model Prediction** tab of the Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="86a2a-117">Nella finestra di dialogo **Seleziona modello di data mining** espandere la struttura Forecasting, selezionare il modello **Forecasting** dall'elenco, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-117">In the **Select Mining Model** dialog box, expand the Forecasting structure, select the **Forecasting** model from the list, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="86a2a-118">Ignorare la casella **Seleziona tabella/** e di input.</span><span class="sxs-lookup"><span data-stu-id="86a2a-118">Ignore the **Select Input Table(s)** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="86a2a-119">Per i modelli Time Series non è necessario specificare un input distinto, a meno che non si stia eseguendo una stima incrociata.</span><span class="sxs-lookup"><span data-stu-id="86a2a-119">For a time series model, you do not need to specify a separate input unless you are doing cross-prediction.</span></span>  
  
4.  <span data-ttu-id="86a2a-120">Nella colonna **origine** , nella griglia della scheda **Stima modello di data mining** , fare clic sulla cella nella prima riga vuota, quindi selezionare **modello di data mining Forecasting**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-120">In the **Source** column, in the grid on the **Mining Model Prediction** tab, click the cell in the first empty row, and then select **Forecasting mining model**.</span></span>  
  
5.  <span data-ttu-id="86a2a-121">Nella colonna **campo** selezionare area del **modello**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-121">In the **Field** column, select **Model Region**.</span></span>  
  
     <span data-ttu-id="86a2a-122">L'identificatore della serie verrà aggiunto alla query di stima per indicare a quale combinazione di modello e area si applica la stima.</span><span class="sxs-lookup"><span data-stu-id="86a2a-122">This action adds the series identifier to the prediction query to indicate the combination of model and region to which the prediction applies.</span></span>  
  
6.  <span data-ttu-id="86a2a-123">Fare clic sulla riga vuota successiva nella colonna **origine** , quindi selezionare **funzione di stima**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-123">Click the next empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
7.  <span data-ttu-id="86a2a-124">Nella colonna **campo** selezionare **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-124">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="86a2a-125">Con i modelli Time Series è inoltre possibile utilizzare la funzione `Predict`.</span><span class="sxs-lookup"><span data-stu-id="86a2a-125">You can also use the `Predict` function with time series models.</span></span> <span data-ttu-id="86a2a-126">Per impostazione predefinita, tuttavia, la funzione Predict crea una sola stima per ogni serie.</span><span class="sxs-lookup"><span data-stu-id="86a2a-126">However, by default, the Predict function creates only one prediction for each series.</span></span> <span data-ttu-id="86a2a-127">Pertanto, per specificare più passaggi di stima, è necessario utilizzare la funzione **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="86a2a-127">Therefore, to specify multiple prediction steps, you must use the **PredictTimeSeries** function.</span></span>  
  
8.  <span data-ttu-id="86a2a-128">Nel riquadro **modello di data mining** selezionare la colonna modello di data mining **Amount.**</span><span class="sxs-lookup"><span data-stu-id="86a2a-128">In the **Mining Model** pane, select the mining model column, **Amount.**</span></span> <span data-ttu-id="86a2a-129">Trascinare Amount nella casella **criteri/argomento** per la funzione **PredictTimeSeries** aggiunta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="86a2a-129">Drag Amount to the **Criteria/Arguments** box for the **PredictTimeSeries** function that you added earlier.</span></span>  
  
9. <span data-ttu-id="86a2a-130">Fare clic sulla casella **criteri/argomento** e digitare una virgola, seguita da **5**, dopo il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="86a2a-130">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="86a2a-131">Il testo nella casella **criteri/argomento** dovrebbe ora visualizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="86a2a-131">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[Amount],5`  
  
10. <span data-ttu-id="86a2a-132">Nella colonna **alias** Digitare `PredictAmount` .</span><span class="sxs-lookup"><span data-stu-id="86a2a-132">In the **Alias** column, type `PredictAmount`.</span></span>  
  
11. <span data-ttu-id="86a2a-133">Fare clic sulla riga vuota successiva nella colonna **origine** , quindi selezionare di nuovo **funzione di stima** .</span><span class="sxs-lookup"><span data-stu-id="86a2a-133">Click the next empty row in the **Source** column, and then select **Prediction Function** again.</span></span>  
  
12. <span data-ttu-id="86a2a-134">Nella colonna **campo** selezionare **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-134">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
13. <span data-ttu-id="86a2a-135">Nel riquadro **modello di data mining** selezionare la colonna Quantity e quindi trascinarla nella casella **criteri/argomento** della seconda funzione **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="86a2a-135">In the **Mining Model** pane, select the column Quantity, and then drag it into the **Criteria/Arguments** box for the second **PredictTimeSeries** function.</span></span>  
  
14. <span data-ttu-id="86a2a-136">Fare clic sulla casella **criteri/argomento** e digitare una virgola, seguita da **5**, dopo il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="86a2a-136">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="86a2a-137">Il testo nella casella **criteri/argomento** dovrebbe ora visualizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="86a2a-137">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[ Quantity],5`  
  
15. <span data-ttu-id="86a2a-138">Nella colonna **alias** Digitare `PredictQuantity` .</span><span class="sxs-lookup"><span data-stu-id="86a2a-138">In the **Alias** column, type `PredictQuantity`.</span></span>  
  
16. <span data-ttu-id="86a2a-139">Fare clic su **passa alla visualizzazione risultati della query**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-139">Click **Switch to query result view**.</span></span>  
  
     <span data-ttu-id="86a2a-140">I risultati della query verranno visualizzati in formato tabulare.</span><span class="sxs-lookup"><span data-stu-id="86a2a-140">The results of the query are displayed in tabular format.</span></span>  
  
 <span data-ttu-id="86a2a-141">Tenere presente che sono stati creati tre tipi diversi di risultati nel generatore di query, uno che utilizza i valori di una colonna e due che ottengono i valori stimati da una funzione di stima.</span><span class="sxs-lookup"><span data-stu-id="86a2a-141">Remember that you created three different types of results in the query builder, one that uses values from a column, and two that get predicted values from a prediction function.</span></span> <span data-ttu-id="86a2a-142">I risultati della query contengono pertanto tre colonne distinte.</span><span class="sxs-lookup"><span data-stu-id="86a2a-142">Therefore, the results of the query contain three separate columns.</span></span> <span data-ttu-id="86a2a-143">La prima colonna contiene l'elenco di combinazioni di prodotto e area,</span><span class="sxs-lookup"><span data-stu-id="86a2a-143">The first column contains the list of product and region combinations.</span></span> <span data-ttu-id="86a2a-144">mentre la seconda e la terza contengono ciascuna una tabella nidificata dei risultati della stima.</span><span class="sxs-lookup"><span data-stu-id="86a2a-144">The second and third columns each contain a nested table of prediction results.</span></span> <span data-ttu-id="86a2a-145">Ogni tabella nidificata contiene intervalli temporali e valori stimati, come nella tabella di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="86a2a-145">Each nested table contains the time step and predicted values, such as the following table:</span></span>  
  
 <span data-ttu-id="86a2a-146">Risultati di esempio (le quantità sono troncate a due posizioni decimali):</span><span class="sxs-lookup"><span data-stu-id="86a2a-146">Example results (amounts are truncated to two decimal places):</span></span>  
  
 <span data-ttu-id="86a2a-147">**M200 Europe PredictAmount**</span><span class="sxs-lookup"><span data-stu-id="86a2a-147">**M200 Europe PredictAmount**</span></span>  
  
|<span data-ttu-id="86a2a-148">$TIME</span><span class="sxs-lookup"><span data-stu-id="86a2a-148">$TIME</span></span>|<span data-ttu-id="86a2a-149">Amount</span><span class="sxs-lookup"><span data-stu-id="86a2a-149">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="86a2a-150">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-150">7/25/2008</span></span>|<span data-ttu-id="86a2a-151">99978,00</span><span class="sxs-lookup"><span data-stu-id="86a2a-151">99978.00</span></span>|  
|<span data-ttu-id="86a2a-152">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-152">8/25/2008</span></span>|<span data-ttu-id="86a2a-153">145575,07</span><span class="sxs-lookup"><span data-stu-id="86a2a-153">145575.07</span></span>|  
|<span data-ttu-id="86a2a-154">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-154">9/25/2008</span></span>|<span data-ttu-id="86a2a-155">116835,19</span><span class="sxs-lookup"><span data-stu-id="86a2a-155">116835.19</span></span>|  
|<span data-ttu-id="86a2a-156">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-156">10/25/2008</span></span>|<span data-ttu-id="86a2a-157">116537,38</span><span class="sxs-lookup"><span data-stu-id="86a2a-157">116537.38</span></span>|  
|<span data-ttu-id="86a2a-158">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-158">11/25/2008</span></span>|<span data-ttu-id="86a2a-159">107760,55</span><span class="sxs-lookup"><span data-stu-id="86a2a-159">107760.55</span></span>|  
  
 <span data-ttu-id="86a2a-160">**M200 Europe PredictQuantity**</span><span class="sxs-lookup"><span data-stu-id="86a2a-160">**M200 Europe PredictQuantity**</span></span>  
  
|<span data-ttu-id="86a2a-161">$TIME</span><span class="sxs-lookup"><span data-stu-id="86a2a-161">$TIME</span></span>|<span data-ttu-id="86a2a-162">Quantità</span><span class="sxs-lookup"><span data-stu-id="86a2a-162">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="86a2a-163">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-163">7/25/2008</span></span>|<span data-ttu-id="86a2a-164">52</span><span class="sxs-lookup"><span data-stu-id="86a2a-164">52</span></span>|  
|<span data-ttu-id="86a2a-165">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-165">8/25/2008</span></span>|<span data-ttu-id="86a2a-166">67</span><span class="sxs-lookup"><span data-stu-id="86a2a-166">67</span></span>|  
|<span data-ttu-id="86a2a-167">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-167">9/25/2008</span></span>|<span data-ttu-id="86a2a-168">58</span><span class="sxs-lookup"><span data-stu-id="86a2a-168">58</span></span>|  
|<span data-ttu-id="86a2a-169">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-169">10/25/2008</span></span>|<span data-ttu-id="86a2a-170">57</span><span class="sxs-lookup"><span data-stu-id="86a2a-170">57</span></span>|  
|<span data-ttu-id="86a2a-171">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-171">11/25/2008</span></span>|<span data-ttu-id="86a2a-172">54</span><span class="sxs-lookup"><span data-stu-id="86a2a-172">54</span></span>|  
  
 <span data-ttu-id="86a2a-173">**M200 America del Nord-PredictAmount**</span><span class="sxs-lookup"><span data-stu-id="86a2a-173">**M200 North America - PredictAmount**</span></span>  
  
|<span data-ttu-id="86a2a-174">$TIME</span><span class="sxs-lookup"><span data-stu-id="86a2a-174">$TIME</span></span>|<span data-ttu-id="86a2a-175">Amount</span><span class="sxs-lookup"><span data-stu-id="86a2a-175">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="86a2a-176">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-176">7/25/2008</span></span>|<span data-ttu-id="86a2a-177">348533,93</span><span class="sxs-lookup"><span data-stu-id="86a2a-177">348533.93</span></span>|  
|<span data-ttu-id="86a2a-178">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-178">8/25/2008</span></span>|<span data-ttu-id="86a2a-179">340097,98</span><span class="sxs-lookup"><span data-stu-id="86a2a-179">340097.98</span></span>|  
|<span data-ttu-id="86a2a-180">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-180">9/25/2008</span></span>|<span data-ttu-id="86a2a-181">257986,19</span><span class="sxs-lookup"><span data-stu-id="86a2a-181">257986.19</span></span>|  
|<span data-ttu-id="86a2a-182">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-182">10/25/2008</span></span>|<span data-ttu-id="86a2a-183">374658,24</span><span class="sxs-lookup"><span data-stu-id="86a2a-183">374658.24</span></span>|  
|<span data-ttu-id="86a2a-184">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-184">11/25/2008</span></span>|<span data-ttu-id="86a2a-185">379241,44</span><span class="sxs-lookup"><span data-stu-id="86a2a-185">379241.44</span></span>|  
  
 <span data-ttu-id="86a2a-186">**M200 America del Nord-PredictQuantity**</span><span class="sxs-lookup"><span data-stu-id="86a2a-186">**M200 North America - PredictQuantity**</span></span>  
  
|<span data-ttu-id="86a2a-187">$TIME</span><span class="sxs-lookup"><span data-stu-id="86a2a-187">$TIME</span></span>|<span data-ttu-id="86a2a-188">Quantità</span><span class="sxs-lookup"><span data-stu-id="86a2a-188">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="86a2a-189">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-189">7/25/2008</span></span>|<span data-ttu-id="86a2a-190">272</span><span class="sxs-lookup"><span data-stu-id="86a2a-190">272</span></span>|  
|<span data-ttu-id="86a2a-191">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-191">8/25/2008</span></span>|<span data-ttu-id="86a2a-192">152</span><span class="sxs-lookup"><span data-stu-id="86a2a-192">152</span></span>|  
|<span data-ttu-id="86a2a-193">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-193">9/25/2008</span></span>|<span data-ttu-id="86a2a-194">250</span><span class="sxs-lookup"><span data-stu-id="86a2a-194">250</span></span>|  
|<span data-ttu-id="86a2a-195">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-195">10/25/2008</span></span>|<span data-ttu-id="86a2a-196">181</span><span class="sxs-lookup"><span data-stu-id="86a2a-196">181</span></span>|  
|<span data-ttu-id="86a2a-197">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="86a2a-197">11/25/2008</span></span>|<span data-ttu-id="86a2a-198">290</span><span class="sxs-lookup"><span data-stu-id="86a2a-198">290</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="86a2a-199">Le date utilizzate nel database di esempio sono state modificate per questa versione.</span><span class="sxs-lookup"><span data-stu-id="86a2a-199">The dates that are used in the sample database have changed for this release.</span></span> <span data-ttu-id="86a2a-200">Se si utilizza una versione precedente dei dati di esempio, è possibile che vengano visualizzati risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="86a2a-200">If you are using an earlier version of the sample data, you might see different results.</span></span>  
  
## <a name="saving-the-prediction-results"></a><span data-ttu-id="86a2a-201">Salvataggio dei risultati della stima</span><span class="sxs-lookup"><span data-stu-id="86a2a-201">Saving the Prediction Results</span></span>  
 <span data-ttu-id="86a2a-202">Le opzioni per l'utilizzo dei risultati della stima sono molte.</span><span class="sxs-lookup"><span data-stu-id="86a2a-202">You have several different options for using the prediction results.</span></span> <span data-ttu-id="86a2a-203">È possibile rendere i risultati bidimensionali, copiare i dati dalla vista dei risultati e incollarli in un foglio di lavoro di Excel o in un altro file.</span><span class="sxs-lookup"><span data-stu-id="86a2a-203">You can flatten the results, copy the data from the Results view, and paste it into an Excel worksheet or other file.</span></span>  
  
 <span data-ttu-id="86a2a-204">Per semplificare il processo di salvataggio dei risultati, in Data Mining Designer è inoltre possibile salvare i dati in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="86a2a-204">To simplify the process of saving results, Data Mining Designer also provides the ability to save the data to a data source view.</span></span> <span data-ttu-id="86a2a-205">La funzionalità per salvare risultati in una vista origine dati è disponibile solo in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86a2a-205">The functionality for saving results to a data source view is available only in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="86a2a-206">I risultati possono essere archiviati solo in un formato bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="86a2a-206">The results can only be stored in a flattened format.</span></span>  
  
#### <a name="to-flatten-the-results-in-the-results-pane"></a><span data-ttu-id="86a2a-207">Per convertire i dati in formato flat nel riquadro Risultati</span><span class="sxs-lookup"><span data-stu-id="86a2a-207">To flatten the results in the Results pane</span></span>  
  
1.  <span data-ttu-id="86a2a-208">In Generatore di query di stima fare clic su **passa alla visualizzazione di progettazione query**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-208">In the Prediction Query Builder, click **Switch to query design view**.</span></span>  
  
     <span data-ttu-id="86a2a-209">La visualizzazione cambierà per consentire la modifica manuale del testo della query DMX.</span><span class="sxs-lookup"><span data-stu-id="86a2a-209">The view changes to allow manual editing of the DMX query text.</span></span>  
  
2.  <span data-ttu-id="86a2a-210">Digitare la parola chiave `FLATTENED` dopo la parola chiave `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="86a2a-210">Type the `FLATTENED` keyword after the `SELECT` keyword.</span></span> <span data-ttu-id="86a2a-211">Il testo completo della query dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="86a2a-211">The complete query text should be as follows:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    ```  
  
3.  <span data-ttu-id="86a2a-212">Facoltativamente, è possibile digitare una clausola per limitare i risultati, simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="86a2a-212">Optionally, you can type a clause to restrict the results, such as the following example:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    WHERE [Forecasting].[Model Region] = 'M200 North America'   
    OR [Forecasting].[Model Region] = 'M200 Europe'  
  
    ```  
  
4.  <span data-ttu-id="86a2a-213">Fare clic su **passa alla visualizzazione risultati della query**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-213">Click **Switch to query result view**.</span></span>  
  
#### <a name="to-export-prediction-query-results"></a><span data-ttu-id="86a2a-214">Per esportare i risultati della query di stima</span><span class="sxs-lookup"><span data-stu-id="86a2a-214">To export prediction query results</span></span>  
  
1.  <span data-ttu-id="86a2a-215">Fare clic su **Salva risultati query**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-215">Click **Save query results**.</span></span>  
  
2.  <span data-ttu-id="86a2a-216">Nella finestra di dialogo **Salva risultati query di data mining** selezionare per **origine dati** [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86a2a-216">In the **Save Data Mining Query Result** dialog box, for **Data Source**, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="86a2a-217">Se si desidera salvare i dati in un database relazionale diverso, è inoltre possibile creare una nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="86a2a-217">You can also create a data source if you want to save the data to a different relational database.</span></span>  
  
3.  <span data-ttu-id="86a2a-218">Nella colonna **nome tabella** Digitare un nuovo nome di tabella temporanea, ad esempio **stime dei test**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-218">In the **Table Name** column, type a new temporary table name, such as **Test Predictions**.</span></span>  
  
4.  <span data-ttu-id="86a2a-219">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="86a2a-219">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="86a2a-220">Per visualizzare la tabella creata, creare una connessione al motore di database dell'istanza in cui sono stati salvati i dati, quindi creare una query.</span><span class="sxs-lookup"><span data-stu-id="86a2a-220">To view the table that you created, create a connection to the database engine of the instance where you saved the data, and create a query.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="86a2a-221">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="86a2a-221">Conclusion</span></span>  
 <span data-ttu-id="86a2a-222">Si è appreso come compilare un modello Time Series di base, interpretare le previsioni e creare stime.</span><span class="sxs-lookup"><span data-stu-id="86a2a-222">You have learned how to build a basic time series model, interpret the forecasts, and create predictions.</span></span>  
  
 <span data-ttu-id="86a2a-223">Le attività restanti in questa esercitazione sono facoltative e descrivono stime avanzate basate su serie temporali.</span><span class="sxs-lookup"><span data-stu-id="86a2a-223">The remaining tasks in this tutorial are optional, and describe advanced time series predictions.</span></span> <span data-ttu-id="86a2a-224">Se si decide di procedere, verrà illustrata la procedura per aggiungere nuovi dati al modello e creare stime nella serie estesa.</span><span class="sxs-lookup"><span data-stu-id="86a2a-224">If you decide to go on, you will learn how to add new data to your model and create predictions on the extended series.</span></span> <span data-ttu-id="86a2a-225">Verrà inoltre illustrata la procedura per eseguire una stima incrociata, tramite la tendenza nel modello ma sostituendo i dati con una nuova serie di dati.</span><span class="sxs-lookup"><span data-stu-id="86a2a-225">You will also learn how to perform cross-prediction, by using the trend in the model but replacing the data with a new series of data.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="86a2a-226">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="86a2a-226">Next Lesson</span></span>  
 [<span data-ttu-id="86a2a-227">Stime avanzate basate su serie temporali &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="86a2a-227">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="86a2a-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86a2a-228">See Also</span></span>  
 [<span data-ttu-id="86a2a-229">Time Series Model Query Examples</span><span class="sxs-lookup"><span data-stu-id="86a2a-229">Time Series Model Query Examples</span></span>](../../2014/analysis-services/data-mining/time-series-model-query-examples.md)  
  
  
