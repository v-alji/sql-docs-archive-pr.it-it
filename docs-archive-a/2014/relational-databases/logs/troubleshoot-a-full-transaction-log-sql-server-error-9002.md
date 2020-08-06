---
title: Risolvere i problemi relativi a un log delle transazioni completo (Errore di SQL Server 9002) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], full
- troubleshooting [SQL Server], full transaction log
- 9002 (Database Engine error)
- transaction logs [SQL Server], truncation
- backing up transaction logs [SQL Server], full logs
- transaction logs [SQL Server], full log
- full transaction logs [SQL Server]
ms.assetid: 0f23aa84-475d-40df-bed3-c923f8c1b520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d03e259bd0aff8fce02558dbe08efb56748493c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624141"
---
# <a name="troubleshoot-a-full-transaction-log-sql-server-error-9002"></a><span data-ttu-id="81b62-102">Risolvere i problemi relativi a un log delle transazioni completo (Errore di SQL Server 9002)</span><span class="sxs-lookup"><span data-stu-id="81b62-102">Troubleshoot a Full Transaction Log (SQL Server Error 9002)</span></span>
  <span data-ttu-id="81b62-103">In questo argomento vengono illustrate le risposte possibili a un log delle transazioni pieno e viene spiegato come evitare tale situazione in futuro.</span><span class="sxs-lookup"><span data-stu-id="81b62-103">This topic discusses possible responses to a full transaction log and suggests how to avoid it in the future.</span></span> <span data-ttu-id="81b62-104">Quando il log delle transazioni è pieno, in [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] viene generato un errore 9002.</span><span class="sxs-lookup"><span data-stu-id="81b62-104">When the transaction log becomes full, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] issues a 9002 error.</span></span> <span data-ttu-id="81b62-105">Il log può riempirsi quando il database è online o in stato di recupero.</span><span class="sxs-lookup"><span data-stu-id="81b62-105">The log can fill when the database is online or in recovery.</span></span> <span data-ttu-id="81b62-106">Se il log si riempie quando il database è online, il database rimane online, ma può solo essere letto, non aggiornato.</span><span class="sxs-lookup"><span data-stu-id="81b62-106">If the log fills while the database is online, the database remains online but can only be read, not updated.</span></span> <span data-ttu-id="81b62-107">Se il log si riempie durante il recupero, in [!INCLUDE[ssDE](../../includes/ssde-md.md)] il database viene contrassegnato come RESOURCE PENDING.</span><span class="sxs-lookup"><span data-stu-id="81b62-107">If the log fills during recovery, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] marks the database as RESOURCE PENDING.</span></span> <span data-ttu-id="81b62-108">In entrambi i casi, è richiesto che l'utente intervenga per liberare spazio nel log.</span><span class="sxs-lookup"><span data-stu-id="81b62-108">In either case, user action is required to make log space available.</span></span>  
  
