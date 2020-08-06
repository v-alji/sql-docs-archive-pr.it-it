---
title: Creazione di una stringa di connessione valida con TCP/IP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine]
- ports [SQL Server], connecting to
- TCP/IP [SQL Server], connection strings
- connection strings [Database Engine], TCP/IP
- aliases [SQL Server], TCP/IP
ms.assetid: ee5dbc2c-1fc6-42bd-bdf5-efa792557934
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f761fa86ec4ed09c13bf4807489754c10b979ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628047"
---
# <a name="creating-a-valid-connection-string-using-tcp-ip"></a><span data-ttu-id="e798b-102">Creazione di una stringa di connessione valida con TCP/IP</span><span class="sxs-lookup"><span data-stu-id="e798b-102">Creating a Valid Connection String Using TCP IP</span></span>
  <span data-ttu-id="e798b-103">Per creare una stringa di connessione valida tramite TCP/IP, è necessario:</span><span class="sxs-lookup"><span data-stu-id="e798b-103">To create a valid connection string using TCP/IP, you must:</span></span>  
  
-   <span data-ttu-id="e798b-104">Specificare un **Nome alias**.</span><span class="sxs-lookup"><span data-stu-id="e798b-104">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="e798b-105">Per **Server**, immettere un nome server a cui connettersi utilizzando l'utilità **PING** o un indirizzo IP a cui è possibile connettersi utilizzando l'utilità **PING**.</span><span class="sxs-lookup"><span data-stu-id="e798b-105">For the **Server**, enter either a server name to which you can connect using the **PING** utility, or an IP address to which you can connect using the **PING** utility.</span></span> <span data-ttu-id="e798b-106">Per un'istanza denominata, aggiungere il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="e798b-106">For a named instance append the instance name.</span></span>  
  
-   <span data-ttu-id="e798b-107">Specificare **TCP/IP** per il **Protocollo**.</span><span class="sxs-lookup"><span data-stu-id="e798b-107">Specify **TCP/IP** for the **Protocol**.</span></span>  
  
-   <span data-ttu-id="e798b-108">Facoltativamente, immettere un numero di porta in **Numero porta**.</span><span class="sxs-lookup"><span data-stu-id="e798b-108">Optionally, enter a port number for the **Port No**.</span></span> <span data-ttu-id="e798b-109">Il numero di porta predefinito è 1433, ossia il numero di porta dell'istanza predefinita di [!INCLUDE[ssDE](../../includes/ssde-md.md)] in un server.</span><span class="sxs-lookup"><span data-stu-id="e798b-109">The default is 1433, which is the port number of the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a server.</span></span> <span data-ttu-id="e798b-110">Per connettersi a un'istanza denominata o a un'istanza predefinita non in attesa sulla porta 1433, è necessario fornire il numero di porta o avviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="e798b-110">To connect to a named instance or a default instance that is not listening on port 1433, you must provide the port number, or start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span> <span data-ttu-id="e798b-111">Per informazioni sulla configurazione del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser, vedere [Servizio SQL Server Browser](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="e798b-111">For information on configuring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service, see [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="e798b-112">Al momento della connessione, tramite il componente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client vengono letti i valori relativi a server, protocollo e porta dal Registro di sistema per il nome alias specificato e viene creata una stringa di connessione nel formato `tcp:<servername>[\<instancename>],<port>` o `tcp:<IPAddress>[\<instancename>],<port>`.</span><span class="sxs-lookup"><span data-stu-id="e798b-112">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and port values from the registry for the specified alias name, and creates a connection string in the format `tcp:<servername>[\<instancename>],<port>` or `tcp:<IPAddress>[\<instancename>],<port>`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e798b-113">Per impostazione predefinita, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall chiude la porta 1433.</span><span class="sxs-lookup"><span data-stu-id="e798b-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 1433 by default.</span></span> <span data-ttu-id="e798b-114">Considerato che [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comunica sulla porta 1433, è necessario aprire nuovamente tale porta se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è configurato per restare in attesa di connessioni client in ingresso che usano TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="e798b-114">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 1433, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using TCP/IP.</span></span> <span data-ttu-id="e798b-115">Per informazioni sulla configurazione di un firewall, vedere "Procedura: Configurazione di un firewall per l’accesso a SQL Server" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oppure vedere la documentazione relativa al firewall.</span><span class="sxs-lookup"><span data-stu-id="e798b-115">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e798b-116">e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client supportano completamente sia IPv4 (protocollo IP versione 4) sia IPv6 (protocollo IP versione 6).</span><span class="sxs-lookup"><span data-stu-id="e798b-116">and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fully support both Internet Protocol version 4 (IPv4) and Internet Protocol version 6 (IPv6).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e798b-117">Gestione configurazione accetta sia il formato IPv4 sia il formato IPv6 per gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="e798b-117">Configuration Manager accepts both IPv4 and IPv6 formats for IP addresses.</span></span> <span data-ttu-id="e798b-118">Per informazioni su IPv6, vedere "Connessioni con IPv6" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e798b-118">For information on IPv6, see "Connecting Using IPv6" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="e798b-119">Connessione al server locale</span><span class="sxs-lookup"><span data-stu-id="e798b-119">Connecting to the Local Server</span></span>  
 <span data-ttu-id="e798b-120">Quando si stabilisce una connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione nello stesso computer del client, è possibile utilizzare `(local)` come nome del server.</span><span class="sxs-lookup"><span data-stu-id="e798b-120">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)` as the server name.</span></span> <span data-ttu-id="e798b-121">Non si tratta di un'operazione consigliabile, in quanto genera ambiguità, ma può risultare utile se si è sicuri che il client viene eseguito nello stesso computer del server.</span><span class="sxs-lookup"><span data-stu-id="e798b-121">This is not encouraged as it leads to ambiguity, however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="e798b-122">Se, ad esempio, si crea un'applicazione per gli utenti mobili non connessi, ad esempio il personale di vendita, e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verrà eseguito su computer portatili e usato per archiviare dati di progetto, un client che si connette a `(local)` si connetterà sempre a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione sul portatile.</span><span class="sxs-lookup"><span data-stu-id="e798b-122">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to `(local)` would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="e798b-123">In sostituzione di `localhost` è possibile usare la parola**o un punto (** . `(local)`).</span><span class="sxs-lookup"><span data-stu-id="e798b-123">The word `localhost` or a period (**.**) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="e798b-124">Verifica del protocollo di connessione</span><span class="sxs-lookup"><span data-stu-id="e798b-124">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="e798b-125">La query seguente restituisce il protocollo utilizzato per la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="e798b-125">The following query returns the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="e798b-126">Esempi</span><span class="sxs-lookup"><span data-stu-id="e798b-126">Examples</span></span>  
 <span data-ttu-id="e798b-127">Connessione tramite il nome del server:</span><span class="sxs-lookup"><span data-stu-id="e798b-127">Connecting by server name:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="e798b-128">Connessione tramite il nome del server a un'istanza denominata:</span><span class="sxs-lookup"><span data-stu-id="e798b-128">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <servername>\<instancename>  
  
```  
  
 <span data-ttu-id="e798b-129">Connessione tramite il nome del server a una porta specifica:</span><span class="sxs-lookup"><span data-stu-id="e798b-129">Connecting by server name to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port>  
