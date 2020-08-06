---
title: Abilitare e disabilitare Change Data Capture (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change data capture [SQL Server], enabling tables
- change data capture [SQL Server], enabling databases
- change data capture [SQL Server], disabling databases
- change data capture [SQL Server], disabling tables
ms.assetid: b741894f-d267-4b10-adfe-cbc14aa6caeb
author: rothja
ms.author: jroth
ms.openlocfilehash: df0a2fd4a2c6ffb2de58d6b52360d1730d0fa7df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628568"
---
# <a name="enable-and-disable-change-data-capture-sql-server"></a><span data-ttu-id="68cc9-102">Abilitare e disabilitare Change Data Capture (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="68cc9-102">Enable and Disable Change Data Capture (SQL Server)</span></span>
  <span data-ttu-id="68cc9-103">In questo argomento viene descritto come abilitare e disabilitare Change Data Capture per un database e una tabella.</span><span class="sxs-lookup"><span data-stu-id="68cc9-103">This topic describes how to enable and disable change data capture for a database and a table.</span></span>  
  
## <a name="enable-change-data-capture-for-a-database"></a><span data-ttu-id="68cc9-104">Abilitazione di Change Data Capture per un database</span><span class="sxs-lookup"><span data-stu-id="68cc9-104">Enable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="68cc9-105">Prima che sia possibile creare un'istanza di acquisizione per singole tabelle, è innanzitutto necessario che un membro del ruolo predefinito del server `sysadmin` abiliti il database per Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="68cc9-105">Before a capture instance can be created for individual tables, a member of the `sysadmin` fixed server role must first enable the database for change data capture.</span></span> <span data-ttu-id="68cc9-106">Questa operazione viene eseguita eseguendo la stored procedure [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) nel contesto del database.</span><span class="sxs-lookup"><span data-stu-id="68cc9-106">This is done by running the stored procedure [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) in the database context.</span></span> <span data-ttu-id="68cc9-107">Per determinare se un database è già abilitato, eseguire una query sulla colonna `is_cdc_enabled` nella vista del catalogo `sys.databases`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-107">To determine if a database is already enabled, query the `is_cdc_enabled` column in the `sys.databases` catalog view.</span></span>  
  
 <span data-ttu-id="68cc9-108">Quando un database è abilitato per Change Data Capture, per il database vengono creati lo schema `cdc`, l'utente `cdc`, le tabelle dei metadati e altri oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="68cc9-108">When a database is enabled for change data capture, the `cdc` schema, `cdc` user, metadata tables, and other system objects are created for the database.</span></span> <span data-ttu-id="68cc9-109">Lo schema `cdc` contiene le tabelle di metadati di Change Data Capture e, dopo l'abilitazione della funzionalità delle tabelle di origine, le singole tabelle delle modifiche fungono da repository per i dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="68cc9-109">The `cdc` schema contains the change data capture metadata tables and, after source tables are enabled for change data capture, the individual change tables serve as a repository for change data.</span></span> <span data-ttu-id="68cc9-110">Lo schema `cdc` contiene inoltre funzioni di sistema associate utilizzate per eseguire query sui dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="68cc9-110">The `cdc` schema also contains associated system functions used to query for change data.</span></span>  
  
 <span data-ttu-id="68cc9-111">Change Data Capture richiede l'utilizzo esclusivo dello schema `cdc` e dell'utente `cdc`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-111">Change data capture requires exclusive use of the `cdc` schema and `cdc` user.</span></span> <span data-ttu-id="68cc9-112">Se in un database è attualmente presente uno schema o un utente di database denominato *cdc* , il database non può essere abilitato per Change Data Capture fino all'eliminazione o alla ridenominazione dello schema o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="68cc9-112">If either a schema or a database user named *cdc* currently exists in a database, the database cannot be enabled for change data capture until the schema and or user are dropped or renamed.</span></span>  
  
 <span data-ttu-id="68cc9-113">Per un esempio di abilitazione di un database, vedere il modello Enable Database for Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="68cc9-113">See the Enable Database for Change Data Capture template for an example of enabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="68cc9-114">Per individuare i modelli in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], scegliere **Esplora modelli**dal menu **Visualizza**, quindi selezionare **Modelli di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="68cc9-114">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then select **SQL Server Templates**.</span></span> <span data-ttu-id="68cc9-115">**Change Data Capture** è una sottocartella.</span><span class="sxs-lookup"><span data-stu-id="68cc9-115">**Change Data Capture** is a sub-folder.</span></span> <span data-ttu-id="68cc9-116">che contiene tutti i modelli a cui si fa riferimento in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="68cc9-116">Under this folder, you will find all the templates referenced in this topic.</span></span> <span data-ttu-id="68cc9-117">È inoltre presente un'icona **Esplora modelli** sulla barra degli strumenti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68cc9-117">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- ====  
