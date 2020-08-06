---
title: Creare un join di una replica secondaria a un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joinreplica.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
ms.assetid: e5bd2489-097a-490e-8ea1-34fe48378ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c38c2d59a46b15fc9a1dca77ae6a67e8e59e1b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627973"
---
# <a name="join-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="4ae2f-102">Creare un join di una replica secondaria a un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4ae2f-102">Join a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="4ae2f-103">In questo argomento si illustra come creare un join di una replica secondaria a un gruppo di disponibilità AlwaysOn utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ae2f-103">This topic describes how to join a secondary replica to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4ae2f-104">Dopo l'aggiunta di una replica secondaria a un gruppo di disponibilità AlwaysOn, è necessario creare un join della replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-104">After a secondary replica is added to an AlwaysOn availability group, the secondary replica must be joined to the availability group.</span></span> <span data-ttu-id="4ae2f-105">L'operazione di join della replica deve essere eseguita nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in cui viene ospitata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-105">The join-replica operation must be performed on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting the secondary replica.</span></span>  
  
-   <span data-ttu-id="4ae2f-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4ae2f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4ae2f-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4ae2f-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="4ae2f-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4ae2f-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4ae2f-109">**Per preparare un database secondario tramite:**</span><span class="sxs-lookup"><span data-stu-id="4ae2f-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="4ae2f-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4ae2f-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4ae2f-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4ae2f-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="4ae2f-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ae2f-112">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="4ae2f-113">**Completamento:** [Configurare i database secondari](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="4ae2f-113">**Follow Up:** [Configure Secondary Databases](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4ae2f-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4ae2f-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4ae2f-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4ae2f-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="4ae2f-116">La replica primaria del gruppo di disponibilità deve essere attualmente online.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-116">The primary replica of the availability group must currently be online.</span></span>  
  
