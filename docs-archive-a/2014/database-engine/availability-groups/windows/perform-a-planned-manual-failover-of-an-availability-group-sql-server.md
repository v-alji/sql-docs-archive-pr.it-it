---
title: Eseguire un failover manuale pianificato di un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.manualfailover.f1
helpviewer_keywords:
- Availability Groups [SQL Server], failover
- failover [SQL Server], AlwaysOn Availability Groups
ms.assetid: 419f655d-3f9a-4e7d-90b9-f0bab47b3178
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c62942eaa8f4ab4472bca5c7123e5999eb069216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718744"
---
# <a name="perform-a-planned-manual-failover-of-an-availability-group-sql-server"></a><span data-ttu-id="956d4-102">Eseguire un failover manuale pianificato di un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="956d4-102">Perform a Planned Manual Failover of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="956d4-103">In questo argomento viene illustrato come eseguire un failover manuale senza perdite di dati (*failover manuale pianificato*) in un gruppo di disponibilità AlwaysOn tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="956d4-103">This topic describes how to perform a manual failover without data loss (a *planned manual failover*) on an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="956d4-104">Per un gruppo di disponibilità il failover si verifica al livello di una replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="956d4-104">An availability group fails over at the level of an availability replica.</span></span> <span data-ttu-id="956d4-105">Con un failover manuale pianificato, come con qualsiasi failover [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , la replica secondaria passa al ruolo primario e, contemporaneamente, la replica primaria precedente passa al ruolo secondario.</span><span class="sxs-lookup"><span data-stu-id="956d4-105">A planned manual failover, like any [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] failover, transitions a secondary replica to primary role and, concurrently, transitions the former primary replica to the secondary role.</span></span>  
  
 <span data-ttu-id="956d4-106">Un failover manuale pianificato, supportato solo quando la replica primaria e la replica secondaria di destinazione sono in esecuzione in modalità con commit sincrono e sono attualmente sincronizzate, mantiene tutti i dati nei database secondari uniti in join al gruppo di disponibilità nella replica secondaria di destinazione.</span><span class="sxs-lookup"><span data-stu-id="956d4-106">A planned manual failover, which is supported only when the primary replica and the target secondary replica are running in synchronous-commit mode and are currently synchronized, preserves all the data in the secondary databases that are joined to the availability group on the target secondary replica.</span></span> <span data-ttu-id="956d4-107">Quando la replica primaria precedente passa al ruolo secondario, i relativi database diventeranno database secondari e viene iniziata la sincronizzazione con i nuovi database primari.</span><span class="sxs-lookup"><span data-stu-id="956d4-107">Once the former primary replica transitions to the secondary role, its databases become secondary databases and begin synchronizing with the new primary databases.</span></span> <span data-ttu-id="956d4-108">Dopo la transizione di tutti i database allo stato SYNCHRONIZED, la nuova replica secondaria diventa idonea a fungere da destinazione di un futuro failover manuale pianificato.</span><span class="sxs-lookup"><span data-stu-id="956d4-108">After they all transition into the SYNCHRONIZED state, the new secondary replica becomes eligible to serve as the target of a future planned manual failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="956d4-109">Se la replica primaria e le repliche secondarie sono configurate per la modalità di failover automatico, dopo la sincronizzazione, la replica secondaria può anche fungere da destinazione per un failover automatico.</span><span class="sxs-lookup"><span data-stu-id="956d4-109">If the secondary and primary replicas are both configured for automatic failover mode, once the secondary replica is synchronized, it can also serve as the target for an automatic failover.</span></span> <span data-ttu-id="956d4-110">Per altre informazioni, vedere [Modalità di disponibilità &#40;gruppi di disponibilità AlwaysOn&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="956d4-110">For more information, see [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="956d4-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="956d4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="956d4-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="956d4-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="956d4-113">Un comando del failover viene restituito non appena la replica secondaria di destinazione ha accettato il comando.</span><span class="sxs-lookup"><span data-stu-id="956d4-113">A failover command returns as soon as the target secondary replica has accepted the command.</span></span> <span data-ttu-id="956d4-114">Tuttavia, il recupero del database si verifica in modo asincrono dopo che il gruppo di disponibilità ha completato il failover.</span><span class="sxs-lookup"><span data-stu-id="956d4-114">However, database recovery occurs asynchronously after the availability group has finished failing over.</span></span>  
  
-   <span data-ttu-id="956d4-115">La coerenza tra i database all'interno del gruppo di disponibilità non viene mantenuta nel failover.</span><span class="sxs-lookup"><span data-stu-id="956d4-115">Cross-database consistency across databases within the availability group is not maintained on failover.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="956d4-116">Le transazioni tra database e quelle distribuite non sono supportate in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="956d4-116">Cross-database transactions and distributed transactions are not supported by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="956d4-117">Per altre informazioni, vedere [Transazioni tra database non supportate per il mirroring del database o i gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="956d4-117">For more information, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="956d4-118">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="956d4-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="956d4-119">La replica secondaria di destinazione e la replica primaria devono essere entrambe in esecuzione in modalità di disponibilità con commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="956d4-119">The target secondary replica and the primary replica must both be running in synchronous-commit availability mode.</span></span>  
  
-   <span data-ttu-id="956d4-120">La replica secondaria di destinazione deve essere attualmente sincronizzata con la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="956d4-120">The target secondary replica must currently be synchronized with the primary replica.</span></span> <span data-ttu-id="956d4-121">È necessario che tutti i database secondari su tale replica secondaria siano uniti in join al gruppo di disponibilità e sincronizzati con i database primari corrispondenti (ossia lo stato dei database secondari locali deve essere SYNCHRONIZED).</span><span class="sxs-lookup"><span data-stu-id="956d4-121">This requires that all the secondary databases on this secondary replica must have been joined to the availability group and be synchronized with their corresponding primary databases (that is, the local secondary databases must be SYNCHRONIZED).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="956d4-122">Per determinare la conformità del failover di una replica secondaria, eseguire una query della colonna **is_failover_ready** nella DMV [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) o esaminare la colonna **Conformità failover** del [dashboard del gruppo AlwaysOn](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="956d4-122">To determine the failover readiness of an secondary replica, query the **is_failover_ready** column in the [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) dynamic management view, or look at the **Failover Readiness** column of the [AlwaysOn Group Dashboard](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
-   <span data-ttu-id="956d4-123">Questa attività è supportata solo nella replica secondaria di destinazione.</span><span class="sxs-lookup"><span data-stu-id="956d4-123">This task is supported only on the target secondary replica.</span></span> <span data-ttu-id="956d4-124">È necessario essere connessi all'istanza del server che ospita la replica secondaria di destinazione.</span><span class="sxs-lookup"><span data-stu-id="956d4-124">You must be connected to the server instance that hosts the target secondary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="956d4-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="956d4-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="956d4-126">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="956d4-126">Permissions</span></span>  
 <span data-ttu-id="956d4-127">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="956d4-127">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="956d4-128">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="956d4-128">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="956d4-129">**Per eseguire manualmente il failover di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="956d4-129">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="956d4-130">In Esplora oggetti connettersi a un'istanza del server che ospita una replica secondaria del gruppo di disponibilità di cui eseguire il failover ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="956d4-130">In Object Explorer, connect to a server instance that hosts a secondary replica of the availability group that needs to be failed over, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="956d4-131">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="956d4-131">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="956d4-132">Fare clic con il pulsante destro del mouse sul gruppo di disponibilità di cui eseguire il failover e selezionare il comando **Failover** .</span><span class="sxs-lookup"><span data-stu-id="956d4-132">Right-click the availability group to be failed over, and select the **Failover** command.</span></span>  
  
4.  <span data-ttu-id="956d4-133">Verrà avviata la Creazione guidata Gruppo di disponibilità di failover.</span><span class="sxs-lookup"><span data-stu-id="956d4-133">This launches the Failover Availability Group Wizard.</span></span> <span data-ttu-id="956d4-134">Per altre informazioni, vedere [Usare la procedura guidata Failover gruppo di disponibilità &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="956d4-134">For more information, see [Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="956d4-135">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="956d4-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="956d4-136">**Per eseguire manualmente il failover di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="956d4-136">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="956d4-137">Connettersi all'istanza del server che ospita la replica secondaria di destinazione.</span><span class="sxs-lookup"><span data-stu-id="956d4-137">Connect to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="956d4-138">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="956d4-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="956d4-139">ALTER AVAILABILITY GROUP *nome_gruppo* FAILOVER</span><span class="sxs-lookup"><span data-stu-id="956d4-139">ALTER AVAILABILITY GROUP *group_name* FAILOVER</span></span>  
  
     <span data-ttu-id="956d4-140">dove *nome_gruppo* è il nome del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="956d4-140">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="956d4-141">Nell'esempio seguente viene eseguito il failover manuale del gruppo di disponibilità *MyAg* alla replica secondaria connessa.</span><span class="sxs-lookup"><span data-stu-id="956d4-141">The following example manually fails over the *MyAg* availability group to the connected secondary replica.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAg FAILOVER;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="956d4-142">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="956d4-142">Using PowerShell</span></span>  
 <span data-ttu-id="956d4-143">**Per eseguire manualmente il failover di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="956d4-143">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="956d4-144">Spostarsi sulla directory (`cd`) dell'istanza del server che ospita la replica secondaria di destinazione.</span><span class="sxs-lookup"><span data-stu-id="956d4-144">Change directory (`cd`) to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="956d4-145">Utilizzare il cmdlet `Switch-SqlAvailabilityGroup`.</span><span class="sxs-lookup"><span data-stu-id="956d4-145">Use the `Switch-SqlAvailabilityGroup` cmdlet.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="956d4-146">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="956d4-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="956d4-147">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="956d4-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
     <span data-ttu-id="956d4-148">Nell'esempio seguente viene eseguito il failover manuale del gruppo di disponibilità *MyAg* alla replica secondaria con il percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="956d4-148">The following example manually fails over the *MyAg* availability group to the secondary replica with the specified path.</span></span>  
  
    ```powershell
    Switch-SqlAvailabilityGroup -Path SQLSERVER:\Sql\SecondaryServer\InstanceName\AvailabilityGroups\MyAg  
    ```  
  
 <span data-ttu-id="956d4-149">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="956d4-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="956d4-150">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="956d4-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="956d4-151">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="956d4-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="follow-up-after-manually-failing-over-an-availability-group"></a><a name="FollowUp"></a><span data-ttu-id="956d4-152">Completamento: dopo il failover manuale di un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="956d4-152">Follow Up: After Manually Failing Over an Availability Group</span></span>  
 <span data-ttu-id="956d4-153">Se è stato eseguito il failover al di fuori del [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] del gruppo di disponibilità, modificare i voti del quorum dei nodi WSFC per riflettere la nuova configurazione del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="956d4-153">If you failed over outside of the [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] of the availability group, adjust the quorum votes of the WSFC nodes to reflect your new availability group configuration.</span></span> <span data-ttu-id="956d4-154">Per ulteriori informazioni, vedere [Windows Server failover clustering &#40;&#41; WSFC con SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="956d4-154">For more information, see [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956d4-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="956d4-155">See Also</span></span>  
 <span data-ttu-id="956d4-156">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="956d4-156">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="956d4-157">[Failover e modalità di failover &#40;Gruppi di disponibilità AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="956d4-157">[Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="956d4-158">Eseguire un failover manuale forzato di un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="956d4-158">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
