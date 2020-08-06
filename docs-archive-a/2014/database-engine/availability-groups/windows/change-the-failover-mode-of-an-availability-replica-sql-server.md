---
title: Modificare la modalità di failover di una replica di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover modes [SQL Server]
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], failover modes
- Availability Groups [SQL Server], configuring
ms.assetid: 619a826f-8e65-48eb-8c34-39497d238279
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d946440e2950192299c42652babb4082790dbd03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724999"
---
# <a name="change-the-failover-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="db1e0-102">Modificare la modalità di failover di una replica di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="db1e0-102">Change the Failover Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="db1e0-103">In questo argomento viene illustrato come modificare la modalità di failover di una replica di disponibilità in un gruppo di disponibilità AlwaysOn in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db1e0-103">This topic describes how to change the failover mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="db1e0-104">La modalità di failover è una proprietà della replica che determina la modalità di failover per le repliche eseguite nella modalità di disponibilità con commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="db1e0-104">The failover mode is a replica property that determines the failover mode for replicas that run under synchronous-commit availability mode.</span></span> <span data-ttu-id="db1e0-105">Per altre informazioni, vedere [Failover e modalità di failover &#40;gruppi di disponibilità AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) e [Modalità di disponibilità &#40;gruppi di disponibilità AlwaysOn&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="db1e0-105">For more information, see [Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) and [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="db1e0-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="db1e0-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="db1e0-107">Prerequisiti e restrizioni</span><span class="sxs-lookup"><span data-stu-id="db1e0-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="db1e0-108">Questa attività può essere eseguita solo sulle repliche primarie.</span><span class="sxs-lookup"><span data-stu-id="db1e0-108">This task is supported only on primary replicas.</span></span> <span data-ttu-id="db1e0-109">È necessario essere connessi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="db1e0-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="db1e0-110">Le istanze del cluster di failover di SQL Server non supportano il failover automatico da gruppi di disponibilità, pertanto le replica di disponibilità ospitate da un'istanza del cluster di failover possono essere configurate solo per il failover manuale.</span><span class="sxs-lookup"><span data-stu-id="db1e0-110">SQL Server Failover Cluster Instances (FCIs) do not support automatic failover by availability groups, so any availability replica that is hosted by an FCI can only be configured for manual failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="db1e0-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="db1e0-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="db1e0-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="db1e0-112">Permissions</span></span>  
 <span data-ttu-id="db1e0-113">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="db1e0-113">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="db1e0-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="db1e0-114">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="db1e0-115">**Per modificare la modalità di failover di una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="db1e0-115">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="db1e0-116">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="db1e0-116">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="db1e0-117">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="db1e0-117">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="db1e0-118">Fare clic sul gruppo di disponibilità di cui si desidera modificare la replica.</span><span class="sxs-lookup"><span data-stu-id="db1e0-118">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="db1e0-119">Fare clic con il pulsante destro del mouse sulla replica e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="db1e0-119">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="db1e0-120">Nella finestra di dialogo **Proprietà replica di disponibilità** utilizzare l'elenco a discesa **Modalità di failover** per modificare la modalità di failover di questa replica.</span><span class="sxs-lookup"><span data-stu-id="db1e0-120">In the **Availability Replica Properties** dialog box, use the **Failover mode** drop list to change the failover mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="db1e0-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="db1e0-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="db1e0-122">**Per modificare la modalità di failover di una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="db1e0-122">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="db1e0-123">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="db1e0-123">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="db1e0-124">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="db1e0-124">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="db1e0-125">ALTER AVAILABILITY GROUP *nome_gruppo* MODIFY REPLICA ON '*nome_server*'</span><span class="sxs-lookup"><span data-stu-id="db1e0-125">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="db1e0-126">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="db1e0-126">WITH ( {</span></span>  
  
     <span data-ttu-id="db1e0-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="db1e0-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="db1e0-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="db1e0-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="db1e0-129">}  )</span><span class="sxs-lookup"><span data-stu-id="db1e0-129">}  )</span></span>  
  
     <span data-ttu-id="db1e0-130">dove</span><span class="sxs-lookup"><span data-stu-id="db1e0-130">where</span></span>  
  
    -   <span data-ttu-id="db1e0-131">*nome_gruppo* è il nome del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="db1e0-131">*group_name* is the name of the availability group.</span></span>  
  
    -   <span data-ttu-id="db1e0-132">{ ' *_sistema*[\\*nome_istanza*]' | '*nome_rete_FCI*[\\*nome_istanza*]' }</span><span class="sxs-lookup"><span data-stu-id="db1e0-132">{ '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }</span></span>  
  
         <span data-ttu-id="db1e0-133">Specifica l'indirizzo dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospita la replica di disponibilità da modificare.</span><span class="sxs-lookup"><span data-stu-id="db1e0-133">Specifies the address of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica to be altered.</span></span> <span data-ttu-id="db1e0-134">I componenti di questo indirizzo sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="db1e0-134">The components of this address are as follows:</span></span>  
  
         <span data-ttu-id="db1e0-135">*_sistema*</span><span class="sxs-lookup"><span data-stu-id="db1e0-135">*system_name*</span></span>  
         <span data-ttu-id="db1e0-136">Nome NetBIOS del computer in cui risiede un'istanza autonoma del server.</span><span class="sxs-lookup"><span data-stu-id="db1e0-136">Is the NetBIOS name of the computer system on which a stand-alone server instance resides.</span></span>  
  
         <span data-ttu-id="db1e0-137">*nome_rete_FCI*</span><span class="sxs-lookup"><span data-stu-id="db1e0-137">*FCI_network_name*</span></span>  
         <span data-ttu-id="db1e0-138">Nome di rete utilizzato per accedere a un cluster di failover di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in cui un'istanza del server di destinazione è un partner di failover di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db1e0-138">Is the network name that is used to access a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster in which a target server instance is a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover partner (an FCI).</span></span>  
  
         <span data-ttu-id="db1e0-139">*instance_name*</span><span class="sxs-lookup"><span data-stu-id="db1e0-139">*instance_name*</span></span>  
         <span data-ttu-id="db1e0-140">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospita la replica di disponibilità di destinazione.</span><span class="sxs-lookup"><span data-stu-id="db1e0-140">Is the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the target availability replica.</span></span> <span data-ttu-id="db1e0-141">Per un'istanza del server predefinita, *nome_istanza* è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="db1e0-141">For a default server instance, *instance_name* is optional.</span></span>  
  
     <span data-ttu-id="db1e0-142">Per altre informazioni su questi parametri, vedere [ALTER AVAILABILITY GROUP &#40; Transact-SQL &#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="db1e0-142">For more information about these parameters, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="db1e0-143">L'esempio seguente, relativo alla replica primaria del gruppo di disponibilità *MyAG* , mostra come impostare la modalità di failover automatico sulla replica di disponibilità situata in un'istanza del server predefinita in un computer denominato *COMPUTER01*.</span><span class="sxs-lookup"><span data-stu-id="db1e0-143">The following example, entered on the primary replica of the *MyAG* availability group, changes the failover mode to automatic failover on the availability replica that is located on the default server instance on a computer named *COMPUTER01*.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP MyAG MODIFY REPLICA ON 'COMPUTER01' WITH  
       (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="db1e0-144">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="db1e0-144">Using PowerShell</span></span>  

### <a name="to-change-the-failover-mode-of-an-availability-replica"></a><span data-ttu-id="db1e0-145">Per modificare la modalità di failover di una replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="db1e0-145">To change the failover mode of an availability replica</span></span>
  
1.  <span data-ttu-id="db1e0-146">Spostarsi nella directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="db1e0-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="db1e0-147">Utilizzare il cmdlet `Set-SqlAvailabilityReplica` con il parametro `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="db1e0-147">Use the `Set-SqlAvailabilityReplica` cmdlet with the `FailoverMode` parameter.</span></span> <span data-ttu-id="db1e0-148">Quando si imposta una replica su failover automatico, potrebbe essere necessario utilizzare il parametro `AvailabilityMode` per impostare la replica su modalità di disponibilità con commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="db1e0-148">When setting a replica to automatic failover, you might need to use the `AvailabilityMode` parameter to change the replica to synchronous-commit availability mode.</span></span>  
  
     <span data-ttu-id="db1e0-149">Ad esempio, con il comando seguente si modifica la replica `MyReplica` nel gruppo di disponibilità `MyAg` in modo da utilizzare la modalità di disponibilità con commit asincrono e supportare il failover automatico.</span><span class="sxs-lookup"><span data-stu-id="db1e0-149">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\Replicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="db1e0-150">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db1e0-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="db1e0-151">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="db1e0-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="db1e0-152">Per configurare e usare il provider di SQL Server PowerShell, vedere [provider di SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="db1e0-152">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db1e0-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db1e0-153">See Also</span></span>  
 [<span data-ttu-id="db1e0-154">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="db1e0-154">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="db1e0-155">[Modalità di disponibilità &#40;Gruppi di disponibilità AlwaysOn&#41;](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="db1e0-155">[Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="db1e0-156">Failover e modalità di failover &#40;Gruppi di disponibilità AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="db1e0-156">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md) 