-   <span data-ttu-id="4ae2f-117">È necessario essere connessi all'istanza del server che ospita una replica secondaria di cui non sia ancora stato creato un join al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-117">You must be connected to the server instance that hosts a secondary replica that has not yet have been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="4ae2f-118">L'istanza del server locale deve essere in grado di connettersi all'endpoint del mirroring del database dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-118">The local server instance must be able to connect to the database mirroring endpoint of the server instance that is hosting the primary replica.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4ae2f-119">Se nessuno dei prerequisiti viene soddisfatto, l'operazione di join non viene completata.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-119">If any prerequisite is not met, the join operation fails.</span></span> <span data-ttu-id="4ae2f-120">Al termine di un tentativo di join errato, potrebbe essere necessario connettersi all'istanza del server in cui è ospitata la replica primaria per rimuovere e aggiungere nuovamente la replica secondaria, prima di poter creare un join al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-120">After a failed join attempt, you might need to connect to the server instance that hosts the primary replica to remove and re-add the secondary replica before you can join it to the availability group.</span></span> <span data-ttu-id="4ae2f-121">Per altre informazioni, vedere [Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) e [Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4ae2f-121">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) and [Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4ae2f-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4ae2f-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4ae2f-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4ae2f-123">Permissions</span></span>  
 <span data-ttu-id="4ae2f-124">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4ae2f-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4ae2f-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4ae2f-126">**Per creare un join di una replica di disponibilità a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="4ae2f-126">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="4ae2f-127">In Esplora oggetti connettersi all'istanza del server in cui viene ospitata la replica secondaria e fare clic sul nome del server per espandere il relativo albero.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-127">In Object Explorer, connect to the server instance that hosts the secondary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="4ae2f-128">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="4ae2f-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="4ae2f-129">Selezionare il gruppo di disponibilità della replica secondaria a cui si è connessi.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-129">Select the availability group of the secondary replica to which you are connected.</span></span>  
  
4.  <span data-ttu-id="4ae2f-130">Fare clic con il pulsante destro del mouse sulla replica secondaria e scegliere **Crea un join del gruppo di disponibilità**.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-130">Right-click the secondary replica, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="4ae2f-131">In questo modo verrà aperta la finestra di dialogo **Creare un join della replica al gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="4ae2f-131">This opens the **Join Replica to Availability Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="4ae2f-132">Per creare un join della replica secondaria al gruppo di disponibilità, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-132">To join the secondary replica to the availability group, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4ae2f-133">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4ae2f-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="4ae2f-134">**Per creare un join di una replica di disponibilità a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="4ae2f-134">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="4ae2f-135">Connettersi all'istanza del server che ospita la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-135">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="4ae2f-136">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4ae2f-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="4ae2f-137">ALTER AVAILABILITY GROUP *nome_gruppo* JOIN</span><span class="sxs-lookup"><span data-stu-id="4ae2f-137">ALTER AVAILABILITY GROUP *group_name* JOIN</span></span>  
  
     <span data-ttu-id="4ae2f-138">dove *nome_gruppo* è il nome del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-138">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="4ae2f-139">Nell'esempio seguente viene creato un join della replica secondaria al gruppo di disponibilità `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-139">The following example, joins the secondary replica to the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ae2f-140">Per un esempio di questa istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] impiegata in un contesto, vedere [Creare un gruppo di disponibilità &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4ae2f-140">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4ae2f-141">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ae2f-141">Using PowerShell</span></span>  
 <span data-ttu-id="4ae2f-142">**Per creare un join di una replica di disponibilità a un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="4ae2f-142">**To join an availability replica to an availability group**</span></span>  
  
 <span data-ttu-id="4ae2f-143">Nel provider PowerShell per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4ae2f-143">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="4ae2f-144">Impostare la directory (`cd`) sull'istanza del server in cui viene ospitata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-144">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="4ae2f-145">Creare un join della replica secondaria al gruppo di disponibilità eseguendo il cmdlet **Join-SqlAvailabilityGroup** con il nome del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-145">Join the secondary replica to the availability group by executing the **Join-SqlAvailabilityGroup** cmdlet with the name of the availability group.</span></span>  
  
     <span data-ttu-id="4ae2f-146">Ad esempio, tramite il comando seguente è possibile creare un join di una replica secondaria ospitata dall'istanza del server presente nel percorso specificato al gruppo di disponibilità denominato `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-146">For example, the following command joins a secondary replica hosted by the server instance located at the specified path to the availability group named `MyAg`.</span></span>  <span data-ttu-id="4ae2f-147">Questa istanza del server deve ospitare una replica secondaria in questo gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-147">This server instance must host a secondary replica in this availability group.</span></span>  
  
    ```powershell
    Join-SqlAvailabilityGroup -Path SQLSERVER:\SQL\SecondaryServer\InstanceName -Name 'MyAg'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ae2f-148">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="4ae2f-149">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4ae2f-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="4ae2f-150">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4ae2f-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="4ae2f-151">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ae2f-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-configure-secondary-databases"></a><a name="FollowUp"></a><span data-ttu-id="4ae2f-152">Completamento: configurare i database secondari</span><span class="sxs-lookup"><span data-stu-id="4ae2f-152">Follow Up: Configure Secondary Databases</span></span>  
 <span data-ttu-id="4ae2f-153">Per ogni database nel gruppo di disponibilità, è necessario un database secondario nell'istanza del server in cui viene ospitata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-153">For every database in the availability group, you need a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="4ae2f-154">È possibile configurare i database secondari prima o dopo la creazione di un join di una replica secondaria a un gruppo di disponibilità, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4ae2f-154">You can configure secondary databases either before or after you join a secondary replica to an availability group, as follows:</span></span>  
  
1.  <span data-ttu-id="4ae2f-155">Ripristinare i backup dei log e dei database recenti di ogni database primario nell'istanza del server in cui viene ospitata la replica secondaria, utilizzando RESTORE WITH NORECOVERY per ogni operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-155">Restore recent database and log backups of each primary database onto the server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="4ae2f-156">Per altre informazioni, vedere [Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4ae2f-156">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="4ae2f-157">Creare un join di ogni database secondario al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4ae2f-157">Join each secondary database to the availability group.</span></span> <span data-ttu-id="4ae2f-158">Per altre informazioni, vedere [Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4ae2f-158">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae2f-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ae2f-159">See Also</span></span>  
 <span data-ttu-id="4ae2f-160">[Creazione e configurazione di gruppi di disponibilità &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ae2f-160">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="4ae2f-161">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4ae2f-161">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="4ae2f-162">Risolvere i problemi di Gruppi di disponibilità AlwaysOn &#40;di configurazione SQL Server eliminati&#41;</span><span class="sxs-lookup"><span data-stu-id="4ae2f-162">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
