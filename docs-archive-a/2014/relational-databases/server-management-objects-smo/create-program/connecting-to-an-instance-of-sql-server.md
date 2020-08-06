---
title: Connessione a un'istanza di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, connections
- connections [SMO]
- instances of SQL Server, connections
- SMO [SQL Server], connections
ms.assetid: ad3cf354-b2e3-468b-b986-1232e375fd84
author: stevestein
ms.author: sstein
ms.openlocfilehash: efc21451f4a876c6edfe4a2389ca937d11bc5c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637208"
---
# <a name="connecting-to-an-instance-of-sql-server"></a><span data-ttu-id="67ebd-102">Connessione a un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="67ebd-102">Connecting to an Instance of SQL Server</span></span>
  <span data-ttu-id="67ebd-103">Il primo passaggio di programmazione in un' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] applicazione SMO (Management Objects) consiste nel creare un'istanza dell' <xref:Microsoft.SqlServer.Management.Smo.Server> oggetto e stabilire la connessione a un'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67ebd-103">The first programming step in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) application is to create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and to establish its connection to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="67ebd-104">È possibile creare un'istanza dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> e stabilire una connessione all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in tre modi diversi.</span><span class="sxs-lookup"><span data-stu-id="67ebd-104">You can create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and establish a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in three ways.</span></span> <span data-ttu-id="67ebd-105">Il primo metodo consiste nell'utilizzare una variabile oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> per fornire le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-105">The first is using a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable to provide the connection information.</span></span> <span data-ttu-id="67ebd-106">Il secondo consiste nel fornire le informazioni di connessione impostando in modo esplicito le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="67ebd-106">The second is to provide the connection information by explicitly setting the <xref:Microsoft.SqlServer.Management.Smo.Server> object properties.</span></span> <span data-ttu-id="67ebd-107">Il terzo consiste infine nel passare il nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel costruttore dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="67ebd-107">The third is to pass the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span>  
  
 <span data-ttu-id="67ebd-108">**Utilizzo di un oggetto ServerConnection**</span><span class="sxs-lookup"><span data-stu-id="67ebd-108">**Using a ServerConnection object**</span></span>  
  
 <span data-ttu-id="67ebd-109">Il vantaggio dell'utilizzo della variabile oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> è costituito dal fatto che consente di riutilizzare le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-109">The advantage of using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable is that the connection information can be reused.</span></span> <span data-ttu-id="67ebd-110">Dichiarare una variabile oggetto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="67ebd-110">Declare a <xref:Microsoft.SqlServer.Management.Smo.Server> object variable.</span></span> <span data-ttu-id="67ebd-111">Dichiarare quindi un oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> e impostare proprietà con le informazioni di connessione, quali il nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e la modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-111">Then, declare a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object and set properties with connection information such as the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and the authentication mode.</span></span> <span data-ttu-id="67ebd-112">Passare quindi la variabile oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> come parametro al costruttore dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="67ebd-112">Then, pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable as a parameter to the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span> <span data-ttu-id="67ebd-113">Non è consigliabile condividere connessioni tra diversi oggetti server contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="67ebd-113">It is not recommended to share connections between different server objects at the same time.</span></span> <span data-ttu-id="67ebd-114">Utilizzare il metodo <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> per ottenere una copia delle impostazioni di connessione esistenti.</span><span class="sxs-lookup"><span data-stu-id="67ebd-114">Use the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to get a copy of the existing connection settings.</span></span>  
  
 <span data-ttu-id="67ebd-115">**Impostazione esplicita delle proprietà dell'oggetto server**</span><span class="sxs-lookup"><span data-stu-id="67ebd-115">**Setting Server object properties explicitly**</span></span>  
  
 <span data-ttu-id="67ebd-116">In alternativa, è possibile dichiarare la variabile oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> e chiamare il costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="67ebd-116">Alternatively, you can declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and call the default constructor.</span></span> <span data-ttu-id="67ebd-117">In questo modo, l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> tenta di connettersi all'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con tutte le impostazioni di connessione predefinite.</span><span class="sxs-lookup"><span data-stu-id="67ebd-117">As is, the <xref:Microsoft.SqlServer.Management.Smo.Server> object tries to connect to the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with all the default connection settings.</span></span>  
  
 <span data-ttu-id="67ebd-118">**Definizione del nome dell'istanza di SQL Server nel costruttore dell'oggetto server**</span><span class="sxs-lookup"><span data-stu-id="67ebd-118">**Providing the SQL Server instance name in the Server object constructor**</span></span>  
  
 <span data-ttu-id="67ebd-119">Dichiarare la variabile oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> e passare il nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] come parametro di stringa nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="67ebd-119">Declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and pass the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance name as a string parameter in the constructor.</span></span> <span data-ttu-id="67ebd-120">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> stabilisce una connessione con l'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con le impostazioni di connessione predefinite.</span><span class="sxs-lookup"><span data-stu-id="67ebd-120">The <xref:Microsoft.SqlServer.Management.Smo.Server> object establishes a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the default connection settings.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="67ebd-121">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="67ebd-121">Connection Pooling</span></span>  
 <span data-ttu-id="67ebd-122">Non è in genere necessario chiamare il metodo <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="67ebd-122">It is typically not required to call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span> <span data-ttu-id="67ebd-123">SMO stabilirà automaticamente una connessione laddove necessario e rilascerà la connessione al pool di connessioni dopo avere completato l'esecuzione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="67ebd-123">SMO will automatically establish a connection when required, and release the connection to the connection pool after it has finished performing operations.</span></span> <span data-ttu-id="67ebd-124">Quando viene chiamato il metodo <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>, la connessione non viene rilasciata al pool.</span><span class="sxs-lookup"><span data-stu-id="67ebd-124">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not released to the pool.</span></span> <span data-ttu-id="67ebd-125">È necessaria una chiamata esplicita al metodo <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> per rilasciare la connessione al pool.</span><span class="sxs-lookup"><span data-stu-id="67ebd-125">An explicit call to the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method is required to release the connection to the pool.</span></span> <span data-ttu-id="67ebd-126">È inoltre possibile richiedere una connessione non in pool impostando la proprietà <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="67ebd-126">Additionally, you can request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="multithreaded-applications"></a><span data-ttu-id="67ebd-127">Applicazioni a thread multipli</span><span class="sxs-lookup"><span data-stu-id="67ebd-127">Multithreaded Applications</span></span>  
 <span data-ttu-id="67ebd-128">Per le applicazioni multithreading, in ogni thread è necessario utilizzare un oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> separato.</span><span class="sxs-lookup"><span data-stu-id="67ebd-128">For multithreaded applications, a separate <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object should be used in each thread.</span></span>  
  
