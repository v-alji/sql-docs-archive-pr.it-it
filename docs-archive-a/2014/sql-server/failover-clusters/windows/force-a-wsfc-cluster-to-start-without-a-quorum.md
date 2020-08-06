---
title: Forzare l'avvio di un cluster WSFC senza un quorum | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: 4a121375-7424-4444-b876-baefa8fe9015
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6f2110b706de015d0c7b19475b335908c118267
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628265"
---
# <a name="force-a-wsfc-cluster-to-start-without-a-quorum"></a><span data-ttu-id="c9bd8-102">Forzare l'avvio di un cluster WSFC senza un quorum</span><span class="sxs-lookup"><span data-stu-id="c9bd8-102">Force a WSFC Cluster to Start Without a Quorum</span></span>
  <span data-ttu-id="c9bd8-103">In questo argomento viene illustrato come forzare l'avvio senza un quorum di un nodo del cluster Windows Server Failover Clustering (WSFC).</span><span class="sxs-lookup"><span data-stu-id="c9bd8-103">This topic describes how to force a Windows Server Failover Clustering (WSFC) cluster node to start without a quorum.</span></span>  <span data-ttu-id="c9bd8-104">Questa operazione potrebbe rivelarsi necessaria negli scenari multi-subnet e in caso di ripristino di emergenza per recuperare i dati e ristabilire completamente la disponibilità elevata per le istanze del cluster di failover di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9bd8-104">This may be required in disaster recovery and multi-subnet scenarios to recover data and fully re-establish high-availability for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="c9bd8-105">**Prima di iniziare:**  [Indicazioni](#Recommendations), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="c9bd8-105">**Before you start:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="c9bd8-106">**Per forzare l'avvio di un cluster senza un quorum usando:**  [Utilizzo di Gestione cluster di failover](#FailoverClusterManagerProcedure), [Utilizzo di Powershell](#PowerShellProcedure), [Utilizzo di Net.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="c9bd8-106">**To force a cluster to start without a quorum using:**  [Using Failover Cluster Manager](#FailoverClusterManagerProcedure), [Using Powershell](#PowerShellProcedure), [Using Net.exe](#CommandPromptProcedure)</span></span>  
  
-   <span data-ttu-id="c9bd8-107">**Completamento:**  [Completamento: dopo avere forzato l'avvio senza un quorum di un cluster](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c9bd8-107">**Follow up:**  [Follow Up: After Forcing Cluster to Start without a Quorum](#FollowUp)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c9bd8-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c9bd8-108">Before You Start</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c9bd8-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c9bd8-109">Recommendations</span></span>  
 <span data-ttu-id="c9bd8-110">Salvo esplicita istruzione, le procedure illustrate in questo argomento funzionano se eseguite da qualsiasi nodo del cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-110">Except where explicitly directed, the procedures in this topic should work if you execute them from any node in the WSFC cluster.</span></span>  <span data-ttu-id="c9bd8-111">Tuttavia, è possibile ottenere risultati migliori ed evitare problemi di rete eseguendo questi passaggi dal nodo di cui si desidera forzare l'avvio senza un quorum.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-111">However, you may obtain better results, and avoid networking issues, by executing these steps from the node that you intend to force to start without a quorum.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c9bd8-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c9bd8-112">Security</span></span>  
 <span data-ttu-id="c9bd8-113">L'utente deve disporre di un account di dominio che sia membro del gruppo Administrators locale su ogni nodo del cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-113">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-failover-cluster-manager"></a><a name="FailoverClusterManagerProcedure"></a><span data-ttu-id="c9bd8-114">Utilizzo di Gestione cluster di failover</span><span class="sxs-lookup"><span data-stu-id="c9bd8-114">Using Failover Cluster Manager</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="c9bd8-115">Per forzare l'avvio di un cluster senza un quorum</span><span class="sxs-lookup"><span data-stu-id="c9bd8-115">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="c9bd8-116">Aprire Gestione cluster di failover e connettersi al nodo del cluster desiderato per forzare la modalità online.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-116">Open a Failover Cluster Manager and connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="c9bd8-117">Nel riquadro **azioni** fare clic su **Forza avvio del cluster**, quindi fare clic su **Sì-forza l'avvio del cluster**.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-117">In the **Actions** pane, click **Force Cluster Start**, and then click **Yes - Force my cluster to start**.</span></span>  
  
3.  <span data-ttu-id="c9bd8-118">Nel riquadro sinistro, nell'albero **Gestione cluster di failover** fare clic sul nome del cluster.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-118">In the left pane, in the **Failover Cluster Manager** tree, click the cluster name.</span></span>  
  
4.  <span data-ttu-id="c9bd8-119">Nel riquadro Riepilogo confermare che il valore **Configurazione quorum** corrente è:  **Avviso: il cluster è in esecuzione in stato ForceQuorum**.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-119">In the summary pane, confirm that the current **Quorum Configuration** value is:  **Warning: Cluster is running in ForceQuorum state**.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a><span data-ttu-id="c9bd8-120">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9bd8-120">Using Powershell</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="c9bd8-121">Per forzare l'avvio di un cluster senza un quorum</span><span class="sxs-lookup"><span data-stu-id="c9bd8-121">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="c9bd8-122">Avviare Windows PowerShell con privilegi elevati tramite **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-122">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="c9bd8-123">Importare il modulo `FailoverClusters` per abilitare i commandlet del cluster.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-123">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="c9bd8-124">Utilizzare `Stop-ClusterNode` per assicurarsi che il servizio cluster sia stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-124">Use `Stop-ClusterNode` to make sure that the cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="c9bd8-125">Utilizzare `Start-ClusterNode` con `-FixQuorum` per forzare l'avvio del servizio cluster.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-125">Use `Start-ClusterNode` with `-FixQuorum` to force the cluster service to start.</span></span>  
  
5.  <span data-ttu-id="c9bd8-126">Utilizzare `Get-ClusterNode` con `-Propery NodeWieght = 1` per impostare il valore che garantisca che il nodo è un membro votante del quorum.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-126">Use `Get-ClusterNode` with `-Propery NodeWieght = 1` to set the value the guarantees that the node is a voting member of the quorum.</span></span>  
  
6.  <span data-ttu-id="c9bd8-127">Restituire le proprietà del nodo del cluster in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-127">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="c9bd8-128">Esempio (Powershell)</span><span class="sxs-lookup"><span data-stu-id="c9bd8-128">Example (Powershell)</span></span>  
 <span data-ttu-id="c9bd8-129">Nell'esempio seguente viene imposto l'avvio senza un quorum del cluster del nodo AlwaysOnSrv02, viene impostato il valore `NodeWeight = 1`e viene enumerato lo stato del nodo del cluster dal nodo appena forzato.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-129">The following example forces the AlwaysOnSrv02 node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv02"  
Stop-ClusterNode -Name $node  
Start-ClusterNode -Name $node -FixQuorum  
  
(Get-ClusterNode $node).NodeWeight = 1  
  
$nodes = Get-ClusterNode -Cluster $node  
$nodes | Format-Table -property NodeName, State, NodeWeight
```  
  
##  <a name="using-netexe"></a><a name="CommandPromptProcedure"></a><span data-ttu-id="c9bd8-130">Utilizzo di Net.exe</span><span class="sxs-lookup"><span data-stu-id="c9bd8-130">Using Net.exe</span></span>  
  
### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="c9bd8-131">Per forzare l'avvio di un cluster senza un quorum</span><span class="sxs-lookup"><span data-stu-id="c9bd8-131">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="c9bd8-132">Utilizzare Desktop remoto per connettersi al nodo del cluster desiderato per attivare la modalità online.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-132">Use Remote Desktop to connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="c9bd8-133">Avviare un prompt dei comandi con privilegi elevati tramite **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-133">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
3.  <span data-ttu-id="c9bd8-134">Utilizzare **net.exe** per assicurarsi che il servizio cluster locale sia stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-134">Use **net.exe** to make sure that the local cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="c9bd8-135">Utilizzo **net.exe** con `/forcequorum` per forzare l'avvio del servizio cluster locale.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-135">Use **net.exe** with `/forcequorum` to force the local cluster service to start.</span></span>  
  
### <a name="example-netexe"></a><span data-ttu-id="c9bd8-136">Esempio (Net.exe)</span><span class="sxs-lookup"><span data-stu-id="c9bd8-136">Example (Net.exe)</span></span>  
 <span data-ttu-id="c9bd8-137">Nell'esempio seguente viene forzato l'avvio senza un quorum del servizio cluster del nodo, viene impostato il valore `NodeWeight = 1`e viene enumerato lo stato del nodo del cluster dal nodo appena forzato.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-137">The following example forces a node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```cmd
net.exe stop clussvc  
net.exe start clussvc /forcequorum  
```  
  
##  <a name="follow-up-after-forcing-cluster-to-start-without-a-quorum"></a><a name="FollowUp"></a><span data-ttu-id="c9bd8-138">Completamento: dopo avere forzato l'avvio del cluster senza un quorum</span><span class="sxs-lookup"><span data-stu-id="c9bd8-138">Follow Up: After Forcing Cluster to Start without a Quorum</span></span>  
  
-   <span data-ttu-id="c9bd8-139">È necessario rivalutare e riconfigurare i valori NodeWeight per costruire correttamente un nuovo quorum prima di riportare online altri nodi.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-139">You must re-evaluate and reconfigure NodeWeight values to correctly construct a new quorum before bringing other nodes back online.</span></span> <span data-ttu-id="c9bd8-140">In caso contrario, è possibile che il cluster torni nuovamente offline.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-140">Otherwise, the cluster may go back offline again.</span></span>  
  
     <span data-ttu-id="c9bd8-141">Per altre informazioni, vedere [Modalità quorum WSFC e configurazione del voto &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c9bd8-141">For more information, see [WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c9bd8-142">Le procedure illustrate in questo argomento rappresentano unicamente un passaggio per riportare online il cluster WSFC in caso di un errore non previsto del quorum.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-142">The procedures in this topic are only one step in bringing the WSFC cluster back online if an un-planned quorum failure were to occur.</span></span>  <span data-ttu-id="c9bd8-143">Potrebbe anche essere necessario effettuare passaggi aggiuntivi per impedire che altri nodi del cluster WSFC interferiscano con la nuova configurazione del quorum.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-143">You may also want to take additional steps to prevent other WSFC cluster nodes from interfering with the new quorum configuration.</span></span>  
  
-   <span data-ttu-id="c9bd8-144">Anche altre funzionalità di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quali [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], mirroring del database e log shipping potrebbero richiedere azioni per recuperare i dati e ristabilire completamente la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="c9bd8-144">Other [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features such as [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], database mirroring, and log shipping may also require subsequent actions to recover data and to fully re-establish high-availability.</span></span>  
  
     <span data-ttu-id="c9bd8-145">**Per ulteriori informazioni:**</span><span class="sxs-lookup"><span data-stu-id="c9bd8-145">**For more information:**</span></span>  
  
     [<span data-ttu-id="c9bd8-146">Eseguire un failover manuale forzato di un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c9bd8-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](../../../database-engine/availability-groups/windows/perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
     [<span data-ttu-id="c9bd8-147">Utilizzo forzato del servizio in una sessione di mirroring del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c9bd8-147">Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](../../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)  
  
     [<span data-ttu-id="c9bd8-148">Failover su un database secondario per il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c9bd8-148">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](../../../database-engine/log-shipping/fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="c9bd8-149">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="c9bd8-149">Related Content</span></span>  
  
-   <span data-ttu-id="c9bd8-150">[Visualizzare eventi e log per un cluster di failover](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="c9bd8-150">[View Events and Logs for a Failover Cluster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span></span>  
  
-   [<span data-ttu-id="c9bd8-151">Pagina relativa al cluster di failover Get-ClusterLog</span><span class="sxs-lookup"><span data-stu-id="c9bd8-151">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="c9bd8-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9bd8-152">See Also</span></span>  
 <span data-ttu-id="c9bd8-153">[Ripristino di emergenza WSFC tramite quorum forzato &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9bd8-153">[WSFC Disaster Recovery through Forced Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span></span>  
 <span data-ttu-id="c9bd8-154">[Configurare le impostazioni del quorum del cluster NodeWeight](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="c9bd8-154">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="c9bd8-155">[Cmdlet del cluster di failover in Windows PowerShell elencati per attività](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c9bd8-155">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
