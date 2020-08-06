---
title: Configurare un server per l'attesa su una porta TCP specifica (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fixed port
- static ports
- ports [SQL Server], assigning numbers
- assigning port numbers
- dynamic ports [SQL Server]
- TCP/IP [SQL Server], port numbers
ms.assetid: 2276a5ed-ae3f-4855-96d8-f5bf01890640
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb740910c65580e8ea3170d03481e6cb628860
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624357"
---
# <a name="configure-a-server-to-listen-on-a-specific-tcp-port-sql-server-configuration-manager"></a><span data-ttu-id="09058-102">Configurazione di un server per l'attesa su una porta TCP specifica (Gestione configurazione SQL Server)</span><span class="sxs-lookup"><span data-stu-id="09058-102">Configure a Server to Listen on a Specific TCP Port (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="09058-103">In questo argomento viene descritto come configurare un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] per essere in ascolto su una porta fissa specifica tramite Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09058-103">This topic describes how to configure an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to listen on a specific fixed port by using the SQL Server Configuration Manager.</span></span> <span data-ttu-id="09058-104">Se abilitata, l'istanza predefinita del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] rimane in attesa sulla porta TCP 1433.</span><span class="sxs-lookup"><span data-stu-id="09058-104">If enabled, the default instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on TCP port 1433.</span></span> <span data-ttu-id="09058-105">Le istanze denominate del [!INCLUDE[ssDE](../../includes/ssde-md.md)] e di [!INCLUDE[ssEW](../../includes/ssew-md.md)] sono configurate per porte dinamiche.</span><span class="sxs-lookup"><span data-stu-id="09058-105">Named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] are configured for dynamic ports.</span></span> <span data-ttu-id="09058-106">Questo significa che selezionano una porta disponibile quando viene avviato il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="09058-106">This means they select an available port when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service is started.</span></span> <span data-ttu-id="09058-107">Quando ci si connette a un'istanza denominata tramite un firewall, configurare [!INCLUDE[ssDE](../../includes/ssde-md.md)] per l'ascolto su una porta specifica, in modo da consentire l'apertura della porta appropriata nel firewall.</span><span class="sxs-lookup"><span data-stu-id="09058-107">When you are connecting to a named instance through a firewall, configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on a specific port, so that the appropriate port can be opened in the firewall.</span></span>  
  
 <span data-ttu-id="09058-108">Per altre informazioni sulle impostazioni predefinite di Windows Firewall e per una descrizione delle porte TCP che interessano il motore di database, Analysis Services, Reporting Services e Integration Services, vedere [Configurare Windows Firewall per consentire l'accesso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="09058-108">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the Database Engine, Analysis Services, Reporting Services, and Integration Services, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="09058-109">Quando si seleziona un numero di porta, vedere la pagina [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) per un elenco di numeri di porta assegnati ad applicazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="09058-109">When selecting a port number, consult [http://www.iana.org/assignments/port-numbers](http://www.iana.org/assignments/port-numbers) for a list of port numbers that are assigned to specific applications.</span></span> <span data-ttu-id="09058-110">Selezionare un numero di porta non assegnato.</span><span class="sxs-lookup"><span data-stu-id="09058-110">Select an unassigned port number.</span></span> <span data-ttu-id="09058-111">Per altre informazioni, vedere la pagina relativa all' [intervallo di porte dinamiche predefinite per TCP/IP modificato in Windows Vista e in Windows Server 2008](https://support.microsoft.com/kb/929851).</span><span class="sxs-lookup"><span data-stu-id="09058-111">For more information, see [The default dynamic port range for TCP/IP has changed in Windows Vista and in Windows Server 2008](https://support.microsoft.com/kb/929851).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="09058-112">L'ascolto viene iniziato dal motore di database su una nuova porta al momento del riavvio.</span><span class="sxs-lookup"><span data-stu-id="09058-112">The Database Engine begins listening on a new port when restarted.</span></span> <span data-ttu-id="09058-113">Tuttavia, tramite il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser viene monitorato il Registro di sistema e viene segnalato il nuovo numero di porta appena la configurazione viene modificata, anche se non in uso da parte del motore di database.</span><span class="sxs-lookup"><span data-stu-id="09058-113">However the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service monitors the registry and reports the new port number as soon as the configuration is changed, even though the Database Engine might not be using it.</span></span> <span data-ttu-id="09058-114">Riavviare il motore di database per garantire coerenza ed evitare errori di connessione.</span><span class="sxs-lookup"><span data-stu-id="09058-114">Restart the Database Engine to ensure consistency and avoid connection failures.</span></span>  
  
 <span data-ttu-id="09058-115">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="09058-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="09058-116">**Per configurare un server per l'attesa su una porta TCP specifica utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="09058-116">**To configure a server to listen on a specific TCP port, using:**</span></span>  
  
     [<span data-ttu-id="09058-117">Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="09058-117">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="09058-118">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="09058-118">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-assign-a-tcpip-port-number-to-the-sql-server-database-engine"></a><span data-ttu-id="09058-119">Per assegnare un numero di porta TCP/IP al motore di database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="09058-119">To assign a TCP/IP port number to the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="09058-120">Nel riquadro della console di Gestione configurazione SQL Server espandere **Configurazione di rete SQL Server**, quindi **Protocolli per \<instance name>** e infine fare doppio clic su **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="09058-120">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, expand **Protocols for \<instance name>**, and then double-click **TCP/IP**.</span></span>  
  
2.  <span data-ttu-id="09058-121">Nella scheda **Indirizzi TCP/IP** della finestra di dialogo **Proprietà TCP/IP** vengono visualizzati vari indirizzi IP nel formato **IP1**, **IP2**e **IPAll**.</span><span class="sxs-lookup"><span data-stu-id="09058-121">In the **TCP/IP Properties** dialog box, on the **IP Addresses** tab, several IP addresses appear in the format **IP1**, **IP2**, up to **IPAll**.</span></span> <span data-ttu-id="09058-122">Uno di tali indirizzi corrisponde all'indirizzo IP della scheda loopback, ovvero 127.0.0.1.</span><span class="sxs-lookup"><span data-stu-id="09058-122">One of these is for the IP address of the loopback adapter, 127.0.0.1.</span></span> <span data-ttu-id="09058-123">Ulteriori indirizzi IP vengono visualizzati per ogni indirizzo IP nel computer.</span><span class="sxs-lookup"><span data-stu-id="09058-123">Additional IP addresses appear for each IP Address on the computer.</span></span> <span data-ttu-id="09058-124">Fare clic con il pulsante destro del mouse su ogni indirizzo e scegliere **Proprietà** per identificare l'indirizzo IP da configurare.</span><span class="sxs-lookup"><span data-stu-id="09058-124">Right-click each address, and then click **Properties** to identify the IP address that you want to configure.</span></span>  
  
3.  <span data-ttu-id="09058-125">Se nella finestra di dialogo **Porte dinamiche TCP** è incluso il valore **0**, che indica che [!INCLUDE[ssDE](../../includes/ssde-md.md)] è in attesa su porte dinamiche, eliminare tale valore.</span><span class="sxs-lookup"><span data-stu-id="09058-125">If the **TCP Dynamic Ports** dialog box contains **0**, indicating the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is listening on dynamic ports, delete the 0.</span></span>  
  
4.  <span data-ttu-id="09058-126">Nella casella **Porta TCP** dell'area **Proprietà** **IP**_n_ immettere il numero di porta su cui deve rimanere in attesa questo indirizzo IP e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="09058-126">In the **IP**_n_ **Properties** area box, in the **TCP Port** box, type the port number you want this IP address to listen on, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="09058-127">Nel riquadro della console fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="09058-127">In the console pane, click **SQL Server Services**.</span></span>  
  
6.  <span data-ttu-id="09058-128">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **SQL Server (** \<instance name> **)** e quindi scegliere **Riavvia** per arrestare e riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09058-128">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="09058-129">Dopo la configurazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'ascolto su una porta specifica sono disponibili tre soluzioni per connettersi a una porta specifica con un'applicazione client:</span><span class="sxs-lookup"><span data-stu-id="09058-129">After you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on a specific port, there are three ways to connect to a specific port with a client application:</span></span>  
  
-   <span data-ttu-id="09058-130">Eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sul server per connettersi all'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)] specificandone il nome.</span><span class="sxs-lookup"><span data-stu-id="09058-130">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance by name.</span></span>  
  
-   <span data-ttu-id="09058-131">Creare un alias sul client, specificando il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="09058-131">Create an alias on the client, specifying the port number.</span></span>  
  
-   <span data-ttu-id="09058-132">Programmare il client affinché si connetta utilizzando una stringa di connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="09058-132">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09058-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09058-133">See Also</span></span>  
 [<span data-ttu-id="09058-134">Creare o eliminare un alias server per l'uso da parte di un client &#40;Gestione configurazione SQL Server Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="09058-134">Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;</span></span>](create-or-delete-a-server-alias-for-use-by-a-client.md)  
  
  