-- Enable Database for CDC template   
-- ====  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_db  
GO  
```  
  
## <a name="disable-change-data-capture-for-a-database"></a><span data-ttu-id="68cc9-118">Disabilitazione di Change Data Capture per un database</span><span class="sxs-lookup"><span data-stu-id="68cc9-118">Disable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="68cc9-119">Un membro del `sysadmin` ruolo predefinito del server può eseguire il stored procedure [sys. Sp_cdc_disable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) nel contesto del database per disabilitare Change Data Capture per un database.</span><span class="sxs-lookup"><span data-stu-id="68cc9-119">A member of the `sysadmin` fixed server role can run the stored procedure [sys.sp_cdc_disable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) in the database context to disable change data capture for a database.</span></span> <span data-ttu-id="68cc9-120">Non è necessario disabilitare singole tabelle prima di disabilitare il database.</span><span class="sxs-lookup"><span data-stu-id="68cc9-120">It is not necessary to disable individual tables before you disable the database.</span></span> <span data-ttu-id="68cc9-121">La disabilitazione del database comporta la rimozione di tutti i metadati di Change Data Capture associati, inclusi l'utente e lo schema `cdc` e i processi Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="68cc9-121">Disabling the database removes all associated change data capture metadata, including the `cdc` user and schema and the change data capture jobs.</span></span> <span data-ttu-id="68cc9-122">Eventuali ruoli di controllo creati da Change Data Capture, tuttavia, non verranno rimossi automaticamente e devono essere eliminati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="68cc9-122">However, any gating roles created by change data capture will not be removed automatically and must be explicitly deleted.</span></span> <span data-ttu-id="68cc9-123">Per determinare se un database è abilitato, eseguire una query sulla colonna `is_cdc_enabled` nella vista del catalogo sys.databases.</span><span class="sxs-lookup"><span data-stu-id="68cc9-123">To determine if a database is enabled, query the `is_cdc_enabled` column in the sys.databases catalog view.</span></span>  
  
 <span data-ttu-id="68cc9-124">Se viene eliminato un database abilitato per Change Data Capture, i processi Change Data Capture vengono automaticamente rimossi.</span><span class="sxs-lookup"><span data-stu-id="68cc9-124">If a change data capture enabled database is dropped, change data capture jobs are automatically removed.</span></span>  
  
 <span data-ttu-id="68cc9-125">Per un esempio di disabilitazione di un database, vedere il modello Disable Database for Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="68cc9-125">See the Disable Database for Change Data Capture template for an example of disabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="68cc9-126">Per individuare i modelli in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], scegliere **Esplora modelli**dal menu **Visualizza**, quindi fare clic su **Modelli di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="68cc9-126">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then click **SQL Server Templates**.</span></span> <span data-ttu-id="68cc9-127">**Change Data Capture** è una sottocartella contenente tutti i modelli a cui si fa riferimento in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="68cc9-127">**Change Data Capture** is a sub-folder where you will find all the templates that are referenced in this topic.</span></span> <span data-ttu-id="68cc9-128">È inoltre presente un'icona **Esplora modelli** sulla barra degli strumenti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="68cc9-128">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- =======  
-- Disable Database for Change Data Capture template   
-- =======  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_db  
GO  
```  
  
