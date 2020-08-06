---
title: Visualizzazione delle Proprietà dei gruppi di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server]
ms.assetid: 61243c87-bd62-4510-863f-2a8f347caf1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b7d1f57a9bd29b6c65160ec9a163bc77dfca48b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626887"
---
# <a name="view-availability-group-properties-sql-server"></a><span data-ttu-id="5d4c0-102">Visualizzazione delle Proprietà dei gruppi di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5d4c0-102">View Availability Group Properties (SQL Server)</span></span>
  <span data-ttu-id="5d4c0-103">In questo argomento viene illustrato come visualizzare le proprietà di un gruppo di disponibilità per un gruppo di disponibilità AlwaysOn tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d4c0-103">This topic describes how to view the properties of an availability group for an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  

  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5d4c0-104">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d4c0-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5d4c0-105">**Per visualizzare e modificare le proprietà di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="5d4c0-105">**To view and change the properties an availability group**</span></span>  
  
1.  <span data-ttu-id="5d4c0-106">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="5d4c0-106">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="5d4c0-107">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="5d4c0-107">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="5d4c0-108">Fare clic con il pulsante destro del mouse sul gruppo di disponibilità di cui visualizzare le proprietà e scegliere il comando **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="5d4c0-108">Right-click the availability group whose properties you want to view, and select the **Properties** command.</span></span>  
  
