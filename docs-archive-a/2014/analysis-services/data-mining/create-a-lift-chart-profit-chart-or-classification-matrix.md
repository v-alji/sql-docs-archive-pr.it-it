---
title: Creare un grafico di accuratezza, un grafico dei profitti o una matrice di classificazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], mining structures
ms.assetid: aa3d052f-58a9-4417-8e7a-5e6feb562af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 932138b37b36269bed86df42786bd5d684f75ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712652"
---
# <a name="create-a-lift-chart-profit-chart-or-classification-matrix"></a><span data-ttu-id="dc4b5-102">Creare un grafico di accuratezza, un grafico dei profitti o una matrice di classificazione</span><span class="sxs-lookup"><span data-stu-id="dc4b5-102">Create a Lift Chart, Profit Chart, or Classification Matrix</span></span>
  <span data-ttu-id="dc4b5-103">È possibile creare un grafico di accuratezza per un modello di data mining di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in cinque passaggi fondamentali:</span><span class="sxs-lookup"><span data-stu-id="dc4b5-103">You can create an accuracy chart for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data mining model in five basic steps:</span></span>  
  
-   <span data-ttu-id="dc4b5-104">Selezionare la struttura di data mining che contiene i modelli di data mining da confrontare.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-104">Select the mining structure that contains the mining models that you want to compare.</span></span>  
  
-   <span data-ttu-id="dc4b5-105">Selezionare i modelli di data mining da aggiungere al grafico.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-105">Select the mining models to add to the chart.</span></span>  
  
-   <span data-ttu-id="dc4b5-106">Specificare un'origine di dati di testing da utilizzare nella generazione del grafico.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-106">Specify a source of testing data to use in generating the chart.</span></span>  
  
-   <span data-ttu-id="dc4b5-107">Scegliere il tipo di grafico.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-107">Choose the chart type.</span></span>  
  
