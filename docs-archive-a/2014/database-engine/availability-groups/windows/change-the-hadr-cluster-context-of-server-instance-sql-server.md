---
title: Modificare il contesto del cluster HADR dell'istanza del server (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- Availability replicas [SQL Server], change WSFC cluster context
ms.assetid: ecd99f91-b9a2-4737-994e-507065a12f80
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbc29fa2ebaaf2bbc9e577b5bd303e8a0dd0ec4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724996"
---
# <a name="change-the-hadr-cluster-context-of-server-instance-sql-server"></a><span data-ttu-id="06199-102">Modificare il contesto del cluster HADR dell'istanza del server (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="06199-102">Change the HADR Cluster Context of Server Instance (SQL Server)</span></span>
  <span data-ttu-id="06199-103">In questo argomento viene descritto come cambiare il contesto del cluster HADR di un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="06199-103">This topic describes how to switch the HADR cluster context of an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] and later versions.</span></span> <span data-ttu-id="06199-104">Il *contesto del cluster HADR* determina il cluster WSFC (Windows Server Failover Clustering) che gestisce i metadati per le repliche di disponibilità ospitate dall'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="06199-104">The *HADR cluster context* determines which Windows Server Failover Clustering (WSFC) cluster manages the metadata for availability replicas hosted by the server instance.</span></span>  
  
 <span data-ttu-id="06199-105">Cambiare il contesto del cluster HADR solo durante una migrazione tra cluster di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] a un'istanza di [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] in un nuovo cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="06199-105">Switch the HADR cluster context only during a cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] to an instance of [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] on a new WSFC cluster.</span></span> <span data-ttu-id="06199-106">La migrazione tra cluster di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] supporta l'aggiornamento del sistema operativo a [!INCLUDE[win8](../../../includes/win8-md.md)] o a [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] con tempi di inattività minimi dei gruppi di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="06199-106">Cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] supports OS upgrade to [!INCLUDE[win8](../../../includes/win8-md.md)] or [!INCLUDE[win8srv](../../../includes/win8srv-md.md)] with minimal downtime of availability groups.</span></span> <span data-ttu-id="06199-107">Per ulteriori informazioni, vedere [Migrazione tra cluster di gruppi di disponibilità AlwaysOn per l'aggiornamento del sistema operativo](https://msdn.microsoft.com/library/jj873730.aspx).</span><span class="sxs-lookup"><span data-stu-id="06199-107">For more information, see [Cross-Cluster Migration of AlwaysOn Availability Groups for OS Upgrade](https://msdn.microsoft.com/library/jj873730.aspx).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="06199-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="06199-108">Before You Begin</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="06199-109">Cambiare il contesto del cluster HADR solo durante la migrazione tra cluster di distribuzioni [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="06199-109">Switch the HADR cluster context only during cross-cluster migration of [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] deployments.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="06199-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="06199-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="06199-111">È possibile cambiare il contesto del cluster HADR solo dal cluster WSFC locale a un cluster remoto e quindi nuovamente dal cluster remoto al cluster locale.</span><span class="sxs-lookup"><span data-stu-id="06199-111">You can switch the HADR cluster context only from the local WSFC cluster to a remote cluster and then back from the remote cluster to the local cluster.</span></span> <span data-ttu-id="06199-112">Non è possibile cambiare il contesto del cluster HADR da un cluster remoto a un altro cluster remoto.</span><span class="sxs-lookup"><span data-stu-id="06199-112">You cannot switch the HADR cluster context from one remote cluster to another remote cluster.</span></span>  
  
-   <span data-ttu-id="06199-113">È possibile cambiare il contesto del cluster HADR in un cluster remoto solo se l'istanza di SQL Server non ospita alcuna replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="06199-113">The HADR cluster context can be switched to a remote cluster only when the instance of SQL Server is not hosting any availability replicas.</span></span>  
  
-   <span data-ttu-id="06199-114">Il contesto di un cluster HADR remoto può essere nuovamente cambiato nel cluster locale in qualsiasi momento,</span><span class="sxs-lookup"><span data-stu-id="06199-114">A remote HADR cluster context can be switched back to the local cluster at any time.</span></span> <span data-ttu-id="06199-115">a meno che l'istanza del server non ospiti una replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="06199-115">However, the context cannot be switched again as long as the server instance is hosting any availability replicas.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="06199-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="06199-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="06199-117">L'istanza del server in cui si cambia il contesto del cluster HADR deve eseguire [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] o versioni successive (Enterprise Edition o versioni successive).</span><span class="sxs-lookup"><span data-stu-id="06199-117">The server instance on which you change the HADR cluster context must be running [!INCLUDE[ssSQL11SP1](../../../includes/sssql11sp1-md.md)] or above (Enterprise edition or above).</span></span>  
  
-   <span data-ttu-id="06199-118">L'istanza del server deve essere abilitata per AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="06199-118">The server instance must be enabled for AlwaysOn.</span></span> <span data-ttu-id="06199-119">Per altre informazioni, vedere [Abilitare e disabilitare la funzionalità Gruppi di disponibilità Always On &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="06199-119">For more information, see [Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](enable-and-disable-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="06199-120">Affinché possa essere cambiata dal contesto del cluster locale in un cluster remoto, un'istanza del server non può ospitare repliche di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="06199-120">To be eligible to be switched from the local cluster context to a remote cluster cluster, a server instance cannot be hosting any availability replicas.</span></span> <span data-ttu-id="06199-121">La vista del catalogo [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) non deve restituire righe.</span><span class="sxs-lookup"><span data-stu-id="06199-121">The [sys.availability_replicas](/sql/relational-databases/system-catalog-views/sys-availability-replicas-transact-sql) catalog view should not return any rows.</span></span>  
  
     <span data-ttu-id="06199-122">Se nell'istanza del server sono presenti repliche di disponibilità, prima di poter cambiare il contesto del cluster HADR è necessario eseguire una delle operazioni indicate di seguito:</span><span class="sxs-lookup"><span data-stu-id="06199-122">If any availability replicas exist on the server instance, before you can change the HADR cluster context, you must do one of the following:</span></span>  
  
    |<span data-ttu-id="06199-123">Ruolo della replica</span><span class="sxs-lookup"><span data-stu-id="06199-123">Replica Role</span></span>|<span data-ttu-id="06199-124">Azione</span><span class="sxs-lookup"><span data-stu-id="06199-124">Action</span></span>|<span data-ttu-id="06199-125">Collegamento</span><span class="sxs-lookup"><span data-stu-id="06199-125">Link</span></span>|  
    |------------------|------------|----------|  
    |<span data-ttu-id="06199-126">Primaria</span><span class="sxs-lookup"><span data-stu-id="06199-126">Primary</span></span>|<span data-ttu-id="06199-127">Gruppo di disponibilità offline.</span><span class="sxs-lookup"><span data-stu-id="06199-127">Take the availability group offline.</span></span>|[<span data-ttu-id="06199-128">Portare un gruppo di disponibilità offline &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-128">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)|  
    |<span data-ttu-id="06199-129">Secondari</span><span class="sxs-lookup"><span data-stu-id="06199-129">Secondary</span></span>|<span data-ttu-id="06199-130">Rimozione della replica dal gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="06199-130">Remove the replica from its availability group</span></span>|[<span data-ttu-id="06199-131">Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-131">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)|  
  
-   <span data-ttu-id="06199-132">Prima di poter passare da un cluster remoto al cluster locale, tutte le repliche con commit sincrono devono essere di tipo SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="06199-132">Before you can switch from a remote cluster to the local cluster, all synchronous-commit replicas must be SYNCHRONIZED.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="06199-133">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="06199-133">Recommendations</span></span>  
  
-   <span data-ttu-id="06199-134">È consigliabile specificare il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="06199-134">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="06199-135">Ciò è dovuto al fatto che, per individuare l'indirizzo IP di destinazione di un nome breve, ALTER SERVER CONFIGURATION utilizza la risoluzione DNS.</span><span class="sxs-lookup"><span data-stu-id="06199-135">This is because to find the target IP address of a short name, ALTER SERVER CONFIGURATION uses DNS resolution.</span></span> <span data-ttu-id="06199-136">In alcuni casi, a seconda dell'ordine di ricerca DNS, l'utilizzo di un nome breve potrebbe creare confusione.</span><span class="sxs-lookup"><span data-stu-id="06199-136">Under some situations, depending on the DNS searching order, using a short name could cause confusion.</span></span> <span data-ttu-id="06199-137">Si consideri, ad esempio, il comando indicato di seguito, eseguito in un nodo nel dominio `abc` (`node1.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="06199-137">For example, consider the following command, which is executed on a node in the `abc` domain, (`node1.abc.com`).</span></span> <span data-ttu-id="06199-138">Il cluster di destinazione desiderato è il cluster `CLUS01` nel dominio `xyz` (`clus01.xyz.com`).</span><span class="sxs-lookup"><span data-stu-id="06199-138">The intended destination cluster is the `CLUS01` cluster in the `xyz` domain (`clus01.xyz.com`).</span></span> <span data-ttu-id="06199-139">Tuttavia, gli host di dominio locali ospitano anche un cluster denominato `CLUS01` (`clus01.abc.com`).</span><span class="sxs-lookup"><span data-stu-id="06199-139">However, the local  domain hosts also hosts a cluster named `CLUS01` (`clus01.abc.com`).</span></span>  
  
     <span data-ttu-id="06199-140">Se è stato specificato il nome breve del cluster di destinazione, `CLUS01`, la risoluzione dei nomi DNS potrebbe restituire l'indirizzo IP del cluster errato, `clus01.abc.com`.</span><span class="sxs-lookup"><span data-stu-id="06199-140">If the short name of the target cluster, `CLUS01`, were specified, DNS name resolution could return the IP address of the wrong cluster, `clus01.abc.com`.</span></span> <span data-ttu-id="06199-141">Per evitare di creare confusione, specificare il nome completo del cluster di destinazione, come nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="06199-141">To avoid such confusion, specify the full name of the target cluster, as in the following example:</span></span>  
  
    ```  
    ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com'  
    ```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="06199-142">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="06199-142">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="06199-143">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="06199-143">Permissions</span></span>  
  
-   <span data-ttu-id="06199-144">**Accesso SQL Server**</span><span class="sxs-lookup"><span data-stu-id="06199-144">**SQL Server login**</span></span>  
  
     <span data-ttu-id="06199-145">È richiesta l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="06199-145">Requires CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="06199-146">**Account del servizio SQL Server**</span><span class="sxs-lookup"><span data-stu-id="06199-146">**SQL Server service account**</span></span>  
  
     <span data-ttu-id="06199-147">L'account di servizio di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dell'istanza del server deve disporre degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="06199-147">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account of the server instance must have:</span></span>  
  
    -   <span data-ttu-id="06199-148">Autorizzazione per aprire il cluster WSFC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="06199-148">Permission to open the destination WSFC cluster.</span></span>  
  
    -   <span data-ttu-id="06199-149">Accesso remoto a WSFC in lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="06199-149">Remote WSFC read-write access.</span></span>  
  
 
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="06199-150">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="06199-150">Using Transact-SQL</span></span>  
 <span data-ttu-id="06199-151">**Per modificare il contesto del cluster WSFC di una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="06199-151">**To change the WSFC cluster context of an availability replica**</span></span>  
  
1.  <span data-ttu-id="06199-152">Connettersi all'istanza del server che ospita la replica primaria o una replica secondaria del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="06199-152">Connect to the server instance that hosts either the primary replica or a secondary replica of the availability group.</span></span>  
  
2.  <span data-ttu-id="06199-153">Usare la clausola SET HADR CLUSTER CONTEXT dell'istruzione [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) , come segue:</span><span class="sxs-lookup"><span data-stu-id="06199-153">Use the SET HADR CLUSTER CONTEXT clause of the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="06199-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **' *`windows_cluster`* '** | LOCALE</span><span class="sxs-lookup"><span data-stu-id="06199-154">ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT **=** { **'*`windows_cluster`*'** | LOCAL }</span></span>  
  
     <span data-ttu-id="06199-155">dove</span><span class="sxs-lookup"><span data-stu-id="06199-155">where,</span></span>  
  
     <span data-ttu-id="06199-156">*windows_cluster*</span><span class="sxs-lookup"><span data-stu-id="06199-156">*windows_cluster*</span></span>  
     <span data-ttu-id="06199-157">Nome dell'oggetto cluster (CON) di un cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="06199-157">The cluster object name (CON) of a WSFC cluster.</span></span> <span data-ttu-id="06199-158">È possibile specificare il nome breve o il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="06199-158">You can specify either the short name or the full domain name.</span></span> <span data-ttu-id="06199-159">È consigliabile specificare il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="06199-159">We recommend that you specify the full domain name.</span></span> <span data-ttu-id="06199-160">Per ulteriori informazioni, vedere [raccomandazioni](#Recommendations), più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="06199-160">For more information, see [Recommendations](#Recommendations), earlier in this topic.</span></span>  
  
     <span data-ttu-id="06199-161">LOCAL</span><span class="sxs-lookup"><span data-stu-id="06199-161">LOCAL</span></span>  
     <span data-ttu-id="06199-162">Cluster WSFC locale.</span><span class="sxs-lookup"><span data-stu-id="06199-162">The local WSFC cluster.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="06199-163">Esempi</span><span class="sxs-lookup"><span data-stu-id="06199-163">Examples</span></span>  
 <span data-ttu-id="06199-164">Nell'esempio seguente il contesto del cluster HADR viene cambiato in un cluster diverso.</span><span class="sxs-lookup"><span data-stu-id="06199-164">The following example changes the HADR cluster context to a different cluster.</span></span> <span data-ttu-id="06199-165">Per identificare il cluster WSFC di destinazione, `clus01`, nell'esempio viene specificato il nome completo dell'oggetto cluster, `clus01.xyz.com`.</span><span class="sxs-lookup"><span data-stu-id="06199-165">To identify the destination WSFC cluster, `clus01`, the example specifies the full cluster object name, `clus01.xyz.com`.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com';  
```  
  
 <span data-ttu-id="06199-166">Nell'esempio seguente il contesto del cluster HADR viene cambiato in un cluster WSFC locale.</span><span class="sxs-lookup"><span data-stu-id="06199-166">The following example changes the HADR cluster context to the local WSFC cluster.</span></span>  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = LOCAL;  
```  
  

  
##  <a name="follow-up-after-switching-the-cluster-context-of-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="06199-167">Completamento: dopo aver cambiato il contesto del cluster di una replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="06199-167">Follow Up: After Switching the Cluster Context of an Availability Replica</span></span>  
 <span data-ttu-id="06199-168">Il nuovo contesto del cluster HADR diviene effettivo immediatamente e non richiede il riavvio dell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="06199-168">The new HADR cluster context takes effect immediately, without restarting the server instance.</span></span> <span data-ttu-id="06199-169">L'impostazione del contesto del cluster HADR è di tipo persistente a livello di istanza e rimane invariata in caso di riavvio dell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="06199-169">The HADR cluster context setting is a persistent instance-level setting that remains unchanged if the server instance restarts.</span></span>  
  
 <span data-ttu-id="06199-170">Confermare il nuovo contesto del cluster HADR eseguendo una query sulla vista a gestione dinamica (DMV) [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) , come segue:</span><span class="sxs-lookup"><span data-stu-id="06199-170">Confirm the new HADR cluster context by querying the [sys.dm_hadr_cluster](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-transact-sql) dynamic management view, as follows:</span></span>  
  
```  
SELECT cluster_name FROM sys.dm_hadr_cluster  
```  
  
 <span data-ttu-id="06199-171">Questa query deve restituire il nome del cluster in cui impostare il contesto del cluster HADR.</span><span class="sxs-lookup"><span data-stu-id="06199-171">This query should return the name of the cluster to which you set the HADR cluster context.</span></span>  
  
 <span data-ttu-id="06199-172">Se il contesto del cluster HADR viene cambiato in un nuovo cluster:</span><span class="sxs-lookup"><span data-stu-id="06199-172">When the HADR cluster context is switched to a new cluster:</span></span>  
  
-   <span data-ttu-id="06199-173">I metadati vengono puliti per qualsiasi replica di disponibilità ospitata dall'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06199-173">The metadata is cleaned up for any availability replicas that are currently hosted by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="06199-174">Tutti i database appartenenti a una replica di disponibilità si trovano ora in uno stato RESTORING.</span><span class="sxs-lookup"><span data-stu-id="06199-174">All the databases that previously belonged to an availability replica are now in the RESTORING state.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="06199-175">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="06199-175">Related Tasks</span></span>  
  
-   [<span data-ttu-id="06199-176">Rimuovere un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-176">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="06199-177">Portare un gruppo di disponibilità offline &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-177">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
-   [<span data-ttu-id="06199-178">Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-178">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="06199-179">Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-179">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="06199-180">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-180">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="06199-181">Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-181">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
 
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="06199-182">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="06199-182">Related Content</span></span>  
  
-   <span data-ttu-id="06199-183">[Articoli tecnici su SQL Server 2012](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="06199-183">[SQL Server 2012 Technical Articles](https://msdn.microsoft.com/library/bb418445\(SQL.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="06199-184">Blog del team di SQL Server AlwaysOn: Blog del team ufficiale di SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="06199-184">SQL Server AlwaysOn Team Blog: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
  
  
## <a name="see-also"></a><span data-ttu-id="06199-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06199-185">See Also</span></span>  
 <span data-ttu-id="06199-186">[Gruppi di disponibilità AlwaysOn (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server Failover Clustering &#40;WSFC&#41; con SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="06199-186">[AlwaysOn Availability Groups (SQL Server)](always-on-availability-groups-sql-server.md) [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md) </span></span>  
 [<span data-ttu-id="06199-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="06199-187">ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-server-configuration-transact-sql)  
  
  
