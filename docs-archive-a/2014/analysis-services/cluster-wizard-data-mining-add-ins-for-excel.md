---
title: Creazione guidata cluster (componenti aggiuntivi Data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clustering [data mining]
ms.assetid: 85b25625-a7ab-4960-9f9c-df22e8ecae37
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90500ae627bcafd1ca5ce17114dac9df9939691d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626392"
---
# <a name="cluster-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="fac3b-102">Procedura guidata Cluster (componenti aggiuntivi Data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="fac3b-102">Cluster Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="fac3b-103">![Procedura guidata Cluster sulla barra multifunzione Data mining](media/dmc-cluster.gif "Procedura guidata Cluster sulla barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="fac3b-103">![Cluster wizard in Data Mining ribbon](media/dmc-cluster.gif "Cluster wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="fac3b-104">La procedura guidata Cluster consente di compilare un modello che rileva le righe che condividono gruppi e caratteristiche simili per ottimizzare la distanza tra i gruppi.</span><span class="sxs-lookup"><span data-stu-id="fac3b-104">The Cluster wizard helps you build a model that detects rows that share similar characteristics and groups them to maximize the distance between groups.</span></span> <span data-ttu-id="fac3b-105">Questa procedura guidata è utile per trovare i modelli in qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="fac3b-105">This wizard is useful for finding patterns in all kinds of data.</span></span>  
  
 <span data-ttu-id="fac3b-106">La procedura guidata Cluster utilizza l'algoritmo Microsoft Clustering e può essere ampiamente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="fac3b-106">The Cluster wizard uses the Microsoft Clustering algorithm and can be extensively customized.</span></span> <span data-ttu-id="fac3b-107">Utilizza i dati esistenti di una tabella di Excel, un intervallo di Excel o una query di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fac3b-107">It works on existing data from an Excel table, an Excel range, or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] query.</span></span> <span data-ttu-id="fac3b-108">Funzionalità simili sono fornite dallo strumento [Rileva categorie](detect-categories-table-analysis-tools-for-excel.md) , disponibile in strumenti di analisi tabelle per Excel.</span><span class="sxs-lookup"><span data-stu-id="fac3b-108">Similar functionality is provided by the [Detect Categories](detect-categories-table-analysis-tools-for-excel.md) tool, provided in the Table Analysis Tools for Excel.</span></span> <span data-ttu-id="fac3b-109">Tuttavia, lo strumento Rileva categorie non può essere personalizzato e deve utilizzare i dati nelle tabelle di Excel.</span><span class="sxs-lookup"><span data-stu-id="fac3b-109">However, the Detect Categories tool cannot be customized and must use data in Excel tables.</span></span>  
  
## <a name="using-the-cluster-wizard"></a><span data-ttu-id="fac3b-110">Utilizzo della procedura guidata Cluster</span><span class="sxs-lookup"><span data-stu-id="fac3b-110">Using the Cluster Wizard</span></span>  
  
1.  <span data-ttu-id="fac3b-111">Sulla barra multifunzione data mining fare clic su **cluster**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fac3b-111">In the Data Mining ribbon, click **Cluster**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="fac3b-112">Nella pagina **selezione dati di origine** selezionare una tabella o un intervallo di Excel.</span><span class="sxs-lookup"><span data-stu-id="fac3b-112">In the **Select Source Data** page, select an Excel table or range.</span></span> <span data-ttu-id="fac3b-113">Oppure specificare un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="fac3b-113">Or specify and external data source.</span></span>  
  
     <span data-ttu-id="fac3b-114">Se si utilizza un'origine dati esterna, è possibile creare viste personalizzate o incollarle nel testo della query personalizzata e salvare il set di dati come origine dati di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fac3b-114">If you use an external data source, you can create custom views or paste in custom query text, and save the data set as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="fac3b-115">Nella pagina **clustering** è possibile personalizzare la modalità di compilazione del modello.</span><span class="sxs-lookup"><span data-stu-id="fac3b-115">On the **Clustering** page, you can customize the way the model is built.</span></span>  
  
    -   <span data-ttu-id="fac3b-116">Per **numero di segmenti**, è possibile indicare alla procedura guidata di creare un numero fisso di categorie o lasciare che venga rilevato automaticamente il numero ottimale di raggruppamenti.</span><span class="sxs-lookup"><span data-stu-id="fac3b-116">For **Number of segments**, you can tell the wizard to create a fixed number of categories, or let it automatically detect the optimum number of groupings.</span></span>  
  
    -   <span data-ttu-id="fac3b-117">Esaminare l'elenco delle colonne nell'elenco **colonne di input** e deselezionare le colonne che non sono utili per la creazione di modelli.</span><span class="sxs-lookup"><span data-stu-id="fac3b-117">Review the list of columns in the **Input columns** list, and deselect any columns that are not useful in creating patterns.</span></span> <span data-ttu-id="fac3b-118">Le colonne che è necessario escludere includono numeri ID, nomi di clienti e così via.</span><span class="sxs-lookup"><span data-stu-id="fac3b-118">Columns you should exclude include ID numbers, customer names, and so on.</span></span>  
  
4.  <span data-ttu-id="fac3b-119">Facoltativamente, fare clic su **parametri** per modificare i parametri dell'algoritmo e personalizzare il comportamento del modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="fac3b-119">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="fac3b-120">Nella pagina **suddivisione dei dati in set di training e di testing** specificare la quantità di dati da mantenere per il test.</span><span class="sxs-lookup"><span data-stu-id="fac3b-120">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="fac3b-121">Il resto viene sempre utilizzato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="fac3b-121">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="fac3b-122">L'impostazione predefinita è il 30% dei dati di testing e il 70% dei dati di training.</span><span class="sxs-lookup"><span data-stu-id="fac3b-122">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="fac3b-123">Nella pagina **fine** specificare un nome descrittivo per il set di dati e il modello, quindi impostare le opzioni seguenti che consentono di controllare la modalità di utilizzo del modello finito:</span><span class="sxs-lookup"><span data-stu-id="fac3b-123">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="fac3b-124">**Esplora modello**.</span><span class="sxs-lookup"><span data-stu-id="fac3b-124">**Browse model**.</span></span> <span data-ttu-id="fac3b-125">Quando questa opzione è selezionata, non appena viene completata l'elaborazione del modello da parte della procedura guidata, viene aperta una finestra **Esplora** che consente di esplorare i risultati.</span><span class="sxs-lookup"><span data-stu-id="fac3b-125">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="fac3b-126">Il contenuto del visualizzatore dipende dal tipo di modello compilato.</span><span class="sxs-lookup"><span data-stu-id="fac3b-126">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="fac3b-127">Per ulteriori informazioni, vedere [esplorazione di un modello di clustering](browsing-a-clustering-model.md).</span><span class="sxs-lookup"><span data-stu-id="fac3b-127">For more information, see [Browsing a Clustering Model](browsing-a-clustering-model.md).</span></span>  
  
    -   <span data-ttu-id="fac3b-128">**Abilitare il drill-through**.</span><span class="sxs-lookup"><span data-stu-id="fac3b-128">**Enable drillthrough**.</span></span> <span data-ttu-id="fac3b-129">Selezionare questa opzione per visualizzare i dati sottostanti dal modello finito.</span><span class="sxs-lookup"><span data-stu-id="fac3b-129">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="fac3b-130">Questa opzione è disponibile solo se si compila un modello Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="fac3b-130">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="fac3b-131">**Usa modello temporaneo**.</span><span class="sxs-lookup"><span data-stu-id="fac3b-131">**Use temporary model**.</span></span> <span data-ttu-id="fac3b-132">Se si seleziona questa opzione, il modello non verrà salvato nel server.</span><span class="sxs-lookup"><span data-stu-id="fac3b-132">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="fac3b-133">I modelli temporanei vengono eliminati quando si chiude Excel.</span><span class="sxs-lookup"><span data-stu-id="fac3b-133">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-clustering-models"></a><span data-ttu-id="fac3b-134">Ulteriori informazioni sui modelli di clustering</span><span class="sxs-lookup"><span data-stu-id="fac3b-134">More about Clustering Models</span></span>  
 <span data-ttu-id="fac3b-135">È possibile modificare l'algoritmo di clustering utilizzato da questa procedura guidata facendo clic su **Avanzate** e utilizzando la finestra di dialogo **parametri algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="fac3b-135">You can change the clustering algorithm used by this wizard by clicking **Advanced** and using the **Algorithm Parameters** dialog box.</span></span>  
  
 <span data-ttu-id="fac3b-136">L'algoritmo Microsoft Clustering fornisce i metodi di clustering seguenti:</span><span class="sxs-lookup"><span data-stu-id="fac3b-136">The Microsoft Clustering algorithm provides these clustering methods:</span></span>  
  
-   <span data-ttu-id="fac3b-137">K-medie, scalabile o non scalabile.</span><span class="sxs-lookup"><span data-stu-id="fac3b-137">K-means -  scalable or non-scaling.</span></span>  
  
-   <span data-ttu-id="fac3b-138">Expectation Maximization (EM), scalabile o non scalabile.</span><span class="sxs-lookup"><span data-stu-id="fac3b-138">Expectation Maximization (EM) - scalable or non-scaling.</span></span>  
  
 <span data-ttu-id="fac3b-139">È anche possibile utilizzare il parametro CLUSTER_SEED per controllare il valore iniziale e assicurarsi che i modelli ripetuti che utilizzano lo stesso set di dati producano gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="fac3b-139">You can also use the CLUSTER_SEED parameter to control the starting value and ensure that repeated models using the same data set have the same results.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="fac3b-140">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fac3b-140">Requirements</span></span>  
 <span data-ttu-id="fac3b-141">Per utilizzare la procedura guidata Cluster, è necessario essere connessi a un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fac3b-141">To use the Cluster wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="fac3b-142">Per ulteriori informazioni, vedere [connettersi ai dati di origine &#40;client di data mining per&#41;Excel ](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="fac3b-142">For more information, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac3b-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fac3b-143">See Also</span></span>  
 <span data-ttu-id="fac3b-144">[Creazione di un modello di data mining](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="fac3b-144">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="fac3b-145">Rilevare le categorie &#40;strumenti di analisi tabelle per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="fac3b-145">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
  
