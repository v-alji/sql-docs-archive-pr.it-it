---
title: Configurare il routing di sola lettura per un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- read-only routing
- Availability Groups [SQL Server], readable secondary replicas
- Availability Groups [SQL Server], read-only routing
- readable secondary replicas
- Availability Groups [SQL Server], client connectivity
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 7bd89ddd-0403-4930-a5eb-3c78718533d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d51d1db75caa29814a01fc1f49bfdd49b403c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635210"
---
# <a name="configure-read-only-routing-for-an-availability-group-sql-server"></a><span data-ttu-id="946f9-102">Configurare il routing di sola lettura per un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="946f9-102">Configure Read-Only Routing for an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="946f9-103">Per configurare un gruppo di disponibilità AlwaysOn in modo da supportare il routing di sola lettura in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], è possibile utilizzare [!INCLUDE[tsql](../../../includes/tsql-md.md)] o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="946f9-103">To configure an AlwaysOn availability group to support read-only routing in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can use either [!INCLUDE[tsql](../../../includes/tsql-md.md)] or PowerShell.</span></span> <span data-ttu-id="946f9-104">Con*routing di sola lettura* si intende la capacità di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] di instradare le richieste di connessione in sola lettura valide a una [replica secondaria leggibile](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) AlwaysOn, ovvero una replica configurata per consentire carichi di lavoro di sola lettura quando viene eseguita nel ruolo secondario.</span><span class="sxs-lookup"><span data-stu-id="946f9-104">*Read-only routing* refers to the ability of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to route qualifying read-only connection requests to an available AlwaysOn [readable secondary replica](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) (that is, a replica that is configured to allow read-only workloads when running under the secondary role).</span></span> <span data-ttu-id="946f9-105">Per supportare il routing di sola lettura, il gruppo di disponibilità deve possedere un [listener del gruppo di disponibilità](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-105">To support read-only routing, the availability group must possess an [availability group listener](../../listeners-client-connectivity-application-failover.md).</span></span> <span data-ttu-id="946f9-106">I client in sola lettura devono indirizzare le richieste di connessione al listener e le stringhe di connessione del client devono specificare la finalità dell'applicazione come in sola lettura,</span><span class="sxs-lookup"><span data-stu-id="946f9-106">Read-only clients must direct their connection requests to this listener, and the client's connection strings must specify the application intent as "read-only."</span></span> <span data-ttu-id="946f9-107">ovvero devono essere *richieste di connessione con finalità di lettura*.</span><span class="sxs-lookup"><span data-stu-id="946f9-107">That is, they must be *read-intent connection requests*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="946f9-108">Per informazioni su come configurare una replica secondaria leggibile, vedere [Configurare l'accesso in sola lettura in una replica di disponibilità &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-108">For information about how to configure a readable secondary replica, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="946f9-109">La configurazione del routing di sola lettura non è supportata in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="946f9-109">Configuring read-only routing is not supported by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="946f9-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="946f9-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="946f9-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="946f9-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="946f9-112">È necessario che il gruppo di disponibilità disponga di un listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="946f9-112">The availability group must possess an availability group listener.</span></span> <span data-ttu-id="946f9-113">Per altre informazioni, vedere [Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-113">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   <span data-ttu-id="946f9-114">È necessario configurare una o più repliche di disponibilità in modo che accettino solo la modalità di sola lettura nel ruolo secondario, ovvero le [repliche secondarie leggibili](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn% 20Availability% 20Groups \) . MD).</span><span class="sxs-lookup"><span data-stu-id="946f9-114">One or more availability replicas must be configured to accept read-only in the secondary role (that is, to be [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)(AlwaysOn%20Availability%20Groups\).md)).</span></span> <span data-ttu-id="946f9-115">Per altre informazioni, vedere [Configurare l'accesso in sola lettura in una replica di disponibilità &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-115">For more information, see [Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;](configure-read-only-access-on-an-availability-replica-sql-server.md).</span></span>  
  
