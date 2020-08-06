---
title: Compattare un file | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkfile.f1
helpviewer_keywords:
- shrinking files
- decreasing file size
- databases [SQL Server], shrinking
- reducing file size
- size [SQL Server], files
- file size [SQL Server]
ms.assetid: ce5c8798-c039-4ab2-81e7-90a8d688b893
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac69e4bd2db3ef7fe0815d235dd1de7d3396b302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712008"
---
# <a name="shrink-a-file"></a><span data-ttu-id="841ea-102">Compattare un file</span><span class="sxs-lookup"><span data-stu-id="841ea-102">Shrink a File</span></span>
  <span data-ttu-id="841ea-103">In questo argomento si illustra come compattare un file di dati o di log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="841ea-103">This topic describes how to shrink a data or log file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="841ea-104">Compattando i file di dati si recupera spazio spostando le pagine di dati dalla fine del file allo spazio non occupato più vicino all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="841ea-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="841ea-105">Quando alla fine del file viene creato sufficiente spazio libero, le pagine di dati possono essere deallocate e restituite al file system.</span><span class="sxs-lookup"><span data-stu-id="841ea-105">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
 <span data-ttu-id="841ea-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="841ea-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="841ea-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="841ea-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="841ea-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="841ea-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="841ea-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="841ea-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="841ea-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="841ea-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="841ea-111">**Per compattare un file di dati o di log usando:**</span><span class="sxs-lookup"><span data-stu-id="841ea-111">**To shrink a data or log file, using:**</span></span>  
  
     [<span data-ttu-id="841ea-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="841ea-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="841ea-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="841ea-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="841ea-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="841ea-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="841ea-115">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="841ea-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="841ea-116">Le dimensioni del file di dati primario non possono essere inferiori a quelle del file primario nel database model.</span><span class="sxs-lookup"><span data-stu-id="841ea-116">The primary data file cannot be made smaller than the size of the primary file in the model database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="841ea-117">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="841ea-117">Recommendations</span></span>  
  
-   <span data-ttu-id="841ea-118">I dati spostati per ridurre un file possono essere dispersi in qualsiasi percorso disponibile nel file,</span><span class="sxs-lookup"><span data-stu-id="841ea-118">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="841ea-119">provocando la frammentazione dell'indice e rallentando le prestazioni di query che eseguono ricerche in un intervallo dell'indice</span><span class="sxs-lookup"><span data-stu-id="841ea-119">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="841ea-120">Per eliminare la frammentazione, valutare la possibilità di ricompilare gli indici sul file dopo la compattazione.</span><span class="sxs-lookup"><span data-stu-id="841ea-120">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="841ea-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="841ea-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="841ea-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="841ea-122">Permissions</span></span>  
 <span data-ttu-id="841ea-123">È richiesta l'appartenenza al ruolo predefinito del server **sysadmin** o al ruolo predefinito del database **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="841ea-123">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="841ea-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="841ea-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="841ea-125">Per compattare un file di dati o di log</span><span class="sxs-lookup"><span data-stu-id="841ea-125">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="841ea-126">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="841ea-126">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="841ea-127">Espandere **Database** , quindi fare clic con il pulsante destro del mouse sul database che si desidera compattare.</span><span class="sxs-lookup"><span data-stu-id="841ea-127">Expand **Databases** and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="841ea-128">Scegliere **Compatta**dal menu **Attività**, quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="841ea-128">Point to **Tasks**, point to **Shrink**, and then click **Files**.</span></span>  
  
     <span data-ttu-id="841ea-129">**Database**</span><span class="sxs-lookup"><span data-stu-id="841ea-129">**Database**</span></span>  
     <span data-ttu-id="841ea-130">Consente di visualizzare il nome del database selezionato.</span><span class="sxs-lookup"><span data-stu-id="841ea-130">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="841ea-131">**Tipo di file**</span><span class="sxs-lookup"><span data-stu-id="841ea-131">**File type**</span></span>  
     <span data-ttu-id="841ea-132">Consente di selezionare il tipo di file.</span><span class="sxs-lookup"><span data-stu-id="841ea-132">Select the file type for the file.</span></span> <span data-ttu-id="841ea-133">È possibile scegliere tra file di **Dati** e file di **Log** .</span><span class="sxs-lookup"><span data-stu-id="841ea-133">The available choices are **Data** and **Log** files.</span></span> <span data-ttu-id="841ea-134">La selezione predefinita è **Dati**.</span><span class="sxs-lookup"><span data-stu-id="841ea-134">The default selection is **Data**.</span></span> <span data-ttu-id="841ea-135">La selezione di un tipo di filegroup diverso determina la conseguente modifica delle selezioni negli altri campi.</span><span class="sxs-lookup"><span data-stu-id="841ea-135">Selecting a different filegroup type changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="841ea-136">**Filegroup**</span><span class="sxs-lookup"><span data-stu-id="841ea-136">**Filegroup**</span></span>  
     <span data-ttu-id="841ea-137">Consente di selezionare un filegroup nell'elenco dei filegroup associato al **Tipo file** selezionato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="841ea-137">Select a filegroup from the list of Filegroups associated with the selected **File type** above.</span></span> <span data-ttu-id="841ea-138">La selezione di un filegroup diverso determina la conseguente modifica delle selezioni negli altri campi.</span><span class="sxs-lookup"><span data-stu-id="841ea-138">Selecting a different filegroup changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="841ea-139">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="841ea-139">**File name**</span></span>  
     <span data-ttu-id="841ea-140">Consente di selezionare un file nell'elenco dei file disponibili relativo al filegroup e al tipo di file selezionati.</span><span class="sxs-lookup"><span data-stu-id="841ea-140">Select a file from the list of available files of the selected filegroup and file type.</span></span>  
  
     <span data-ttu-id="841ea-141">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="841ea-141">**Location**</span></span>  
     <span data-ttu-id="841ea-142">Visualizza il percorso completo del file attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="841ea-142">Displays the full path to the currently selected file.</span></span> <span data-ttu-id="841ea-143">Il percorso non è modificabile, ma può essere copiato negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="841ea-143">The path is not editable, but it can be copied to the clipboard.</span></span>  
  
     <span data-ttu-id="841ea-144">**Spazio allocato**</span><span class="sxs-lookup"><span data-stu-id="841ea-144">**Currently allocated space**</span></span>  
     <span data-ttu-id="841ea-145">In caso di file di dati, visualizza lo spazio attualmente allocato.</span><span class="sxs-lookup"><span data-stu-id="841ea-145">For data files, displays the current allocated space.</span></span> <span data-ttu-id="841ea-146">In caso di file di log, visualizza lo spazio attualmente allocato calcolato in base all'output di DBCC SQLPERF(LOGSPACE).</span><span class="sxs-lookup"><span data-stu-id="841ea-146">For log files, displays the current allocated space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="841ea-147">**Spazio disponibile**</span><span class="sxs-lookup"><span data-stu-id="841ea-147">**Available free space**</span></span>  
     <span data-ttu-id="841ea-148">In caso di file di dati, visualizza lo spazio attualmente disponibile calcolato in base all'output di DBCC SHOWFILESTATS(fileid).</span><span class="sxs-lookup"><span data-stu-id="841ea-148">For data files, displays the current available free space computed from the output of DBCC SHOWFILESTATS(fileid).</span></span> <span data-ttu-id="841ea-149">In caso di file di log, visualizza lo spazio attualmente disponibile calcolato in base all'output di DBCC SQLPERF(LOGSPACE).</span><span class="sxs-lookup"><span data-stu-id="841ea-149">For log files, displays the current available free space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="841ea-150">**Rilascia spazio inutilizzato**</span><span class="sxs-lookup"><span data-stu-id="841ea-150">**Release unused space**</span></span>  
     <span data-ttu-id="841ea-151">Causa il rilascio al sistema operativo dello spazio non usato nei file e compatta il file fino all'ultimo extent allocato, riducendo le dimensioni del file senza spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="841ea-151">Cause any unused space in the files to be released to the operating system and shrink the file to the last allocated extent, reducing the file size without moving any data.</span></span> <span data-ttu-id="841ea-152">Non viene eseguito alcun tentativo di rilocazione delle righe in pagine non allocate.</span><span class="sxs-lookup"><span data-stu-id="841ea-152">No attempt is made to relocate rows to unallocated pages.</span></span>  
  
     <span data-ttu-id="841ea-153">**Riorganizza le pagine prima di rilasciare lo spazio inutilizzato**</span><span class="sxs-lookup"><span data-stu-id="841ea-153">**Reorganize pages before releasing unused space**</span></span>  
     <span data-ttu-id="841ea-154">Equivale a eseguire DBCC SHRINKFILE specificando le dimensioni del file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="841ea-154">Equivalent to executing DBCC SHRINKFILE specifying the target file size.</span></span> <span data-ttu-id="841ea-155">Quando questa opzione è selezionata, è necessario specificare le dimensioni del file di destinazione nella casella **Dimensioni file compattato** .</span><span class="sxs-lookup"><span data-stu-id="841ea-155">When this option is selected, the user must specify a target file size in the **Shrink file to** box.</span></span>  
  
     <span data-ttu-id="841ea-156">**Dimensioni file compattato**</span><span class="sxs-lookup"><span data-stu-id="841ea-156">**Shrink file to**</span></span>  
     <span data-ttu-id="841ea-157">Consente di specificare le dimensioni del file di destinazione per l'operazione di compattazione.</span><span class="sxs-lookup"><span data-stu-id="841ea-157">Specifies the target file size for the shrink operation.</span></span> <span data-ttu-id="841ea-158">Le dimensioni non possono essere minori dello spazio allocato o maggiori del numero di extent totali allocati al file.</span><span class="sxs-lookup"><span data-stu-id="841ea-158">The size cannot be less than the current allocated space or more than the total extents allocated to the file.</span></span> <span data-ttu-id="841ea-159">L'immissione di un valore non compreso nel limite minimo o massimo determinerà il ripristino dei valori minimo e massimo in seguito alla modifica dello stato attivo o alla pressione di un pulsante sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="841ea-159">Entering a value beyond the minimum or the maximum will revert to the min or the max once the focus is changed or when any of the buttons on the toolbar are clicked.</span></span>  
  
     <span data-ttu-id="841ea-160">**Svuota il file eseguendo la migrazione dei dati in altri file nello stesso filegroup**</span><span class="sxs-lookup"><span data-stu-id="841ea-160">**Empty file by migrating the data to other files in the same filegroup**</span></span>  
     <span data-ttu-id="841ea-161">Consente di eseguire la migrazione di tutti i dati dal file specificato.</span><span class="sxs-lookup"><span data-stu-id="841ea-161">Migrate all data from the specified file.</span></span> <span data-ttu-id="841ea-162">Questa opzione consente l'eliminazione del file tramite l'istruzione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="841ea-162">This option allows the file to be dropped using the ALTER DATABASE statement.</span></span> <span data-ttu-id="841ea-163">Questa opzione equivale a eseguire DBCC SHRINKFILE con l'opzione EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="841ea-163">This option is equivalent to executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
4.  <span data-ttu-id="841ea-164">Selezionare il tipo e il nome del file.</span><span class="sxs-lookup"><span data-stu-id="841ea-164">Select the file type and file name.</span></span>  
  
5.  <span data-ttu-id="841ea-165">Facoltativamente, selezionare la casella di controllo **Rilascia spazio inutilizzato** .</span><span class="sxs-lookup"><span data-stu-id="841ea-165">Optionally, select the **Release unused space** check box.</span></span>  
  
     <span data-ttu-id="841ea-166">Se selezionata, questa opzione consente di rilasciare al sistema operativo lo spazio inutilizzato del file e di compattare il file fino all'ultimo extent allocato,</span><span class="sxs-lookup"><span data-stu-id="841ea-166">Selecting this option causes any unused space in the file to be released to the operating system and shrinks the file to the last allocated extent.</span></span> <span data-ttu-id="841ea-167">riducendo quindi le dimensioni del file senza spostare i dati.</span><span class="sxs-lookup"><span data-stu-id="841ea-167">This reduces the file size without moving any data.</span></span>  
  
6.  <span data-ttu-id="841ea-168">Facoltativamente, selezionare la casella di controllo **Riorganizza i file prima di rilasciare lo spazio inutilizzato** .</span><span class="sxs-lookup"><span data-stu-id="841ea-168">Optionally, select the **Reorganize files before releasing unused space** check box.</span></span> <span data-ttu-id="841ea-169">Se si seleziona questa opzione, è necessario specificare il valore di **Dimensioni file compattato** .</span><span class="sxs-lookup"><span data-stu-id="841ea-169">If this is selected, the **Shrink file to** value must be specified.</span></span> <span data-ttu-id="841ea-170">Per impostazione predefinita, questa opzione è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="841ea-170">By default, the option is cleared.</span></span>  
  
     <span data-ttu-id="841ea-171">Se selezionata, questa opzione consente di rilasciare al sistema operativo lo spazio inutilizzato del file e di spostare, se possibile, le righe in pagine non allocate.</span><span class="sxs-lookup"><span data-stu-id="841ea-171">Selecting this option causes any unused space in the file to be released to the operating system and tries to relocate rows to unallocated pages.</span></span>  
  
7.  <span data-ttu-id="841ea-172">Facoltativamente, immettere la percentuale massima di spazio libero da rendere disponibile nel database dopo la compattazione.</span><span class="sxs-lookup"><span data-stu-id="841ea-172">Optionally, enter the maximum percentage of free space to be left in the database file after the database has been shrunk.</span></span> <span data-ttu-id="841ea-173">I valori consentiti sono compresi tra 0 e 99.</span><span class="sxs-lookup"><span data-stu-id="841ea-173">Permissible values are between 0 and 99.</span></span> <span data-ttu-id="841ea-174">Questa opzione è disponibile solo se l'opzione **Riorganizza i file prima di rilasciare lo spazio inutilizzato** è abilitata.</span><span class="sxs-lookup"><span data-stu-id="841ea-174">This option is only available when **Reorganize files before releasing unused space** is enabled.</span></span>  
  
8.  <span data-ttu-id="841ea-175">Facoltativamente, selezionare la casella di controllo **Svuota il file eseguendo la migrazione dei dati in altri file nello stesso filegroup** .</span><span class="sxs-lookup"><span data-stu-id="841ea-175">Optionally, select the **Empty file by migrating the data to other files in the same filegroup** check box.</span></span>  
  
     <span data-ttu-id="841ea-176">Se selezionata, questa opzione consente di spostare tutti i dati dal file selezionato ad altri file nel filegroup.</span><span class="sxs-lookup"><span data-stu-id="841ea-176">Selecting this option moves all data from the specified file to other files in the filegroup.</span></span> <span data-ttu-id="841ea-177">È quindi possibile eliminare il file vuoto.</span><span class="sxs-lookup"><span data-stu-id="841ea-177">The empty file can then be deleted.</span></span> <span data-ttu-id="841ea-178">L'opzione è equivalente all'esecuzione dell'istruzione DBCC SHRINKFILE con l'opzione EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="841ea-178">This option is the same as executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
9. <span data-ttu-id="841ea-179">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="841ea-179">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="841ea-180">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="841ea-180">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="841ea-181">Per compattare un file di dati o di log</span><span class="sxs-lookup"><span data-stu-id="841ea-181">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="841ea-182">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="841ea-182">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="841ea-183">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="841ea-183">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="841ea-184">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="841ea-184">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="841ea-185">In questo esempio si usano [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) per compattare le dimensioni di un file di dati denominato `DataFile1` nel database `UserDB` a 7 MB.</span><span class="sxs-lookup"><span data-stu-id="841ea-185">This example uses [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) to shrink the size of a data file named `DataFile1` in the `UserDB` database to 7 MB.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKFILE1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkfile1)]  
  
## <a name="see-also"></a><span data-ttu-id="841ea-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="841ea-186">See Also</span></span>  
 <span data-ttu-id="841ea-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="841ea-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span></span>  
 <span data-ttu-id="841ea-188">[Compattare un database](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="841ea-188">[Shrink a Database](shrink-a-database.md) </span></span>  
 <span data-ttu-id="841ea-189">[Eliminare file di dati o file di log da un database](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="841ea-189">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 <span data-ttu-id="841ea-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="841ea-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="841ea-191">sys.database_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="841ea-191">sys.database_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql)  
  
  
