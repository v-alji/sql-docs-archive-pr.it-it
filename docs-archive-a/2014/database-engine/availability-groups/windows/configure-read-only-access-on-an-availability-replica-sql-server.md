---
title: Configurare l'accesso in sola lettura in una replica di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- connection access to availability replicas
- Availability Groups [SQL Server], readable secondary replicas
- active secondary replicas [SQL Server], read-only access to
- Availability Groups [SQL Server], read-only routing
- Availability Groups [SQL Server], client connectivity
ms.assetid: 22387419-22c4-43fa-851c-5fecec4b049b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab13081396aff46d193c1b0449d6b93042ee60d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713512"
---
# <a name="configure-read-only-access-on-an-availability-replica-sql-server"></a><span data-ttu-id="989f1-102">Configurare l'accesso in sola lettura in una replica di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="989f1-102">Configure Read-Only Access on an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="989f1-103">Per impostazione predefinita, gli accessi in lettura e scrittura e l'accesso con finalità di lettura sono entrambi consentiti alla replica primaria, ma alle repliche secondarie non sono consentite connessioni di un gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="989f1-103">By default both read-write and read-intent access are allowed to the primary replica and no connections are allowed to secondary replicas of an AlwaysOn availability group.</span></span> <span data-ttu-id="989f1-104">In questo argomento viene illustrato come configurare l'accesso alla connessione su una replica di disponibilità di un gruppo di disponibilità AlwaysOn in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="989f1-104">This topic describes how to configure connection access on an availability replica of an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="989f1-105">Per informazioni sulle implicazioni dell'abilitazione dell'accesso di sola lettura per una replica secondaria e per un'introduzione all'accesso alla connessione, vedere [Informazioni sull'accesso alla connessione client per le repliche di disponibilità &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) e [Repliche secondarie attive: Repliche secondarie leggibili &#40;Gruppi di disponibilità AlwaysOn&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="989f1-105">For information about the implications of enabling read-only access for a secondary replica and for an introduction to connection access, see [About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) and [Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="989f1-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="989f1-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="989f1-107">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="989f1-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="989f1-108">Per configurare un accesso alla connessione diverso, è necessario essere connessi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="989f1-108">To configure different connection access, you must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="989f1-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="989f1-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="989f1-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="989f1-110">Permissions</span></span>  
  
|<span data-ttu-id="989f1-111">Attività</span><span class="sxs-lookup"><span data-stu-id="989f1-111">Task</span></span>|<span data-ttu-id="989f1-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="989f1-112">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="989f1-113">Per configurare le repliche durante la creazione di un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="989f1-113">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="989f1-114">Sono necessarie l'appartenenza al ruolo predefinito del server **sysadmin** e l'autorizzazione server CREATE AVAILABILITY GROUP oppure l'autorizzazione ALTER ANY AVAILABILITY GROUP o CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="989f1-114">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="989f1-115">Per modificare una replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="989f1-115">To modify an availability replica</span></span>|<span data-ttu-id="989f1-116">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="989f1-116">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="989f1-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="989f1-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="989f1-118">**Per configurare l'accesso su una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="989f1-118">**To configure access on an availability replica**</span></span>  
  
