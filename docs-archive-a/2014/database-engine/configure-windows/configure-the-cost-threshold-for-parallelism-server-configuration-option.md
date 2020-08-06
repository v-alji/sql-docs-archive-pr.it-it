---
title: Configurare l'opzione di configurazione del server cost threshold for parallelism | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cost threshold for parallelism option
ms.assetid: dad21bee-fe28-41f6-9d2f-e6ababfaf9db
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 675055a753e84ace3a4fcb44b41b8c914326c5c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624949"
---
# <a name="configure-the-cost-threshold-for-parallelism-server-configuration-option"></a><span data-ttu-id="04e77-102">Configurare l'opzione di configurazione del server cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="04e77-102">Configure the cost threshold for parallelism Server Configuration Option</span></span>
  <span data-ttu-id="04e77-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **cost threshold for parallelism** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04e77-103">This topic describes how to configure the **cost threshold for parallelism** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="04e77-104">Con l'opzione **cost threshold for parallelism** è possibile specificare la soglia oltre la quale in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono creati ed eseguiti piani paralleli per le query.</span><span class="sxs-lookup"><span data-stu-id="04e77-104">The **cost threshold for parallelism** option specifies the threshold at which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates and runs parallel plans for queries.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="04e77-105">viene creato ed eseguito un piano parallelo per una query solo quando il costo stimato per l'esecuzione di un piano seriale per la stessa query è più elevato del valore impostato in **cost threshold for parallelism**.</span><span class="sxs-lookup"><span data-stu-id="04e77-105">creates and runs a parallel plan for a query only when the estimated cost to run a serial plan for the same query is higher than the value set in **cost threshold for parallelism**.</span></span> <span data-ttu-id="04e77-106">Il costo equivale al tempo (in secondi) stimato per l'esecuzione del piano seriale in una configurazione hardware specifica.</span><span class="sxs-lookup"><span data-stu-id="04e77-106">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="04e77-107">L'opzione **cost threshold for parallelism** può essere impostata su qualsiasi valore compreso tra 0 e 32767.</span><span class="sxs-lookup"><span data-stu-id="04e77-107">The **cost threshold for parallelism** option can be set to any value from 0 through 32767.</span></span> <span data-ttu-id="04e77-108">Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="04e77-108">The default value is 5.</span></span>  
  
 <span data-ttu-id="04e77-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="04e77-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="04e77-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="04e77-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="04e77-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="04e77-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="04e77-112">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="04e77-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="04e77-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="04e77-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="04e77-114">**Per configurare l'opzione cost threshold for parallelism utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="04e77-114">**To configure the cost threshold for parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="04e77-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04e77-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="04e77-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="04e77-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="04e77-117">**Completamento:**  [Dopo la configurazione dell'opzione cost threshold for parallelism](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="04e77-117">**Follow Up:**  [After you configure the cost threshold for parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="04e77-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="04e77-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="04e77-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="04e77-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="04e77-120">Il costo equivale al tempo (in secondi) stimato per l'esecuzione del piano seriale in una configurazione hardware specifica.</span><span class="sxs-lookup"><span data-stu-id="04e77-120">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="04e77-121">Impostare l'opzione **cost threshold for parallelism** esclusivamente in sistemi basati su multiprocessori simmetrici.</span><span class="sxs-lookup"><span data-stu-id="04e77-121">Only set **cost threshold for parallelism** on symmetric multiprocessors.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="04e77-122">il valore dell'opzione **cost threshold for parallelism** verrà ignorato nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="04e77-122">ignores the **cost threshold for parallelism** value under the following conditions:</span></span>  
  
    -   <span data-ttu-id="04e77-123">Il computer in uso è dotato di un solo processore.</span><span class="sxs-lookup"><span data-stu-id="04e77-123">Your computer has only one logical processor.</span></span>  
  
    -   <span data-ttu-id="04e77-124">È disponibile un solo processore logico per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a causa dell'opzione di configurazione **affinity mask** .</span><span class="sxs-lookup"><span data-stu-id="04e77-124">Only a single logical processor is available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because of the **affinity mask** configuration option.</span></span>  
  
    -   <span data-ttu-id="04e77-125">L'opzione **max degree of parallelism** è impostata su 1.</span><span class="sxs-lookup"><span data-stu-id="04e77-125">The **max degree of parallelism** option is set to 1.</span></span>  
  
 <span data-ttu-id="04e77-126">Un processore logico è l'unità di base dell'hardware del processore che consente al sistema operativo di inviare un'attività o eseguire un contesto di thread.</span><span class="sxs-lookup"><span data-stu-id="04e77-126">A logical processor is the basic unit of processor hardware that allows the operating system to dispatch a task or execute a thread context.</span></span> <span data-ttu-id="04e77-127">Ogni processore logico può eseguire un solo contesto di thread per volta.</span><span class="sxs-lookup"><span data-stu-id="04e77-127">Each logical processor can execute only one thread context at a time.</span></span> <span data-ttu-id="04e77-128">Il core del processore è il set di circuiti che consente di decodificare ed eseguire istruzioni.</span><span class="sxs-lookup"><span data-stu-id="04e77-128">The processor core is the circuitry that provides ability to decode and execute instructions.</span></span> <span data-ttu-id="04e77-129">Un core di processore può contenere uno o più processori logici.</span><span class="sxs-lookup"><span data-stu-id="04e77-129">A processor core may contain one or more logical processors.</span></span> <span data-ttu-id="04e77-130">La query [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente può essere utilizzata per l'acquisizione di informazioni sulla CPU del sistema.</span><span class="sxs-lookup"><span data-stu-id="04e77-130">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] query can be used for obtaining CPU information for the system.</span></span>  
  
