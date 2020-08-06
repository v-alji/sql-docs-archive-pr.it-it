---
title: Configurare l'opzione di configurazione del server max worker threads | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- worker threads [SQL Server]
- max worker threads option
ms.assetid: abeadfa4-a14d-469a-bacf-75812e48fac1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4881cefee350d34d93b539c56be6f43866d3ddfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630049"
---
# <a name="configure-the-max-worker-threads-server-configuration-option"></a><span data-ttu-id="d5500-102">Configurare l'opzione di configurazione del server max worker threads</span><span class="sxs-lookup"><span data-stu-id="d5500-102">Configure the max worker threads Server Configuration Option</span></span>
  <span data-ttu-id="d5500-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **max worker threads** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5500-103">This topic describes how to configure the **max worker threads** server configuration option in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d5500-104">Con l'opzione **max worker threads** è possibile configurare il numero di thread di lavoro disponibili per i processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5500-104">The **max worker threads** option configures the number of worker threads that are available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d5500-105">vengono utilizzati i servizi thread nativi dei sistemi operativi in modo che uno o più thread supportino ogni rete supportata simultaneamente in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , che tramite un altro thread vengano gestiti i checkpoint di database e che tutti gli utenti siano gestiti da un pool di thread.</span><span class="sxs-lookup"><span data-stu-id="d5500-105">uses the native thread services of the operating systems so that one or more threads support each network that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports simultaneously, another thread handles database checkpoints, and a pool of threads handles all users.</span></span> <span data-ttu-id="d5500-106">Il valore predefinito per **max worker threads** è 0.</span><span class="sxs-lookup"><span data-stu-id="d5500-106">The default value for **max worker threads** is 0.</span></span> <span data-ttu-id="d5500-107">In questo modo, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è possibile configurare automaticamente il numero di thread di lavoro all'avvio.</span><span class="sxs-lookup"><span data-stu-id="d5500-107">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically configure the number of worker threads at startup.</span></span> <span data-ttu-id="d5500-108">L'impostazione predefinita è la migliore per la maggior parte dei sistemi.</span><span class="sxs-lookup"><span data-stu-id="d5500-108">The default setting is best for most systems.</span></span> <span data-ttu-id="d5500-109">A seconda della configurazione del sistema, tuttavia, l'impostazione di **max worker thread** su un valore specifico determina talvolta un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d5500-109">However, depending on your system configuration, setting **max worker threads** to a specific value sometimes improves performance.</span></span>  
  
 <span data-ttu-id="d5500-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d5500-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d5500-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d5500-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d5500-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d5500-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d5500-113">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="d5500-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="d5500-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5500-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d5500-115">**Per configurare l'opzione max worker threads utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="d5500-115">**To configure the max worker threads option, using:**</span></span>  
  
     [<span data-ttu-id="d5500-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d5500-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d5500-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d5500-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d5500-118">**Completamento:**  [Dopo la configurazione dell'opzione max worker threads](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d5500-118">**Follow Up:**  [After you configure the max worker threads option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d5500-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d5500-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d5500-120">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d5500-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d5500-121">Quando il numero effettivo di richieste di query è inferiore al valore impostato per **max worker threads**, viene assegnato un thread per la gestione di ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="d5500-121">When the actual number of query requests is less than the amount set in **max worker threads**, one thread handles each query request.</span></span> <span data-ttu-id="d5500-122">Tuttavia, se il numero effettivo di richieste di query supera il valore impostato per **max worker threads**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] il pool dei thread di lavoro in modo che il successivo thread di lavoro disponibile possa gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="d5500-122">However, if the actual number of query request exceeds the amount set in **max worker threads**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pools the worker threads so that the next available worker thread can handle the request.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d5500-123">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="d5500-123">Recommendations</span></span>  
  
-   <span data-ttu-id="d5500-124">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5500-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="d5500-125">La creazione di un pool di thread consente di ottimizzare le prestazioni quando al server è connesso un numero elevato di client.</span><span class="sxs-lookup"><span data-stu-id="d5500-125">Thread pooling helps optimize performance when large numbers of clients are connected to the server.</span></span> <span data-ttu-id="d5500-126">In genere viene creato un thread del sistema operativo distinto per ogni richiesta di query.</span><span class="sxs-lookup"><span data-stu-id="d5500-126">Usually, a separate operating system thread is created for each query request.</span></span> <span data-ttu-id="d5500-127">In presenza, tuttavia, di centinaia di connessioni al server, l'utilizzo di un thread per ogni richiesta di query può occupare quantità elevate di risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="d5500-127">However, with hundreds of connections to the server, using one thread per query request can consume large amounts of system resources.</span></span> <span data-ttu-id="d5500-128">L'opzione **max worker threads** consente di migliorare le prestazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] grazie alla creazione di un pool di thread di lavoro per soddisfare una maggiore quantità di richieste di query.</span><span class="sxs-lookup"><span data-stu-id="d5500-128">The **max worker threads** option enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to create a pool of worker threads to service a larger number of query requests, which improves performance.</span></span>  
  
-   <span data-ttu-id="d5500-129">Nella tabella seguente viene mostrato il numero massimo di thread di lavoro configurato automaticamente per diverse combinazioni di CPU e versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5500-129">The following table shows the automatically configured number of max worker threads for various combinations of CPUs and versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    |<span data-ttu-id="d5500-130">Numero di CPU</span><span class="sxs-lookup"><span data-stu-id="d5500-130">Number of CPUs</span></span>|<span data-ttu-id="d5500-131">computer a 32 bit</span><span class="sxs-lookup"><span data-stu-id="d5500-131">32-bit computer</span></span>|<span data-ttu-id="d5500-132">Computer a 64 bit</span><span class="sxs-lookup"><span data-stu-id="d5500-132">64-bit computer</span></span>|  
    |--------------------|----------------------|----------------------|  
    |<span data-ttu-id="d5500-133">\<= 4 processori</span><span class="sxs-lookup"><span data-stu-id="d5500-133">\<= 4 processors</span></span>|<span data-ttu-id="d5500-134">256</span><span class="sxs-lookup"><span data-stu-id="d5500-134">256</span></span>|<span data-ttu-id="d5500-135">512</span><span class="sxs-lookup"><span data-stu-id="d5500-135">512</span></span>|  
    |<span data-ttu-id="d5500-136">8 processori</span><span class="sxs-lookup"><span data-stu-id="d5500-136">8 processors</span></span>|<span data-ttu-id="d5500-137">288</span><span class="sxs-lookup"><span data-stu-id="d5500-137">288</span></span>|<span data-ttu-id="d5500-138">576</span><span class="sxs-lookup"><span data-stu-id="d5500-138">576</span></span>|  
    |<span data-ttu-id="d5500-139">16 processori</span><span class="sxs-lookup"><span data-stu-id="d5500-139">16 processors</span></span>|<span data-ttu-id="d5500-140">352</span><span class="sxs-lookup"><span data-stu-id="d5500-140">352</span></span>|<span data-ttu-id="d5500-141">704</span><span class="sxs-lookup"><span data-stu-id="d5500-141">704</span></span>|  
    |<span data-ttu-id="d5500-142">32 processori</span><span class="sxs-lookup"><span data-stu-id="d5500-142">32 processors</span></span>|<span data-ttu-id="d5500-143">480</span><span class="sxs-lookup"><span data-stu-id="d5500-143">480</span></span>|<span data-ttu-id="d5500-144">960</span><span class="sxs-lookup"><span data-stu-id="d5500-144">960</span></span>|  
    |<span data-ttu-id="d5500-145">64 processori</span><span class="sxs-lookup"><span data-stu-id="d5500-145">64 processors</span></span>|<span data-ttu-id="d5500-146">736</span><span class="sxs-lookup"><span data-stu-id="d5500-146">736</span></span>|<span data-ttu-id="d5500-147">1472</span><span class="sxs-lookup"><span data-stu-id="d5500-147">1472</span></span>|  
    |<span data-ttu-id="d5500-148">128 processori</span><span class="sxs-lookup"><span data-stu-id="d5500-148">128 processors</span></span>|<span data-ttu-id="d5500-149">4224</span><span class="sxs-lookup"><span data-stu-id="d5500-149">4224</span></span>|<span data-ttu-id="d5500-150">4480</span><span class="sxs-lookup"><span data-stu-id="d5500-150">4480</span></span>|  
    |<span data-ttu-id="d5500-151">256 processori</span><span class="sxs-lookup"><span data-stu-id="d5500-151">256 processors</span></span>|<span data-ttu-id="d5500-152">8320</span><span class="sxs-lookup"><span data-stu-id="d5500-152">8320</span></span>|<span data-ttu-id="d5500-153">8576</span><span class="sxs-lookup"><span data-stu-id="d5500-153">8576</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5500-154">Per consigli sull'uso di più di 64 CPU, vedere [Procedure consigliate per l'esecuzione di SQL Server in computer con più di 64 CPU](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d5500-154">For recommendations on using more than 64 CPUs, refer to [Best Practices for Running SQL Server on Computers That Have More Than 64 CPUs](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="d5500-155">Si consiglia 1024 come numero massimo di thread di lavoro per un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione in un computer a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="d5500-155">We recommend 1024 as the maximum number of worker threads for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on a 32-bit computer.</span></span>  
  
-   <span data-ttu-id="d5500-156">Se tutti i thread di lavoro sono attivi con query a esecuzione prolungata, si potrebbe non ricevere alcuna risposta da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finché un thread di lavoro non viene completato e diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="d5500-156">When all worker threads are active with long running queries, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might appear unresponsive until a worker thread completes and becomes available.</span></span> <span data-ttu-id="d5500-157">Anche se non si tratta di un difetto, questo comportamento può talvolta risultare indesiderato.</span><span class="sxs-lookup"><span data-stu-id="d5500-157">Although this is not a defect, it can sometimes be undesirable.</span></span> <span data-ttu-id="d5500-158">Se non si riceve risposta da un processo e non è possibile elaborare alcuna query, connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando la connessione amministrativa dedicata (DAC) e terminare il processo.</span><span class="sxs-lookup"><span data-stu-id="d5500-158">If a process appears to be unresponsive and no new queries can be processed, then connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the dedicated administrator connection (DAC), and kill the process.</span></span> <span data-ttu-id="d5500-159">Per evitare questo problema, aumentare il numero massimo di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d5500-159">To prevent this, increase the number of max worker threads.</span></span>  
  
 <span data-ttu-id="d5500-160">L'opzione di configurazione del server **max worker threads** non considera i thread che sono richiesti per tutte le attività di sistema come i gruppi di disponibilità, Service Broker, gestione blocchi e altri.</span><span class="sxs-lookup"><span data-stu-id="d5500-160">The **max worker threads** server configuration option does not take into account threads that are required for all the system tasks such as Availibility Groups, Service Broker, Lock Manager, and others.</span></span>  <span data-ttu-id="d5500-161">Se viene superato il numero di thread configurato, la seguente query fornirà informazioni sulle attività di sistema che hanno generato i thread aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d5500-161">If the number of threads configured are being exceeded, the following query will provide information about the system tasks that have spawned the additional threads.</span></span>  
  
```  
SELECT  
s.session_id,  
r.command,  
r.status,  
r.wait_type,  
r.scheduler_id,  
w.worker_address,  
w.is_preemptive,  
w.state,  
t.task_state,  
t.session_id,  
t.exec_context_id,  
t.request_id  
FROM sys.dm_exec_sessions AS s  
INNERJOIN sys.dm_exec_requests AS r  
    ON s.session_id = r.session_id  
INNER JOIN sys.dm_os_tasks AS t  
    ON r.task_address = t.task_address  
INNER JOIN sys.dm_os_workers AS w  
    ON t.worker_address = w.worker_address  
WHERE s.is_user_process = 0;  
  
```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d5500-162">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d5500-162">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d5500-163">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d5500-163">Permissions</span></span>  
 <span data-ttu-id="d5500-164">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d5500-164">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="d5500-165">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="d5500-165">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="d5500-166">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="d5500-166">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d5500-167">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d5500-167">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="d5500-168">Per configurare l'opzione max worker threads</span><span class="sxs-lookup"><span data-stu-id="d5500-168">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="d5500-169">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d5500-169">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d5500-170">Fare clic sul nodo **Processori** .</span><span class="sxs-lookup"><span data-stu-id="d5500-170">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="d5500-171">Nella casella **max worker threads** Digitare o selezionare un valore compreso tra 128 e 32767.</span><span class="sxs-lookup"><span data-stu-id="d5500-171">In the **Max worker threads** box, type or select a value from 128 through 32767.</span></span>  
  
     <span data-ttu-id="d5500-172">L'opzione **max worker threads** consente di configurare il numero di thread di lavoro disponibili per i processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5500-172">Use the **max worker threads** option to configure the number of worker threads available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> <span data-ttu-id="d5500-173">L'impostazione predefinita di **max worker threads** è ottimale per la maggior parte dei sistemi.</span><span class="sxs-lookup"><span data-stu-id="d5500-173">The default setting for **max worker threads** is best for most systems.</span></span> <span data-ttu-id="d5500-174">A seconda della configurazione del sistema, tuttavia, l'impostazione di **max worker thread** su un valore inferiore determina talvolta un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d5500-174">However, depending on your system configuration, setting **max worker threads** to a smaller value sometimes improves performance.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d5500-175">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d5500-175">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="d5500-176">Per configurare l'opzione max worker threads</span><span class="sxs-lookup"><span data-stu-id="d5500-176">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="d5500-177">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5500-177">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d5500-178">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d5500-178">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d5500-179">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d5500-179">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d5500-180">In questo esempio si illustra come utilizzare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per configurare l'opzione `max worker threads` su `900`.</span><span class="sxs-lookup"><span data-stu-id="d5500-180">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max worker threads` option to `900`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'max worker threads', 900 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="d5500-181">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="d5500-181">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-worker-threads-option"></a><a name="FollowUp"></a> <span data-ttu-id="d5500-182">Completamento: Dopo la configurazione dell'opzione max worker threads</span><span class="sxs-lookup"><span data-stu-id="d5500-182">Follow Up: After you configure the max worker threads option</span></span>  
 <span data-ttu-id="d5500-183">La modifica sarà applicata immediatamente senza richiedere il riavvio del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5500-183">The change will take effect immediately without requiring the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5500-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5500-184">See Also</span></span>  
 <span data-ttu-id="d5500-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5500-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="d5500-186">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d5500-186">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="d5500-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d5500-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="d5500-188">Connessione di diagnostica per gli amministratori di database</span><span class="sxs-lookup"><span data-stu-id="d5500-188">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