-   <span data-ttu-id="946f9-116">È necessario essere connessi all'istanza del server che ospita la replica primaria corrente.</span><span class="sxs-lookup"><span data-stu-id="946f9-116">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
###  <a name="what-replica-properties-do-you-need-to-configure-to-support-read-only-routing"></a><a name="RORReplicaProperties"></a> <span data-ttu-id="946f9-117">Proprietà della replica da configurare per il supporto del routing di sola lettura</span><span class="sxs-lookup"><span data-stu-id="946f9-117">What Replica Properties Do you Need to Configure to Support Read-Only Routing?</span></span>  
  
-   <span data-ttu-id="946f9-118">Per ogni replica secondaria leggibile che deve supportare il routing di sola lettura, è necessario specificare un *URL di routing di sola lettura*.</span><span class="sxs-lookup"><span data-stu-id="946f9-118">For each readable secondary replica that is to support read-only routing, you need to specify a *read-only routing URL*.</span></span> <span data-ttu-id="946f9-119">L'URL viene usato solo quando la replica locale viene eseguita nel ruolo secondario.</span><span class="sxs-lookup"><span data-stu-id="946f9-119">This URL takes effect only when the local replica is running under the secondary role.</span></span> <span data-ttu-id="946f9-120">L'URL di routing di sola lettura deve essere specificato per ogni singola replica in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="946f9-120">The read-only routing URL must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="946f9-121">Ogni URL di routing di sola lettura viene usato per il routing delle richieste di connessione con finalità di lettura a una replica secondaria leggibile specifica.</span><span class="sxs-lookup"><span data-stu-id="946f9-121">Each read-only routing URL is used for routing read-intent connection requests to a specific readable secondary replica.</span></span> <span data-ttu-id="946f9-122">In genere, a ogni replica secondaria leggibile viene assegnato un URL di routing di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="946f9-122">Typically, every readable secondary replica is assigned a read-only routing URL.</span></span>  
  
     <span data-ttu-id="946f9-123">Per informazioni sul calcolo dell'URL di routing di sola lettura per una replica di disponibilità, vedere [Calcolo di read_only_routing_url per AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="946f9-123">For information about calculating the read-only routing URL for an availability replica, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
