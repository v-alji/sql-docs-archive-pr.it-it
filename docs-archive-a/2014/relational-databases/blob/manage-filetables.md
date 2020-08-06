---
title: Gestire tabelle FileTable | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], security
- FileTables [SQL Server], managing access
ms.assetid: 93af982c-b4fe-4be0-8268-11f86dae27e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a15a914c243f1fafd3b913d98113e984bf533086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715407"
---
# <a name="manage-filetables"></a><span data-ttu-id="ba3f2-102">Gestione di tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-102">Manage FileTables</span></span>
  <span data-ttu-id="ba3f2-103">Vengono descritte attività amministrative comuni per la gestione di tabelle FileTable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-103">Describes common administrative tasks for managing FileTables.</span></span>  
  
##  <a name="how-to-get-a-list-of-filetables-and-related-objects"></a><a name="HowToEnumerate"></a> <span data-ttu-id="ba3f2-104">Procedura: Recuperare un elenco di tabelle FileTable e di oggetti correlati</span><span class="sxs-lookup"><span data-stu-id="ba3f2-104">How To: Get a List of FileTables and Related Objects</span></span>  
 <span data-ttu-id="ba3f2-105">Per ottenere un elenco di tabelle FileTable, eseguire una query su una delle viste del catalogo riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="ba3f2-105">To get a list of FileTables, query one of the following catalog views:</span></span>  
  
-   [<span data-ttu-id="ba3f2-106">sys.filetables &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ba3f2-106">sys.filetables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-filetables-transact-sql)  
  
-   <span data-ttu-id="ba3f2-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (verificare il valore della colonna **is_filetable**).</span><span class="sxs-lookup"><span data-stu-id="ba3f2-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Check the value of the **is_filetable** column.)</span></span>  
  