## <a name="connecting-to-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="67ebd-129">Connessione a un'istanza di SQL Server per RMO</span><span class="sxs-lookup"><span data-stu-id="67ebd-129">Connecting to an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="67ebd-130">RMO (Replication Management Objects) utilizza un metodo leggermente diverso da SMO per connettersi a un server di replica.</span><span class="sxs-lookup"><span data-stu-id="67ebd-130">Replication Management Objects (RMO) uses a slightly different method from SMO to connect to a replication server.</span></span>  
  
 <span data-ttu-id="67ebd-131">Gli oggetti di programmazione RMO richiedono l'esecuzione di una connessione a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> implementato dallo spazio dei nomi `Microsoft.SqlServer.Management.Common`.</span><span class="sxs-lookup"><span data-stu-id="67ebd-131">RMO programming objects require that a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is made by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object implemented by the `Microsoft.SqlServer.Management.Common` namespace.</span></span> <span data-ttu-id="67ebd-132">Questa connessione al server viene stabilita indipendentemente da un oggetto di programmazione RMO.</span><span class="sxs-lookup"><span data-stu-id="67ebd-132">This connection to the server is made independently of an RMO programming object.</span></span> <span data-ttu-id="67ebd-133">La connessione viene quindi passata all'oggetto RMO durante la creazione dell'istanza o tramite l'assegnazione alla proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="67ebd-133">It is then it is passed to the RMO object either during instance creation or by assignment to the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property of the object.</span></span> <span data-ttu-id="67ebd-134">In questo modo, un oggetto di programmazione RMO e le istanze dell'oggetto connessione possono essere creati e gestiti separatamente e un singolo oggetto connessione può essere riutilizzato con più oggetti di programmazione RMO.</span><span class="sxs-lookup"><span data-stu-id="67ebd-134">In this manner, an RMO programming object and the connection object instances can be created and managed separately, and a single connection object can be reused with multiple RMO programming objects.</span></span> <span data-ttu-id="67ebd-135">Le regole seguenti sono valide per le connessioni a un server di replica:</span><span class="sxs-lookup"><span data-stu-id="67ebd-135">The following rules apply for connections to a replication server:</span></span>  
  