-   <span data-ttu-id="946f9-124">Per ogni replica di disponibilità che deve supportare il routing di sola lettura quando viene eseguita come replica primaria, è necessario specificare un *elenco di routing di sola lettura*.</span><span class="sxs-lookup"><span data-stu-id="946f9-124">For each availability replica that you want to support read-only routing when it is the primary replica, you need to specify a *read-only routing list*.</span></span> <span data-ttu-id="946f9-125">L'elenco di routing di sola lettura viene usato solo quando la replica locale viene eseguita nel ruolo primario.</span><span class="sxs-lookup"><span data-stu-id="946f9-125">A given read-only routing list takes effect only when the local replica is running under the primary role.</span></span> <span data-ttu-id="946f9-126">L'elenco deve essere specificato per ogni singola replica in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="946f9-126">This list must be specified on a replica-by-replica basis, as needed.</span></span> <span data-ttu-id="946f9-127">In genere, ciascun elenco di routing di sola lettura deve contenere tutti gli URL di routing di sola lettura, con l'URL della replica locale alla fine dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="946f9-127">Typically, each read-only routing list would contain every read-only routing URL, with the URL of the local replica at the end of the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="946f9-128">Le richieste di connessione con finalità di lettura vengono instradate alla prima replica secondaria leggibile disponibile nell'elenco di routing di sola lettura della replica primaria corrente.</span><span class="sxs-lookup"><span data-stu-id="946f9-128">Read-intent connection requests are routed to the first available readable secondary on the read-only routing list of the current primary replica.</span></span> <span data-ttu-id="946f9-129">Non viene eseguito alcun bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="946f9-129">There is no load balancing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="946f9-130">Per informazioni sui listener del gruppo di disponibilità e altre informazioni sul routing di sola lettura, vedere [Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-130">For information about availability group listeners and more information about read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="946f9-131">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="946f9-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="946f9-132">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="946f9-132">Permissions</span></span>  
  
|<span data-ttu-id="946f9-133">Attività</span><span class="sxs-lookup"><span data-stu-id="946f9-133">Task</span></span>|<span data-ttu-id="946f9-134">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="946f9-134">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="946f9-135">Per configurare le repliche durante la creazione di un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="946f9-135">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="946f9-136">Sono necessarie l'appartenenza al ruolo predefinito del server **sysadmin** e l'autorizzazione server CREATE AVAILABILITY GROUP oppure l'autorizzazione ALTER ANY AVAILABILITY GROUP o CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="946f9-136">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="946f9-137">Per modificare una replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="946f9-137">To modify an availability replica</span></span>|<span data-ttu-id="946f9-138">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="946f9-138">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="946f9-139">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="946f9-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="946f9-140">**Per configurare il routing di sola lettura**</span><span class="sxs-lookup"><span data-stu-id="946f9-140">**To Configure read-only routing**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="946f9-141">Per un esempio di codice, vedere [Esempio (Transact-SQL)](#TsqlExample), più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="946f9-141">For a code example, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="946f9-142">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="946f9-142">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="946f9-143">Se si specifica una replica per un nuovo gruppo di disponibilità, usare l'istruzione [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="946f9-143">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="946f9-144">Se si aggiunge o si modifica una replica per un gruppo di disponibilità esistente, utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="946f9-144">If you are adding or modifying a replica for an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="946f9-145">Per configurare il routing di sola lettura per il ruolo secondario, nella clausola ADD REPLICA o MODIFY REPLICA WITH specificare l'opzione SECONDARY_ROLE, come segue:</span><span class="sxs-lookup"><span data-stu-id="946f9-145">To configure read-only routing for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="946f9-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **='** TCP **:// *`system-address`* : *`port`* ')**</span><span class="sxs-lookup"><span data-stu-id="946f9-146">SECONDARY_ROLE **(** READ_ONLY_ROUTING_URL **='** TCP **://*`system-address`*:*`port`*')**</span></span>  
  
         <span data-ttu-id="946f9-147">I parametri dell'URL del routing di sola lettura sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="946f9-147">The parameters of the read-only routing URL are as follows:</span></span>  
  
         <span data-ttu-id="946f9-148">*system-address*</span><span class="sxs-lookup"><span data-stu-id="946f9-148">*system-address*</span></span>  
         <span data-ttu-id="946f9-149">Stringa, ad esempio un nome di sistema, un nome di dominio completo o un indirizzo IP, che identifica in modo univoco il computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="946f9-149">Is a string, such as a system name, a fully qualified domain name, or an IP address, that unambiguously identifies the destination computer system.</span></span>  
  
         <span data-ttu-id="946f9-150">*port*</span><span class="sxs-lookup"><span data-stu-id="946f9-150">*port*</span></span>  
         <span data-ttu-id="946f9-151">Numero di porta utilizzato dal motore di database dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="946f9-151">Is a port number that is used by the Database Engine of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="946f9-152">Esempio:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span><span class="sxs-lookup"><span data-stu-id="946f9-152">For example:   `SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433')`</span></span>  
  
         <span data-ttu-id="946f9-153">In una clausola MODIFY REPLICA l'argomento ALLOW_CONNECTIONS è facoltativo se la replica è già configurata per consentire connessioni in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="946f9-153">In a MODIFY REPLICA clause the ALLOW_CONNECTIONS is optional if the replica is already configured to allow read-only connections.</span></span>  
  
         <span data-ttu-id="946f9-154">Per ulteriori informazioni, vedere [Calcolo di Read_only_routing_url per AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="946f9-154">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="946f9-155">Per configurare il routing di sola lettura per il ruolo primario, nella clausola ADD REPLICA o MODIFY REPLICA WITH specificare l'opzione PRIMARY_ROLE, come segue:</span><span class="sxs-lookup"><span data-stu-id="946f9-155">To configure read-only routing for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="946f9-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **= (' *`server`* '** [ **,**... *n* ] **)**</span><span class="sxs-lookup"><span data-stu-id="946f9-156">PRIMARY_ROLE **(** READ_ONLY_ROUTING_LIST **=('*`server`*'** [ **,**...*n* ] **))**</span></span>  
  
         <span data-ttu-id="946f9-157">dove *server* identifica un'istanza del server in cui viene ospitata una replica secondaria di sola lettura nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="946f9-157">where, *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span>  
  
         <span data-ttu-id="946f9-158">Esempio:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span><span class="sxs-lookup"><span data-stu-id="946f9-158">For example:   `PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('Server1','Server2'))`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="946f9-159">È necessario impostare l'URL del routing di sola lettura prima di configurare l'elenco di routing di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="946f9-159">You must set the read-only routing URL before configuring the read-only routing list.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="946f9-160">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="946f9-160">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="946f9-161">Nell'esempio seguente vengono modificate due repliche di disponibilità di un gruppo di disponibilità esistente, `AG1` , per supportare il routing di sola lettura se a una di queste repliche è attualmente assegnato il ruolo primario.</span><span class="sxs-lookup"><span data-stu-id="946f9-161">The following example modifies two availability replicas of an existing availability group, `AG1` to support read-only routing if one of these replicas currently owns the primary role.</span></span> <span data-ttu-id="946f9-162">Per identificare le istanze del server che ospitano la replica di disponibilità, in questo esempio vengono specificati i nomi delle istanze, `COMPUTER01` e `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="946f9-162">To identify the server instances that host the availability replica, this example specifies the instance names-`COMPUTER01` and `COMPUTER02`.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER01.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY));  
ALTER AVAILABILITY GROUP [AG1]  
 MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(SECONDARY_ROLE (READ_ONLY_ROUTING_URL = N'TCP://COMPUTER02.contoso.com:1433'));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER01' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER02','COMPUTER01')));  
  
