---
title: Aggiunta di connessioni a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- connection managers [Integration Services], packages
- Integration Services packages, connections
- connections [Integration Services], packages
- SSIS packages, connections
- packages [Integration Services], connections
- intrinsic properties [Integration Services]
- SQL Server Integration Services packages, connections
- ConnectionManager class
- SSIS connection managers
- adding package connections
ms.assetid: d90716d1-4c65-466c-b82c-4aabbee1e3e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5952221dbf2689d2328695baf965ce884dc07fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627358"
---
# <a name="adding-connections-programmatically"></a><span data-ttu-id="48061-102">Aggiunta di connessioni a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="48061-102">Adding Connections Programmatically</span></span>
  <span data-ttu-id="48061-103">La classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> rappresenta le connessioni fisiche alle origini dati esterne.</span><span class="sxs-lookup"><span data-stu-id="48061-103">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class represents physical connections to external data sources.</span></span> <span data-ttu-id="48061-104">La classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> isola i dettagli di implementazione della connessione dal runtime.</span><span class="sxs-lookup"><span data-stu-id="48061-104">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class isolates the implementation details of the connection from the runtime.</span></span> <span data-ttu-id="48061-105">In questo modo il runtime è in grado di interagire con ogni gestione connessione in modo coerente e stimabile.</span><span class="sxs-lookup"><span data-stu-id="48061-105">This enables the runtime to interact with each connection manager in a consistent and predictable manner.</span></span> <span data-ttu-id="48061-106">Le gestioni connessione contengono un set di proprietà predefinite comuni a tutte le connessioni, ad esempio <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="48061-106">Connection managers contain a set of stock properties that all connections have in common, such as the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span></span> <span data-ttu-id="48061-107">Le proprietà <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, tuttavia, sono in genere le uniche necessarie per configurare una gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="48061-107">However, the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> properties are ordinarily the only properties required to configure a connection manager.</span></span> <span data-ttu-id="48061-108">A differenza di altri paradigmi di programmazione, in cui le classi di connessione espongono metodi quali `Open` o `Connect` per stabilire fisicamente una connessione all'origine dati, il motore di run-time gestisce tutte le connessioni per il pacchetto mentre è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="48061-108">Unlike other programming paradigms, where connection classes expose methods such as `Open` or `Connect` to physically establish a connection to the data source, the run-time engine manages all the connections for the package while it runs.</span></span>  
  
 <span data-ttu-id="48061-109">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Connections> è una raccolta delle gestioni connessione aggiunte a tale pacchetto e disponibili per essere utilizzate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="48061-109">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> class is a collection of the connection managers that have been added to that package and are available for use at run time.</span></span> <span data-ttu-id="48061-110">È possibile aggiungere altre gestioni connessione alla raccolta utilizzando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> della raccolta e fornendo una stringa che indica il tipo di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="48061-110">You can add more connection managers to the collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method of the collection, and supplying a string that indicates the connection manager type.</span></span> <span data-ttu-id="48061-111">Il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> restituisce l'istanza <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> aggiunta al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="48061-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method returns the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> instance that was added to the package.</span></span>  
  
