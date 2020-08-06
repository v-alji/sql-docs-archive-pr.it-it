---
title: Visualizzare le proprietà del listener del gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistenerproperties.general.f1
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
ms.assetid: aca0d016-3228-40b8-bdc3-285ed6d9b280
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7fe316394a030350ceb12a0d1b8e2d48ee1d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624361"
---
# <a name="view-availability-group-listener-properties-sql-server"></a><span data-ttu-id="d74f7-102">Visualizzare le proprietà del listener del gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d74f7-102">View Availability Group Listener Properties (SQL Server)</span></span>
  <span data-ttu-id="d74f7-103">In questo argomento viene illustrato come visualizzare le proprietà di un *listener del gruppo di disponibilità* AlwaysOn tramite [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d74f7-103">This topic describes how to view the properties of an AlwaysOn *availability group listener* by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="d74f7-104">**Per visualizzare le proprietà del listener utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="d74f7-104">**To view listener properties, using:**</span></span>  
  
     [<span data-ttu-id="d74f7-105">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d74f7-105">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d74f7-106">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d74f7-106">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d74f7-107">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d74f7-107">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d74f7-108">**Per visualizzare le proprietà del listener**</span><span class="sxs-lookup"><span data-stu-id="d74f7-108">**To view listener properties**</span></span>  
  
1.  <span data-ttu-id="d74f7-109">In Esplora oggetti connettersi a un'istanza del server che ospita una replica di disponibilità del gruppo di disponibilità di cui si desidera visualizzare il listener.</span><span class="sxs-lookup"><span data-stu-id="d74f7-109">In Object Explorer, connect to a server instance that hosts any availability replica of the availability group whose listener you want to view.</span></span> <span data-ttu-id="d74f7-110">Fare clic sul nome del server per espandere il relativo albero.</span><span class="sxs-lookup"><span data-stu-id="d74f7-110">Click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d74f7-111">Espandere il nodo **Disponibilità elevata AlwaysOn** e il nodo **Gruppi di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="d74f7-111">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="d74f7-112">Espandere il nodo del gruppo di disponibilità ed espandere il nodo **Listener gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="d74f7-112">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="d74f7-113">Fare clic con il pulsante destro del mouse sul listener da visualizzare e scegliere il comando **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="d74f7-113">Right-click the listener that you want to view, and select the **Properties** command.</span></span>  
  
5.  <span data-ttu-id="d74f7-114">Verrà aperta la finestra di dialogo **Proprietà listener gruppo di disponibilità** .</span><span class="sxs-lookup"><span data-stu-id="d74f7-114">This opens the **Availability Group Listener Properties** dialog box.</span></span> <span data-ttu-id="d74f7-115">Per altre informazioni, vedere [Proprietà listener gruppo di disponibilità (finestra di dialogo)](#AgListenerPropertiesDialog), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d74f7-115">For more information, see [Availability Group Listener Properties (Dialog Box)](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="availability-group-listener-properties-dialog-box"></a><a name="AgListenerPropertiesDialog"></a> <span data-ttu-id="d74f7-116">Proprietà listener gruppo di disponibilità (finestra di dialogo)</span><span class="sxs-lookup"><span data-stu-id="d74f7-116">Availability Group Listener Properties (Dialog Box)</span></span>  
 <span data-ttu-id="d74f7-117">**Nome DNS del listener**</span><span class="sxs-lookup"><span data-stu-id="d74f7-117">**Listener DNS Name**</span></span>  
 <span data-ttu-id="d74f7-118">Nome di rete del listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="d74f7-118">The network name of the availability group listener.</span></span>  
  
 <span data-ttu-id="d74f7-119">**Porta**</span><span class="sxs-lookup"><span data-stu-id="d74f7-119">**Port**</span></span>  
 <span data-ttu-id="d74f7-120">Porta TCP usata dal listener.</span><span class="sxs-lookup"><span data-stu-id="d74f7-120">The TCP port used by this listener.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d74f7-121">Se la replica primaria è connessa, è possibile utilizzare il campo per modificare il numero di porta del listener.</span><span class="sxs-lookup"><span data-stu-id="d74f7-121">If you are connected the primary replica, you can use this field to modify the port number of the listener.</span></span> <span data-ttu-id="d74f7-122">È necessaria l'autorizzazione ALTER AVAILABILITY GROUP nel gruppo di disponibilità, l'autorizzazione CONTROL AVAILABILITY GROUP, l'autorizzazione ALTER ANY AVAILABILITY GROUP o l'autorizzazione CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="d74f7-122">This requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
 <span data-ttu-id="d74f7-123">**Modalità di rete**</span><span class="sxs-lookup"><span data-stu-id="d74f7-123">**Network Mode**</span></span>  
 <span data-ttu-id="d74f7-124">Indica il protocollo TCP utilizzato dal listener. È possibile scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d74f7-124">Indicates the TCP protocol used by the listener, one of:</span></span>  
  
 <span data-ttu-id="d74f7-125">**DHCP**</span><span class="sxs-lookup"><span data-stu-id="d74f7-125">**DHCP**</span></span>  
 <span data-ttu-id="d74f7-126">Il listener utilizza un indirizzo IP dinamico assegnato da un server in cui viene eseguito il protocollo DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="d74f7-126">The listener uses an dynamic IP address that is assigned by a server running the Dynamic Host Configuration Protocol (DHCP).</span></span>  
  
 <span data-ttu-id="d74f7-127">**Indirizzo IP statico**</span><span class="sxs-lookup"><span data-stu-id="d74f7-127">**Static IP**</span></span>  
 <span data-ttu-id="d74f7-128">Il listener utilizza uno o più indirizzi IP statici.</span><span class="sxs-lookup"><span data-stu-id="d74f7-128">The listener uses one or more Static IP addresses.</span></span> <span data-ttu-id="d74f7-129">Per accedere ad altre subnet, è necessario che un listener del gruppo di disponibilità utilizzi indirizzi IP statici.</span><span class="sxs-lookup"><span data-stu-id="d74f7-129">To access the different subnets, an availability group listener must use static IP addresses.</span></span>  
  
 <span data-ttu-id="d74f7-130">Nella griglia vengono visualizzate le subnet in cui il listener è in attesa e l'indirizzo IP associato a ciascuna subnet.</span><span class="sxs-lookup"><span data-stu-id="d74f7-130">The grid displays each of the subnets on which the listener listens and the IP address associated with that subnet.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d74f7-131">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d74f7-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="d74f7-132">**Per visualizzare le proprietà del listener**</span><span class="sxs-lookup"><span data-stu-id="d74f7-132">**To view listener properties**</span></span>  
  
 <span data-ttu-id="d74f7-133">Per monitorare i listener del gruppo di disponibilità, utilizzare le viste seguenti:</span><span class="sxs-lookup"><span data-stu-id="d74f7-133">To monitor the availability group listeners, use the following views:</span></span>  
  
 [<span data-ttu-id="d74f7-134">sys.availability_group_listener_ip_addresses</span><span class="sxs-lookup"><span data-stu-id="d74f7-134">sys.availability_group_listener_ip_addresses</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listener-ip-addresses-transact-sql)  
 <span data-ttu-id="d74f7-135">Restituisce una riga per ogni indirizzo IP virtuale conforme attualmente online per un listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="d74f7-135">Returns a row for every conformant virtual IP address that is currently online for an availability group listener.</span></span>  
  
 <span data-ttu-id="d74f7-136">**Nomi delle colonne:** listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span><span class="sxs-lookup"><span data-stu-id="d74f7-136">**Column names:** listener_id, ip_address, ip_subnet_mask, is_dhcp, network_subnet_ip, network_subnet_prefix_length, network_subnet_ipv4_mask, state, state_desc</span></span>  
  
 [<span data-ttu-id="d74f7-137">sys.availability_group_listeners</span><span class="sxs-lookup"><span data-stu-id="d74f7-137">sys.availability_group_listeners</span></span>](/sql/relational-databases/system-catalog-views/sys-availability-group-listeners-transact-sql)  
 <span data-ttu-id="d74f7-138">Per un determinato gruppo di disponibilità, restituisce zero righe, cosa che indica che nessun nome di rete è associato al gruppo di disponibilità, oppure restituisce una riga per ogni configurazione del listener del gruppo di disponibilità nel cluster WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="d74f7-138">For a given availability group, returns either zero rows indicating that no network name is associated with the availability group, or returns a row for each availability-group listener configuration in the WSFC cluster.</span></span>  
  
 <span data-ttu-id="d74f7-139">**Nomi delle colonne:** group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span><span class="sxs-lookup"><span data-stu-id="d74f7-139">**Column names:** group_id, listener_id, dns_name, port, is_conformant, ip_configuration_string_from_cluster</span></span>  
  
 [<span data-ttu-id="d74f7-140">sys.dm_tcp_listener_states</span><span class="sxs-lookup"><span data-stu-id="d74f7-140">sys.dm_tcp_listener_states</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tcp-listener-states-transact-sql)  
 <span data-ttu-id="d74f7-141">Restituisce una riga contenente informazioni sullo stato dinamico per ogni listener TCP.</span><span class="sxs-lookup"><span data-stu-id="d74f7-141">Returns a row containing dynamic-state information for each TCP listener.</span></span>  
  
 <span data-ttu-id="d74f7-142">**Nomi delle colonne:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span><span class="sxs-lookup"><span data-stu-id="d74f7-142">**Column names:** listener_id, ip_address, is_ipv4, port, type, type_desc, state, state_desc, start_time</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d74f7-143">Per altre informazioni sull'uso di [!INCLUDE[tsql](../../../includes/tsql-md.md)] per monitorare l'ambiente di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , vedere [Monitorare Gruppi di disponibilità &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d74f7-143">For more information about using [!INCLUDE[tsql](../../../includes/tsql-md.md)] to monitor your [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] environment, see [Monitor Availability Groups &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d74f7-144">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="d74f7-144">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d74f7-145">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d74f7-145">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="d74f7-146">Rimuovere un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d74f7-146">Remove an Availability Group Listener &#40;SQL Server&#41;</span></span>](remove-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d74f7-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d74f7-147">See Also</span></span>  
 <span data-ttu-id="d74f7-148">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d74f7-148">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="d74f7-149">[Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="d74f7-149">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="d74f7-150">Monitorare Gruppi di disponibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d74f7-150">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
