---
title: ALTER AVAILABILITY GROUP offline
description: Procedura per impostare il gruppo di disponibilità Always On offline
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], take offline
ms.assetid: 50f5aad8-0dff-45ef-8350-f9596d3db898
author: rothja
ms.author: jroth
ms.openlocfilehash: db2f56befe6905b9c3de6bd1ab6a2e5a4a00b1b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629583"
---
# <a name="take-an-availability-group-offline-sql-server"></a><span data-ttu-id="4450b-103">Portare un gruppo di disponibilità offline (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4450b-103">Take an Availability Group Offline (SQL Server)</span></span>
  <span data-ttu-id="4450b-104">In questo argomento viene descritto come portare un gruppo di disponibilità AlwaysOn da uno stato ONLINE a uno stato OFFLINE mediante [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="4450b-104">This topic describes how to take an AlwaysOn availability group from the ONLINE state to the OFFLINE state by using [!INCLUDE[tsql](../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="4450b-105">Non si verifica alcuna perdita di dati per i database con commit sincrono, poiché se una replica con commit sincrono non è sincronizzata, l'operazione OFFLINE genera un errore e mantiene il gruppo di disponibilità nello stato ONLINE.</span><span class="sxs-lookup"><span data-stu-id="4450b-105">There is no data loss for synchronous-commit databases because if any synchronous-commit replica is not synchronized, the OFFLINE operation raises an error and leaves the availability group ONLINE.</span></span> <span data-ttu-id="4450b-106">Mantenendo il gruppo di disponibilità online, verrà evitata una possibile perdita di dati nei database non sincronizzati con commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="4450b-106">Keeping the availability group online protects unsynchronized synchronous-commit databases from possible data loss.</span></span> <span data-ttu-id="4450b-107">Dopo aver portato un gruppo di disponibilità offline, i relativi database non saranno più disponibili per i client e non sarà possibile riportare nuovamente online il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4450b-107">After an availability group goes offline, its databases become unavailable to clients and you cannot bring the availability group back online.</span></span> <span data-ttu-id="4450b-108">Pertanto, portare un gruppo di disponibilità offline esclusivamente per eseguire la migrazione delle risorse del gruppo di disponibilità da un cluster WSFC a un altro.</span><span class="sxs-lookup"><span data-stu-id="4450b-108">Therefore, take an availability group offline only to migrate the availability group resources from one WSFC cluster to another.</span></span>  
  
 <span data-ttu-id="4450b-109">Durante la migrazione tra cluster di [!INCLUDE[ssHADR](../includes/sshadr-md.md)], se si connettono applicazioni direttamente alla replica primaria di un gruppo di disponibilità, il gruppo di disponibilità dovrà essere portato offline.</span><span class="sxs-lookup"><span data-stu-id="4450b-109">During a cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)], if any applications connect directly to the primary replica of an availability group, the availability group must be taken offline.</span></span> <span data-ttu-id="4450b-110">La migrazione tra cluster di [!INCLUDE[ssHADR](../includes/sshadr-md.md)] supporta l'aggiornamento del sistema operativo con tempi di inattività minimi dei gruppi di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4450b-110">Cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] supports OS upgrade with minimal downtime of availability groups.</span></span> <span data-ttu-id="4450b-111">Lo scenario tipico prevede l'utilizzo della migrazione tra cluster di [!INCLUDE[ssHADR](../includes/sshadr-md.md)] per l'aggiornamento del sistema operativo a [!INCLUDE[win8](../includes/win8-md.md)] o [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4450b-111">The typical scenario is to use cross-cluster migration of [!INCLUDE[ssHADR](../includes/sshadr-md.md)] for OS upgrade to [!INCLUDE[win8](../includes/win8-md.md)] or [!INCLUDE[win8srv](../includes/win8srv-md.md)].</span></span> <span data-ttu-id="4450b-112">Per ulteriori informazioni, vedere [Migrazione tra cluster di gruppi di disponibilità AlwaysOn per l'aggiornamento del sistema operativo](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="4450b-112">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4450b-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4450b-113">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4450b-114">Utilizzare l'opzione OFFLINE solo per una migrazione tra cluster di risorse di gruppi di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4450b-114">Use the OFFLINE option only for a cross-cluster migration of availability group resources.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4450b-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4450b-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="4450b-116">L'istanza del server in cui si immette il comando OFFLINE deve eseguire [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] o versioni successive (Enterprise Edition o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="4450b-116">The server instance on which you enter the OFFLINE command must be running [!INCLUDE[ssSQL11SP1](../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="4450b-117">Il gruppo di disponibilità deve essere attualmente online.</span><span class="sxs-lookup"><span data-stu-id="4450b-117">The availability group must currently be online.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4450b-118">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="4450b-118">Recommendations</span></span>  
 <span data-ttu-id="4450b-119">Prima di portare il gruppo di disponibilità offline, eliminare eventuali listener del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4450b-119">Before you take the availability group offline, delete the availability group listener or listeners.</span></span> <span data-ttu-id="4450b-120">Per altre informazioni, vedere [Rimuovere un listener del gruppo di disponibilità &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4450b-120">For more information, see [Remove an Availability Group Listener &#40;SQL Server&#41;](availability-groups/windows/remove-an-availability-group-listener-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4450b-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4450b-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4450b-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4450b-122">Permissions</span></span>  
 <span data-ttu-id="4450b-123">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4450b-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4450b-124">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4450b-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="4450b-125">**Per portare un gruppo di disponibilità offline**</span><span class="sxs-lookup"><span data-stu-id="4450b-125">**To take an availability group offline**</span></span>  
  
1.  <span data-ttu-id="4450b-126">Connettersi a un'istanza del server in cui viene ospitata una replica di disponibilità del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4450b-126">Connect to a server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="4450b-127">Può trattarsi della replica primaria o di una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="4450b-127">This replica can be the primary replica or a secondary replica.</span></span>  
  
2.  <span data-ttu-id="4450b-128">Utilizzare l'istruzione [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4450b-128">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="4450b-129">ALTER AVAILABILITY GROUP *nome_gruppo* OFFLINE</span><span class="sxs-lookup"><span data-stu-id="4450b-129">ALTER AVAILABILITY GROUP *group_name* OFFLINE</span></span>  
  
     <span data-ttu-id="4450b-130">dove *nome_gruppo* è il nome del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="4450b-130">where *group_name* is the name of the availability group.</span></span>  
  
### <a name="example"></a><span data-ttu-id="4450b-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="4450b-131">Example</span></span>  
 <span data-ttu-id="4450b-132">Nell'esempio seguente il gruppo di disponibilità `AccountsAG` viene portato offline.</span><span class="sxs-lookup"><span data-stu-id="4450b-132">The following example takes the `AccountsAG` availability group offline.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AccountsAG OFFLINE;  
```  
  
##  <a name="follow-up-after-the-availability-group-goes-offline"></a><a name="FollowUp"></a> <span data-ttu-id="4450b-133">Completamento: Dopo aver portato il gruppo di disponibilità offline</span><span class="sxs-lookup"><span data-stu-id="4450b-133">Follow Up: After the Availability Group Goes Offline</span></span>  
  
-   <span data-ttu-id="4450b-134">**Registrazione dell'operazione OFFLINE:**  l'identità del nodo WSFC in cui è stata avviata l'operazione OFFLINE è archiviata nel log del cluster WSFC e in SQL ERRORLOG.</span><span class="sxs-lookup"><span data-stu-id="4450b-134">**Logging of OFFLINE operation:**  The identity of the WSFC node where the OFFLINE operation was initiated is stored in both the WSFC cluster log and the SQL ERRORLOG.</span></span>  
  
-   <span data-ttu-id="4450b-135">**Se non è stato eliminato il listener del gruppo di disponibilità prima di portare offline il gruppo:**  se si esegue la migrazione del gruppo di disponibilità a un altro cluster WSFC, eliminare il nome di rete virtuale e l'indirizzo VIP del listener.</span><span class="sxs-lookup"><span data-stu-id="4450b-135">**If you did not delete the availability group listener before taking the group offline:**  If you are migrating the availability group to another WSFC cluster, delete the VNN and VIP of the listener.</span></span> <span data-ttu-id="4450b-136">È possibile eliminarli tramite la console Gestione cluster di failover, il cmdlet [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) di PowerShell o [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="4450b-136">You can delete them by using either the Failover Cluster Management console, the [Remove-ClusterResource](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx) PowerShell cmdlet, or [cluster.exe](https://technet.microsoft.com/library/ee461015\(WS.10\).aspx).</span></span> <span data-ttu-id="4450b-137">Cluster.exe è deprecato in Windows 8.</span><span class="sxs-lookup"><span data-stu-id="4450b-137">Note that cluster.exe is deprecated on Windows 8.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4450b-138">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4450b-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4450b-139">Rimuovere un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4450b-139">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](availability-groups/windows/remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="4450b-140">Modificare il contesto del cluster HADR dell'istanza del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4450b-140">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](availability-groups/windows/change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="4450b-141">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="4450b-141">Related Content</span></span>  
  
-   <span data-ttu-id="4450b-142">[Articoli tecnici su SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4450b-142">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="4450b-143">Blog del team di SQL Server AlwaysOn: Blog del team ufficiale di SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="4450b-143">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
## <a name="see-also"></a><span data-ttu-id="4450b-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4450b-144">See Also</span></span>  
 [<span data-ttu-id="4450b-145">Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4450b-145">AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/always-on-availability-groups-sql-server.md)  