## <a name="enable-change-data-capture-for-a-table"></a><span data-ttu-id="68cc9-129">Abilitazione di Change Data Capture per una tabella</span><span class="sxs-lookup"><span data-stu-id="68cc9-129">Enable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="68cc9-130">Dopo avere abilitato un database per Change Data Capture, i membri del ruolo predefinito del database `db_owner` possono creare un'istanza di acquisizione per singole tabelle di origine utilizzando la stored procedure `sys.sp_cdc_enable_table`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-130">After a database has been enabled for change data capture, members of the `db_owner` fixed database role can create a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_enable_table`.</span></span> <span data-ttu-id="68cc9-131">Per determinare se una tabella di origine è già stata abilitata per Change Data Capture, esaminare la colonna is_tracked_by_cdc nella vista del catalogo `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-131">To determine whether a source table has already been enabled for change data capture, examine the is_tracked_by_cdc column in the `sys.tables` catalog view.</span></span>  
  
 <span data-ttu-id="68cc9-132">Quando si crea un'istanza di acquisizione, è possibile specificare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="68cc9-132">The following options can be specified when creating a capture instance:</span></span>  
  
 <span data-ttu-id="68cc9-133">`Columns in the source table to be captured`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-133">`Columns in the source table to be captured`.</span></span>  
  
 <span data-ttu-id="68cc9-134">Per impostazione predefinita, tutte le colonne della tabella di origine vengono identificate come colonne acquisite.</span><span class="sxs-lookup"><span data-stu-id="68cc9-134">By default, all of the columns in the source table are identified as captured columns.</span></span> <span data-ttu-id="68cc9-135">Se è necessario rilevare solo un subset di colonne, ad esempio per motivi di privacy o di prestazioni, utilizzare il *@captured_column_list* parametro per specificare il subset di colonne.</span><span class="sxs-lookup"><span data-stu-id="68cc9-135">If only a subset of columns need to be tracked, such as for privacy or performance reasons, use the *@captured_column_list* parameter to specify the subset of columns.</span></span>  
  
 `A filegroup to contain the change table.`  
  
 <span data-ttu-id="68cc9-136">Per impostazione predefinita, la tabella delle modifiche si trova nel filegroup predefinito del database.</span><span class="sxs-lookup"><span data-stu-id="68cc9-136">By default, the change table is located in the default filegroup of the database.</span></span> <span data-ttu-id="68cc9-137">I proprietari del database che desiderano controllare la posizione di singole tabelle delle modifiche possono utilizzare il *@filegroup_name* parametro per specificare un determinato filegroup per la tabella delle modifiche associata all'istanza di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="68cc9-137">Database owners who want to control the placement of individual change tables can use the *@filegroup_name* parameter to specify a particular filegroup for the change table associated with the capture instance.</span></span> <span data-ttu-id="68cc9-138">È necessario che il filegroup specificato sia già presente.</span><span class="sxs-lookup"><span data-stu-id="68cc9-138">The named filegroup must already exist.</span></span> <span data-ttu-id="68cc9-139">È in genere consigliabile inserire le tabelle delle modifiche in un filegroup distinto dalle tabelle di origine.</span><span class="sxs-lookup"><span data-stu-id="68cc9-139">Generally, it is recommended that change tables be placed in a filegroup separate from source tables.</span></span> <span data-ttu-id="68cc9-140">Vedere il `Enable a Table Specifying Filegroup Option` modello per un esempio che illustra l'uso del *@filegroup_name* parametro.</span><span class="sxs-lookup"><span data-stu-id="68cc9-140">See the `Enable a Table Specifying Filegroup Option` template for an example showing use of the *@filegroup_name* parameter.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Specifying Filegroup Option Template  
-- =========  
USE MyDB  
GO  
  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@filegroup_name = N'MyDB_CT',  