## <a name="intrinsic-properties"></a><span data-ttu-id="48061-112">Proprietà intrinseche</span><span class="sxs-lookup"><span data-stu-id="48061-112">Intrinsic Properties</span></span>  
 <span data-ttu-id="48061-113">La classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> espone un set di proprietà comuni a tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="48061-113">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class exposes a set of properties that are common to all connections.</span></span> <span data-ttu-id="48061-114">Tuttavia, è talvolta necessario accedere a proprietà univoche per il tipo di connessione specifico.</span><span class="sxs-lookup"><span data-stu-id="48061-114">However, sometimes you need access to properties that are unique to the specific connection type.</span></span> <span data-ttu-id="48061-115">La raccolta <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> della classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> fornisce l'accesso a queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="48061-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class provides access to these properties.</span></span> <span data-ttu-id="48061-116">È possibile recuperare le proprietà dalla raccolta usando l'indicizzatore o il nome della proprietà e il metodo **GetValue**, mentre i valori vengono impostati usando il metodo **SetValue**.</span><span class="sxs-lookup"><span data-stu-id="48061-116">The properties can be retrieved from the collection using the indexer or the property name and the **GetValue** method, and the values are set using the **SetValue** method.</span></span> <span data-ttu-id="48061-117">È possibile impostare le proprietà delle proprietà dell'oggetto connessione sottostante anche acquisendo un'istanza effettiva dell'oggetto e impostandone direttamente le proprietà.</span><span class="sxs-lookup"><span data-stu-id="48061-117">The properties of the underlying connection object properties can also be set by acquiring an actual instance of the object and setting its properties directly.</span></span> <span data-ttu-id="48061-118">Per ottenere la connessione sottostante, utilizzare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="48061-118">To get the underlying connection, use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> property of the connection manager.</span></span> <span data-ttu-id="48061-119">Nella riga seguente di codice è mostrata una riga C# che crea una gestione connessione ADO.NET che dispone della classe sottostante, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span><span class="sxs-lookup"><span data-stu-id="48061-119">The following line of code shows a C# line that creates an ADO.NET connection manager that has the underlying class, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span></span>  
  
 `ConnectionManagerAdoNetClass cmado = cm.InnerObject as ConnectionManagerAdoNet;`  
  
 <span data-ttu-id="48061-120">Esegue il cast dell'oggetto gestione connessione gestito all'oggetto connessione sottostante.</span><span class="sxs-lookup"><span data-stu-id="48061-120">This casts the managed connection manager object to its underlying connection object.</span></span> <span data-ttu-id="48061-121">Se si utilizza C++, viene chiamato il metodo `QueryInterface` dell'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e viene richiesta l'interfaccia dell'oggetto connessione sottostante.</span><span class="sxs-lookup"><span data-stu-id="48061-121">If you are using C++, the `QueryInterface` method of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object is called and the interface of the underlying connection object is requested.</span></span>  
  
 <span data-ttu-id="48061-122">Nella tabella seguente sono elencate le gestioni connessioni incluse in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48061-122">The following table lists the connection managers included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="48061-123">e la stringa utilizzata nell'istruzione `package.Connections.Add("xxx")`</span><span class="sxs-lookup"><span data-stu-id="48061-123">and the string that is used in the `package.Connections.Add("xxx")` statement.</span></span> <span data-ttu-id="48061-124">Per un elenco di tutte le gestioni connessioni, vedere [Connessioni di Integration Services &#40;SSIS&#41;](../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="48061-124">For a list of all connection managers, see [Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
