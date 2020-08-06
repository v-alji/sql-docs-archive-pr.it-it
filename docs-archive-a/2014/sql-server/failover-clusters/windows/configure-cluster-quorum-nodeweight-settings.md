---
title: Configurare le impostazioni NodeWeight per il quorum del cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: cb3fd9a6-39a2-4e9c-9157-619bf3db9951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e469d5fc0fc030304a7cf2f1bdd894eb578aa056
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628277"
---
# <a name="configure-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="29e82-102">Configurare le impostazioni NodeWeight per il quorum del cluster</span><span class="sxs-lookup"><span data-stu-id="29e82-102">Configure Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="29e82-103">In questo argomento viene illustrato come configurare le impostazioni NodeWeight per un nodo membro di un cluster WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="29e82-103">This topic describes how to configure NodeWeight settings for a member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="29e82-104">Le impostazioni NodeWeight vengono utilizzate durante la votazione quorum per supportare scenari di ripristino di emergenza e multi-subnet per istanze del cluster di failover di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29e82-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="29e82-105">**Prima di iniziare:**  [Prerequisiti](#Prerequisites), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="29e82-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="29e82-106">**Per visualizzare le impostazioni NodeWeight per il quorum:** [Uso di Powershell](#PowerShellProcedure), [Uso di Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="29e82-106">**To view quorum NodeWeight settings using:** [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
-   [<span data-ttu-id="29e82-107">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="29e82-107">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="29e82-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="29e82-108">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="29e82-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="29e82-109">Prerequisites</span></span>  
 <span data-ttu-id="29e82-110">Questa caratteristica è supportata solo in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="29e82-110">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="29e82-111">Per utilizzare le impostazioni NodeWeight, è necessario applicare l'aggiornamento rapido seguente a tutti i server del cluster WSFC:</span><span class="sxs-lookup"><span data-stu-id="29e82-111">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="29e82-112">[KB2494036](https://support.microsoft.com/kb/2494036): è disponibile un aggiornamento rapido per configurare un nodo del cluster che non presenta voti quorum in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] e in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29e82-112">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="29e82-113">Se questo aggiornamento rapido non viene installato, gli esempi in questo argomento restituiranno valori vuoti o NULL per NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="29e82-113">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="29e82-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="29e82-114">Security</span></span>  
 <span data-ttu-id="29e82-115">L'utente deve disporre di un account di dominio che sia membro del gruppo Administrators locale su ogni nodo del cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="29e82-115">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="29e82-116">Utilizzo di Powershell</span><span class="sxs-lookup"><span data-stu-id="29e82-116">Using Powershell</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="29e82-117">Per configurare le impostazioni NodeWeight</span><span class="sxs-lookup"><span data-stu-id="29e82-117">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="29e82-118">Avviare Windows PowerShell con privilegi elevati tramite **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="29e82-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="29e82-119">Importare il modulo `FailoverClusters` per abilitare i commandlet del cluster.</span><span class="sxs-lookup"><span data-stu-id="29e82-119">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="29e82-120">Utilizzare l'oggetto `Get-ClusterNode` per impostare la proprietà `NodeWeight` per ogni nodo nel cluster.</span><span class="sxs-lookup"><span data-stu-id="29e82-120">Use the `Get-ClusterNode` object to set the `NodeWeight` property for each node in the cluster.</span></span>  
  
4.  <span data-ttu-id="29e82-121">Restituire le proprietà del nodo del cluster in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="29e82-121">Output the cluster node properties in a readable format.</span></span>  
  
 <span data-ttu-id="29e82-122">Nell'esempio seguente viene modificata l'impostazione NodeWeight per rimuovere il voto quorum per il nodo "AlwaysOnSrv1" e quindi vengono restituite le impostazioni per tutti i nodi del cluster.</span><span class="sxs-lookup"><span data-stu-id="29e82-122">The following example changes the NodeWeight setting to remove the quorum vote for the "AlwaysOnSrv1" node, and then outputs the settings for all nodes in the cluster.</span></span>
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv1"  
(Get-ClusterNode $node).NodeWeight = 0  
  
$cluster = (Get-ClusterNode $node).Cluster  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="29e82-123">Utilizzo di Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="29e82-123">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29e82-124">L'utilità cluster.exe è deprecata nella versione [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29e82-124">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="29e82-125">Utilizzare PowerShell con il clustering di failover per lo sviluppo futuro.</span><span class="sxs-lookup"><span data-stu-id="29e82-125">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="29e82-126">L'utilità cluster.exe verrà rimossa nella versione successiva di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="29e82-126">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="29e82-127">Per altre informazioni, vedere [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx)(Mapping di comandi Cluster.exe a cmdlet di Windows PowerShell per i cluster di failover).</span><span class="sxs-lookup"><span data-stu-id="29e82-127">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="29e82-128">Per configurare le impostazioni NodeWeight</span><span class="sxs-lookup"><span data-stu-id="29e82-128">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="29e82-129">Avviare un prompt dei comandi con privilegi elevati tramite **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="29e82-129">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="29e82-130">Utilizzare **cluster.exe** per impostare valori `NodeWeight` .</span><span class="sxs-lookup"><span data-stu-id="29e82-130">Use **cluster.exe** to set `NodeWeight` values.</span></span>  

 <span data-ttu-id="29e82-131">Nell'esempio seguente viene modificato il valore NodeWeight per rimuovere il voto quorum del nodo "AlwaysOnSrv1" nel cluster "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="29e82-131">The following example changes the NodeWeight value to remove the quorum vote of the "AlwaysOnSrv1" node in the "Cluster001" cluster.</span></span>  
  
```cmd
cluster.exe Cluster001 node AlwaysOnSrv1 /prop NodeWeight=0  
```  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="29e82-132">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="29e82-132">Related Content</span></span>  
  
-   <span data-ttu-id="29e82-133">[Visualizzare eventi e log per un cluster di failover](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="29e82-133">[View Events and Logs for a Failover Cluster](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="29e82-134">Pagina relativa al cluster di failover Get-ClusterLog</span><span class="sxs-lookup"><span data-stu-id="29e82-134">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="29e82-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29e82-135">See Also</span></span>  
 <span data-ttu-id="29e82-136">[Modalità quorum WSFC e configurazione del voto &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="29e82-136">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="29e82-137">[Visualizzare le impostazioni del quorum del cluster NodeWeight](view-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="29e82-137">[View Cluster Quorum NodeWeight Settings](view-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="29e82-138">[Cmdlet del cluster di failover in Windows PowerShell elencati per attività](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="29e82-138">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
