---
title: Specificare una versione come ultima versione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], latest version
- latest file version specified
- file versions [SQL Server]
ms.assetid: 407dffb1-3ecf-461e-835d-124781f26ee7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: dafe4f757e33a5db63340c3d3cc7c9151871d438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624322"
---
# <a name="specify-a-version-as-the-latest-version"></a><span data-ttu-id="e8032-102">Specifica di una versione come ultima versione</span><span class="sxs-lookup"><span data-stu-id="e8032-102">Specify a Version as the Latest Version</span></span>
  <span data-ttu-id="e8032-103">Quando un file viene archiviato nel controllo del codice sorgente, l'ultima versione diventa quella archiviata. Gli utenti che la estraggono o la recuperano ricevono copie locali dell'elemento archiviato più di recente.</span><span class="sxs-lookup"><span data-stu-id="e8032-103">When you check a file into source control, the version you check in becomes the latest version; users who check out or retrieve the latest version receive local copies of the item most recently checked in.</span></span>  
  
 <span data-ttu-id="e8032-104">In alcune situazioni, tuttavia, potrebbe essere necessario designare come ultima una versione precedente di un elemento.</span><span class="sxs-lookup"><span data-stu-id="e8032-104">However, in some situations, you may want to designate an earlier version of an item as the latest version.</span></span> <span data-ttu-id="e8032-105">Ad esempio, si estrae, si modifica e quindi si archivia il file.</span><span class="sxs-lookup"><span data-stu-id="e8032-105">For example, you check out a file, modify the file, and then check the file in.</span></span> <span data-ttu-id="e8032-106">In un secondo momento si decide di rimuovere le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e8032-106">You later decide to discard your modifications.</span></span> <span data-ttu-id="e8032-107">Dal momento che il file è stato archiviato, non è possibile annullare l'estrazione originale.</span><span class="sxs-lookup"><span data-stu-id="e8032-107">Because you have checked in the item, undoing your original checkout is not an option.</span></span> <span data-ttu-id="e8032-108">In questo caso è possibile impostare la versione estratta originariamente come ultima versione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e8032-108">In this situation, you can designate the version you originally checked out as the latest version of the item.</span></span>  
  
 <span data-ttu-id="e8032-109">Per impostare l'ultima versione:</span><span class="sxs-lookup"><span data-stu-id="e8032-109">You can designate the latest version by:</span></span>  
  
-   <span data-ttu-id="e8032-110">**Aggiunta di una versione**.</span><span class="sxs-lookup"><span data-stu-id="e8032-110">**Pinning a version**.</span></span> <span data-ttu-id="e8032-111">Quando si blocca una versione del file, le versioni più recenti di quella bloccata non vengono eliminate.</span><span class="sxs-lookup"><span data-stu-id="e8032-111">When you pin a file version, versions that are more recent than the pinned version are not deleted.</span></span> <span data-ttu-id="e8032-112">È inoltre possibile sbloccare un file bloccato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e8032-112">In addition, you can unpin a file that you have previously pinned.</span></span> <span data-ttu-id="e8032-113">In questo caso, l'ultima versione del file sarà quella archiviata più di recente.</span><span class="sxs-lookup"><span data-stu-id="e8032-113">When you do this, the most recently checked in version of the file becomes the latest version.</span></span> <span data-ttu-id="e8032-114">Non è tuttavia possibile estrarre un file bloccato.</span><span class="sxs-lookup"><span data-stu-id="e8032-114">However, you cannot check out a pinned file.</span></span>  
  
-   <span data-ttu-id="e8032-115">**Rollback a una versione specificata**.</span><span class="sxs-lookup"><span data-stu-id="e8032-115">**Rolling back to a specified version**.</span></span> <span data-ttu-id="e8032-116">Quando viene eseguito il ripristino di una versione, tutte le versioni più recenti di quella ripristinata verranno eliminate dal controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e8032-116">When you roll back to a version, all versions more recent than the one to which you have rolled back are deleted from source control.</span></span> <span data-ttu-id="e8032-117">È possibile quindi estrarre l'ultima versione rimanente.</span><span class="sxs-lookup"><span data-stu-id="e8032-117">You can then check out the latest remaining version.</span></span>  
  
