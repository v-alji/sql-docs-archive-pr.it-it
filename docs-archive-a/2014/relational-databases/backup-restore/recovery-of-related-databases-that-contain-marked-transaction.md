---
title: Recupero di database correlati che contengono transazioni contrassegnate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction logs [SQL Server], marks
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- transactions [SQL Server], recovering to a mark
- database recovery [SQL Server]
- marked transactions [SQL Server], restoring
- database restores [SQL Server], point in time
ms.assetid: 77a0d9c0-978a-4891-8b0d-a4256c81c3f8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b968322f92c7a135adb5fd0733b5774e7562bc39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721520"
---
# <a name="recovery-of-related--databases-that-contain-marked-transaction"></a><span data-ttu-id="069fd-102">Recupero di database correlati che contengono transazioni contrassegnate</span><span class="sxs-lookup"><span data-stu-id="069fd-102">Recovery of Related  Databases That Contain Marked Transaction</span></span>
  <span data-ttu-id="069fd-103">Le informazioni contenute in questo argomento sono rilevanti solo per i database che includono transazioni contrassegnate e utilizzano il modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="069fd-103">This topic is relevant only for databases that contain marked transactions and that use the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="069fd-104">Per informazioni sui requisiti per il ripristino fino a un punto di recupero specifico, vedere [Ripristinare un database di SQL Server fino a un punto specifico &#40;modello di recupero con registrazione completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="069fd-104">For information about the requirements for restoring to a specific recovery point, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="069fd-105">supporta l'inserimento di contrassegni denominati nel log delle transazioni per il recupero fino a un punto specifico.</span><span class="sxs-lookup"><span data-stu-id="069fd-105">supports inserting named marks into the transaction log to allow recovery to that specific mark.</span></span> <span data-ttu-id="069fd-106">I contrassegni del log sono specifici della transazione e vengono inseriti solo se viene eseguito il commit della transazione associata.</span><span class="sxs-lookup"><span data-stu-id="069fd-106">Log marks are transaction specific and are inserted only if their associated transaction commits.</span></span> <span data-ttu-id="069fd-107">In questo modo, i contrassegni risultano legati a serie di operazioni specifiche ed è possibile eseguire il recupero includendo o escludendo le serie di operazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="069fd-107">As a result, marks can be tied to specific work, and you can recover to a point that includes or excludes this work.</span></span>  
  
 <span data-ttu-id="069fd-108">Prima di inserire contrassegni denominati nel log delle transazioni, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="069fd-108">Before you insert named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="069fd-109">I contrassegni di transazione occupano spazio nei log e pertanto è consigliabile utilizzarli esclusivamente per transazioni importanti ai fini della strategia di recupero dei database.</span><span class="sxs-lookup"><span data-stu-id="069fd-109">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="069fd-110">Dopo il commit di una transazione contrassegnata, viene inserita una riga nella tabella [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) del database **msdb**.</span><span class="sxs-lookup"><span data-stu-id="069fd-110">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="069fd-111">Se una transazione contrassegnata si estende su più database dello stesso server di database o di server diversi, i contrassegni devono essere registrati nei log di tutti i database interessati.</span><span class="sxs-lookup"><span data-stu-id="069fd-111">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span> <span data-ttu-id="069fd-112">Per altre informazioni, vedere [Usare transazioni contrassegnate per recuperare coerentemente i database correlati &#40;modello di recupero con registrazione completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="069fd-112">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="069fd-113">Per informazioni sul contrassegno delle transazioni, vedere [Usare transazioni contrassegnate per recuperare coerentemente i database correlati &#40;modello di recupero con registrazione completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="069fd-113">For information about how to mark transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-inserting-named-marks-into-a-transaction-log"></a><span data-ttu-id="069fd-114">Sintassi Transact-SQL per l'inserimento di contrassegni denominati in un log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="069fd-114">Transact-SQL Syntax for Inserting Named Marks into a Transaction Log</span></span>  
 <span data-ttu-id="069fd-115">Per inserire contrassegni nei log delle transazioni, usare l'istruzione [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) e la clausola WITH MARK [*description*].</span><span class="sxs-lookup"><span data-stu-id="069fd-115">To insert marks into the transaction logs, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="069fd-116">Al contrassegno viene assegnato lo stesso nome della transazione.</span><span class="sxs-lookup"><span data-stu-id="069fd-116">The mark is named the same as the transaction.</span></span> <span data-ttu-id="069fd-117">L'argomento *description* facoltativo è una descrizione testuale del contrassegno e non corrisponde al nome del contrassegno.</span><span class="sxs-lookup"><span data-stu-id="069fd-117">The optional *description* is a textual description of the mark, not the mark name.</span></span> <span data-ttu-id="069fd-118">Il nome sia della transazione sia del contrassegno creato nella seguente istruzione `BEGIN TRANSACTION` è ad esempio `Tx1`:</span><span class="sxs-lookup"><span data-stu-id="069fd-118">For example, the name of both the transaction and the mark that is created in the following `BEGIN TRANSACTION` statement is `Tx1`:</span></span>  
  
```wmimof  
BEGIN TRANSACTION Tx1 WITH MARK 'not the mark name, just a description'    
```  
  
 <span data-ttu-id="069fd-119">Nel log delle transazioni vengono registrati il nome del contrassegno (il nome della transazione), la descrizione, il database, l'utente, le informazioni di tipo `datetime` e il numero di sequenza del file di log (LSN).</span><span class="sxs-lookup"><span data-stu-id="069fd-119">The transaction log records the mark name (transaction name), description, database, user, `datetime` information, and the log sequence number (LSN).</span></span> <span data-ttu-id="069fd-120">Per l'identificazione univoca del contrassegno, il nome viene associato alle informazioni `datetime`.</span><span class="sxs-lookup"><span data-stu-id="069fd-120">The `datetime` information is used with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="069fd-121">Per informazioni sull'inserimento di un contrassegno in una transazione che si estende su più database, vedere [Usare transazioni contrassegnate per recuperare coerentemente i database correlati &#40;modello di recupero con registrazione completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="069fd-121">For information about how to insert a mark into a transaction that spans multiple databases, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-recovering-to-a-mark"></a><span data-ttu-id="069fd-122">Sintassi Transact-SQL per il recupero fino a un contrassegno</span><span class="sxs-lookup"><span data-stu-id="069fd-122">Transact-SQL Syntax for Recovering to a Mark</span></span>  
 <span data-ttu-id="069fd-123">Quando si specifica una transazione contrassegnata come destinazione usando un'istruzione[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql), è possibile usare una delle clausole seguenti per arrestare l'operazione in corrispondenza del contrassegno o immediatamente prima di esso:</span><span class="sxs-lookup"><span data-stu-id="069fd-123">When you target a marked transaction by using a[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql)statement, you can use one the following clauses to stop at or immediately before the mark:</span></span>  
  
-   <span data-ttu-id="069fd-124">Utilizzare la clausola WITH STOPATMARK = **' *`<mark_name>`* '** per specificare che la transazione contrassegnata è il punto di ripristino.</span><span class="sxs-lookup"><span data-stu-id="069fd-124">Use the WITH STOPATMARK = **'*`<mark_name>`*'** clause to specify that the marked transaction is the recovery point.</span></span>  
  
     <span data-ttu-id="069fd-125">STOPATMARK esegue il rollforward fino al contrassegno, includendovi la transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="069fd-125">STOPATMARK rolls forward to the mark and includes the marked transaction in the roll forward.</span></span>  
  
-   <span data-ttu-id="069fd-126">Utilizzare la clausola WITH STOPBEFOREMARK = **' *`<mark_name>`* '** per specificare che il punto di recupero corrisponde al record di log immediatamente precedente al contrassegno.</span><span class="sxs-lookup"><span data-stu-id="069fd-126">Use the WITH STOPBEFOREMARK = **'*`<mark_name>`*'** clause to specify that the log record that is immediately before the mark is the recovery point.</span></span>  
  
     <span data-ttu-id="069fd-127">STOPBEFOREMARK esegue il rollforward fino al contrassegno, escludendo la transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="069fd-127">STOPBEFOREMARK rolls forward to the mark and excludes marked the transaction from the roll forward.</span></span>  
  
 <span data-ttu-id="069fd-128">Entrambe le opzioni STOPATMARK e STOPBEFOREMARK supportano una clausola AFTER *datetime* facoltativa.</span><span class="sxs-lookup"><span data-stu-id="069fd-128">The STOPATMARK and STOPBEFOREMARK options both support an optional AFTER *datetime* clause.</span></span> <span data-ttu-id="069fd-129">Quando si usa *datetime* , non è necessario che i nomi dei contrassegni siano univoci.</span><span class="sxs-lookup"><span data-stu-id="069fd-129">When *datetime* is used, mark names do not have to be unique.</span></span>  
  
 <span data-ttu-id="069fd-130">Se AFTER *datetime* viene omesso, il rollforward viene arrestato in corrispondenza del primo contrassegno con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="069fd-130">If AFTER *datetime* is omitted, roll forward stops at the first mark that has the specified name.</span></span> <span data-ttu-id="069fd-131">Se AFTER *datetime* viene specificato, il rollforward viene arrestato in corrispondenza del primo contrassegno con il nome specificato, nella data e ora indicate in *datetime*o in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="069fd-131">If AFTER *datetime* is specified, roll forward stops at the first mark that has the specified name, exactly at or after *datetime*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="069fd-132">Come per tutte le operazioni di ripristino temporizzato, il recupero fino a un contrassegno è disattivato quando nel database sono in corso operazioni con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="069fd-132">As in all point-in-time restore operations, recovering to a mark is disallowed when the database is undergoing operations that are bulk-logged.</span></span>  
  
 <span data-ttu-id="069fd-133">**Per ripristinare una transazione contrassegnata**</span><span class="sxs-lookup"><span data-stu-id="069fd-133">**To restore to a marked transaction**</span></span>  
  
 [<span data-ttu-id="069fd-134">Ripristinare un database fino a una transazione contrassegnata &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="069fd-134">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
 [<span data-ttu-id="069fd-135">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="069fd-135">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
### <a name="preparing-the-log-backups"></a><span data-ttu-id="069fd-136">Preparazione dei backup del log</span><span class="sxs-lookup"><span data-stu-id="069fd-136">Preparing the Log Backups</span></span>  
 <span data-ttu-id="069fd-137">In questo esempio, una strategia di backup appropriata per i database correlati potrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="069fd-137">For this example, an appropriate backup strategy for these related databases would be the following:</span></span>  
  
1.  <span data-ttu-id="069fd-138">Utilizzare il modello di recupero con registrazione completa per entrambi i database.</span><span class="sxs-lookup"><span data-stu-id="069fd-138">Use the full recovery model for both databases.</span></span>  
  
2.  <span data-ttu-id="069fd-139">Creare un backup completo di ogni database.</span><span class="sxs-lookup"><span data-stu-id="069fd-139">Create a full backup of each database.</span></span>  
  
     <span data-ttu-id="069fd-140">È possibile eseguire il backup dei database in sequenza o simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="069fd-140">The databases can be backed up sequentially or simultaneously.</span></span>  
  
3.  <span data-ttu-id="069fd-141">Prima di eseguire il backup del log delle transazioni, contrassegnare una transazione che viene eseguita in tutti i database.</span><span class="sxs-lookup"><span data-stu-id="069fd-141">Before backing up the transaction log, mark a transaction that executes in all databases.</span></span> <span data-ttu-id="069fd-142">Per informazioni sulla creazione di transazioni contrassegnate, vedere [Usare transazioni contrassegnate per recuperare coerentemente i database correlati &#40;modello di recupero con registrazione completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="069fd-142">For information about how to create the marked transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
4.  <span data-ttu-id="069fd-143">Eseguire il backup del log delle transazioni in ogni database.</span><span class="sxs-lookup"><span data-stu-id="069fd-143">Back up the transaction log on each database.</span></span>  
  
### <a name="recovering-the-database-to-a-marked-transaction"></a><span data-ttu-id="069fd-144">Recupero del database fino a una transazione contrassegnata</span><span class="sxs-lookup"><span data-stu-id="069fd-144">Recovering the Database to a Marked Transaction</span></span>  
 <span data-ttu-id="069fd-145">**Per ripristinare il backup**</span><span class="sxs-lookup"><span data-stu-id="069fd-145">**To restore the backup**</span></span>  
  
1.  <span data-ttu-id="069fd-146">Se possibile, creare [backup della parte finale del log](tail-log-backups-sql-server.md) per i database non danneggiati.</span><span class="sxs-lookup"><span data-stu-id="069fd-146">Create [tail-log backups](tail-log-backups-sql-server.md) of the undamaged databases, if possible.</span></span>  
  
2.  <span data-ttu-id="069fd-147">Ripristinare il backup completo più recente di ogni database.</span><span class="sxs-lookup"><span data-stu-id="069fd-147">Restore the most recent full database backup of each database.</span></span>  
  
3.  <span data-ttu-id="069fd-148">Individuare la transazione contrassegnata più recente disponibile in tutti i backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="069fd-148">Identify the most recent marked transaction that is available in all of the transaction log backups.</span></span> <span data-ttu-id="069fd-149">Questa informazione è archiviata nella tabella **logmarkhistory** del database **msdb** in ogni server.</span><span class="sxs-lookup"><span data-stu-id="069fd-149">This information is stored in the **logmarkhistory** table in the **msdb** database on each server.</span></span>  
  
4.  <span data-ttu-id="069fd-150">Individuare i backup del log di tutti i database correlati che contengono questo contrassegno.</span><span class="sxs-lookup"><span data-stu-id="069fd-150">Identify the log backups for all related databases that contain this mark.</span></span>  
  
5.  <span data-ttu-id="069fd-151">Ripristinare ogni backup del log fino alla transazione contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="069fd-151">Restore each log backup, stopping at the marked transaction.</span></span>  
  
6.  <span data-ttu-id="069fd-152">Recuperare ogni database.</span><span class="sxs-lookup"><span data-stu-id="069fd-152">Recover each database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="069fd-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="069fd-153">See Also</span></span>  
 <span data-ttu-id="069fd-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="069fd-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="069fd-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="069fd-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="069fd-156">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="069fd-156">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="069fd-157">[Usare transazioni contrassegnate per recuperare coerentemente i database correlati &#40;modello di recupero con registrazione completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span><span class="sxs-lookup"><span data-stu-id="069fd-157">[Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span></span>  
 <span data-ttu-id="069fd-158">[Panoramica del ripristino e del recupero &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="069fd-158">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="069fd-159">[Ripristinare un database di SQL Server fino a un punto specifico &#40;Modello di recupero con registrazione completa&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="069fd-159">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="069fd-160">Pianificare ed eseguire sequenze di ripristino &#40;Modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="069fd-160">Plan and Perform Restore Sequences &#40;Full Recovery Model&#41;</span></span>](plan-and-perform-restore-sequences-full-recovery-model.md)  
  
  