## <a name="responding-to-a-full-transaction-log"></a><span data-ttu-id="81b62-109">Risposta a un log delle transazioni pieno</span><span class="sxs-lookup"><span data-stu-id="81b62-109">Responding to a Full Transaction Log</span></span>  
 <span data-ttu-id="81b62-110">La risposta appropriata a un log delle transazioni pieno dipende in parte dalla condizione o dalle condizioni che hanno causato il riempimento del log.</span><span class="sxs-lookup"><span data-stu-id="81b62-110">The appropriate response to a full transaction log depends partly on what condition or conditions caused the log to fill.</span></span> <span data-ttu-id="81b62-111">Per individuare la condizione che impedisce il troncamento del log in un caso specifico, usare le colonne **log_reuse_wait** e **log_reuse_wait_desc** della vista del catalogo **sys.database**.</span><span class="sxs-lookup"><span data-stu-id="81b62-111">To discover what is preventing log truncation in a given case, use the **log_reuse_wait** and **log_reuse_wait_desc** columns of the **sys.database** catalog view.</span></span> <span data-ttu-id="81b62-112">Per altre informazioni, vedere [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="81b62-112">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span> <span data-ttu-id="81b62-113">Per le descrizioni dei fattori che possono ritardare il troncamento del log, vedere [Log delle transazioni &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="81b62-113">For descriptions of factors that can delay log truncation, see [The Transaction Log &#40;SQL Server&#41;](the-transaction-log-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="81b62-114">Se l'errore 9002 si è verificato durante il recupero del database, risolvere il problema, quindi recuperare il database tramite ALTER DATABASE *nome_database* SET ONLINE.</span><span class="sxs-lookup"><span data-stu-id="81b62-114">If the database was in recovery when the 9002 error occurred, after resolving the problem, recover the database by using ALTER DATABASE *database_name* SET ONLINE.</span></span>  
  
 <span data-ttu-id="81b62-115">Per gestire un log delle transazioni pieno sono disponibili le soluzioni alternative seguenti:</span><span class="sxs-lookup"><span data-stu-id="81b62-115">Alternatives for responding to a full transaction log include:</span></span>  
  
-   <span data-ttu-id="81b62-116">Esecuzione del backup del log</span><span class="sxs-lookup"><span data-stu-id="81b62-116">Backing up the log.</span></span>  
  
-   <span data-ttu-id="81b62-117">Aumento dello spazio libero su disco in modo che le dimensioni del log possano aumentare automaticamente</span><span class="sxs-lookup"><span data-stu-id="81b62-117">Freeing disk space so that the log can automatically grow.</span></span>  
  
-   <span data-ttu-id="81b62-118">Spostamento del file di log in un'unità disco con spazio sufficiente</span><span class="sxs-lookup"><span data-stu-id="81b62-118">Moving the log file to a disk drive with sufficient space.</span></span>  
  
-   <span data-ttu-id="81b62-119">Aumento delle dimensioni di un file di log</span><span class="sxs-lookup"><span data-stu-id="81b62-119">Increasing the size of a log file.</span></span>  
  
-   <span data-ttu-id="81b62-120">Aggiunta di un file di log in un altro disco</span><span class="sxs-lookup"><span data-stu-id="81b62-120">Adding a log file on a different disk.</span></span>  
  
-   <span data-ttu-id="81b62-121">Completamento o termine di una transazione con esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="81b62-121">Completing or killing a long-running transaction.</span></span>  
  
 <span data-ttu-id="81b62-122">Queste soluzioni alternative verranno illustrate nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="81b62-122">These alternatives are discussed in the following sections.</span></span> <span data-ttu-id="81b62-123">Scegliere la risposta più appropriata a seconda della situazione.</span><span class="sxs-lookup"><span data-stu-id="81b62-123">Choose a response that fits your situation best.</span></span>  
  
### <a name="backing-up-the-log"></a><span data-ttu-id="81b62-124">Backup del log</span><span class="sxs-lookup"><span data-stu-id="81b62-124">Backing up the Log</span></span>  
 <span data-ttu-id="81b62-125">Nel modello di recupero con registrazione completa o nel modello di recupero con registrazione minima delle operazioni bulk, se non è stato eseguito il backup del log delle transazioni di recente, è possibile che sia il backup a impedire il troncamento del log.</span><span class="sxs-lookup"><span data-stu-id="81b62-125">Under the full recovery model or bulk-logged recovery model, if the transaction log has not been backed up recently, backup might be what is preventing log truncation.</span></span> <span data-ttu-id="81b62-126">Se il backup del log non è mai stato eseguito, è necessario creare due backup del log per consentire a [!INCLUDE[ssDE](../../includes/ssde-md.md)] di troncare il log in corrispondenza del punto dell'ultimo backup.</span><span class="sxs-lookup"><span data-stu-id="81b62-126">If the log has never been backed up, you must create two log backups to permit the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to truncate the log to the point of the last backup.</span></span> <span data-ttu-id="81b62-127">Il troncamento del log consente di rendere disponibile spazio per nuovi record del log.</span><span class="sxs-lookup"><span data-stu-id="81b62-127">Truncating the log frees space for new log records.</span></span> <span data-ttu-id="81b62-128">Per evitare che il log si riempia di nuovo, eseguire backup del log frequenti.</span><span class="sxs-lookup"><span data-stu-id="81b62-128">To keep the log from filling up again, take log backups frequently.</span></span>  
  
 <span data-ttu-id="81b62-129">**Per creare un backup del log delle transazioni**</span><span class="sxs-lookup"><span data-stu-id="81b62-129">**To create a transaction log backup**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="81b62-130">Se il database è danneggiato, vedere [Backup della parte finale del log &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="81b62-130">If the database is damaged, see [Tail-Log Backups &#40;SQL Server&#41;](../backup-restore/tail-log-backups-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="81b62-131">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="81b62-131">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="81b62-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="81b62-132"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
### <a name="freeing-disk-space"></a><span data-ttu-id="81b62-133">Aumento dello spazio disponibile su disco</span><span class="sxs-lookup"><span data-stu-id="81b62-133">Freeing Disk Space</span></span>  
 <span data-ttu-id="81b62-134">Potrebbe essere possibile liberare spazio sull'unità disco contenente il file del log delle transazioni per il database, eliminando o spostando altri file.</span><span class="sxs-lookup"><span data-stu-id="81b62-134">You might be able to free disk space on the disk drive that contains the transaction log file for the database by deleting or moving other files.</span></span> <span data-ttu-id="81b62-135">L'aumento dello spazio disponibile su disco consente al sistema di recupero di ingrandire automaticamente il file di log.</span><span class="sxs-lookup"><span data-stu-id="81b62-135">The freed disk space allows the recovery system to enlarge the log file automatically.</span></span>  
  
### <a name="moving-the-log-file-to-a-different-disk"></a><span data-ttu-id="81b62-136">Spostamento del file di log in un altro disco</span><span class="sxs-lookup"><span data-stu-id="81b62-136">Moving the Log File to a Different Disk</span></span>  
 <span data-ttu-id="81b62-137">Se non é possibile liberare spazio su disco sufficiente nell'unità che attualmente contiene il file di log, prendere in considerazione lo spostamento del file in un'altra unità con spazio adeguato.</span><span class="sxs-lookup"><span data-stu-id="81b62-137">If you cannot free enough disk space on the drive that currently contains the log file, consider moving the file to another drive with sufficient space.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="81b62-138">È consigliabile non memorizzare mai file di log in file system compressi.</span><span class="sxs-lookup"><span data-stu-id="81b62-138">Log files should never be placed on compressed file systems.</span></span>  
  
 <span data-ttu-id="81b62-139">**Per spostare un file di log**</span><span class="sxs-lookup"><span data-stu-id="81b62-139">**To move a log file**</span></span>  
  
-   [<span data-ttu-id="81b62-140">Spostare file del database</span><span class="sxs-lookup"><span data-stu-id="81b62-140">Move Database Files</span></span>](../databases/move-database-files.md)  
  
### <a name="increasing-the-size-of-a-log-file"></a><span data-ttu-id="81b62-141">Aumento delle dimensioni di un file di log</span><span class="sxs-lookup"><span data-stu-id="81b62-141">Increasing the Size of a Log File</span></span>  
 <span data-ttu-id="81b62-142">Se nel disco del log è disponibile spazio, è possibile aumentare le dimensioni del file di log.</span><span class="sxs-lookup"><span data-stu-id="81b62-142">If space is available on the log disk, you can increase the size of the log file.</span></span> <span data-ttu-id="81b62-143">La dimensione massima per i file di log è due terabyte per file di log.</span><span class="sxs-lookup"><span data-stu-id="81b62-143">The maximum size for log files is two terabytes (TB) per log file.</span></span>  
  
 <span data-ttu-id="81b62-144">**Per aumentare le dimensioni dei file**</span><span class="sxs-lookup"><span data-stu-id="81b62-144">**To increase the file size**</span></span>  
  
 <span data-ttu-id="81b62-145">Se l'aumento automatico dimensioni è disabilitato, il database è online ed è disponibile spazio sufficiente sul disco, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="81b62-145">If autogrow is disabled, the database is online, and sufficient space is available on the disk, either:</span></span>  
  
-   <span data-ttu-id="81b62-146">Aumentare manualmente le dimensioni del file per produrre un incremento di crescita singolo.</span><span class="sxs-lookup"><span data-stu-id="81b62-146">Manually increase the file size to produce a single growth increment.</span></span>  
  
-   <span data-ttu-id="81b62-147">Abilitare l'aumento automatico dimensioni utilizzando l'istruzione ALTER DATABASE per impostare un incremento di crescita diverso da zero per l'opzione FILEGROWTH.</span><span class="sxs-lookup"><span data-stu-id="81b62-147">Turn on autogrow by using the ALTER DATABASE statement to set a non-zero growth increment for the FILEGROWTH option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81b62-148">In entrambi i casi, se sono state raggiunte le dimensioni massime consentite correnti, aumentare il valore MAXSIZE.</span><span class="sxs-lookup"><span data-stu-id="81b62-148">In either case, if the current size limit has been reached, increase the MAXSIZE value.</span></span>  
  
### <a name="adding-a-log-file-on-a-different-disk"></a><span data-ttu-id="81b62-149">Aggiunta di un file di log in un altro disco</span><span class="sxs-lookup"><span data-stu-id="81b62-149">Adding a Log File on a Different Disk</span></span>  
 <span data-ttu-id="81b62-150">Aggiungere un nuovo file di log al database in un altro disco contenente spazio sufficiente utilizzando ALTER DATABASE <database_name> ADD LOG FILE.</span><span class="sxs-lookup"><span data-stu-id="81b62-150">Add a new log file to the database on a different disk that has sufficient space by using ALTER DATABASE <database_name> ADD LOG FILE.</span></span>  
  
 <span data-ttu-id="81b62-151">**Per aggiungere un file di log**</span><span class="sxs-lookup"><span data-stu-id="81b62-151">**To add a log file**</span></span>  
  
-   [<span data-ttu-id="81b62-152">Aggiungere file di dati o file di log a un database</span><span class="sxs-lookup"><span data-stu-id="81b62-152">Add Data or Log Files to a Database</span></span>](../databases/add-data-or-log-files-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="81b62-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81b62-153">See Also</span></span>  
 <span data-ttu-id="81b62-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81b62-154">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="81b62-155">[Gestione delle dimensioni del file di log delle transazioni](manage-the-size-of-the-transaction-log-file.md) </span><span class="sxs-lookup"><span data-stu-id="81b62-155">[Manage the Size of the Transaction Log File](manage-the-size-of-the-transaction-log-file.md) </span></span>  
 <span data-ttu-id="81b62-156">[Backup di log delle transazioni &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="81b62-156">[Transaction Log Backups &#40;SQL Server&#41;](../backup-restore/transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="81b62-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="81b62-157">sp_add_log_file_recover_suspect_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-log-file-recover-suspect-db-transact-sql)  
  
  