```  
SELECT (cpu_count / hyperthread_ratio) AS PhysicalCPUs,   
cpu_count AS logicalCPUs   
FROM sys.dm_os_sys_info  
```  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="04e77-131">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="04e77-131">Recommendations</span></span>  
  
-   <span data-ttu-id="04e77-132">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04e77-132">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="04e77-133">In determinati casi il piano parallelo viene scelto anche se il piano costi di una query risulta inferiore al valore corrente di **cost threshold for parallelism** .</span><span class="sxs-lookup"><span data-stu-id="04e77-133">In certain cases, a parallel plan may be chosen even though the query's cost plan is less than the current **cost threshold for parallelism** value.</span></span> <span data-ttu-id="04e77-134">La scelta tra piano parallelo o seriale è infatti basata su una stima dei costi elaborata prima del completamento dell'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="04e77-134">This can happen because the decision to use a parallel or serial plan is based on a cost estimate provided before the full optimization is complete.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="04e77-135">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="04e77-135">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="04e77-136">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="04e77-136">Permissions</span></span>  
 <span data-ttu-id="04e77-137">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="04e77-137">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="04e77-138">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="04e77-138">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="04e77-139">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="04e77-139">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="04e77-140">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="04e77-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="04e77-141">Per configurare l'opzione cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="04e77-141">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="04e77-142">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="04e77-142">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="04e77-143">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="04e77-143">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="04e77-144">In **Parallelismo**impostare l'opzione **CostThresholdForParallelism** sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="04e77-144">Under **Parallelism**, change the **CostThresholdForParallelism** option to the value you want.</span></span> <span data-ttu-id="04e77-145">Digitare o selezionare un valore compreso tra 0 e 32767.</span><span class="sxs-lookup"><span data-stu-id="04e77-145">Type or select a value from 0 to 32767.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="04e77-146">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="04e77-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="04e77-147">Per configurare l'opzione cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="04e77-147">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="04e77-148">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04e77-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="04e77-149">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="04e77-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="04e77-150">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="04e77-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="04e77-151">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `cost threshold for parallelism` su `10`.</span><span class="sxs-lookup"><span data-stu-id="04e77-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `cost threshold for parallelism` option to `10`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cost threshold for parallelism', 10 ;  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="04e77-152">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="04e77-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cost-threshold-for-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="04e77-153">Completamento: Dopo la configurazione dell'opzione cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="04e77-153">Follow Up: After you configure the cost threshold for parallelism option</span></span>  
 <span data-ttu-id="04e77-154">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="04e77-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e77-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04e77-155">See Also</span></span>  
 <span data-ttu-id="04e77-156">[Configurazione di operazioni parallele sugli indici](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="04e77-156">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="04e77-157">[Hint di query &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="04e77-157">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 <span data-ttu-id="04e77-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04e77-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="04e77-159">[Opzione di configurazione del server affinity mask](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="04e77-159">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="04e77-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04e77-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="04e77-161">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="04e77-161">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="04e77-162">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04e77-162">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
