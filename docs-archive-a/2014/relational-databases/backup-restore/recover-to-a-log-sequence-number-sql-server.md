---
title: Eseguire il recupero fino a un numero di sequenza del file di log (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log sequence numbers [SQL Server]
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- LSNs
- database recovery [SQL Server]
- database restores [SQL Server], point in time
ms.assetid: f7b3de5b-198d-448d-8c71-1cdd9239676c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4df55c3468fc009d86cffd58a837d6935f5ce14b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635683"
---
# <a name="recover-to-a-log-sequence-number-sql-server"></a><span data-ttu-id="eb576-102">Recupero fino a un numero di sequenza del file di log (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="eb576-102">Recover to a Log Sequence Number (SQL Server)</span></span>
  <span data-ttu-id="eb576-103">Le informazioni contenute in questo argomento sono rilevanti solo per i database che utilizzano il modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="eb576-103">This topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="eb576-104">È possibile utilizzare un numero di sequenza del file di log (LSN) per definire il punto di recupero per un'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="eb576-104">You can use a log sequence number (LSN) to define the recovery point for a restore operation.</span></span> <span data-ttu-id="eb576-105">Si tratta tuttavia di una funzionalità specializzata progettata per i fornitori di strumenti e viene utilizzata solo in rari casi.</span><span class="sxs-lookup"><span data-stu-id="eb576-105">However, this is a specialized feature that is intended for tools vendors and is unlikely to be generally useful.</span></span>  
  
##  <a name="overview-of-log-sequence-numbers"></a><a name="LSNs"></a> <span data-ttu-id="eb576-106">Panoramica dei numeri di sequenza del file di log</span><span class="sxs-lookup"><span data-stu-id="eb576-106">Overview of Log Sequence Numbers</span></span>  
 <span data-ttu-id="eb576-107">Gli LSN sono utilizzati internamente durante una sequenza RESTORE per tenere traccia del momento specifico rispetto al quale i dati sono stati ripristinati.</span><span class="sxs-lookup"><span data-stu-id="eb576-107">LSNs are used internally during a RESTORE sequence to track the point in time to which data has been restored.</span></span> <span data-ttu-id="eb576-108">Quando un backup viene ripristinato, i dati vengono ripristinati sull'LSN corrispondente al momento specifico di esecuzione del backup.</span><span class="sxs-lookup"><span data-stu-id="eb576-108">When a backup is restored, the data is restored to the LSN corresponding to the point in time at which the backup was taken.</span></span> <span data-ttu-id="eb576-109">Backup dei log e differenziali spostano il database ripristinato a un momento successivo, corrispondente a un LSN maggiore.</span><span class="sxs-lookup"><span data-stu-id="eb576-109">Differential and log backups advance the restored database to a later time, which corresponds to a higher LSN.</span></span>  
  
 <span data-ttu-id="eb576-110">Ogni record presente nel log delle transazioni è identificato in modo univoco da un numero di sequenza dei file di log (LSN).</span><span class="sxs-lookup"><span data-stu-id="eb576-110">Every record in the transaction log is uniquely identified by a log sequence number (LSN).</span></span> <span data-ttu-id="eb576-111">Gli LSN sono ordinati in modo tale che se LSN è maggiore di LSN1, la modifica descritta dal record di log cui fa riferimento LSN2 si verifica dopo la modifica descritta dall'LSN del record di log.</span><span class="sxs-lookup"><span data-stu-id="eb576-111">LSNs are ordered such that if LSN2 is greater than LSN1, the change described by the log record referred to by LSN2 occurred after the change described by the log record LSN.</span></span>  
  
 <span data-ttu-id="eb576-112">L'LSN di un record di log in corrispondenza del quale si è verificato un evento significativo può essere utile per creare sequenze di ripristino corrette.</span><span class="sxs-lookup"><span data-stu-id="eb576-112">The LSN of a log record at which a significant event occurred can be useful for constructing correct restore sequences.</span></span> <span data-ttu-id="eb576-113">Poiché LSN sono ordinati, possono essere confrontati per verificarne l'uguaglianza e la disuguaglianza (ovvero,, **\<**, **>** **=** **\<=**, **>=** ).</span><span class="sxs-lookup"><span data-stu-id="eb576-113">Because LSNs are ordered, they can be compared for equality and inequality (that is, **\<**, **>**, **=**, **\<=**, **>=**).</span></span> <span data-ttu-id="eb576-114">Questi confronti sono utili nella creazione di sequenze di ripristino.</span><span class="sxs-lookup"><span data-stu-id="eb576-114">Such comparisons are useful when constructing restore sequences.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb576-115">Gli LSN sono valori di tipo di dati `numeric`(25,0).</span><span class="sxs-lookup"><span data-stu-id="eb576-115">LSNs are values of data type `numeric`(25,0).</span></span> <span data-ttu-id="eb576-116">Gli operatori matematici, ad esempio addizione o sottrazione, non sono significativi e non devono essere utilizzati con gli LSN.</span><span class="sxs-lookup"><span data-stu-id="eb576-116">Arithmetic operations (for example, addition or subtraction) are not meaningful and must not be used with LSNs.</span></span>  
  

  
## <a name="viewing-lsns-used-by-backup-and-restore"></a><span data-ttu-id="eb576-117">Visualizzazione degli LSN utilizzati tramite backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="eb576-117">Viewing LSNs Used by Backup and Restore</span></span>  
 <span data-ttu-id="eb576-118">L'LSN di un record di log in corrispondenza del quale si è verificato un determinato evento di backup e di ripristino è visibile utilizzando una o più delle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb576-118">The LSN of a log record at which a given backup and restore event occurred is viewable using one or more of the following:</span></span>  
  
-   [<span data-ttu-id="eb576-119">backupset</span><span class="sxs-lookup"><span data-stu-id="eb576-119">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
-   [<span data-ttu-id="eb576-120">backupfile</span><span class="sxs-lookup"><span data-stu-id="eb576-120">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)  
  
-   <span data-ttu-id="eb576-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="eb576-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span></span>  
  
-   [<span data-ttu-id="eb576-122">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="eb576-122">RESTORE HEADERONLY</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="eb576-123">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="eb576-123">RESTORE FILELISTONLY</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="eb576-124">Gli LSN sono inoltre visualizzati nel testo di alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="eb576-124">LSNs also appear in some message texts.</span></span>  
  
## <a name="transact-sql-syntax-for-restoring-to-an-lsn"></a><span data-ttu-id="eb576-125">Sintassi Transact-SQL per il ripristino fino a un numero di sequenza del file di log (LSN)</span><span class="sxs-lookup"><span data-stu-id="eb576-125">Transact-SQL Syntax for Restoring to an LSN</span></span>  
 <span data-ttu-id="eb576-126">Un'istruzione [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) consente di arrestare il processo esattamente in corrispondenza dell'LSN o immediatamente prima, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="eb576-126">By using a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, you can stop at or immediately before the LSN, as follows:</span></span>  
  
-   <span data-ttu-id="eb576-127">Usare la clausola WITH STOPATMARK **='** lsn: _<lsn_number>_ **'** , dove lsn: *\<lsnNumber>* è una stringa che specifica che il punto di recupero corrisponde al record di log contenente l'LSN specificato.</span><span class="sxs-lookup"><span data-stu-id="eb576-127">Use the WITH STOPATMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record that contains the specified LSN is the recovery point.</span></span>  
  
     <span data-ttu-id="eb576-128">STOPATMARK esegue il rollforward al numero di sequenza del file di log (LSN) includendo anche tale record del log.</span><span class="sxs-lookup"><span data-stu-id="eb576-128">STOPATMARK roll forwards to the LSN and includes that log record in the roll forward.</span></span>  
  
-   <span data-ttu-id="eb576-129">Usare la clausola WITH STOPBEFOREMARK **='** lsn: _<lsn_number>_ **'** , dove lsn: *\<lsnNumber>* è una stringa che specifica che il punto di recupero corrisponde al record di log immediatamente precedente a quello contenente l'LSN specificato.</span><span class="sxs-lookup"><span data-stu-id="eb576-129">Use the WITH STOPBEFOREMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record immediately before the log record that contains the specified LSN number is the recovery point.</span></span>  
  
     <span data-ttu-id="eb576-130">Tramite STOPBEFOREMARK viene eseguito il rollforward fino all'LSN escludendo tale record di log.</span><span class="sxs-lookup"><span data-stu-id="eb576-130">STOPBEFOREMARK rolls forward to the LSN and excludes that log record from the roll forward.</span></span>  
  
 <span data-ttu-id="eb576-131">In genere, viene selezionata una transazione specifica da includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="eb576-131">Typically, a specific transaction is selected to be included or excluded.</span></span> <span data-ttu-id="eb576-132">Sebbene non sia necessario, il record di log specificato è in pratica un record di commit delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="eb576-132">Although not required, in practice, the specified log record is a transaction-commit record.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="eb576-133">Esempi</span><span class="sxs-lookup"><span data-stu-id="eb576-133">Examples</span></span>  
 <span data-ttu-id="eb576-134">Nell'esempio seguente si presuppone che il database `AdventureWorks` sia stato modificato in modo da utilizzare il modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="eb576-134">The following example assumes that the `AdventureWorks` database has been changed to use the full recovery model.</span></span>  
  
```  
RESTORE LOG AdventureWorks FROM DISK = 'c:\adventureworks_log.bak'   
WITH STOPATMARK = 'lsn:15000000040000037'  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="eb576-135">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="eb576-135">Related Tasks</span></span>  
  
-   [<span data-ttu-id="eb576-136">Ripristinare un backup del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="eb576-136">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="eb576-137">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb576-137">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="eb576-138">Ripristinare un backup del log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb576-138">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="eb576-139">Ripristinare un database fino al punto di errore nel modello di recupero con registrazione completa &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eb576-139">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="eb576-140">Ripristinare un database fino a una transazione contrassegnata &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="eb576-140">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="eb576-141">Ripristinare un database di SQL Server fino a un punto specifico &#40;modello di recupero con registrazione completa&#41;</span><span class="sxs-lookup"><span data-stu-id="eb576-141">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb576-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb576-142">See Also</span></span>  
 <span data-ttu-id="eb576-143">[Applicare backup del log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb576-143">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="eb576-144">[Log delle transazioni &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb576-144">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="eb576-145">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eb576-145">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
