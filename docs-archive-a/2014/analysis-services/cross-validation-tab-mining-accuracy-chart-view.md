---
title: Scheda convalida incrociata (vista Grafico accuratezza modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.crossvalidation.f1
ms.assetid: bd215a68-1ad7-4046-9c44-ec8e2be13a64
author: minewiskan
ms.author: owend
ms.openlocfilehash: 867bd6d1abffb29ec3eb2a8a78e562e5cbcc5b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627564"
---
# <a name="cross-validation-tab-mining-accuracy-chart-view"></a><span data-ttu-id="61ec2-102">Scheda Convalida incrociata (vista Grafico accuratezza modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="61ec2-102">Cross-Validation Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="61ec2-103">La convalida incrociata consente di partizionare una struttura di data mining in sezioni trasversali, eseguire in maniera iterativa il training dei modelli e testarli a fronte di ciascuna sezione trasversale.</span><span class="sxs-lookup"><span data-stu-id="61ec2-103">Cross-validation lets you partition a mining structure into cross-sections and iteratively train and test models against each cross-section.</span></span> <span data-ttu-id="61ec2-104">È possibile specificare un numero di riduzioni in cui suddividere i dati. Ciascuna riduzione viene a sua volta utilizzata come dati di test, mentre i dati rimanenti vengono usati per eseguire il training di un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="61ec2-104">You specify a number of folds to divide the data into, and each fold is used in turn as the test data, whereas the remaining data is used to train a new model.</span></span> <span data-ttu-id="61ec2-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] viene quindi generato un set di misure di accuratezza standard per ogni modello.</span><span class="sxs-lookup"><span data-stu-id="61ec2-105">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] then generates a set of standard accuracy metrics for each model.</span></span> <span data-ttu-id="61ec2-106">Confrontando le misure relative ai modelli generati per ogni sezione trasversale, è possibile valutare l'affidabilità del modello di data mining per l'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="61ec2-106">By comparing the metrics for the models generated for each cross-section, you can get a good idea of how reliable the mining model is for the whole data set.</span></span>  
  
 <span data-ttu-id="61ec2-107">Per altre informazioni, vedere [Convalida incrociata &#40;Analysis Services - Data mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="61ec2-107">For more information, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61ec2-108">Non è possibile usare la funzione di convalida incrociata con i modelli compilati mediante l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series o [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering.</span><span class="sxs-lookup"><span data-stu-id="61ec2-108">Cross-validation cannot be used with models that were built by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span> <span data-ttu-id="61ec2-109">Se si esegue il report su una struttura di data mining che contiene tali tipi di modelli, questi ultimi non saranno inclusi nel report.</span><span class="sxs-lookup"><span data-stu-id="61ec2-109">If you run the report on a mining structure that contains these types of models, the models will not be included in the report.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="61ec2-110">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="61ec2-110">Task List</span></span>  
  
-   <span data-ttu-id="61ec2-111">Specificare il numero di riduzioni.</span><span class="sxs-lookup"><span data-stu-id="61ec2-111">Specify the number of folds.</span></span>  
  
-   <span data-ttu-id="61ec2-112">Specificare il numero massimo di case da utilizzare per la convalida incrociata.</span><span class="sxs-lookup"><span data-stu-id="61ec2-112">Specify the maximum number of cases to use for cross-validation.</span></span>  
  
-   <span data-ttu-id="61ec2-113">Specificare la colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="61ec2-113">Specify the predictable column.</span></span>  
  
-   <span data-ttu-id="61ec2-114">Se si desidera, specificare un stato stimabile.</span><span class="sxs-lookup"><span data-stu-id="61ec2-114">Optionally, specify a predictable state.</span></span>  
  
-   <span data-ttu-id="61ec2-115">Se si desidera, impostare i parametri che consentono di controllare la modalità di valutazione dell'accuratezza della stima.</span><span class="sxs-lookup"><span data-stu-id="61ec2-115">Optionally, set parameters that control how the accuracy of prediction is assessed.</span></span>  
  
-   <span data-ttu-id="61ec2-116">Fare clic su **Ottieni risultati** per visualizzare i risultati della convalida incrociata.</span><span class="sxs-lookup"><span data-stu-id="61ec2-116">Click **Get Results** to display the results of cross-validation.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="61ec2-117">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="61ec2-117">UI element list</span></span>  
 <span data-ttu-id="61ec2-118">**Conteggio di riduzioni**</span><span class="sxs-lookup"><span data-stu-id="61ec2-118">**Fold Count**</span></span>  
 <span data-ttu-id="61ec2-119">Specificare il numero di riduzioni, o partizioni, da creare.</span><span class="sxs-lookup"><span data-stu-id="61ec2-119">Specify the number of folds, or partitions, to create.</span></span> <span data-ttu-id="61ec2-120">Poiché il valore minimo è 2, metà del set di dati viene utilizzata per il testing e l'altra metà per il training.</span><span class="sxs-lookup"><span data-stu-id="61ec2-120">The minimum value is 2, meaning that half the data set is used for testing and half for training.</span></span>  
  
 <span data-ttu-id="61ec2-121">Per le strutture di data mining di sessione, il valore massimo è 10.</span><span class="sxs-lookup"><span data-stu-id="61ec2-121">The maximum value is 10 for session mining structures.</span></span>  
  
 <span data-ttu-id="61ec2-122">Se la struttura di data mining è archiviata in un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], il valore massimo è 256.</span><span class="sxs-lookup"><span data-stu-id="61ec2-122">The maximum value is 256 if the mining structure is stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61ec2-123">Aumentando il numero di riduzioni, aumenta anche il tempo necessario per l'esecuzione della convalida incrociata.</span><span class="sxs-lookup"><span data-stu-id="61ec2-123">As you increase the number of folds, the time that is required to perform cross-validation similarly increases by n.</span></span> <span data-ttu-id="61ec2-124">È possibile che si verifichino problemi di prestazioni se il numero di case e il valore di **Conteggio di riduzione** sono grandi.</span><span class="sxs-lookup"><span data-stu-id="61ec2-124">You might experience performance issues if the number of cases is large and the value of **Fold Count** is also large.</span></span>  
  
 <span data-ttu-id="61ec2-125">**Numero massimo di case**</span><span class="sxs-lookup"><span data-stu-id="61ec2-125">**Max Cases**</span></span>  
 <span data-ttu-id="61ec2-126">Specificare il numero massimo di case da utilizzare per la convalida incrociata.</span><span class="sxs-lookup"><span data-stu-id="61ec2-126">Specify the maximum number of cases to use for cross-validation.</span></span> <span data-ttu-id="61ec2-127">Il numero di case in una determinata riduzione corrisponde al valore **Numero massimo di case** diviso per il valore **Conteggio di riduzione** .</span><span class="sxs-lookup"><span data-stu-id="61ec2-127">The number of cases in any particular fold is equal to the **Max Cases** value divided by the **Fold Count** value.</span></span>  
  
 <span data-ttu-id="61ec2-128">Se **0**è il valore specificato, tutti i case nei dati di origine vengono usati per la convalida incrociata.</span><span class="sxs-lookup"><span data-stu-id="61ec2-128">If you use **0**, all cases in the source data are used for cross-validation.</span></span>  
  
 <span data-ttu-id="61ec2-129">Non è disponibile alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="61ec2-129">There is no default value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61ec2-130">Il tempo di elaborazione è direttamente proporzionale all'aumento del numero di case.</span><span class="sxs-lookup"><span data-stu-id="61ec2-130">As you increase the number of cases, processing time also increases.</span></span>  
  
 <span data-ttu-id="61ec2-131">**Attributo di destinazione**</span><span class="sxs-lookup"><span data-stu-id="61ec2-131">**Target Attribute**</span></span>  
 <span data-ttu-id="61ec2-132">Selezionare una colonna dall'elenco di colonne stimabili presenti in tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="61ec2-132">Select a column from the list of predictable columns found in all models.</span></span> <span data-ttu-id="61ec2-133">Per ciascuna operazione di convalida incrociata è possibile selezionare solo una colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="61ec2-133">You can only select one predictable column every time that you perform cross-validation.</span></span>  
  
 <span data-ttu-id="61ec2-134">Per testare solo i modelli di clustering, selezionare **Cluster**.</span><span class="sxs-lookup"><span data-stu-id="61ec2-134">To test only clustering models, select **Cluster**.</span></span>  
  
 <span data-ttu-id="61ec2-135">**Stato di destinazione**</span><span class="sxs-lookup"><span data-stu-id="61ec2-135">**Target State**</span></span>  
 <span data-ttu-id="61ec2-136">Digitare un valore o selezionarne uno di destinazione da un elenco a discesa di valori.</span><span class="sxs-lookup"><span data-stu-id="61ec2-136">Type a value, or select a target value from a drop-down list of values.</span></span>  
  
 <span data-ttu-id="61ec2-137">Il valore predefinito è `null`, ad indicare che deve essere eseguito il test di tutti gli stati.</span><span class="sxs-lookup"><span data-stu-id="61ec2-137">The default value is `null`, indicating that all states are to be tested.</span></span>  
  
 <span data-ttu-id="61ec2-138">Opzione disabilitata per i modelli di clustering.</span><span class="sxs-lookup"><span data-stu-id="61ec2-138">Disabled for clustering models.</span></span>  
  
 <span data-ttu-id="61ec2-139">**Target\*\*\*\*Soglia** di destinazione  </span><span class="sxs-lookup"><span data-stu-id="61ec2-139">**Target**  **Threshold**</span></span>  
 <span data-ttu-id="61ec2-140">Specificare un valore compreso tra 0 e 1 per indicare la probabilità di stima al di sopra della quale uno stato stimato viene considerato corretto.</span><span class="sxs-lookup"><span data-stu-id="61ec2-140">Specify a value between 0 and 1 that indicates the prediction probability above which a predicted state is considered to be correct.</span></span> <span data-ttu-id="61ec2-141">Il valore può essere impostato con incrementi di 0,1.</span><span class="sxs-lookup"><span data-stu-id="61ec2-141">The value can be set in 0.1 increments.</span></span>  
  
 <span data-ttu-id="61ec2-142">Il valore predefinito è `null`, ad indicare che la stima più probabile viene conteggiata come corretta.</span><span class="sxs-lookup"><span data-stu-id="61ec2-142">The default is `null`, indicating that the most probable prediction is counted as correct.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61ec2-143">Anche se è possibile impostare 0,0, l'utilizzo di questo valore aumenta il tempo di elaborazione e non produce risultati significativi.</span><span class="sxs-lookup"><span data-stu-id="61ec2-143">Although you can set the value to 0.0, using this value will increase processing time and not yield meaningful results.</span></span>  
  
 <span data-ttu-id="61ec2-144">**Ottieni risultati**</span><span class="sxs-lookup"><span data-stu-id="61ec2-144">**Get Results**</span></span>  
 <span data-ttu-id="61ec2-145">Fare clic per avviare la convalida incrociata del modello mediante i parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="61ec2-145">Click to begin cross-validation of the model using the specified parameters.</span></span>  
  
 <span data-ttu-id="61ec2-146">Il modello viene partizionato nel numero specificato di riduzioni e viene eseguito il test di un modello distinto per ciascuna riduzione.</span><span class="sxs-lookup"><span data-stu-id="61ec2-146">The model is partitioned into the specified number of folds and a separate model is tested for each fold.</span></span> <span data-ttu-id="61ec2-147">La restituzione di risultati da parte della convalida incrociata potrebbe pertanto richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="61ec2-147">Therefore, it might take some time for cross-validation to return the results.</span></span>  
  
 <span data-ttu-id="61ec2-148">Per altre informazioni sull'interpretazione dei risultati del report di convalida incrociata, vedere [Misure nel report di convalida incrociata](data-mining/measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="61ec2-148">For more information about how to interpret the results of the cross-validation report, see [Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md).</span></span>  
  
## <a name="setting-the-accuracy-threshold"></a><span data-ttu-id="61ec2-149">Impostazione della soglia di accuratezza</span><span class="sxs-lookup"><span data-stu-id="61ec2-149">Setting the Accuracy Threshold</span></span>  
 <span data-ttu-id="61ec2-150">È possibile controllare lo standard per valutare l'accuratezza della stima impostando un valore per l'opzione **Soglia** **di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="61ec2-150">You can control the standard for measuring prediction accuracy by setting a value for **Target** **Threshold**.</span></span> <span data-ttu-id="61ec2-151">Una soglia rappresenta una sorta di barra di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="61ec2-151">A threshold represents a kind of accuracy bar.</span></span> <span data-ttu-id="61ec2-152">A ogni stima viene assegnata una probabilità di correttezza del valore stimato.</span><span class="sxs-lookup"><span data-stu-id="61ec2-152">Each prediction is assigned a probability that the predicted value is correct.</span></span> <span data-ttu-id="61ec2-153">Se si imposta pertanto **Soglia** **di destinazione** su un valore più prossimo a 1, si richiede che la probabilità per una determinata stima sia abbastanza elevata da essere considerata come affidabile.</span><span class="sxs-lookup"><span data-stu-id="61ec2-153">Therefore, if you set the **Target** **Threshold** value closer to 1, you are requiring that the probability for any particular prediction to be fairly high to be counted as a good prediction.</span></span> <span data-ttu-id="61ec2-154">Viceversa, se si imposta il valore **Soglia** **di destinazione** più prossimo a 0, anche le stime con i valori di probabilità più bassi vengono considerate come affidabili.</span><span class="sxs-lookup"><span data-stu-id="61ec2-154">Conversely, if you set **Target** **Threshold** closer to 0, even predictions with lower probability values are counted as "good" predictions.</span></span>  
  
 <span data-ttu-id="61ec2-155">Non esiste un valore soglia consigliato perché la probabilità di una stima dipende dalla quantità di dati e dal tipo di valutazione che si sta effettuando.</span><span class="sxs-lookup"><span data-stu-id="61ec2-155">There is no recommended threshold value because the probability of any prediction depends on the amount of data and the type of prediction you are making.</span></span> <span data-ttu-id="61ec2-156">È necessario esaminare le stime a livelli di probabilità diversi per determinare una barra di accuratezza appropriata per i dati.</span><span class="sxs-lookup"><span data-stu-id="61ec2-156">You should review some predictions at different probability levels to determine an appropriate accuracy bar for your data.</span></span> <span data-ttu-id="61ec2-157">È importante seguire questa procedura perché il valore impostato per **Soglia** **di destinazione** influisce sull'accuratezza di misurazione del modello.</span><span class="sxs-lookup"><span data-stu-id="61ec2-157">It is important that you do this, because the value that you set for **Target** **Threshold** affects the measured accuracy of the model.</span></span>  
  
 <span data-ttu-id="61ec2-158">Si supponga ad esempio che vengano effettuate tre stime per un particolare stato di destinazione e che le probabilità di ogni stima siano 0,05, 0,15 e 0,8.</span><span class="sxs-lookup"><span data-stu-id="61ec2-158">For example, suppose three predictions are made for a particular target state, and the probabilities of each prediction are 0.05, 0.15, and 0.8.</span></span> <span data-ttu-id="61ec2-159">Se si imposta la soglia su 0,5, solo una stima viene conteggiata come corretta.</span><span class="sxs-lookup"><span data-stu-id="61ec2-159">If you set the threshold to 0.5, only one prediction is counted as being correct.</span></span> <span data-ttu-id="61ec2-160">Se si imposta **Soglia** **di destinazione** su 0,10, due stime vengono conteggiate come corrette.</span><span class="sxs-lookup"><span data-stu-id="61ec2-160">If you set **Target** **Threshold** to 0.10, two predictions are counted as being correct.</span></span>  
  
 <span data-ttu-id="61ec2-161">Quando la **soglia** di **destinazione** è impostata su `null` , ovvero il valore predefinito, la stima più probabile per ogni case viene conteggiata come corretta.</span><span class="sxs-lookup"><span data-stu-id="61ec2-161">When **Target** **Threshold** is set to `null`, which is the default value, the most probable prediction for each case is counted as correct.</span></span> <span data-ttu-id="61ec2-162">Nell'esempio precedente, 0,05, 0,15 e 0,8 sono le probabilità per le stime nei tre diversi case.</span><span class="sxs-lookup"><span data-stu-id="61ec2-162">In the example just cited, 0.05, 0.15, and 0.8 are the probabilities for predictions in three different cases.</span></span> <span data-ttu-id="61ec2-163">Nonostante le probabilità siano molto diverse, ciascuna stima viene conteggiata come corretta, perché ogni case genera una sola stima. Si tratta inoltre delle stime migliori per tali case.</span><span class="sxs-lookup"><span data-stu-id="61ec2-163">Although the probabilities are very different, each prediction would be counted as correct, because each case generates only one prediction and these are the best predictions for these cases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ec2-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61ec2-164">See Also</span></span>  
 <span data-ttu-id="61ec2-165">[Test e convalida &#40;&#41;di data mining](data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="61ec2-165">[Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="61ec2-166">[Convalida incrociata &#40;Analysis Services-&#41;di data mining](data-mining/cross-validation-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="61ec2-166">[Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="61ec2-167">[Misure nel report di convalida incrociata](data-mining/measures-in-the-cross-validation-report.md) </span><span class="sxs-lookup"><span data-stu-id="61ec2-167">[Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md) </span></span>  
 [<span data-ttu-id="61ec2-168">Stored procedure di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="61ec2-168">Data Mining Stored Procedures &#40;Analysis Services - Data Mining&#41;</span></span>](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining)  
  
  
