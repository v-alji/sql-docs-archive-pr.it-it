---
title: MSSQLSERVER_824 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
ms.assetid: 2aa22246-2712-4fdb-9744-36e7e6f3175e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d57b19bc8c837b92b65728fbb0046039b862d31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628697"
---
# <a name="mssqlserver_824"></a><span data-ttu-id="cd4a8-102">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="cd4a8-102">MSSQLSERVER_824</span></span>
    
## <a name="details"></a><span data-ttu-id="cd4a8-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cd4a8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd4a8-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="cd4a8-104">Product Name</span></span>|<span data-ttu-id="cd4a8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cd4a8-105">SQL Server</span></span>|  
|<span data-ttu-id="cd4a8-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="cd4a8-106">Event ID</span></span>|<span data-ttu-id="cd4a8-107">824</span><span class="sxs-lookup"><span data-stu-id="cd4a8-107">824</span></span>|  
|<span data-ttu-id="cd4a8-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="cd4a8-108">Event Source</span></span>|<span data-ttu-id="cd4a8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cd4a8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cd4a8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cd4a8-110">Component</span></span>|<span data-ttu-id="cd4a8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cd4a8-111">SQLEngine</span></span>|  
|<span data-ttu-id="cd4a8-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="cd4a8-112">Symbolic Name</span></span>|<span data-ttu-id="cd4a8-113">B_HARDSSERR</span><span class="sxs-lookup"><span data-stu-id="cd4a8-113">B_HARDSSERR</span></span>|  
|<span data-ttu-id="cd4a8-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="cd4a8-114">Message Text</span></span>|<span data-ttu-id="cd4a8-115">SQL Server ha rilevato un errore di I/O logico legato alla consistenza. Errore %1!s!</span><span class="sxs-lookup"><span data-stu-id="cd4a8-115">SQL Server detected a logical consistency-based I/O error: %ls.</span></span> <span data-ttu-id="cd4a8-116">durante un'operazione di %S_MSG della pagina %S_PGID nel database con ID %d all'offset %#016I64x nel file '%ls'.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-116">It occurred during a %S_MSG of page %S_PGID in database ID %d at offset %#016I64x in file '%ls'.</span></span>  <span data-ttu-id="cd4a8-117">Per informazioni più dettagliate, vedere i messaggi aggiuntivi nel log degli errori di SQL Server e nel registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-117">Additional messages in the SQL Server error log or system event log may provide more detail.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cd4a8-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="cd4a8-118">Explanation</span></span>  
 <span data-ttu-id="cd4a8-119">Questo errore indica che, sebbene Windows segnali che la pagina è stata correttamente letta dal disco, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha individuato un errore nella pagina.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-119">This error indicates that Windows reports that the page is successfully read from disk, but [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has discovered something wrong with the page.</span></span> <span data-ttu-id="cd4a8-120">Questo errore è simile all'errore 823, con la sola differenza che Windows non ha rilevato l'errore.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-120">This error is similar to error 823 except that Windows did not detect the error.</span></span> <span data-ttu-id="cd4a8-121">Indica in genere un problema relativo al sottosistema di I/O, ad esempio un'unità disco danneggiata, problemi relativi al firmware del disco, un driver di dispositivo difettoso e così via.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-121">This usually indicates a problem in the I/O subsystem, such as a failing disk drive, disk firmware problems, faulty device driver, and so on.</span></span> <span data-ttu-id="cd4a8-122">Per altre informazioni sugli errori di I/O, vedere il capitolo 2 della pagina relativa alle [nozioni fondamentali sull'I/O in Microsoft SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="cd4a8-122">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd4a8-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="cd4a8-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="cd4a8-124">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="cd4a8-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="cd4a8-125">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="cd4a8-126">Esaminare inoltre il registro di sistema e il registro applicazioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred because of hardware failure.</span></span> <span data-ttu-id="cd4a8-127">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="cd4a8-128">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="cd4a8-129">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="cd4a8-130">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="cd4a8-131">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="cd4a8-132">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="cd4a8-133">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="cd4a8-133">Restore from Backup</span></span>  
 <span data-ttu-id="cd4a8-134">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-134">If the problem is not hardware-related and a known clean backup is available, restore the database from the backup.</span></span>  
  
 <span data-ttu-id="cd4a8-135">Provare a cambiare i database per utilizzare l'opzione PAGE_VERIFY CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-135">Consider changing the databases to use the PAGE_VERIFY CHECKSUM option.</span></span> <span data-ttu-id="cd4a8-136">Per informazioni su PAGE_VERIFY, vedere [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cd4a8-136">For information about PAGE_VERIFY, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4a8-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd4a8-137">See Also</span></span>  
 [<span data-ttu-id="cd4a8-138">Gestione della tabella suspect_pages &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cd4a8-138">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
