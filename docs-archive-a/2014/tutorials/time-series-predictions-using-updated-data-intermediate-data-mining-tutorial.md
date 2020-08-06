---
title: Stime basate su serie temporali con dati aggiornati (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af73681d-ce1c-4b6e-b195-6df3d2fb5275
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2017defaba74071b1a12bee14a5d8907e4c71cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623630"
---
# <a name="time-series-predictions-using-updated-data-intermediate-data-mining-tutorial"></a><span data-ttu-id="effcd-102">Stime basate su serie temporali utilizzando dati aggiornati (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="effcd-102">Time Series Predictions using Updated Data (Intermediate Data Mining Tutorial)</span></span>
    
## <a name="creating-predictions-using-the-extended-sales-data"></a><span data-ttu-id="effcd-103">Creazione di stime tramite dati di vendita estesi</span><span class="sxs-lookup"><span data-stu-id="effcd-103">Creating Predictions using the Extended Sales Data</span></span>  
 <span data-ttu-id="effcd-104">In questa lezione verrà creata una query di stima che aggiunge i nuovi dati di vendita al modello.</span><span class="sxs-lookup"><span data-stu-id="effcd-104">In this lesson, you will create a prediction query that adds the new sales data to the model.</span></span> <span data-ttu-id="effcd-105">Estendendo il modello con nuovi dati, è possibile ottenere stime aggiornate che includono i punti dati più recenti.</span><span class="sxs-lookup"><span data-stu-id="effcd-105">By extending the model with new data, you can get up-to-date predictions that include the newest data points.</span></span>  
  
 <span data-ttu-id="effcd-106">La creazione di stime basate su serie temporali che utilizzano nuovi dati è semplice: è sufficiente aggiungere il parametro EXTEND_MODEL_CASES alla funzione [&#41;DMX PredictTimeSeries &#40;](/sql/dmx/predicttimeseries-dmx) , specificare l'origine dei nuovi dati e specificare il numero di stime che si desidera ottenere.</span><span class="sxs-lookup"><span data-stu-id="effcd-106">Creating time series predictions that use new data is easy: you simply add the parameter EXTEND_MODEL_CASES to the [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) function, specify the source of the new data, and specify how many predictions you want to get.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="effcd-107">Il parametro EXTEND_MODEL_CASES è facoltativo. Per impostazione predefinita, il modello viene esteso ogni volta che si crea una query di stima basata su serie temporali mediante l'unione in join di nuovi dati come input.</span><span class="sxs-lookup"><span data-stu-id="effcd-107">The parameter EXTEND_MODEL_CASES is optional; by default the model is extended any time that you create a time series prediction query by joining new data as inputs.</span></span>  
  
#### <a name="to-build-the-prediction-query-and-add-new-data"></a><span data-ttu-id="effcd-108">Per compilare la query di stima ed aggiungere nuovi dati</span><span class="sxs-lookup"><span data-stu-id="effcd-108">To build the prediction query and add new data</span></span>  
  
1.  <span data-ttu-id="effcd-109">Se il modello non è già aperto, fare doppio clic sulla struttura di previsione e in Progettazione modelli di data mining fare clic sulla scheda **Stima modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="effcd-109">If the model is not already open, double-click the Forecasting structure, and in Data Mining Designer, click the **Mining Model Prediction** tab.</span></span>  
  
2.  <span data-ttu-id="effcd-110">Nel riquadro **modello di data mining** è necessario che la previsione del modello sia già selezionata.</span><span class="sxs-lookup"><span data-stu-id="effcd-110">In the **Mining Model** pane, the model Forecasting should already be selected.</span></span> <span data-ttu-id="effcd-111">Se non è selezionata, fare clic su **Seleziona modello**, quindi selezionare il modello, previsione.</span><span class="sxs-lookup"><span data-stu-id="effcd-111">If it is not selected, click **Select Model**, and then select the model, Forecasting.</span></span>  
  
3.  <span data-ttu-id="effcd-112">Nel riquadro **Seleziona tabella/** e di input fare clic su **Seleziona tabella del case**.</span><span class="sxs-lookup"><span data-stu-id="effcd-112">In the **Select Input Table(s)** pane, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="effcd-113">Nella finestra di dialogo **Seleziona tabella** selezionare l'origine dati, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="effcd-113">In the **Select Table** dialog box, select the data source, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
     <span data-ttu-id="effcd-114">Dall'elenco di viste origine dati selezionare NewSalesData e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="effcd-114">From the list of data source views, select NewSalesData and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="effcd-115">Fare clic con il pulsante destro del mouse sulla superficie dell'area di progettazione e scegliere **modifica connessioni**.</span><span class="sxs-lookup"><span data-stu-id="effcd-115">Right-click the surface of the design area and select **Modify Connections**.</span></span>  
  
6.  <span data-ttu-id="effcd-116">Utilizzando la finestra di dialogo **Modifica mapping** , eseguire il mapping delle colonne del modello alle colonne nei dati esterni come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="effcd-116">Using the **Modify Mapping** dialog box, map the columns in the model to the columns in the external data as follows:</span></span>  
  
    -   <span data-ttu-id="effcd-117">Eseguire il mapping della colonna ReportingDate nel modello di data mining alla colonna NewDate nei dati di input.</span><span class="sxs-lookup"><span data-stu-id="effcd-117">Map the ReportingDate column in the mining model to the NewDate column in the input data.</span></span>  
  
    -   <span data-ttu-id="effcd-118">Eseguire il mapping della colonna Amount nel modello di data mining alla colonna NewAmount nei dati di input.</span><span class="sxs-lookup"><span data-stu-id="effcd-118">Map the Amount column in the mining model to the NewAmount column in the input data.</span></span>  
  
    -   <span data-ttu-id="effcd-119">Eseguire il mapping della colonna Quantity nel modello di data mining alla colonna NewQty nei dati di input.</span><span class="sxs-lookup"><span data-stu-id="effcd-119">Map the Quantity column in the mining model to the NewQty column in the input data.</span></span>  
  
    -   <span data-ttu-id="effcd-120">Eseguire il mapping della colonna ModelRegion nel modello di data mining alla colonna serie nei dati di input.</span><span class="sxs-lookup"><span data-stu-id="effcd-120">Map the ModelRegion column in the mining model to the Series column in the input data.</span></span>  
  
7.  <span data-ttu-id="effcd-121">A questo punto si compilerà la query di stima.</span><span class="sxs-lookup"><span data-stu-id="effcd-121">Now you will build the prediction query.</span></span>  
  
     <span data-ttu-id="effcd-122">Aggiungere innanzitutto una colonna alla query di stima per restituire la serie a cui si applica la stima.</span><span class="sxs-lookup"><span data-stu-id="effcd-122">First, add a column to the prediction query to output the series the prediction applies to.</span></span>  
  
    1.  <span data-ttu-id="effcd-123">Nella griglia fare clic sulla prima riga vuota, in **origine**, quindi selezionare previsioni.</span><span class="sxs-lookup"><span data-stu-id="effcd-123">In the grid, click the first empty row, under **Source**, and then select Forecasting.</span></span>  
  
    2.  <span data-ttu-id="effcd-124">Nella colonna **campo** selezionare area del modello e per **alias**digitare `Model Region` .</span><span class="sxs-lookup"><span data-stu-id="effcd-124">In the **Field** column, select Model Region and for **Alias**, type `Model Region`.</span></span>  
  
8.  <span data-ttu-id="effcd-125">Aggiungere, quindi, e modificare la funzione di stima.</span><span class="sxs-lookup"><span data-stu-id="effcd-125">Next, add and edit the prediction function.</span></span>  
  
    1.  <span data-ttu-id="effcd-126">Fare clic su una riga vuota, quindi in **origine**selezionare **funzione di stima**.</span><span class="sxs-lookup"><span data-stu-id="effcd-126">Click an empty row, and under **Source**, select **Prediction Function**.</span></span>  
  
    2.  <span data-ttu-id="effcd-127">In **campo**selezionare **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="effcd-127">For **Field**, select **PredictTimeSeries**.</span></span>  
  
    3.  <span data-ttu-id="effcd-128">Per **alias**digitare **valori stimati**.</span><span class="sxs-lookup"><span data-stu-id="effcd-128">For **Alias**, type **Predicted Values**.</span></span>  
  
    4.  <span data-ttu-id="effcd-129">Trascinare la quantità di campo dal riquadro **modello di data mining** nella colonna **criteri/argomento** .</span><span class="sxs-lookup"><span data-stu-id="effcd-129">Drag the field Quantity from the **Mining Model** pane into the **Criteria/Argument** column.</span></span>  
  
    5.  <span data-ttu-id="effcd-130">Nella colonna **criteri/argomento** , dopo il nome del campo, digitare il testo seguente: **5 EXTEND_MODEL_CASES**</span><span class="sxs-lookup"><span data-stu-id="effcd-130">In the **Criteria/Argument** column, after the field name, type the following text:  **5,EXTEND_MODEL_CASES**</span></span>  
  
         <span data-ttu-id="effcd-131">Il testo completo della casella di testo **criteri/argomento** dovrebbe essere il seguente:`[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span><span class="sxs-lookup"><span data-stu-id="effcd-131">The complete text of the **Criteria/Argument** text box should be as follows: `[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span></span>  
  
9. <span data-ttu-id="effcd-132">Fare clic su **risultati** ed esaminare i risultati.</span><span class="sxs-lookup"><span data-stu-id="effcd-132">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="effcd-133">Le stime iniziano a luglio (il primo intervallo di tempo dopo la fine dei dati originali) e terminano a novembre (il quinto intervallo di tempo dopo la fine dei dati originali).</span><span class="sxs-lookup"><span data-stu-id="effcd-133">The predictions begin in July (the first time slice after the end of the original data) and end at November (the fifth time slice after the end of the original data).</span></span>  
  
 <span data-ttu-id="effcd-134">È possibile osservare che, per utilizzare questo tipo di query di stima in modo efficiente, è necessario sapere quando terminano i dati precedenti e quanti intervalli di tempo sono presenti nei nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="effcd-134">You can see that to use this type of prediction query effectively, you need to know when the old data ends, as well as how many time slices there are in the new data.</span></span>  
  
 <span data-ttu-id="effcd-135">In questo modello, ad esempio, le serie dei dati originali terminano a giugno e i dati sono per i mesi di luglio, agosto e settembre.</span><span class="sxs-lookup"><span data-stu-id="effcd-135">For example, in this model, the original data series ended in June, and the data is for the months of July, August, and September.</span></span>  
  
 <span data-ttu-id="effcd-136">Le stime che utilizzano EXTEND_MODEL_CASES iniziano sempre alla fine della serie di dati originali.</span><span class="sxs-lookup"><span data-stu-id="effcd-136">Predictions that use EXTEND_MODEL_CASES always begin at the end of the original data series.</span></span> <span data-ttu-id="effcd-137">Pertanto, se si desidera ottenere solo le stime per i mesi sconosciuti, è necessario specificare i punti iniziale e finale per la stima.</span><span class="sxs-lookup"><span data-stu-id="effcd-137">Therefore, if you want to get only the predictions for the unknown months, you need to specify the starting point and the end point for prediction.</span></span> <span data-ttu-id="effcd-138">Entrambi valori vengono specificati come un numero di intervalli di tempo che iniziano dalla fine dei dati precedenti.</span><span class="sxs-lookup"><span data-stu-id="effcd-138">Both values are specified as a number of time slices starting at the end of the old data.</span></span>  
  
 <span data-ttu-id="effcd-139">Nella procedura riportata di seguito viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="effcd-139">The following procedure demonstrates how to do this.</span></span>  
  
### <a name="change-the-start-and-end-points-of-the-predictions"></a><span data-ttu-id="effcd-140">Modificare i punti iniziale e finale delle stime</span><span class="sxs-lookup"><span data-stu-id="effcd-140">Change the start and end points of the predictions</span></span>  
  
1.  <span data-ttu-id="effcd-141">In Generatore di query di stima fare clic su **query** per passare alla visualizzazione DMX.</span><span class="sxs-lookup"><span data-stu-id="effcd-141">In Prediction Query Builder, click **Query** to switch to DMX view.</span></span>  
  
2.  <span data-ttu-id="effcd-142">Individuare l'istruzione DMX che contiene la funzione PredictTimeSeries e modificarla come segue:</span><span class="sxs-lookup"><span data-stu-id="effcd-142">Locate the DMX statement that contains the PredictTimeSeries function and change it as follows:</span></span>  
  
     `PredictTimeSeries([Forecasting 12].[Quantity],4,6,EXTEND_MODEL_CASES)`  
  
3.  <span data-ttu-id="effcd-143">Fare clic su **risultati** ed esaminare i risultati.</span><span class="sxs-lookup"><span data-stu-id="effcd-143">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="effcd-144">Ora le stime iniziano a ottobre (il quarto intervallo di tempo, contando dalla fine dei dati originali) e terminano a dicembre (il sesto intervallo di tempo, contando dalla fine dei dati originali).</span><span class="sxs-lookup"><span data-stu-id="effcd-144">Now the predictions begin at October (the fourth time slice, counting from the end of the original data) and end at December (the sixth time slice, counting from the end of the original data).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="effcd-145">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="effcd-145">Next Task in Lesson</span></span>  
 [<span data-ttu-id="effcd-146">Stime basate su serie temporali che utilizzano dati sostitutivi &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="effcd-146">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="effcd-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="effcd-147">See Also</span></span>  
 <span data-ttu-id="effcd-148">[Riferimento tecnico per l'algoritmo Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="effcd-148">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="effcd-149">Contenuto dei modelli di data mining per i modelli Time Series &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="effcd-149">Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md)  
  
  
