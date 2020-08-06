---
title: Creazione di una stringa di connessione valida tramite named pipe | Microsoft Docs
description: Informazioni su come creare una stringa di connessione valida quando si usa il protocollo Named Pipes per connettersi a un'istanza di SQL Server. Visualizza esempi di nomi di pipe validi.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connection strings [Database Engine], named pipes
- pipes [SQL Server]
- pipes [SQL Server], connecting to
- aliases [SQL Server], named pipes
- Named Pipes [SQL Server], connection strings
ms.assetid: 90930ff2-143b-4651-8ae3-297103600e4f
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f3e1d01e9e5b7b1d1c0d1bb822bf233ceee636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628049"
---
# <a name="creating-a-valid-connection-string-using-named-pipes"></a><span data-ttu-id="03456-104">Creazione di una stringa di connessione valida tramite named pipe</span><span class="sxs-lookup"><span data-stu-id="03456-104">Creating a Valid Connection String Using Named Pipes</span></span>
  <span data-ttu-id="03456-105">A meno che non venga modificato dall'utente, quando l'istanza predefinita di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in attesa sul protocollo Named Pipes, utilizza `\\.\pipe\sql\query` come nome della pipe.</span><span class="sxs-lookup"><span data-stu-id="03456-105">Unless changed by the user, when the default instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on the named pipes protocol, it uses `\\.\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="03456-106">Il periodo indica che il computer è il computer locale, `pipe` indica che la connessione è una named pipe e `sql\query` è il nome della pipe.</span><span class="sxs-lookup"><span data-stu-id="03456-106">The period indicates that the computer is the local computer, `pipe` indicates that the connection is a named pipe, and `sql\query` is the name of the pipe.</span></span> <span data-ttu-id="03456-107">Per connettersi alla pipe predefinita, è necessario che il nome della pipe dell'alias sia `\\<computer_name>\pipe\sql\query`.</span><span class="sxs-lookup"><span data-stu-id="03456-107">To connect to the default pipe, the alias must have `\\<computer_name>\pipe\sql\query` as the pipe name.</span></span> <span data-ttu-id="03456-108">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato configurato per essere in attesa su una pipe diversa, è necessario che il nome della pipe utilizzi tale pipe.</span><span class="sxs-lookup"><span data-stu-id="03456-108">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been configured to listen on a different pipe, the pipe name must use that pipe.</span></span> <span data-ttu-id="03456-109">Se ad esempio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizza `\\.\pipe\unit\app` come pipe, è necessario che l'alias utilizzi `\\<computer_name>\pipe\unit\app` come nome della pipe.</span><span class="sxs-lookup"><span data-stu-id="03456-109">For instance, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using `\\.\pipe\unit\app` as the pipe, the alias must use `\\<computer_name>\pipe\unit\app` as the pipe name.</span></span>  
  
 <span data-ttu-id="03456-110">Per creare un nome di pipe valido, è necessario:</span><span class="sxs-lookup"><span data-stu-id="03456-110">To create a valid pipe name, you must:</span></span>  
  
-   <span data-ttu-id="03456-111">Specificare un **Nome alias**.</span><span class="sxs-lookup"><span data-stu-id="03456-111">Specify an **Alias Name**.</span></span>  
  
-   <span data-ttu-id="03456-112">Selezionare **Named Pipes** come **protocollo**.</span><span class="sxs-lookup"><span data-stu-id="03456-112">Select **Named Pipes** as the **Protocol**.</span></span>  
  
-   <span data-ttu-id="03456-113">Immettere il **nome della pipe**.</span><span class="sxs-lookup"><span data-stu-id="03456-113">Enter the **Pipe Name**.</span></span> <span data-ttu-id="03456-114">In alternativa, è possibile lasciare vuoto il **nome della pipe** e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager completerà il nome della pipe appropriato dopo aver specificato il **protocollo** e il **Server**</span><span class="sxs-lookup"><span data-stu-id="03456-114">Alternatively, you can leave **Pipe Name** blank and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager will complete the appropriate pipe name after you specify the **Protocol** and **Server**</span></span>  
  
-   <span data-ttu-id="03456-115">Specificare un **Server**.</span><span class="sxs-lookup"><span data-stu-id="03456-115">Specify a **Server**.</span></span> <span data-ttu-id="03456-116">Per un'istanza denominata è possibile specificare un nome di server e un nome di istanza.</span><span class="sxs-lookup"><span data-stu-id="03456-116">For a named instance you can provide a server name and instance name.</span></span>  
  
 <span data-ttu-id="03456-117">Al momento della connessione, tramite il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componente native client vengono letti i valori del nome del server, del protocollo e della pipe dal registro di sistema per il nome alias specificato e viene creato un nome di pipe nel formato `np:\\<computer_name>\pipe\<pipename>` o `np:\\<IPAddress>\pipe\<pipename>` . Per un'istanza denominata, il nome della pipe predefinita è `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query` .</span><span class="sxs-lookup"><span data-stu-id="03456-117">At the time of connection, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client component reads the server, protocol, and pipe name values from the registry for the specified alias name, and creates a pipe name in the format `np:\\<computer_name>\pipe\<pipename>` or `np:\\<IPAddress>\pipe\<pipename>`.For a named instance, the default pipe name is `\\<computer_name>\pipe\MSSQL$<instance_name>\sql\query`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03456-118">Per impostazione predefinita, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall chiude la porta 445.</span><span class="sxs-lookup"><span data-stu-id="03456-118">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Firewall closes port 445 by default.</span></span> <span data-ttu-id="03456-119">Poiché [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comunica sulla porta 445, è necessario aprire nuovamente tale porta se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è configurato per restare in attesa di connessioni client in arrivo mediante Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="03456-119">Because [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] communicates over port 445, you must reopen the port if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to listen for incoming client connections using named pipes.</span></span> <span data-ttu-id="03456-120">Per informazioni sulla configurazione di un firewall, vedere "Procedura: Configurazione di un firewall per l’accesso a SQL Server" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oppure vedere la documentazione relativa al firewall.</span><span class="sxs-lookup"><span data-stu-id="03456-120">For information on configuring a firewall, see "How to: Configure a Firewall for SQL Server Access" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or review your firewall documentation.</span></span>  
  
## <a name="connecting-to-the-local-server"></a><span data-ttu-id="03456-121">Connessione al server locale</span><span class="sxs-lookup"><span data-stu-id="03456-121">Connecting to the Local Server</span></span>  
 <span data-ttu-id="03456-122">Quando si stabilisce una connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione nello stesso computer del client, è possibile utilizzare `(local)` come nome del server.</span><span class="sxs-lookup"><span data-stu-id="03456-122">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the same computer as the client, you can use `(local)`as the server name.</span></span> <span data-ttu-id="03456-123">L'utilizzo di `(local)` non è consigliabile in quanto genera ambiguità, ma può risultare utile se si è sicuri che il client venga eseguito nel computer desiderato.</span><span class="sxs-lookup"><span data-stu-id="03456-123">Using `(local)` is not encouraged because it leads to ambiguity; however it can be useful when the client is known to be running on the intended computer.</span></span> <span data-ttu-id="03456-124">Se, ad esempio, si crea un'applicazione per gli utenti mobili non connessi, ad esempio il personale di vendita, e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verrà eseguito su computer portatili e utilizzato per archiviare dati di progetto, un client che si connette al server (local) si connetterà sempre all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione sul portatile.</span><span class="sxs-lookup"><span data-stu-id="03456-124">For instance, when creating an application for mobile disconnected users, such as a sales force, where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will run on laptop computers and store project data, a client connecting to (local) would always connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the laptop.</span></span> <span data-ttu-id="03456-125">In sostituzione di `localhost` è possibile utilizzare la parola `(local)` o un punto (.).</span><span class="sxs-lookup"><span data-stu-id="03456-125">The word `localhost` or a period (.) can be used in place of `(local)`.</span></span>  
  
## <a name="verifying-your-connection-protocol"></a><span data-ttu-id="03456-126">Verifica del protocollo di connessione</span><span class="sxs-lookup"><span data-stu-id="03456-126">Verifying Your Connection Protocol</span></span>  
 <span data-ttu-id="03456-127">La query seguente restituisce il protocollo utilizzato per la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="03456-127">The following query will return the protocol used for the current connection.</span></span>  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## <a name="examples"></a><span data-ttu-id="03456-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="03456-128">Examples</span></span>  
 <span data-ttu-id="03456-129">Connessione tramite il nome del server alla pipe predefinita:</span><span class="sxs-lookup"><span data-stu-id="03456-129">Connecting by server name to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="03456-130">Connessione tramite indirizzo IP alla pipe predefinita:</span><span class="sxs-lookup"><span data-stu-id="03456-130">Connecting by IP Address to the default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <leave blank>  
Protocol           Named Pipes  
Server             <IPAddress>  
  
```  
  
 <span data-ttu-id="03456-131">Connessione tramite il nome del server a una pipe non predefinita:</span><span class="sxs-lookup"><span data-stu-id="03456-131">Connecting by server name to a non-default pipe:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\unit\app  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="03456-132">Connessione tramite il nome del server a un'istanza denominata:</span><span class="sxs-lookup"><span data-stu-id="03456-132">Connecting by server name to a named instance:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          \\<servername>\pipe\MSSQL$<instancename>\SQL\query  