1.  <span data-ttu-id="989f1-119">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="989f1-119">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="989f1-120">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="989f1-120">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="989f1-121">Fare clic sul gruppo di disponibilità di cui si desidera modificare la replica.</span><span class="sxs-lookup"><span data-stu-id="989f1-121">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="989f1-122">Fare clic con il pulsante destro del mouse sulla replica di disponibilità e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="989f1-122">Right-click the availability replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="989f1-123">Nella finestra di dialogo **Proprietà replica di disponibilità** è possibile modificare l'accesso alla connessione per il ruolo primario e per il ruolo secondario, come segue:</span><span class="sxs-lookup"><span data-stu-id="989f1-123">In the **Availability Replica Properties** dialog box, you can change the connection access for the primary role and for the secondary role, as follows:</span></span>  
  
    -   <span data-ttu-id="989f1-124">Per il ruolo secondario, selezionare un nuovo valore dall'elenco a discesa **Secondario leggibile** , come segue:</span><span class="sxs-lookup"><span data-stu-id="989f1-124">For the secondary role, select a new value from the **Readable secondary** drop list, as follows:</span></span>  
  
         <span data-ttu-id="989f1-125">**No**</span><span class="sxs-lookup"><span data-stu-id="989f1-125">**No**</span></span>  
         <span data-ttu-id="989f1-126">Non sono consentite connessioni utente ai database secondari di questa replica.</span><span class="sxs-lookup"><span data-stu-id="989f1-126">No user connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="989f1-127">I database non sono disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-127">They are not available for read access.</span></span> <span data-ttu-id="989f1-128">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="989f1-128">This is the default setting.</span></span>  
  
         <span data-ttu-id="989f1-129">**Solo con finalità di lettura**</span><span class="sxs-lookup"><span data-stu-id="989f1-129">**Read-intent only**</span></span>  
         <span data-ttu-id="989f1-130">Sono consentite solo connessioni in sola lettura ai database secondari di questa replica.</span><span class="sxs-lookup"><span data-stu-id="989f1-130">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="989f1-131">Il database o i database secondari sono tutti disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-131">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="989f1-132">**Sì**</span><span class="sxs-lookup"><span data-stu-id="989f1-132">**Yes**</span></span>  
         <span data-ttu-id="989f1-133">Sono consentite tutte le connessioni ai database secondari di questa replica, ma solo per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-133">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="989f1-134">Il database o i database secondari sono tutti disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-134">The secondary database(s) are all available for read access.</span></span>  
  
    -   <span data-ttu-id="989f1-135">Per il ruolo primario, selezionare un nuovo valore dall'elenco a discesa **Connessioni nel ruolo primario** , come segue:</span><span class="sxs-lookup"><span data-stu-id="989f1-135">For the primary role, select a new value from the **Connections in primary role** drop list, as follows:</span></span>  
  
         <span data-ttu-id="989f1-136">**Consenti tutte le connessioni**</span><span class="sxs-lookup"><span data-stu-id="989f1-136">**Allow all connections**</span></span>  
         <span data-ttu-id="989f1-137">Sono consentite tutte le connessioni ai database nella replica primaria.</span><span class="sxs-lookup"><span data-stu-id="989f1-137">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="989f1-138">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="989f1-138">This is the default setting.</span></span>  
  
         <span data-ttu-id="989f1-139">**Consenti connessioni in lettura/scrittura**</span><span class="sxs-lookup"><span data-stu-id="989f1-139">**Allow read/write connections**</span></span>  
         <span data-ttu-id="989f1-140">Se la proprietà Finalità dell'applicazione è impostata su **Lettura/Scrittura** o se tale proprietà non è impostata, la connessione è consentita.</span><span class="sxs-lookup"><span data-stu-id="989f1-140">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="989f1-141">Non sono consentite le connessioni in cui la proprietà di connessione Finalità dell'applicazione è impostata su **Sola lettura** .</span><span class="sxs-lookup"><span data-stu-id="989f1-141">Connections where the Application Intent connection property is set to **ReadOnly** are not allowed.</span></span> <span data-ttu-id="989f1-142">In questo modo è possibile impedire la connessione, per errore, di un carico di lavoro con finalità di lettura alla replica primaria da parte dei clienti.</span><span class="sxs-lookup"><span data-stu-id="989f1-142">This can help prevent customers from connecting a read-intent work load to the primary replica by mistake.</span></span> <span data-ttu-id="989f1-143">Per altre informazioni sulla proprietà di connessione Finalità dell'applicazione, vedere [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="989f1-143">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="989f1-144">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="989f1-144">Using Transact-SQL</span></span>  
 <span data-ttu-id="989f1-145">**Per configurare l'accesso su una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="989f1-145">**To configure access on an availability replica**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="989f1-146">Per un esempio di questa procedura, vedere [Esempio (Transact-SQL)](#TsqlExample)più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="989f1-146">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="989f1-147">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="989f1-147">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="989f1-148">Se si specifica una replica per un nuovo gruppo di disponibilità, usare l'istruzione [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="989f1-148">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="989f1-149">Se si aggiunge o si modifica una replica di un gruppo di disponibilità esistente, usare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="989f1-149">If you are adding or modifying a replica of an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="989f1-150">Per configurare l'accesso alla connessione per il ruolo secondario, nella clausola ADD REPLICA o MODIFY REPLICA WITH specificare l'opzione SECONDARY_ROLE, come segue:</span><span class="sxs-lookup"><span data-stu-id="989f1-150">To configure connection access for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="989f1-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="989f1-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span></span>  
  
         <span data-ttu-id="989f1-152">dove</span><span class="sxs-lookup"><span data-stu-id="989f1-152">where,</span></span>  
  
         <span data-ttu-id="989f1-153">NO</span><span class="sxs-lookup"><span data-stu-id="989f1-153">NO</span></span>  
         <span data-ttu-id="989f1-154">Non sono consentite connessioni dirette ai database secondari di questa replica.</span><span class="sxs-lookup"><span data-stu-id="989f1-154">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="989f1-155">I database non sono disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-155">They are not available for read access.</span></span> <span data-ttu-id="989f1-156">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="989f1-156">This is the default setting.</span></span>  
  
         <span data-ttu-id="989f1-157">READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="989f1-157">READ_ONLY</span></span>  
         <span data-ttu-id="989f1-158">Sono consentite solo connessioni in sola lettura ai database secondari di questa replica.</span><span class="sxs-lookup"><span data-stu-id="989f1-158">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="989f1-159">Il database o i database secondari sono tutti disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-159">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="989f1-160">ALL</span><span class="sxs-lookup"><span data-stu-id="989f1-160">ALL</span></span>  
         <span data-ttu-id="989f1-161">Sono consentite tutte le connessioni ai database secondari di questa replica, ma solo per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-161">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="989f1-162">Il database o i database secondari sono tutti disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-162">The secondary database(s) are all available for read access.</span></span>  
  
3.  <span data-ttu-id="989f1-163">Per configurare l'accesso alla connessione per il ruolo primario, nella clausola ADD REPLICA o MODIFY REPLICA WITH specificare l'opzione PRIMARY_ROLE, come segue:</span><span class="sxs-lookup"><span data-stu-id="989f1-163">To configure connection access for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
     <span data-ttu-id="989f1-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="989f1-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span></span>  
  
     <span data-ttu-id="989f1-165">dove</span><span class="sxs-lookup"><span data-stu-id="989f1-165">where,</span></span>  
  
     <span data-ttu-id="989f1-166">READ_WRITE</span><span class="sxs-lookup"><span data-stu-id="989f1-166">READ_WRITE</span></span>  
     <span data-ttu-id="989f1-167">Non sono consentite le connessioni in cui la proprietà di connessione Finalità dell'applicazione è impostata su **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="989f1-167">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span>  <span data-ttu-id="989f1-168">Se la proprietà Finalità dell'applicazione è impostata su **Lettura/Scrittura** o se tale proprietà non è impostata, la connessione è consentita.</span><span class="sxs-lookup"><span data-stu-id="989f1-168">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="989f1-169">Per altre informazioni sulla proprietà di connessione Finalità dell'applicazione, vedere [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="989f1-169">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
     <span data-ttu-id="989f1-170">ALL</span><span class="sxs-lookup"><span data-stu-id="989f1-170">ALL</span></span>  
     <span data-ttu-id="989f1-171">Sono consentite tutte le connessioni ai database nella replica primaria.</span><span class="sxs-lookup"><span data-stu-id="989f1-171">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="989f1-172">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="989f1-172">This is the default setting.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="989f1-173">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="989f1-173">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="989f1-174">L'esempio seguente aggiunge una replica secondaria a un gruppo di disponibilità denominato *AG2*.</span><span class="sxs-lookup"><span data-stu-id="989f1-174">The following example adds a secondary replica to an availability group named *AG2*.</span></span> <span data-ttu-id="989f1-175">Un'istanza del server autonoma, *COMPUTER03\HADR_INSTANCE*, viene specificata per ospitare la nuova replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="989f1-175">A stand-alone server instance, *COMPUTER03\HADR_INSTANCE*, is specified to host the new availability replica.</span></span> <span data-ttu-id="989f1-176">Questa replica è configurata per consentire unicamente le connessioni in lettura e scrittura per il ruolo primario e le connessioni con finalità di lettura per il ruolo secondario.</span><span class="sxs-lookup"><span data-stu-id="989f1-176">This replica configured to allow only read-write connections for the primary role and to allow only read-intent connections for secondary role.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AG2   
   ADD REPLICA ON   
      'COMPUTER03\HADR_INSTANCE' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER03:7022',  
         PRIMARY_ROLE ( ALLOW_CONNECTIONS = READ_WRITE ),  
         SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY )  
         );   