|<span data-ttu-id="48061-125">string</span><span class="sxs-lookup"><span data-stu-id="48061-125">String</span></span>|<span data-ttu-id="48061-126">Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="48061-126">Connection manager</span></span>|  
|------------|------------------------|  
|<span data-ttu-id="48061-127">"OLEDB"</span><span class="sxs-lookup"><span data-stu-id="48061-127">"OLEDB"</span></span>|<span data-ttu-id="48061-128">Gestione connessione per le connessioni OLE DB.</span><span class="sxs-lookup"><span data-stu-id="48061-128">Connection manager for OLE DB connections.</span></span>|  
|<span data-ttu-id="48061-129">"ODBC"</span><span class="sxs-lookup"><span data-stu-id="48061-129">"ODBC"</span></span>|<span data-ttu-id="48061-130">Gestione connessione per le connessioni ODBC.</span><span class="sxs-lookup"><span data-stu-id="48061-130">Connection manager for ODBC connections.</span></span>|  
|<span data-ttu-id="48061-131">"ADO"</span><span class="sxs-lookup"><span data-stu-id="48061-131">"ADO"</span></span>|<span data-ttu-id="48061-132">Gestione connessione per le connessioni ADO.</span><span class="sxs-lookup"><span data-stu-id="48061-132">Connection manager for ADO connections.</span></span>|  
|<span data-ttu-id="48061-133">"ADO.NET:SQL"</span><span class="sxs-lookup"><span data-stu-id="48061-133">"ADO.NET:SQL"</span></span>|<span data-ttu-id="48061-134">Gestione connessione per le connessioni ADO.NET (provider di dati SQL).</span><span class="sxs-lookup"><span data-stu-id="48061-134">Connection manager for ADO.NET (SQL data provider) connections.</span></span>|  
|<span data-ttu-id="48061-135">"ADO.NET:OLEDB"</span><span class="sxs-lookup"><span data-stu-id="48061-135">"ADO.NET:OLEDB"</span></span>|<span data-ttu-id="48061-136">Gestione connessione per le connessioni ADO.NET (provider di dati OLE DB).</span><span class="sxs-lookup"><span data-stu-id="48061-136">Connection manager for ADO.NET (OLE DB data provider) connections.</span></span>|  
|<span data-ttu-id="48061-137">"FLATFILE"</span><span class="sxs-lookup"><span data-stu-id="48061-137">"FLATFILE"</span></span>|<span data-ttu-id="48061-138">Gestione connessione per le connessioni file flat.</span><span class="sxs-lookup"><span data-stu-id="48061-138">Connection manager for flat file connections.</span></span>|  
|<span data-ttu-id="48061-139">"FILE"</span><span class="sxs-lookup"><span data-stu-id="48061-139">"FILE"</span></span>|<span data-ttu-id="48061-140">Gestione connessione per le connessioni file.</span><span class="sxs-lookup"><span data-stu-id="48061-140">Connection manager for file connections.</span></span>|  
|<span data-ttu-id="48061-141">"MULTIFLATFILE"</span><span class="sxs-lookup"><span data-stu-id="48061-141">"MULTIFLATFILE"</span></span>|<span data-ttu-id="48061-142">Gestione connessione per le connessioni di più file flat.</span><span class="sxs-lookup"><span data-stu-id="48061-142">Connection manager for multiple flat file connections.</span></span>|  
|<span data-ttu-id="48061-143">"MULTIFILE"</span><span class="sxs-lookup"><span data-stu-id="48061-143">"MULTIFILE"</span></span>|<span data-ttu-id="48061-144">Gestione connessione per le connessioni di più file.</span><span class="sxs-lookup"><span data-stu-id="48061-144">Connection manager for multiple file connections.</span></span>|  
|<span data-ttu-id="48061-145">"SQLMOBILE"</span><span class="sxs-lookup"><span data-stu-id="48061-145">"SQLMOBILE"</span></span>|<span data-ttu-id="48061-146">Gestione connessione per le connessioni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="48061-146">Connection manager for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connections.</span></span>|  
|<span data-ttu-id="48061-147">"MSOLAP100"</span><span class="sxs-lookup"><span data-stu-id="48061-147">"MSOLAP100"</span></span>|<span data-ttu-id="48061-148">Gestione connessione per le connessioni [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48061-148">Connection manager for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connections.</span></span>|  
|<span data-ttu-id="48061-149">"FTP"</span><span class="sxs-lookup"><span data-stu-id="48061-149">"FTP"</span></span>|<span data-ttu-id="48061-150">Gestione connessione per le connessioni FTP.</span><span class="sxs-lookup"><span data-stu-id="48061-150">Connection manager for FTP connections.</span></span>|  
|<span data-ttu-id="48061-151">"HTTP"</span><span class="sxs-lookup"><span data-stu-id="48061-151">"HTTP"</span></span>|<span data-ttu-id="48061-152">Gestione connessione per le connessioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="48061-152">Connection manager for HTTP connections.</span></span>|  
|<span data-ttu-id="48061-153">"MSMQ"</span><span class="sxs-lookup"><span data-stu-id="48061-153">"MSMQ"</span></span>|<span data-ttu-id="48061-154">Gestione connessione per le connessioni di accodamento messaggi (anche noto come MSMQ).</span><span class="sxs-lookup"><span data-stu-id="48061-154">Connection manager for Message Queuing (also known as MSMQ) connections.</span></span>|  
|<span data-ttu-id="48061-155">"SMTP"</span><span class="sxs-lookup"><span data-stu-id="48061-155">"SMTP"</span></span>|<span data-ttu-id="48061-156">Gestione connessione per le connessioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="48061-156">Connection manager for SMTP connections.</span></span>|  
|<span data-ttu-id="48061-157">"WMI"</span><span class="sxs-lookup"><span data-stu-id="48061-157">"WMI"</span></span>|<span data-ttu-id="48061-158">Gestione connessione per le connessioni Strumentazione gestioneWindows (WMI) di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="48061-158">Connection manager for Microsoft Windows Management Instrumentation (WMI) connections.</span></span>|  
  
 <span data-ttu-id="48061-159">Nell'esempio di codice seguente è illustrata l'aggiunta di una connessione FILE e OLE DB alla raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> di un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span><span class="sxs-lookup"><span data-stu-id="48061-159">The following code example demonstrates adding an OLE DB and FILE connection to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> collection of a <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span></span> <span data-ttu-id="48061-160">Nell'esempio vengono quindi impostate le proprietà <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="48061-160">The example then sets the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> properties.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      // Create a package, and retrieve its connections.  
      Package pkg = new Package();  
      Connections pkgConns = pkg.Connections;  
  
      // Add an OLE DB connection to the package, using the   
      // method defined in the AddConnection class.  
      CreateConnection myOLEDBConn = new CreateConnection();  
      myOLEDBConn.CreateOLEDBConnection(pkg);  
  
      // View the new connection in the package.  
      Console.WriteLine("Connection description: {0}",  
         pkg.Connections["SSIS Connection Manager for OLE DB"].Description);  
  
      // Add a second connection to the package.  
      CreateConnection myFileConn = new CreateConnection();  
      myFileConn.CreateFileConnection(pkg);  
  
      // View the second connection in the package.  
      Console.WriteLine("Connection description: {0}",  
        pkg.Connections["SSIS Connection Manager for Files"].Description);  
  
      Console.WriteLine();  
      Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count);  
  
      Console.Read();  
    }  
  }  
  // <summary>  
  // This class contains the definitions for multiple  
  // connection managers.  
  // </summary>  
  public class CreateConnection  
  {  
    // Private data.  
    private ConnectionManager ConMgr;  
  
    // Class definition for OLE DB Provider.  
    public void CreateOLEDBConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("OLEDB");  
      ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" +  
        "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" +  
        "Data Source=(local);";  
      ConMgr.Name = "SSIS Connection Manager for OLE DB";  
      ConMgr.Description = "OLE DB connection to the AdventureWorks database.";  
    }  
    public void CreateFileConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("File");  
      ConMgr.ConnectionString = @"\\<yourserver>\<yourfolder>\books.xml";  
      ConMgr.Name = "SSIS Connection Manager for Files";  
      ConMgr.Description = "Flat File connection";  
    }  
  }  
  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    ' Create a package, and retrieve its connections.  
    Dim pkg As New Package()  
    Dim pkgConns As Connections = pkg.Connections  
  
    ' Add an OLE DB connection to the package, using the   
    ' method defined in the AddConnection class.  
    Dim myOLEDBConn As New CreateConnection()  
    myOLEDBConn.CreateOLEDBConnection(pkg)  
  
    ' View the new connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for OLE DB").Description)  
  
    ' Add a second connection to the package.  
    Dim myFileConn As New CreateConnection()  
    myFileConn.CreateFileConnection(pkg)  
  
    ' View the second connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for Files").Description)  
  
    Console.WriteLine()  
    Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
