---
title: Spostare o eliminare un elemento (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- moving items
- items [Reporting Services], moving
ms.assetid: 980a66c7-a18b-4af7-8954-45726fa517d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a61ad56ea9e20e7fdf38d5acf05529b685ee896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711604"
---
# <a name="move-or-delete-an-item-report-manager"></a><span data-ttu-id="98fa8-102">Spostare o eliminare un elemento (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="98fa8-102">Move or Delete an Item (Report Manager)</span></span>
  <span data-ttu-id="98fa8-103">I report e gli altri elementi relativi ai report pubblicati in un server di report vengono archiviati in cartelle.</span><span class="sxs-lookup"><span data-stu-id="98fa8-103">Reports and report-related items that you publish to a report server are stored in folders.</span></span> <span data-ttu-id="98fa8-104">È possibile spostare gli elementi in una cartella diversa e i riferimenti a tali elementi vengono mantenuti automaticamente dal server di report.</span><span class="sxs-lookup"><span data-stu-id="98fa8-104">You can move items to a different folder and references to those items are maintained automatically by the report server.</span></span> <span data-ttu-id="98fa8-105">Prima di eliminare un elemento, verificare se sono presenti altri elementi che dipendono da esso.</span><span class="sxs-lookup"><span data-stu-id="98fa8-105">Before you delete an item, consider whether other items depend on it.</span></span>  
  
## <a name="move-an-item"></a><span data-ttu-id="98fa8-106">Spostare un elemento</span><span class="sxs-lookup"><span data-stu-id="98fa8-106">Move an Item</span></span>  
 <span data-ttu-id="98fa8-107">È possibile spostare gli elementi del server di report in percorsi di cartelle diversi nella gerarchia di cartelle del server di report.</span><span class="sxs-lookup"><span data-stu-id="98fa8-107">You can move report server items to different folder locations in the report server folder hierarchy.</span></span> <span data-ttu-id="98fa8-108">Quando si sposta un elemento, tutte le proprietà, incluse le impostazioni di sicurezza, vengono spostate con l'elemento nel nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="98fa8-108">When you move an item, all properties (including security settings) move with the item to the new location.</span></span> <span data-ttu-id="98fa8-109">Quando si sposta una cartella, vengono spostati tutti gli elementi contenuti nella cartella.</span><span class="sxs-lookup"><span data-stu-id="98fa8-109">When you move a folder, all the items in the folder move with it.</span></span>  
  
 <span data-ttu-id="98fa8-110">In Gestione report gli elementi che è possibile spostare vengono indicati nella gerarchia di cartelle.</span><span class="sxs-lookup"><span data-stu-id="98fa8-110">In Report Manager, the items that you can move are indicated in the folder hierarchy.</span></span> <span data-ttu-id="98fa8-111">Nella tabella seguente sono illustrate le icone di ogni elemento che è possibile spostare.</span><span class="sxs-lookup"><span data-stu-id="98fa8-111">The following table shows the icon for each movable item.</span></span>  
  
|<span data-ttu-id="98fa8-112">Icona</span><span class="sxs-lookup"><span data-stu-id="98fa8-112">Icon</span></span>|<span data-ttu-id="98fa8-113">Elemento spostabile</span><span class="sxs-lookup"><span data-stu-id="98fa8-113">Moveable item</span></span>|  
|----------|-------------------|  
|<span data-ttu-id="98fa8-114">![Report icon](../media/hlp-16doc.gif "Icona di report")</span><span class="sxs-lookup"><span data-stu-id="98fa8-114">![Report icon](../media/hlp-16doc.gif "Report icon")</span></span>|<span data-ttu-id="98fa8-115">Report</span><span class="sxs-lookup"><span data-stu-id="98fa8-115">Report</span></span>|  
|<span data-ttu-id="98fa8-116">![Icona di report collegato](../media/hlp-16linked.gif "Icona di report collegato")</span><span class="sxs-lookup"><span data-stu-id="98fa8-116">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>|<span data-ttu-id="98fa8-117">Report collegato</span><span class="sxs-lookup"><span data-stu-id="98fa8-117">Linked report</span></span>|  
|<span data-ttu-id="98fa8-118">![Icona Cartella](../media/hlp-16folder.gif "Icona Cartella")</span><span class="sxs-lookup"><span data-stu-id="98fa8-118">![Folder icon](../media/hlp-16folder.gif "Folder icon")</span></span>|<span data-ttu-id="98fa8-119">Cartella</span><span class="sxs-lookup"><span data-stu-id="98fa8-119">Folder</span></span>|  
|<span data-ttu-id="98fa8-120">![Icona di risorsa generica](../media/hlp-16file.gif "Icona di risorsa generica")</span><span class="sxs-lookup"><span data-stu-id="98fa8-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon")</span></span>|<span data-ttu-id="98fa8-121">Risorsa generica</span><span class="sxs-lookup"><span data-stu-id="98fa8-121">Generic resource</span></span>|  
|<span data-ttu-id="98fa8-122">![Shared data source icon](../media/hlp-16datasource.png "Icona dell'origine dati condivisa")</span><span class="sxs-lookup"><span data-stu-id="98fa8-122">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>|<span data-ttu-id="98fa8-123">Origine dati condivisa</span><span class="sxs-lookup"><span data-stu-id="98fa8-123">Shared data source</span></span>|  
||<span data-ttu-id="98fa8-124">Set di dati condiviso</span><span class="sxs-lookup"><span data-stu-id="98fa8-124">Shared dataset</span></span>|  
  
 <span data-ttu-id="98fa8-125">Non tutti gli elementi possono essere spostati.</span><span class="sxs-lookup"><span data-stu-id="98fa8-125">Not all items that you work with can be moved.</span></span> <span data-ttu-id="98fa8-126">Non è possibile spostare elementi associati a un report, ad esempio le sottoscrizioni o la cronologia del report.</span><span class="sxs-lookup"><span data-stu-id="98fa8-126">You cannot move items that are associated with a report, such as subscriptions or report history.</span></span> <span data-ttu-id="98fa8-127">Tali elementi si spostano insieme ai report a essi associati.</span><span class="sxs-lookup"><span data-stu-id="98fa8-127">Those items move with their associated reports.</span></span> <span data-ttu-id="98fa8-128">Analogamente, non è possibile spostare elementi disponibili all'esterno della gerarchia di cartelle, ad esempio le pianificazioni condivise.</span><span class="sxs-lookup"><span data-stu-id="98fa8-128">Similarly, you cannot move items, such as shared schedules, that exist outside of the folder hierarchy.</span></span> <span data-ttu-id="98fa8-129">Non è possibile spostare gli elementi se non si dispone delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="98fa8-129">You cannot move items if you lack permission to do so.</span></span> <span data-ttu-id="98fa8-130">L'autorizzazione per lo spostamento di un elemento viene concessa a un utente selezionando le attività seguenti nell'assegnazione di ruolo dell'utente per l'elemento specifico: "Gestione di report", "Gestione modelli", "Gestione di cartelle" e "Gestione di origini dei dati".</span><span class="sxs-lookup"><span data-stu-id="98fa8-130">Permission to move an item is conveyed when the following tasks are selected in your role assignment for the item in question: "Manage reports," "Manage models", "Manage folders," and "Manage data sources."</span></span>  
  
