---
title: Sequenza temporale di backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.POINTINTIMERESTORE.F1
- sql12.swb.backuptimeline.f1
helpviewer_keywords:
- Backup Timeline
ms.assetid: ae3565f2-ddb2-4469-a992-7531d4f9ebb8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b075f8c9ec32cfe483c64e34e9f9b4e4b6e80e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637938"
---
# <a name="backup-timeline"></a><span data-ttu-id="078bd-102">Sequenza temporale backup</span><span class="sxs-lookup"><span data-stu-id="078bd-102">Backup Timeline</span></span>
  <span data-ttu-id="078bd-103">Usare la finestra di dialogo **Cronologia di backup** per trovare e specificare backup ed eseguire il ripristino temporizzato di un database.</span><span class="sxs-lookup"><span data-stu-id="078bd-103">Use the **Backup Timeline** dialog box to locate and specify backups to restore a database to a point-in-time.</span></span> <span data-ttu-id="078bd-104">Per accedere alla finestra di dialogo **Cronologia di backup** , fare clic su **Cronologia** nel riquadro **Ripristina database (pagina Generale)** .</span><span class="sxs-lookup"><span data-stu-id="078bd-104">The **Backup Timeline** dialog box is accessed by clicking **Timeline** on the **Restore Database (General Page)** pane.</span></span> <span data-ttu-id="078bd-105">In questa finestra di dialogo è possibile visualizzare una cronologia delle operazioni di ripristino effettuate nel database.</span><span class="sxs-lookup"><span data-stu-id="078bd-105">This dialog box allows you to view a timeline of the restore operations performed on the database.</span></span>  
  
 <span data-ttu-id="078bd-106">Tramite Database Recovery Advisor viene assicurato che vengano selezionati solo i backup necessari per il ripristino a questa temporizzazione.</span><span class="sxs-lookup"><span data-stu-id="078bd-106">The Database Recovery Advisor ensures that only backups that are required for restoring to that point in time are selected.</span></span> <span data-ttu-id="078bd-107">Questi backup selezionati costituiscono il piano di ripristino consigliato per l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="078bd-107">These selected backups make up the recommended restore plan for your restore operation.</span></span> <span data-ttu-id="078bd-108">È consigliabile utilizzare solo i backup selezionati.</span><span class="sxs-lookup"><span data-stu-id="078bd-108">You should use only the selected backups.</span></span> <span data-ttu-id="078bd-109">Per informazioni su Database Recovery Advisor, vedere [Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="078bd-109">For information about the Database Recovery Advisor, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
## <a name="restore-to"></a><span data-ttu-id="078bd-110">Ripristina fino a</span><span class="sxs-lookup"><span data-stu-id="078bd-110">Restore to</span></span>  
 <span data-ttu-id="078bd-111">L'opzione**Ultimo backup eseguito** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="078bd-111">**Last backup taken** is selected by default.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="078bd-112">selezionerà i backup appropriati per il ripristino del database, che verrà ripristinato nel punto dell'ultimo backup.</span><span class="sxs-lookup"><span data-stu-id="078bd-112">will select the appropriate backups to restore the database, and will restore the database to the point of the last backup.</span></span> <span data-ttu-id="078bd-113">Fare clic su **Data e ora specifiche** per impostare manualmente la data e l'ora (selezionando un punto nel tempo specifico).</span><span class="sxs-lookup"><span data-stu-id="078bd-113">Click **A specific date and time** to manually set the date and time (selecting a specific point in time).</span></span>  
  
 <span data-ttu-id="078bd-114">Attraverso**Data e ora specifiche** è possibile arrestare il ripristino a una data e un'ora specifiche selezionate.</span><span class="sxs-lookup"><span data-stu-id="078bd-114">**Specific date and time** permits you stop the restore at a specific date and time that you select.</span></span> <span data-ttu-id="078bd-115">La cronologia mostra una rappresentazione delle operazioni di backup eseguite nelle 24 ore prossime alla data e all'ora selezionate.</span><span class="sxs-lookup"><span data-stu-id="078bd-115">The timeline shows a representation of the backup operations performed in the 24 hours around the select date and time.</span></span>  
  
 <span data-ttu-id="078bd-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="078bd-116">**Date**</span></span>  
 <span data-ttu-id="078bd-117">Immettere o selezionare una data dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="078bd-117">Enter or select a date from the drop-down list.</span></span>  
  
 <span data-ttu-id="078bd-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="078bd-118">**Time**</span></span>  
 <span data-ttu-id="078bd-119">Immettere o selezionare una data per definire il punto specifico per l'arresto del ripristino.</span><span class="sxs-lookup"><span data-stu-id="078bd-119">Enter or select a date to designate the specific point-in-time for the restore to stop.</span></span>  
  
 <span data-ttu-id="078bd-120">**Intervallo temporale**</span><span class="sxs-lookup"><span data-stu-id="078bd-120">**Timeline Interval**</span></span>  
 <span data-ttu-id="078bd-121">Consente di visualizzare le opzioni per i tipi di intervallo visualizzabili all'interno della sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="078bd-121">Displays the options for the interval types viewable on the timeline.</span></span>  
  
## <a name="timeline-and-legend"></a><span data-ttu-id="078bd-122">Cronologia e legenda</span><span class="sxs-lookup"><span data-stu-id="078bd-122">Timeline and Legend</span></span>  
 <span data-ttu-id="078bd-123">Utilizzare la barra di scorrimento sotto la cronologia per spostare il cursore avanti e indietro lungo la sequenza temporale.</span><span class="sxs-lookup"><span data-stu-id="078bd-123">Use the scroll bar beneath the timeline to move the cursor forward and backward along the timeline.</span></span> <span data-ttu-id="078bd-124">Fare clic su un backup per spostare la barra di scorrimento alla fine del backup selezionato.</span><span class="sxs-lookup"><span data-stu-id="078bd-124">Click on a backup to move the scroll bar to the end of that backup.</span></span> <span data-ttu-id="078bd-125">Posizionare il mouse su un marcatore per visualizzare una Descrizione comandi che fornisce informazioni sul set di backup selezionato.</span><span class="sxs-lookup"><span data-stu-id="078bd-125">Hover the mouse over a marker to display a ScreenTip providing information about the selected backup set.</span></span> <span data-ttu-id="078bd-126">Le informazioni sul backup vengono mostrate all'interno della cronologia tramite i seguenti marcatori.</span><span class="sxs-lookup"><span data-stu-id="078bd-126">Backup information is shown on the timeline by the following markers.</span></span>  
  
 <span data-ttu-id="078bd-127">Triangolo di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="078bd-127">Larger triangle</span></span>  
 <span data-ttu-id="078bd-128">Rappresenta i backup completi eseguiti nel database e indica il momento specifico in cui è stato eseguito ogni backup completo.</span><span class="sxs-lookup"><span data-stu-id="078bd-128">Represents the full backups performed on the database, denoting the specific point in time each full backup was performed.</span></span>  
  
 <span data-ttu-id="078bd-129">Triangolo di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="078bd-129">Smaller triangle</span></span>  
 <span data-ttu-id="078bd-130">Rappresenta i backup differenziali eseguiti nel database e indica il momento specifico in cui è stato eseguito ogni backup differenziale.</span><span class="sxs-lookup"><span data-stu-id="078bd-130">Represents the differential backups performed on the database, denoting the specific point in time that each differential backup was performed.</span></span>  
  
 <span data-ttu-id="078bd-131">Aree verdi ombreggiate</span><span class="sxs-lookup"><span data-stu-id="078bd-131">Green shaded areas</span></span>  
 <span data-ttu-id="078bd-132">Rappresentano la copertura del backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="078bd-132">Represents the transaction log backup coverage.</span></span>  
  
 <span data-ttu-id="078bd-133">Linea rossa</span><span class="sxs-lookup"><span data-stu-id="078bd-133">Red line</span></span>  
 <span data-ttu-id="078bd-134">Può essere posizionata lungo la cronologia solo nel punto in cui è possibile effettuare il ripristino.</span><span class="sxs-lookup"><span data-stu-id="078bd-134">Can only be positioned along the timeline where the restore is possible.</span></span> <span data-ttu-id="078bd-135">Spostando la linea rossa lungo la cronologia, è possibile regolare data e ora visualizzate nelle caselle **Data** e **Ora** .</span><span class="sxs-lookup"><span data-stu-id="078bd-135">Moving the red line along the timeline adjusts the date and time displayed in the **Date** and **Time** boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="078bd-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="078bd-136">See Also</span></span>  
 [<span data-ttu-id="078bd-137">Ripristina database &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="078bd-137">Restore Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
  
