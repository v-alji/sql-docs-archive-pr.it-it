---
title: Disconnessione da un'istanza di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, disconnecting
- SMO [SQL Server], disconnecting
- instances of SQL Server, disconnecting
- disconnecting [SMO]
ms.assetid: 4ca7f7eb-6b3f-4c73-ac63-88afa8570b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3514fce8fb8f1ccc8bd1b54acfa27825eaebbd34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637206"
---
# <a name="disconnecting-from-an-instance-of-sql-server"></a><span data-ttu-id="39399-102">Disconnessione da un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="39399-102">Disconnecting from an Instance of SQL Server</span></span>
  <span data-ttu-id="39399-103">Non è richiesta la chiusura e la disconnessione manuale degli oggetti SMO ( [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects).</span><span class="sxs-lookup"><span data-stu-id="39399-103">Manually closing and disconnecting [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects is not required.</span></span> <span data-ttu-id="39399-104">Le connessioni vengono aperte e chiuse in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="39399-104">Connections are opened and closed as required.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="39399-105">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="39399-105">Connection Pooling</span></span>  
 <span data-ttu-id="39399-106">Quando viene chiamato il metodo <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>, la connessione non viene rilasciata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="39399-106">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not automatically released.</span></span> <span data-ttu-id="39399-107">Per rilasciare la connessione nel pool di connessioni, è necessario che il metodo <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> venga richiamato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="39399-107">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method must be called explicitly to release the connection to the connection pool.</span></span> <span data-ttu-id="39399-108">È inoltre possibile richiedere una connessione non in pool.</span><span class="sxs-lookup"><span data-stu-id="39399-108">Also, you can request a non-pooled connection.</span></span> <span data-ttu-id="39399-109">Per eseguire questa operazione, impostare la proprietà <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> della proprietà <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> che fa riferimento all'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="39399-109">You do this by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property that references the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="disconnecting-from-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="39399-110">Disconnessione da un'istanza di SQL Server per RMO</span><span class="sxs-lookup"><span data-stu-id="39399-110">Disconnecting from an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="39399-111">La chiusura delle connessioni al server quando si programma con RMO funziona in modo leggermente diverso da SMO.</span><span class="sxs-lookup"><span data-stu-id="39399-111">Closing server connections when you are programming with RMO works slightly different from SMO.</span></span>  
  
 <span data-ttu-id="39399-112">Poiché la connessione al server per un oggetto RMO viene gestita dall' <xref:Microsoft.SqlServer.Management.Common.ServerConnection> oggetto, questo oggetto viene utilizzato anche per la disconnessione da un'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando si programma utilizzando RMO.</span><span class="sxs-lookup"><span data-stu-id="39399-112">Because the server connection for an RMO object is maintained by the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, this object is also used when disconnecting from an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when you program by using RMO.</span></span> <span data-ttu-id="39399-113">Per chiudere una connessione tramite l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, chiamare il metodo <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> dell'oggetto RMO.</span><span class="sxs-lookup"><span data-stu-id="39399-113">To close a connection by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method of the RMO object.</span></span> <span data-ttu-id="39399-114">Dopo che è stata chiusa la connessione, gli oggetti RMO non possono essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="39399-114">After the connection has been closed, RMO objects cannot be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39399-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="39399-115">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-basic"></a><span data-ttu-id="39399-116">Chiusura e disconnessione di un oggetto SMO in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39399-116">Closing and Disconnecting an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="39399-117">In questo esempio di codice viene illustrato come richiedere una connessione non in pool impostando la proprietà <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> della proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="39399-117">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB4](SMO How to#SMO_VB4)]  -->  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-c"></a><span data-ttu-id="39399-118">Chiusura e disconnessione di un oggetto SMO in Visual C#</span><span class="sxs-lookup"><span data-stu-id="39399-118">Closing and Disconnecting an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="39399-119">In questo esempio di codice viene illustrato come richiedere una connessione non in pool impostando la proprietà <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> della proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="39399-119">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
//Disable automatic disconnection.   
srv.ConnectionContext.AutoDisconnectMode = AutoDisconnectMode.NoAutoDisconnect;   
//Connect to the local, default instance of SQL Server.   
srv.ConnectionContext.Connect();   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
//Disconnect explicitly.   
srv.ConnectionContext.Disconnect();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="39399-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39399-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
