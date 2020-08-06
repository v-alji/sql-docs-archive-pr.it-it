---
title: Scrittura del codice di una gestione connessione personalizzata | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], coding
ms.assetid: b12b6778-1f01-4a7d-984d-73f2f7630aa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 793d70ba0a9ae6176ab35c82e16b9aba8c9ba2cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721620"
---
# <a name="coding-a-custom-connection-manager"></a><span data-ttu-id="f7d0b-102">Scrittura del codice di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="f7d0b-102">Coding a Custom Connection Manager</span></span>
  <span data-ttu-id="f7d0b-103">Dopo avere creato una classe che eredita dalla classe di base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> e avere applicato l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> alla classe, è necessario eseguire l'override dell'implementazione delle proprietà e dei metodi della classe di base per fornire la funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="f7d0b-104">Per esempi di gestioni connessione personalizzate, vedere [Sviluppo di un'interfaccia utente per una gestione connessione personalizzata](developing-a-user-interface-for-a-custom-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f7d0b-104">For samples of custom connection managers, see [Developing a User Interface for a Custom Connection Manager](developing-a-user-interface-for-a-custom-connection-manager.md).</span></span> <span data-ttu-id="f7d0b-105">Gli esempi di codice illustrati in questo argomento sono tratti dall'esempio di gestione connessione personalizzata SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-105">The code examples shown in this topic are drawn from the SQL Server Custom Connection Manager sample.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7d0b-106">La maggior parte delle attività, delle origini e delle destinazioni incluse in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] funziona solo con tipi specifici di gestioni connessioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-106">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="f7d0b-107">Questi esempi, pertanto, non possono essere testati con le attività e i componenti predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-107">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="configuring-the-connection-manager"></a><span data-ttu-id="f7d0b-108">Configurazione della gestione connessione</span><span class="sxs-lookup"><span data-stu-id="f7d0b-108">Configuring the Connection Manager</span></span>  
  
### <a name="setting-the-connectionstring-property"></a><span data-ttu-id="f7d0b-109">Impostazione della proprietà ConnectionString</span><span class="sxs-lookup"><span data-stu-id="f7d0b-109">Setting the ConnectionString Property</span></span>  
 <span data-ttu-id="f7d0b-110">La proprietà <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> è un'importante proprietà ed è l'unica specifica di una gestione connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-110">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property is an important property and the only property unique to a custom connection manager.</span></span> <span data-ttu-id="f7d0b-111">La gestione connessione utilizza il valore di questa proprietà per connettersi all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-111">The connection manager uses the value of this property to connect to the external data source.</span></span> <span data-ttu-id="f7d0b-112">Se si combinano diverse altre proprietà, ad esempio il nome del server e il nome del database, per creare la stringa di connessione, è possibile utilizzare una funzione di supporto per assemblare la stringa sostituendo determinati valori in un modello di stringa di connessione con il nuovo valore fornito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-112">If you are combining several other properties, such as server name and database name, to create the connection string, you can use a helper function to assemble the string by replacing certain values in a connection string template with the new value supplied by the user.</span></span> <span data-ttu-id="f7d0b-113">Nell'esempio di codice seguente è illustrata un'implementazione della proprietà <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> che si basa su una funzione di supporto per assemblare la stringa.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-113">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property that relies on a helper function to assemble the string.</span></span>  
  
```vb  
' Default values.  
Private _serverName As String = "(local)"  
Private _databaseName As String = "AdventureWorks"  
Private _connectionString As String = String.Empty  
  
Private Const CONNECTIONSTRING_TEMPLATE As String = _  
  "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI"  
  
Public Property ServerName() As String  
  Get  
    Return _serverName  
  End Get  
  Set(ByVal value As String)  
    _serverName = value  
  End Set  
End Property  
  
Public Property DatabaseName() As String  
  Get  
    Return _databaseName  
  End Get  
  Set(ByVal value As String)  
    _databaseName = value  
  End Set  
End Property  
  
Public Overrides Property ConnectionString() As String  
  Get  
    UpdateConnectionString()  
    Return _connectionString  
  End Get  
  Set(ByVal value As String)  
    _connectionString = value  
  End Set  
End Property  
  
Private Sub UpdateConnectionString()  
  
  Dim temporaryString As String = CONNECTIONSTRING_TEMPLATE  
  
  If Not String.IsNullOrEmpty(_serverName) Then  
    temporaryString = temporaryString.Replace("<servername>", _serverName)  
  End If  
  If Not String.IsNullOrEmpty(_databaseName) Then  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName)  
  End If  
  
  _connectionString = temporaryString  
  
End Sub  
```  
  
