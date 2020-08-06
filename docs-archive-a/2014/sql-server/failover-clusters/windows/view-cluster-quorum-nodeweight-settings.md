---
title: Visualizzare le impostazioni NodeWeight per il quorum del cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: b845e73a-bb01-4de2-aac2-8ac12abebc95
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef2176d4916e8affbb9ef89c9b26499289c520ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628262"
---
# <a name="view-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="c0be9-102">Visualizzare le impostazioni NodeWeight per il quorum del cluster</span><span class="sxs-lookup"><span data-stu-id="c0be9-102">View Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="c0be9-103">In questo argomento viene illustrato come visualizzare le impostazioni NodeWeight per ogni nodo membro di un cluster WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="c0be9-103">This topic describes how to view NodeWeight settings for each member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="c0be9-104">Le impostazioni NodeWeight vengono utilizzate durante la votazione quorum per supportare scenari di ripristino di emergenza e multi-subnet per istanze del cluster di failover di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0be9-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="c0be9-105">**Prima di iniziare:**  [Prerequisiti](#Prerequisites), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="c0be9-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="c0be9-106">**Per visualizzare le impostazioni NodeWeight per il quorum:** [Uso di Transact-SQL](#TsqlProcedure), [Uso di Powershell](#PowerShellProcedure), [Uso di Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="c0be9-106">**To view quorum NodeWeight settings using:** [Using Transact-SQL](#TsqlProcedure), [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c0be9-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c0be9-107">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c0be9-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c0be9-108">Prerequisites</span></span>  
 <span data-ttu-id="c0be9-109">Questa caratteristica è supportata solo in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c0be9-109">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c0be9-110">Per utilizzare le impostazioni NodeWeight, è necessario applicare l'aggiornamento rapido seguente a tutti i server del cluster WSFC:</span><span class="sxs-lookup"><span data-stu-id="c0be9-110">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="c0be9-111">[KB2494036](https://support.microsoft.com/kb/2494036): è disponibile un aggiornamento rapido per configurare un nodo del cluster che non presenta voti quorum in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] e in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0be9-111">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="c0be9-112">Se questo aggiornamento rapido non viene installato, gli esempi in questo argomento restituiranno valori vuoti o NULL per NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="c0be9-112">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c0be9-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c0be9-113">Security</span></span>  
 <span data-ttu-id="c0be9-114">L'utente deve disporre di un account di dominio che sia membro del gruppo Administrators locale su ogni nodo del cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="c0be9-114">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c0be9-115">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0be9-115">Using Transact-SQL</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="c0be9-116">Per visualizzare le impostazioni NodeWeight</span><span class="sxs-lookup"><span data-stu-id="c0be9-116">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="c0be9-117">Connettersi a qualsiasi istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel cluster.</span><span class="sxs-lookup"><span data-stu-id="c0be9-117">Connect to any [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the cluster.</span></span>  
  
2.  <span data-ttu-id="c0be9-118">Eseguire una query sulla vista [sys].[dm_hadr_cluster_members].</span><span class="sxs-lookup"><span data-stu-id="c0be9-118">Query the [sys].[dm_hadr_cluster_members] view.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="c0be9-119">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c0be9-119">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="c0be9-120">Nell'esempio seguente viene eseguita una query su una vista di sistema affinché vengano restituiti valori per tutti i nodi del cluster dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="c0be9-120">The following example queries a system view to return values for all of the nodes in that instance's cluster.</span></span>  
  
```sql  
SELECT  member_name, member_state_desc, number_of_quorum_votes  
 FROM   sys.dm_hadr_cluster_members;  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="c0be9-121">Utilizzo di Powershell</span><span class="sxs-lookup"><span data-stu-id="c0be9-121">Using Powershell</span></span>  
  
### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="c0be9-122">Per visualizzare le impostazioni NodeWeight</span><span class="sxs-lookup"><span data-stu-id="c0be9-122">To view NodeWeight settings</span></span>
  
1.  <span data-ttu-id="c0be9-123">Avviare Windows PowerShell con privilegi elevati tramite **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c0be9-123">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="c0be9-124">Importare il modulo `FailoverClusters` per abilitare i commandlet del cluster.</span><span class="sxs-lookup"><span data-stu-id="c0be9-124">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="c0be9-125">Utilizzare l'oggetto `Get-ClusterNode` per restituire una raccolta di oggetti del nodo del cluster.</span><span class="sxs-lookup"><span data-stu-id="c0be9-125">Use the `Get-ClusterNode` object to return a collection of cluster node objects.</span></span>  
  
4.  <span data-ttu-id="c0be9-126">Restituire le proprietà del nodo del cluster in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="c0be9-126">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="c0be9-127">Esempio (Powershell)</span><span class="sxs-lookup"><span data-stu-id="c0be9-127">Example (Powershell)</span></span>  
 <span data-ttu-id="c0be9-128">Nell'esempio seguente vengono restituite alcune delle proprietà del nodo per il cluster denominato "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="c0be9-128">The following example output some of the node properties for the cluster called "Cluster001".</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$cluster = "Cluster001"  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -Property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="c0be9-129">Utilizzo di Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="c0be9-129">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0be9-130">L'utilità cluster.exe è deprecata nella versione [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0be9-130">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="c0be9-131">Utilizzare PowerShell con il clustering di failover per lo sviluppo futuro.</span><span class="sxs-lookup"><span data-stu-id="c0be9-131">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="c0be9-132">L'utilità cluster.exe verrà rimossa nella versione successiva di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c0be9-132">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="c0be9-133">Per altre informazioni, vedere [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx)(Mapping di comandi Cluster.exe a cmdlet di Windows PowerShell per i cluster di failover).</span><span class="sxs-lookup"><span data-stu-id="c0be9-133">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="c0be9-134">Per visualizzare le impostazioni NodeWeight</span><span class="sxs-lookup"><span data-stu-id="c0be9-134">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="c0be9-135">Avviare un prompt dei comandi con privilegi elevati tramite **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c0be9-135">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="c0be9-136">Utilizzare **cluster.exe** per restituire lo stato del nodo e i valori NodeWeight</span><span class="sxs-lookup"><span data-stu-id="c0be9-136">Use **cluster.exe** to return node status and NodeWeight values</span></span>  
  
### <a name="example-clusterexe"></a><span data-ttu-id="c0be9-137">Esempio (Cluster.exe)</span><span class="sxs-lookup"><span data-stu-id="c0be9-137">Example (Cluster.exe)</span></span>  
 <span data-ttu-id="c0be9-138">Nell'esempio seguente vengono restituite alcune delle proprietà del nodo per il cluster denominato "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="c0be9-138">The following example outputs some of the node properties for the cluster called "Cluster001".</span></span>  
  
```cmd
cluster.exe Cluster001 node /status /properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0be9-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0be9-139">See Also</span></span>  
 <span data-ttu-id="c0be9-140">[Modalità quorum WSFC e configurazione del voto &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c0be9-140">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="c0be9-141">[Configurare le impostazioni NodeWeight per il quorum del cluster](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="c0be9-141">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="c0be9-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0be9-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span></span>  
 <span data-ttu-id="c0be9-143">[Cmdlet del cluster di failover in Windows PowerShell elencati per attività](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c0be9-143">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
