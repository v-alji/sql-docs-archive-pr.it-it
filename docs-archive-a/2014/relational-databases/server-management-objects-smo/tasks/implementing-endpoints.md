---
title: Implementazione di endpoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- endpoints [SMO]
ms.assetid: f8674dbb-9bc0-488f-9def-e9e0ce1ddf86
author: stevestein
ms.author: sstein
ms.openlocfilehash: 293a661c6e1ad6f6139e30e0824e99686af98f90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723643"
---
# <a name="implementing-endpoints"></a><span data-ttu-id="d1c95-102">Implementazione di endpoint</span><span class="sxs-lookup"><span data-stu-id="d1c95-102">Implementing Endpoints</span></span>
  <span data-ttu-id="d1c95-103">Un endpoint è un servizio che può restare in attesa di richieste a livello nativo.</span><span class="sxs-lookup"><span data-stu-id="d1c95-103">An endpoint is a service that can listen natively for requests.</span></span> <span data-ttu-id="d1c95-104">In SMO sono supportati vari tipi di endpoint tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Endpoint>.</span><span class="sxs-lookup"><span data-stu-id="d1c95-104">SMO supports various types of endpoints by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object.</span></span> <span data-ttu-id="d1c95-105">È possibile creare un servizio di endpoint che gestisce un tipo specifico di payload, il quale utilizza un protocollo specifico, creando un'istanza di un oggetto <xref:Microsoft.SqlServer.Management.Smo.Endpoint> e impostandone le proprietà.</span><span class="sxs-lookup"><span data-stu-id="d1c95-105">You can create an endpoint service that handles a specific type of payload, which uses a specific protocol, by creating an instance of an <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object and setting its properties.</span></span>  
  
 <span data-ttu-id="d1c95-106">La proprietà <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Endpoint> può essere utilizzata per specificare uno dei seguenti tipi di payload:</span><span class="sxs-lookup"><span data-stu-id="d1c95-106">The <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object can be used to specify on of the following payload types:</span></span>  
  
-   <span data-ttu-id="d1c95-107">Mirroring del database</span><span class="sxs-lookup"><span data-stu-id="d1c95-107">Database mirroring</span></span>  
  
-   <span data-ttu-id="d1c95-108">SOAP (il supporto per gli endpoint SOAP è presente in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] e nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="d1c95-108">SOAP (support for SOAP endpoints is present in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] and earlier [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] versions)</span></span>  
  
-   <span data-ttu-id="d1c95-109">Broker di servizio</span><span class="sxs-lookup"><span data-stu-id="d1c95-109">Service Broker</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)]  
  
 <span data-ttu-id="d1c95-110">La proprietà <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> può inoltre essere utilizzata per specificare i due protocolli supportati seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1c95-110">Also, the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property can be used to specify the following two supported protocols:</span></span>  
  
-   <span data-ttu-id="d1c95-111">Protocollo HTTP</span><span class="sxs-lookup"><span data-stu-id="d1c95-111">HTTP protocol</span></span>  
  
