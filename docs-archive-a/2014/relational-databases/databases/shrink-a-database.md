---
title: Compattare un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkdatabase.f1
helpviewer_keywords:
- shrinking databases
- databases [SQL Server], shrinking
- decreasing database size
- database shrinking [SQL Server]
- reducing database size
ms.assetid: 83afbf74-fd50-4c39-831c-b1f473a50620
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246036bfea6dc8431f878165330f7f0571949897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712011"
---
# <a name="shrink-a-database"></a><span data-ttu-id="9986d-102">Compattare un database</span><span class="sxs-lookup"><span data-stu-id="9986d-102">Shrink a Database</span></span>
  <span data-ttu-id="9986d-103">In questo argomento si illustra come compattare un database mediante Esplora oggetti in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9986d-103">This topic describes how to shrink a database by using Object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9986d-104">Compattando i file di dati si recupera spazio spostando le pagine di dati dalla fine del file allo spazio non occupato più vicino all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="9986d-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="9986d-105">Quando alla fine del file viene creato sufficiente spazio libero, le pagine di dati possono essere deallocate e restituite al file system.</span><span class="sxs-lookup"><span data-stu-id="9986d-105">When enough free space is created at the end of the file, data pages at end of the file can be deallocated and returned to the file system.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9986d-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9986d-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9986d-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="9986d-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9986d-108">Non è possibile ridurre il database a dimensioni inferiori a quelle minime.</span><span class="sxs-lookup"><span data-stu-id="9986d-108">The database cannot be made smaller than the minimum size of the database.</span></span> <span data-ttu-id="9986d-109">Le dimensioni minime corrispondono alle dimensioni specificate quando il database è stato inizialmente creato o alle ultime dimensioni impostate in modo esplicito mediante un'operazione di modifica delle dimensioni dei file, ad esempio DBCC SHRINKFILE.</span><span class="sxs-lookup"><span data-stu-id="9986d-109">The minimum size is the size specified when the database was originally created, or the last explicit size set by using a file-size-changing operation, such as DBCC SHRINKFILE.</span></span> <span data-ttu-id="9986d-110">Pertanto, se originariamente è stato creato un database con dimensioni pari a 10 MB e le dimensioni sono aumentate fino a 100 MB, è possibile compattare il database fino a un minimo di 10 MB, anche se tutti i dati nel database sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="9986d-110">For example, if a database was originally created with a size of 10 MB and grew to 100 MB, the smallest size the database could be reduced to is 10 MB, even if all the data in the database has been deleted.</span></span>  
  
-   <span data-ttu-id="9986d-111">Non è possibile compattare un database mentre ne viene eseguito il backup</span><span class="sxs-lookup"><span data-stu-id="9986d-111">You cannot shrink a database while the database is being backed up.</span></span> <span data-ttu-id="9986d-112">e non è possibile eseguire il backup di un database mentre è in corso un'operazione di compattazione.</span><span class="sxs-lookup"><span data-stu-id="9986d-112">Conversely, you cannot backup a database while a shrink operation on the database is in process.</span></span>  
  
-   <span data-ttu-id="9986d-113">Se viene rilevato un indice columnstore ottimizzato in memoria xVelocity, DBCC SHRINKDATABASE avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="9986d-113">DBCC SHRINKDATABASE will fail when it encounters an xVelocity memory optimized columnstore index.</span></span> <span data-ttu-id="9986d-114">L'operazione avrà esito positivo se completata prima del rilevamento dell'indice columnstore ottenendo dimensioni del database inferiori.</span><span class="sxs-lookup"><span data-stu-id="9986d-114">Work completed before encountering the columnstore index will succeed so the database might be smaller.</span></span> <span data-ttu-id="9986d-115">Per completare DBCC SHRINKDATABASE, disabilitare tutti gli indici columnstore prima di eseguire DBCC SHRINKDATABASE, quindi ricompilare gli indici columnstore.</span><span class="sxs-lookup"><span data-stu-id="9986d-115">To complete DBCC SHRINKDATABASE, disable all columnstore indexes before executing DBCC SHRINKDATABASE, and then rebuild the columnstore indexes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="9986d-116">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="9986d-116">Recommendations</span></span>  
  
-   <span data-ttu-id="9986d-117">Per visualizzare la quantità corrente di spazio disponibile, cioè non allocato, nel database.</span><span class="sxs-lookup"><span data-stu-id="9986d-117">To view the current amount of free (unallocated) space in the database.</span></span> <span data-ttu-id="9986d-118">Per altre informazioni, vedere [Visualizzare le informazioni sullo spazio allocato ai dati e ai log per un database](display-data-and-log-space-information-for-a-database.md)</span><span class="sxs-lookup"><span data-stu-id="9986d-118">For more information, see [Display Data and Log Space Information for a Database](display-data-and-log-space-information-for-a-database.md)</span></span>  
  
