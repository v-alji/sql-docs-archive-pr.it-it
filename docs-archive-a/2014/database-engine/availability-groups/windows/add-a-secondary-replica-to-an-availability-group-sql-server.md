---
title: Aggiungere una replica secondaria a un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 6669dcce-85f9-495f-aadf-7f62cff4a9da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 498103a781641c72e166c6b11663f5248ae5ccfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624966"
---
# <a name="add-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="214de-102">Aggiungere una replica secondaria a un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="214de-102">Add a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="214de-103">In questo argomento viene illustrato come aggiungere una replica secondaria a un gruppo di disponibilità AlwaysOn esistente utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="214de-103">This topic describes how to add a secondary replica to an existing AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="214de-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="214de-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="214de-105">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="214de-105">Prerequisites and Restrictions</span></span>](#PrerequisitesRestrictions)  
  
     [<span data-ttu-id="214de-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="214de-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="214de-107">**Per aggiungere una replica mediante:**</span><span class="sxs-lookup"><span data-stu-id="214de-107">**To add a replica, using:**</span></span>  
  
     [<span data-ttu-id="214de-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="214de-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="214de-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="214de-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="214de-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="214de-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="214de-111">**Completamento:**  [Dopo l'aggiunta di una replica secondaria](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="214de-111">**Follow Up:**  [After Adding a Secondary Replica](#FollowUp)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="214de-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="214de-112">Before You Begin</span></span>  
 <span data-ttu-id="214de-113">Prima di iniziare a creare il primo gruppo di disponibilità, è consigliabile leggere questa sezione.</span><span class="sxs-lookup"><span data-stu-id="214de-113">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
##  <a name="prerequisites-and-restrictions"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="214de-114">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="214de-114">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="214de-115">È necessario essere connessi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="214de-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
 <span data-ttu-id="214de-116">Per altre informazioni, vedere [Prerequisiti, restrizioni e consigli per i gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="214de-116">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="214de-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="214de-117">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="214de-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="214de-118">Permissions</span></span>  
 <span data-ttu-id="214de-119">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="214de-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="214de-120">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="214de-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="214de-121">**Per aggiungere una replica**</span><span class="sxs-lookup"><span data-stu-id="214de-121">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="214de-122">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="214de-122">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="214de-123">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="214de-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="214de-124">Fare clic con il pulsante destro del mouse sul gruppo di disponibilità e selezionare uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="214de-124">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="214de-125">Per avviare la procedura guidata Aggiungi replica a gruppo di disponibilità, selezionare il comando **Aggiungi replica** .</span><span class="sxs-lookup"><span data-stu-id="214de-125">Select the **Add Replica** command to launch the Add Replica to Availability Group Wizard.</span></span> <span data-ttu-id="214de-126">Per altre informazioni, vedere [Usare la procedura guidata Aggiungi replica a gruppo di disponibilità &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="214de-126">For more information, see [Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
    -   <span data-ttu-id="214de-127">In alternativa, selezionare il comando **Proprietà** per aprire la finestra di dialogo **Proprietà gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="214de-127">Alternatively, select the **Properties** command to open the **Availability Group Properties** dialog box.</span></span> <span data-ttu-id="214de-128">I passaggi per l'aggiunta di una replica in questa finestra di dialogo sono indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="214de-128">The steps for adding a replica in this dialog box are as follows:</span></span>  
  
        1.  <span data-ttu-id="214de-129">Nel riquadro **Repliche di disponibilità** della finestra di dialogo fare clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="214de-129">In the **Availability Replicas** pane of the dialog box, click the **Add** button.</span></span> <span data-ttu-id="214de-130">Verrà creata e selezionata una replica in cui il campo Istanza del server vuoto è selezionato.</span><span class="sxs-lookup"><span data-stu-id="214de-130">This creates and selects a replica entry in which the blank Server Instance field is selected.</span></span>  
  
        2.  <span data-ttu-id="214de-131">Immettere il nome di un'istanza del server che soddisfa i prerequisiti per ospitare una replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="214de-131">Enter the name of a server instance that meets the prerequisites for hosting an availability replica.</span></span>  
  
         <span data-ttu-id="214de-132">Per aggiungere repliche aggiuntive, ripetere i passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="214de-132">To add an additional replicas, repeat the preceding steps.</span></span> <span data-ttu-id="214de-133">Dopo avere specificato le repliche, fare clic su **OK** per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="214de-133">When you are done specifying replicas, click **OK** to complete the operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="214de-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="214de-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="214de-135">**Per aggiungere una replica**</span><span class="sxs-lookup"><span data-stu-id="214de-135">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="214de-136">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="214de-136">Connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="214de-137">Aggiungere la nuova replica secondaria al gruppo di disponibilità utilizzando la clausola ADD REPLICA ON dell'istruzione ALTER AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="214de-137">Add the new secondary replica to the availability group by using the ADD REPLICA ON clause of the ALTER AVAILABILITY GROUP statement.</span></span> <span data-ttu-id="214de-138">Le opzioni ENDPOINT_URL, AVAILABILITY_MODE e FAILOVER_MODE sono obbligatorie in una clausola ADD REPLICA ON.</span><span class="sxs-lookup"><span data-stu-id="214de-138">The ENDPOINT_URL, AVAILABILITY_MODE, and FAILOVER_MODE options are required in an ADD REPLICA ON clause.</span></span> <span data-ttu-id="214de-139">Le altre opzioni di replica, BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE e SESSION_TIMEOUT, sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="214de-139">The other replica options- BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE, and SESSION_TIMEOUT-are optional.</span></span> <span data-ttu-id="214de-140">Per altre informazioni, vedere [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="214de-140">For more information, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="214de-141">Ad esempio, nell'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] seguente viene creata una nuova replica per un gruppo di disponibilità denominato `MyAG` sull'istanza del server predefinita ospitata da `COMPUTER04`, il cui URL dell'endpoint è `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span><span class="sxs-lookup"><span data-stu-id="214de-141">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement creates a new replica to an availability group named `MyAG` on the default server instance hosted by `COMPUTER04`, whose endpoint URL is `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span></span> <span data-ttu-id="214de-142">Questa replica supporta il failover manuale e la modalità di disponibilità con commit asincrono.</span><span class="sxs-lookup"><span data-stu-id="214de-142">This replica supports manual failover and asynchronous-commit availability mode.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG ADD REPLICA ON 'COMPUTER04'   
       WITH (  
             ENDPOINT_URL = 'TCP://COMPUTER04.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="214de-143">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="214de-143">Using PowerShell</span></span>  
 <span data-ttu-id="214de-144">**Per aggiungere una replica**</span><span class="sxs-lookup"><span data-stu-id="214de-144">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="214de-145">Spostarsi nella directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="214de-145">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="214de-146">Usare il cmdlet **New-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="214de-146">Use the **New-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="214de-147">Ad esempio, il seguente comando aggiunge una replica di disponibilità per un gruppo di disponibilità esistente denominato `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="214de-147">For example, the following command adds an availability replica to an existing availability group named `MyAg`.</span></span> <span data-ttu-id="214de-148">Questa replica supporta il failover manuale e la modalità di disponibilità con commit asincrono.</span><span class="sxs-lookup"><span data-stu-id="214de-148">This replica supports manual failover and asynchronous-commit availability mode.</span></span> <span data-ttu-id="214de-149">Nel ruolo secondario, questa replica supporterà le connessioni con accesso in lettura consentendo all'utente di ripartire il carico dell'elaborazione di sola lettura in questa replica.</span><span class="sxs-lookup"><span data-stu-id="214de-149">In the secondary role, this replica will support read access connections, allowing you to offload read-only processing to this replica.</span></span>  
  
    ```powershell
    $agPath = "SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
    $endpointURL = "TCP://PrimaryServerName.domain.com:5022"  
    $failoverMode = "Manual"  
    $availabilityMode = "AsynchronousCommit"  
    $secondaryReadMode = "AllowAllConnections"  
  
    New-SqlAvailabilityReplica -Name SecondaryServer\Instance `   
    -EndpointUrl $endpointURL `   
    -FailoverMode $failoverMode `   
    -AvailabilityMode $availabilityMode `   
    -ConnectionModeInSecondaryRole $secondaryReadMode `   
    -Path $agPath  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="214de-150">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="214de-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="214de-151">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="214de-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="214de-152">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="214de-152">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="214de-153">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="214de-153">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-adding-a-secondary-replica"></a><a name="FollowUp"></a><span data-ttu-id="214de-154">Completamento: dopo l'aggiunta di una replica secondaria</span><span class="sxs-lookup"><span data-stu-id="214de-154">Follow Up: After Adding a Secondary Replica</span></span>  
 <span data-ttu-id="214de-155">Per aggiungere una replica per un gruppo di disponibilità esistente, è necessario effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="214de-155">To add a replica for an existing availability group, you must perform the following steps:</span></span>  
  
1.  <span data-ttu-id="214de-156">Connettersi all'istanza del server che ospiterà la nuova replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="214de-156">Connect to the server instance that is going to host the new secondary replica.</span></span>  
  
2.  <span data-ttu-id="214de-157">Creare un join della nuova replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="214de-157">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="214de-158">Per altre informazioni, vedere [Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="214de-158">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="214de-159">Per ogni database nel gruppo di disponibilità, creare un database secondario nell'istanza del server che ospita la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="214de-159">For each database in the availability group, create a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="214de-160">Per altre informazioni, vedere [Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="214de-160">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="214de-161">Creare un join dei nuovi database secondari al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="214de-161">Join each of the new secondary databases to the availability group.</span></span> <span data-ttu-id="214de-162">Per altre informazioni, vedere [Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="214de-162">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="214de-163">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="214de-163">Related Tasks</span></span>  
 <span data-ttu-id="214de-164">**Per gestire una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="214de-164">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="214de-165">Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="214de-165">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="214de-166">Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="214de-166">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="214de-167">Configurare l'accesso in sola lettura in una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="214de-167">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="214de-168">Modificare la modalità di disponibilità di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="214de-168">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="214de-169">Modificare la modalità di failover di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="214de-169">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="214de-170">Modificare il periodo di timeout della sessione per una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="214de-170">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="214de-171">Modificare il periodo di timeout della sessione per una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="214de-171">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="214de-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="214de-172">See Also</span></span>  
 <span data-ttu-id="214de-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="214de-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="214de-174">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="214de-174">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="214de-175">[Creazione e configurazione di gruppi di disponibilità &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="214de-175">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="214de-176">[Usare il dashboard AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="214de-176">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="214de-177">Monitorare Gruppi di disponibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="214de-177">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
