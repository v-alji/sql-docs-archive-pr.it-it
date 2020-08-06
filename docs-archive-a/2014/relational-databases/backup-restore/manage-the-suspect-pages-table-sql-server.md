---
title: Gestire la tabella suspect_pages (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
- restoring pages [SQL Server]
- pages [SQL Server], suspect
- pages [SQL Server], restoring
- suspect_pages system table
- suspect pages [SQL Server]
- restoring [SQL Server], pages
ms.assetid: f394d4bc-1518-4e61-97fc-bf184d972e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dd7aea63ae85a16e23ff532c7e18ace3c376a707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637920"
---
# <a name="manage-the-suspect_pages-table-sql-server"></a><span data-ttu-id="10ab3-102">Gestione della tabella suspect_pages (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="10ab3-102">Manage the suspect_pages Table (SQL Server)</span></span>
  <span data-ttu-id="10ab3-103">In questo argomento viene descritto come gestire la tabella **suspect_pages** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10ab3-103">This topic describes how to manage the **suspect_pages** table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="10ab3-104">La tabella **suspect_pages** , usata per la gestione di informazioni sulle pagine sospette, è importante per stabilire se è necessario un ripristino.</span><span class="sxs-lookup"><span data-stu-id="10ab3-104">The **suspect_pages** table is used for maintaining information about suspect pages, and is relevant in helping to decide whether a restore is necessary.</span></span> <span data-ttu-id="10ab3-105">La tabella [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) è contenuta nel [database msdb](../databases/msdb-database.md).</span><span class="sxs-lookup"><span data-stu-id="10ab3-105">The [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) table resides in the [msdb database](../databases/msdb-database.md).</span></span>  
  
 <span data-ttu-id="10ab3-106">Una pagina è considerata "sospetta" quando nel [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] si verifica uno dei seguenti errori quando viene tentata la lettura di una pagina di dati:</span><span class="sxs-lookup"><span data-stu-id="10ab3-106">A page is considered "suspect" when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] encounters one of the following errors when it tries to read a data page:</span></span>  
  
-   <span data-ttu-id="10ab3-107">[Errore 823](../errors-events/mssqlserver-823-database-engine-error.md) causato da un controllo di ridondanza ciclico (CRC) emesso dal sistema operativo, ad esempio un errore del disco (alcuni errori hardware)</span><span class="sxs-lookup"><span data-stu-id="10ab3-107">An [823 error](../errors-events/mssqlserver-823-database-engine-error.md) that was caused by a cyclic redundancy check (CRC) issued by the operating system, such as a disk error (certain hardware errors)</span></span>  
  
-   <span data-ttu-id="10ab3-108">[Errore 824](../errors-events/mssqlserver-824-database-engine-error.md), ad esempio una pagina incompleta (qualsiasi errore logico)</span><span class="sxs-lookup"><span data-stu-id="10ab3-108">An [824 error](../errors-events/mssqlserver-824-database-engine-error.md), such as a torn page (any logical error)</span></span>  
  
 <span data-ttu-id="10ab3-109">L'ID di ogni pagina sospetta viene registrato nella tabella **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="10ab3-109">The page ID of every suspect page is recorded in the **suspect_pages** table.</span></span> <span data-ttu-id="10ab3-110">[!INCLUDE[ssDE](../../includes/ssde-md.md)] registra tutte le pagine sospette rilevate durante la normale elaborazione, ad esempio nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="10ab3-110">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] records any suspect pages encountered during regular processing, such as the following:</span></span>  
  
-   <span data-ttu-id="10ab3-111">Una pagina deve essere letta da una query.</span><span class="sxs-lookup"><span data-stu-id="10ab3-111">A query has to read a page.</span></span>  
  
-   <span data-ttu-id="10ab3-112">Durante un'operazione DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="10ab3-112">During a DBCC CHECKDB operation.</span></span>  
  
-   <span data-ttu-id="10ab3-113">Durante un'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="10ab3-113">During a backup operation.</span></span>  
  
 <span data-ttu-id="10ab3-114">La tabella **suspect_pages** viene aggiornata in base alle necessità durante un'operazione di ripristino, di correzione DBCC o di rimozione del database.</span><span class="sxs-lookup"><span data-stu-id="10ab3-114">The **suspect_pages** table is also updated as necessary during a restore operation, a DBCC repair operation, or a drop database operation.</span></span>  
  
 <span data-ttu-id="10ab3-115">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="10ab3-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="10ab3-116">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="10ab3-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="10ab3-117">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="10ab3-117">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="10ab3-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="10ab3-118">Security</span></span>](#Security)  
  
