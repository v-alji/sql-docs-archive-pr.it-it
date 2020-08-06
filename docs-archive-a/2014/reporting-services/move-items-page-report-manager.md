---
title: Pagina Sposta elementi (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fc83b8d2-bc79-4b56-8970-34a1cbbcc176
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98ff306caf634a5f0478e2eba03c2313b24be274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723580"
---
# <a name="move-items-page-report-manager"></a><span data-ttu-id="13d29-102">Pagina Spostamento elementi (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="13d29-102">Move Items Page (Report Manager)</span></span>
  <span data-ttu-id="13d29-103">La pagina di spostamento degli elementi consente di spostare un report, una cartella o altri elementi in una nuova posizione nel server di report.</span><span class="sxs-lookup"><span data-stu-id="13d29-103">Use the Move Items page to move a report, folder, or other item to a new location on the report server.</span></span> <span data-ttu-id="13d29-104">È possibile digitare il percorso della nuova posizione oppure utilizzare una visualizzazione albero per selezionare una nuova posizione nello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="13d29-104">You can type the path of the new location or use a tree view to browse to a new location in the report server namespace.</span></span> <span data-ttu-id="13d29-105">Si possono spostare solo gli elementi per i quali si dispone delle autorizzazioni per lo spostamento e che sono archiviati nel server di report corrente.</span><span class="sxs-lookup"><span data-stu-id="13d29-105">You can only move items that you have permission to move and that are stored on the current report server.</span></span>  
  
 <span data-ttu-id="13d29-106">Quando si sposta un elemento a cui un altro elemento fa riferimento, ad esempio un'origine dati condivisa o un modello a cui fanno riferimento molti report, le informazioni sul percorso dell'elemento vengono aggiornate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="13d29-106">When you move an item that is referenced by another item (for example, a shared data source or model that is referenced by many reports), the path information for that item is updated automatically.</span></span> <span data-ttu-id="13d29-107">Un'origine dati condivisa può pertanto essere spostata senza interrompere la connessione all'origine dati dei report e dei modelli che la utilizzano.</span><span class="sxs-lookup"><span data-stu-id="13d29-107">Moving a shared data source does not disrupt a data source connection to the reports and models that use it.</span></span> <span data-ttu-id="13d29-108">Se si sposta un'origine dati condivisa o un modello in una cartella per la quale gli utenti non dispongono di autorizzazioni, gli utenti potranno comunque eseguire i report che fanno riferimento all'origine dati o al modello, ma l'elemento non sarà visibile nella gerarchia di cartelle.</span><span class="sxs-lookup"><span data-stu-id="13d29-108">If you move a shared data source or model to a folder for which users do not have permission, they will still be able to run any report that references the data source or model, however the item will not be visible to them in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="13d29-109">In **Percorso**specificare il percorso completo della cartella, a partire dal nome della cartella radice.</span><span class="sxs-lookup"><span data-stu-id="13d29-109">For **Location**, specify the full path to folder, beginning with the root folder name.</span></span> <span data-ttu-id="13d29-110">È possibile digitare il nome del percorso oppure utilizzare la visualizzazione albero per passare alla cartella desiderata.</span><span class="sxs-lookup"><span data-stu-id="13d29-110">You can type the path name or use the tree view to navigate to the folder you want.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13d29-111">Non tutti gli elementi sono mobili.</span><span class="sxs-lookup"><span data-stu-id="13d29-111">Not all items are movable.</span></span> <span data-ttu-id="13d29-112">Non è possibile spostare cartelle riservate come Home, Report personali o Cartelle utenti.</span><span class="sxs-lookup"><span data-stu-id="13d29-112">You cannot move reserved folders such as Home, My Reports, or Users Folders.</span></span> <span data-ttu-id="13d29-113">Non è inoltre possibile spostare la cronologia o gli snapshot dei report in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="13d29-113">You cannot move report history or snapshots to different locations.</span></span> <span data-ttu-id="13d29-114">La cronologia e gli snapshot sono sempre posizionati nello stesso percorso del report su cui si basano ed è possibile accedervi solo tramite il report associato.</span><span class="sxs-lookup"><span data-stu-id="13d29-114">History and snapshots are always located with, and accessed through, the report on which they are based.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="13d29-115">Spostamento</span><span class="sxs-lookup"><span data-stu-id="13d29-115">Navigation</span></span>  
 <span data-ttu-id="13d29-116">Utilizzare le procedure riportate di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="13d29-116">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-details-view"></a><span data-ttu-id="13d29-117">Per aprire la pagina di spostamento degli elementi dalla pagina Contenuto in Visualizzazione Dettagli</span><span class="sxs-lookup"><span data-stu-id="13d29-117">To open the Move Items page from the Contents page in Details View</span></span>  
  
1.  <span data-ttu-id="13d29-118">Aprire Gestione report e navigare fino alla cartella che contiene l'elemento che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="13d29-118">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="13d29-119">È possibile spostare anche elementi dalla home page di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="13d29-119">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="13d29-120">Nella barra degli strumenti fare clic su **Visualizzazione Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="13d29-120">In the toolbar, click **Details View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13d29-121"> Se viene visualizzato solo **Visualizzazione Affiancata**, ci si trova già in **Visualizzazione Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="13d29-121">If you see only **Tiles View**, you are already in **Details View**.</span></span>  
  
3.  <span data-ttu-id="13d29-122">Selezionare la casella accanto all'elemento, quindi fare clic su **Sposta** nella barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="13d29-122">Select the box next to an item, and then click **Move** in the toolbar.</span></span> <span data-ttu-id="13d29-123">È possibile selezionare più di una casella se si desidera spostare più elementi nello stesso percorso nuovo.</span><span class="sxs-lookup"><span data-stu-id="13d29-123">You can select more than one box if you want to move multiple items to the same new location.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-tiles-view"></a><span data-ttu-id="13d29-124">Per aprire la pagina di spostamento degli elementi dalla pagina Contenuto in Visualizzazione Affiancata</span><span class="sxs-lookup"><span data-stu-id="13d29-124">To open the Move Items page from the Contents page in Tiles View</span></span>  
  
1.  <span data-ttu-id="13d29-125">Aprire Gestione report e navigare fino alla cartella che contiene l'elemento che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="13d29-125">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="13d29-126">È possibile spostare anche elementi dalla home page di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="13d29-126">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="13d29-127">Nella barra degli strumenti fare clic su **Visualizzazione Affiancata**.</span><span class="sxs-lookup"><span data-stu-id="13d29-127">In the toolbar, click **Tiles View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="13d29-128"> Se viene visualizzato solo **Visualizzazione Dettagli**, ci si trova già in **Visualizzazione Affiancata**.</span><span class="sxs-lookup"><span data-stu-id="13d29-128">If you see only **Details View**, you are already in **Tiles View**.</span></span>  
  
3.  <span data-ttu-id="13d29-129">Passare con il puntatore del mouse su un elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="13d29-129">Hover over an item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="13d29-130">Nel menu a discesa fare clic su **Sposta**.</span><span class="sxs-lookup"><span data-stu-id="13d29-130">In the drop-down menu, click **Move**.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-general-properties-page-of-an-item"></a><span data-ttu-id="13d29-131">Per aprire la pagina di spostamento degli elementi dalla pagina delle proprietà Generale di un elemento</span><span class="sxs-lookup"><span data-stu-id="13d29-131">To open the Move Items page from the General Properties page of an item</span></span>  
  
1.  <span data-ttu-id="13d29-132">Aprire Gestione report e navigare fino alla cartella che contiene l'elemento che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="13d29-132">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="13d29-133">È possibile spostare anche elementi dalla home page di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="13d29-133">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="13d29-134">Passare con il puntatore del mouse su un elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="13d29-134">Hover over an item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="13d29-135">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="13d29-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="13d29-136">Viene visualizzata la pagina delle proprietà Generale per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="13d29-136">This opens the General properties page for an item.</span></span>  
  
4.  <span data-ttu-id="13d29-137">Sulla barra degli strumenti dell'elemento, fare clic su **Sposta**.</span><span class="sxs-lookup"><span data-stu-id="13d29-137">In the item toolbar, click **Move**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d29-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13d29-138">See Also</span></span>  
 <span data-ttu-id="13d29-139">[Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="13d29-139">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="13d29-140">[Pagina delle proprietà generale, cartelle &#40;Gestione report&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="13d29-140">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="13d29-141">[Pagina delle proprietà generale, report &#40;Gestione report&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="13d29-141">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="13d29-142">[Pagina delle proprietà generale, risorse &#40;Gestione report&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="13d29-142">[General Properties Page, Resources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span></span>  
 <span data-ttu-id="13d29-143">[Pagina delle proprietà generale, origini dati condivise &#40;Gestione report&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="13d29-143">[General Properties Page, Shared Data Sources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span></span>  
 [<span data-ttu-id="13d29-144">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="13d29-144">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