-   <span data-ttu-id="9986d-119">Quando si pianifica la compattazione di un database, considerare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9986d-119">Consider the following information when you plan to shrink a database:</span></span>  
  
    -   <span data-ttu-id="9986d-120">Un'operazione di compattazione è più efficace dopo l'esecuzione di un'operazione che crea una quantità elevata di spazio inutilizzato, ad esempio il troncamento o l'eliminazione di una tabella.</span><span class="sxs-lookup"><span data-stu-id="9986d-120">A shrink operation is most effective after an operation that creates lots of unused space, such as a truncate table or a drop table operation.</span></span>  
  
    -   <span data-ttu-id="9986d-121">La maggior parte dei database richiede spazio disponibile per lo svolgimento delle normali attività quotidiane.</span><span class="sxs-lookup"><span data-stu-id="9986d-121">Most databases require some free space to be available for regular day-to-day operations.</span></span> <span data-ttu-id="9986d-122">Se si compatta ripetutamente un database ma le sue dimensioni aumentano di nuovo significa che lo spazio compattato è necessario per le normali operazioni.</span><span class="sxs-lookup"><span data-stu-id="9986d-122">If you shrink a database repeatedly and notice that the database size grows again, this indicates that the space that was shrunk is required for regular operations.</span></span> <span data-ttu-id="9986d-123">In questi casi è inutile compattare ripetutamente il database.</span><span class="sxs-lookup"><span data-stu-id="9986d-123">In these cases, repeatedly shrinking the database is a wasted operation.</span></span>  
  
    -   <span data-ttu-id="9986d-124">L'operazione di compattazione generalmente aumenta la frammentazione degli indici del database.</span><span class="sxs-lookup"><span data-stu-id="9986d-124">A shrink operation does not preserve the fragmentation state of indexes in the database, and generally increases fragmentation to a degree.</span></span> <span data-ttu-id="9986d-125">Questo è un ulteriore motivo per evitare di compattare ripetutamente un database.</span><span class="sxs-lookup"><span data-stu-id="9986d-125">This is another reason not to repeatedly shrink the database.</span></span>  
  
    -   <span data-ttu-id="9986d-126">Se non è necessario soddisfare esigenze specifiche, non impostare l'opzione di database AUTO_SHRINK su ON.</span><span class="sxs-lookup"><span data-stu-id="9986d-126">Unless you have a specific requirement, do not set the AUTO_SHRINK database option to ON.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9986d-127">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="9986d-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9986d-128">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="9986d-128">Permissions</span></span>  
 <span data-ttu-id="9986d-129">È richiesta l'appartenenza al ruolo predefinito del server **sysadmin** o al ruolo predefinito del database **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="9986d-129">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9986d-130">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9986d-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="9986d-131">Per compattare un database</span><span class="sxs-lookup"><span data-stu-id="9986d-131">To shrink a database</span></span>  
  