-   <span data-ttu-id="d1c95-112">Protocollo TCP</span><span class="sxs-lookup"><span data-stu-id="d1c95-112">TCP protocol</span></span>  
  
 <span data-ttu-id="d1c95-113">Avendo specificato il tipo di payload, il payload effettivo può essere impostato tramite la proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1c95-113">Having specified the type of payload, the actual payload can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A> object property.</span></span> <span data-ttu-id="d1c95-114">La proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Payload> fornisce un riferimento a un oggetto payload del tipo specificato, per cui è possibile modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="d1c95-114">The <xref:Microsoft.SqlServer.Management.Smo.Payload> object property provides a reference to a payload object of the specified type, for which the properties can be modified.</span></span>  
  
 <span data-ttu-id="d1c95-115">Per l'oggetto <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload>, è necessario specificare il ruolo di mirroring e se è abilitata o meno la crittografia.</span><span class="sxs-lookup"><span data-stu-id="d1c95-115">For the <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload> object, you must specify the mirroring role and whether encryption is enabled.</span></span> <span data-ttu-id="d1c95-116">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> richiede informazioni sull'inoltro di messaggi, sul numero massimo di connessioni consentite e sulla modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d1c95-116">The <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> object requires information about message forwarding, maximum number of connections allowed and the authentication mode.</span></span> <span data-ttu-id="d1c95-117">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> richiede l'impostazione di varie proprietà tra cui la proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> che specifica i metodi di payload SOAP disponibili ai client (stored procedure e funzioni definite dall'utente).</span><span class="sxs-lookup"><span data-stu-id="d1c95-117">The <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> object requires various properties to be set including the <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> object property that specifies the SOAP payload methods available to clients (stored procedures and user-defined functions).</span></span>  
  
 <span data-ttu-id="d1c95-118">Analogamente, il protocollo può essere impostato tramite la proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> che fa riferimento a un oggetto protocollo del tipo specificato dalla proprietà <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1c95-118">Similarly, the actual protocol can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> object property that references a protocol object of the type specified by <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property.</span></span> <span data-ttu-id="d1c95-119">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> richiede un elenco di indirizzi IP con restrizioni e informazioni relative a porte, siti Web e autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d1c95-119">The <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> object requires a list of restricted IP addresses, and port, website, and authentication information.</span></span> <span data-ttu-id="d1c95-120">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> richiede inoltre un elenco di indirizzi IP con restrizioni e informazioni relative alle porte.</span><span class="sxs-lookup"><span data-stu-id="d1c95-120">The <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> object also requires a list of restricted IP addresses and port information.</span></span>  
  
 <span data-ttu-id="d1c95-121">Quando l'endpoint è stato creato e definito completamente, è possibile concedere, revocare e negare l'accesso a utenti, gruppi, ruoli e account di accesso del database.</span><span class="sxs-lookup"><span data-stu-id="d1c95-121">When the endpoint has been created and fully defined, access can be granted to, revoked from, and denied to database users, groups, roles, and logons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1c95-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1c95-122">Example</span></span>  
 <span data-ttu-id="d1c95-123">Per l'esempio di codice seguente, è necessario selezionare l'ambiente, il modello e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d1c95-123">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="d1c95-124">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e alla [creazione di un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="d1c95-124">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-basic"></a><span data-ttu-id="d1c95-125">Creazione di un servizio di endpoint del mirroring del database in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1c95-125">Creating a Database Mirroring Endpoint Service in Visual Basic</span></span>  
 <span data-ttu-id="d1c95-126">Nell'esempio di codice viene illustrato come creare un endpoint del mirroring del database in SMO.</span><span class="sxs-lookup"><span data-stu-id="d1c95-126">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="d1c95-127">È necessario eseguire questa operazione prima di creare un database mirror.</span><span class="sxs-lookup"><span data-stu-id="d1c95-127">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="d1c95-128">Utilizzare <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> e altre proprietà nell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> per creare un mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="d1c95-128">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEndpoints1](SMO How to#SMO_VBEndpoints1)]  -->  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-c"></a><span data-ttu-id="d1c95-129">Creazione di un servizio di endpoint del mirroring del database in Visual C#</span><span class="sxs-lookup"><span data-stu-id="d1c95-129">Creating a Database Mirroring Endpoint Service in Visual C#</span></span>  
 <span data-ttu-id="d1c95-130">Nell'esempio di codice viene illustrato come creare un endpoint del mirroring del database in SMO.</span><span class="sxs-lookup"><span data-stu-id="d1c95-130">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="d1c95-131">È necessario eseguire questa operazione prima di creare un database mirror.</span><span class="sxs-lookup"><span data-stu-id="d1c95-131">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="d1c95-132">Utilizzare <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> e altre proprietà nell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> per creare un mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="d1c95-132">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```csharp
{  
            //Set up a database mirroring endpoint on the server before   
        //setting up a database mirror.   
        //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Define an Endpoint object variable for database mirroring.   
            Endpoint ep = default(Endpoint);  
            ep = new Endpoint(srv, "Mirroring_Endpoint");  
            ep.ProtocolType = ProtocolType.Tcp;  
            ep.EndpointType = EndpointType.DatabaseMirroring;  
            //Specify the protocol ports.   
            ep.Protocol.Http.SslPort = 5024;  
            ep.Protocol.Tcp.ListenerPort = 6666;  
            //Specify the role of the payload.   
            ep.Payload.DatabaseMirroring.ServerMirroringRole = ServerMirroringRole.All;  
            //Create the endpoint on the instance of SQL Server.   
            ep.Create();  
            //Start the endpoint.   
            ep.Start();  
            Console.WriteLine(ep.EndpointState);  
        }  
```  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-powershell"></a><span data-ttu-id="d1c95-133">Creazione di un servizio di endpoint del mirroring del database in PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1c95-133">Creating a Database Mirroring Endpoint Service in PowerShell</span></span>  
 <span data-ttu-id="d1c95-134">Nell'esempio di codice viene illustrato come creare un endpoint del mirroring del database in SMO.</span><span class="sxs-lookup"><span data-stu-id="d1c95-134">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="d1c95-135">È necessario eseguire questa operazione prima di creare un database mirror.</span><span class="sxs-lookup"><span data-stu-id="d1c95-135">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="d1c95-136">Utilizzare <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> e altre proprietà nell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> per creare un mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="d1c95-136">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get a new endpoint to congure and add  
$ep = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Endpoint -argumentlist $srv,"Mirroring_Endpoint"  
  
#Set some properties  
$ep.ProtocolType = [Microsoft.SqlServer.Management.SMO.ProtocolType]::Tcp  
$ep.EndpointType = [Microsoft.SqlServer.Management.SMO.EndpointType]::DatabaseMirroring  
$ep.Protocol.Http.SslPort = 5024  
$ep.Protocol.Tcp.ListenerPort = 6666 #inline comment  
$ep.Payload.DatabaseMirroring.ServerMirroringRole = [Microsoft.SqlServer.Management.SMO.ServerMirroringRole]::All  
  
# Create the endpoint on the instance  
$ep.Create()  
  
# Start the endpoint  
$ep.Start()  
  
# Report its state  
$ep.EndpointState;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1c95-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1c95-137">See Also</span></span>  
 [<span data-ttu-id="d1c95-138">Endpoint del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d1c95-138">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
