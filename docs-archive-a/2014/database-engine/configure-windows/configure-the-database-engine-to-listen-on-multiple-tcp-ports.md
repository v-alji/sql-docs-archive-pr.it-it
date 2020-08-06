---
title: Configurare il motore di database per l'attesa su più porte TCP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- ports [SQL Server], multiple
- TDS
- listen on multiple ports
- endpoints [SQL Server], TDS
- adding ports
- tabular data stream
- multiple ports
ms.assetid: 8e955033-06ef-403f-b813-3d8241b62f1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab803bcaa5ab6b6187c1a994abef02f81ae105c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624946"
---
# <a name="configure-the-database-engine-to-listen-on-multiple-tcp-ports"></a><span data-ttu-id="33e02-102">Configurazione del Motore di database per l'attesa su più porte TCP</span><span class="sxs-lookup"><span data-stu-id="33e02-102">Configure the Database Engine to Listen on Multiple TCP Ports</span></span>
  <span data-ttu-id="33e02-103">In questo argomento viene illustrato come configurare il [!INCLUDE[ssDE](../../includes/ssde-md.md)] per l'ascolto su più porte TCP in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="33e02-103">This topic describes how to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on multiple TCP ports in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="33e02-104">Quando TCP/IP è abilitato per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il [!INCLUDE[ssDE](../../includes/ssde-md.md)] è in attesa delle connessioni in ingresso su un punto di connessione composto da un indirizzo IP e dal numero di porta TCP. Le procedure riportate di seguito consentono di creare un endpoint del flusso TDS, in modo che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possa essere in ascolto su una porta TCP aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="33e02-104">When TCP/IP is enabled for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will listen for incoming connections on a connection point consisting of an IP address and TCP port number.The following procedures create a tabular data stream (TDS) endpoint, so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will listen on an additional TCP port.</span></span>  
  
 <span data-ttu-id="33e02-105">Possibili motivi per la creazione di un secondo endpoint TDS:</span><span class="sxs-lookup"><span data-stu-id="33e02-105">Possible reasons to create a second TDS endpoint include:</span></span>  
  
-   <span data-ttu-id="33e02-106">Aumentare la sicurezza configurando il firewall in modo da limitare l'accesso all'endpoint predefinito ai computer client locali in una subnet specifica.</span><span class="sxs-lookup"><span data-stu-id="33e02-106">Increase security by configuring the firewall to restrict access to the default endpoint to local client computers on a specific subnet.</span></span> <span data-ttu-id="33e02-107">Mantenere l'accesso tramite Internet a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per il personale di supporto tecnico, creando un nuovo endpoint che il firewall espone a Internet e autorizzando la connessione all'endpoint al solo personale di supporto tecnico del server.</span><span class="sxs-lookup"><span data-stu-id="33e02-107">Maintain Internet access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for your support team by creating a new endpoint that the firewall exposes to the Internet, and restricting connection rights to this endpoint to your server support team.</span></span>  
  
-   <span data-ttu-id="33e02-108">Impostare l'affinità fra connessioni e processori specifici quando si utilizza la configurazione NUMA (Non-Uniform Memory Access).</span><span class="sxs-lookup"><span data-stu-id="33e02-108">Affinitizing connections to specific processors when using Non-Uniform Memory Access (NUMA).</span></span>  
  
 <span data-ttu-id="33e02-109">La configurazione di un endpoint TDS include i passaggi seguenti, che possono essere eseguiti in qualsiasi ordine:</span><span class="sxs-lookup"><span data-stu-id="33e02-109">Configuring a TDS endpoint consists of the following steps, which can be done in any order:</span></span>  
  
-   <span data-ttu-id="33e02-110">Creare l'endpoint TDS per la porta TCP e ripristinare l'accesso all'endpoint predefinito, ove appropriato.</span><span class="sxs-lookup"><span data-stu-id="33e02-110">Create the TDS endpoint for the TCP port, and restore access to the default endpoint if appropriate.</span></span>  
  