' This class contains the definitions for multiple  
' connection managers.  
  
Public Class CreateConnection  
  ' Private data.  
  Private ConMgr As ConnectionManager  
  
  ' Class definition for OLE DB provider.  
  Public Sub CreateOLEDBConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("OLEDB")  
    ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" & _  
      "Data Source=(local);"  
    ConMgr.Name = "SSIS Connection Manager for OLE DB"  
    ConMgr.Description = "OLE DB connection to the AdventureWorks database."  
  End Sub  
  
  Public Sub CreateFileConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("File")  
    ConMgr.ConnectionString = "\\<yourserver>\<yourfolder>\books.xml"  
    ConMgr.Name = "SSIS Connection Manager for Files"  
    ConMgr.Description = "Flat File connection"  
  End Sub  
  
End Class  
```  
  
 <span data-ttu-id="48061-161">**Esempio di output**</span><span class="sxs-lookup"><span data-stu-id="48061-161">**Sample Output:**</span></span>  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Number of connections in package: 2`  
  
## <a name="external-resources"></a><span data-ttu-id="48061-162">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="48061-162">External Resources</span></span>  
 <span data-ttu-id="48061-163">Articolo tecnico [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743) (stringhe di connessione) su carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="48061-163">Technical article, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743), on carlprothman.net.</span></span>  
  
<span data-ttu-id="48061-164">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="48061-164">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="48061-165">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="48061-165">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="48061-166">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="48061-166">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="48061-167">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="48061-167">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48061-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48061-168">See Also</span></span>  
 <span data-ttu-id="48061-169">[Integration Services &#40;connessioni SSIS&#41;](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="48061-169">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="48061-170">Creazione di gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="48061-170">Create Connection Managers</span></span>](../create-connection-managers.md)  
  
  
