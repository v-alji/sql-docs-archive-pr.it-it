---
title: Procedura guidata classificazione (componenti aggiuntivi Data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- classification [data mining]
ms.assetid: 409c5076-c4c3-4f09-8f30-d3297df45f13
author: minewiskan
ms.author: owend
ms.openlocfilehash: b82fc98df10ae2e6754a378dacea108f9f3379ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625776"
---
# <a name="classify-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="4dd8d-102">Procedura guidata Classificazione (componenti aggiuntivi Data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="4dd8d-102">Classify Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="4dd8d-103">![Procedura guidata Classificazione sulla barra multifunzione Data mining](media/dmc-classify.gif "Procedura guidata Classificazione sulla barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="4dd8d-103">![Classify wizard in Data Mining ribbon](media/dmc-classify.gif "Classify wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="4dd8d-104">La procedura guidata **Classificazione** consente di generare un modello di classificazione in base a dati esistenti di una tabella di Excel, un intervallo di Excel o un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-104">The **Classify** wizard helps you build a classification model based on existing data in an Excel table, an Excel range, or an external data source.</span></span>  
  
 <span data-ttu-id="4dd8d-105">Un modello di classificazione consente di estrarre modelli dai dati che indicano somiglianze e di eseguire stime basate su raggruppamenti di valori.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-105">A classification model extracts patterns in your data that indicate similarities and helps you make predictions based on groupings of values.</span></span> <span data-ttu-id="4dd8d-106">È possibile utilizzare un modello di classificazione, ad esempio, per stimare i rischi in base ai modelli di ricavo o costi.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-106">For example, a classification model might be used to predict risk based on income or spending patterns.</span></span>  
  
## <a name="using-the-classify-wizard"></a><span data-ttu-id="4dd8d-107">Utilizzo della procedura guidata Classificazione</span><span class="sxs-lookup"><span data-stu-id="4dd8d-107">Using the Classify Wizard</span></span>  
  
1.  <span data-ttu-id="4dd8d-108">Sulla barra multifunzione **data mining** fare clic su **classificazione**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-108">In the **Data Mining** ribbon, click **Classify**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="4dd8d-109">Nella pagina **selezione dati di origine** scegliere i dati da analizzare.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-109">In the **Select Source Data** page, choose the data to analyze.</span></span>  
  
     <span data-ttu-id="4dd8d-110">Questa procedura guidata supporta più tipi di dati: tabelle di Excel, intervalli di Excel e origini dati esterne.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-110">This wizard supports multiple kinds of data: Excel tables, Excel ranges, and external data sources.</span></span> <span data-ttu-id="4dd8d-111">Con i dati esterni, è possibile aggiungerli in Excel oppure scegliere un set di tabelle o viste in un'origine dati di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-111">With external data, you can either add it into Excel, or choose a set of tables or views in an Analysis Services data source.</span></span> <span data-ttu-id="4dd8d-112">È inoltre possibile aggiungere tabelle e modificare le colonne per creare origini dati ad hoc.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-112">You can also add tables and change columns to create ad hoc data sources.</span></span>  
  
3.  <span data-ttu-id="4dd8d-113">Nella pagina **classificazione** scegliere la colonna che si desidera classificare.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-113">On the **Classification** page, choose the column that you want to classify.</span></span>  
  
     <span data-ttu-id="4dd8d-114">Esaminare le colonne dell'elenco, le **colonne di input**e deselezionare tutte le colonne con valori univoci e pertanto non sono utili per la creazione di modelli, ad esempio numeri ID, nomi di clienti e così via.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-114">Review the columns in the list, **Input columns**, and deselect any columns that have unique values and thus aren't useful for creating patterns, such as ID numbers, customer names, and so on.</span></span> <span data-ttu-id="4dd8d-115">È inoltre necessario rimuovere le colonne che essenzialmente duplicano la colonna classificabile.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-115">You should also remove columns that essentially duplicate the classifiable column.</span></span>  
  
     <span data-ttu-id="4dd8d-116">Ad esempio, se si esegue la classificazione tramite la stima della categoria di un prodotto, è necessario escludere il campo della sottocategoria se esiste una regola business nota. In caso contrario, l'attendibilità di tale regola potrebbe impedire di individuare altre correlazioni.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-116">For example, if you are classifying predicting the category of a product, you should exclude the subcategory field if there is a known business rule, or else the strength of that rule might prevent you from discovering other correlations.</span></span>  
  
4.  <span data-ttu-id="4dd8d-117">Facoltativamente, fare clic su **parametri** per modificare i parametri dell'algoritmo e personalizzare il comportamento del modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-117">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="4dd8d-118">Nella pagina **suddivisione dei dati in set di training e di testing** specificare la quantità di dati da mantenere per il test.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-118">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="4dd8d-119">Il resto viene sempre utilizzato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-119">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="4dd8d-120">L'impostazione predefinita è il 30% dei dati di testing e il 70% dei dati di training.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-120">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="4dd8d-121">Nella pagina **fine** specificare un nome descrittivo per il set di dati e il modello, quindi impostare le opzioni seguenti che consentono di controllare la modalità di utilizzo del modello finito:</span><span class="sxs-lookup"><span data-stu-id="4dd8d-121">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="4dd8d-122">**Esplora modello**.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-122">**Browse model**.</span></span> <span data-ttu-id="4dd8d-123">Quando questa opzione è selezionata, non appena viene completata l'elaborazione del modello da parte della procedura guidata, viene aperta una finestra **Esplora** che consente di esplorare i risultati.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-123">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="4dd8d-124">Il contenuto del visualizzatore dipende dal tipo di modello compilato.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-124">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="4dd8d-125">Per ulteriori informazioni, vedere [esplorazione di un modello Decision Trees](browsing-a-decision-trees-model.md) ed [esplorazione di un modello di rete neurale](browsing-a-neural-network-model.md).</span><span class="sxs-lookup"><span data-stu-id="4dd8d-125">For more information, see [Browsing a Decision Trees Model](browsing-a-decision-trees-model.md) and [Browsing a Neural Network Model](browsing-a-neural-network-model.md).</span></span>  
  
    -   <span data-ttu-id="4dd8d-126">**Abilitare il drill-through**.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-126">**Enable drillthrough**.</span></span> <span data-ttu-id="4dd8d-127">Selezionare questa opzione per visualizzare i dati sottostanti dal modello finito.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-127">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="4dd8d-128">Questa opzione è disponibile solo se si compila un modello Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-128">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="4dd8d-129">**Usa modello temporaneo**.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-129">**Use temporary model**.</span></span> <span data-ttu-id="4dd8d-130">Se si seleziona questa opzione, il modello non verrà salvato nel server.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-130">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="4dd8d-131">I modelli temporanei vengono eliminati quando si chiude Excel.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-131">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-classification-models"></a><span data-ttu-id="4dd8d-132">Ulteriori informazioni sui modelli di classificazione</span><span class="sxs-lookup"><span data-stu-id="4dd8d-132">More About Classification Models</span></span>  
 <span data-ttu-id="4dd8d-133">Nella finestra di dialogo **parametri algoritmo** è inoltre possibile scegliere il metodo di classificazione tra gli algoritmi disponibili in Analysis Services:</span><span class="sxs-lookup"><span data-stu-id="4dd8d-133">In the **Algorithm Parameters** dialog box, you can also choose the classification method from among these algorithms provided in Analysis Services:</span></span>  
  
-   <span data-ttu-id="4dd8d-134">Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="4dd8d-134">Microsoft Decision Tree</span></span>  
  
-   <span data-ttu-id="4dd8d-135">Microsoft Logistic Regression</span><span class="sxs-lookup"><span data-stu-id="4dd8d-135">Microsoft Logistic Regression</span></span>  
  
-   <span data-ttu-id="4dd8d-136">Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="4dd8d-136">Microsoft Naïve Bayes</span></span>  
  
-   <span data-ttu-id="4dd8d-137">Microsoft Neural Network</span><span class="sxs-lookup"><span data-stu-id="4dd8d-137">Microsoft Neural Network</span></span>  
  
 <span data-ttu-id="4dd8d-138">Sebbene gli algoritmi possano restituire risultati simili, analizzano i dati in modo diverso, pertanto è consigliabile provare diversi algoritmi e confrontare i risultati.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-138">Although the algorithms might yield similar results, they analyze the data differently, so we recommend trying several algorithms and comparing the results.</span></span> <span data-ttu-id="4dd8d-139">Il metodo predefinito è Microsoft Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-139">The default method is Microsoft Decision Trees.</span></span>  
  
 <span data-ttu-id="4dd8d-140">Nell'elenco **Parameters** è possibile modificare le opzioni avanzate, che dipendono dal tipo di algoritmo scelto.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-140">In the **Parameters** list, you can change advanced options, which depend on the type of algorithm you choose.</span></span> <span data-ttu-id="4dd8d-141">I parametri per ogni algoritmo vengono descritti in modo più dettagliato nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-141">The parameters for each algorithm are described in more detail in SQL Server Books Online.</span></span>  
  
 [<span data-ttu-id="4dd8d-142">Guida di riferimento tecnico per l'algoritmo Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="4dd8d-142">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="4dd8d-143">Riferimento tecnico per l'algoritmo Microsoft Logistic Regression</span><span class="sxs-lookup"><span data-stu-id="4dd8d-143">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="4dd8d-144">Riferimento tecnico per l'algoritmo Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="4dd8d-144">Microsoft Naive Bayes Algorithm Technical Reference</span></span>](data-mining/microsoft-naive-bayes-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="4dd8d-145">Microsoft Neural Network Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="4dd8d-145">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="4dd8d-146">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4dd8d-146">Requirements</span></span>  
 <span data-ttu-id="4dd8d-147">Per utilizzare la procedura guidata **classificazione** , è necessario essere connessi a un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database di.</span><span class="sxs-lookup"><span data-stu-id="4dd8d-147">To use the **Classify** wizard, you must be connected to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="4dd8d-148">Per informazioni su come creare una connessione, vedere [connettersi ai dati di origine &#40;client di data mining per&#41;Excel ](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="4dd8d-148">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd8d-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dd8d-149">See Also</span></span>  
 [<span data-ttu-id="4dd8d-150">Creazione di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="4dd8d-150">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
