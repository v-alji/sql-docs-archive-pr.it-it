---
title: Modificare la modalità di disponibilità di una replica di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], availability modes
ms.assetid: c4da8f25-fb1b-45a4-8bf2-195df6df634c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1636f3ea86e083e47276423b120dbc8d3744d387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725008"
---
# <a name="change-the-availability-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="f1759-102">Modificare la modalità di disponibilità di una replica di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f1759-102">Change the Availability Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="f1759-103">In questo argomento viene illustrato come modificare la modalità di disponibilità di una replica di disponibilità in un gruppo di disponibilità AlwaysOn in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1759-103">This topic describes how to change the availability mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="f1759-104">La modalità di disponibilità è una proprietà della replica che determina se il commit della replica viene eseguito in modo asincrono o sincrono.</span><span class="sxs-lookup"><span data-stu-id="f1759-104">The availability mode is a replica property that controls the whether the replica commits asynchronously or synchronously.</span></span> <span data-ttu-id="f1759-105">La*modalità con commit asincrono* ottimizza le prestazioni a discapito della disponibilità elevata e supporta solo il failover manuale forzato (con possibile perdita di dati), generalmente denominato *failover forzato*.</span><span class="sxs-lookup"><span data-stu-id="f1759-105">*Asynchronous-commit mode* maximizes performance at the expense of high availability and supports only forced manual failover (with possible data loss), typically called *forced failover*.</span></span> <span data-ttu-id="f1759-106">La*modalità con commit sincrono* privilegia la disponibilità elevata rispetto alle prestazioni e, una volta sincronizzata la replica secondaria, supporta il failover manuale e, facoltativamente, quello automatico.</span><span class="sxs-lookup"><span data-stu-id="f1759-106">*Synchronous-commit mode* emphasizes high availability over performance and, once the secondary replica is synchronized, supports manual failover and, optionally, automatic failover.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1759-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f1759-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f1759-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f1759-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="f1759-109">È necessario essere connessi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="f1759-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1759-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f1759-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1759-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f1759-111">Permissions</span></span>  
 <span data-ttu-id="f1759-112">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="f1759-112">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f1759-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1759-113">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f1759-114">**Per modificare la modalità di disponibilità di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="f1759-114">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="f1759-115">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="f1759-115">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f1759-116">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="f1759-116">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="f1759-117">Fare clic sul gruppo di disponibilità di cui si desidera modificare la replica.</span><span class="sxs-lookup"><span data-stu-id="f1759-117">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="f1759-118">Fare clic con il pulsante destro del mouse sulla replica e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f1759-118">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="f1759-119">Nella finestra di dialogo **Proprietà replica di disponibilità** utilizzare l'elenco a discesa **Modalità di disponibilità** per modificare la modalità di disponibilità di questa replica.</span><span class="sxs-lookup"><span data-stu-id="f1759-119">In the **Availability Replica Properties** dialog box, use the **Availability mode** drop list to change the availability mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f1759-120">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1759-120">Using Transact-SQL</span></span>  
 <span data-ttu-id="f1759-121">**Per modificare la modalità di disponibilità di un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="f1759-121">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="f1759-122">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="f1759-122">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="f1759-123">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f1759-123">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="f1759-124">ALTER AVAILABILITY GROUP *nome_gruppo* MODIFY REPLICA ON '*nome_server*'</span><span class="sxs-lookup"><span data-stu-id="f1759-124">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="f1759-125">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="f1759-125">WITH ( {</span></span>  
  
     <span data-ttu-id="f1759-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="f1759-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="f1759-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="f1759-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="f1759-128">} )</span><span class="sxs-lookup"><span data-stu-id="f1759-128">} )</span></span>  
  
     <span data-ttu-id="f1759-129">dove *group_name* è il nome del gruppo di disponibilità e *server_name* è il nome dell'istanza del server che ospita la replica da modificare.</span><span class="sxs-lookup"><span data-stu-id="f1759-129">where *group_name* is the name of the availability group and *server_name* is the name of the server instance that hosts the replica to be modified.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1759-130">FAILOVER_MODE = AUTOMATIC è supportata solo se si specifica anche AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span><span class="sxs-lookup"><span data-stu-id="f1759-130">FAILOVER_MODE = AUTOMATIC is supported only if you also specify AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span></span>  
  
     <span data-ttu-id="f1759-131">Nell'esempio seguente, relativo alla replica primaria del gruppo di disponibilità `AccountsAG` , vengono impostate le modalità di disponibilità e di failover sul commit sincrono e il failover automatico, rispettivamente, per la replica ospitata dall'istanza del server `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="f1759-131">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the availability and failover modes to synchronous commit and automatic failover, respectively, for the replica hosted by the `INSTANCE09` server instance.</span></span>  
  
    ```  
  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (AVAILABILITY_MODE = SYNCHRONOUS_COMMIT);  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="f1759-132">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1759-132">Using PowerShell</span></span>

### <a name="to-change-the-availability-mode-of-an-availability-group"></a><span data-ttu-id="f1759-133">Per modificare la modalità di disponibilità di un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="f1759-133">To change the availability mode of an availability group</span></span>
  
1.  <span data-ttu-id="f1759-134">Spostarsi nella directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="f1759-134">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="f1759-135">Utilizzare il cmdlet `Set-SqlAvailabilityReplica` con il parametro `AvailabilityMode` e, facoltativamente, con il parametro `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="f1759-135">Use the `Set-SqlAvailabilityReplica` cmdlet with the `AvailabilityMode` parameter and, optionally, the `FailoverMode` parameter.</span></span>  
  
     <span data-ttu-id="f1759-136">Ad esempio, con il comando seguente si modifica la replica `MyReplica` nel gruppo di disponibilità `MyAg` in modo da utilizzare la modalità di disponibilità con commit asincrono e supportare il failover automatico.</span><span class="sxs-lookup"><span data-stu-id="f1759-136">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `   
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f1759-137">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1759-137">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f1759-138">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f1759-138">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="f1759-139">Per configurare e usare il provider di SQL Server PowerShell, vedere [provider di SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f1759-139">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f1759-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1759-140">See Also</span></span>  
 <span data-ttu-id="f1759-141">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f1759-141">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="f1759-142">[Modalità di disponibilità (Gruppi di disponibilità AlwaysOn)](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="f1759-142">[Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="f1759-143">Failover e modalità di failover &#40;Gruppi di disponibilità AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="f1759-143">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md)  