ALTER AVAILABILITY GROUP [AG1]   
MODIFY REPLICA ON  
N'COMPUTER02' WITH   
(PRIMARY_ROLE (READ_ONLY_ROUTING_LIST=('COMPUTER01','COMPUTER02')));  
GO
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="946f9-163">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="946f9-163">Using PowerShell</span></span>  

### <a name="to-configure-read-only-routing"></a><span data-ttu-id="946f9-164">Per configurare il routing di sola lettura</span><span class="sxs-lookup"><span data-stu-id="946f9-164">To Configure read-only routing</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="946f9-165">Per un esempio di codice, vedere [Esempio (PowerShell)](#PSExample), più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="946f9-165">For a code example, see [Example (PowerShell)](#PSExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="946f9-166">Impostare il valore predefinito (`cd`) sull'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="946f9-166">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="946f9-167">Quando si aggiunge una replica di disponibilità a un gruppo di disponibilità, utilizzare il cmdlet `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="946f9-167">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="946f9-168">Quando si modifica una replica di disponibilità esistente, utilizzare il cmdlet `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="946f9-168">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="946f9-169">I parametri pertinenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="946f9-169">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="946f9-170">Per configurare il routing di sola lettura per il ruolo secondario, specificare il parametro **parametro ReadonlyRoutingConnectionUrl " *`url`* "** .</span><span class="sxs-lookup"><span data-stu-id="946f9-170">To configure read-only routing for the secondary role, specify the **ReadonlyRoutingConnectionUrl"*`url`*"** parameter.</span></span>  
  
         <span data-ttu-id="946f9-171">dove *url* è il nome di dominio completo (FQDN) e la porta di connettività da usare in caso di routing alla replica per le connessioni di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="946f9-171">where, *url* is the connectivity fully-qualified domain name (FQDN) and port to use when routing to the replica for read-only connections.</span></span> <span data-ttu-id="946f9-172">Ad esempio: `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span><span class="sxs-lookup"><span data-stu-id="946f9-172">For example:  `-ReadonlyRoutingConnectionUrl "TCP://DBSERVER8.manufacturing.Adventure-Works.com:7024"`</span></span>  
  
         <span data-ttu-id="946f9-173">Per ulteriori informazioni, vedere [Calcolo di Read_only_routing_url per AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span><span class="sxs-lookup"><span data-stu-id="946f9-173">For more information, see [Calculating read_only_routing_url for AlwaysOn](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson).</span></span>  
  
    -   <span data-ttu-id="946f9-174">Per configurare l'accesso alla connessione per il ruolo primario, specificare **ReadonlyRoutingList " *`server`* "** [ **,**... *n* ], dove *Server* identifica un'istanza del server che ospita una replica secondaria di sola lettura nel gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="946f9-174">To configure connection access for the primary role, specify **ReadonlyRoutingList"*`server`*"** [ **,**...*n* ], where *server* identifies a server instance that hosts a read-only secondary replica in the availability group.</span></span> <span data-ttu-id="946f9-175">Ad esempio: `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span><span class="sxs-lookup"><span data-stu-id="946f9-175">For example:  `-ReadOnlyRoutingList "SecondaryServer","PrimaryServer"`</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="946f9-176">È necessario impostare l'URL del routing di sola lettura di una replica prima di configurare il relativo elenco di routing di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="946f9-176">You must set the read-only routing URL of a replica before configuring its read-only routing list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="946f9-177">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="946f9-177">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="946f9-178">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-178">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="946f9-179">Per configurare e usare il provider di SQL Server PowerShell, vedere [provider SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md) e [ottenere assistenza SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-179">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md) and [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>
  