@supports_net_changes = 1  
GO  
```  
  
 `A role for controlling access to a change table.`  
  
 <span data-ttu-id="68cc9-141">Lo scopo del ruolo specificato consiste nel controllare l'accesso ai dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="68cc9-141">The purpose of the named role is to control access to the change data.</span></span> <span data-ttu-id="68cc9-142">Il ruolo specificato può essere un ruolo predefinito del server esistente o un ruolo del database.</span><span class="sxs-lookup"><span data-stu-id="68cc9-142">The specified role can be an existing fixed server role or a database role.</span></span> <span data-ttu-id="68cc9-143">Se il ruolo specificato non è già presente, verrà automaticamente creato un ruolo del database con il nome indicato.</span><span class="sxs-lookup"><span data-stu-id="68cc9-143">If the specified role does not already exist, a database role of that name is created automatically.</span></span> <span data-ttu-id="68cc9-144">I membri del ruolo `sysadmin` o `db_owner` dispongono di accesso completo ai dati nelle tabelle delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="68cc9-144">Members of either the `sysadmin` or `db_owner` role have full access to the data in the change tables.</span></span> <span data-ttu-id="68cc9-145">Tutti gli altri utenti devono disporre dell'autorizzazione SELECT per tutte le colonne acquisite della tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="68cc9-145">All other users must have SELECT permission on all the captured columns of the source table.</span></span> <span data-ttu-id="68cc9-146">Quando viene specificato un ruolo, inoltre, gli utenti che non sono membri del ruolo `sysadmin` o `db_owner` devono essere anche membri del ruolo specificato.</span><span class="sxs-lookup"><span data-stu-id="68cc9-146">In addition, when a role is specified, users who are not members of either the `sysadmin` or `db_owner` role must also be members of the specified role.</span></span>  
  
 <span data-ttu-id="68cc9-147">Se non si vuole usare un ruolo di controllo, impostare in modo esplicito il *@role_name* parametro su null.</span><span class="sxs-lookup"><span data-stu-id="68cc9-147">If you do not want to use a gating role, explicitly set the *@role_name* parameter to NULL.</span></span> <span data-ttu-id="68cc9-148">Per un esempio di abilitazione di una tabella senza un ruolo di controllo, vedere il modello `Enable a Table Without Using a Gating Role`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-148">See the `Enable a Table Without Using a Gating Role` template for an example of enabling a table without a gating role.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Without Using a Gating Role template   
-- =========  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = NULL,  
@supports_net_changes = 1  
GO  
  
```  
  
 `A function to query for net changes.`  
  
 <span data-ttu-id="68cc9-149">Un'istanza di acquisizione includerà sempre una funzione con valori di tabella per la restituzione di tutte le voci della tabella delle modifiche generate in un intervallo definito.</span><span class="sxs-lookup"><span data-stu-id="68cc9-149">A capture instance will always include a table valued function for returning all change table entries that occurred within a defined interval.</span></span> <span data-ttu-id="68cc9-150">Il nome di questa funzione viene creato aggiungendo il nome dell'istanza di acquisizione a "cdc.fn_cdc_get_all_changes_."</span><span class="sxs-lookup"><span data-stu-id="68cc9-150">This function is named by appending the capture instance name to "cdc.fn_cdc_get_all_changes_".</span></span> <span data-ttu-id="68cc9-151">Per altre informazioni, vedere [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68cc9-151">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="68cc9-152">Se il parametro *@supports_net_changes* è impostato su 1, viene generata anche una funzione net changes per l'istanza di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="68cc9-152">If the parameter *@supports_net_changes* is set to 1, a net changes function is also generated for the capture instance.</span></span> <span data-ttu-id="68cc9-153">Questa funzione restituisce solo una modifica per ogni riga distinta modificata nell'intervallo specificato nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="68cc9-153">This function returns only one change for each distinct row changed in the interval specified in the call.</span></span> <span data-ttu-id="68cc9-154">Per altre informazioni, vedere [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="68cc9-154">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="68cc9-155">Per supportare le query sulle modifiche delta, è necessario che la tabella di origine disponga di una chiave primaria o di un indice univoco per identificare le righe in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="68cc9-155">To support net changes queries, the source table must have a primary key or unique index to uniquely identify rows.</span></span> <span data-ttu-id="68cc9-156">Se viene utilizzato un indice univoco, il nome dell'indice deve essere specificato utilizzando il *@index_name* parametro.</span><span class="sxs-lookup"><span data-stu-id="68cc9-156">If a unique index is used, the name of the index must be specified using the *@index_name* parameter.</span></span> <span data-ttu-id="68cc9-157">Le colonne definite nella chiave primaria o nell'indice univoco devono essere incluse nell'elenco delle colonne di origine da acquisire.</span><span class="sxs-lookup"><span data-stu-id="68cc9-157">The columns defined in the primary key or unique index must be included in the list of source columns to be captured.</span></span>  
  
 <span data-ttu-id="68cc9-158">Per un esempio di creazione di un'istanza di acquisizione con entrambe le funzioni di query, vedere il modello `Enable a Table for All and Net Changes Queries`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-158">See the `Enable a Table for All and Net Changes Queries` template for an example demonstrating the creation of a capture instance with both query functions.</span></span>  
  
```sql  
-- =============  
-- Enable a Table for All and Net Changes Queries template   
-- =============  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@supports_net_changes = 1  
GO  
```  
  
> [!NOTE]
>  <span data-ttu-id="68cc9-159">Se Change Data Capture è abilitato in una tabella con una chiave primaria esistente e il *@index_name* parametro non viene utilizzato per identificare un indice univoco alternativo, la funzionalità Change Data Capture utilizzerà la chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="68cc9-159">If change data capture is enabled on a table with an existing primary key, and the *@index_name* parameter is not used to identify an alternative unique index, the change data capture feature will use the primary key.</span></span> <span data-ttu-id="68cc9-160">Non saranno consentite modifiche successive alla chiave primaria se prima non si disabilita Change Data Capture per la tabella.</span><span class="sxs-lookup"><span data-stu-id="68cc9-160">Subsequent changes to the primary key will not be allowed without first disabling change data capture for the table.</span></span> <span data-ttu-id="68cc9-161">Questa regola è sempre valida, indipendentemente dal fatto che durante la configurazione di Change Data Capture sia stato o meno richiesto il supporto per le query sulle modifiche delta.</span><span class="sxs-lookup"><span data-stu-id="68cc9-161">This is true regardless of whether support for net changes queries was requested when change data capture was configured.</span></span> <span data-ttu-id="68cc9-162">Se in una tabella non è presente alcuna chiave primaria al momento dell'abilitazione di Change Data Capture, l'aggiunta successiva di una chiave primaria verrà ignorata da Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="68cc9-162">If there is no primary key on a table at the time it is enabled for change data capture, the subsequent addition of a primary key is ignored by change data capture.</span></span> <span data-ttu-id="68cc9-163">Poiché Change Data Capture non utilizzerà una chiave primaria creata in seguito all'abilitazione della tabella, la chiave e le colonne chiave possono essere rimosse senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="68cc9-163">Because change data capture will not use a primary key that is created after the table was enabled, the key and key columns can be removed without restrictions.</span></span>  
  
## <a name="disable-change-data-capture-for-a-table"></a><span data-ttu-id="68cc9-164">Disabilitazione di Change Data Capture per una tabella</span><span class="sxs-lookup"><span data-stu-id="68cc9-164">Disable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="68cc9-165">I membri del ruolo predefinito del database `db_owner` possono rimuovere un'istanza di acquisizione per singole tabelle di origine utilizzando la stored procedure `sys.sp_cdc_disable_table`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-165">Members of the `db_owner` fixed database role can remove a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_disable_table`.</span></span> <span data-ttu-id="68cc9-166">Per determinare se una tabella di origine sia attualmente abilitata per Change Data Capture, esaminare la colonna `is_tracked_by_cdc` nella vista del catalogo `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="68cc9-166">To determine whether a source table is currently enabled for change data capture, examine the `is_tracked_by_cdc` column in the `sys.tables` catalog view.</span></span> <span data-ttu-id="68cc9-167">Se in seguito alla disabilitazione non è presente alcuna tabella abilitata per il database, vengono rimossi anche i processi Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="68cc9-167">If there are no tables enabled for the database after the disabling takes place, the change data capture jobs are also removed.</span></span>  
  
 <span data-ttu-id="68cc9-168">Se viene eliminata una tabella abilitata per Change Data Capture, i metadati di Change Data Capture associati alla tabella vengono automaticamente rimossi.</span><span class="sxs-lookup"><span data-stu-id="68cc9-168">If a change data capture-enabled table is dropped, change data capture metadata that is associated with the table is automatically removed.</span></span>  
  
 <span data-ttu-id="68cc9-169">Per un esempio di disabilitazione di una tabella, vedere il modello Disable a Capture Instance for a Table.</span><span class="sxs-lookup"><span data-stu-id="68cc9-169">See the Disable a Capture Instance for a Table template for an example of disabling a table.</span></span>  
  
```sql  
-- =====  
-- Disable a Capture Instance for a Table template   
-- =====  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@capture_instance = N'dbo_MyTable'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="68cc9-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68cc9-170">See Also</span></span>  
 <span data-ttu-id="68cc9-171">[Tenere traccia delle modifiche ai dati &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="68cc9-171">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="68cc9-172">[Informazioni su Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="68cc9-172">[About Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span></span>  
 <span data-ttu-id="68cc9-173">[Usare Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="68cc9-173">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="68cc9-174">Amministrare e monitorare Change Data Capture &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="68cc9-174">Administer and Monitor Change Data Capture &#40;SQL Server&#41;</span></span>](../track-changes/administer-and-monitor-change-data-capture-sql-server.md)  
  
  
