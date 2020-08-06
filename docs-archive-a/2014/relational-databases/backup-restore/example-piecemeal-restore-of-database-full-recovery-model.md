---
title: 'Esempio: Ripristino a fasi di un database (modello di recupero con registrazione completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- piecemeal restores [SQL Server], full recovery model
- restore sequences [SQL Server], piecemeal
ms.assetid: 0a84892d-2f7a-4e77-b2d0-d68b95595210
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfccccdbdc0c4fb3b189ee0a9fa3aeaf426578b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720099"
---
# <a name="example-piecemeal-restore-of-database-full-recovery-model"></a><span data-ttu-id="7b25e-102">Esempio: Ripristino a fasi di un database (modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="7b25e-102">Example: Piecemeal Restore of Database (Full Recovery Model)</span></span>
  <span data-ttu-id="7b25e-103">Con una sequenza di ripristino a fasi, il database viene ripristinato e recuperato in varie fasi a livello di filegroup, partendo dal filegroup primario e da tutti i filegroup secondari in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="7b25e-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read-write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="7b25e-104">In questo esempio il database `adb` viene ripristinato in un nuovo computer dopo un'emergenza.</span><span class="sxs-lookup"><span data-stu-id="7b25e-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="7b25e-105">Dato che il database utilizza il modello di recupero con registrazione completa, prima dell'avvio del ripristino è necessario eseguire un backup della parte finale del log per il database.</span><span class="sxs-lookup"><span data-stu-id="7b25e-105">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="7b25e-106">Prima dell'emergenza, tutti i filegroup erano online.</span><span class="sxs-lookup"><span data-stu-id="7b25e-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="7b25e-107">Il filegroup `B` è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="7b25e-107">Filegroup `B` is read-only.</span></span> <span data-ttu-id="7b25e-108">Tutti i filegroup secondari devono essere ripristinati, ma il ripristino avviene in ordine di importanza: `A` (importanza massima), `C`e infine `B`.</span><span class="sxs-lookup"><span data-stu-id="7b25e-108">All of the secondary filegroups must be restored, but they are restored in order of importance: `A` (highest), `C`, and lastly `B`.</span></span> <span data-ttu-id="7b25e-109">In questo esempio sono presenti quattro backup dei log, incluso il backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="7b25e-109">In this example, there are four log backups, including the tail-log backup.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="7b25e-110">Backup della parte finale del log</span><span class="sxs-lookup"><span data-stu-id="7b25e-110">Tail-Log Backup</span></span>  
 <span data-ttu-id="7b25e-111">Prima di ripristinare il database, è necessario che l'amministratore del database esegua il backup della parte finale del log.</span><span class="sxs-lookup"><span data-stu-id="7b25e-111">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="7b25e-112">Dato che il database è danneggiato, la creazione di tale backup richiede l'utilizzo dell'opzione NO_TRUNCATE:</span><span class="sxs-lookup"><span data-stu-id="7b25e-112">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="7b25e-113">Il backup della parte finale del log è l'ultimo backup applicato nelle sequenze di ripristino seguenti.</span><span class="sxs-lookup"><span data-stu-id="7b25e-113">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="7b25e-114">Sequenze di ripristino</span><span class="sxs-lookup"><span data-stu-id="7b25e-114">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b25e-115">La sintassi di una sequenza di ripristino online è la stessa di una sequenza di ripristino offline.</span><span class="sxs-lookup"><span data-stu-id="7b25e-115">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="7b25e-116">Ripristino parziale del filegroup primario e secondario `A`.</span><span class="sxs-lookup"><span data-stu-id="7b25e-116">Partial restore of the primary and secondary filegroup `A`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
       WITH PARTIAL, NORECOVERY  
    RESTORE DATABASE adb FILEGROUP='A' FROM backup2   
       WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