```csharp  
// Default values.  
private string _serverName = "(local)";  
private string _databaseName = "AdventureWorks";  
private string _connectionString = String.Empty;  
  
private const string CONNECTIONSTRING_TEMPLATE = "Data Source=<servername>;Initial Catalog=<databasename>;Integrated Security=SSPI";  
  
public string ServerName  
{  
  get  
  {  
    return _serverName;  
  }  
  set  
  {  
    _serverName = value;  
  }  
}  
  
public string DatabaseName  
{  
  get  
  {  
    return _databaseName;  
  }  
  set  
  {  
    _databaseName = value;  
  }  
}  
  
public override string ConnectionString  
{  
  get  
  {  
    UpdateConnectionString();  
    return _connectionString;  
  }  
  set  
  {  
    _connectionString = value;  
  }  
}  
  
private void UpdateConnectionString()  
{  
  
  string temporaryString = CONNECTIONSTRING_TEMPLATE;  
  
  if (!String.IsNullOrEmpty(_serverName))  
  {  
    temporaryString = temporaryString.Replace("<servername>", _serverName);  
  }  
  
  if (!String.IsNullOrEmpty(_databaseName))  
  {  
    temporaryString = temporaryString.Replace("<databasename>", _databaseName);  
  }  
  
  _connectionString = temporaryString;  
  
}  
```  
  
### <a name="validating-the-connection-manager"></a><span data-ttu-id="f7d0b-114">Convalida della gestione connessione</span><span class="sxs-lookup"><span data-stu-id="f7d0b-114">Validating the Connection Manager</span></span>  
 <span data-ttu-id="f7d0b-115">Eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> per verificare che la gestione connessione sia stata configurata correttamente e sia pronta per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-115">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method to make sure that the connection manager has been configured correctly.</span></span> <span data-ttu-id="f7d0b-116">È necessario convalidare almeno il formato della stringa di connessione e verificare che siano stati forniti valori per tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-116">At a minimum, you should validate the format of the connection string and make sure that values have been provided for all arguments.</span></span> <span data-ttu-id="f7d0b-117">L'esecuzione non può continuare finché la gestione connessione non restituisce <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> dal metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-117">Execution cannot continue until the connection manager returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="f7d0b-118">Nell'esempio di codice seguente è illustrata un'implementazione di <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> che verifica che l'utente abbia specificato un nome di server per la connessione.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-118">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.Validate%2A> that makes sure that the user has specified a server name for the connection.</span></span>  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents) As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  If String.IsNullOrEmpty(_serverName) Then  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0)  
    Return DTSExecResult.Failure  
  Else  
    Return DTSExecResult.Success  
  End If  
  
