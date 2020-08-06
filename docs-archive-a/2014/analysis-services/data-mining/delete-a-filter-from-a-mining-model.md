---
title: Eliminare un filtro da un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filters [Analysis Services]
ms.assetid: 91220b21-adbc-49a9-b200-8bf0a724eff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 404c23c0e55bffba2ce8410c9c30d6ad1fa1991b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625033"
---
# <a name="delete-a-filter-from-a-mining-model"></a><span data-ttu-id="83ae2-102">Eliminare un filtro da un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="83ae2-102">Delete a Filter from a Mining Model</span></span>
  <span data-ttu-id="83ae2-103">Quando si crea un filtro in un modello di data mining, è possibile creare modelli in un subset dei dati nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="83ae2-103">When you create a filter on a mining model, you can create models on a subset of the data in the data source view.</span></span> <span data-ttu-id="83ae2-104">I filtri sono anche utili per il test dell'accuratezza del modello su un subset dei dati originali.</span><span class="sxs-lookup"><span data-stu-id="83ae2-104">Filters are also useful for testing the accuracy of the model on a subset of the original data.</span></span>  
  
 <span data-ttu-id="83ae2-105">Tuttavia, è necessario eliminare il filtro se si desidera visualizzare nuovamente il set completo dei case.</span><span class="sxs-lookup"><span data-stu-id="83ae2-105">However, you must delete the filter if you want to view the complete set of cases again.</span></span> <span data-ttu-id="83ae2-106">In questa procedura viene descritto come rimuovere le condizioni su un filtro o eliminare completamente il filtro.</span><span class="sxs-lookup"><span data-stu-id="83ae2-106">This procedure describes how to remove conditions on a filter, or delete the filter completely.</span></span>  
  
### <a name="to-delete-a-condition-from-a-filter-on-a-mining-model"></a><span data-ttu-id="83ae2-107">Per eliminare una condizione da un filtro su un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="83ae2-107">To delete a condition from a filter on a mining model</span></span>  
  
1.  <span data-ttu-id="83ae2-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Esplora soluzioni, fare clic sulla struttura di data mining che contiene il modello di data mining da filtrare.</span><span class="sxs-lookup"><span data-stu-id="83ae2-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="83ae2-109">Fare clic sulla scheda **Modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="83ae2-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="83ae2-110">Selezionare il modello, quindi fare clic con il pulsante destro del mouse per aprire il menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="83ae2-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="83ae2-111">-oppure-</span><span class="sxs-lookup"><span data-stu-id="83ae2-111">-or-</span></span>  
  
     <span data-ttu-id="83ae2-112">Selezionare il modello.</span><span class="sxs-lookup"><span data-stu-id="83ae2-112">Select the model.</span></span> <span data-ttu-id="83ae2-113">Scegliere **Imposta filtro modello** dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-113">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="83ae2-114">Nella finestra di dialogo **Filtro modello** fare clic con il pulsante destro del mouse sulla riga della griglia che contiene la condizione da eliminare.</span><span class="sxs-lookup"><span data-stu-id="83ae2-114">In the **Model Filter** dialog box, right-click the row in the grid that contains the condition you want to delete.</span></span>  
  
5.  <span data-ttu-id="83ae2-115">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-115">Select **Delete**.</span></span>  
  
### <a name="to-clear-the-filter-on-a-mining-model-in-the-filter-editor-dialog-box"></a><span data-ttu-id="83ae2-116">Per cancellare il filtro su un modello di data mining nella finestra di dialogo Editor filtri</span><span class="sxs-lookup"><span data-stu-id="83ae2-116">To clear the filter on a mining model in the Filter Editor dialog box</span></span>  
  
-   <span data-ttu-id="83ae2-117">Nella finestra di dialogo **Editor filtri** fare clic con il pulsante destro del mouse su una riga della griglia e quindi scegliere **Elimina tutto**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-117">In the **Filter Editor** dialog box, right-click any row in the grid, and select **Delete All**.</span></span>  
  
## <a name="working-with-model-filters-using-the-properties-window"></a><span data-ttu-id="83ae2-118">Utilizzo dei filtri di modelli con la finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="83ae2-118">Working with Model Filters Using the Properties Window</span></span>  
 <span data-ttu-id="83ae2-119">Se si desidera eliminare l'intero filtro, non è necessario aprire le finestre di dialogo Editor filtri.</span><span class="sxs-lookup"><span data-stu-id="83ae2-119">If you want to delete the whole filter, you do not need to open the filter editor dialog boxes.</span></span> <span data-ttu-id="83ae2-120">Le condizioni di filtro create sono disponibili nella proprietà `Filter` del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="83ae2-120">The filter conditions that you created are available in the `Filter` property of the mining model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83ae2-121">È possibile visualizzare le proprietà di un modello di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ma non in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83ae2-121">You can view the properties of a mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], but not in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-clear-the-filter-on-a-mining-model-in-solution-explorer"></a><span data-ttu-id="83ae2-122">Per cancellare il filtro su un modello di data mining in Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="83ae2-122">To clear the filter on a mining model in Solution Explorer</span></span>  
  
1.  <span data-ttu-id="83ae2-123">In Esplora soluzioni fare clic sul modello di data mining che contiene il filtro.</span><span class="sxs-lookup"><span data-stu-id="83ae2-123">In Solution Explorer, click the mining model that contains the filter.</span></span>  
  
2.  <span data-ttu-id="83ae2-124">Nella finestra **Proprietà** fare clic con il pulsante destro del mouse sul testo del filtro nella `Filter` proprietà, quindi scegliere **Seleziona tutto**.</span><span class="sxs-lookup"><span data-stu-id="83ae2-124">In the **Properties** window, right-click the filter text in the `Filter` property, and select **Select All**.</span></span>  
  
3.  <span data-ttu-id="83ae2-125">Premere il tasto BACKSPACE o CANC.</span><span class="sxs-lookup"><span data-stu-id="83ae2-125">Press the Backspace or Delete key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ae2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83ae2-126">See Also</span></span>  
 <span data-ttu-id="83ae2-127">[Drill-through sui dati del case da un modello di data mining](drill-through-to-case-data-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="83ae2-127">[Drill Through to Case Data from a Mining Model](drill-through-to-case-data-from-a-mining-model.md) </span></span>  
 <span data-ttu-id="83ae2-128">[Attività e procedure relative al modello di data mining](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="83ae2-128">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="83ae2-129">Filtri per i modelli di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="83ae2-129">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
  
