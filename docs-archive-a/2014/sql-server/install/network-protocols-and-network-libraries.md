---
title: Protocolli e librerie di rete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- protocols [SQL Server]
- configuration options [SQL Server], protocols
- network libraries [SQL Server]
- protocols [SQL Server], about network protocols
- pipes [SQL Server]
- network protocols [SQL Server]
- default SQL Server configurations
- library [SQL Server]
- network protocols [SQL Server], about network protocols
- configuration options [SQL Server], libraries
ms.assetid: 8cd437f6-9af1-44ce-9cb0-4d10c83da9ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be012ea2bc9499a99ca7763446c6f26cf219a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637035"
---
# <a name="network-protocols-and-network-libraries"></a><span data-ttu-id="24f2f-102">Protocolli e librerie di rete</span><span class="sxs-lookup"><span data-stu-id="24f2f-102">Network Protocols and Network Libraries</span></span>
  <span data-ttu-id="24f2f-103">Un server può consentire di restare in attesa su più protocolli di rete contemporaneamente o di monitorarli.</span><span class="sxs-lookup"><span data-stu-id="24f2f-103">A server can listen on, or monitor, multiple network protocols at one time.</span></span> <span data-ttu-id="24f2f-104">È tuttavia necessario configurare ogni protocollo.</span><span class="sxs-lookup"><span data-stu-id="24f2f-104">However, each protocol must be configured.</span></span> <span data-ttu-id="24f2f-105">Se un particolare protocollo non è configurato, il server non può restare in attesa su tale protocollo.</span><span class="sxs-lookup"><span data-stu-id="24f2f-105">If a particular protocol is not configured, the server cannot listen on that protocol.</span></span> <span data-ttu-id="24f2f-106">Le configurazioni dei protocolli possono essere modificate dopo l'installazione utilizzando Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24f2f-106">After installation, you can change the protocol configurations using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="default-sql-server-network-configuration"></a><span data-ttu-id="24f2f-107">Configurazione di rete predefinita di SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f2f-107">Default SQL Server Network Configuration</span></span>  
 <span data-ttu-id="24f2f-108">Un'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene configurata per la porta TCP/IP 1433 e la named pipe \\\\\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="24f2f-108">A default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for TCP/IP port 1433, and named pipe \\\\.\pipe\sql\query.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="24f2f-109">vengono configurate per le porte dinamiche TCP, con un numero di porta assegnato dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="24f2f-109">named instances are configured for TCP dynamic ports, with a port number assigned by the operating system.</span></span>  
  
 <span data-ttu-id="24f2f-110">Se non è possibile utilizzare indirizzi di porta dinamici (ad esempio, quando le connessioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devono passare tramite un server firewall configurato per l'utilizzo di indirizzi di porte specifici).</span><span class="sxs-lookup"><span data-stu-id="24f2f-110">If you cannot use dynamic port addresses (for example, when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections must pass through a firewall server configured to pass through specific port addresses).</span></span> <span data-ttu-id="24f2f-111">Selezionare un numero di porta non assegnato.</span><span class="sxs-lookup"><span data-stu-id="24f2f-111">Select an unassigned port number.</span></span> <span data-ttu-id="24f2f-112">Le assegnazioni dei numeri di porta vengono gestite da IANA (Internet Assigned Numbers Authority) e sono elencate in [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span><span class="sxs-lookup"><span data-stu-id="24f2f-112">Port number assignments are managed by the Internet Assigned Numbers Authority and are listed at [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span></span>  
  
 <span data-ttu-id="24f2f-113">Per migliorare la sicurezza, la connettività di rete non viene abilitata completamente durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24f2f-113">To enhance security, network connectivity is not fully enabled when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span> <span data-ttu-id="24f2f-114">Per abilitare, disabilitare e configurare i protocolli di rete al termine dell'installazione, utilizzare l'area Configurazione di rete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24f2f-114">To enable, disable, and configure network protocols after Setup is complete, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Configuration area of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="server-message-block-protocol"></a><span data-ttu-id="24f2f-115">Protocollo Server Message Block</span><span class="sxs-lookup"><span data-stu-id="24f2f-115">Server Message Block Protocol</span></span>  
 <span data-ttu-id="24f2f-116">È necessario disabilitare tutti i protocolli non richiesti, incluso il protocollo SMB (Server Message Block), dei server della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="24f2f-116">Servers in the perimeter network should have all unnecessary protocols disabled, including server message block (SMB).</span></span> <span data-ttu-id="24f2f-117">Per i server Web e i server DNS (Domain Name System) non è necessario SMB.</span><span class="sxs-lookup"><span data-stu-id="24f2f-117">Web servers and Domain Name System (DNS) servers do not require SMB.</span></span> <span data-ttu-id="24f2f-118">È necessario disabilitare questo protocollo per proteggersi dal rischio di enumerazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="24f2f-118">This protocol should be disabled to counter the threat of user enumeration.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="24f2f-119">Tramite la disabilitazione di SMB (Server Message Block) verrà bloccato il servizio cluster di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o Windows, impedendo l'accesso alla condivisione file remota.</span><span class="sxs-lookup"><span data-stu-id="24f2f-119">Disabling Server Message Block will block the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Windows Cluster service from accessing the remote file share.</span></span> <span data-ttu-id="24f2f-120">Non disabilitare SMB se si esegue o si pianifica di eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24f2f-120">Do not disable SMB if you do or plan to do one of the following:</span></span>  
> 
>  -   <span data-ttu-id="24f2f-121">Utilizzare la modalità di quorum di tipo Maggioranza dei nodi del cluster e delle condivisioni file di Windows</span><span class="sxs-lookup"><span data-stu-id="24f2f-121">Use Windows Cluster Node and File Share Majority Quorum mode</span></span>  
> -   <span data-ttu-id="24f2f-122">Specificare una condivisione file SMB come directory dei dati durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24f2f-122">Specify an SMB file share as the data directory during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation</span></span>  
> -   <span data-ttu-id="24f2f-123">Creare un file di database in una condivisione file SMB</span><span class="sxs-lookup"><span data-stu-id="24f2f-123">Create a database file on an SMB file share</span></span>  
  
#### <a name="to-disable-smb"></a><span data-ttu-id="24f2f-124">Per disabilitare SMB</span><span class="sxs-lookup"><span data-stu-id="24f2f-124">To disable SMB</span></span>  
  
1.  <span data-ttu-id="24f2f-125">Scegliere **Impostazioni** dal menu **Start**e quindi fare clic su **Rete e connessioni remote**.</span><span class="sxs-lookup"><span data-stu-id="24f2f-125">On the **Start** menu, point to **Settings**, and then click **Network and Dial-up Connections**.</span></span>  
  
     <span data-ttu-id="24f2f-126">Fare clic con il pulsante destro del mouse sulla connessione Internet e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="24f2f-126">Right-click the Internet-facing connection, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="24f2f-127">Selezionare la casella di controllo **Client per reti Microsoft** e quindi fare clic su **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="24f2f-127">Select the **Client for Microsoft Networks** check box, and then click **Uninstall**.</span></span>  
  
3.  <span data-ttu-id="24f2f-128">Eseguire la procedura di disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="24f2f-128">Follow the uninstall steps.</span></span>  
  
4.  <span data-ttu-id="24f2f-129">Selezionare **Condivisione file e stampanti per reti Microsoft**e quindi fare clic su **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="24f2f-129">Select **File and Printer Sharing for Microsoft Networks**, and then click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="24f2f-130">Eseguire la procedura di disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="24f2f-130">Follow the uninstall steps.</span></span>  
  
#### <a name="to-disable-smb-on-servers-accessible-from-the-internet"></a><span data-ttu-id="24f2f-131">Per disabilitare SMB nei server accessibili da Internet</span><span class="sxs-lookup"><span data-stu-id="24f2f-131">To disable SMB on servers accessible from the Internet</span></span>  
  
-   <span data-ttu-id="24f2f-132">In Connessione alla rete locale (LAN) usare la finestra di dialogo **Proprietà TCP/IP** per rimuovere **Condivisione file e stampanti per reti Microsoft** e **Client per reti Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="24f2f-132">In the Local Area Connection properties, use the **Transmission Control Protocol/Internet Protocol (TCP/IP) properties** dialog box to remove **File and Printer Sharing for Microsoft Networks** and **Client for Microsoft Networks**.</span></span>  
  
## <a name="endpoints"></a><span data-ttu-id="24f2f-133">Endpoint</span><span class="sxs-lookup"><span data-stu-id="24f2f-133">Endpoints</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="24f2f-134">introduce un nuovo concetto in base al quale le connessioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono rappresentate sul lato server da un [!INCLUDE[tsql](../../includes/tsql-md.md)]*endpoint*.</span><span class="sxs-lookup"><span data-stu-id="24f2f-134">introduces a new concept for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections; the connection is represented on the server end by a [!INCLUDE[tsql](../../includes/tsql-md.md)]*endpoint*.</span></span> <span data-ttu-id="24f2f-135">È possibile concedere, revocare o negare le autorizzazioni per gli endpoint [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24f2f-135">Permissions can be granted, revoked, and denied for [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints.</span></span> <span data-ttu-id="24f2f-136">Per impostazione predefinita, tutti gli utenti dispongono delle autorizzazioni di accesso a un endpoint a meno che tali autorizzazioni non vengano negate o revocate da un membro del gruppo sysadmin o dal proprietario dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="24f2f-136">By default, all users have permissions to access an endpoint unless the permissions are denied or revoked by a member of the sysadmin group or by the endpoint owner.</span></span> <span data-ttu-id="24f2f-137">La sintassi GRANT, REVOKE e DENY ENDPOINT utilizza un ID di endpoint che l'amministratore deve ottenere dalla vista del catalogo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="24f2f-137">The GRANT, REVOKE, and DENY ENDPOINT syntax uses an endpoint ID that the administrator must get from the endpoint's catalog view.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="24f2f-138">crea endpoint [!INCLUDE[tsql](../../includes/tsql-md.md)] per tutti i protocolli di rete supportati, nonché per la connessione amministrativa dedicata.</span><span class="sxs-lookup"><span data-stu-id="24f2f-138">Setup creates [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints for all supported network protocols, as well as for the dedicated administrator connection.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="24f2f-139">creati dal programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="24f2f-139">endpoints created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup are as follows:</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="24f2f-140">computer locale</span><span class="sxs-lookup"><span data-stu-id="24f2f-140">local machine</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="24f2f-141">named pipe</span><span class="sxs-lookup"><span data-stu-id="24f2f-141">named pipes</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="24f2f-142">TCP predefinito</span><span class="sxs-lookup"><span data-stu-id="24f2f-142">default TCP</span></span>  
  
 <span data-ttu-id="24f2f-143">Per altre informazioni sugli endpoint, vedere [Configurazione del Motore di database per l'attesa su più porte TCP](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) e [Viste del catalogo degli endpoint &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="24f2f-143">For more information about endpoints, see [Configure the Database Engine to Listen on Multiple TCP Ports](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) and [Endpoints Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span></span>  
  
 <span data-ttu-id="24f2f-144">Per altre informazioni sulle configurazioni di rete di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere l'argomento seguente nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="24f2f-144">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network configurations, see the following topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="24f2f-145">Configurazione di rete del server</span><span class="sxs-lookup"><span data-stu-id="24f2f-145">Server Network Configuration</span></span>](../../database-engine/configure-windows/server-network-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="24f2f-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24f2f-146">See Also</span></span>  
 <span data-ttu-id="24f2f-147">[Configurazione superficie di attacco](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="24f2f-147">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 <span data-ttu-id="24f2f-148">[Considerazioni sulla sicurezza per un'installazione di SQL Server](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="24f2f-148">[Security Considerations for a SQL Server Installation](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="24f2f-149">Pianificazione di un'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="24f2f-149">Planning a SQL Server Installation</span></span>](../../../2014/sql-server/install/planning-a-sql-server-installation.md)  
  
  