-   <span data-ttu-id="67ebd-136">Tutte le proprietà per la connessione vengono definite per un oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> specificato.</span><span class="sxs-lookup"><span data-stu-id="67ebd-136">All properties for the connection are defined for a specified <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="67ebd-137">Ogni connessione a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deve disporre del relativo oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="67ebd-137">Each connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must have its own <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="67ebd-138">Tutte le informazioni di autenticazione che consentono di stabilire la connessione e accedere correttamente al server vengono fornite nell'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="67ebd-138">All authentication information to make the connection and successfully log on to the server is supplied in the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="67ebd-139">Per impostazione predefinita, le connessioni vengono stabilite tramite l'autenticazione di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="67ebd-139">By default, connections are made by using Microsoft Windows Authentication.</span></span> <span data-ttu-id="67ebd-140">Per utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], la proprietà <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> deve essere impostata su False e <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> e <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> devono essere impostate su un account di accesso e una password di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] validi.</span><span class="sxs-lookup"><span data-stu-id="67ebd-140">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> must be set to False and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> must be set to a valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logon and password.</span></span> <span data-ttu-id="67ebd-141">Le credenziali di sicurezza devono essere sempre archiviate e gestite in modo protetto, e fornite in fase di esecuzione laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="67ebd-141">Security credentials must always be stored and handled securely, and supplied at run time whenever possible.</span></span>  
  