```sql  
SELECT * FROM sys.filetables;  
GO  
  
SELECT * FROM sys.tables WHERE is_filetable = 1;  
GO  
```  
  
 <span data-ttu-id="ba3f2-108">Per ottenere un elenco degli oggetti definiti dal sistema creati quando sono state create le tabelle FileTable associate, eseguire una query sulla vista del catalogo [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba3f2-108">To get a list of the system-defined objects that were created when the associated FileTables were created, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
SELECT object_id, OBJECT_NAME(object_id) AS 'Object Name'  
    FROM sys.filetable_system_defined_objects  
    WHERE object_id = filetable_object_id;  
GO  
```  
  
##  <a name="disabling-and-re-enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsDisabling"></a> <span data-ttu-id="ba3f2-109">Disabilitare e riabilitare l'accesso non transazionale a livello di database</span><span class="sxs-lookup"><span data-stu-id="ba3f2-109">Disabling and Re-enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="ba3f2-110">Per acquisire l'accesso esclusivo necessario per determinate attività di amministrazione, può essere necessario disabilitare temporaneamente l'accesso non transazionale.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-110">To acquire the exclusive access that is required for certain administrative tasks, you may have to disable non-transactional access temporarily.</span></span>  
  
 <span data-ttu-id="ba3f2-111">**Comportamento dell'istruzione ALTER DATABASE in caso di modifica del livello di accesso non transazionale**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-111">**Behavior of the ALTER DATABASE statement when changing the level of non-transactional access**</span></span>  
  
-   <span data-ttu-id="ba3f2-112">Quando si imposta l'accesso non transazionale su READ_ONLY o OFF, il comando ALTER DATABASE non restituisce il controllo all'utente finché sono presenti handle di file aperti che creano conflitti con l'operazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-112">When you set non-transactional access to READ_ONLY or OFF, the ALTER DATABASE command does not return control to the user as long as there are open file handles that conflict with the requested operation.</span></span> <span data-ttu-id="ba3f2-113">Gli handle di file che creano conflitti con questa operazione includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba3f2-113">The file handles that conflict with this operation include the following:</span></span>  
  
    -   <span data-ttu-id="ba3f2-114">Quando l'accesso viene impostato su **NESSUNO**, tutti gli handle di file aperti.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-114">When you are setting access to **NONE**, all open file handles.</span></span>  
  
    -   <span data-ttu-id="ba3f2-115">Quando l'accesso viene impostato su **READ_ONLY**, tutti gli handle di file aperti per l'accesso in scrittura.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-115">When you are setting access to **READ_ONLY**, all file handles opened for write access.</span></span>  
  
     <span data-ttu-id="ba3f2-116">Per informazioni sulla terminazione degli handle di file aperti, vedere [Terminazione di handle di file aperti associati a una tabella FileTable](#BasicsKilling) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-116">For information about killing open file handles, see [Killing Open File Handles Associated with a FileTable](#BasicsKilling) in this topic.</span></span>  
  
     <span data-ttu-id="ba3f2-117">Se il comando ALTER DATABASE è annullato o termina con un timeout, il livello di accesso transazionale non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-117">If the ALTER DATABASE command is canceled or ends with a timeout, then the level of transactional access is not changed.</span></span>  
  
-   <span data-ttu-id="ba3f2-118">Se viene chiamata l'istruzione ALTER DATABASE con una clausola WITH \<termination>(ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), vengono terminati tutti gli handle di file non transazionali aperti.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-118">If you call the ALTER DATABASE statement with a WITH \<termination> clause (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), then all open non-transactional file handles are killed.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ba3f2-119">La terminazione di handle di file aperti può causare la perdita dei dati non salvati da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-119">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="ba3f2-120">Questo comportamento è coerente con quello del file system stesso.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-120">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
 <span data-ttu-id="ba3f2-121">**Effetti della disabilitazione dell'accesso non transazionale**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-121">**Effects of disabling non-transactional access**</span></span>  
  
 <span data-ttu-id="ba3f2-122">La modifica del livello dell'accesso non transazionale a livello del database comporta gli effetti seguenti sulle directory FileTable all'interno della directory a livello di database:</span><span class="sxs-lookup"><span data-stu-id="ba3f2-122">Changing the level of non-transactional access at the database level has the following effects on the FileTable directories under the database-level directory:</span></span>  
  
-   <span data-ttu-id="ba3f2-123">Quando l'accesso viene impostato su **NESSUNO**, tutte le directory FileTable e il relativo contenuto non sono più accessibili o visibili.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-123">When you set access to **NONE**, then all the FileTable directories and their contents are no longer accessible or visible.</span></span>  
  
-   <span data-ttu-id="ba3f2-124">Quando l'accesso viene impostato su **READ_ONLY**, anche tutte le directory FileTable e il relativo contenuto sono in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-124">When you set access to **READ_ONLY**, then all the FileTable directories and their contents are also read-only.</span></span>  
  
 <span data-ttu-id="ba3f2-125">La disabilitazione di FILESTREAM a livello di istanza comporta gli effetti seguenti sulle directory a livello di database nell'istanza e la tabella FileTable all'interno di esse:</span><span class="sxs-lookup"><span data-stu-id="ba3f2-125">Disabling FILESTREAM at the instance level has the following effects on the database-level directories on that instance, and the FileTable directories under them:</span></span>  
  
-   <span data-ttu-id="ba3f2-126">Nessuna delle directory a livello di database nell'istanza è visibile se FILESTREAM è disabilitato a livello di istanza.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-126">None of the database-level directories on the instance are visible if FILESTREAM is disabled at the instance level.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-non-transactional-access-at-the-database-level"></a><a name="HowToDisable"></a> <span data-ttu-id="ba3f2-127">Procedura: Disabilitare e riabilitare l'accesso non transazionale a livello di database</span><span class="sxs-lookup"><span data-stu-id="ba3f2-127">How To: Disable and Re-enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="ba3f2-128">Per altre informazioni, vedere [Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="ba3f2-128">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="ba3f2-129">**Per disabilitare l'accesso non transazionale completo**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-129">**To disable full non-transactional access**</span></span>  
 <span data-ttu-id="ba3f2-130">Chiamare l'istruzione **ALTER DATABASE** e usare SET per impostare il valore di **NON_TRANSACTED_ACCESS** su **READ_ONLY** o **OFF**.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-130">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **READ_ONLY** or **OFF**.</span></span>  
  
```sql  
-- Disable write access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = READ_ONLY );  
GO  
  
