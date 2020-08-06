---
title: Visualizzare un elenco di file modificati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckinWindow
helpviewer_keywords:
- listing modified files
- modified files list [SQL Server]
- checking in files
ms.assetid: 1b053719-8500-4300-a169-fffca5801dd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a2899ab9889908089d17b3c929e7bf4b2dfe2185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635715"
---
# <a name="view-a-list-of-modified-files"></a><span data-ttu-id="24a54-102">Visualizzazione di un elenco di file modificati</span><span class="sxs-lookup"><span data-stu-id="24a54-102">View a List of Modified Files</span></span>
  <span data-ttu-id="24a54-103">È possibile utilizzare la finestra **archiviazioni in sospeso** per visualizzare in qualsiasi momento un elenco dei file estratti nella soluzione corrente e per archiviare questi file con un solo clic del mouse.</span><span class="sxs-lookup"><span data-stu-id="24a54-103">You can use the **Pending Checkins** window to display at all times a list of the checked-out files in the current solution, and to check in these files with a single button click.</span></span>  
  
### <a name="to-view-a-list-of-modified-files"></a><span data-ttu-id="24a54-104">Per visualizzare un elenco di file modificati</span><span class="sxs-lookup"><span data-stu-id="24a54-104">To view a list of modified files</span></span>  
  
1.  <span data-ttu-id="24a54-105">Scegliere **archiviazioni in sospeso**dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="24a54-105">On the **View** menu, click **Pending Checkins**.</span></span>  
  
