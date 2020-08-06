---
title: 'Esempio: Ripristino online di un file di lettura/scrittura (modello di recupero con registrazione completa) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- online restores [SQL Server], full recovery model
- restore sequences [SQL Server], online
ms.assetid: 0dbeda81-1464-44ba-9011-914900096368
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5b99a3d97644c2a5f104173457f30fc5b3fd7188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624777"
---
# <a name="example-online-restore-of-a-read-write-file-full-recovery-model"></a><span data-ttu-id="a015a-102">Esempio: Ripristino online di un file di lettura/scrittura (modello di recupero con registrazione completa)</span><span class="sxs-lookup"><span data-stu-id="a015a-102">Example: Online Restore of a Read-Write File (Full Recovery Model)</span></span>
  <span data-ttu-id="a015a-103">Le informazioni contenute in questo argomento interessano i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] basati sul modello di recupero con registrazione completa che includono più file o filegroup.</span><span class="sxs-lookup"><span data-stu-id="a015a-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="a015a-104">In questo esempio un database denominato `adb`, che utilizza il modello di recupero con registrazione completa, contiene tre filegroup.</span><span class="sxs-lookup"><span data-stu-id="a015a-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="a015a-105">Il filegroup `A` è in lettura/scrittura, mentre i filegroup `B` e `C` sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a015a-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="a015a-106">Inizialmente, tutti i filegroup sono online.</span><span class="sxs-lookup"><span data-stu-id="a015a-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="a015a-107">Il file `a1` del filegroup `A` è danneggiato e l'amministratore del database decide di ripristinarlo, mantenendo online il database.</span><span class="sxs-lookup"><span data-stu-id="a015a-107">File `a1` in filegroup `A` appears to be damaged, and the database administrator decides to restore it while the database remains online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a015a-108">Il modello di recupero con registrazione minima non consente il ripristino online di dati di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="a015a-108">Under the simple recovery model, online restore of read/write data is not allowed.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="a015a-109">Sequenze di ripristino</span><span class="sxs-lookup"><span data-stu-id="a015a-109">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a015a-110">La sintassi di una sequenza di ripristino online è la stessa di una sequenza di ripristino offline.</span><span class="sxs-lookup"><span data-stu-id="a015a-110">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="a015a-111">Ripristino in linea del file `a1`.</span><span class="sxs-lookup"><span data-stu-id="a015a-111">Online restore of file `a1`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILE='a1' FROM backup   
    WITH NORECOVERY;  
    ```  
  
     <span data-ttu-id="a015a-112">A questo punto lo stato del file a1 è RESTORING e il filegroup A è offline.</span><span class="sxs-lookup"><span data-stu-id="a015a-112">At this point, file a1 is in the RESTORING state, and filegroup A is offline.</span></span>  
  
2.  <span data-ttu-id="a015a-113">Al termine del ripristino del file, l'amministratore del database esegue un nuovo backup del log per garantire l'acquisizione del punto in cui il file è passato offline.</span><span class="sxs-lookup"><span data-stu-id="a015a-113">After restoring the file, the database administrator takes a new log backup to make sure that the point at which the file went offline is captured.</span></span>  
  
    ```  
    BACKUP LOG adb TO log_backup3;   
    ```  
  
3.  <span data-ttu-id="a015a-114">Ripristino online dei backup del log.</span><span class="sxs-lookup"><span data-stu-id="a015a-114">Online restore of log backups.</span></span>  
  
     <span data-ttu-id="a015a-115">L'amministratore ripristina tutti i backup del log a partire dal backup del file ripristinato fino all'ultimo backup del log (*log_backup3*, eseguito nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="a015a-115">The administrator restores all the log backups taken since the restored file backup, ending with the latest log backup (*log_backup3*, taken in step 2).</span></span> <span data-ttu-id="a015a-116">Una volta ripristinato l'ultimo backup, viene recuperato il database.</span><span class="sxs-lookup"><span data-stu-id="a015a-116">After the last backup is restored, the database is recovered.</span></span>  
  
    ```  
    RESTORE LOG adb FROM log_backup1 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup2 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup3 WITH NORECOVERY;  
    RESTORE LOG adb WITH RECOVERY;  
    ```  
  
     <span data-ttu-id="a015a-117">Il file `a1` è ora online.</span><span class="sxs-lookup"><span data-stu-id="a015a-117">File `a1` is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="a015a-118">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="a015a-118">Additional Examples</span></span>  
  
-   [<span data-ttu-id="a015a-119">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="a015a-119">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="a015a-120">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="a015a-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="a015a-121">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="a015a-121">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="a015a-122">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="a015a-122">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="a015a-123">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="a015a-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="a015a-124">Esempio: Ripristino online di un file di sola lettura &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="a015a-124">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="a015a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a015a-125">See Also</span></span>  
 <span data-ttu-id="a015a-126">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a015a-126">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="a015a-127">[Ripristini a fasi &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a015a-127">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="a015a-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a015a-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="a015a-129">[Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a015a-129">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="a015a-130">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a015a-130">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="a015a-131">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a015a-131">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