GO  
```  
  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="989f1-177">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="989f1-177">Using PowerShell</span></span>  

### <a name="to-configure-access-on-an-availability-replica"></a><span data-ttu-id="989f1-178">Per configurare l'accesso su una replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="989f1-178">To configure access on an availability replica</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="989f1-179">Per un esempio di codice, vedere gli esempi di PowerShell più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="989f1-179">For a code example, see the PowerShell examples later in this section.</span></span>  
  
1.  <span data-ttu-id="989f1-180">Spostarsi nella directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="989f1-180">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="989f1-181">Quando si aggiunge una replica di disponibilità a un gruppo di disponibilità, utilizzare il cmdlet `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="989f1-181">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="989f1-182">Quando si modifica una replica di disponibilità esistente, utilizzare il cmdlet `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="989f1-182">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="989f1-183">I parametri pertinenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="989f1-183">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="989f1-184">Per configurare l'accesso alla connessione per il ruolo secondario, specificare il `ConnectionModeInSecondaryRole` parametro *secondary_role_keyword* , dove *secondary_role_keyword* è uguale a uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="989f1-184">To configure connection access for the secondary role, specify the `ConnectionModeInSecondaryRole`*secondary_role_keyword* parameter, where *secondary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowNoConnections`  
         <span data-ttu-id="989f1-185">Non è consentita alcuna connessione diretta ai database nella replica secondaria e i database non sono disponibili per l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-185">No direct connections are allowed to the databases in the secondary replica and the databases are not available for read access.</span></span> <span data-ttu-id="989f1-186">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="989f1-186">This is the default setting.</span></span>  
  
         `AllowReadIntentConnectionsOnly`  
         <span data-ttu-id="989f1-187">Sono consentite solo connessioni ai database nella replica secondaria in cui la proprietà Finalità dell'applicazione è impostata su **Sola lettura**.</span><span class="sxs-lookup"><span data-stu-id="989f1-187">Connections are allowed only to the databases in the secondary replica where the Application Intent property is set to **ReadOnly**.</span></span> <span data-ttu-id="989f1-188">Per altre informazioni su questa proprietà, vedere [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="989f1-188">For more information about this property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="989f1-189">Sono consentite tutte le connessioni ai database nella replica secondaria per l'accesso in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="989f1-189">All connections are allowed to the databases in the secondary replica for read-only access.</span></span>  
  
    -   <span data-ttu-id="989f1-190">Per configurare l'accesso alla connessione per il ruolo primario, specificare `ConnectionModeInPrimaryRole` *primary_role_keyword*, dove *primary_role_keyword* è uguale a uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="989f1-190">To configure connection access for the primary role, specify `ConnectionModeInPrimaryRole`*primary_role_keyword*, where *primary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowReadWriteConnections`  
         <span data-ttu-id="989f1-191">Non sono consentite le connessioni in cui la proprietà di connessione Finalità dell'applicazione è impostata su ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="989f1-191">Connections where the Application Intent connection property is set to ReadOnly are disallowed.</span></span> <span data-ttu-id="989f1-192">Se la proprietà Finalità dell'applicazione è impostata su ReadWrite o se tale proprietà non è impostata, la connessione è consentita.</span><span class="sxs-lookup"><span data-stu-id="989f1-192">When the Application Intent property is set to ReadWrite or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="989f1-193">Per altre informazioni sulla proprietà di connessione Finalità dell'applicazione, vedere [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="989f1-193">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="989f1-194">Sono consentite tutte le connessioni ai database nella replica primaria.</span><span class="sxs-lookup"><span data-stu-id="989f1-194">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="989f1-195">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="989f1-195">This is the default setting.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="989f1-196">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="989f1-196">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="989f1-197">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="989f1-197">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="989f1-198">Per configurare e usare il provider di SQL Server PowerShell, vedere [provider di SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="989f1-198">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