###  <a name="example-powershell"></a><a name="PSExample"></a> <span data-ttu-id="946f9-180">Esempio (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="946f9-180">Example (PowerShell)</span></span>  
 <span data-ttu-id="946f9-181">Nell'esempio seguente vengono configurate la replica primaria e una replica secondaria in un gruppo di disponibilità per il routing di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="946f9-181">The following example configures the primary replica and one secondary replica in an availability group for read-only routing.</span></span> <span data-ttu-id="946f9-182">Innanzi tutto, nell'esempio viene assegnato un URL di routing di sola lettura a ciascuna replica.</span><span class="sxs-lookup"><span data-stu-id="946f9-182">First, the example assigns a read-only routing URL to each replica.</span></span> <span data-ttu-id="946f9-183">L'elenco di routing di sola lettura viene quindi impostato sulla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="946f9-183">Then it sets the read-only routing list on the primary replica.</span></span> <span data-ttu-id="946f9-184">Le connessioni la cui proprietà "ReadOnly" è impostata nella stringa di connessione verranno reindirizzate alla replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="946f9-184">Connections with the "ReadOnly" property set in the connection string will be redirected to the secondary replica.</span></span> <span data-ttu-id="946f9-185">Se la replica secondaria non è leggibile (in base all'impostazione `ConnectionModeInSecondaryRole`), la connessione verrà nuovamente indirizzata alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="946f9-185">If this secondary replica is not readable (as determined by the `ConnectionModeInSecondaryRole` setting), the connection will be directed back to the primary replica.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  
$secondaryReplica = Get-Item "AvailabilityReplicas\SecondaryServer"  
  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://PrimaryServer.domain.com:1433" -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingConnectionUrl "TCP://SecondaryServer.domain.com:1433" -InputObject $secondaryReplica  