2.  <span data-ttu-id="24a54-106">Per archiviare i file selezionati, fare clic su **Archivia**.</span><span class="sxs-lookup"><span data-stu-id="24a54-106">To check in the selected files, click **Check In**.</span></span> <span data-ttu-id="24a54-107">In alternativa, è possibile ancorare la finestra **archiviazioni in sospeso** sul lato destro dell'ambiente in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] modo da poter archiviare i file al termine del lavoro.</span><span class="sxs-lookup"><span data-stu-id="24a54-107">Alternatively, you can dock the **Pending Checkins** window on the right side of the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment so that you can check in the files when you are finished working.</span></span>  
  
     <span data-ttu-id="24a54-108">**Archivia**</span><span class="sxs-lookup"><span data-stu-id="24a54-108">**Check In**</span></span>  
     <span data-ttu-id="24a54-109">Consente di eseguire l'archiviazione della soluzione.</span><span class="sxs-lookup"><span data-stu-id="24a54-109">Checks in the solution.</span></span>  
  
     <span data-ttu-id="24a54-110">**Commenti**</span><span class="sxs-lookup"><span data-stu-id="24a54-110">**Comments**</span></span>  
     <span data-ttu-id="24a54-111">Consente di associare un commento in formato testo normale all'archiviazione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="24a54-111">Associates a plain text comment with the pending check in.</span></span> <span data-ttu-id="24a54-112">Viene creato un commento che viene associato a ogni versione di un progetto e memorizzato nel database del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="24a54-112">A comment is created and associated with each version of a project, and stored in the source control database.</span></span>  
  
     <span data-ttu-id="24a54-113">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="24a54-113">**Options**</span></span>  
     <span data-ttu-id="24a54-114">Specifica le azioni che devono essere eseguite dal controllo del codice sorgente quando si fa clic sul pulsante **Archivia** .</span><span class="sxs-lookup"><span data-stu-id="24a54-114">Specifies the actions that source control should take when you click the **Check In** button.</span></span>  
  
    -   <span data-ttu-id="24a54-115">**Mantieni tutte le versioni estratte**</span><span class="sxs-lookup"><span data-stu-id="24a54-115">**Keep All Checked Out**</span></span>  
  
         <span data-ttu-id="24a54-116">Consente di specificare che le modifiche devono essere scritte nel provider del controllo del codice sorgente, ma che i file devono rimanere estratti.</span><span class="sxs-lookup"><span data-stu-id="24a54-116">Specifies that your changes should be written to the source control provider but that the files should remain checked out.</span></span>  
  
     <span data-ttu-id="24a54-117">**Sort**</span><span class="sxs-lookup"><span data-stu-id="24a54-117">**Sort**</span></span>  
     <span data-ttu-id="24a54-118">Consente di specificare il tipo di ordinamento per le colonne visualizzate nell'elenco Elementi.</span><span class="sxs-lookup"><span data-stu-id="24a54-118">Specifies the sort order for the columns displayed in the Items list.</span></span>  
  
     <span data-ttu-id="24a54-119">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="24a54-119">**Columns**</span></span>  
     <span data-ttu-id="24a54-120">Consente di visualizzare un elenco delle colonne che è possibile aggiungere all'elenco Elementi della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="24a54-120">Displays a list of the columns you can add to the window's Items list.</span></span>  
  
     <span data-ttu-id="24a54-121">**Visualizzazione albero**</span><span class="sxs-lookup"><span data-stu-id="24a54-121">**Tree View**</span></span>  
     <span data-ttu-id="24a54-122">Consente di visualizzare la gerarchia di cartelle e di file per la soluzione o il progetto che si sta archiviando.</span><span class="sxs-lookup"><span data-stu-id="24a54-122">Displays the folder and file hierarchy for the solution or project you are checking in.</span></span>  
  
     <span data-ttu-id="24a54-123">**Visualizzazione semplice**</span><span class="sxs-lookup"><span data-stu-id="24a54-123">**Flat View**</span></span>  
     <span data-ttu-id="24a54-124">Consente di visualizzare i file in corso di archiviazione come elenchi semplici sotto la relativa connessione del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="24a54-124">Displays the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="24a54-125">**Confronta versioni**</span><span class="sxs-lookup"><span data-stu-id="24a54-125">**Compare Versions**</span></span>  
     <span data-ttu-id="24a54-126">Consente di aprire la finestra di dialogo **Opzioni differenze** Visual SourceSafe, che consente di confrontare un file selezionato nel progetto dell'ambiente di sviluppo con qualsiasi altro file selezionato e di visualizzare le eventuali differenze.</span><span class="sxs-lookup"><span data-stu-id="24a54-126">Opens the Visual SourceSafe **Difference Options** dialog box, which compares a selected file in your development environment project to any other selected file and shows you the differences, if any.</span></span>  
  
     <span data-ttu-id="24a54-127">**Annulla estrazione**</span><span class="sxs-lookup"><span data-stu-id="24a54-127">**Undo checkout**</span></span>  
     <span data-ttu-id="24a54-128">Inverte l'estrazione di tutti gli elementi selezionati nella finestra **archiviazioni in sospeso** .</span><span class="sxs-lookup"><span data-stu-id="24a54-128">Reverses the checkout of all items selected in the **Pending Checkins** window.</span></span>  
  
     <span data-ttu-id="24a54-129">**Nome**</span><span class="sxs-lookup"><span data-stu-id="24a54-129">**Name**</span></span>  
     <span data-ttu-id="24a54-130">Consente di visualizzare un elenco degli elementi disponibili per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="24a54-130">Displays a list of the items available for check in.</span></span> <span data-ttu-id="24a54-131">Accanto a ciascun elemento viene visualizzata la casella di controllo selezionata.</span><span class="sxs-lookup"><span data-stu-id="24a54-131">Items appear with the check box next to them selected.</span></span> <span data-ttu-id="24a54-132">Se non si desidera archiviare un determinato elemento, deselezionare la relativa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="24a54-132">If you do not want to check in a particular item, clear the check box next to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a54-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24a54-133">See Also</span></span>  
 <span data-ttu-id="24a54-134">[Gestisci archiviazioni](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="24a54-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="24a54-135">Gestione delle estrazioni</span><span class="sxs-lookup"><span data-stu-id="24a54-135">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
