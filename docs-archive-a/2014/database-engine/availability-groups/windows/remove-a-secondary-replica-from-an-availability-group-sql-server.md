---
title: Rimuovere una replica secondaria da un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removesecondaryar.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 35ddc8b6-3e7c-4417-9a0a-d4987a09ddf7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e3f2b35ec9cf27f2f7b23714a41665f2709837a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626306"
---
# <a name="remove-a-secondary-replica-from-an-availability-group-sql-server"></a><span data-ttu-id="a00ef-102">Rimuovere una replica secondaria da un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a00ef-102">Remove a Secondary Replica from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="a00ef-103">In questo argomento viene illustrato come rimuovere una replica secondaria da un gruppo di disponibilità AlwaysOn utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a00ef-103">This topic describes how to remove a secondary replica from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="a00ef-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a00ef-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a00ef-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a00ef-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a00ef-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a00ef-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a00ef-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a00ef-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a00ef-108">**Per rimuovere una replica secondaria utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="a00ef-108">**To remove a secondary replica, using:**</span></span>  
  
     [<span data-ttu-id="a00ef-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a00ef-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a00ef-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a00ef-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a00ef-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a00ef-111">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="a00ef-112">**Completamento:**  [Dopo la rimozione di una replica secondaria](#PostBestPractices)</span><span class="sxs-lookup"><span data-stu-id="a00ef-112">**Follow Up:**  [After Removing a Secondary Replica](#PostBestPractices)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a00ef-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a00ef-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a00ef-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a00ef-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a00ef-115">Questa attività è supportata solo nella replica primaria.</span><span class="sxs-lookup"><span data-stu-id="a00ef-115">This task is supported only on the primary replica.</span></span>  
  
-   <span data-ttu-id="a00ef-116">È possibile rimuove solo una replica secondaria da un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a00ef-116">Only a secondary replica can be removed from an availability group.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a00ef-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a00ef-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="a00ef-118">È necessario essere connessi all'istanza del server che ospita la replica primaria del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a00ef-118">You must be connected to the server instance that hosts the primary replica of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a00ef-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a00ef-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a00ef-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a00ef-120">Permissions</span></span>  
 <span data-ttu-id="a00ef-121">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="a00ef-121">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a00ef-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a00ef-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a00ef-123">**Per rimuovere una replica secondaria**</span><span class="sxs-lookup"><span data-stu-id="a00ef-123">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="a00ef-124">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="a00ef-124">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a00ef-125">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="a00ef-125">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a00ef-126">Selezionare il gruppo di disponibilità ed espandere il nodo **Repliche di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="a00ef-126">Select the availability group, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="a00ef-127">Questo passaggio dipende dalla scelta di rimuovere più repliche o una sola replica, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a00ef-127">This step depends on whether you want to remove multiple replicas or only one replica, as follows:</span></span>  
  
    -   <span data-ttu-id="a00ef-128">Per rimuovere più repliche, utilizzare il riquadro **Dettagli Esplora oggetti** per visualizzare e selezionare tutte le repliche che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="a00ef-128">To remove multiple replicas, use the **Object Explorer Details** pane to view and select all the replicas that you want to remove.</span></span> <span data-ttu-id="a00ef-129">Per altre informazioni, vedere [Utilizzare Dettagli Esplora oggetti per monitorare Gruppi di disponibilità &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="a00ef-129">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="a00ef-130">Per rimuovere una singola replica, selezionarla nel riquadro **Esplora oggetti** o **Dettagli Esplora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="a00ef-130">To remove a single replica, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="a00ef-131">Fare clic con il pulsante destro del mouse sulla replica o sulle repliche secondarie selezionate e scegliere **Rimuovi da gruppo di disponibilità** nel menu dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a00ef-131">Right-click the selected secondary replica or replicas, and select **Remove from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="a00ef-132">Nella finestra di dialogo **Rimozione delle repliche secondarie dal gruppo di disponibilità** scegliere **OK**per rimuovere tutte le repliche secondarie elencate.</span><span class="sxs-lookup"><span data-stu-id="a00ef-132">In the **Remove Secondary Replicas from Availability Group** dialog box, to remove all the listed secondary replicas, click **OK**.</span></span> <span data-ttu-id="a00ef-133">Se non si desidera rimuovere tutte le repliche elencate, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="a00ef-133">If you do not want to remove all the listed replicas, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a00ef-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a00ef-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="a00ef-135">**Per rimuovere una replica secondaria**</span><span class="sxs-lookup"><span data-stu-id="a00ef-135">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="a00ef-136">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="a00ef-136">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="a00ef-137">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a00ef-137">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="a00ef-138">ALTER AVAILABILITY GROUP *nome_gruppo* REMOVE REPLICA ON '*nome_istanza*' [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="a00ef-138">ALTER AVAILABILITY GROUP *group_name* REMOVE REPLICA ON '*instance_name*' [,...*n*]</span></span>  
  
     <span data-ttu-id="a00ef-139">dove *nome_gruppo* è il nome del gruppo di disponibilità e *nome_istanza* è l'istanza del server in cui si trova la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="a00ef-139">where *group_name* is the name of the availability group and *instance_name* is the server instance where the secondary replica is located.</span></span>  
  
     <span data-ttu-id="a00ef-140">Nell'esempio seguente viene rimossa una replica secondaria dal gruppo di disponibilità *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="a00ef-140">The following example removes a secondary replica from the *MyAG* availability group.</span></span> <span data-ttu-id="a00ef-141">La replica secondaria di destinazione si trova in un'istanza del server denominata *HADR_INSTANCE* in un computer denominato *COMPUTER02*.</span><span class="sxs-lookup"><span data-stu-id="a00ef-141">The target secondary replica is located on a server instance named *HADR_INSTANCE* on a computer named *COMPUTER02*.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE REPLICA ON 'COMPUTER02\HADR_INSTANCE';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a00ef-142">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="a00ef-142">Using PowerShell</span></span>  
 <span data-ttu-id="a00ef-143">**Per rimuovere una replica secondaria**</span><span class="sxs-lookup"><span data-stu-id="a00ef-143">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="a00ef-144">Spostarsi nella directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="a00ef-144">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="a00ef-145">Usare il cmdlet **Remove-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="a00ef-145">Use the **Remove-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="a00ef-146">Ad esempio, il seguente comando rimuove la replica di disponibilità nel server `MyReplica` dal gruppo di disponibilità denominato `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="a00ef-146">For example, the following command removes the availability replica on the server `MyReplica` from the availability group named `MyAg`.</span></span>  <span data-ttu-id="a00ef-147">Il comando deve essere eseguito nell'istanza del server che ospita la replica primaria del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="a00ef-147">This command must be run on the server instance that hosts the primary replica of the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityReplica -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a00ef-148">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a00ef-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a00ef-149">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a00ef-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="a00ef-150">**Per impostare e utilizzare il provider PowerShell per SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a00ef-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="a00ef-151">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="a00ef-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-replica"></a><a name="PostBestPractices"></a> <span data-ttu-id="a00ef-152">Completamento: Dopo la rimozione di una replica secondaria</span><span class="sxs-lookup"><span data-stu-id="a00ef-152">Follow Up: After Removing a Secondary Replica</span></span>  
 <span data-ttu-id="a00ef-153">Se si specifica una replica che non è attualmente disponibile, quando viene portata online viene rilevato che è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="a00ef-153">If you specify a replica that is currently unavailable, when the replica comes online, it will discover that it has been removed.</span></span>  
  
 <span data-ttu-id="a00ef-154">La rimozione di una replica ne arresta la ricezione di dati.</span><span class="sxs-lookup"><span data-stu-id="a00ef-154">Removing a replica causes it to stop receiving data.</span></span> <span data-ttu-id="a00ef-155">Dopo la conferma della rimozione dall'archivio globale di una replica secondaria, la replica rimuove le impostazioni del gruppo di disponibilità dai relativi database che rimangono nell'istanza del server locale nello stato RECOVERING.</span><span class="sxs-lookup"><span data-stu-id="a00ef-155">After a secondary replica confirms that it has been removed from the global store, the replica removes the availability group settings from its databases, which remain on the local server instance in the RECOVERING state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00ef-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a00ef-156">See Also</span></span>  
 <span data-ttu-id="a00ef-157">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a00ef-157">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="a00ef-158">[Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a00ef-158">[Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span></span>  
 [<span data-ttu-id="a00ef-159">Rimuovere un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a00ef-159">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