### <a name="to-pin-a-version"></a><span data-ttu-id="e8032-118">Per bloccare una versione</span><span class="sxs-lookup"><span data-stu-id="e8032-118">To pin a version</span></span>  
  
1.  <span data-ttu-id="e8032-119">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] aprire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="e8032-119">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="e8032-120">In Esplora soluzioni selezionare il file che si desidera specificare come ultima versione.</span><span class="sxs-lookup"><span data-stu-id="e8032-120">In Solution Explorer, select the file that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="e8032-121">Scegliere **controllo del codice sorgente** dal menu **file** e fare clic su **ViewHistory**.</span><span class="sxs-lookup"><span data-stu-id="e8032-121">On the **File** menu, point to **Source Control** and click **ViewHistory**.</span></span>  
  
4.  <span data-ttu-id="e8032-122">Nella finestra **di dialogo cronologia di** \<file> selezionare la versione che si desidera specificare come ultima e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e8032-122">In the **History of** \<file> dialog box, select the version that you want to specify as the latest, and click **Pin**.</span></span>  
  
     <span data-ttu-id="e8032-123">Accanto alla versione selezionata viene visualizzato un simbolo di blocco per indicare che si tratta della versione corrente del file.</span><span class="sxs-lookup"><span data-stu-id="e8032-123">A pin symbol appears next to the version you have selected, indicating that it is the current file version.</span></span> <span data-ttu-id="e8032-124">Se in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] è caricata una versione diversa, viene chiesto di ricaricare il file.</span><span class="sxs-lookup"><span data-stu-id="e8032-124">If you have a different version loaded in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you are prompted to reload the file.</span></span>  
  
### <a name="to-roll-back-to-a-version"></a><span data-ttu-id="e8032-125">Per ripristinare una versione</span><span class="sxs-lookup"><span data-stu-id="e8032-125">To roll back to a version</span></span>  
  
1.  <span data-ttu-id="e8032-126">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] aprire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="e8032-126">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="e8032-127">In Esplora soluzioni selezionare l'elemento che si desidera specificare come ultima versione.</span><span class="sxs-lookup"><span data-stu-id="e8032-127">In Solution Explorer, select the item that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="e8032-128">Scegliere **controllo del codice sorgente** dal menu **file** e fare clic su **cronologia**.</span><span class="sxs-lookup"><span data-stu-id="e8032-128">On the **File** menu, point to **Source Control** and click **History**.</span></span>  
  
4.  <span data-ttu-id="e8032-129">Nella finestra di dialogo **Opzioni cronologia** fare clic su **OK** per visualizzare la finestra **di dialogo Cronologia file** .</span><span class="sxs-lookup"><span data-stu-id="e8032-129">In the **History Options** dialog box, click **OK** to display the **History of File** dialog box.</span></span>  
  
5.  <span data-ttu-id="e8032-130">Nella casella **cronologia del file** selezionare la versione che si desidera specificare come ultima versione, quindi fare clic su **rollback**.</span><span class="sxs-lookup"><span data-stu-id="e8032-130">In the **History of File** box, select the version you want to specify as the latest version, and click **Rollback**.</span></span>  
  
     <span data-ttu-id="e8032-131">Verrà visualizzato un messaggio che informa che tutte le versioni successive a quella selezionata verranno eliminate.</span><span class="sxs-lookup"><span data-stu-id="e8032-131">A message appears notifying you that all versions subsequent to the one you have selected will be deleted.</span></span>  
  
6.  <span data-ttu-id="e8032-132">Fare clic su **Sì** per eseguire il rollback alla versione selezionata.</span><span class="sxs-lookup"><span data-stu-id="e8032-132">Click **Yes** to roll back to the selected version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8032-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8032-133">See Also</span></span>  
 <span data-ttu-id="e8032-134">[Gestisci archiviazioni](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="e8032-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="e8032-135">Archiviazione di file</span><span class="sxs-lookup"><span data-stu-id="e8032-135">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)  
  
  