End Function  
```  
  
```csharp  
public override Microsoft.SqlServer.Dts.Runtime.DTSExecResult Validate(Microsoft.SqlServer.Dts.Runtime.IDTSInfoEvents infoEvents)  
{  
  
  if (String.IsNullOrEmpty(_serverName))  
  {  
    infoEvents.FireError(0, "SqlConnectionManager", "No server name specified", String.Empty, 0);  
    return DTSExecResult.Failure;  
  }  
  else  
  {  
    return DTSExecResult.Success;  
  }  
  
}  
```  
  
### <a name="persisting-the-connection-manager"></a><span data-ttu-id="f7d0b-119">Persistenza della gestione connessione</span><span class="sxs-lookup"><span data-stu-id="f7d0b-119">Persisting the Connection Manager</span></span>  
 <span data-ttu-id="f7d0b-120">In genere non è necessario implementare la persistenza personalizzata per una gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-120">Usually, you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="f7d0b-121">La persistenza personalizzata è richiesta solo quando le proprietà di un oggetto utilizzano tipi di dati complessi.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-121">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="f7d0b-122">Per altre informazioni, vedere [Sviluppo di oggetti personalizzati per Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7d0b-122">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="working-with-the-external-data-source"></a><span data-ttu-id="f7d0b-123">Utilizzo dell'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="f7d0b-123">Working with the External Data Source</span></span>  
 <span data-ttu-id="f7d0b-124">I metodi più importanti di una gestione connessione personalizzata sono quelli che supportano la connessione a un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-124">The methods that support connecting to an external data source are the most important methods of a custom connection manager.</span></span> <span data-ttu-id="f7d0b-125">I metodi <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> vengono chiamati in vari momenti durante la fase di progettazione e la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-125">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods are called at various times during both design time and run time.</span></span>  
  
### <a name="acquiring-the-connection"></a><span data-ttu-id="f7d0b-126">Acquisizione della connessione</span><span class="sxs-lookup"><span data-stu-id="f7d0b-126">Acquiring the Connection</span></span>  
 <span data-ttu-id="f7d0b-127">È necessario stabilire il tipo di oggetto appropriato che il metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> deve restituire dalla gestione connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-127">You need to decide what type of object it is appropriate for the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method to return from your custom connection manager.</span></span> <span data-ttu-id="f7d0b-128">Ad esempio, una gestione connessione file restituisce solo una stringa che contiene un percorso e un nome file, mentre una gestione connessione ADO.NET restituisce un oggetto connessione gestito che già è aperto.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-128">For example, a File connection manager returns only a string that contains a path and filename, whereas an ADO.NET connection manager returns a managed connection object that is already open.</span></span> <span data-ttu-id="f7d0b-129">Una gestione connessione OLE DB restituisce un oggetto connessione OLE DB nativo che non può essere utilizzato da codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-129">An OLE DB connection manager returns a native OLE DB connection object that cannot be used from managed code.</span></span> <span data-ttu-id="f7d0b-130">La gestione connessione personalizzata SQL Server, da cui sono tratti i frammenti di codice in questo argomento, restituisce un oggetto `SqlConnection` aperto.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-130">The custom SQL Server connection manager, from which the code snippets in this topic are taken, returns an open `SqlConnection` object.</span></span>  
  
 <span data-ttu-id="f7d0b-131">Gli utenti della gestione connessione devono sapere in anticipo quale tipo di oggetto aspettarsi, in modo che possano eseguire il cast dell'oggetto restituito nel tipo appropriato e accedere ai relativi metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-131">Users of your connection manager need to know in advance what type of object to expect, so that they can cast the returned object to the appropriate type and access its methods and properties.</span></span>  
  
```vb  
Public Overrides Function AcquireConnection(ByVal txn As Object) As Object  
  
  Dim sqlConnection As New SqlConnection  
  
  UpdateConnectionString()  
  
  With sqlConnection  
    .ConnectionString = _connectionString  
    .Open()  
  End With  
  
  Return sqlConnection  
  
End Function  
```  
  
```csharp  
public override object AcquireConnection(object txn)  
{  
  
  SqlConnection sqlConnection = new SqlConnection();  
  
  UpdateConnectionString();  
  
  {  
    sqlConnection.ConnectionString = _connectionString;  
    sqlConnection.Open();  
  }  
  
  return sqlConnection;  
  
}  
```  
  
### <a name="releasing-the-connection"></a><span data-ttu-id="f7d0b-132">Rilascio della connessione</span><span class="sxs-lookup"><span data-stu-id="f7d0b-132">Releasing the Connection</span></span>  
 <span data-ttu-id="f7d0b-133">L'azione eseguita nel metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> dipende dal tipo di oggetto restituito dal metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-133">The action that you take in the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> method depends on the type of object that you returned from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span> <span data-ttu-id="f7d0b-134">Se è disponibile un oggetto connessione aperto, è necessario chiuderlo e rilasciare le eventuali risorse che utilizza.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-134">If there is an open connection object, you should close it and to release any resources that it is using.</span></span> <span data-ttu-id="f7d0b-135">Se <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> ha restituito solo un valore stringa, non è necessario eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-135">If <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> returned only a string value, no action needs to be taken.</span></span>  
  
```vb  
Public Overrides Sub ReleaseConnection(ByVal connection As Object)  
  
  Dim sqlConnection As SqlConnection  
  
  sqlConnection = DirectCast(connection, SqlConnection)  
  
  If sqlConnection.State <> ConnectionState.Closed Then  
    sqlConnection.Close()  
  End If  
  
End Sub  
```  
  
```csharp  
public override void ReleaseConnection(object connection)  
{  
  SqlConnection sqlConnection;  
  sqlConnection = (SqlConnection)connection;  
  if (sqlConnection.State != ConnectionState.Closed)  
    sqlConnection.Close();  
}  
```  
  
<span data-ttu-id="f7d0b-136">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f7d0b-136">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f7d0b-137">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="f7d0b-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f7d0b-138">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="f7d0b-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f7d0b-139">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f7d0b-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d0b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7d0b-140">See Also</span></span>  
 <span data-ttu-id="f7d0b-141">[Creazione di una gestione connessione personalizzata](creating-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f7d0b-141">[Creating a Custom Connection Manager](creating-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="f7d0b-142">Sviluppo di un'interfaccia utente per una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="f7d0b-142">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
