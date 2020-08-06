---
title: Configurare l'opzione di configurazione del server max degree of parallelism | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parallel queries [SQL Server]
- processors [SQL Server], parallel queries
- number of processors for parallel queries
- max degree of parallelism option
ms.assetid: 86b65bf1-a6a1-4670-afc0-cdfad1558032
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 824dc837142acc4a0898cb04b4a8687bc5be4043
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630051"
---
# <a name="configure-the-max-degree-of-parallelism-server-configuration-option"></a><span data-ttu-id="f9171-102">Configurare l'opzione di configurazione del server max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="f9171-102">Configure the max degree of parallelism Server Configuration Option</span></span>
  <span data-ttu-id="f9171-103">In questo argomento viene descritto come configurare l' `max degree of parallelism` opzione di configurazione del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9171-103">This topic describes how to configure the `max degree of parallelism` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f9171-104">Quando un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguita in un computer con più microprocessori o CPU, viene automaticamente rilevato il grado di parallelismo migliore, cioè il numero di processori utilizzati per eseguire una singola istruzione per l'esecuzione di ogni piano parallelo.</span><span class="sxs-lookup"><span data-stu-id="f9171-104">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on a computer that has more than one microprocessor or CPU, it detects the best degree of parallelism, that is, the number of processors employed to run a single statement, for each parallel plan execution.</span></span> <span data-ttu-id="f9171-105">È possibile utilizzare l'opzione `max degree of parallelism` per limitare il numero di processori da utilizzare per l'esecuzione di piani paralleli.</span><span class="sxs-lookup"><span data-stu-id="f9171-105">You can use the `max degree of parallelism` option to limit the number of processors to use in parallel plan execution.</span></span> <span data-ttu-id="f9171-106">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono valutati i piani di esecuzione parallela per le query, le operazioni DDL (Data Definition Language) sugli indici e il popolamento dei cursori statici e gestiti da keyset.</span><span class="sxs-lookup"><span data-stu-id="f9171-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] considers parallel execution plans for queries, index data definition language (DDL) operations, and static and keyset-driven cursor population.</span></span>  
  
 <span data-ttu-id="f9171-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="f9171-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f9171-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="f9171-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f9171-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f9171-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f9171-110">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="f9171-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f9171-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f9171-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f9171-112">**Per configurare l'opzione max degree of parallelism utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="f9171-112">**To configure the max degree of parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="f9171-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9171-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f9171-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9171-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="f9171-115">**Completamento:**  [Dopo la configurazione dell'opzione max degree of parallelism](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f9171-115">**Follow Up:**  [After you configure the max degree of parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f9171-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f9171-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f9171-117">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="f9171-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f9171-118">Se l'opzione affinity mask non è impostata sul valore predefinito, il numero di processori disponibili per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in sistemi SMP (multiprocessori simmetrici, Symmetric Multiprocessor) potrebbe risultare ridotto.</span><span class="sxs-lookup"><span data-stu-id="f9171-118">If the affinity mask option is not set to the default, it may restrict the number of processors available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on symmetric multiprocessing (SMP) systems.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f9171-119">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="f9171-119">Recommendations</span></span>  
  
-   <span data-ttu-id="f9171-120">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9171-120">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="f9171-121">Per consentire al server di determinare il grado massimo di parallelismo, impostare questa opzione su 0, cioè il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f9171-121">To enable the server to determine the maximum degree of parallelism, set this option to 0, the default value.</span></span> <span data-ttu-id="f9171-122">L'impostazione di grado massimo di parallelismo su 0 consente a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di utilizzare tutti i processori disponibili fino a un massimo di 64.</span><span class="sxs-lookup"><span data-stu-id="f9171-122">Setting maximum degree of parallelism to 0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use all the available processors up to 64 processors.</span></span> <span data-ttu-id="f9171-123">Per eliminare la generazione di piani paralleli, impostare `max degree of parallelism` su 1.</span><span class="sxs-lookup"><span data-stu-id="f9171-123">To suppress parallel plan generation, set `max degree of parallelism` to 1.</span></span> <span data-ttu-id="f9171-124">Impostare il valore su un numero compreso tra 1 e 32.767 per specificare il numero massimo di core del processore che può essere utilizzato per l'esecuzione di una singola query.</span><span class="sxs-lookup"><span data-stu-id="f9171-124">Set the value to a number from 1 to 32,767 to specify the maximum number of processor cores that can be used by a single query execution.</span></span> <span data-ttu-id="f9171-125">Se il valore è maggiore di quello dei processori disponibili, viene utilizzato il numero effettivo di processori disponibili.</span><span class="sxs-lookup"><span data-stu-id="f9171-125">If a value greater than the number of available processors is specified, the actual number of available processors is used.</span></span> <span data-ttu-id="f9171-126">Se il computer dispone di un unico processore, il valore di `max degree of parallelism` verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="f9171-126">If the computer has only one processor, the `max degree of parallelism` value is ignored.</span></span>  
  
-   <span data-ttu-id="f9171-127">È possibile sostituire il valore di max degree of parallelism nelle query specificando l'hint per la query MAXDOP nell'istruzione per la query.</span><span class="sxs-lookup"><span data-stu-id="f9171-127">You can override the max degree of parallelism value in queries by specifying the MAXDOP query hint in the query statement.</span></span> <span data-ttu-id="f9171-128">Per altre informazioni, vedere [Hint per la query &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="f9171-128">For more information, see [Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
-   <span data-ttu-id="f9171-129">Le operazioni tramite cui viene creato o ricompilato un indice o eliminato un indice cluster possono richiedere un elevato utilizzo di risorse.</span><span class="sxs-lookup"><span data-stu-id="f9171-129">Index operations that create or rebuild an index, or that drop a clustered index, can be resource intensive.</span></span> <span data-ttu-id="f9171-130">È possibile sostituire il valore di max degree of parallelism per le operazioni sugli indici specificando l'opzione per gli indici MAXDOP nell'istruzione per l'indice.</span><span class="sxs-lookup"><span data-stu-id="f9171-130">You can override the max degree of parallelism value for index operations by specifying the MAXDOP index option in the index statement.</span></span> <span data-ttu-id="f9171-131">Il valore MAXDOP viene applicato all'istruzione al momento dell'esecuzione e non viene archiviato nei metadati dell'indice.</span><span class="sxs-lookup"><span data-stu-id="f9171-131">The MAXDOP value is applied to the statement at execution time and is not stored in the index metadata.</span></span> <span data-ttu-id="f9171-132">Per altre informazioni, vedere [Configurazione di operazioni parallele sugli indici](../../relational-databases/indexes/configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f9171-132">For more information, see [Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md).</span></span>  
  
-   <span data-ttu-id="f9171-133">Oltre al parallelismo delle query e delle operazioni sugli indici, questa opzione controlla anche il parallelismo dei controlli DBCC CHECKTABLE, DBCC CHECKDB e DBCC CHECKFILEGROUP.</span><span class="sxs-lookup"><span data-stu-id="f9171-133">In addition to queries and index operations, this option also controls the parallelism of DBCC CHECKTABLE, DBCC CHECKDB, and DBCC CHECKFILEGROUP.</span></span> <span data-ttu-id="f9171-134">È possibile disabilitare i piani di esecuzione parallela per queste istruzioni utilizzando il flag di traccia 2528.</span><span class="sxs-lookup"><span data-stu-id="f9171-134">You can disable parallel execution plans for these statements by using trace flag 2528.</span></span> <span data-ttu-id="f9171-135">Per altre informazioni, vedere [Flag di traccia &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f9171-135">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f9171-136">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f9171-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f9171-137">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f9171-137">Permissions</span></span>  
 <span data-ttu-id="f9171-138">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f9171-138">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="f9171-139">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="f9171-139">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="f9171-140">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="f9171-140">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f9171-141">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9171-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="f9171-142">Per configurare l'opzione max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="f9171-142">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="f9171-143">In **Esplora oggetti**fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f9171-143">In **Object Explorer**, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f9171-144">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="f9171-144">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="f9171-145">Nella casella **Max Degree of Parallelism** selezionare il numero massimo di processori da utilizzare nell'esecuzione di piani paralleli.</span><span class="sxs-lookup"><span data-stu-id="f9171-145">In the **Max Degree of Parallelism** box, select the maximum number of processors to use in parallel plan execution.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f9171-146">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9171-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="f9171-147">Per configurare l'opzione max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="f9171-147">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="f9171-148">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9171-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f9171-149">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="f9171-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f9171-150">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f9171-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f9171-151">In questo esempio si illustra come utilizzare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per configurare l'opzione `max degree of parallelism` su `8`.</span><span class="sxs-lookup"><span data-stu-id="f9171-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max degree of parallelism` option to `8`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO   
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
EXEC sp_configure 'max degree of parallelism', 8;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
```  
  
 <span data-ttu-id="f9171-152">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="f9171-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-degree-of-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="f9171-153">Completamento: Dopo la configurazione dell'opzione max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="f9171-153">Follow Up: After you configure the max degree of parallelism option</span></span>  
 <span data-ttu-id="f9171-154">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="f9171-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9171-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9171-155">See Also</span></span>  
 <span data-ttu-id="f9171-156">[Opzione di configurazione del server affinity mask](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="f9171-156">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="f9171-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9171-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="f9171-158">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f9171-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="f9171-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9171-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="f9171-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9171-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="f9171-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9171-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="f9171-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9171-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="f9171-163">[DBCC CHECKTABLE &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9171-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span></span>  
 <span data-ttu-id="f9171-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9171-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="f9171-165">[DBCC CHECKFILEGROUP &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9171-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="f9171-166">[Configurazione di operazioni parallele sugli indici](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="f9171-166">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="f9171-167">[Hint di query &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="f9171-167">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="f9171-168">Impostare le opzioni di indice</span><span class="sxs-lookup"><span data-stu-id="f9171-168">Set Index Options</span></span>](../../relational-databases/indexes/set-index-options.md)  
  
  
