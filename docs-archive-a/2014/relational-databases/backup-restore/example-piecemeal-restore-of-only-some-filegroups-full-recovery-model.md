---
title: 'Esempio: Ripristino a fasi di filegroup selezionati (modello di recupero con registrazione completa) | Microsoft Docs'
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
ms.assetid: bced4b54-e819-472b-b784-c72e14e72a0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b3cb1a5ea33a5016c99fdf1f5a7f4e892c045b59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725999"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-full-recovery-model"></a><span data-ttu-id="e2190-102">Esempio: Ripristino a fasi di un numero limitato di filegroup (modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="e2190-102">Example: Piecemeal Restore of Only Some Filegroups (Full Recovery Model)</span></span>
  <span data-ttu-id="e2190-103">Le informazioni contenute in questo argomento interessano i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] basati sul modello di recupero con registrazione completa che includono più file o filegroup.</span><span class="sxs-lookup"><span data-stu-id="e2190-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="e2190-104">Una sequenza di ripristino a fasi consente di ripristinare e recuperare un database in varie fasi a livello di filegroup, a partire dal filegroup primario e tutti i filegroup secondari di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="e2190-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="e2190-105">In questo esempio un database denominato `adb`, che utilizza il modello di recupero con registrazione completa, contiene tre filegroup.</span><span class="sxs-lookup"><span data-stu-id="e2190-105">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="e2190-106">Il filegroup `A` è in lettura/scrittura, mentre i filegroup `B` e `C` sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="e2190-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="e2190-107">Inizialmente, tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="e2190-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="e2190-108">Il filegroup primario e il filegroup `B` del database `adb` risultano danneggiati.</span><span class="sxs-lookup"><span data-stu-id="e2190-108">The primary and filegroup `B` of database `adb` appear to be damaged.</span></span> <span data-ttu-id="e2190-109">Il filegroup primario è di dimensioni limitate ed è possibile ripristinarlo rapidamente.</span><span class="sxs-lookup"><span data-stu-id="e2190-109">The primary filegroup is fairly small and can be restored quickly.</span></span> <span data-ttu-id="e2190-110">L'amministratore del database decide di ripristinare i filegroup utilizzando una sequenza di ripristino a fasi.</span><span class="sxs-lookup"><span data-stu-id="e2190-110">The database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="e2190-111">Innanzitutto, il filegroup primario e i log delle transazioni successivi vengono ripristinati e il database recuperato.</span><span class="sxs-lookup"><span data-stu-id="e2190-111">First, the primary filegroup and the subsequent transaction logs are restored the database is recovered.</span></span>  
  
 <span data-ttu-id="e2190-112">I filegroup integri `A` e `C` includono dati di importanza critica.</span><span class="sxs-lookup"><span data-stu-id="e2190-112">The intact filegroups `A` and `C` contain critical data.</span></span> <span data-ttu-id="e2190-113">Verranno pertanto recuperati e resi disponibili online il più rapidamente possibile.</span><span class="sxs-lookup"><span data-stu-id="e2190-113">Therefore, they will be recovered next to bring them online as quickly as possible.</span></span> <span data-ttu-id="e2190-114">Infine, viene ripristinato e recuperato il filegroup secondario danneggiato `B`.</span><span class="sxs-lookup"><span data-stu-id="e2190-114">Finally, the damaged secondary filegroup, `B`, is restored and recovered.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="e2190-115">Sequenze di ripristino:</span><span class="sxs-lookup"><span data-stu-id="e2190-115">Restore Sequences:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2190-116">La sintassi di una sequenza di ripristino online è la stessa di una sequenza di ripristino offline.</span><span class="sxs-lookup"><span data-stu-id="e2190-116">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="e2190-117">Creare un backup della parte finale del log per il database `adb`.</span><span class="sxs-lookup"><span data-stu-id="e2190-117">Create a tail log backup of database `adb`.</span></span> <span data-ttu-id="e2190-118">Questo passaggio è fondamentale per fare in modo che i filegroup integri `A` e `C` vengano aggiornati rispetto al punto di recupero del database.</span><span class="sxs-lookup"><span data-stu-id="e2190-118">This step is essential to make the intact filegroups `A` and `C` current with the recovery point of the database.</span></span>  
  
    ```  
    BACKUP LOG adb TO tailLogBackup WITH NORECOVERY  
    ```  
  
