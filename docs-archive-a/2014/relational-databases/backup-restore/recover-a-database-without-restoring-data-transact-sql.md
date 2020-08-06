---
title: Recuperare un database senza ripristino dei dati (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], recovery-only
- recovery-only scenario [SQL Server]
- restoring databases [SQL Server], recovery-only
- recovery [SQL Server], recovery-only
- database recovery [SQL Server]
- database restores [SQL Server], recovery-only
- recovery [SQL Server], without restoring data
ms.assetid: 7e8fa620-315d-4e10-a718-23fa5171c09e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 04e4f78e51adb803bb65530c0b3b903aa7f76419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635687"
---
# <a name="recover-a-database-without-restoring-data-transact-sql"></a><span data-ttu-id="cad73-102">Recupero di un database senza ripristino dei dati (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cad73-102">Recover a Database Without Restoring Data (Transact-SQL)</span></span>
  <span data-ttu-id="cad73-103">Generalmente, tutti i dati in un database [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono ripristinati prima che venga recuperato il database.</span><span class="sxs-lookup"><span data-stu-id="cad73-103">Usually, all of the data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is restored before the database is recovered.</span></span> <span data-ttu-id="cad73-104">È tuttavia possibile che un'operazione di ripristino recuperi il database senza ripristinare effettivamente un backup, ad esempio nel caso di recupero di un file di sola lettura compatibile con il database.</span><span class="sxs-lookup"><span data-stu-id="cad73-104">However, a restore operation can recover a database without actually restoring a backup; for example, when recovering a read-only file that is consistent with the database.</span></span> <span data-ttu-id="cad73-105">Questa operazione viene definita *ripristino con solo recupero*.</span><span class="sxs-lookup"><span data-stu-id="cad73-105">This is referred to as a *recovery-only restore*.</span></span> <span data-ttu-id="cad73-106">Quando i dati offline sono già compatibili con il database è necessario solo renderli disponibili; un'operazione di ripristino con solo recupero completa il recupero del database e porta i dati online.</span><span class="sxs-lookup"><span data-stu-id="cad73-106">When offline data is already consistent with the database and needs only to be made available, a recovery-only restore operation completes the recovery of the database and bring the data online.</span></span>  
  
 <span data-ttu-id="cad73-107">Un ripristino con solo recupero può essere eseguito per un intero database, per uno o più file o filegroup.</span><span class="sxs-lookup"><span data-stu-id="cad73-107">A recovery-only restore can occur for a whole database or for one or more a files or filegroups.</span></span>  
  
## <a name="recovery-only-database-restore"></a><span data-ttu-id="cad73-108">Ripristino del database con solo recupero</span><span class="sxs-lookup"><span data-stu-id="cad73-108">Recovery-Only Database Restore</span></span>  
 <span data-ttu-id="cad73-109">Un ripristino di database con solo recupero può risultare utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cad73-109">A recovery-only database restore can be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="cad73-110">Il database non è stato recuperato durante il ripristino dell'ultimo backup in una sequenza di ripristino e ora si desidera recuperare il database per attivare la modalità online.</span><span class="sxs-lookup"><span data-stu-id="cad73-110">You did not recover the database when restoring the last backup in a restore sequence, and you now want to recover the database to bring it online.</span></span>  
  
-   <span data-ttu-id="cad73-111">Il database è in modalità standby e si desidera renderlo aggiornabile senza applicare un ulteriore backup del log.</span><span class="sxs-lookup"><span data-stu-id="cad73-111">The database is in standby mode, and you want to make the database updatable without applying another log backup.</span></span>  
  
 <span data-ttu-id="cad73-112">La sintassi dell'istruzione [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) per un ripristino di database con solo recupero è la seguente:</span><span class="sxs-lookup"><span data-stu-id="cad73-112">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only database restore is as follows:</span></span>  
  
 <span data-ttu-id="cad73-113">RESTORE DATABASE *nome_database* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="cad73-113">RESTORE DATABASE *database_name* WITH RECOVERY</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cad73-114">La clausola FROM **=** \<*backup_device>\* non viene utilizzata per i ripristini con solo recupero perché non è necessario usare un backup.</span><span class="sxs-lookup"><span data-stu-id="cad73-114">The FROM **=** \<*backup_device>\* clause is not used for recovery-only restores because no backup is necessary.</span></span>  
  
 <span data-ttu-id="cad73-115">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cad73-115">**Example**</span></span>  
  
 <span data-ttu-id="cad73-116">Nel seguente esempio viene recuperato il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] durante un'operazione di recupero senza eseguire il ripristino dei dati.</span><span class="sxs-lookup"><span data-stu-id="cad73-116">The following example recovers the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in a restore operation without restoring data.</span></span>  
  
```  
-- Restore database using WITH RECOVERY.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY  
```  
  