-   <span data-ttu-id="33e02-111">Concedere l'accesso all'endpoint alle entità del server desiderate.</span><span class="sxs-lookup"><span data-stu-id="33e02-111">Grant access to the endpoint to the desired server principals.</span></span>  
  
-   <span data-ttu-id="33e02-112">Specificare il numero della porta TCP per l'indirizzo IP selezionato.</span><span class="sxs-lookup"><span data-stu-id="33e02-112">Specify the TCP port number for the selected IP address.</span></span>  
  
 <span data-ttu-id="33e02-113">Per altre informazioni sulle impostazioni predefinite di Windows Firewall e per una descrizione delle porte TCP che interessano il motore di database, Analysis Services, Reporting Services e Integration Services, vedere [Configurare Windows Firewall per consentire l'accesso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="33e02-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-create-a-tds-endpoint"></a><span data-ttu-id="33e02-114">Per creare un endpoint TDS</span><span class="sxs-lookup"><span data-stu-id="33e02-114">To create a TDS endpoint</span></span>  
  
-   <span data-ttu-id="33e02-115">Eseguire l'istruzione seguente per creare un endpoint denominato **CustomConnection** per la porta 1500 per tutti gli indirizzi TCP disponibili nel server.</span><span class="sxs-lookup"><span data-stu-id="33e02-115">Issue the following statement to create an endpoint named **CustomConnection** for port 1500 for all available TCP addresses on the server.</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE ENDPOINT [CustomConnection]  
    STATE = STARTED  
    AS TCP  
       (LISTENER_PORT = 1500, LISTENER_IP =ALL)  
    FOR TSQL() ;  
    GO  
    ```  
  
 <span data-ttu-id="33e02-116">La creazione di un nuovo endpoint [!INCLUDE[tsql](../../includes/tsql-md.md)] comporta la revoca delle autorizzazioni di connessione **public** nell'endpoint TDS predefinito.</span><span class="sxs-lookup"><span data-stu-id="33e02-116">When you create a new [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoint, connect permissions for **public** are revoked for the default TDS endpoint.</span></span> <span data-ttu-id="33e02-117">Se per l'endpoint predefinito è necessario l'accesso al gruppo **public** , riapplicare l'autorizzazione utilizzando l'istruzione `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` .</span><span class="sxs-lookup"><span data-stu-id="33e02-117">If access to the **public** group is needed for the default endpoint, reapply this permission by using the `GRANT CONNECT ON ENDPOINT::[TSQL Default TCP] to [public];` statement.</span></span>  
  
#### <a name="to-grant-access-to-the-endpoint"></a><span data-ttu-id="33e02-118">Per concedere l'accesso all'endpoint</span><span class="sxs-lookup"><span data-stu-id="33e02-118">To grant access to the endpoint</span></span>  
  
-   <span data-ttu-id="33e02-119">Eseguire l'istruzione seguente per concedere l'accesso all'endpoint **CustomConnection** al gruppo SQLSupport nel dominio aziendale.</span><span class="sxs-lookup"><span data-stu-id="33e02-119">Issue the following statement to grant access to the **CustomConnection** endpoint to the SQLSupport group in the corp domain.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[CustomConnection] to [corp\SQLSupport] ;  
    GO  
    ```  
  
#### <a name="to-configure-the-sql-server-database-engine-to-listen-on-an-additional-tcp-port"></a><span data-ttu-id="33e02-120">Per configurare il Motore di database di SQL Server per l'attesa su una porta TCP aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="33e02-120">To configure the SQL Server Database Engine to listen on an additional TCP port</span></span>  
  
1.  <span data-ttu-id="33e02-121">In Gestione configurazione SQL Server espandere **Configurazione di rete SQL Server** e quindi fare clic su **Protocolli per** _<nome_istanza>_ .</span><span class="sxs-lookup"><span data-stu-id="33e02-121">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for**_<instance_name>_.</span></span>  
  
2.  <span data-ttu-id="33e02-122">Espandere **Protocolli per** _<nome_istanza>_ e quindi fare clic su **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="33e02-122">Expand **Protocols for**_<instance_name>_, and then click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="33e02-123">Nel riquadro di destra, fare clic con il pulsante destro del mouse sugli indirizzi IP disabilitati da attivare, quindi scegliere **lita**.</span><span class="sxs-lookup"><span data-stu-id="33e02-123">In the right pane, right-click each disabled IP address that you want to enable, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="33e02-124">Fare clic con il pulsante destro del mouse su **IPAll**e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="33e02-124">Right-click **IPAll**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="33e02-125">Nella casella **Porta TCP** digitare le porte sulle quali si desidera che [!INCLUDE[ssDE](../../includes/ssde-md.md)] resti in attesa, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="33e02-125">In the **TCP Port** box, type the ports that you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, separated by commas.</span></span> <span data-ttu-id="33e02-126">In questo esempio, se la porta predefinita 1433 è elencata, digitare in `,1500` modo che la casella legga `1433,1500` , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="33e02-126">In our example, if the default port 1433 is listed, type `,1500` so the box reads `1433,1500`, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33e02-127">Se non si sta abilitando la porta su tutti gli indirizzi IP, configurare la porta aggiuntiva nella casella delle proprietà per il solo indirizzo desiderato.</span><span class="sxs-lookup"><span data-stu-id="33e02-127">If you are not enabling the port on all IP addresses, configure the additional port in the property box for only for the desired address.</span></span> <span data-ttu-id="33e02-128">Nel riquadro della console fare quindi clic con il pulsante destro del mouse su **TCP/IP**, scegliere **Proprietà**e nella casella **Attesa su tutti** selezionare **No**.</span><span class="sxs-lookup"><span data-stu-id="33e02-128">Then, in the console pane, right-click **TCP/IP**, click **Properties**, and in the **Listen All** box, select **No**.</span></span>  
  
6.  <span data-ttu-id="33e02-129">Nel riquadro di sinistra fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="33e02-129">In the left pane, click **SQL Server Services**.</span></span>  
  
7.  <span data-ttu-id="33e02-130">Nel riquadro di destra fare clic con il pulsante destro del mouse su **SQL Server** _<nome_istanza>_ e quindi scegliere **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="33e02-130">In the right pane, right-click **SQL Server**_<instance_name>_, and then click **Restart**.</span></span>  
  
     <span data-ttu-id="33e02-131">Dopo il riavvio di [!INCLUDE[ssDE](../../includes/ssde-md.md)], il log degli errori conterrà l'elenco delle porte sulle quali [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in attesa.</span><span class="sxs-lookup"><span data-stu-id="33e02-131">When the [!INCLUDE[ssDE](../../includes/ssde-md.md)] restarts, the Error log will list the ports on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening.</span></span>  
  
#### <a name="to-connect-to-the-new-endpoint"></a><span data-ttu-id="33e02-132">Per eseguire la connessione al nuovo endpoint</span><span class="sxs-lookup"><span data-stu-id="33e02-132">To connect to the new endpoint</span></span>  
  
-   <span data-ttu-id="33e02-133">Per eseguire la connessione all'endpoint **CustomConnection** dell'istanza predefinita di SQL Server nel server ACCT, usando una connessione trusted e supponendo che l'utente sia membro del gruppo [corp\SQLSupport], eseguire questa istruzione.</span><span class="sxs-lookup"><span data-stu-id="33e02-133">Issue the following statement to connect to the **CustomConnection** endpoint of the default instance of SQL Server on the server named ACCT, using a trusted connection, and assuming the user is a member of the [corp\SQLSupport] group.</span></span>  
  
    ```  
    sqlcmd -SACCT,1500  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="33e02-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33e02-134">See Also</span></span>  
 <span data-ttu-id="33e02-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="33e02-135">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="33e02-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="33e02-136">[DROP ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="33e02-137">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="33e02-137">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="33e02-138">Eseguire il mapping delle porte TCP/IP ai nodi NUMA &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="33e02-138">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)  
  
  