-   <span data-ttu-id="67ebd-142">Il metodo <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> deve essere chiamato prima di passare la connessione a qualsiasi oggetto di programmazione RMO.</span><span class="sxs-lookup"><span data-stu-id="67ebd-142">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method must be called before passing the connection to any RMO programming object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="67ebd-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="67ebd-143">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="67ebd-144">Connessione all'istanza locale di SQL Server tramite l'autenticazione di Windows in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67ebd-144">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="67ebd-145">La connessione all'istanza locale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] non richiede molto codice,</span><span class="sxs-lookup"><span data-stu-id="67ebd-145">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="67ebd-146">ma si basa al contrario sulle impostazioni predefinite per il metodo di autenticazione e per il server.</span><span class="sxs-lookup"><span data-stu-id="67ebd-146">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="67ebd-147">La prima operazione che richiede il recupero di dati comporterà la creazione di una connessione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-147">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="67ebd-148">Questo esempio è [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] codice .NET che si connette all'istanza locale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="67ebd-148">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB1](SMO How to#SMO_VB1)]  -->  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="67ebd-149">Connessione all'istanza locale di SQL Server tramite l'autenticazione di Windows in Visual C#</span><span class="sxs-lookup"><span data-stu-id="67ebd-149">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="67ebd-150">La connessione all'istanza locale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] non richiede molto codice,</span><span class="sxs-lookup"><span data-stu-id="67ebd-150">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="67ebd-151">ma si basa al contrario sulle impostazioni predefinite per il metodo di autenticazione e per il server.</span><span class="sxs-lookup"><span data-stu-id="67ebd-151">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="67ebd-152">La prima operazione che richiede il recupero di dati comporterà la creazione di una connessione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-152">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="67ebd-153">Questo esempio include il codice Visual C# .NET per la connessione all'istanza locale di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="67ebd-153">This example is Visual C# .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//The connection is established when a property is requested.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="67ebd-154">Connessione a un'istanza remota di SQL Server tramite l'autenticazione di Windows in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67ebd-154">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="67ebd-155">Quando ci si connette a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di Windows, non è necessario specificare il tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-155">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="67ebd-156">L'autenticazione di Windows rappresenta l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="67ebd-156">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="67ebd-157">Questo esempio è [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] codice .NET che si connette all'istanza remota di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="67ebd-157">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="67ebd-158">La variabile di stringa *strServer* contiene il nome dell'istanza remota.</span><span class="sxs-lookup"><span data-stu-id="67ebd-158">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB2](SMO How to#SMO_VB2)]  -->  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="67ebd-159">Connessione a un'istanza remota di SQL Server tramite l'autenticazione di Windows in Visual C#</span><span class="sxs-lookup"><span data-stu-id="67ebd-159">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="67ebd-160">Quando ci si connette a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di Windows, non è necessario specificare il tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-160">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="67ebd-161">L'autenticazione di Windows rappresenta l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="67ebd-161">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="67ebd-162">Questo esempio include il codice Visual C# .NET per la connessione all'istanza remota di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="67ebd-162">This example is Visual C# .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="67ebd-163">La variabile di stringa *strServer* contiene il nome dell'istanza remota.</span><span class="sxs-lookup"><span data-stu-id="67ebd-163">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
```  
{   
//Connect to a remote instance of SQL Server.   
Server srv;   
//The strServer string variable contains the name of a remote instance of SQL Server.   
srv = new Server(strServer);   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-basic"></a><span data-ttu-id="67ebd-164">Connessione a un'istanza di SQL Server tramite l'autenticazione di SQL Server in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67ebd-164">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual Basic</span></span>  
 <span data-ttu-id="67ebd-165">Quando ci si connette a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è necessario specificare il tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-165">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="67ebd-166">In questo esempio viene illustrato il metodo alternativo per dichiarare una variabile oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> che consente il riutilizzo delle informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-166">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="67ebd-167">L'esempio è il [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] codice .NET che illustra come connettersi a remote e *mentre oggetto vPassword* contengono l'accesso e la password.</span><span class="sxs-lookup"><span data-stu-id="67ebd-167">The example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll  
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      Dim sqlServerLogin As [String] = "user_id"  
      Dim password As [String] = "pwd"  
      Dim instanceName As [String] = "instance_name"  
      Dim remoteSvrName As [String] = "remote_server_name"  
  
      ' Connecting to an instance of SQL Server using SQL Server Authentication  
      Dim srv1 As New Server()   ' connects to default instance  
      srv1.ConnectionContext.LoginSecure = False   ' set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin  
      srv1.ConnectionContext.Password = password  
      Console.WriteLine(srv1.Information.Version)   ' connection is established  
  
      ' Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      Dim srvConn As New ServerConnection()  
      srvConn.ServerInstance = ".\" & instanceName   ' connects to named instance  
      srvConn.LoginSecure = False   ' set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin  
      srvConn.Password = password  
      Dim srv2 As New Server(srvConn)  
      Console.WriteLine(srv2.Information.Version)   ' connection is established  
  
      ' For remote connection, remote server name / ServerInstance needs to be specified  
      Dim srvConn2 As New ServerConnection(remoteSvrName)  
      srvConn2.LoginSecure = False  
      srvConn2.Login = sqlServerLogin  
      srvConn2.Password = password  
      Dim srv3 As New Server(srvConn2)  
      Console.WriteLine(srv3.Information.Version)   ' connection is established  
   End Sub  
End Class  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-c"></a><span data-ttu-id="67ebd-168">Connessione a un'istanza di SQL Server tramite l'autenticazione di SQL Server in Visual C#</span><span class="sxs-lookup"><span data-stu-id="67ebd-168">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual C#</span></span>  
 <span data-ttu-id="67ebd-169">Quando ci si connette a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è necessario specificare il tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-169">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="67ebd-170">In questo esempio viene illustrato il metodo alternativo per dichiarare una variabile oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> che consente il riutilizzo delle informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="67ebd-170">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="67ebd-171">L'esempio è il codice Visual C# .NET che illustra come connettersi a remote e *mentre oggetto vPassword* contengono l'accesso e la password.</span><span class="sxs-lookup"><span data-stu-id="67ebd-171">The example is Visual C# .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll  
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {   
      String sqlServerLogin = "user_id";  
      String password = "pwd";  
      String instanceName = "instance_name";  
      String remoteSvrName = "remote_server_name";  
  
      // Connecting to an instance of SQL Server using SQL Server Authentication  
      Server srv1 = new Server();   // connects to default instance  
      srv1.ConnectionContext.LoginSecure = false;   // set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin;  
      srv1.ConnectionContext.Password = password;  
      Console.WriteLine(srv1.Information.Version);   // connection is established  
  
      // Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      ServerConnection srvConn = new ServerConnection();  
      srvConn.ServerInstance = @".\" + instanceName;   // connects to named instance  
      srvConn.LoginSecure = false;   // set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin;  
      srvConn.Password = password;  
      Server srv2 = new Server(srvConn);  
      Console.WriteLine(srv2.Information.Version);   // connection is established  
  
      // For remote connection, remote server name / ServerInstance needs to be specified  
      ServerConnection srvConn2 = new ServerConnection(remoteSvrName);  
      srvConn2.LoginSecure = false;  
      srvConn2.Login = sqlServerLogin;  
      srvConn2.Password = password;  
      Server srv3 = new Server(srvConn2);  
      Console.WriteLine(srv3.Information.Version);   // connection is established  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="67ebd-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67ebd-172">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