Protocol           Named Pipes  
Server             <servername>  
  
```  
  
 <span data-ttu-id="03456-133">Connessione al computer locale tramite `localhost`:</span><span class="sxs-lookup"><span data-stu-id="03456-133">Connecting to the local computer using `localhost`:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <blank>  
Protocol           Named Pipes  
Server             localhost  
  
```  
  
 <span data-ttu-id="03456-134">Connessione al computer locale tramite un punto:</span><span class="sxs-lookup"><span data-stu-id="03456-134">Connecting to the local computer using a period:</span></span>  
  
```  
Alias Name         <serveralias>  
Pipe Name          <left blank>  
Protocol           Named Pipes  
Server             .  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="03456-135">Per specificare il protocollo di rete come parametro **SQLCMD** , vedere "procedura: connessione al motore di database utilizzando sqlcmd.exe" nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentazione online di.</span><span class="sxs-lookup"><span data-stu-id="03456-135">To specify the network protocol as a **sqlcmd** parameter, see "How to: Connect to the Database Engine Using sqlcmd.exe" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03456-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03456-136">See Also</span></span>  
 <span data-ttu-id="03456-137">[Creazione di una stringa di connessione valida tramite il protocollo Shared Memory](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="03456-137">[Creating a Valid Connection String Using Shared Memory Protocol](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md) </span></span>  
 <span data-ttu-id="03456-138">[Creazione di una stringa di connessione valida tramite TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span><span class="sxs-lookup"><span data-stu-id="03456-138">[Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md) </span></span>  
 [<span data-ttu-id="03456-139">Scelta di un protocollo di rete</span><span class="sxs-lookup"><span data-stu-id="03456-139">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