-- Disable non-transactional access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = OFF );  
GO  
```  
  
 <span data-ttu-id="ba3f2-131">**Per riabilitare l'accesso non transazionale completo**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-131">**To re-enable full non-transactional access**</span></span>  
 <span data-ttu-id="ba3f2-132">Chiamare l'istruzione **ALTER DATABASE** e usare SET per impostare il valore di **NON_TRANSACTED_ACCESS** su **FULL**.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-132">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **FULL**.</span></span>  
  
```sql  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL );  
GO  
```  
  
###  <a name="how-to-ensure-the-visibility-of-the-filetables-in-a-database"></a><a name="visible"></a> <span data-ttu-id="ba3f2-133">Procedura: Assicurare la visibilità delle tabelle FileTables in un database</span><span class="sxs-lookup"><span data-stu-id="ba3f2-133">How to: Ensure the Visibility of the FileTables in a Database</span></span>  
 <span data-ttu-id="ba3f2-134">Una directory a livello di database e le directory FileTable in essa contenute sono visibili se si verificano tutte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba3f2-134">A database-level directory and the FileTable directories under it are visible when all of these conditions are true:</span></span>  
  
1.  <span data-ttu-id="ba3f2-135">FILESTREAM è abilitato a livello di istanza.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-135">FILESTREAM is enabled at the instance level.</span></span>  
  
2.  <span data-ttu-id="ba3f2-136">L'accesso non transazionale è abilitato a livello di database.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-136">Non-transactional access is enabled at the database level.</span></span>  
  
3.  <span data-ttu-id="ba3f2-137">Una directory valida è stata specificata al livello di database.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-137">A valid directory has been specified at the database level.</span></span>  
  
##  <a name="disabling-and-re-enabling-the-filetable-namespace-at-the-table-level"></a><a name="BasicsEnabling"></a> <span data-ttu-id="ba3f2-138">Disabilitare e riabilitare lo spazio dei nomi FileTable a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="ba3f2-138">Disabling and Re-enabling the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="ba3f2-139">Disabilitando lo spazio dei nomi della tabella FileTable vengono disabilitati tutti i vincoli e i trigger definiti dal sistema creati con la tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-139">Disabling the FileTable namespace disables all the system-defined constraints and triggers that were created with the FileTable.</span></span> <span data-ttu-id="ba3f2-140">Ciò è utile nei casi in cui una tabella FileTable deve essere riorganizzata su larga scala utilizzando operazioni [!INCLUDE[tsql](../../includes/tsql-md.md)] , ma si desidera evitare le spese correlate all'applicazione di semantica della tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-140">This is useful in cases where a FileTable has to be reorganized on a large scale by using [!INCLUDE[tsql](../../includes/tsql-md.md)] operations without incurring the expense of enforcing FileTable semantics.</span></span> <span data-ttu-id="ba3f2-141">Queste operazioni possono, tuttavia, lasciare la tabella FileTable in uno stato non coerente e impedire l'operazione di abilitazione dello spazio dei nomi di Filetable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-141">However these operations can leave the FileTable in an inconsistent state, and can prevent the re-enabling of the FileTable namespace.</span></span>  
  
 <span data-ttu-id="ba3f2-142">La disabilitazione di uno spazio dei nomi FileTable comporta i risultati riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="ba3f2-142">Disabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="ba3f2-143">Le colonne e i dati della tabella FileTable non vengono eliminati fisicamente dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-143">FileTable columns and data are not physically dropped from the table.</span></span>  
  
-   <span data-ttu-id="ba3f2-144">La directory FileTable, i file e le directory in essa contenute vengono rimossi dal file system e non sono disponibili per l'accesso I/O al file.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-144">The FileTable directory and the files and directories that it contains disappear from the file system and are not available for file i/o access.</span></span>  
  
-   <span data-ttu-id="ba3f2-145">Le colonne della tabella FileTable definite dal sistema non possono essere eliminate e ricreate, diversamente si comportano come colonne ordinarie per le operazioni DML.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-145">System-defined FileTable columns cannot be dropped and recreated; otherwise, however, they behave like ordinary columns for DML operations.</span></span>  
  
-   <span data-ttu-id="ba3f2-146">Gli handle di file aperti impediscono la disabilitazione dei vincoli FileTable, poiché questa operazione richiede un blocco dello schema sulla tabella.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-146">Open file handles prevent the FileTable constraints from being disabled, since this operation requires a schema lock on the table.</span></span>  
  
-   <span data-ttu-id="ba3f2-147">L'applicazione di tutta la semantica FileTable, incluso i vincoli e i trigger definiti dal sistema, si arresta dopo la disabilitazione dello spazio dei nomi FileTable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-147">Enforcement of all the FileTable semantics, including system-defined constraints and triggers, stops after the FileTable namespace is disabled.</span></span>  
  
 <span data-ttu-id="ba3f2-148">La riabilitazione di uno spazio dei nomi FileTable comporta i risultati riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="ba3f2-148">Re-enabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="ba3f2-149">Viene verificata la coerenza della tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-149">The FileTable is checked for consistency.</span></span> <span data-ttu-id="ba3f2-150">Quando vengono individuate incoerenze, viene generato un errore e FileTable rimane disabilitata; in caso contrario la tabella FileTable viene riabilitata.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-150">If inconsistencies are found, then an error is raised and the FileTable remains disabled; otherwise, the FileTable is re-enabled.</span></span>  
  
-   <span data-ttu-id="ba3f2-151">L'applicazione della semantica FileTable, incluso i vincoli e i trigger definiti dal sistema, viene ripristinata.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-151">The enforcement of FileTable semantics, including system-defined constraints and triggers, is restored.</span></span>  
  
-   <span data-ttu-id="ba3f2-152">La directory FileTable, i file e le directory in essa contenute diventano visibili nel file system e disponibili per l'accesso I/O al file.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-152">The FileTable directory and the files and directories that it contains become visible in the file system and become available for file i/o access.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-the-filetable-namespace-at-the-table-level"></a><a name="HowToEnableNS"></a> <span data-ttu-id="ba3f2-153">Procedura: Disabilitare e riabilitare lo spazio dei nomi FileTable a livello di tabella</span><span class="sxs-lookup"><span data-stu-id="ba3f2-153">How To: Disable and Re-enable the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="ba3f2-154">Chiamare l'istruzione ALTER TABLE con l'opzione **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** .</span><span class="sxs-lookup"><span data-stu-id="ba3f2-154">Call the ALTER TABLE statement with the **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** option.</span></span>  
  
 <span data-ttu-id="ba3f2-155">**Per disabilitare lo spazio dei nomi FileTable**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-155">**To disable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    DISABLE FILETABLE_NAMESPACE;  
GO  
```  
  
 <span data-ttu-id="ba3f2-156">**Per riabilitare lo spazio dei nomi FileTable**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-156">**To re-enable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    ENABLE FILETABLE_NAMESPACE;  