Protocol           TCP/IP  
Server             <servername>  
  
```  
  
 <span data-ttu-id="e798b-130">Connessione tramite indirizzo IP:</span><span class="sxs-lookup"><span data-stu-id="e798b-130">Connecting by IP address:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="e798b-131">Connessione tramite indirizzo IP a un'istanza denominata:</span><span class="sxs-lookup"><span data-stu-id="e798b-131">Connecting by IP address to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             <IPAddress>\<instancename>  
  
```  
  
 <span data-ttu-id="e798b-132">Connessione tramite indirizzo IP a una porta specificata:</span><span class="sxs-lookup"><span data-stu-id="e798b-132">Connecting by IP address to a specified port:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <port number>  
Protocol           TCP/IP  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="e798b-133">Connessione al computer locale tramite `(local)`:</span><span class="sxs-lookup"><span data-stu-id="e798b-133">Connecting to the local computer using `(local)`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             (local)  
  
```  
  
 <span data-ttu-id="e798b-134">Connessione al computer locale tramite `localhost`:</span><span class="sxs-lookup"><span data-stu-id="e798b-134">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost  
  
```  
  
 <span data-ttu-id="e798b-135">Connessione a un'istanza denominata nel computer locale tramite `localhost`:</span><span class="sxs-lookup"><span data-stu-id="e798b-135">Connecting to a named instance on the local computer `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             localhost\<instancename>  
  
```  
  
 <span data-ttu-id="e798b-136">Connessione al computer locale tramite un punto:</span><span class="sxs-lookup"><span data-stu-id="e798b-136">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .  
  
```  
  
 <span data-ttu-id="e798b-137">Connessione a un'istanza denominata nel computer locale tramite un punto:</span><span class="sxs-lookup"><span data-stu-id="e798b-137">Connecting to a named instance on the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Port No            <blank>  
Protocol           TCP/IP  
Server             .\<instancename>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e798b-138">Per informazioni su come specificare il protocollo di rete come parametro **sqlcmd** , vedere "Procedura: Connessione al Motore di database tramite sqlcmd.exe" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e798b-138">For information on specifying the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e798b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e798b-139">See Also</span></span>  
 <span data-ttu-id="e798b-140">[Creazione di una stringa di connessione valida mediante il protocollo di memoria condivisa](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="e798b-140">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="e798b-141">[Creazione di una stringa di connessione valida tramite named pipe](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span><span class="sxs-lookup"><span data-stu-id="e798b-141">[Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md) </span></span>  
 [<span data-ttu-id="e798b-142">Scelta di un protocollo di rete</span><span class="sxs-lookup"><span data-stu-id="e798b-142">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
