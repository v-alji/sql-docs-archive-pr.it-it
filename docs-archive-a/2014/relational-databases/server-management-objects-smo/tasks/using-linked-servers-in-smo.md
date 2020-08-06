---
title: Utilizzo di server collegati in SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- linked servers [SQL Server], SMO
ms.assetid: 0ea8837b-2596-4df1-b065-3bb717c9f22c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 58804e2be1edfa685a57f56c173c77a50e0f9126
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624570"
---
# <a name="using-linked-servers-in-smo"></a><span data-ttu-id="47dda-102">Utilizzo di server collegati in SMO</span><span class="sxs-lookup"><span data-stu-id="47dda-102">Using Linked Servers in SMO</span></span>
  <span data-ttu-id="47dda-103">Un server collegato rappresenta un'origine dati OLE DB in un server remoto.</span><span class="sxs-lookup"><span data-stu-id="47dda-103">A linked server represents an OLE DB data source on a remote server.</span></span> <span data-ttu-id="47dda-104">Le origini dati OLE DB remote vengono collegate all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="47dda-104">Remote OLE DB data sources are linked to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span>  
  
 <span data-ttu-id="47dda-105">I server di database remoti possono essere collegati all'istanza corrente di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite un provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="47dda-105">Remote database servers can be linked to the current instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using an OLE DB Provider.</span></span> <span data-ttu-id="47dda-106">In SMO i server collegati sono rappresentati dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="47dda-106">In SMO, linked servers are represented by the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="47dda-107">La proprietà <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> fa riferimento a una raccolta di oggetti <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin></span><span class="sxs-lookup"><span data-stu-id="47dda-107">The <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> property references a collection of <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin> objects.</span></span> <span data-ttu-id="47dda-108">in cui sono archiviate le credenziali di accesso necessarie per stabilire una connessione con il server collegato.</span><span class="sxs-lookup"><span data-stu-id="47dda-108">These store the logon credentials that are required to establish a connection with the linked server.</span></span>  
  
## <a name="ole-db-providers"></a><span data-ttu-id="47dda-109">Provider OLE DB</span><span class="sxs-lookup"><span data-stu-id="47dda-109">OLE-DB Providers</span></span>  
 <span data-ttu-id="47dda-110">In SMO i provider OLE DB installati sono rappresentati da una raccolta di oggetti <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings>.</span><span class="sxs-lookup"><span data-stu-id="47dda-110">In SMO, installed OLE-DB providers are represented by a collection of <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47dda-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="47dda-111">Example</span></span>  
 <span data-ttu-id="47dda-112">Per l'esempio di codice seguente, è necessario selezionare l'ambiente, il modello e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47dda-112">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="47dda-113">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e alla [creazione di un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="47dda-113">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-basic"></a><span data-ttu-id="47dda-114">Creazione di un collegamento a un server del provider OLE DB in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47dda-114">Creating a link to an OLE-DB Provider Server in Visual Basic</span></span>  
 <span data-ttu-id="47dda-115">Nell'esempio di codice viene illustrato come creare un collegamento a un'origine dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB eterogenea tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="47dda-115">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="47dda-116">Specificando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] come nome del prodotto, è possibile accedere ai dati nel server collegato utilizzando il [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider OLE DB client, che è il provider OLE DB ufficiale per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47dda-116">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLinkedServers1](SMO How to#SMO_VBLinkedServers1)]  -->  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-c"></a><span data-ttu-id="47dda-117">Creazione di un collegamento a un server del provider OLE DB in Visual C#</span><span class="sxs-lookup"><span data-stu-id="47dda-117">Creating a link to an OLE-DB Provider Server in Visual C#</span></span>  
 <span data-ttu-id="47dda-118">Nell'esempio di codice viene illustrato come creare un collegamento a un'origine dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB eterogenea tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="47dda-118">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="47dda-119">Specificando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] come nome di prodotto, è possibile accedere ai dati nel server collegato tramite il provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client, ovvero il provider OLE DB ufficiale per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47dda-119">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
{   
   Server srv = new Server();   
   //Create a linked server.   
   LinkedServer lsrv = default(LinkedServer);   
   lsrv = new LinkedServer(srv, "OLEDBSRV");   
   //When the product name is SQL Server the remaining properties are   
   //not required to be set.   
   lsrv.ProductName = "SQL Server";   
   lsrv.Create();   
}   
```  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-powershell"></a><span data-ttu-id="47dda-120">Creazione di un collegamento a un server del provider OLE DB in PowerShell</span><span class="sxs-lookup"><span data-stu-id="47dda-120">Creating a link to an OLE-DB Provider Server in PowerShell</span></span>  
 <span data-ttu-id="47dda-121">Nell'esempio di codice viene illustrato come creare un collegamento a un'origine dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB eterogenea tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="47dda-121">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="47dda-122">Specificando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] come nome di prodotto, è possibile accedere ai dati nel server collegato tramite il provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client, ovvero il provider OLE DB ufficiale per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47dda-122">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$svr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a linked server object which corresponds to an OLEDB type of SQL server product  
$lsvr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.LinkedServer -ArgumentList $svr,"OLEDBSRV"  
  
#When the product name is SQL Server the remaining properties are not required to be set.
$lsvr.ProductName = "SQL Server"
  
#Create the Database Object  
$lsvr.Create()
```  