GO  
```  
  
##  <a name="killing-open-file-handles-associated-with-a-filetable"></a><a name="BasicsKilling"></a> <span data-ttu-id="ba3f2-157">Terminazione di handle di file aperti associati a una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-157">Killing Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="ba3f2-158">Gli handle aperti per i file archiviati in una tabella FileTable possono impedire l'accesso esclusivo necessario per determinate attività di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-158">Open handles to the files stored in a FileTable can prevent the exclusive access that is required for certain administrative tasks.</span></span> <span data-ttu-id="ba3f2-159">Per consentire attività urgenti, può essere necessario terminare gli handle di file aperti associati a una o più tabelle FileTable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-159">To enable urgent tasks, you may have to kill open file handles associated with one or more FileTables.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ba3f2-160">La terminazione di handle di file aperti può causare la perdita dei dati non salvati da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-160">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="ba3f2-161">Questo comportamento è coerente con quello del file system stesso.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-161">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
###  <a name="how-to-get-a-list-of-open-file-handles-associated-with-a-filetable"></a><a name="HowToListOpen"></a> <span data-ttu-id="ba3f2-162">Procedura: Recuperare un elenco di handle di file aperti associati a una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-162">How To: Get a List of Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="ba3f2-163">Eseguire una query sulla vista del catalogo [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba3f2-163">Query the catalog view [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.dm_filestream_non_transacted_handles;  
GO  
```  
  