1.  <span data-ttu-id="9986d-132">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="9986d-132">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9986d-133">Espandere **Database**, quindi fare clic con il pulsante destro del mouse sul database che si vuole compattare.</span><span class="sxs-lookup"><span data-stu-id="9986d-133">Expand **Databases**, and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="9986d-134">Scegliere **Attività**, **Compatta**, quindi fare clic su **Database**.</span><span class="sxs-lookup"><span data-stu-id="9986d-134">Point to **Tasks**, point to **Shrink**, and then click **Database**.</span></span>  
  
     <span data-ttu-id="9986d-135">**Database**</span><span class="sxs-lookup"><span data-stu-id="9986d-135">**Database**</span></span>  
     <span data-ttu-id="9986d-136">Consente di visualizzare il nome del database selezionato.</span><span class="sxs-lookup"><span data-stu-id="9986d-136">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="9986d-137">**Spazio allocato**</span><span class="sxs-lookup"><span data-stu-id="9986d-137">**Current allocated space**</span></span>  
     <span data-ttu-id="9986d-138">Consente di visualizzare lo spazio totale utilizzato e inutilizzato per il database selezionato.</span><span class="sxs-lookup"><span data-stu-id="9986d-138">Displays the total used and unused space for the selected database.</span></span>  
  
     <span data-ttu-id="9986d-139">**Spazio disponibile**</span><span class="sxs-lookup"><span data-stu-id="9986d-139">**Available free space**</span></span>  
     <span data-ttu-id="9986d-140">Consente di visualizzare lo spazio disponibile totale nei file di log e di dati del database selezionato.</span><span class="sxs-lookup"><span data-stu-id="9986d-140">Displays the sum of free space in the log and data files of the selected database.</span></span>  
  
     <span data-ttu-id="9986d-141">**Riorganizza i file prima di rilasciare lo spazio inutilizzato**</span><span class="sxs-lookup"><span data-stu-id="9986d-141">**Reorganize files before releasing unused space**</span></span>  
     <span data-ttu-id="9986d-142">La selezione di questa opzione equivale all'esecuzione di DBCC SHRINKDATABASE specificando la percentuale di compattazione.</span><span class="sxs-lookup"><span data-stu-id="9986d-142">Selecting this option is equivalent to executing DBCC SHRINKDATABASE specifying a target percent option.</span></span> <span data-ttu-id="9986d-143">Deselezionare l'opzione equivale all'esecuzione di DBCC SHRINKDATABASE con l'opzione TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="9986d-143">Clearing this option is equivalent to executing DBCC SHRINKDATABASE with TRUNCATEONLY option.</span></span> <span data-ttu-id="9986d-144">Per impostazione predefinita, questa opzione non è selezionata all'apertura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="9986d-144">By default, this option is not selected when the dialog is opened.</span></span> <span data-ttu-id="9986d-145">Se viene selezionata, l'utente deve specificare la percentuale di compattazione.</span><span class="sxs-lookup"><span data-stu-id="9986d-145">If this option is selected, the user must specify a target percent option.</span></span>  
  
     <span data-ttu-id="9986d-146">**Spazio massimo disponibile nei file dopo la compattazione**</span><span class="sxs-lookup"><span data-stu-id="9986d-146">**Maximum free space in files after shrinking**</span></span>  
     <span data-ttu-id="9986d-147">Immettere la massima percentuale di spazio che si desidera sia disponibile nei file del database dopo la compattazione del database.</span><span class="sxs-lookup"><span data-stu-id="9986d-147">Enter the maximum percentage of free space to be left in the database files after the database has been shrunk.</span></span> <span data-ttu-id="9986d-148">I valori consentiti sono compresi tra 0 e 99.</span><span class="sxs-lookup"><span data-stu-id="9986d-148">Permissible values are between 0 and 99.</span></span>  
  
4.  <span data-ttu-id="9986d-149">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9986d-149">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9986d-150">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9986d-150">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="9986d-151">Per compattare un database</span><span class="sxs-lookup"><span data-stu-id="9986d-151">To shrink a database</span></span>  
  
1.  <span data-ttu-id="9986d-152">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9986d-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9986d-153">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="9986d-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9986d-154">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="9986d-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="9986d-155">In questo esempio si utilizza [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) per ridurre le dimensioni dei file di dati e di log nel database `UserDB` e per ottenere il `10` percento di spazio disponibile nel database.</span><span class="sxs-lookup"><span data-stu-id="9986d-155">This example uses [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) to decreases the size of the data and log files in the `UserDB` database and to allow for `10` percent free space in the database.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKDB1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkdb1)]  
  
##  <a name="follow-up-after-you-shrink-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="9986d-156">Completamento: dopo la compattazione di un database</span><span class="sxs-lookup"><span data-stu-id="9986d-156">Follow Up: After you shrink a database</span></span>  
 <span data-ttu-id="9986d-157">I dati spostati per ridurre un file possono essere dispersi in qualsiasi percorso disponibile nel file,</span><span class="sxs-lookup"><span data-stu-id="9986d-157">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="9986d-158">provocando la frammentazione dell'indice e rallentando le prestazioni di query che eseguono ricerche in un intervallo dell'indice</span><span class="sxs-lookup"><span data-stu-id="9986d-158">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="9986d-159">Per eliminare la frammentazione, valutare la possibilità di ricompilare gli indici sul file dopo la compattazione.</span><span class="sxs-lookup"><span data-stu-id="9986d-159">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9986d-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9986d-160">See Also</span></span>  
 <span data-ttu-id="9986d-161">[Compattare un file](shrink-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="9986d-161">[Shrink a File](shrink-a-file.md) </span></span>  
 <span data-ttu-id="9986d-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9986d-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="9986d-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9986d-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="9986d-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9986d-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="9986d-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9986d-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span></span>  
 [<span data-ttu-id="9986d-166">Filegroup e file di database</span><span class="sxs-lookup"><span data-stu-id="9986d-166">Database Files and Filegroups</span></span>](database-files-and-filegroups.md)  
  
  