<span data-ttu-id="989f1-199">Nell'esempio seguente vengono impostati i parametri `ConnectionModeInSecondaryRole` e `ConnectionModeInPrimaryRole` su `AllowAllConnections`.</span><span class="sxs-lookup"><span data-stu-id="989f1-199">The following example, sets the both the `ConnectionModeInSecondaryRole` and `ConnectionModeInPrimaryRole` parameters to `AllowAllConnections`.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  

Set-SqlAvailabilityReplica -ConnectionModeInSecondaryRole "AllowAllConnections" `
 -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ConnectionModeInPrimaryRole "AllowAllConnections" `
-InputObject $primaryReplica
```  

##  <a name="follow-up-after-configuring-read-only-access-for-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="989f1-200">Completamento: Dopo la configurazione dell'accesso in sola lettura per una replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="989f1-200">Follow Up: After Configuring Read-Only Access for an Availability Replica</span></span>  
 <span data-ttu-id="989f1-201">**Accesso in sola lettura a una replica secondaria leggibile.**</span><span class="sxs-lookup"><span data-stu-id="989f1-201">**Read-only access to a readable secondary replica**</span></span>  
  
-   <span data-ttu-id="989f1-202">Quando si usa l'utilità [bcp](../../../tools/bcp-utility.md) o l' [utilità sqlcmd](../../../tools/sqlcmd-utility.md), è possibile specificare l'accesso in sola lettura a qualsiasi replica secondaria abilitata per l'accesso in sola lettura specificando l' `-K ReadOnly` opzione.</span><span class="sxs-lookup"><span data-stu-id="989f1-202">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
-   <span data-ttu-id="989f1-203">Per consentire alle applicazioni client di connettersi a repliche secondarie leggibili:</span><span class="sxs-lookup"><span data-stu-id="989f1-203">To enable client applications to connect to readable secondary replicas:</span></span>  
  
    ||<span data-ttu-id="989f1-204">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="989f1-204">Prerequisite</span></span>|<span data-ttu-id="989f1-205">Collegamento</span><span class="sxs-lookup"><span data-stu-id="989f1-205">Link</span></span>|  
    |-|------------------|----------|  
    |<span data-ttu-id="989f1-206">![Casella di controllo](../../media/checkboxemptycenterxtraspacetopandright.gif "Casella di controllo")</span><span class="sxs-lookup"><span data-stu-id="989f1-206">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="989f1-207">Assicurarsi che nel gruppo di disponibilità sia presente un listener.</span><span class="sxs-lookup"><span data-stu-id="989f1-207">Ensure that the availability group has a listener.</span></span>|[<span data-ttu-id="989f1-208">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="989f1-208">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)|  
    |<span data-ttu-id="989f1-209">![Casella di controllo](../../media/checkboxemptycenterxtraspacetopandright.gif "Casella di controllo")</span><span class="sxs-lookup"><span data-stu-id="989f1-209">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="989f1-210">Configurare il routing di sola lettura per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="989f1-210">Configure read-only routing for the availability group.</span></span>|[<span data-ttu-id="989f1-211">Configurare il routing di sola lettura per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="989f1-211">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)|  
  
 <span data-ttu-id="989f1-212">**Fattori che potrebbero influire su trigger e processi dopo un failover**</span><span class="sxs-lookup"><span data-stu-id="989f1-212">**Factors that might affect triggers and jobs after a failover**</span></span>  
  
 <span data-ttu-id="989f1-213">Se sono presenti trigger e processi che avranno esito negativo se vengono eseguiti su una replica secondaria non leggibile o su un database secondario leggibile, è necessario generare script per trigger e processi per effettuare una verifica su una replicato specifica per determinare se il database è un database primario o un database secondario leggibile.</span><span class="sxs-lookup"><span data-stu-id="989f1-213">If you have triggers and jobs that will fail when running on a non-readable secondary database or on a readable secondary database, you need to script the triggers and jobs to check on a given replica to determine whether the database is a primary database or is a readable secondary database.</span></span> <span data-ttu-id="989f1-214">Per ottenere queste informazioni, usare la funzione [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) per restituire la proprietà **Updatability** del database.</span><span class="sxs-lookup"><span data-stu-id="989f1-214">To obtain this information, use the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **Updatability** property of the database.</span></span> <span data-ttu-id="989f1-215">Per identificare un database di sola lettura, specificare il valore READ_ONLY come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="989f1-215">To identify a read-only database, specify READ_ONLY as the value, as follows:</span></span>  
  
```  
DATABASEPROPERTYEX([db name],'Updatability') = N'READ_ONLY'  
```  
  
 <span data-ttu-id="989f1-216">Per identificare un database di lettura/scrittura, specificare il valore READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="989f1-216">To identify a read-write database, specify READ_WRITE as the value.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="989f1-217">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="989f1-217">Related Tasks</span></span>  
  
-   [<span data-ttu-id="989f1-218">Configurare il routing di sola lettura per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="989f1-218">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="989f1-219">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="989f1-219">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="989f1-220">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="989f1-220">Related Content</span></span>  
  
-   [<span data-ttu-id="989f1-221">Always On: proposta di valore di Secondario leggibile</span><span class="sxs-lookup"><span data-stu-id="989f1-221">Always On: Value Proposition of Readable Secondary</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-value-proposition-of-readable-secondary)  
  
-   [<span data-ttu-id="989f1-222">Always On: motivi per cui sono presenti due opzioni per abilitare una replica secondaria per un carico di lavoro di lettura</span><span class="sxs-lookup"><span data-stu-id="989f1-222">Always On: Why there are two options to enable a secondary replica for read workload?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-why-there-are-two-options-to-enable-a-secondary-replica-for-read-workload)  
  
-   [<span data-ttu-id="989f1-223">Always On: configurazione di una replica secondaria leggibile</span><span class="sxs-lookup"><span data-stu-id="989f1-223">Always On: Setting up Readable Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-setting-up-readable-seconary-replica)  
  
-   [<span data-ttu-id="989f1-224">Always On: motivo per cui anche se Secondario leggibile è appena stato abilitato la query rimane bloccata</span><span class="sxs-lookup"><span data-stu-id="989f1-224">Always On: I just enabled Readable Secondary but my query is blocked?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-i-just-enabled-readable-secondary-but-my-query-is-blocked)  
  
-   [<span data-ttu-id="989f1-225">Always On: come rendere disponibili le statistiche più recenti in Secondario leggibile, nel database di sola lettura e nello snapshot del database</span><span class="sxs-lookup"><span data-stu-id="989f1-225">Always On: Making latest statistics available on Readable Secondary, Read-Only database and Database Snapshot</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-making-latest-statistics-available-on-readable-secondary-read-only-database-and-database-snapshot)  
  
-   [<span data-ttu-id="989f1-226">Always On: problematiche riguardanti le statistiche sul database di sola lettura, sullo snapshot del database e sulla replica secondaria</span><span class="sxs-lookup"><span data-stu-id="989f1-226">Always On: Challenges with statistics on ReadOnly database, Database Snapshot and Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-challenges-with-statistics-on-readonly-database-database-snapshot-and-secondary-replica)  
  
-   [<span data-ttu-id="989f1-227">Always On: impatto sul carico di lavoro primario quando viene eseguito il carico di lavoro di report nella replica secondaria</span><span class="sxs-lookup"><span data-stu-id="989f1-227">Always On: Impact on the primary workload when you run reporting workload on the secondary replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-on-the-primary-workload-when-you-run-reporting-workload-on-the-secondary-replica)  
  
-   [<span data-ttu-id="989f1-228">Always On: impatto del mapping del carico di lavoro di report in Secondario leggibile all'isolamento dello snapshot</span><span class="sxs-lookup"><span data-stu-id="989f1-228">Always On: Impact of mapping reporting workload on Readable Secondary to Snapshot Isolation</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-of-mapping-reporting-workload-on-readable-secondary-to-snapshot-isolation)  
  
-   [<span data-ttu-id="989f1-229">Always On: riduzione al minimo del blocco del thread REDO quando si esegue il carico di lavoro di report nella replica secondaria</span><span class="sxs-lookup"><span data-stu-id="989f1-229">Always On: Minimizing blocking of REDO thread when running reporting workload on Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-minimizing-blocking-of-redo-thread-when-running-reporting-workload-on-secondary-replica)  
  
-   [<span data-ttu-id="989f1-230">Always On: Secondario leggibile e latenza dei dati</span><span class="sxs-lookup"><span data-stu-id="989f1-230">Always On: Readable Secondary and data latency</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-readable-secondary-and-data-latency)  
  
## <a name="see-also"></a><span data-ttu-id="989f1-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="989f1-231">See Also</span></span>  
 <span data-ttu-id="989f1-232">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="989f1-232">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="989f1-233">Repliche secondarie attive: repliche secondarie leggibili &#40;Gruppi di disponibilità AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="989f1-233">Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)  
 [<span data-ttu-id="989f1-234">Informazioni sull'accesso alla connessione client per le repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="989f1-234">About Client Connection Access to Availability Replicas &#40;SQL Server&#41;</span></span>](about-client-connection-access-to-availability-replicas-sql-server.md)  