2.  <span data-ttu-id="e2190-119">Eseguire un ripristino parziale del filegroup primario.</span><span class="sxs-lookup"><span data-stu-id="e2190-119">Partial restore of the primary filegroup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup   
    WITH PARTIAL, NORECOVERY  
    RESTORE LOG adb FROM backup1 WITH NORECOVERY  
    RESTORE LOG adb FROM backup2 WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="e2190-120">In questa fase il filegroup primario è online.</span><span class="sxs-lookup"><span data-stu-id="e2190-120">At this point the primary is online.</span></span> <span data-ttu-id="e2190-121">Il recupero dei file nei filegroup `A`, `B`e `C` è in sospeso e questi filegroup sono offline.</span><span class="sxs-lookup"><span data-stu-id="e2190-121">Files in filegroups `A`, `B`, and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
3.  <span data-ttu-id="e2190-122">Eseguire un ripristino online dei filegroup `A` e `C`.</span><span class="sxs-lookup"><span data-stu-id="e2190-122">Online restore of filegroups `A` and `C`.</span></span>  
  
     <span data-ttu-id="e2190-123">Non è necessario ripristinare questi filegroup da un backup poiché i dati in essi contenuti non sono danneggiati, ma è necessario recuperarli per attivare la modalità online.</span><span class="sxs-lookup"><span data-stu-id="e2190-123">Because their data is undamaged, these filegroups do not have to be restored from a backup, but they do have to be recovered to bring them online.</span></span>  
  
     <span data-ttu-id="e2190-124">L'amministratore del database recupera `A` e `C` immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e2190-124">The database administrator recovers `A` and `C` immediately.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A', FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="e2190-125">A questo punto il filegroup primario e i filegroup `A` e `C` sono online.</span><span class="sxs-lookup"><span data-stu-id="e2190-125">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="e2190-126">Il recupero dei file nel filegroup `B` è ancora in sospeso e questo filegroup è offline.</span><span class="sxs-lookup"><span data-stu-id="e2190-126">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span>  
  
4.  <span data-ttu-id="e2190-127">Eseguire un ripristino online del filegroup `B`.</span><span class="sxs-lookup"><span data-stu-id="e2190-127">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="e2190-128">I file nel filegroup `B` vengono ripristinati in un qualsiasi momento successivo.</span><span class="sxs-lookup"><span data-stu-id="e2190-128">Files in filegroup `B` are restored any time thereafter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2190-129">Il backup del filegroup `B` è stato eseguito dopo che il filegroup è diventato di sola lettura, quindi non è necessario eseguire il roll forward di questi file.</span><span class="sxs-lookup"><span data-stu-id="e2190-129">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, these files do not have to be rolled forward.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="e2190-130">In questa fase tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="e2190-130">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="e2190-131">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="e2190-131">Additional Examples</span></span>  
  
-   [<span data-ttu-id="e2190-132">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="e2190-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="e2190-133">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="e2190-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="e2190-134">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="e2190-134">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="e2190-135">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="e2190-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="e2190-136">Esempio: Ripristino online di un file di lettura/scrittura &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="e2190-136">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="e2190-137">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="e2190-137">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2190-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2190-138">See Also</span></span>  
 <span data-ttu-id="e2190-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e2190-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="e2190-140">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e2190-140">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="e2190-141">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e2190-141">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="e2190-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e2190-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="e2190-143">Ripristini a fasi &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e2190-143">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