## <a name="recovery-only-file-restore"></a><span data-ttu-id="cad73-117">Ripristino del file con solo recupero</span><span class="sxs-lookup"><span data-stu-id="cad73-117">Recovery-Only File Restore</span></span>  
 <span data-ttu-id="cad73-118">Un ripristino di file con solo recupero può risultare utile nella situazione seguente:</span><span class="sxs-lookup"><span data-stu-id="cad73-118">A recovery-only file restore can be useful in the following situation:</span></span>  
  
 <span data-ttu-id="cad73-119">Viene eseguito il ripristino a fasi di un database.</span><span class="sxs-lookup"><span data-stu-id="cad73-119">A database is restored piecemeal.</span></span> <span data-ttu-id="cad73-120">Dopo il ripristino del filegroup primario, uno o più file non ripristinati sono consistenti con il nuovo stato del database, ad esempio perché è stato mantenuto l'accesso in sola lettura per un certo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="cad73-120">After restore of the primary filegroup is complete, one or more of the unrestored files are consistent with the new database state, perhaps because it has been read-only for some time.</span></span> <span data-ttu-id="cad73-121">È pertanto sufficiente recuperare questi file senza eseguire un'operazione di copia dei dati.</span><span class="sxs-lookup"><span data-stu-id="cad73-121">These files only have to be recovered; data copying is unnecessary.</span></span>  
  
 <span data-ttu-id="cad73-122">Un'operazione di ripristino con solo recupero attiva la modalità online per i dati del filegroup offline. Non è prevista alcuna fase di copia dei dati, di rollforward o di rollback.</span><span class="sxs-lookup"><span data-stu-id="cad73-122">A recovery-only restore operation brings the data in the offline filegroup online; no data-copy, redo, or undo phase occurs.</span></span> <span data-ttu-id="cad73-123">Per informazioni sulle fasi del ripristino, vedere [Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cad73-123">For information about the phases of restore, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
 <span data-ttu-id="cad73-124">La sintassi dell'istruzione [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) per un ripristino del file con solo recupero è la seguente:</span><span class="sxs-lookup"><span data-stu-id="cad73-124">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only file restore is:</span></span>  
  
 <span data-ttu-id="cad73-125">RESTOre DATABASE *database_name* {file **=** _logical_file_name_ | FILEgroup **=** _logical_filegroup_name_ } [ **,**... *n* ] con ripristino</span><span class="sxs-lookup"><span data-stu-id="cad73-125">RESTORE DATABASE *database_name* { FILE **=**_logical_file_name_ | FILEGROUP **=**_logical_filegroup_name_ }[ **,**...*n* ] WITH RECOVERY</span></span>  
  
 <span data-ttu-id="cad73-126">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="cad73-126">**Example**</span></span>  
  
 <span data-ttu-id="cad73-127">Nell'esempio riportato di seguito, viene illustrato un ripristino di file con solo recupero, dei file presenti in un filegroup secondario, `SalesGroup2`, nel database `Sales` .</span><span class="sxs-lookup"><span data-stu-id="cad73-127">The following example illustrates a recovery-only file restore of the files in a secondary filegroup, `SalesGroup2`, in the `Sales` database.</span></span> <span data-ttu-id="cad73-128">Il filegroup primario è già stato ripristinato durante la fase iniziale di un ripristino a fasi e `SalesGroup2` è consistente con il filegroup primario ripristinato.</span><span class="sxs-lookup"><span data-stu-id="cad73-128">The primary filegroup has already been restored as the initial step of a piecemeal restore, and `SalesGroup2` is consistent with the restored primary filegroup.</span></span> <span data-ttu-id="cad73-129">Per recuperare questo filegroup e attivare la modalità online, è sufficiente una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="cad73-129">Recovering this filegroup and bringing it online requires only a single statement.</span></span>  
  
```  
RESTORE DATABASE Sales FILEGROUP=SalesGroup2 WITH RECOVERY;  
```  
  
## <a name="examples-of-completing-a-piecemeal-restore-scenario-with-a-recovery-only-restore"></a><span data-ttu-id="cad73-130">Esempi di completamento di uno scenario di ripristino frammentario con un ripristino con solo recupero</span><span class="sxs-lookup"><span data-stu-id="cad73-130">Examples of Completing a Piecemeal Restore Scenario with a Recovery-Only Restore</span></span>  
 <span data-ttu-id="cad73-131">**Modello di recupero con registrazione minima**</span><span class="sxs-lookup"><span data-stu-id="cad73-131">**Simple recovery model**</span></span>  
  
-   [<span data-ttu-id="cad73-132">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="cad73-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="cad73-133">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="cad73-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
 <span data-ttu-id="cad73-134">**Modello di recupero con registrazione completa**</span><span class="sxs-lookup"><span data-stu-id="cad73-134">**Full recovery model**</span></span>  
  
-   [<span data-ttu-id="cad73-135">Esempio: Ripristino a fasi di un database &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="cad73-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="cad73-136">Esempio: Ripristino a fasi di alcuni filegroup &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="cad73-136">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
## <a name="see-also"></a><span data-ttu-id="cad73-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cad73-137">See Also</span></span>  
 <span data-ttu-id="cad73-138">[Ripristino online &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cad73-138">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="cad73-139">[Ripristini a fasi &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cad73-139">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="cad73-140">[Ripristini di file &#40;modello di recupero con registrazione minima&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="cad73-140">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="cad73-141">[Ripristini di file &#40;modello di recupero con registrazione completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="cad73-141">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="cad73-142">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cad73-142">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