-   <span data-ttu-id="dc4b5-108">Configurare le opzioni del grafico.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-108">Configure the chart options.</span></span>  
  
 <span data-ttu-id="dc4b5-109">Questi passaggi di base sono identici per il grafico di accuratezza, il grafico di profitti e la matrice di classificazione.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-109">These basic steps are the same for the lift chart, profit chart, and classification matrix.</span></span> <span data-ttu-id="dc4b5-110">Nelle procedure seguenti vengono descritti i passaggi per configurare le opzioni di base per questi tipi di grafico.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-110">The following procedures outline the steps to configure the basic chart options for these chart types.</span></span> <span data-ttu-id="dc4b5-111">Per altre informazioni su come creare un report di convalida incrociata, vedere [Misure nel report di convalida incrociata](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="dc4b5-111">For information about how to create a cross-validation report, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
### <a name="open-the-mining-structure-in-the-accuracy-chart-designer"></a><span data-ttu-id="dc4b5-112">Aprire la struttura di data mining nella Finestra di progettazione Grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="dc4b5-112">Open the mining structure in the Accuracy Chart Designer</span></span>  
  
1.  <span data-ttu-id="dc4b5-113">Aprire Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc4b5-113">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="dc4b5-114">In Esplora soluzioni fare doppio clic sulla struttura che contiene il modello o i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-114">In Solution Explorer, double-click the structure that contains the mining model or models.</span></span>  
  
3.  <span data-ttu-id="dc4b5-115">Fare clic sulla scheda **Grafico accuratezza modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="dc4b5-115">Click the **Mining Accuracy Chart** tab.</span></span>  
  
### <a name="select-mining-models-for-inclusion-in-the-chart"></a><span data-ttu-id="dc4b5-116">Selezionare i modelli di data mining da includere nel grafico</span><span class="sxs-lookup"><span data-stu-id="dc4b5-116">Select mining models for inclusion in the chart</span></span>  
  
1.  <span data-ttu-id="dc4b5-117">Nella scheda **Grafico accuratezza modello di data mining** di Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare clic sulla scheda **Selezione input** .</span><span class="sxs-lookup"><span data-stu-id="dc4b5-117">On the **Mining Accuracy Chart** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Input Selection** tab.</span></span>  
  
     <span data-ttu-id="dc4b5-118">Nell'elenco verranno visualizzati tutti i modelli presenti nella struttura corrente con lo stesso attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-118">The list displays all models in the current structure that have the same predictable attribute.</span></span>  
  
2.  <span data-ttu-id="dc4b5-119">Selezionare la casella **Mostra** per ogni modello da includere nel grafico.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-119">Select the **Show box** for each model that you want to include in the chart.</span></span>  
  
3.  <span data-ttu-id="dc4b5-120">Fare clic sulla casella di testo **Nome colonna stimabile** e selezionare il nome di una colonna stimabile nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-120">Click the **Predictable Column Name** text box, and select the name of a predictable column from the list.</span></span> <span data-ttu-id="dc4b5-121">Tutti i modelli inclusi in un grafico devono avere la stessa colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-121">All models that you put in one chart must have the same predictable column.</span></span>  
  
4.  <span data-ttu-id="dc4b5-122">Se si confrontano due modelli e le colonne stimabili contengono valori o tipi di dati diversi, deselezionare la casella **Sincronizza colonne e valori di stima** per forzare un confronto.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-122">If you compare two models and the predictable columns have different values or different data types, clear the **Synchonize prediction columns and values** box to force a comparison.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc4b5-123">Se la casella **Sincronizza colonne e valori di stima** è selezionata, verranno analizzati i dati nelle colonne stimabili del modello e i dati di test e verrà effettuato il tentativo di trovare la migliore corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-123">If the **Synchonize prediction columns and values** box is selected, Analysis Services analyzes the data in the predictable columns of the model and the test data, and attempts to find the best match.</span></span> <span data-ttu-id="dc4b5-124">Pertanto, non deselezionare la casella a meno che non sia assolutamente necessario per forzare un confronto delle colonne.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-124">Therefore, do not clear the box unless absolutely necessary to force a comparison of the columns.</span></span>  
  
5.  <span data-ttu-id="dc4b5-125">Fare clic sulla casella di testo **Valore stima** e selezionare un valore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-125">Click the **Predict Value** text box, and select a value from the list.</span></span> <span data-ttu-id="dc4b5-126">Se la colonna stimabile è un tipo di dati continuo, è necessario digitare un valore nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-126">If the predictable column is a continuous data type, you must type a value in the text box.</span></span>  
  
     <span data-ttu-id="dc4b5-127">Per altre informazioni, vedere [Scegliere la colonna da usare per il test di un modello di data mining](choose-the-column-to-use-for-testing-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="dc4b5-127">For more information, see [Choose the Column to Use for Testing a Mining Model](choose-the-column-to-use-for-testing-a-mining-model.md).</span></span>  
  
### <a name="select-testing-data"></a><span data-ttu-id="dc4b5-128">Selezionare i dati di test</span><span class="sxs-lookup"><span data-stu-id="dc4b5-128">Select testing data</span></span>  
  
1.  <span data-ttu-id="dc4b5-129">Nella scheda **Selezione input** della scheda **Grafico accuratezza modello di data mining** specificare l'origine dei dati che verranno usati per generare il grafico selezionando una delle opzioni del gruppo **Seleziona set di dati da utilizzare per il grafico di accuratezza**.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-129">On the **Input Selection** tab of the **Mining Accuracy Chart** tab, specify the source of the data that you will use to generate the chart by selecting one of the options in the group, **Select data set to be used for accuracy chart**.</span></span>  
  
    -   <span data-ttu-id="dc4b5-130">Selezionare l'opzione **Usa test case del modello di data mining**se si intende usare il subset di case definiti tramite l'intersezione dei test case della struttura di data mining ed eventuali filtri applicati durante la creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-130">Select the option, **Use Mining Model test cases**, if you want to use the subset of cases that is defined by the intersection of the mining structure test cases and any filters that may have been applied during model creation.</span></span>  
  
    -   <span data-ttu-id="dc4b5-131">Selezionare l'opzione **Usa test case della struttura di data mining**per usare il set completo di test case definiti come parte del set di dati di controllo delle strutture di data mining.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-131">Select the option, **Use mining structure test cases**, to use the full set of testing cases that were defined as part of the mining structures holdout data set.</span></span>  
  
    -   <span data-ttu-id="dc4b5-132">Selezionare l'opzione **Specifica un set di dati diverso**se si vuole usare dati esterni.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-132">Select the option, **Specify a different data set**, if you want to use external data.</span></span>  <span data-ttu-id="dc4b5-133">Il set di dati deve essere disponibile come vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-133">The data set must be available as a data source view.</span></span>   <span data-ttu-id="dc4b5-134">Fare clic sul pulsante Sfoglia (**..**.) per scegliere le tabelle di dati da utilizzare per il grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-134">Click the browse (**...**) button to choose the data tables to use for the accuracy chart.</span></span> <span data-ttu-id="dc4b5-135">Per altre informazioni, vedere [Scegliere ed eseguire il mapping dei dati di test del modello](choose-and-map-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="dc4b5-135">For more information, see [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span></span>  
  
         <span data-ttu-id="dc4b5-136">Se si utilizza un set di dati esterno, è possibile scegliere di filtrare il set di dati di input.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-136">If you are using an external data set, you can optionally filter the input data set.</span></span> <span data-ttu-id="dc4b5-137">Per altre informazioni, vedere [Applicare filtri ai dati di test del modello](apply-filters-to-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="dc4b5-137">For more information, see [Apply Filters to Model Testing Data](apply-filters-to-model-testing-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc4b5-138">Non è possibile creare un filtro sui test case del modello o sui test case della struttura di data mining nella scheda **Selezione input** . Per creare un filtro sul modello di data mining, modificare la proprietà Filter del modello.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-138">You cannot create a filter on the model test cases or the mining structure test cases on the **Input Selection** tab. To create a filter on the mining model, modify the Filter property of the model.</span></span> <span data-ttu-id="dc4b5-139">Per altre informazioni, vedere [Applicare un filtro a un modello di data mining](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="dc4b5-139">For more information, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
### <a name="configure-chart-settings-and-generate-the-chart"></a><span data-ttu-id="dc4b5-140">Configurare le impostazioni e generare il grafico</span><span class="sxs-lookup"><span data-stu-id="dc4b5-140">Configure chart settings and generate the chart</span></span>  
  
1.  <span data-ttu-id="dc4b5-141">Nella scheda **Grafico accuratezza modello di data mining** fare clic sulla scheda relativa al grafico da creare.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-141">In the **Mining Accuracy Chart** tab, click the tab for the chart you want to create.</span></span>  
  
2.  <span data-ttu-id="dc4b5-142">Per un **grafico di accuratezza**, fare clic sulla scheda **grafico di accuratezza** . Il grafico viene generato automaticamente in base al modello, agli attributi stimabili e ai dati di input appena selezionati.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-142">For a **lift chart**, click the **Lift Chart** tab. The chart is automatically generated based on the model, predictable attributes, and input data that you just selected.</span></span>  
  
3.  <span data-ttu-id="dc4b5-143">Per una **matrice di classificazione**, fare clic sulla scheda **matrice di classificazione** . Non sono necessarie altre impostazioni. il grafico viene generato automaticamente in base ai dati di input e al modello selezionati.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-143">For a **classification matrix**, click the **Classification Matrix** tab. No further settings are needed; the chart is automatically generated based on the input data and model that you selected.</span></span>  
  
4.  <span data-ttu-id="dc4b5-144">Per un **grafico dei profitti**, fare prima clic sulla scheda **grafico di accuratezza** . Quindi selezionare **grafico profitti**nell'elenco a discesa **tipo di grafico** .</span><span class="sxs-lookup"><span data-stu-id="dc4b5-144">For a **profit chart**, first click the **Lift Chart** tab. Then, from the **Chart type** drop-down list, select **Profit chart**.</span></span>  
  
     <span data-ttu-id="dc4b5-145">Immettere le impostazioni seguenti nella finestra di dialogo **Impostazioni grafico profitti** .</span><span class="sxs-lookup"><span data-stu-id="dc4b5-145">Enter the following settings in the **Profit Chart Settings** dialog box.</span></span>  
  
     <span data-ttu-id="dc4b5-146">**Popolazione**</span><span class="sxs-lookup"><span data-stu-id="dc4b5-146">**Population**</span></span>  
     <span data-ttu-id="dc4b5-147">Numero di case del set di dati che si desidera utilizzare per la creazione del grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-147">The number of cases from the data set that you want to use when creating the lift chart.</span></span>  
  
     <span data-ttu-id="dc4b5-148">Il modello sceglie sempre i case in ordine di probabilità decrescente. Ciò significa che, se si desidera valutare i potenziali clienti e si sceglie un numero che rappresenta solo metà dei record nel database dei clienti, il modello misurerà l'accuratezza nel subset di case più adatti al modello.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-148">The model always chooses the cases in order of decreasing probability; that is, if you are assessing potential customers and you choose a number that represents only half the records in your customer database, the model will measure accuracy on the subset of cases that best fit your model.</span></span>  
  
     <span data-ttu-id="dc4b5-149">Ciò è dovuto al fatto che quando il modello viene utilizzato per generare un mailing o creare una campagna, verrà utilizzata la probabilità di stima associata a ogni case per individuare solo i clienti la cui risposta sarà positiva in base alla probabilità più alta.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-149">This is because when you use the model to generate a mailing or create a campaign, you will use the prediction probability associated with each case to target only the customers who have the highest probability of making a positive response.</span></span>  
  
     <span data-ttu-id="dc4b5-150">**Costo fisso**</span><span class="sxs-lookup"><span data-stu-id="dc4b5-150">**Fixed Cost**</span></span>  
     <span data-ttu-id="dc4b5-151">Costi fissi associati al problema aziendale.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-151">The fixed cost that is associated with the business problem.</span></span>  
  
     <span data-ttu-id="dc4b5-152">Nel caso di una soluzione di mailing diretto, i costi fissi potrebbero essere correlati alla configurazione di una stampante per la copertura dei costi iniziali necessari per la preparazione del mailing promozionale.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-152">If this were for a targeted mailing solution, the fixed cost might represent a printer setup fee that covers the initial cost of preparing the promotional mailing.</span></span>  
  
     <span data-ttu-id="dc4b5-153">Tali costi si applicano una volta all'intera popolazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-153">This cost applies one time to the entire target population.</span></span>  
  
     <span data-ttu-id="dc4b5-154">**Costo individuale**</span><span class="sxs-lookup"><span data-stu-id="dc4b5-154">**Individual Cost**</span></span>  
     <span data-ttu-id="dc4b5-155">Costi extra in aggiunta ai costi fissi che possono essere associati al contatto di ogni cliente,</span><span class="sxs-lookup"><span data-stu-id="dc4b5-155">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="dc4b5-156">È possibile, ad esempio, immettere i costi di affrancatura per un mailing promozionale o per l'esecuzione di telefonate.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-156">For example, you might enter the postage cost for a promotional mailing or the cost of making telephone calls.</span></span>  
  
     <span data-ttu-id="dc4b5-157">Tali costi devono essere identici per l'intera popolazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-157">This cost must be the same for the entire target population.</span></span> <span data-ttu-id="dc4b5-158">Ogni valore viene moltiplicato per il numero di case di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-158">Each value is multiplied by the number of cases that are targeted.</span></span>  
  
     <span data-ttu-id="dc4b5-159">**Ricavi per singolo utente**</span><span class="sxs-lookup"><span data-stu-id="dc4b5-159">**Revenue Per Individual**</span></span>  
     <span data-ttu-id="dc4b5-160">Importo dei ricavi associati a ogni vendita effettuata.</span><span class="sxs-lookup"><span data-stu-id="dc4b5-160">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc4b5-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc4b5-161">See Also</span></span>  
 <span data-ttu-id="dc4b5-162">[Grafico di accuratezza &#40;Analysis Services-&#41;di data mining](lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="dc4b5-162">[Lift Chart &#40;Analysis Services - Data Mining&#41;](lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="dc4b5-163">Matrice di classificazione &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="dc4b5-163">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](classification-matrix-analysis-services-data-mining.md)  
  
  
