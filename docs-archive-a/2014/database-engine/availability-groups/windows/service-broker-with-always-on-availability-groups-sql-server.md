---
title: Service Broker con Gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 881c20e5-1c99-44eb-b393-09fc5ea0f122
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da179219363422c4ec242d29be61f35dd1609823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628990"
---
# <a name="service-broker-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="9a065-102">Service Broker con i gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9a065-102">Service Broker with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="9a065-103">In questo argomento sono contenute informazioni sulla configurazione di Service Broker per poter utilizzarlo con i [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a065-103">This topic contains information about configuring Service Broker to work with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="9a065-104">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="9a065-104">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="9a065-105">Requisiti per un servizio in un gruppo di disponibilità per la ricezione di messaggi remoti</span><span class="sxs-lookup"><span data-stu-id="9a065-105">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>](#ReceiveRemoteMessages)  
  
-   [<span data-ttu-id="9a065-106">Requisiti per l'invio di messaggi a un servizio remoto in un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="9a065-106">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>](#SendRemoteMessages)  
  
##  <a name="requirements-for-a-service-in-an-availability-group-to-receive-remote-messages"></a><a name="ReceiveRemoteMessages"></a> <span data-ttu-id="9a065-107">Requisiti necessari affinché i messaggi remoti vengano ricevuti da un servizio in un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="9a065-107">Requirements for a Service in an Availability Group to Receive Remote Messages</span></span>  
  
1.  <span data-ttu-id="9a065-108">**Assicurarsi che nel gruppo di disponibilità sia disponibile un listener.**</span><span class="sxs-lookup"><span data-stu-id="9a065-108">**Ensure that the availability group possesses a listener.**</span></span>  
  
     <span data-ttu-id="9a065-109">Per altre informazioni, vedere [Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a065-109">For more information, see [Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="9a065-110">**Assicurarsi che l'endpoint di Service Broker sia presente e che sia configurato correttamente.**</span><span class="sxs-lookup"><span data-stu-id="9a065-110">**Ensure that the Service Broker endpoint exists and is correctly configured.**</span></span>  
  
     <span data-ttu-id="9a065-111">In ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in cui è ospitata una replica di disponibilità per il gruppo di disponibilità, configurare l'endpoint di Service Broker come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9a065-111">On every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica for the availability group, configure the Service Broker endpoint, as follows:</span></span>  
  
    -   <span data-ttu-id="9a065-112">Impostare LISTENER_IP su 'ALL'.</span><span class="sxs-lookup"><span data-stu-id="9a065-112">Set LISTENER_IP to 'ALL'.</span></span> <span data-ttu-id="9a065-113">Con questa impostazione vengono abilitate le connessioni in qualsiasi indirizzo IP valido associato al listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="9a065-113">This setting enables connections on any valid IP address that is bound to the availability group listener.</span></span>  
  
    -   <span data-ttu-id="9a065-114">Impostare la porta di Service Broker sullo stesso numero di porta in tutte le istanze del server host.</span><span class="sxs-lookup"><span data-stu-id="9a065-114">Set the Service Broker PORT to the same port number on all the host server instances.</span></span>  
  
        > [!TIP]  
        >  <span data-ttu-id="9a065-115">Per visualizzare il numero di porta dell'endpoint di Service Broker in un'istanza del server specifica, eseguire una query sulla colonna **port** della vista del catalogo [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) , dove **type_desc** = 'SERVICE_BROKER'.</span><span class="sxs-lookup"><span data-stu-id="9a065-115">To view the port number of the Service Broker endpoint on a given server instance, query the **port** column of the [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) catalog view, where **type_desc** = 'SERVICE_BROKER'.</span></span>  
  
     <span data-ttu-id="9a065-116">Nell'esempio seguente viene creato un endpoint di Service Broker con autenticazione di Windows in cui viene utilizzata la porta predefinita di Service Broker (4022) e si è in ascolto di tutti gli indirizzi IP validi.</span><span class="sxs-lookup"><span data-stu-id="9a065-116">The following example creates a Windows authenticated Service Broker endpoint that uses the default Service Broker port (4022) and listens to all valid IP addresses.</span></span>  
  
    ```  
    CREATE ENDPOINT [SSBEndpoint]  
        STATE = STARTED  
        AS TCP  (LISTENER_PORT = 4022, LISTENER_IP = ALL )  
        FOR SERVICE_BROKER (AUTHENTICATION = WINDOWS)  
    ```  
  
     <span data-ttu-id="9a065-117">Per altre informazioni, vedere [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a065-117">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
3.  <span data-ttu-id="9a065-118">**Concedere l'autorizzazione CONNECT nell'endpoint.**</span><span class="sxs-lookup"><span data-stu-id="9a065-118">**Grant CONNECT permission on the endpoint.**</span></span>  
  
     <span data-ttu-id="9a065-119">Concedere l'autorizzazione CONNECT per l'endpoint di Service Broker al ruolo PUBLIC o a un account di accesso.</span><span class="sxs-lookup"><span data-stu-id="9a065-119">Grant CONNECT permission on the Service Broker endpoint either to PUBLIC or to a login.</span></span>  
  
     <span data-ttu-id="9a065-120">Nell'esempio seguente viene concessa la connessione in un endpoint di Service Broker denominato `broker_endpoint` al ruolo PUBLIC.</span><span class="sxs-lookup"><span data-stu-id="9a065-120">The following example grants the connection on a Service Broker endpoint named `broker_endpoint` to PUBLIC.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[broker_endpoint] TO [PUBLIC]  
    ```  
  
     <span data-ttu-id="9a065-121">Per altre informazioni, vedere [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a065-121">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span>  
  
4.  <span data-ttu-id="9a065-122">**Assicurarsi che msdb contenga una route AutoCreatedLocal o una route al servizio specifico.**</span><span class="sxs-lookup"><span data-stu-id="9a065-122">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a065-123">Per impostazione predefinita, tutti i database utente, incluso **msdb**, contengono la route **AutoCreatedLocal**.</span><span class="sxs-lookup"><span data-stu-id="9a065-123">By default, each user database, including **msdb**, contains the route **AutoCreatedLocal**.</span></span> <span data-ttu-id="9a065-124">Questa route corrisponde a qualsiasi nome di servizio e istanza di Service Broker e, tramite essa, viene specificato che il messaggio deve essere recapitato all'interno dell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="9a065-124">This route matches any service name and broker instance and specifies that the message should be delivered within the current instance.</span></span> <span data-ttu-id="9a065-125">**AutoCreatedLocal** ha una priorità inferiore rispetto alle route che specifica esplicitamente un servizio specifico usato per comunicare con un'istanza remota.</span><span class="sxs-lookup"><span data-stu-id="9a065-125">**AutoCreatedLocal** has lower priority than routes that explicitly specify a specific service that communicates with a remote instance.</span></span>  
  
     <span data-ttu-id="9a065-126">Per informazioni sulla creazione di route, vedere [Esempi di routing di Service Broker](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) nella versione [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] della documentazione online e [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a065-126">For information about creating routes, see [Service Broker Routing Examples](https://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (in the [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] version of Books Online) and [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
##  <a name="requirements-for-sending-messages-to-a-remote-service-in-an-availability-group"></a><a name="SendRemoteMessages"></a> <span data-ttu-id="9a065-127">Requisiti per inviare messaggi a un servizio remoto in un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="9a065-127">Requirements for Sending Messages to a Remote Service in an Availability Group</span></span>  
  
1.  <span data-ttu-id="9a065-128">**Creare una route al servizio di destinazione.**</span><span class="sxs-lookup"><span data-stu-id="9a065-128">**Create a route to the target service.**</span></span>  
  
     <span data-ttu-id="9a065-129">Configurare la route come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9a065-129">Configure the route as follows:</span></span>  
  
    -   <span data-ttu-id="9a065-130">Impostare ADDRESS sull'indirizzo IP del listener del gruppo di disponibilità in cui è ospitato il database del servizio.</span><span class="sxs-lookup"><span data-stu-id="9a065-130">Set ADDRESS to the listener IP address of availability group that hosts the service database.</span></span>  
  
    -   <span data-ttu-id="9a065-131">Impostare PORT sulla porta specificata nell'endpoint di Service Broker di ogni istanza remota di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9a065-131">Set PORT to the port that you specified in the Service Broker endpoint of each of the remote SQL Server instances.</span></span>  
  
     <span data-ttu-id="9a065-132">Nell'esempio seguente viene creata una route denominata `RouteToTargetService` per il servizio `ISBNLookupRequestService` .</span><span class="sxs-lookup"><span data-stu-id="9a065-132">The following example creates a route named `RouteToTargetService` for the `ISBNLookupRequestService` service.</span></span> <span data-ttu-id="9a065-133">La route è destinata al listener del gruppo di disponibilità, `MyAgListener`, da cui viene utilizzata la porta 4022.</span><span class="sxs-lookup"><span data-stu-id="9a065-133">The route targets the availability group listener, `MyAgListener`, which uses port 4022.</span></span>  
  
    ```  
    CREATE ROUTE [RouteToTargetService] WITH   
    SERVICE_NAME = 'ISBNLookupRequestService',   
    ADDRESS = 'TCP://MyAgListener:4022';  
  
    ```  
  
     <span data-ttu-id="9a065-134">Per altre informazioni, vedere [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a065-134">For more information, see [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).</span></span>  
  
2.  <span data-ttu-id="9a065-135">**Assicurarsi che msdb contenga una route AutoCreatedLocal o una route al servizio specifico.**</span><span class="sxs-lookup"><span data-stu-id="9a065-135">**Ensure that msdb contains either an AutoCreatedLocal route or a route to the specific service.**</span></span> <span data-ttu-id="9a065-136">Per altre informazioni, vedere [Requisiti necessari affinché i messaggi remoti vengano ricevuti da un servizio in un gruppo di disponibilità](#ReceiveRemoteMessages)più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9a065-136">(For more information, see [Requirements for a Service in an Availability Group to Receive Remote Messages](#ReceiveRemoteMessages), earlier in this topic.)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9a065-137">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="9a065-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9a065-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a065-138">CREATE ENDPOINT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-endpoint-transact-sql)  
  
-   [<span data-ttu-id="9a065-139">CREATE ROUTE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a065-139">CREATE ROUTE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-route-transact-sql)  
  
-   [<span data-ttu-id="9a065-140">GRANT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a065-140">GRANT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-transact-sql)  
  
-   <span data-ttu-id="9a065-141">[Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a065-141">[Create or Configure an Availability Group Listener &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).</span></span>  
  
-   [<span data-ttu-id="9a065-142">Creazione e configurazione di gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9a065-142">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="9a065-143">Configurare gli account di accesso per il mirroring del database o Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9a065-143">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../../database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a065-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a065-144">See Also</span></span>  
 <span data-ttu-id="9a065-145">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9a065-145">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="9a065-146">[Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="9a065-146">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="9a065-147">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="9a065-147">SQL Server Service Broker</span></span>](../../configure-windows/sql-server-service-broker.md)  
  
  
