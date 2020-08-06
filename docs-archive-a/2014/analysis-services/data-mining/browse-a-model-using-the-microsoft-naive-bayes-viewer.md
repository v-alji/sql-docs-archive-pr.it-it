---
title: Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discrimination [Analysis Services]
- naive bayes model [Analysis Services]
- Bayesian classifiers
- mining model content, viewing
- predictive modeling [Analysis Services]
- Naive Bayes Viewer [Analysis Services]
- data mining [Analysis Services], predictive modeling
- Microsoft Naive Bayes Viewer
- histograms [Analysis Services]
- mining models [Analysis Services], predictive modeling
- dependencies [Analysis Services]
ms.assetid: 19743095-63c1-4486-8c1d-2efc143243be
author: minewiskan
ms.author: owend
ms.openlocfilehash: 03469e73d82a389426f91d8757630f50fe78fc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638195"
---
# <a name="browse-a-model-using-the-microsoft-naive-bayes-viewer"></a><span data-ttu-id="bd931-102">Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="bd931-102">Browse a Model Using the Microsoft Naive Bayes Viewer</span></span>
  <span data-ttu-id="bd931-103">Il [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visualizzatore Naive Bayes in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] consente di visualizzare i modelli di data mining compilati con l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] algoritmo Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="bd931-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] displays mining models that are built with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm.</span></span> <span data-ttu-id="bd931-104">L'algoritmo [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes è un algoritmo di classificazione altamente adattabile alle attività di modellazione predittiva.</span><span class="sxs-lookup"><span data-stu-id="bd931-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes algorithm is a classification algorithm that is highly adaptable to predictive modeling tasks.</span></span> <span data-ttu-id="bd931-105">Per altre informazioni su questo algoritmo, vedere [Algoritmo Microsoft Naive Bayes](microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="bd931-105">For more information about this algorithm, see [Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="bd931-106">Poiché uno degli scopi principali di un modello Naive Bayes consiste nell'esplorare rapidamente i dati di un set, il Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes include diversi metodi per la visualizzazione dell'interazione tra gli attributi stimabili e gli attributi di input per una tabella del case.</span><span class="sxs-lookup"><span data-stu-id="bd931-106">Because one of the main purposes of a naive Bayes model is to provide a way to quickly explore the data in a dataset, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides several methods for displaying the interaction between predictable attributes and input attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd931-107">Per visualizzare informazioni dettagliate sulle equazioni utilizzate nel modello e sugli schemi individuati, utilizzare il [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer.</span><span class="sxs-lookup"><span data-stu-id="bd931-107">If you want to view detailed information about the equations used in the model and the patterns that were discovered, you can switch to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree viewer.</span></span> <span data-ttu-id="bd931-108">Per altre informazioni, vedere [Visualizzare un modello usando Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) o [Microsoft Generic Content Tree Viewer &#40;Data mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="bd931-108">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) or [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>  
  
##  <a name="viewer-tabs"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="bd931-109">Schede del Visualizzatore</span><span class="sxs-lookup"><span data-stu-id="bd931-109">Viewer Tabs</span></span>  
 <span data-ttu-id="bd931-110">Per la visualizzazione di un modello di data mining in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]viene utilizzato il visualizzatore appropriato nella scheda **Visualizzatore modello di data mining** di Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="bd931-110">When you browse a mining model in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the model is displayed on the **Mining Model Viewer** tab of Data Mining Designer in the appropriate viewer for the model.</span></span> <span data-ttu-id="bd931-111">Per l'esplorazione dei dati, nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes sono disponibili le schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd931-111">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for exploring data:</span></span>  
  
-   [<span data-ttu-id="bd931-112">Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="bd931-112">Dependency Network</span></span>](#BKMK_Dependency)  
  
-   [<span data-ttu-id="bd931-113">Profili attributo</span><span class="sxs-lookup"><span data-stu-id="bd931-113">Attribute Profiles</span></span>](#BKMK_Profiles)  
  
-   [<span data-ttu-id="bd931-114">Caratteristiche attributo</span><span class="sxs-lookup"><span data-stu-id="bd931-114">Attribute Characteristics</span></span>](#BKMK_Characteristics)  
  
-   [<span data-ttu-id="bd931-115">Analisi discriminante attributi</span><span class="sxs-lookup"><span data-stu-id="bd931-115">Attribute Discrimination</span></span>](#BKMK_Discrimination)  
  
##  <a name="dependency-network"></a><a name="BKMK_Dependency"></a><span data-ttu-id="bd931-116">Rete di dipendenze</span><span class="sxs-lookup"><span data-stu-id="bd931-116">Dependency Network</span></span>  
 <span data-ttu-id="bd931-117">Nella scheda **Rete di dipendenze** vengono visualizzate le dipendenze tra gli attributi di input e gli attributi stimabili di un modello.</span><span class="sxs-lookup"><span data-stu-id="bd931-117">The **Dependency Network** tab displays the dependencies between the input attributes and the predictable attributes in a model.</span></span> <span data-ttu-id="bd931-118">Il dispositivo di scorrimento a sinistra del visualizzatore svolge la funzione di filtro correlato ai livelli di attendibilità delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="bd931-118">The slider at the left of the viewer acts as a filter that is tied to the strengths of the dependencies.</span></span> <span data-ttu-id="bd931-119">Se si sposta il dispositivo di scorrimento verso il basso, vengono visualizzati solo i collegamenti più attendibili.</span><span class="sxs-lookup"><span data-stu-id="bd931-119">Lowering the slider shows only the strongest links.</span></span>  
  
 <span data-ttu-id="bd931-120">Quando si seleziona un nodo, nel visualizzatore vengono evidenziate le dipendenze specifiche del nodo.</span><span class="sxs-lookup"><span data-stu-id="bd931-120">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="bd931-121">Se ad esempio si sceglie un nodo stimabile, nel visualizzatore verrà inoltre evidenziato ogni nodo che contribuisce alla stima del nodo stimabile.</span><span class="sxs-lookup"><span data-stu-id="bd931-121">For example, if you choose a predictable node, the viewer also highlights each node that helps predict the predictable node.</span></span>  
  
 <span data-ttu-id="bd931-122">La legenda nella parte inferiore del visualizzatore consente di individuare le corrispondenze tra i colori e i tipi di dipendenza rappresentati nel grafico.</span><span class="sxs-lookup"><span data-stu-id="bd931-122">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="bd931-123">Ad esempio, quando si seleziona un nodo stimabile, a quest'ultimo viene applicata un'ombreggiatura turchese mentre ai nodi utilizzati per la stima del nodo selezionato viene applicata un'ombreggiatura arancione.</span><span class="sxs-lookup"><span data-stu-id="bd931-123">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="bd931-124">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="bd931-124">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-profiles"></a><a name="BKMK_Profiles"></a> <span data-ttu-id="bd931-125">Profili attributo</span><span class="sxs-lookup"><span data-stu-id="bd931-125">Attribute Profiles</span></span>  
 <span data-ttu-id="bd931-126">Nella scheda **Profili attributo** viene visualizzata una griglia con istogrammi.</span><span class="sxs-lookup"><span data-stu-id="bd931-126">The **Attribute Profiles** tab displays histograms in a grid.</span></span> <span data-ttu-id="bd931-127">Tale griglia consente di confrontare l'attributo stimabile selezionato nella casella **Stimabile** con tutti gli altri attributi del modello.</span><span class="sxs-lookup"><span data-stu-id="bd931-127">You can use this grid to compare the predictable attribute that you select in the **Predictable** box to all other attributes that are in the model.</span></span> <span data-ttu-id="bd931-128">Ogni colonna della scheda rappresenta uno stato dell'attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="bd931-128">Each column in the tab represents a state of the predictable attribute.</span></span> <span data-ttu-id="bd931-129">Se l'attributo stimabile include molti stati, è possibile modificare il numero di stati visualizzati nell'istogramma regolando le **Barre istogramma**.</span><span class="sxs-lookup"><span data-stu-id="bd931-129">If the predictable attribute has many states, you can change the number of states that appear in the histogram by adjusting the **Histogram bars**.</span></span> <span data-ttu-id="bd931-130">Se il numero scelto è inferiore al numero totale di stati dell'attributo, gli stati saranno elencati nell'ordine in cui vengono supportati, con gli stati rimanenti raccolti in un singolo bucket grigio.</span><span class="sxs-lookup"><span data-stu-id="bd931-130">If the number you choose is less than the total number of states in the attribute, the states are listed in order of support, with the remaining states collected into a single gray bucket.</span></span>  
  
 <span data-ttu-id="bd931-131">Fare clic sulla casella di controllo **Mostra legenda** per visualizzare una legenda di data mining che consente di individuare le corrispondenze tra i colori dell'istogramma e gli stati di un attributo.</span><span class="sxs-lookup"><span data-stu-id="bd931-131">To display a Mining Legend that relates the colors of the histogram to the states of an attribute, click the **Show Legend** check box.</span></span> <span data-ttu-id="bd931-132">Nella legenda di data mining viene visualizzata anche la distribuzione di case per ogni coppia attributo-valore selezionata.</span><span class="sxs-lookup"><span data-stu-id="bd931-132">The Mining Legend also displays the distribution of cases for each attribute-value pair that you select.</span></span>  
  
 <span data-ttu-id="bd931-133">Per copiare il contenuto della griglia negli Appunti in formato tabella HTML, fare clic con il pulsante destro del mouse sulla scheda **Profili attributo** e scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="bd931-133">To copy the contents of the grid to the Clipboard as an HTML table, right-click the **Attribute Profiles** tab and select **Copy**.</span></span>  
  
 [<span data-ttu-id="bd931-134">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="bd931-134">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-characteristics"></a><a name="BKMK_Characteristics"></a><span data-ttu-id="bd931-135">Caratteristiche degli attributi</span><span class="sxs-lookup"><span data-stu-id="bd931-135">Attribute Characteristics</span></span>  
 <span data-ttu-id="bd931-136">Per usare la scheda **Caratteristiche attributo** , è necessario selezionare un attributo stimabile dall'elenco **Attributo** e uno degli stati corrispondenti dall'elenco **Valore** .</span><span class="sxs-lookup"><span data-stu-id="bd931-136">To use the **Attribute Characteristics** tab, select a predictable attribute from the **Attribute** list and select a state of the selected attribute from the **Value** list.</span></span> <span data-ttu-id="bd931-137">Quando si impostano tali variabili, nella scheda **Caratteristiche attributo** vengono visualizzati gli stati degli attributi associati al case dell'attributo selezionato.</span><span class="sxs-lookup"><span data-stu-id="bd931-137">When you set these variables, the **Attribute Characteristics** tab displays the states of the attributes that are associated with the selected case of the selected attribute.</span></span> <span data-ttu-id="bd931-138">Gli attributi vengono ordinati in base alla priorità.</span><span class="sxs-lookup"><span data-stu-id="bd931-138">The attributes are sorted by importance.</span></span>  
  
 [<span data-ttu-id="bd931-139">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="bd931-139">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
##  <a name="attribute-discrimination"></a><a name="BKMK_Discrimination"></a><span data-ttu-id="bd931-140">Discriminazione degli attributi</span><span class="sxs-lookup"><span data-stu-id="bd931-140">Attribute Discrimination</span></span>  
 <span data-ttu-id="bd931-141">Per usare la scheda **Analisi discriminante attributi** , è necessario selezionare un attributo stimabile e due degli stati corrispondenti dagli elenchi **Attributo**, **Valore 1**e **Valore 2** .</span><span class="sxs-lookup"><span data-stu-id="bd931-141">To use the **Attribute Discrimination** tab, select a predictable attribute and two of its states from the **Attribute**, **Value 1**, and **Value 2** lists.</span></span> <span data-ttu-id="bd931-142">Nella griglia della scheda **Analisi discriminante attributi** verranno visualizzate colonne con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd931-142">The grid on the **Attribute Discrimination** tab then displays the following information in columns:</span></span>  
  
 <span data-ttu-id="bd931-143">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="bd931-143">**Attribute**</span></span>  
 <span data-ttu-id="bd931-144">Elenca altri attributi nel set di dati contenente uno stato che predilige in modo significativo uno stato dell'attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="bd931-144">Lists other attributes in the dataset that contain a state that highly favors one state of the predictable attribute.</span></span>  
  
 <span data-ttu-id="bd931-145">**Valori**</span><span class="sxs-lookup"><span data-stu-id="bd931-145">**Values**</span></span>  
 <span data-ttu-id="bd931-146">Mostra il valore dell'attributo nella colonna **Attributo**.</span><span class="sxs-lookup"><span data-stu-id="bd931-146">Shows the value of the attribute in the **Attribute** column.</span></span>  
  
 <span data-ttu-id="bd931-147">**Predilige\<value 1>**</span><span class="sxs-lookup"><span data-stu-id="bd931-147">**Favors \<value 1>**</span></span>  
 <span data-ttu-id="bd931-148">Mostra una barra colorata che indica in quale misura il valore dell'attributo predilige il valore dell'attributo stimabile mostrato in **Valore 1**.</span><span class="sxs-lookup"><span data-stu-id="bd931-148">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 1**.</span></span>  
  
 <span data-ttu-id="bd931-149">**Predilige\<value 2>**</span><span class="sxs-lookup"><span data-stu-id="bd931-149">**Favors \<value 2>**</span></span>  
 <span data-ttu-id="bd931-150">Mostra una barra colorata che indica in quale misura il valore dell'attributo predilige il valore dell'attributo stimabile mostrato in **Valore 2**.</span><span class="sxs-lookup"><span data-stu-id="bd931-150">Shows a colored bar that indicates how strongly the attribute value favors the predictable attribute value shown in **Value 2**.</span></span>  
  
 [<span data-ttu-id="bd931-151">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="bd931-151">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="see-also"></a><span data-ttu-id="bd931-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd931-152">See Also</span></span>  
 <span data-ttu-id="bd931-153">[Algoritmo Microsoft Naive Bayes](microsoft-naive-bayes-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="bd931-153">[Microsoft Naive Bayes Algorithm](microsoft-naive-bayes-algorithm.md) </span></span>  
 <span data-ttu-id="bd931-154">[Attività e procedure relative al Visualizzatore modello di data mining](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="bd931-154">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="bd931-155">[Strumenti di data mining](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="bd931-155">[Data Mining Tools](data-mining-tools.md) </span></span>  
 [<span data-ttu-id="bd931-156">Visualizzatori modello di data mining</span><span class="sxs-lookup"><span data-stu-id="bd931-156">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
  