2.  <span data-ttu-id="7b25e-117">Eseguire un ripristino online del filegroup `C`.</span><span class="sxs-lookup"><span data-stu-id="7b25e-117">Online restore of filegroup `C`.</span></span>  
  
     <span data-ttu-id="7b25e-118">A questo punto sono online il filegroup primario e il filegroup secondario `A` .</span><span class="sxs-lookup"><span data-stu-id="7b25e-118">At this point, the primary filegroup and secondary filegroup `A` are online.</span></span> <span data-ttu-id="7b25e-119">Il recupero di tutti i file nei filegroup `B` e `C` è in sospeso e i filegroup sono offline.</span><span class="sxs-lookup"><span data-stu-id="7b25e-119">All the files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
     <span data-ttu-id="7b25e-120">I messaggi relativi all'ultima istruzione `RESTORE LOG` nel passaggio 1 indicano che il rollback delle transazioni che interessano il filegroup `C` è stato posticipato, poiché tale filegroup non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="7b25e-120">Messages from the last `RESTORE LOG` statement in step 1 indicate that rollback of transactions that involve filegroup `C` was deferred, because this filegroup is not available.</span></span> <span data-ttu-id="7b25e-121">È possibile continuare a eseguire le normali operazioni, ma sono attivi blocchi da parte di queste transazioni e non sarà possibile eseguire il troncamento del log fino al completamento del rollback.</span><span class="sxs-lookup"><span data-stu-id="7b25e-121">Regular operations can continue, but locks are held by these transactions and log truncation will not occur until the rollback can complete.</span></span>  
  
     <span data-ttu-id="7b25e-122">Nella seconda sequenza di ripristino l'amministratore del database ripristina il filegroup `C`:</span><span class="sxs-lookup"><span data-stu-id="7b25e-122">In the second restore sequence, the database administrator restores filegroup `C`:</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' FROM backup2a WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="7b25e-123">A questo punto il filegroup primario e i filegroup `A` e `C` sono online.</span><span class="sxs-lookup"><span data-stu-id="7b25e-123">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="7b25e-124">Il recupero dei file nel filegroup `B` è ancora in sospeso e questo filegroup è offline.</span><span class="sxs-lookup"><span data-stu-id="7b25e-124">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span> <span data-ttu-id="7b25e-125">Le transazioni posticipate sono state risolte e si procede al troncamento del log.</span><span class="sxs-lookup"><span data-stu-id="7b25e-125">Deferred transactions have been resolved, and log truncation occurs.</span></span>  
  
3.  <span data-ttu-id="7b25e-126">Eseguire un ripristino online del filegroup `B`.</span><span class="sxs-lookup"><span data-stu-id="7b25e-126">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="7b25e-127">Nella terza sequenza di ripristino l'amministratore del database ripristina il filegroup `B`.</span><span class="sxs-lookup"><span data-stu-id="7b25e-127">In the third restore sequence, the database administrator restores filegroup `B`.</span></span> <span data-ttu-id="7b25e-128">Il backup del filegroup `B` è stato eseguito dopo la sua conversione in filegroup di sola lettura. Non è pertanto necessario eseguire il roll forward del filegroup durante il recupero.</span><span class="sxs-lookup"><span data-stu-id="7b25e-128">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, it does not have to be rolled forward during recovery.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup2b WITH RECOVERY  
    ```  
  
     <span data-ttu-id="7b25e-129">In questa fase tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="7b25e-129">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="7b25e-130">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="7b25e-130">Additional Examples</span></span>  
  
-   [<span data-ttu-id="7b25e-131">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="7b25e-131">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="7b25e-132">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="7b25e-132">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="7b25e-133">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="7b25e-133">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="7b25e-134">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="7b25e-134">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="7b25e-135">Esempio: Ripristino online di un file di lettura/scrittura &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="7b25e-135">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="7b25e-136">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="7b25e-136">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b25e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b25e-137">See Also</span></span>  
 <span data-ttu-id="7b25e-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b25e-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="7b25e-139">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7b25e-139">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="7b25e-140">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7b25e-140">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="7b25e-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7b25e-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="7b25e-142">Ripristini a fasi &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7b25e-142">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