Set-SqlAvailabilityReplica -ReadOnlyRoutingList "SecondaryServer","PrimaryServer" -InputObject $primaryReplica  
```  
  
##  <a name="follow-up-after-configuring-read-only-routing"></a><a name="FollowUp"></a> <span data-ttu-id="946f9-186">Completamento: Dopo la configurazione del routing di sola lettura</span><span class="sxs-lookup"><span data-stu-id="946f9-186">Follow Up: After Configuring Read-Only Routing</span></span>  
 <span data-ttu-id="946f9-187">Una volta configurate la replica primaria corrente e le repliche secondarie leggibili per supportare il routing di sola lettura in entrambi i ruoli, le repliche secondarie leggibili potranno ricevere richieste di connessione con finalità di lettura dai client che si connettono tramite il listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="946f9-187">Once the current primary replica and the readable secondary replicas are configured to support read-only routing in both roles, the readable secondary replicas can receive read read-intent connection requests from clients that connect via the availability group listener.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="946f9-188">Quando si usa l'utilità [bcp](../../../tools/bcp-utility.md) o l' [utilità sqlcmd](../../../tools/sqlcmd-utility.md), è possibile specificare l'accesso in sola lettura a qualsiasi replica secondaria abilitata per l'accesso in sola lettura specificando l' `-K ReadOnly` opzione.</span><span class="sxs-lookup"><span data-stu-id="946f9-188">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
###  <a name="requirements-and-recommendations-for-client-connection-strings"></a><a name="ConnStringReqsRecs"></a> <span data-ttu-id="946f9-189">Requisiti e indicazioni per le stringhe di connessione del client</span><span class="sxs-lookup"><span data-stu-id="946f9-189">Requirements and Recommendations for Client Connection-Strings</span></span>  
 <span data-ttu-id="946f9-190">Per consentire a un'applicazione client di utilizzare il routing di sola lettura, è necessario che la relativa stringa di connessione soddisfi i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="946f9-190">For a client application to use read-only routing, its connection string must satisfy the following requirements:</span></span>  
  
-   <span data-ttu-id="946f9-191">Utilizzare il protocollo TCP.</span><span class="sxs-lookup"><span data-stu-id="946f9-191">Use the TCP protocol.</span></span>  
  
-   <span data-ttu-id="946f9-192">Impostare la proprietà o l'attributo della finalità dell'applicazione su readonly.</span><span class="sxs-lookup"><span data-stu-id="946f9-192">Set the application intent attribute/property to readonly.</span></span>  
  
-   <span data-ttu-id="946f9-193">Fare riferimento al listener di un gruppo di disponibilità configurato per supportare il routing di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="946f9-193">Reference the listener of an availability group that is configured to support read-only routing.</span></span>  
  
-   <span data-ttu-id="946f9-194">Fare riferimento a un database in tale gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="946f9-194">Reference a database in that availability group.</span></span>  
  
 <span data-ttu-id="946f9-195">È inoltre consigliabile che le stringhe di connessione consentano il failover su più subnet, che supporta un thread client parallelo per ogni replica in ogni subnet.</span><span class="sxs-lookup"><span data-stu-id="946f9-195">In addition, we recommend that connection strings enable multi-subnet failover, which supports a parallel client thread for each replica on each subnet.</span></span> <span data-ttu-id="946f9-196">In questo modo di riduce al minimo il tempo di riconnessione del client dopo un failover.</span><span class="sxs-lookup"><span data-stu-id="946f9-196">This minimizes client reconnection time after a failover.</span></span>  
  
 <span data-ttu-id="946f9-197">La sintassi per una stringa di connessione dipende dal provider SQL Server utilizzato da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="946f9-197">The syntax for a connection string depends on the SQL Server provider an application is using.</span></span> <span data-ttu-id="946f9-198">Nella stringa di connessione di esempio seguente per il Provider di dati .NET Framework 4.0.2 per SQL Server sono illustrate le parti di una stringa di connessione necessarie e consigliate per il funzionamento del routing di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="946f9-198">The following example connection string for the .NET Framework Data Provider 4.0.2 for SQL Server illustrates the parts of a connection string that are required and recommended to work for read-only routing.</span></span>  
  
```  
Server=tcp:MyAgListener,1433;Database=Db1;IntegratedSecurity=SSPI;ApplicationIntent=ReadOnly;MultiSubnetFailover=True  
```  
  
 <span data-ttu-id="946f9-199">Per altre informazioni sulla finalità dell'applicazione di sola lettura e sul routing di sola lettura, vedere [Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-199">For more information about read-only application intent and read-only routing, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
### <a name="if-read-only-routing-is-not-working-correctly"></a><span data-ttu-id="946f9-200">Se il routing di sola lettura non funziona correttamente</span><span class="sxs-lookup"><span data-stu-id="946f9-200">If Read-Only Routing is Not Working Correctly</span></span>  
 <span data-ttu-id="946f9-201">Per informazioni sulla risoluzione dei problemi di una configurazione di routing di sola lettura, vedere [Il routing di sola lettura non funziona correttamente](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="946f9-201">For information about troubleshooting a read-only routing configuration, see [Read-Only Routing is Not Working Correctly](troubleshoot-always-on-availability-groups-configuration-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="946f9-202">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="946f9-202">Related Tasks</span></span>  

### <a name="to-view-read-only-routing-configurations"></a><span data-ttu-id="946f9-203">Per visualizzare le configurazioni del routing di sola lettura</span><span class="sxs-lookup"><span data-stu-id="946f9-203">To view read-only routing configurations</span></span>
  
-   [<span data-ttu-id="946f9-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="946f9-204">sys.availability_read_only_routing_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
  
-   <span data-ttu-id="946f9-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (colonna **read_only_routing_url**)</span><span class="sxs-lookup"><span data-stu-id="946f9-205">[sys.availability_replicas &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) (**read_only_routing_url** column)</span></span>  
  
### <a name="to-configure-client-connection-access"></a><span data-ttu-id="946f9-206">Per configurare l'accesso alla connessione client</span><span class="sxs-lookup"><span data-stu-id="946f9-206">To configure client connection access</span></span>
  
-   [<span data-ttu-id="946f9-207">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="946f9-207">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="946f9-208">Configurare l'accesso in sola lettura in una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="946f9-208">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
### <a name="to-use-connection-strings-in-applications"></a><span data-ttu-id="946f9-209">Per utilizzare stringhe di connessione nelle applicazioni</span><span class="sxs-lookup"><span data-stu-id="946f9-209">To use connection strings in applications</span></span>
  
-   [<span data-ttu-id="946f9-210">Supporto di SQL Server Native Client per il ripristino di emergenza a disponibilità elevata</span><span class="sxs-lookup"><span data-stu-id="946f9-210">SQL Server Native Client Support for High Availability, Disaster Recovery</span></span>](../../../relational-databases/native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md)  
  
-   [<span data-ttu-id="946f9-211">Utilizzo delle parole chiave delle stringhe di connessione con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="946f9-211">Using Connection String Keywords with SQL Server Native Client</span></span>](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="946f9-212">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="946f9-212">Related Content</span></span>  
  
-   <span data-ttu-id="946f9-213">**Blog:**</span><span class="sxs-lookup"><span data-stu-id="946f9-213">**Blogs:**</span></span>  
  
     [<span data-ttu-id="946f9-214">Calcolo di read_only_routing_url per AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="946f9-214">Calculating read_only_routing_url for AlwaysOn</span></span>](https://docs.microsoft.com/archive/blogs/mattn/calculating-read_only_routing_url-for-alwayson)  
  
     [<span data-ttu-id="946f9-215">Blog del team di SQL Server AlwaysOn: Blog ufficiale del team di SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="946f9-215">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="946f9-216">Pagina relativa ai blog del Servizio Supporto Tecnico Clienti per gli ingegneri di SQL Server</span><span class="sxs-lookup"><span data-stu-id="946f9-216">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="946f9-217">**White paper:**</span><span class="sxs-lookup"><span data-stu-id="946f9-217">**White papers:**</span></span>  
  
     [<span data-ttu-id="946f9-218">Pagina relativa ai white paper Microsoft per SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="946f9-218">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="946f9-219">Pagina relativa ai white paper del team di consulenza clienti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="946f9-219">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="946f9-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="946f9-220">See Also</span></span>  
 <span data-ttu-id="946f9-221">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="946f9-221">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="946f9-222">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="946f9-222">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="946f9-223">[Repliche secondarie attive: repliche secondarie leggibili (Gruppi di disponibilità AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="946f9-223">[Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 <span data-ttu-id="946f9-224">[Informazioni sull'accesso alla connessione client per le repliche di disponibilità &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="946f9-224">[About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) </span></span>  
 [<span data-ttu-id="946f9-225">Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="946f9-225">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
