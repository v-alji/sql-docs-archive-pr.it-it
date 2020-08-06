---
title: Copiare una vista di un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clipboards [data mining]
- Mining Model Viewer [Analysis Services], clipboards
- copying mining models to clipboard
ms.assetid: 768372db-e5b4-4990-b459-03d854fd9a6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 36d4d372bd235cd1cc0c043ff98151091e242269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711167"
---
# <a name="copy-a-view-of-a-mining-model"></a><span data-ttu-id="8793e-102">Copiare una vista di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="8793e-102">Copy a View of a Mining Model</span></span>
  <span data-ttu-id="8793e-103">Nella scheda **Visualizzatore modello di data mining** di Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] viene usato un visualizzatore separato per ogni tipo di modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="8793e-103">The **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] uses a separate viewer for each type of mining model.</span></span> <span data-ttu-id="8793e-104">Alcuni visualizzatori includono componenti da cui è possibile copiare i contenuti negli Appunti e quindi incollarli in un documento o in un software per la modifica di immagini.</span><span class="sxs-lookup"><span data-stu-id="8793e-104">Several of the viewers have components from which you can copy the contents to the Clipboard, and from there paste the contents into a document or into image manipulation software.</span></span> <span data-ttu-id="8793e-105">Questa funzionalità è disponibile nei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8793e-105">The following components make this functionality available:</span></span>  
  
-   <span data-ttu-id="8793e-106">Diagramma dei cluster nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Clustering e nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="8793e-106">Cluster Diagram in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="8793e-107">Albero delle decisioni nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Trees e nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series</span><span class="sxs-lookup"><span data-stu-id="8793e-107">Decision Tree in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series Viewer</span></span>  
  
-   <span data-ttu-id="8793e-108">Transizioni di stato nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="8793e-108">State Transitions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="8793e-109">Rete di dipendenze nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules, nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes e nel Visualizzatore [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees</span><span class="sxs-lookup"><span data-stu-id="8793e-109">Dependency Network in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer, and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer</span></span>  
  
-   <span data-ttu-id="8793e-110">Contenuto del modello di data mining, dal riquadro Dettagli nodo di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer</span><span class="sxs-lookup"><span data-stu-id="8793e-110">Mining model content, from the Node Details pane of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer</span></span>  
  
 <span data-ttu-id="8793e-111">È possibile copiare l'intera rappresentazione del modello di data mining oppure solo la parte visibile nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="8793e-111">You can copy the complete representation of the mining model, or just the part that is visible in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8793e-112">Quando si copia un modello utilizzando il visualizzatore, non si crea un nuovo oggetto modello.</span><span class="sxs-lookup"><span data-stu-id="8793e-112">When you copy a model using the viewer, it does not create a new model object.</span></span> <span data-ttu-id="8793e-113">Per creare un nuovo modello, è necessario utilizzare la procedura guidata oppure Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="8793e-113">To create a new model, you must use either the wizard, or the Data Mining Designer,.</span></span> <span data-ttu-id="8793e-114">Per altre informazioni, vedere [Eseguire una copia di un modello di data mining](make-a-copy-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="8793e-114">For more information, see [Make a Copy of a Mining Model](make-a-copy-of-a-mining-model.md).</span></span>  
  
### <a name="to-copy-the-complete-model-to-the-clipboard"></a><span data-ttu-id="8793e-115">Per copiare l'intero modello negli Appunti</span><span class="sxs-lookup"><span data-stu-id="8793e-115">To copy the complete model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="8793e-116">Nell'elenco **Modello di data mining** nella scheda **Visualizzatore modello di data mining** selezionare il modello di data mining che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8793e-116">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="8793e-117">Selezionare la scheda appropriata, ad esempio la scheda **Rete di dipendenze** , quindi fare clic su **Copia grafico intero** sulla barra degli strumenti della scheda.</span><span class="sxs-lookup"><span data-stu-id="8793e-117">Select the appropriate tab, such as the **Dependency Network** tab, and then click **Copy Entire Graph** on the toolbar of that tab.</span></span>  
  
### <a name="to-copy-the-visible-piece-of-the-model-to-the-clipboard"></a><span data-ttu-id="8793e-118">Per copiare la parte visibile del modello negli Appunti</span><span class="sxs-lookup"><span data-stu-id="8793e-118">To copy the visible piece of the model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="8793e-119">Nell'elenco **Modello di data mining** nella scheda **Visualizzatore modello di data mining** selezionare il modello di data mining che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8793e-119">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="8793e-120">Selezionare la scheda appropriata, ad esempio la scheda **Rete di dipendenze** , quindi ingrandire o ridurre la visualizzazione del modello in base al livello desiderato.</span><span class="sxs-lookup"><span data-stu-id="8793e-120">Select the appropriate tab, such as the **Dependency Network** tab, and then zoom in or out to view the model at the level that you want.</span></span>  
  
3.  <span data-ttu-id="8793e-121">Fare clic su **Copia parte visibile del grafico** sulla barra degli strumenti della scheda selezionata.</span><span class="sxs-lookup"><span data-stu-id="8793e-121">Click **Copy Graph View** on the toolbar of the selected tab.</span></span>  
  
### <a name="to-copy-the-mining-model-content-to-the-clipboard"></a><span data-ttu-id="8793e-122">Per copiare il contenuto di un modello di data mining negli Appunti</span><span class="sxs-lookup"><span data-stu-id="8793e-122">To copy the mining model content to the Clipboard</span></span>  
  
1.  <span data-ttu-id="8793e-123">Nell'elenco **Modello di data mining** nella scheda **Visualizzatore modello di data mining** selezionare il modello di data mining che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8793e-123">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="8793e-124">Dall'elenco a discesa **Visualizzatore** selezionare **Microsoft Generic Content Tree Viewer**.</span><span class="sxs-lookup"><span data-stu-id="8793e-124">From the **Viewer** drop-down list, select **Microsoft Generic Content Tree Viewer**.</span></span>  
  
3.  <span data-ttu-id="8793e-125">Nel riquadro **Didascalia nodo (ID univoco)** fare clic su un nodo.</span><span class="sxs-lookup"><span data-stu-id="8793e-125">In the **Node Caption (Unique ID)** pane, click a node.</span></span>  
  
4.  <span data-ttu-id="8793e-126">Fare clic con il pulsante destro del mouse sul riquadro **Dettagli nodo** , quindi scegliere **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="8793e-126">Right-click the **Node Details** pane and then select **Select All**.</span></span>  
  
5.  <span data-ttu-id="8793e-127">Fare nuovamente clic con il pulsante destro del mouse sul riquadro **Dettagli nodo** , quindi scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="8793e-127">Right-click the **Node Details** pane again and select **Copy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8793e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8793e-128">See Also</span></span>  
 [<span data-ttu-id="8793e-129">Attività e procedure relative al visualizzatore modello di data mining</span><span class="sxs-lookup"><span data-stu-id="8793e-129">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
  