-   <span data-ttu-id="10ab3-119">**Per gestire la tabella suspect_pages utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="10ab3-119">**To manage the suspect_pages table, using:**</span></span>  
  
     [<span data-ttu-id="10ab3-120">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10ab3-120">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="10ab3-121">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10ab3-121">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="10ab3-122">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="10ab3-122">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="10ab3-123">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="10ab3-123">Recommendations</span></span>  
  
-   <span data-ttu-id="10ab3-124">**Errori registrati nella tabella suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="10ab3-124">**Errors Recorded in suspect_pages Table**</span></span>  
  
     <span data-ttu-id="10ab3-125">La tabella **suspect_pages** include una riga per ogni pagina che ha restituito un errore 824, fino a un limite di 1.000 righe.</span><span class="sxs-lookup"><span data-stu-id="10ab3-125">The **suspect_pages** table contains one row per page that failed with an 824 error, up to a limit of 1,000 rows.</span></span> <span data-ttu-id="10ab3-126">Nella seguente tabella vengono mostrati errori registrati nella colonna **event_type** della tabella **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="10ab3-126">The following table shows errors logged in the **event_type** column of the **suspect_pages** table.</span></span>  
  
    |<span data-ttu-id="10ab3-127">Descrizione dell'errore</span><span class="sxs-lookup"><span data-stu-id="10ab3-127">Error description</span></span>|<span data-ttu-id="10ab3-128">Valore**event_type**</span><span class="sxs-lookup"><span data-stu-id="10ab3-128">**event_type** value</span></span>|  
    |-----------------------|---------------------------|  
    |<span data-ttu-id="10ab3-129">Errore 823 causato da un errore CRC del sistema operativo o errore 824 diverso da un errore nel checksum o da una pagina incompleta (ad esempio un ID pagina errato)</span><span class="sxs-lookup"><span data-stu-id="10ab3-129">823 error caused by an operating system CRC error  or 824 error other than a bad checksum or a torn page (for example, a bad page ID)</span></span>|<span data-ttu-id="10ab3-130">1</span><span class="sxs-lookup"><span data-stu-id="10ab3-130">1</span></span>|  
    |<span data-ttu-id="10ab3-131">Errore nel checksum</span><span class="sxs-lookup"><span data-stu-id="10ab3-131">Bad checksum</span></span>|<span data-ttu-id="10ab3-132">2</span><span class="sxs-lookup"><span data-stu-id="10ab3-132">2</span></span>|  
    |<span data-ttu-id="10ab3-133">Pagina incompleta</span><span class="sxs-lookup"><span data-stu-id="10ab3-133">Torn page</span></span>|<span data-ttu-id="10ab3-134">3</span><span class="sxs-lookup"><span data-stu-id="10ab3-134">3</span></span>|  
    |<span data-ttu-id="10ab3-135">Pagina ripristinata (la pagina è stata ripristinata dopo essere stata contrassegnata come danneggiata)</span><span class="sxs-lookup"><span data-stu-id="10ab3-135">Restored (The page was restored after it was marked bad)</span></span>|<span data-ttu-id="10ab3-136">4</span><span class="sxs-lookup"><span data-stu-id="10ab3-136">4</span></span>|  
    |<span data-ttu-id="10ab3-137">Pagina corretta (la pagina è stata corretta da DBCC, da AlwaysOn o dal mirroring)</span><span class="sxs-lookup"><span data-stu-id="10ab3-137">Repaired (DBCC, AlwaysOn, or mirroring repaired the page)</span></span>|<span data-ttu-id="10ab3-138">5</span><span class="sxs-lookup"><span data-stu-id="10ab3-138">5</span></span>|  
    |<span data-ttu-id="10ab3-139">Pagina deallocata da DBCC</span><span class="sxs-lookup"><span data-stu-id="10ab3-139">Deallocated by DBCC</span></span>|<span data-ttu-id="10ab3-140">7</span><span class="sxs-lookup"><span data-stu-id="10ab3-140">7</span></span>|  
  
     <span data-ttu-id="10ab3-141">Nella tabella **suspect_pages** vengono anche registrati gli errori temporanei.</span><span class="sxs-lookup"><span data-stu-id="10ab3-141">The **suspect_pages** table also records transient errors.</span></span> <span data-ttu-id="10ab3-142">Tra le origini degli errori temporanei rientrano gli errori di I/O, ad esempio un cavo disconnesso, o le pagine che non superano temporaneamente un test di checksum ripetuto.</span><span class="sxs-lookup"><span data-stu-id="10ab3-142">Sources of transient errors include an I/O error (for example, a cable was disconnected) or a page that temporarily fails a repeated checksum test.</span></span>  
  
-   <span data-ttu-id="10ab3-143">**Procedura di aggiornamento della tabella suspect_pages tramite il Motore di database**</span><span class="sxs-lookup"><span data-stu-id="10ab3-143">**How the Database Engine Updates the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="10ab3-144">Il [!INCLUDE[ssDE](../../includes/ssde-md.md)] esegue le azioni seguenti nella tabella **suspect_pages** :</span><span class="sxs-lookup"><span data-stu-id="10ab3-144">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes the following actions on the **suspect_pages** table:</span></span>  
  
    -   <span data-ttu-id="10ab3-145">Se la tabella non è piena, viene aggiornata per ogni errore 824 in modo da segnalare il verificarsi dell'errore e viene incrementato il contatore degli errori.</span><span class="sxs-lookup"><span data-stu-id="10ab3-145">If the table is not full, it is updated for every 824 error, to indicate that an error has occurred, and the error counter is incremented.</span></span> <span data-ttu-id="10ab3-146">Se una pagina contiene un errore dopo l'esecuzione di un'operazione di correzione, ripristino o deallocazione, il conteggio **number_of_errors** corrispondente viene incrementato e la relativa colonna **last_update** viene aggiornata</span><span class="sxs-lookup"><span data-stu-id="10ab3-146">If a page has an error after it is fixed by being repaired, restored, or deallocated, its **number_of_errors** count is incremented and its **last_update** column is updated</span></span>  
  
    -   <span data-ttu-id="10ab3-147">Dopo l'esecuzione di un'operazione di ripristino o di correzione di una pagina elencata, la riga **suspect_pages** viene aggiornata per indicare che la pagina è stata corretta (**event_type** = 5) o ripristinata (**event_type** = 4).</span><span class="sxs-lookup"><span data-stu-id="10ab3-147">After a listed page is fixed by a restore or a repair operation, the operation updates the **suspect_pages** row to indicate that the page is repaired (**event_type** = 5) or restored (**event_type** = 4).</span></span>  
  
    -   <span data-ttu-id="10ab3-148">Se viene eseguito un controllo DBCC, tutte le pagine prive di errori vengono contrassegnate come corrette (**event_type** = 5) o deallocate (**event_type** = 7).</span><span class="sxs-lookup"><span data-stu-id="10ab3-148">If a DBCC check is run, the check marks any error-free pages as repaired (**event_type** = 5) or deallocated (**event_type** = 7).</span></span>  
  
-   <span data-ttu-id="10ab3-149">**Aggiornamenti automatici della tabella suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="10ab3-149">**Automatic Updates to the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="10ab3-150">Un partner di mirroring di database o una replica di disponibilità AlwaysOn aggiorna la tabella **suspect_pages** dopo che un tentativo di leggere una pagina da un file di dati non riesce per una delle seguenti ragioni.</span><span class="sxs-lookup"><span data-stu-id="10ab3-150">A database mirroring partner or AlwaysOn availability replica updates the **suspect_pages** table after an attempt to read a page from a data file fails for one of the following reasons.</span></span>  
  
    -   <span data-ttu-id="10ab3-151">Un errore del 823 causato da un errore CRC del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="10ab3-151">An 823 error that is caused by an operating system CRC error.</span></span>  
  
    -   <span data-ttu-id="10ab3-152">Un errore 824 (danneggiamento logico, ad esempio una pagina incompleta)</span><span class="sxs-lookup"><span data-stu-id="10ab3-152">An 824 error (logical corruption such as a torn page).</span></span>  
  
     <span data-ttu-id="10ab3-153">Le azioni seguenti aggiornano anche automaticamente righe nella tabella **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="10ab3-153">The following actions also automatically update rows in the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="10ab3-154">L'azione DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS aggiorna la tabella **suspect_pages** per indicare ogni pagina deallocata o corretta.</span><span class="sxs-lookup"><span data-stu-id="10ab3-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS updates the **suspect_pages** table to indicate each page that it has deallocated or repaired.</span></span>  
  
    -   <span data-ttu-id="10ab3-155">In seguito a un ripristino (RESTORE) completo del file o della pagina, le voci della pagina vengono contrassegnate come ripristinate.</span><span class="sxs-lookup"><span data-stu-id="10ab3-155">A full, file, or page RESTORE marks the page entries as restored.</span></span>  
  
     <span data-ttu-id="10ab3-156">Le azioni seguenti eliminano automaticamente righe dalla tabella **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="10ab3-156">The following actions automatically delete rows from the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="10ab3-157">ALTER DATABASE REMOVE FILE</span><span class="sxs-lookup"><span data-stu-id="10ab3-157">ALTER DATABASE REMOVE FILE</span></span>  
  
    -   <span data-ttu-id="10ab3-158">DROP DATABASE</span><span class="sxs-lookup"><span data-stu-id="10ab3-158">DROP DATABASE</span></span>  
  
-   <span data-ttu-id="10ab3-159">**Ruolo di gestione dell'amministratore del database**</span><span class="sxs-lookup"><span data-stu-id="10ab3-159">**Maintenance Role of the Database Administrator**</span></span>  
  
     <span data-ttu-id="10ab3-160">Gli amministratori dei database sono responsabili della gestione della tabella, in particolare dell'eliminazione delle righe meno recenti.</span><span class="sxs-lookup"><span data-stu-id="10ab3-160">Database administrators are responsible for managing the table, primarily by deleting old rows.</span></span> <span data-ttu-id="10ab3-161">Poiché le dimensioni della tabella **suspect_pages** sono limitate, se questa si riempie, non verranno registrati nuovi errori.</span><span class="sxs-lookup"><span data-stu-id="10ab3-161">The **suspect_pages** table is limited in size, and if it fills, new errors are not logged.</span></span> <span data-ttu-id="10ab3-162">Per evitare che lo spazio della tabella si esaurisca, l'amministratore del database o l'amministratore di sistema devono cancellare manualmente i dati meno recenti dalla tabella tramite l'eliminazione delle righe.</span><span class="sxs-lookup"><span data-stu-id="10ab3-162">To prevent this table from filling up, the database administrator or system administrator must manually clear out old entries from this table by deleting rows.</span></span> <span data-ttu-id="10ab3-163">È quindi consigliabile archiviare o eliminare periodicamente le righe aventi un valore **event_type** ripristinato o riparato oppure le righe con un valore **last_update** obsoleto.</span><span class="sxs-lookup"><span data-stu-id="10ab3-163">Therefore, we recommend that you periodically delete or archive rows that have an **event_type** of restored or repaired, or rows that have an old **last_update** value.</span></span>  
  
     <span data-ttu-id="10ab3-164">Per monitorare l'attività sulla tabella suspect_pages è possibile usare [Classe di evento Database Suspect Data Page](../event-classes/database-suspect-data-page-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="10ab3-164">To monitor the activity on the suspect_pages table, you can use the [Database Suspect Data Page Event Class](../event-classes/database-suspect-data-page-event-class.md).</span></span> <span data-ttu-id="10ab3-165">Talvolta, a causa di errori temporanei, vengono aggiunte righe alla tabella **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="10ab3-165">Rows are sometimes added to the **suspect_pages** table because of transient errors.</span></span> <span data-ttu-id="10ab3-166">Tuttavia se vengono aggiunte molte righe alla tabella è probabile che vi sia un problema con il sottosistema I/O.</span><span class="sxs-lookup"><span data-stu-id="10ab3-166">If many rows are being added to the table, however, a problem probably exists with the I/O subsystem.</span></span> <span data-ttu-id="10ab3-167">Se si nota un aumento improvviso nel numero di righe che vengono aggiunte alla tabella, si consiglia di esaminare possibili problemi nel sottosistema I/O.</span><span class="sxs-lookup"><span data-stu-id="10ab3-167">If you notice a sudden increase in the number of rows being added to the table, we recommend that you investigate possible problems in your I/O subsystem.</span></span>  
  
     <span data-ttu-id="10ab3-168">L'amministratore del database può inoltre inserire o aggiornare i record.</span><span class="sxs-lookup"><span data-stu-id="10ab3-168">A database administrator can also insert or update records.</span></span> <span data-ttu-id="10ab3-169">Ad esempio, l'aggiornamento di una riga potrebbe essere utile se l'amministratore del database è certo che una determinata pagina sospetta è in realtà rimasta invariata, ma desidera mantenere temporaneamente il record.</span><span class="sxs-lookup"><span data-stu-id="10ab3-169">For example, updating a row might useful when the database administrator knows that a particular suspect page is actually intact, but wants to preserve the record for a while.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="10ab3-170">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="10ab3-170">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="10ab3-171">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="10ab3-171">Permissions</span></span>  
 <span data-ttu-id="10ab3-172">Chiunque abbia accesso a **msdb** può leggere i dati nella tabella **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="10ab3-172">Anyone with access to **msdb** can read the data in the **suspect_pages** table.</span></span> <span data-ttu-id="10ab3-173">Chiunque disponga dell'autorizzazione UPDATE nella tabella suspect_pages può aggiornare i relativi record.</span><span class="sxs-lookup"><span data-stu-id="10ab3-173">Anyone with UPDATE permission on the suspect_pages table can update its records.</span></span> <span data-ttu-id="10ab3-174">I membri del ruolo predefinito del database **db_owner** in **msdb** o del ruolo predefinito del server **sysadmin** possono inserire, aggiornare ed eliminare i record.</span><span class="sxs-lookup"><span data-stu-id="10ab3-174">Members the **db_owner** fixed database role on **msdb** or the **sysadmin** fixed server role can insert, update, and delete records.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="10ab3-175">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="10ab3-175">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="10ab3-176">Per gestire la tabella suspect_pages</span><span class="sxs-lookup"><span data-stu-id="10ab3-176">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="10ab3-177">In **Esplora oggetti**connettersi a un'istanza di [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], espandere tale istanza, quindi espandere **Database**.</span><span class="sxs-lookup"><span data-stu-id="10ab3-177">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="10ab3-178">Espandere **Database di sistema**, espandere **msdb**, espandere **Tabelle**, quindi espandere **Tabelle di sistema**.</span><span class="sxs-lookup"><span data-stu-id="10ab3-178">Expand **System Databases**, expand **msdb**, expand **Tables**, and then expand **System Tables**.</span></span>  
  
3.  <span data-ttu-id="10ab3-179">Espandere **dbo.suspect_pages** e fare clic con il pulsante destro del mouse su **Modifica le prime 200 righe**.</span><span class="sxs-lookup"><span data-stu-id="10ab3-179">Expand **dbo.suspect_pages** and right-click **Edit Top 200 Rows**.</span></span>  
  
4.  <span data-ttu-id="10ab3-180">Nella finestra Query, modificare, aggiornare o eliminare le righe desiderate.</span><span class="sxs-lookup"><span data-stu-id="10ab3-180">In the query window, edit, update, or delete the rows that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="10ab3-181">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="10ab3-181">Using Transact-SQL</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="10ab3-182">Per gestire la tabella suspect_pages</span><span class="sxs-lookup"><span data-stu-id="10ab3-182">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="10ab3-183">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10ab3-183">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="10ab3-184">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="10ab3-184">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="10ab3-185">Copiare e incollare gli esempi seguenti nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="10ab3-185">Copy and paste the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="10ab3-186">Nell'esempio seguente vengono eliminate alcune righe dalla tabella `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="10ab3-186">This example deletes some of the rows from the `suspect_pages` table.</span></span>  
  
```  
-- Delete restored, repaired, or deallocated pages.  
DELETE FROM msdb..suspect_pages  
   WHERE (event_type = 4 OR event_type = 5 OR event_type = 7);  
GO  
  
```  
  
 <span data-ttu-id="10ab3-187">In questo esempio vengono restituite le pagine errate nella tabella `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="10ab3-187">This example returns the bad pages in the `suspect_pages` table.</span></span>  
  
```  
-- Select nonspecific 824, bad checksum, and torn page errors.  
SELECT * FROM msdb..suspect_pages  
   WHERE (event_type = 1 OR event_type = 2 OR event_type = 3);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="10ab3-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ab3-188">See Also</span></span>  
 <span data-ttu-id="10ab3-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10ab3-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 <span data-ttu-id="10ab3-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10ab3-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="10ab3-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10ab3-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="10ab3-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10ab3-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="10ab3-193">[Ripristino di pagine &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="10ab3-193">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 <span data-ttu-id="10ab3-194">[suspect_pages &#40;&#41;Transact-SQL](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="10ab3-194">[suspect_pages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span></span>  
 <span data-ttu-id="10ab3-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="10ab3-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span></span>  
 [<span data-ttu-id="10ab3-196">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="10ab3-196">MSSQLSERVER_824</span></span>](../errors-events/mssqlserver-824-database-engine-error.md)  
  
  