4.  <span data-ttu-id="5d4c0-109">Nella finestra di dialogo **Proprietà gruppo di disponibilità** , utilizzare le pagine **Generale** e **Preferenze di backup** per visualizzare e, talvolta, modificare le proprietà del gruppo di disponibilità selezionato.</span><span class="sxs-lookup"><span data-stu-id="5d4c0-109">In the **Availability Group Properties** dialog box, use the **General** and **Backup Preferences** pages to view and, in some cases, change properties of the selected availability group.</span></span> <span data-ttu-id="5d4c0-110">Per altre informazioni, vedere [Proprietà dei gruppi di disponibilità/Nuovo gruppo di disponibilità &#40;pagina Generale&#41;](availability-group-properties-new-availability-group-general-page.md) e [Proprietà dei gruppi di disponibilità/Nuovo gruppo di disponibilità &#40;pagina Preferenze di backup&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span><span class="sxs-lookup"><span data-stu-id="5d4c0-110">For more information, see [Availability Group Properties and New Availability Group &#40;General Page&#41;](availability-group-properties-new-availability-group-general-page.md) and [Availability Group Properties: New Availability Group &#40;Backup Preferences Page&#41;](availability-group-properties-new-availability-group-backup-preferences-page.md).</span></span>  
  
     <span data-ttu-id="5d4c0-111">Utilizzare la pagina **Autorizzazioni** per visualizzare gli account di accesso, i ruoli e le autorizzazioni esplicite correnti associati al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="5d4c0-111">Use the **Permissions** page to view the current logins, roles, and explicit permissions associated with the availability group.</span></span> <span data-ttu-id="5d4c0-112">Per ulteriori informazioni, vedere [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span><span class="sxs-lookup"><span data-stu-id="5d4c0-112">For more information, see [Permissions or Securables Page](../../../relational-databases/security/permissions-or-securables-page.md).</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5d4c0-113">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d4c0-113">Using Transact-SQL</span></span>  
 <span data-ttu-id="5d4c0-114">**Per visualizzare le proprietà e lo stato di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="5d4c0-114">**To view the properties and state of an availability group**</span></span>  
  
 <span data-ttu-id="5d4c0-115">Per eseguire una query sulle proprietà e sugli stati dei gruppi di disponibilità per cui l'istanza del server ospita una replica di disponibilità, utilizzare le viste seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d4c0-115">To query the properties and states of the availability groups for which the server instance hosts an availability replica, use the following views:</span></span>  
  
 [<span data-ttu-id="5d4c0-116">sys.availability_groups</span><span class="sxs-lookup"><span data-stu-id="5d4c0-116">sys.availability_groups</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-transact-sql)  
 <span data-ttu-id="5d4c0-117">Restituisce una riga per ogni gruppo di disponibilità per il quale l'istanza locale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ospita una replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="5d4c0-117">Returns a row for each availability group for which the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hosts an availability replica.</span></span> <span data-ttu-id="5d4c0-118">Ogni riga contiene una copia memorizzata nella cache dei metadati del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="5d4c0-118">Each row contains a cached copy of the availability group metadata.</span></span>  
  
 <span data-ttu-id="5d4c0-119">**Nomi delle colonne:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="5d4c0-119">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="5d4c0-120">sys.availability_groups_cluster</span><span class="sxs-lookup"><span data-stu-id="5d4c0-120">sys.availability_groups_cluster</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-groups-cluster-transact-sql)  
 <span data-ttu-id="5d4c0-121">Restituisce una riga per ogni gruppo di disponibilità nel cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="5d4c0-121">Returns a row for each availability group in the WSFC cluster.</span></span> <span data-ttu-id="5d4c0-122">Ogni riga contiene i metadati del gruppo di disponibilità del cluster WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="5d4c0-122">Each row contains the availability group metadata from the Windows Server Failover Clustering (WSFC) cluster.</span></span>  
  
 <span data-ttu-id="5d4c0-123">**Nomi delle colonne:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span><span class="sxs-lookup"><span data-stu-id="5d4c0-123">**Column names:** group_id, name, resource_id, resource_group_id, failure_condition_level, health_check_timeout, automated_backup_preference, automated_backup_preference_desc</span></span>  
  
 [<span data-ttu-id="5d4c0-124">sys.dm_hadr_availability_group_states</span><span class="sxs-lookup"><span data-stu-id="5d4c0-124">sys.dm_hadr_availability_group_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-availability-group-states-transact-sql)  
 <span data-ttu-id="5d4c0-125">Restituisce una riga per ogni gruppo di disponibilità che dispone di una replica di disponibilità sull'istanza locale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d4c0-125">Returns a row for each availability group that possesses an availability replica on the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5d4c0-126">Ogni riga visualizza gli stati che definiscono l'integrità di un determinato gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="5d4c0-126">Each row displays the states that define the health of a given availability group.</span></span>  
  
 <span data-ttu-id="5d4c0-127">**:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span><span class="sxs-lookup"><span data-stu-id="5d4c0-127">**Column names:** group_id, primary_replica, primary_recovery_health, primary_recovery_health_desc, secondary_recovery_health, secondary_recovery_health_desc, synchronization_health, synchronization_health_desc</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5d4c0-128">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="5d4c0-128">Related Tasks</span></span>  
 <span data-ttu-id="5d4c0-129">**Per visualizzare le informazioni sui gruppi di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="5d4c0-129">**To view information about availability groups**</span></span>  
  
-   [<span data-ttu-id="5d4c0-130">Visualizzazione delle proprietà della replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-130">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-131">Visualizzare le proprietà del listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-131">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-132">Criteri AlwaysOn per problemi operativi con Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-132">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](always-on-policies-for-operational-issues-always-on-availability.md)
  
-   [<span data-ttu-id="5d4c0-133">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-133">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="5d4c0-134">Monitorare Gruppi di disponibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-134">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
 <span data-ttu-id="5d4c0-135">**Per configurare un gruppo di disponibilità esistente**</span><span class="sxs-lookup"><span data-stu-id="5d4c0-135">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="5d4c0-136">Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-136">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-137">Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-137">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-138">Aggiungere un database a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-138">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="5d4c0-139">Rimuovere un database secondario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-139">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-140">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-140">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-141">Rimuovere un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-141">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-142">Rimuovere un database primario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-142">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-143">Rimuovere un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-143">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="5d4c0-144">**Per eseguire manualmente il failover di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="5d4c0-144">**To manually fail over an availability group**</span></span>  
  
-   [<span data-ttu-id="5d4c0-145">Eseguire un failover manuale pianificato di un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-145">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="5d4c0-146">Eseguire un failover manuale forzato di un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="5d4c0-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d4c0-147">See Also</span></span>  
 <span data-ttu-id="5d4c0-148">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [monitorare i gruppi di disponibilità &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [criteri AlwaysOn per problemi operativi con](always-on-policies-for-operational-issues-always-on-availability.md) gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d4c0-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md) [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md)</span></span> 
  
  