###  <a name="how-to-kill-open-file-handles-associated-with-a-filetable"></a><a name="HowToKill"></a> <span data-ttu-id="ba3f2-164">Procedura: Terminare gli handle di file aperti associati a una tabella FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-164">How To: Kill Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="ba3f2-165">Chiamare la stored procedure [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) con gli argomenti appropriati per terminare tutti gli handle di file aperti nel database o nella tabella FileTable o per terminare un handle specifico.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-165">Call the stored procedure [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) with the appropriate arguments to kill all open file handles in the database or in the FileTable, or to kill a specific handle.</span></span>  
  
```  
USE database_name;  
  
-- Kill all open handles in all the filetables in the database.  
EXEC sp_kill_filestream_non_transacted_handles;  
GO  
  
-- Kill all open handles in a single filetable.  
EXEC sp_kill_filestream_non_transacted_handles @table_name = 'filetable_name';  
GO  
  
-- Kill a single handle.  
EXEC sp_kill_filestream_non_transacted_handles @handle_id = integer_handle_id;  
GO  
```  
  
###  <a name="how-to-identify-the-locks-held-by-filetables"></a><a name="HowToIdentifyLocks"></a> <span data-ttu-id="ba3f2-166">Procedura: Identificare i blocchi usati da tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-166">How to: Identify the Locks Held by FileTables</span></span>  
 <span data-ttu-id="ba3f2-167">La maggior parte dei blocchi applicati da tabelle FileTable corrisponde a file aperti dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-167">Most locks taken by FileTables correspond to files opened by applications.</span></span>  
  
 <span data-ttu-id="ba3f2-168">**Identificazione di file aperti e blocchi associati**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-168">**To identify open files and the associated locks**</span></span>  
 <span data-ttu-id="ba3f2-169">Aggiungere il campo **request_owner_id** nella vista a gestione dinamica [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) con il campo **fcb_id** in [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba3f2-169">Join the **request_owner_id** field in the dynamic management view [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) with the **fcb_id** field in [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span> <span data-ttu-id="ba3f2-170">In alcuni casi, il blocco non corrisponde a un solo handle di file aperto.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-170">In some cases, the lock does not correspond to a single open file handle.</span></span>  
  
```sql  
SELECT opened_file_name  
    FROM sys.dm_filestream_non_transacted_handles  
    WHERE fcb_id IN  
        ( SELECT request_owner_id FROM sys.dm_tran_locks );  
GO  
```  
  
##  <a name="filetable-security"></a><a name="BasicsSecurity"></a> <span data-ttu-id="ba3f2-171">Sicurezza delle tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-171">FileTable Security</span></span>  
 <span data-ttu-id="ba3f2-172">I file e le directory archiviati nelle tabelle FileTable sono protetti solo dalla sicurezza di SQL.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-172">The files and directories stored in FileTables are secured by SQL Server security only.</span></span> <span data-ttu-id="ba3f2-173">La sicurezza basata sulla tabella e sulla colonna è applicata per l'accesso al file system nonché per l'accesso a [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ba3f2-173">Table and column-based security is enforced for file system access as well as [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="ba3f2-174">Le API di sicurezza del file system di Windows e le impostazioni ACL non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-174">Windows file system security APIs and ACL settings are not supported.</span></span>  
  
 <span data-ttu-id="ba3f2-175">Alle tabelle File Table vengono applicate anche le autorizzazioni di sicurezza e accesso applicabili a filegroup e contenitori FILESTREAM, in quanto i dati dei file vengono archiviati come colonna FILESTREAM nella tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-175">The security and access permissions that are applicable to FILESTREAM filegroups and containers also apply to FileTables, since the file data is stored as a FILESTREAM column in the FileTable.</span></span>  
  
 <span data-ttu-id="ba3f2-176">**Sicurezza delle tabelle FileTable e accesso Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-176">**FileTable Security and Transact-SQL Access**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="ba3f2-177">L'accesso ai dati nelle tabelle FileTable è protetto con la stessa modalità di qualsiasi altra tabella.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-177">access to data in FileTables is secured in the same way as any other table.</span></span> <span data-ttu-id="ba3f2-178">Per ogni operazione di accesso o modifica dei dati, vengono effettuati controlli di sicurezza appropriati a livello di tabella e colonna.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-178">Appropriate table and column-level security checks are done for every operation that accesses or changes the data.</span></span>  
  
 <span data-ttu-id="ba3f2-179">**Sicurezza delle tabelle FileTable e accesso al file system**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-179">**FileTable Security and File System Access**</span></span>  
 <span data-ttu-id="ba3f2-180">Per aprire un handle per una directory o un file archiviato nella tabella FileTable tramite API del file system, saranno necessarie autorizzazioni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appropriate per l'intera riga nella tabella FileTable (ovvero autorizzazioni a livello di tabella).</span><span class="sxs-lookup"><span data-stu-id="ba3f2-180">File system APIs require appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions on the entire row in the FileTable (that is, table-level permission) to open a handle to a file or directory stored in the FileTable.</span></span> <span data-ttu-id="ba3f2-181">Se l'utente non dispone dell'autorizzazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appropriata per una qualsiasi colonna nella tabella FileTable, l'accesso al file system viene negato.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-181">If the user does not have the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission on any column in the FileTable, then file system access is denied.</span></span>  
  
##  <a name="backup-and-filetables"></a><a name="OtherBackup"></a> <span data-ttu-id="ba3f2-182">Backup e tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-182">Backup and FileTables</span></span>  
 <span data-ttu-id="ba3f2-183">Quando si utilizza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per eseguire il backup di una tabella FileTable, viene eseguito il backup dei dati FILESTREAM con i dati strutturati nel database.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-183">When you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to back up a FileTable, the FILESTREAM data is backed up with the structured data in the database.</span></span> <span data-ttu-id="ba3f2-184">Se non si desidera eseguire il backup dei dati FILESTREAM con i dati relazionali, è possibile utilizzare un backup parziale per escludere i filegroup FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-184">If you do not want to back up FILESTREAM data with relational data, you can use a partial backup to exclude FILESTREAM filegroups.</span></span>  
  
 <span data-ttu-id="ba3f2-185">**Consistenza transazionale dei backup di FileTable**</span><span class="sxs-lookup"><span data-stu-id="ba3f2-185">**Transactional Consistency of FileTable Backups**</span></span>  
  
 <span data-ttu-id="ba3f2-186">Molti strumenti e operazioni di amministrazione, quali backup, backup del log e replica transazionale, leggono dati coerenti a livello di transazione tramite la lettura dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-186">Many administrative tools and operations, (including backup, log backup, and transactional replication) read transactionally consistent data by reading the transaction logs.</span></span> <span data-ttu-id="ba3f2-187">A questo punto, leggono tutti i dati FILESTREAM aggiornati come parte di una transazione.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-187">At this time, they read any FILESTREAM data updated as part of a transaction.</span></span> <span data-ttu-id="ba3f2-188">Quando l'accesso non transazionale non è abilitato a livello di database, questi strumenti e operazioni funzionano con coerenza transazionale completa.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-188">When non-transactional access is not enabled at the database level, these tools and operations work with full transactional consistency.</span></span>  
  
 <span data-ttu-id="ba3f2-189">Quando invece è abilitato l'accesso non transazionale completo, una tabella FileTable potrebbe contenere dati aggiornati più recentemente (tramite un aggiornamento non transazionale) rispetto alla transazione letta dallo strumento o dal processo dal log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-189">However, when full non-transactional access is enabled, then a FileTable could contain data that was updated more recently (through a non-transactional update) than the transaction that the tool or process is reading from the transaction log.</span></span> <span data-ttu-id="ba3f2-190">Ciò significa che un'operazione di ripristino temporizzata di una transazione specifica può contenere dati FILESTREAM più recenti di tale transazione.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-190">This means that a "point in time" restore operation to a specific transaction may contain FILESTREAM data that is more recent than that transaction.</span></span> <span data-ttu-id="ba3f2-191">Si tratta del comportamento previsto quando nelle tabelle FileTable sono consentiti gli aggiornamenti non transazionali.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-191">This is the expected behavior when non-transactional updates are allowed on FileTables.</span></span>  
  
##  <a name="sql-server-profiler-and-filetables"></a><a name="Monitor"></a> <span data-ttu-id="ba3f2-192">SQL Server Profiler e tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-192">SQL Server Profiler and FileTables</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ba3f2-193">Il profiler può acquisire le operazioni di Windows File Open e File Close nell'output di traccia per i file archiviati in una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-193">Profiler can capture the Windows File Open and File Close operations in trace output for files that are stored in a FileTable.</span></span>  
  
##  <a name="auditing-and-filetables"></a><a name="OtherAuditing"></a> <span data-ttu-id="ba3f2-194">Controllo e tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-194">Auditing and FileTables</span></span>  
 <span data-ttu-id="ba3f2-195">È possibile controllare una tabella FileTable proprio come qualsiasi altra tabella.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-195">FileTable can be audited just like any other table.</span></span> <span data-ttu-id="ba3f2-196">I modelli di accesso Win32, tuttavia, non sono operazioni basate su set.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-196">Howerver, Win32 access patterns are not set based operations.</span></span> <span data-ttu-id="ba3f2-197">Una singola azione nel file system si traduce in più operazioni DML Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-197">A single action in the file system translates into multiple Transact-SQL DML operations.</span></span> <span data-ttu-id="ba3f2-198">L'apertura di un file in Microsoft Word, ad esempio, si traduce in più operazioni di apertura/chiusura/creazione/ridenominazione/eliminazione e nelle attività DML Transact-SQL corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-198">For example, opening a file in Microsoft Word translates into multiple open/close/create/rename/delete operations and corresponding Transact-SQL DML activities.</span></span> <span data-ttu-id="ba3f2-199">Ciò comporta record di controllo dettagliati in cui è difficile correlare i record tra azioni del file system e i record di controllo DML Transact-SQL corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-199">This results in verbose audit records where it is hard to correlate records between file system actions and corresponding Transact-SQL DML audit records.</span></span>  
  
##  <a name="dbcc-and-filetables"></a><a name="OtherDBCC"></a> <span data-ttu-id="ba3f2-200">DBCC e tabelle FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-200">DBCC and FileTables</span></span>  
 <span data-ttu-id="ba3f2-201">È possibile utilizzare DBCC CHECKCONSTRAINTS per convalidare i vincoli su una tabella FileTable, inclusi i vincoli definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="ba3f2-201">You can use DBCC CHECKCONSTRAINTS to validate the constraints on a FileTable including system-defined constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3f2-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba3f2-202">See Also</span></span>  
 <span data-ttu-id="ba3f2-203">[Compatibilità di FileTable con altre funzionalità di SQL Server](filetable-compatibility-with-other-sql-server-features.md) </span><span class="sxs-lookup"><span data-stu-id="ba3f2-203">[FileTable Compatibility with Other SQL Server Features](filetable-compatibility-with-other-sql-server-features.md) </span></span>  
 [<span data-ttu-id="ba3f2-204">DDL, funzioni, stored procedure e viste FileTable</span><span class="sxs-lookup"><span data-stu-id="ba3f2-204">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
