---
title: Visualizzazione delle proprietà della replica di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- ', policies'
ms.assetid: 14fed3c4-8ecc-4e1c-931d-a7ec1e9f9e90
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ca7b0508907b4d86c9ee627438a3f18e1b01fdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716828"
---
# <a name="view-availability-replica-properties-sql-server"></a><span data-ttu-id="0946f-102">Visualizzazione delle proprietà della replica di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0946f-102">View Availability Replica Properties (SQL Server)</span></span>
  <span data-ttu-id="0946f-103">In questo argomento viene illustrato come visualizzare le proprietà di una replica di disponibilità per un gruppo di disponibilità AlwaysOn tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0946f-103">This topic describes how to view the properties of an availability replica for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0946f-104">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0946f-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="0946f-105">**Per visualizzare e modificare le proprietà di una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="0946f-105">**To view and change properties an availability replica**</span></span>  
  
1.  <span data-ttu-id="0946f-106">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="0946f-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="0946f-107">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="0946f-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="0946f-108">Espandere il gruppo di disponibilità al quale appartiene la replica di disponibilità ed espandere il nodo **Repliche di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="0946f-108">Expand the availability group to which the availability replica belongs, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="0946f-109">Fare clic con il pulsante destro del mouse sulla replica di disponibilità di cui si vuole visualizzare le proprietà e selezionare il comando **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="0946f-109">Right-click the availability replica whose properties you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="0946f-110">Nella finestra di dialogo **Proprietà replica di disponibilità** usare la pagina **Generale** per visualizzare le proprietà della replica.</span><span class="sxs-lookup"><span data-stu-id="0946f-110">In the **Availability Replica Properties** dialog box, use the **General** page to view the properties of this replica.</span></span> <span data-ttu-id="0946f-111">Se si è connessi alla replica primaria, è possibile modificare le proprietà seguenti: modalità di disponibilità, modalità di failover, accesso alla connessione per il ruolo primario, accesso in lettura per il ruolo secondario (secondario leggibile) e valore del timeout di sessione.</span><span class="sxs-lookup"><span data-stu-id="0946f-111">If you are connected to the primary replica, you can change the following properties: availability mode, failover mode, connection access for the primary role, read-access for the secondary role (readable-secondary), and the session-timeout value.</span></span> <span data-ttu-id="0946f-112">Per altre informazioni, vedere [proprietà della replica di disponibilità &#40;&#41;della pagina generale ](availability-replica-properties-general-page.md).</span><span class="sxs-lookup"><span data-stu-id="0946f-112">For more information, see  [Availability Replica Properties &#40;General Page&#41;](availability-replica-properties-general-page.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0946f-113">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0946f-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="0946f-114">**Per visualizzare le proprietà e gli stati delle repliche di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="0946f-114">**To view properties and states of availability replicas**</span></span>  
  
 <span data-ttu-id="0946f-115">Per visualizzare le proprietà e gli stati delle repliche di disponibilità, utilizzare la funzione di sistema e le viste seguenti:</span><span class="sxs-lookup"><span data-stu-id="0946f-115">To view the properties and states of availability replicas, use the following views and system function:</span></span>  
  
 [<span data-ttu-id="0946f-116">sys.availability_replicas</span><span class="sxs-lookup"><span data-stu-id="0946f-116">sys.availability_replicas</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql)  
 <span data-ttu-id="0946f-117">Restituisce una riga per ogni replica di disponibilità in ogni gruppo di disponibilità per il quale l'istanza locale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ospita una replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0946f-117">Returns a row for every availability replica in each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span>  
  
 <span data-ttu-id="0946f-118">**Nomi colonne:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span><span class="sxs-lookup"><span data-stu-id="0946f-118">**Column names:** replica_id, group_id, replica_metadata_id, replica_server_name, owner_sid, endpoint_url, availability_mode, availability_mode_desc, failover_mode, failover_mode_desc, session_timeout, primary_role_allow_connections, primary_role_allow_connections_desc, secondary_role_allow_connections, secondary_role_allow_connections_desc, create_date, modify_date, backup_priority, read_only_routing_url</span></span>  
  
 [<span data-ttu-id="0946f-119">sys.availability_read_only_routing_lists</span><span class="sxs-lookup"><span data-stu-id="0946f-119">sys.availability_read_only_routing_lists</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-read-only-routing-lists-transact-sql)  
 <span data-ttu-id="0946f-120">Viene restituita una riga per l'elenco di routing di sola lettura di ogni replica di disponibilità in un gruppo di disponibilità AlwaysOn nel cluster di failover WSFC.</span><span class="sxs-lookup"><span data-stu-id="0946f-120">Returns a row for the read only routing list of each availability replica in an AlwaysOn availability group in the WSFC failover cluster.</span></span>  
  
 <span data-ttu-id="0946f-121">**Nomi colonne:** replica_id, routing_priority, read_only_replica_id</span><span class="sxs-lookup"><span data-stu-id="0946f-121">**Column names:** replica_id, routing_priority, read_only_replica_id</span></span>  
  
 [<span data-ttu-id="0946f-122">sys.dm_hadr_availability_replica_cluster_nodes</span><span class="sxs-lookup"><span data-stu-id="0946f-122">sys.dm_hadr_availability_replica_cluster_nodes</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-nodes-transact-sql)  
 <span data-ttu-id="0946f-123">Restituisce una riga per ogni replica di disponibilità, indipendentemente dallo stato di join, dei gruppi di disponibilità AlwaysOn nel cluster WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="0946f-123">Returns a row for every availability replica (regardless of join state) of the AlwaysOn availability groups in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="0946f-124">**Nomi colonne:** group_name, replica_server_name, node_name</span><span class="sxs-lookup"><span data-stu-id="0946f-124">**Column names:** group_name, replica_server_name, node_name</span></span>  
  
 [<span data-ttu-id="0946f-125">sys.dm_hadr_availability_replica_cluster_states</span><span class="sxs-lookup"><span data-stu-id="0946f-125">sys.dm_hadr_availability_replica_cluster_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-cluster-states-transact-sql)  
 <span data-ttu-id="0946f-126">Restituisce una riga per ogni replica, indipendentemente dallo stato del join, di tutti i gruppi di disponibilità AlwaysOn, indipendentemente dal percorso della replica, nel cluster WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="0946f-126">Returns a row for each replica (regardless of join state) of all AlwaysOn availability groups (regardless of replica location) in the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="0946f-127">**Nomi colonne:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span><span class="sxs-lookup"><span data-stu-id="0946f-127">**Column names:** replica_id, replica_server_name, group_id, join_state, join_state_desc</span></span>  
  
 [<span data-ttu-id="0946f-128">sys.dm_hadr_availability_replica_states</span><span class="sxs-lookup"><span data-stu-id="0946f-128">sys.dm_hadr_availability_replica_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-replica-states-transact-sql)  
 <span data-ttu-id="0946f-129">Restituisce una riga in cui viene mostrato lo stato di ogni replica di disponibilità locale e una riga per ogni replica di disponibilità remota nello stesso gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0946f-129">Returns a row showing the state of each local availability replica and a row for each remote availability replica in the same availability group.</span></span>  
  
 <span data-ttu-id="0946f-130">**Nomi colonne:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description e last_connect_error_timestamp</span><span class="sxs-lookup"><span data-stu-id="0946f-130">**Column names:** replica_id, group_id, is_local, role, role_desc, operational_state, operational_state_desc, connected_state, connected_state_desc, recovery_health, recovery_health_desc, synchronization_health, synchronization_health_desc, last_connect_error_number, last_connect_error_description, and last_connect_error_timestamp</span></span>  
  
 [<span data-ttu-id="0946f-131">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="0946f-131">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
 <span data-ttu-id="0946f-132">Determina se la replica corrente è la replica di backup preferita.</span><span class="sxs-lookup"><span data-stu-id="0946f-132">Determines whether the current replica is the preferred backup replica.</span></span> <span data-ttu-id="0946f-133">Restituisce 1 se il database nell'istanza server corrente è la replica preferita.</span><span class="sxs-lookup"><span data-stu-id="0946f-133">Returns 1 if the database on the current server instance is the preferred replica.</span></span> <span data-ttu-id="0946f-134">In caso contrario, viene restituito 0.</span><span class="sxs-lookup"><span data-stu-id="0946f-134">Otherwise, it returns 0.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0946f-135">Per informazioni sui contatori delle prestazioni per le repliche di disponibilità (oggetto prestazioni **SQLServer:Availability Replica**  ), vedere [SQL Server, replica di disponibilità](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="0946f-135">For information about performance counters for availability replicas (the **SQLServer:Availability Replica**  performance object), see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0946f-136">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0946f-136">Related Tasks</span></span>  
 <span data-ttu-id="0946f-137">**Per visualizzare le informazioni sui gruppi di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="0946f-137">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="0946f-138">Visualizzazione delle Proprietà dei gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-138">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="0946f-139">Visualizzare le proprietà del listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-139">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="0946f-140">Criteri AlwaysOn per problemi operativi con Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-140">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="0946f-141">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0946f-142">Monitorare Gruppi di disponibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-142">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="0946f-143">**Per gestire le repliche di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="0946f-143">**To manage availability replicas**</span></span>  
  
-   [<span data-ttu-id="0946f-144">Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-144">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0946f-145">Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-145">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0946f-146">Configurare l'accesso in sola lettura in una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-146">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="0946f-147">Modificare la modalità di disponibilità di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-147">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="0946f-148">Modificare la modalità di failover di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-148">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="0946f-149">Modificare il periodo di timeout della sessione per una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-149">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="0946f-150">Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-150">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="0946f-151">**Per gestire un database di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="0946f-151">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="0946f-152">Aggiungere un database a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-152">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="0946f-153">Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-153">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0946f-154">Sospendere un database di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-154">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="0946f-155">Riprendere un database di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-155">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="0946f-156">Rimuovere un database secondario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-156">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="0946f-157">Rimuovere un database primario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-157">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="0946f-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0946f-158">See Also</span></span>  
 <span data-ttu-id="0946f-159">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0946f-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="0946f-160">[Monitorare i gruppi di disponibilità &#40;&#41;Transact-SQL](monitor-availability-groups-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="0946f-160">[Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) </span></span>  
 <span data-ttu-id="0946f-161">[Criteri AlwaysOn per problemi operativi con Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="0946f-161">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 [<span data-ttu-id="0946f-162">Amministrazione di un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0946f-162">Administration of an Availability Group &#40;SQL Server&#41;</span></span>](administration-of-an-availability-group-sql-server.md)  
  
  
