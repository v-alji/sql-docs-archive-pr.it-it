---
title: Creare e gestire gerarchie (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8dd30cd0-a831-4d25-b577-648d7f3c7fa6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0bab3e09aadb4e0c857b9c1da3111e03e90f777e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626918"
---
# <a name="create-and-manage-hierarchies-ssas-tabular"></a><span data-ttu-id="2b8b0-102">Creare e gestire gerarchie (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="2b8b0-102">Create and Manage Hierarchies (SSAS Tabular)</span></span>
  <span data-ttu-id="2b8b0-103">Le gerarchie possono essere create e gestite in Progettazione modelli in Vista diagramma.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-103">Hierarchies can be created and managed in the model designer, in Diagram View.</span></span> <span data-ttu-id="2b8b0-104">Per visualizzare Progettazione modelli in Vista diagramma, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], fare clic sul menu **Modello** , scegliere **Vista modelli**, quindi **Vista diagramma**.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-104">To view the model designer in Diagram View, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
 <span data-ttu-id="2b8b0-105">In questo argomento sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b8b0-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="2b8b0-106">Creare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-106">Create a Hierarchy</span></span>](#bkmk_create)  
  
-   [<span data-ttu-id="2b8b0-107">Modificare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-107">Edit a Hierarchy</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="2b8b0-108">Eliminare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-108">Delete a Hierarchy</span></span>](#bkmk_delete)  
  
##  <a name="create-a-hierarchy"></a><a name="bkmk_create"></a> <span data-ttu-id="2b8b0-109">Creare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-109">Create a Hierarchy</span></span>  
 <span data-ttu-id="2b8b0-110">È possibile creare una gerarchia utilizzando le colonne e il menu di scelta rapida della tabella.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-110">You can create a hierarchy by using the columns and table context menu.</span></span> <span data-ttu-id="2b8b0-111">Quando si crea una gerarchia, un nuovo livello padre viene visualizzato con le colonne selezionate come livelli figlio.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-111">When you create a hierarchy, a new parent level displays with selected columns as child levels.</span></span>  
  
#### <a name="to-create-a-hierarchy-from-the-context-menu"></a><span data-ttu-id="2b8b0-112">Per creare una gerarchia dal menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="2b8b0-112">To create a hierarchy from the context menu</span></span>  
  
1.  <span data-ttu-id="2b8b0-113">Nella finestra di una tabella di Progettazione modelli (Vista diagramma) fare clic con il pulsante destro del mouse su una colonna, quindi scegliere **Crea gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-113">In the model designer (Diagram View), in a table window, right-click on a column, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="2b8b0-114">Per selezionare più colonne, fare clic su ciascuna colonna, fare clic con il pulsante destro del mouse per aprire il menu di scelta rapida, quindi scegliere **Crea gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-114">To select multiple columns, click each column, then right-click to open the context menu, and then click **Create Hierarchy**.</span></span>  
  
     <span data-ttu-id="2b8b0-115">Nella parte inferiore della finestra della tabella viene creato un livello di gerarchia padre e le colonne selezionate vengono copiate nella gerarchia come livelli figlio.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-115">A parent hierarchy level is created at the bottom of the table window and the selected columns are copied under the hierarchy as child levels.</span></span>  
  
2.  <span data-ttu-id="2b8b0-116">Digitare un nome per la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-116">Type a name for the hierarchy.</span></span>  
  
 <span data-ttu-id="2b8b0-117">È possibile trascinare colonne aggiuntive nel livello padre della gerarchia, che consente di copiare le colonne.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-117">You can drag additional columns into your hierarchy's parent level, which copies the columns.</span></span> <span data-ttu-id="2b8b0-118">Rilasciare il livello figlio per posizionarlo nel punto in cui si desidera venga visualizzato nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-118">Drop the child level to place it where you want it to appear in the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b8b0-119">Il comando Crea gerarchia sarà disabilitato nel menu di scelta rapida se si effettua una selezione multipla di una misura con una o più colonne oppure se si selezionano colonne da più tabelle.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-119">The Create Hierarchy command is disabled in the context menu if you multi-select a measure along with one or more columns or you select columns from multiple tables.</span></span>  
  
##  <a name="edit-a-hierarchy"></a><a name="bkmk_edit"></a><span data-ttu-id="2b8b0-120">Modificare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-120">Edit a Hierarchy</span></span>  
 <span data-ttu-id="2b8b0-121">È possibile rinominare una gerarchia o un livello figlio, modificare l'ordine dei livelli figlio, aggiungere altre colonne come livelli figlio, rimuovere un livello figlio da una gerarchia, mostrare il nome di origine di un livello figlio (il nome della colonna) e nascondere un livello figlio se il suo nome coincide con quello del livello padre della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-121">You can rename a hierarchy, rename a child level, change the order of the child levels, add additional columns as child levels, remove a child level from a hierarchy, show the source name of a child level (the column name), and hide a child level if it has the same name as the hierarchy parent level.</span></span>  
  
#### <a name="to-change-the-name-of-a-hierarchy-or-child-level"></a><span data-ttu-id="2b8b0-122">Per modificare il nome di una gerarchia o di un livello figlio</span><span class="sxs-lookup"><span data-stu-id="2b8b0-122">To change the name of a hierarchy or child level</span></span>  
  
1.  <span data-ttu-id="2b8b0-123">Fare clic con il pulsante destro del mouse sul livello padre della gerarchia o su un livello figlio, quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-123">Right-click the hierarchy parent level or a child level, and the click **Rename**.</span></span>  
  
2.  <span data-ttu-id="2b8b0-124">Digitare un nuovo nome o modificarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-124">Type a new name or edit the existing name.</span></span>  
  
#### <a name="to-change-the-order-of-a-child-level-in-a-hierarchy"></a><span data-ttu-id="2b8b0-125">Per modificare l'ordine di un livello figlio in una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-125">To change the order of a child level in a hierarchy</span></span>  
  
-   <span data-ttu-id="2b8b0-126">Fare clic e trascinare un livello figlio in una nuova posizione all'interno della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-126">Click and drag a child level into a new position in the hierarchy.</span></span>  
  
-   <span data-ttu-id="2b8b0-127">In alternativa, fare clic con il pulsante destro del mouse su un livello figlio della gerarchia e scegliere Sposta su per spostare in alto il livello nell'elenco oppure Sposta giù per spostarlo in basso.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-127">Or, right-click a child level of the hierarchy, and then click Move Up to move the level up in the list, or click Move Down to move the level down in the list.</span></span>  
  
-   <span data-ttu-id="2b8b0-128">In alternativa, fare clic su un livello figlio per selezionarlo, quindi premere ALT+freccia SU per spostare in alto il livello oppure ALT+freccia GIÙ per spostarlo in basso.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-128">Or, click a child level to select it, and then press Alt + Up Arrow to move the level up, or press Alt+Down Arrow to move the level down in the list.</span></span>  
  
#### <a name="to-add-another-child-level-to-a-hierarchy"></a><span data-ttu-id="2b8b0-129">Per aggiungere un altro livello figlio a una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-129">To add another child level to a hierarchy</span></span>  
  
-   <span data-ttu-id="2b8b0-130">Fare clic e trascinare una colonna nel livello padre o in un percorso specifico della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-130">Click and drag a column onto the parent level or into a specific location of the hierarchy.</span></span> <span data-ttu-id="2b8b0-131">La colonna verrà copiata come livello figlio della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-131">The column is copied as a child level of the hierarchy.</span></span>  
  
-   <span data-ttu-id="2b8b0-132">In alternativa, fare clic con il pulsante destro del mouse su una colonna, scegliere **Aggiungi a gerarchia**, quindi fare clic sulla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-132">Or, right-click a column, point to **Add to Hierarchy**, and then click the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b8b0-133">È possibile aggiungere una colonna nascosta dai report come livello figlio alla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-133">You can add a hidden column (a column that is hidden from reports) as a child level to the hierarchy.</span></span> <span data-ttu-id="2b8b0-134">Il livello figlio non sarà nascosto.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-134">The child level is not hidden.</span></span>  
  
#### <a name="to-remove-a-child-level-from-a-hierarchy"></a><span data-ttu-id="2b8b0-135">Per rimuovere un livello figlio da una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-135">To remove a child level from a hierarchy</span></span>  
  
-   <span data-ttu-id="2b8b0-136">Fare clic con il pulsante destro del mouse su un livello figlio, quindi scegliere **Rimuovi da gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-136">Right-click a child level, and then click **Remove from Hierarchy**.</span></span>  
  
-   <span data-ttu-id="2b8b0-137">In alternativa, fare clic su un livello figlio e premere **CANC**.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-137">Or, click a child level, and then press **Delete**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b8b0-138">Se si rinomina un livello figlio della gerarchia, non condividerà più lo stesso nome della colonna da cui è stato copiato.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-138">If you rename a hierarchy child level, it no longer shares the same name as the column that it is copied from.</span></span> <span data-ttu-id="2b8b0-139">Utilizzare il comando **Mostra nome di origine** per visualizzare la colonna da cui è stato copiato.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-139">Use the **Show Source Name** command to see which column it was copied from.</span></span>  
  
#### <a name="to-show-a-source-name"></a><span data-ttu-id="2b8b0-140">Per mostrare un nome di origine</span><span class="sxs-lookup"><span data-stu-id="2b8b0-140">To show a source name</span></span>  
  
-   <span data-ttu-id="2b8b0-141">Fare clic con il pulsante destro del mouse su un livello figlio della gerarchia, quindi scegliere **Show Source Name**(Mostra nome di origine).</span><span class="sxs-lookup"><span data-stu-id="2b8b0-141">Right-click a hierarchy child level, and then click **Show Source Name**.</span></span> <span data-ttu-id="2b8b0-142">Viene visualizzato il nome della colonna da cui è stato copiato.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-142">The name of the column that it was copied from appears.</span></span>  
  
##  <a name="delete-a-hierarchy"></a><a name="bkmk_delete"></a> <span data-ttu-id="2b8b0-143">Eliminare una gerarchia</span><span class="sxs-lookup"><span data-stu-id="2b8b0-143">Delete a Hierarchy</span></span>  
  
#### <a name="to-delete-a-hierarchy-and-remove-its-child-levels"></a><span data-ttu-id="2b8b0-144">Per eliminare una gerarchia e rimuovere i relativi livelli figlio</span><span class="sxs-lookup"><span data-stu-id="2b8b0-144">To delete a hierarchy and remove its child levels</span></span>  
  
-   <span data-ttu-id="2b8b0-145">Fare clic con il pulsante destro del mouse sul livello padre della gerarchia, quindi scegliere Elimina gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-145">Right-click the parent hierarchy level, and then click Delete Hierarchy.</span></span>  
  
-   <span data-ttu-id="2b8b0-146">In alternativa, fare clic sul livello padre della gerarchia e premere CANC.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-146">Or, click the parent hierarchy level, and then press Delete.</span></span> <span data-ttu-id="2b8b0-147">Verranno rimossi anche tutti i livelli figlio.</span><span class="sxs-lookup"><span data-stu-id="2b8b0-147">This also removes all the child levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b8b0-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b8b0-148">See Also</span></span>  
 <span data-ttu-id="2b8b0-149">[Progettazione di modelli tabulari &#40;SSAS tabulare&#41;](../tabular-model-designer-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="2b8b0-149">[Tabular Model Designer &#40;SSAS Tabular&#41;](../tabular-model-designer-ssas-tabular.md) </span></span>  
 <span data-ttu-id="2b8b0-150">[Gerarchie &#40;SSAS tabulare&#41;](hierarchies-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="2b8b0-150">[Hierarchies &#40;SSAS Tabular&#41;](hierarchies-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="2b8b0-151">Misure &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="2b8b0-151">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
