---
title: Modificare il periodo di timeout della sessione per una replica di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], session timeout
- session timeout [SQL Server]
ms.assetid: e23c6e06-1cd1-4d4a-9bc2-e3e06ab2933d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 302ba4a2b0b72a70b05e563eb4085913074469eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724992"
---
# <a name="change-the-session-timeout-period-for-an-availability-replica-sql-server"></a><span data-ttu-id="43abd-102">Modificare il periodo di timeout della sessione per una replica di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="43abd-102">Change the Session-Timeout Period for an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="43abd-103">In questo argomento viene illustrato come configurare il periodo di timeout della sessione di una replica di disponibilità AlwaysOn utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43abd-103">This topic describes how to configure the session-timeout period of an AlwaysOn availability replica by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="43abd-104">Il periodo di timeout della sessione è una proprietà della replica che determina i secondi di attesa di una replica di disponibilità per una risposta del ping da una replica connessa prima di considerare la connessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="43abd-104">The session-timeout period is a replica property that controls how many seconds (in seconds) that an availability replica waits for a ping response from a connected replica before considering the connection to have failed.</span></span> <span data-ttu-id="43abd-105">Per impostazione predefinita, l'attesa di una replica è di 10 secondi per una risposta del ping.</span><span class="sxs-lookup"><span data-stu-id="43abd-105">By default, a replica waits 10 seconds for a ping response.</span></span> <span data-ttu-id="43abd-106">Questa proprietà della replica si applica solo alla connessione tra una determinata replica secondaria e la replica primaria del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="43abd-106">This replica property applies only the connection between a given secondary replica and the primary replica of the availability group.</span></span> <span data-ttu-id="43abd-107">Per altre informazioni sul periodo di timeout della sessione, vedere [Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="43abd-107">For more information about the session-timeout period, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="43abd-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="43abd-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="43abd-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="43abd-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="43abd-110">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="43abd-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="43abd-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="43abd-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="43abd-112">**Per modificare il periodo di timeout della sessione mediante:**</span><span class="sxs-lookup"><span data-stu-id="43abd-112">**To change the session-timeout period, using:**</span></span>  
  
     [<span data-ttu-id="43abd-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43abd-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="43abd-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43abd-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="43abd-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="43abd-115">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="43abd-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="43abd-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="43abd-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="43abd-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="43abd-118">È necessario essere connessi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="43abd-118">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="43abd-119">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="43abd-119">Recommendations</span></span>  
 <span data-ttu-id="43abd-120">È consigliabile usare un periodo di timeout di almeno 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="43abd-120">We recommend that you keep the time-out period at 10 seconds or greater.</span></span> <span data-ttu-id="43abd-121">Con un valore inferiore a 10 secondi, può verificarsi un sovraccarico del sistema, con perdita di PING e generazione di falsi errori.</span><span class="sxs-lookup"><span data-stu-id="43abd-121">Setting the value to less than 10 seconds creates the possibility of a heavily loaded system missing PINGs and declaring a false failure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="43abd-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="43abd-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="43abd-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="43abd-123">Permissions</span></span>  
 <span data-ttu-id="43abd-124">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="43abd-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43abd-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43abd-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="43abd-126">**Per modificare il periodo di timeout della sessione per una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="43abd-126">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="43abd-127">In Esplora oggetti connettersi all'istanza del server che ospita la replica primaria ed espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="43abd-127">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="43abd-128">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="43abd-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="43abd-129">Fare clic sul gruppo di disponibilità di cui si desidera configurare la replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="43abd-129">Click the availability group whose availability replica you want to configure.</span></span>  
  
4.  <span data-ttu-id="43abd-130">Fare clic con il pulsante destro del mouse sulla replica da configurare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="43abd-130">Right-click the replica to be configured, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="43abd-131">Nella finestra di dialogo **Proprietà replica di disponibilità** usare il campo **Timeout sessione (secondi)** per modificare il numero di secondi per il periodo di timeout della sessione su questa replica.</span><span class="sxs-lookup"><span data-stu-id="43abd-131">In the **Availability Replica Properties** dialog box, use the **Session timeout (seconds)** field to change the number of seconds for the session-timeout period on this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="43abd-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43abd-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="43abd-133">**Per modificare il periodo di timeout della sessione per una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="43abd-133">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="43abd-134">Connettersi all'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="43abd-134">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="43abd-135">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="43abd-135">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="43abd-136">ALTER AVAILABILITY GROUP *nome_gruppo*</span><span class="sxs-lookup"><span data-stu-id="43abd-136">ALTER AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="43abd-137">MODIFY REPLICA ON '*nome_istanza*' WITH ( SESSION_TIMEOUT =*secondi* )</span><span class="sxs-lookup"><span data-stu-id="43abd-137">MODIFY REPLICA ON '*instance_name*' WITH ( SESSION_TIMEOUT =*seconds* )</span></span>  
  
     <span data-ttu-id="43abd-138">dove *nome_gruppo* è il nome del gruppo di disponibilità, *nome_istanza* è il nome dell'istanza del server che ospita la replica di disponibilità da modificare e *secondi* specifica il numero minimo di secondi di attesa della replica prima di applicare log ai database quando funge da replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="43abd-138">where *group_name* is the name of the availability group, *instance_name* is the name of the server instance that hosts the availability replica to be modified, and *seconds* specifies the minimum number of seconds that the replica must wait before applying log to databases when acting as a secondary replica.</span></span> <span data-ttu-id="43abd-139">Il valore predefinito è 0 secondi, che indica la non applicazione di ritardo.</span><span class="sxs-lookup"><span data-stu-id="43abd-139">The default is 0 seconds, which indicates that there is no apply delay.</span></span>  
  
     <span data-ttu-id="43abd-140">Nell'esempio seguente, relativo alla replica primaria del gruppo di disponibilità `AccountsAG` , il valore del timeout della sessione viene impostato su `15` secondi per la replica presente nell'istanza del server `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="43abd-140">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the session-timeout value to `15` seconds for the replica located on the `INSTANCE09` server instance.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP AccountsAG   
       MODIFY REPLICA ON 'INSTANCE09' WITH (SESSION_TIMEOUT = 15);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="43abd-141">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="43abd-141">Using PowerShell</span></span>  

### <a name="to-change-the-session-timeout-period-for-an-availability-replica"></a><span data-ttu-id="43abd-142">Per modificare il periodo di timeout della sessione per una replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="43abd-142">To change the session-timeout period for an availability replica</span></span>
  
1.  <span data-ttu-id="43abd-143">Spostarsi nella directory (`cd`) dell'istanza del server che ospita la replica primaria.</span><span class="sxs-lookup"><span data-stu-id="43abd-143">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="43abd-144">Utilizzare il cmdlet `Set-SqlAvailabilityReplica` con il parametro `SessionTimeout` per modificare il numero di secondi per il periodo di timeout della sessione su una replica di disponibilità specificata.</span><span class="sxs-lookup"><span data-stu-id="43abd-144">Use the `Set-SqlAvailabilityReplica` cmdlet with the `SessionTimeout` parameter to change the number of seconds for the session-timeout period on a specified availability replica.</span></span>  
  
     <span data-ttu-id="43abd-145">Ad esempio, nel comando seguente viene impostato un periodo della sessione di timeout su 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="43abd-145">For example, the following command sets the session-timeout period to 15 seconds.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -SessionTimeout 15 -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="43abd-146">Per visualizzare la sintassi di un cmdlet, utilizzare il cmdlet `Get-Help` nell'ambiente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43abd-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="43abd-147">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="43abd-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="43abd-148">Per configurare e usare il provider di SQL Server PowerShell, vedere [provider di SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="43abd-148">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="43abd-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43abd-149">See Also</span></span>  
 [<span data-ttu-id="43abd-150">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43abd-150">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
