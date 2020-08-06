---
title: Creazione di un report di convalida incrociata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- validating data mining models
- mining structures [Analysis Services], how-to topics
- cross-validation [data mining]
- statistical standard deviation
ms.assetid: 7b1fec4c-7053-41eb-b030-5179257967a4
author: minewiskan
ms.author: owend
ms.openlocfilehash: ccbafe63b0026cd45a15ea71fd84e223c1b32a9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711159"
---
# <a name="create-a-cross-validation-report"></a><span data-ttu-id="85917-102">Creare un report di convalida incrociata</span><span class="sxs-lookup"><span data-stu-id="85917-102">Create a Cross-Validation Report</span></span>
  <span data-ttu-id="85917-103">In questo argomento viene illustrata la creazione di un report di convalida incrociata utilizzando la scheda Grafico di accuratezza in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="85917-103">This topic walks you through creation of a cross-validation report using the Accuracy Chart tab in Data Mining Designer.</span></span> <span data-ttu-id="85917-104">Per informazioni generali sui report di convalida incrociata e sulle misure statistiche in esso contenute, vedere [Convalida incrociata &#40;Analysis Services - Data mining&#41;](cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="85917-104">For general information about what a cross-validation report looks like, and the statistical measures it includes, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="85917-105">Un report di convalida incrociata è fondamentalmente diverso da un grafico di accuratezza, ad esempio una matrice di classificazione.</span><span class="sxs-lookup"><span data-stu-id="85917-105">A cross-validation report is fundamentally different from an accuracy chart, such as a lift chart or classification matrix.</span></span>  
  
-   <span data-ttu-id="85917-106">La convalida incrociata consente di valutare la distribuzione complessiva dei dati utilizzati in un modello o una struttura, pertanto non si specifica un set di dati di test.</span><span class="sxs-lookup"><span data-stu-id="85917-106">Cross-validation assesses the overall distribution of data that is used in a model or structure; therefore, you do not specify a testing data set.</span></span> <span data-ttu-id="85917-107">La convalida incrociata è sempre basata sull'utilizzo dei soli dati originali utilizzati per il training del modello o della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="85917-107">Cross-validation always uses only the original data that was used to train the model or the mining structure.</span></span>  
  
-   <span data-ttu-id="85917-108">La convalida incrociata può essere eseguita solo rispetto a un singolo risultato stimabile.</span><span class="sxs-lookup"><span data-stu-id="85917-108">Cross-validation can only be performed with respect to a single predictable outcome.</span></span> <span data-ttu-id="85917-109">Se la struttura supporta modelli con attributi stimabili diversi, è necessario creare report separati per ogni output stimabile.</span><span class="sxs-lookup"><span data-stu-id="85917-109">If the structure supports models that have different predictable attributes, you must create separate reports for each predictable output.</span></span>  
  
-   <span data-ttu-id="85917-110">Solo i modelli correlati alla struttura attualmente selezionata sono disponibili per la convalida incrociata.</span><span class="sxs-lookup"><span data-stu-id="85917-110">Only models that are related to the currently selected structure are available for cross-validation.</span></span>  
  
-   <span data-ttu-id="85917-111">Se la struttura attualmente selezionata supporta una combinazione di modelli di clustering e non, quando si fa clic su **Ottieni risultati**, la stored procedure di convalida incrociata caricherà automaticamente i modelli che presentano la stessa colonna stimata e ignorerà i modelli di clustering che non condividono lo stesso attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="85917-111">If the structure that is currently selected supports a combination of clustering and non-clustering models, when you click **Get Results**, the cross-validation stored procedure will automatically load models that have the same predicted column, and ignore clustering models that do not share the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="85917-112">È possibile creare un report di convalida incrociata su un modello di clustering che non dispone di un attributo stimabile solo se la struttura di data mining non supporta altri attributi stimabili.</span><span class="sxs-lookup"><span data-stu-id="85917-112">You can create a cross-validation report on a clustering model that does not have a predictable attribute only if the mining structure does not support any other predictable attributes.</span></span>  
  
### <a name="select-a-mining-structure"></a><span data-ttu-id="85917-113">Selezionare una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="85917-113">Select a mining structure</span></span>  
  
1.  <span data-ttu-id="85917-114">Aprire Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85917-114">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="85917-115">In Esplora soluzioni aprire il database che contiene la struttura o il modello per cui si desidera creare un report.</span><span class="sxs-lookup"><span data-stu-id="85917-115">In Solution Explorer, open the database that contains the structure or model for which you want to create a report.</span></span>  
  
3.  <span data-ttu-id="85917-116">Fare doppio clic sulla struttura di data mining per aprire la struttura e i modelli correlati in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="85917-116">Double-click the mining structure to open the structure and its related models in Data Mining Designer.</span></span>  
  
4.  <span data-ttu-id="85917-117">Fare clic sulla scheda **Grafico accuratezza modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="85917-117">Click the **Mining Accuracy Chart** tab.</span></span>  
  
5.  <span data-ttu-id="85917-118">Fare clic sulla scheda **Convalida incrociata** .</span><span class="sxs-lookup"><span data-stu-id="85917-118">Click the **Cross Validation** tab.</span></span>  
  
### <a name="set-cross-validation-options"></a><span data-ttu-id="85917-119">Impostare le opzioni di convalida incrociata</span><span class="sxs-lookup"><span data-stu-id="85917-119">Set cross-validation options</span></span>  
  
1.  <span data-ttu-id="85917-120">Nella scheda **Convalida incrociata** per **FoldCount**fare clic sulla freccia giù per selezionare un numero compreso tra 1 e 10.</span><span class="sxs-lookup"><span data-stu-id="85917-120">On the **Cross Validation** tab, for **Fold Count**, click the down arrow to select a number between 1 and 10.</span></span> <span data-ttu-id="85917-121">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="85917-121">The default value is 10.</span></span>  
  
     <span data-ttu-id="85917-122">**FoldCount** rappresenta il numero di partizioni che verranno create all'interno del set di dati originali.</span><span class="sxs-lookup"><span data-stu-id="85917-122">The **Fold Count** represents the number of partitions that will be created within the original data set.</span></span> <span data-ttu-id="85917-123">Se si imposta FoldCount su 1, il set di training verrà utilizzato senza partizionamento.</span><span class="sxs-lookup"><span data-stu-id="85917-123">If you set Fold Count to 1, the training set will be used without partitioning.</span></span>  
  
2.  <span data-ttu-id="85917-124">Per **TargetAttribute**fare clic sulla freccia verso il basso e selezionare una colonna nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="85917-124">For **Target Attribute**, click the down arrow, and select a column from the list.</span></span> <span data-ttu-id="85917-125">Se si tratta di un modello di clustering, selezionare **#Cluster** per indicare che il modello non dispone di un modello stimabile.</span><span class="sxs-lookup"><span data-stu-id="85917-125">If the model is a clustering model, select **#Cluster** to indicate that the model does not have a predictable attribute.</span></span> <span data-ttu-id="85917-126">Si noti che il valore **#Cluster**è disponibile solo quando la struttura di data mining non supporta altri tipi di attributi stimabili.</span><span class="sxs-lookup"><span data-stu-id="85917-126">Note that the value, **#Cluster**, is available only when the mining structure does not support other types of predictable attributes.</span></span>  
  
     <span data-ttu-id="85917-127">È possibile selezionare solo un attributo stimabile per report.</span><span class="sxs-lookup"><span data-stu-id="85917-127">You can select only one predictable attribute per report.</span></span> <span data-ttu-id="85917-128">Per impostazione predefinita, tutti i modelli correlati che includono lo stesso attributo stimabile vengono inclusi nel report.</span><span class="sxs-lookup"><span data-stu-id="85917-128">By default, all related models that have the same predictable attribute are included in the report.</span></span>  
  
3.  <span data-ttu-id="85917-129">Per **MaxCases**digitare un numero sufficientemente elevato per fornire un esempio rappresentativo di dati quando questi sono suddivisi fra il numero specificato di riduzioni.</span><span class="sxs-lookup"><span data-stu-id="85917-129">For **Max Cases**, type a number that is large enough to provide a representative sample of data when the data is split among the specified number of folds.</span></span> <span data-ttu-id="85917-130">Se il numero è maggiore del conteggio dei case nel set di training del modello, verranno utilizzati tutti i case.</span><span class="sxs-lookup"><span data-stu-id="85917-130">If the number is greater than the count of cases in the model training set, all cases will be used.</span></span>  
  
     <span data-ttu-id="85917-131">Se il set di dati di training è di dimensioni molto elevate, l'impostazione del valore per **MaxCases** limita il numero totale di case elaborati e consente di completare il report più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="85917-131">If the training data set is very large, setting the value for **Max Cases** limits the total number of cases processed, and lets the report finish faster.</span></span> <span data-ttu-id="85917-132">È tuttavia consigliabile non impostare **MaxCases** su un valore troppo basso. In questo caso, il numero di dati per la convalida incrociata potrebbe risultare insufficiente.</span><span class="sxs-lookup"><span data-stu-id="85917-132">However, you should not set **Max Cases** too low or there may be insufficient data for cross-validation.</span></span>  
  
4.  <span data-ttu-id="85917-133">Per **TargetState**è possibile digitare il valore dell'attributo stimabile di cui eseguire la modellazione.</span><span class="sxs-lookup"><span data-stu-id="85917-133">Optionally, for **Target State**, type the value of the predictable attribute that you want to model.</span></span> <span data-ttu-id="85917-134">Se, ad esempio, per la colonna [Bike Buyer] sono possibili due valori, ovvero 1 (Sì) e 2 (No), è possibile immettere il valore 1 per valutare l'accuratezza del modello per il risultato desiderato.</span><span class="sxs-lookup"><span data-stu-id="85917-134">For example, if the column [Bike Buyer] has two possible values, 1 (Yes) and 2 (No), you can enter the value 1 to assess the accuracy of the model for just the desired outcome.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85917-135"> Se non si immette alcun valore, l'opzione **TargetThreshold** non è disponibile e il modello viene valutato per tutti i valori possibili dell'attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="85917-135">If you do not enter a value, the **Target Threshold** option is not available, and the model is assessed for all possible values of the predictable attribute.</span></span>  
  
5.  <span data-ttu-id="85917-136">Per **TargetThreshold**è possibile digitare un numero decimale compreso tra 0 e 1 per specificare la probabilità minima da applicare a una stima affinché questa venga ritenuta accurata.</span><span class="sxs-lookup"><span data-stu-id="85917-136">Optionally, for **Target Threshold**, type a decimal number between 0 and 1 to specify the minimum probability that a prediction must have to be counted as accurate.</span></span>  
  
     <span data-ttu-id="85917-137">Per suggerimenti aggiuntivi sull'impostazione di soglie di probabilità, vedere [Misure nel report di convalida incrociata](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="85917-137">For additional tips about how to set probability thresholds, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
6.  <span data-ttu-id="85917-138">Fare clic su **Ottieni risultati**.</span><span class="sxs-lookup"><span data-stu-id="85917-138">Click **Get Results**.</span></span>  
  
### <a name="print-the-cross-validation-report"></a><span data-ttu-id="85917-139">Stampare il report di convalida incrociata</span><span class="sxs-lookup"><span data-stu-id="85917-139">Print the cross-validation report</span></span>  
  
1.  <span data-ttu-id="85917-140">Fare clic con il pulsante destro del mouse sul report completato nella scheda **Convalida incrociata** .</span><span class="sxs-lookup"><span data-stu-id="85917-140">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="85917-141">Scegliere **Stampa** o **Anteprima di stampa** dal menu di scelta rapida per controllare il report prima di stamparlo.</span><span class="sxs-lookup"><span data-stu-id="85917-141">In the shortcut menu, select **Print** or **Print Preview** to review the report first.</span></span>  
  
### <a name="create-a-copy-of-the-report-in-microsoft-excel"></a><span data-ttu-id="85917-142">Creare una copia del report in Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="85917-142">Create a copy of the report in Microsoft Excel</span></span>  
  
1.  <span data-ttu-id="85917-143">Fare clic con il pulsante destro del mouse sul report completato nella scheda **Convalida incrociata** .</span><span class="sxs-lookup"><span data-stu-id="85917-143">Right-click the completed report on the **Cross Validation** tab.</span></span>  
  
2.  <span data-ttu-id="85917-144">Dal menu di scelta rapida scegliere **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="85917-144">In the shortcut menu, select **Select All**.</span></span>  
  
3.  <span data-ttu-id="85917-145">Fare clic con il pulsante destro del mouse sul testo selezionato, quindi scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="85917-145">Right-click the selected text, and select **Copy**.</span></span>  
  
4.  <span data-ttu-id="85917-146">Incollare la selezione in una cartella di lavoro di Excel aperta.</span><span class="sxs-lookup"><span data-stu-id="85917-146">Paste the selection into an open Excel workbook.</span></span> <span data-ttu-id="85917-147">Se si utilizza l'opzione **Incolla** , il report viene incollato in Excel in formato HTML, mantenendo la formattazione di righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="85917-147">If you use the **Paste** option, the report is pasted into Excel as HTML, which preserves row and column formatting.</span></span> <span data-ttu-id="85917-148">Se si usano le opzioni **Incolla speciale** per testo o testo Unicode, il report viene incollato in formato delimitato da righe.</span><span class="sxs-lookup"><span data-stu-id="85917-148">If you paste the report by using the **Paste Special** options for text or Unicode text, the report is pasted in row-delimited format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85917-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85917-149">See Also</span></span>  
 [<span data-ttu-id="85917-150">Misure nel report di convalida incrociata</span><span class="sxs-lookup"><span data-stu-id="85917-150">Measures in the Cross-Validation Report</span></span>](measures-in-the-cross-validation-report.md)  
  
  