#### <a name="to-move-an-item-from-within-the-contents-page"></a><span data-ttu-id="98fa8-131">Per spostare un elemento dalla pagina Contenuto</span><span class="sxs-lookup"><span data-stu-id="98fa8-131">To move an item from within the Contents page</span></span>  
  
1.  <span data-ttu-id="98fa8-132">Start [Gestione report &#40;modalità nativa SSRS&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="98fa8-132">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="98fa8-133">In Gestione report passare alla pagina **Contenuto** e individuare l'elemento da spostare.</span><span class="sxs-lookup"><span data-stu-id="98fa8-133">In Report Manager, navigate to the **Contents** page, and locate the item that you want to move.</span></span>  
  
3.  <span data-ttu-id="98fa8-134">Posizionare il puntatore del mouse sull'elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="98fa8-134">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="98fa8-135">Nel menu a discesa fare clic su **Sposta**.</span><span class="sxs-lookup"><span data-stu-id="98fa8-135">In the drop-down menu, click **Move**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="98fa8-136">In **Percorso**specificare la cartella in cui si vuole spostare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="98fa8-136">For **Location**, specify the folder you want to move the item to.</span></span> <span data-ttu-id="98fa8-137">È possibile digitare il nome completo della cartella oppure utilizzare il controllo dell'albero per passare alla cartella desiderata.</span><span class="sxs-lookup"><span data-stu-id="98fa8-137">You can type the fully qualified folder name or use the tree control to navigate to the folder.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="98fa8-138">In alternativa, è possibile passare all'oggetto da spostare, fare clic su **Proprietà**e quindi su **Sposta** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="98fa8-138">Alternatively, you can navigate to the object you want to move, click **Properties**, and then click **Move** at the top of the page.</span></span>  
  
## <a name="delete-an-item"></a><span data-ttu-id="98fa8-139">Eliminare un elemento</span><span class="sxs-lookup"><span data-stu-id="98fa8-139">Delete an item</span></span>  
 <span data-ttu-id="98fa8-140">Prima di eliminare un elemento, determinare se è utilizzato da altri elementi.</span><span class="sxs-lookup"><span data-stu-id="98fa8-140">Before you delete an item, determine if it is used by other items.</span></span> <span data-ttu-id="98fa8-141">Se ad esempio si elimina un'origine dati condivisa, i report e i modelli che la utilizzano non verranno più eseguiti.</span><span class="sxs-lookup"><span data-stu-id="98fa8-141">For example, if you delete a shared data source, reports and models that use that data source will no longer run.</span></span> <span data-ttu-id="98fa8-142">Quando si elimina un report, vengono eliminate anche la cronologia del report e le sottoscrizioni associate.</span><span class="sxs-lookup"><span data-stu-id="98fa8-142">If you delete a report, subscriptions and report history associated with that report are also deleted.</span></span> <span data-ttu-id="98fa8-143">Per trovare elementi dipendenti per un elemento, vedere la pagina relativa agli elementi dipendenti &#40;Gestione report&#41;]. /dependent-items-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="98fa8-143">To find dependent items for an item, see [Dependent Items Page &#40;Report Manager&#41;]../dependent-items-page-report-manager.md).</span></span>  
  
#### <a name="to-delete-a-report-or-item"></a><span data-ttu-id="98fa8-144">Per eliminare un report o un elemento</span><span class="sxs-lookup"><span data-stu-id="98fa8-144">To delete a report or item</span></span>  
  
1.  <span data-ttu-id="98fa8-145">Start [Gestione report &#40;modalità nativa SSRS&#41;].. /report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="98fa8-145">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="98fa8-146">In Gestione report passare alla pagina **Contenuto** e quindi individuare l'elemento da eliminare.</span><span class="sxs-lookup"><span data-stu-id="98fa8-146">In Report Manager, navigate to the **Contents** page, and locate the item that you want to delete.</span></span>  
  
3.  <span data-ttu-id="98fa8-147">Posizionare il puntatore del mouse sull'elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="98fa8-147">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="98fa8-148">Scegliere **Elimina**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="98fa8-148">In the drop-down menu, click **Delete**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98fa8-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98fa8-149">See Also</span></span>  
 <span data-ttu-id="98fa8-150">[Contenuto pagina &#40;Gestione report&#41;].. /contents-page-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="98fa8-150">[Contents Page &#40;Report Manager&#41;]../contents-page-report-manager.md)</span></span>   
 [<span data-ttu-id="98fa8-151">Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="98fa8-151">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
