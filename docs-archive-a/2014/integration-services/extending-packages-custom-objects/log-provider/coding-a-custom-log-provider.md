---
title: Scrittura del codice di un provider di log personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom log providers [Integration Services], coding
ms.assetid: 979a29ca-956e-4fdd-ab47-f06e84cead7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d529420207ac065ae5ecb3c1d984de3021845b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716423"
---
# <a name="coding-a-custom-log-provider"></a><span data-ttu-id="987f1-102">Scrittura del codice di un provider di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="987f1-102">Coding a Custom Log Provider</span></span>
  <span data-ttu-id="987f1-103">Dopo avere creato una classe che eredita dalla classe di base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> e avere applicato l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> alla classe, è necessario eseguire l'override dell'implementazione delle proprietà e dei metodi della classe di base per fornire la funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="987f1-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="987f1-104">Per esempi reali dei provider di log personalizzati, vedere [Sviluppo di un'interfaccia utente per un provider di log personalizzato](developing-a-user-interface-for-a-custom-log-provider.md).</span><span class="sxs-lookup"><span data-stu-id="987f1-104">For working samples of custom log providers, see [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md).</span></span>  
  
## <a name="configuring-the-log-provider"></a><span data-ttu-id="987f1-105">Configurazione del provider di log</span><span class="sxs-lookup"><span data-stu-id="987f1-105">Configuring the Log Provider</span></span>  
  
### <a name="initializing-the-log-provider"></a><span data-ttu-id="987f1-106">Inizializzazione del provider di log</span><span class="sxs-lookup"><span data-stu-id="987f1-106">Initializing the Log Provider</span></span>  
 <span data-ttu-id="987f1-107">Eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> per memorizzare nella cache i riferimenti alla raccolta di connessioni e all'interfaccia degli eventi.</span><span class="sxs-lookup"><span data-stu-id="987f1-107">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> method to cache references to the connections collection and the events interface.</span></span> <span data-ttu-id="987f1-108">È possibile utilizzare questi riferimenti memorizzati nella cache in seguito in altri metodi del provider di log.</span><span class="sxs-lookup"><span data-stu-id="987f1-108">You can use these cached references later in other methods of the log provider.</span></span>  
  
### <a name="using-the-configstring-property"></a><span data-ttu-id="987f1-109">Utilizzo della proprietà ConfigString</span><span class="sxs-lookup"><span data-stu-id="987f1-109">Using the ConfigString Property</span></span>  
 <span data-ttu-id="987f1-110">In fase di progettazione un provider di log riceve le informazioni di configurazione dalla colonna **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="987f1-110">At design time, a log provider receives configuration information from the **Configuration** column.</span></span> <span data-ttu-id="987f1-111">Tali informazioni corrispondono alla proprietà <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> del provider di log.</span><span class="sxs-lookup"><span data-stu-id="987f1-111">This configuration information corresponds to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property of the log provider.</span></span> <span data-ttu-id="987f1-112">Per impostazione predefinita, questa colonna contiene una casella di testo da cui è possibile recuperare qualsiasi informazione in formato stringa.</span><span class="sxs-lookup"><span data-stu-id="987f1-112">By default, this column contains a text box from which you can retrieve any string information.</span></span> <span data-ttu-id="987f1-113">La maggior parte dei provider di log inclusi in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] utilizza questa proprietà per archiviare il nome della gestione connessione utilizzata per connettersi a un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="987f1-113">Most of the log providers included with [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] use this property to store the name of the connection manager that the provider uses to connect to an external data source.</span></span> <span data-ttu-id="987f1-114">Se il provider di log usa la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>, usare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> per convalidarla e verificare che sia impostata correttamente.</span><span class="sxs-lookup"><span data-stu-id="987f1-114">If your log provider uses the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property, use the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to validate this property and make sure that the property is set correctly.</span></span>  
  
### <a name="validating-the-log-provider"></a><span data-ttu-id="987f1-115">Convalida del provider di log</span><span class="sxs-lookup"><span data-stu-id="987f1-115">Validating the Log Provider</span></span>  
 <span data-ttu-id="987f1-116">Eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> per verificare che il provider sia stato configurato correttamente e sia pronto per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="987f1-116">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to make sure that the provider has been configured correctly and is ready for execution.</span></span> <span data-ttu-id="987f1-117">In genere, è richiesto un livello minimo di convalida per verificare che <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> sia impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="987f1-117">Typically, a minimum level of validation is to make sure that the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> is set correctly.</span></span> <span data-ttu-id="987f1-118">L'esecuzione non può continuare finché il provider di log non restituisce <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> dal metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="987f1-118">Execution cannot continue until the log provider returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="987f1-119">Nell'esempio di codice seguente è illustrata un'implementazione di <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> che verifica che sia specificato il nome di una gestione connessione, che la gestione connessione esista nel pacchetto e che restituisca un nome di file nella proprietà <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="987f1-119">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> that makes sure that the name of a connection manager name is specified, that the connection manager exists in the package, and that the connection manager returns a file name in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override DTSExecResult Validate(IDTSInfoEvents infoEvents)  
{  
    if (this.ConfigString.Length == 0 || connections.Contains(ConfigString) == false)  
    {  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
        return DTSExecResult.Failure;  
    }  
    else  
    {  
        string fileName = connections[ConfigString].AcquireConnection(null) as string;  
  
        if (fileName == null || fileName.Length == 0)  
        {  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
            return DTSExecResult.Failure;  
        }  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As IDTSInfoEvents) As DTSExecResult  
    If Me.ConfigString.Length = 0 Or connections.Contains(ConfigString) = False Then  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
        Return DTSExecResult.Failure  
    Else   
        Dim fileName As String =  connections(ConfigString).AcquireConnectionCType(as string, Nothing)  
  
        If fileName = Nothing Or fileName.Length = 0 Then  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
            Return DTSExecResult.Failure  
        End If  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
### <a name="persisting-the-log-provider"></a><span data-ttu-id="987f1-120">Persistenza del provider di log</span><span class="sxs-lookup"><span data-stu-id="987f1-120">Persisting the Log Provider</span></span>  
 <span data-ttu-id="987f1-121">In genere non è necessario implementare la persistenza personalizzata per una gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="987f1-121">Ordinarily you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="987f1-122">La persistenza personalizzata è richiesta solo quando le proprietà di un oggetto utilizzano tipi di dati complessi.</span><span class="sxs-lookup"><span data-stu-id="987f1-122">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="987f1-123">Per altre informazioni, vedere [Sviluppo di oggetti personalizzati per Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="987f1-123">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="logging-with-the-log-provider"></a><span data-ttu-id="987f1-124">Registrazione con il provider di log</span><span class="sxs-lookup"><span data-stu-id="987f1-124">Logging with the Log Provider</span></span>  
 <span data-ttu-id="987f1-125">Tutti i provider di log devono eseguire l'override di tre metodi di runtime: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="987f1-125">There are three run-time methods that must be overridden by all log providers: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="987f1-126">Durante la convalida e l'esecuzione di un singolo pacchetto, i metodi <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> vengono chiamati più di una volta.</span><span class="sxs-lookup"><span data-stu-id="987f1-126">During the validation and execution of a single package, the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods are called more than one time.</span></span> <span data-ttu-id="987f1-127">Verificare che il codice personalizzato non produca la sovrascrittura delle voci precedenti del log le volte successive che il log viene aperto e chiuso.</span><span class="sxs-lookup"><span data-stu-id="987f1-127">Make sure that your custom code does not cause earlier log entries to be overwritten by the next opening and closing of the log.</span></span> <span data-ttu-id="987f1-128">Se è stato selezionato di registrare gli eventi di convalida nel pacchetto di test, il primo evento registrato che dovrebbe apparire è OnPreValidate; se invece il primo evento registrato visualizzato è PackageStart, significa che gli eventi di convalida iniziali sono stati sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="987f1-128">If you have selected to log validation events in your test package, the first logged event that you should see is OnPreValidate; if instead the first logged event that you see is PackageStart, the initial validation events have been overwritten.</span></span>  
  
### <a name="opening-the-log"></a><span data-ttu-id="987f1-129">Apertura del log</span><span class="sxs-lookup"><span data-stu-id="987f1-129">Opening the Log</span></span>  
 <span data-ttu-id="987f1-130">La maggior parte dei provider di log si connette a un'origine dati esterna, ad esempio un file o un database, per archiviare le informazioni degli eventi raccolte durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="987f1-130">Most log providers connect to an external data source, such as a file or database, to store the event information that is collected during package execution.</span></span> <span data-ttu-id="987f1-131">Come per qualsiasi altro oggetto nel runtime, la connessione all'origine dati esterna viene in genere stabilita tramite oggetti gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="987f1-131">As with any other object in the runtime, connecting to the external data source is typically accomplished by using connection manager objects.</span></span>  
  
 <span data-ttu-id="987f1-132">Il metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> viene chiamato all'inizio dell'esecuzione del pacchetto. Eseguire l'override di questo metodo per stabilire una connessione con l'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="987f1-132">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method is called at the start of package execution.Override this method to establish a connection to the external data source.</span></span>  
  
 <span data-ttu-id="987f1-133">Nel codice di esempio seguente è illustrato un provider di log che apre un file di testo per la scrittura durante <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="987f1-133">The following sample code shows a log provider that opens a text file for writing during <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span></span> <span data-ttu-id="987f1-134">Il file viene aperto tramite una chiamata al metodo <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> della gestione connessione specificata nella proprietà <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="987f1-134">It opens the file by calling the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager that was specified in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override void OpenLog()  
{  
    if(!this.connections.Contains(this.ConfigString))  
        throw new Exception("The ConnectionManager " + this.ConfigString + " does not exist in the Connections collection.");  
  
    this.connectionManager = connections[ConfigString];  
    string filePath = this.connectionManager.AcquireConnection(null) as string;  
  
    if(filePath == null || filePath.Length == 0)  
        throw new Exception("The ConnectionManager " + this.ConfigString + " is not a valid FILE ConnectionManager");  
  
    //  Create a StreamWriter to append to.  
    sw = new StreamWriter(filePath,true);  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString());  
}  
```  
  
```vb  
Public Overrides  Sub OpenLog()  
    If Not Me.connections.Contains(Me.ConfigString) Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " does not exist in the Connections collection.")  
    End If  
  
    Me.connectionManager = connections(ConfigString)  
    Dim filePath As String =  Me.connectionManager.AcquireConnectionCType(as string, Nothing)  
  
    If filePath = Nothing Or filePath.Length = 0 Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " is not a valid FILE ConnectionManager")  
    End If  
  
    '  Create a StreamWriter to append to.  
    sw = New StreamWriter(filePath,True)  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString())  
End Sub  
```  
  
### <a name="writing-log-entries"></a><span data-ttu-id="987f1-135">Scrittura di voci di log</span><span class="sxs-lookup"><span data-stu-id="987f1-135">Writing Log Entries</span></span>  
 <span data-ttu-id="987f1-136">Il metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> viene chiamato ogni volta che un oggetto del pacchetto genera un evento chiamando un metodo Fire\<event> in una delle interfacce degli eventi.</span><span class="sxs-lookup"><span data-stu-id="987f1-136">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method is called every time that an object in the package raises an event by calling a Fire\<event> method on one of the event interfaces.</span></span> <span data-ttu-id="987f1-137">Ogni evento viene generato con informazioni sul relativo contesto e in genere con un messaggio descrittivo.</span><span class="sxs-lookup"><span data-stu-id="987f1-137">Each event is raised with information about its context and usually an explanatory message.</span></span> <span data-ttu-id="987f1-138">Tuttavia, non tutte le chiamate al metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> includono informazioni per ogni parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="987f1-138">However, not every call to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method includes information for every method parameter.</span></span> <span data-ttu-id="987f1-139">Ad esempio, alcuni eventi standard i cui nomi sono autodescrittivi non forniscono MessageText, mentre DataCode e DataBytes vengono utilizzati per fornire informazioni supplementari facoltative.</span><span class="sxs-lookup"><span data-stu-id="987f1-139">For example, some standard events whose names are self-explanatory do not provide MessageText, and DataCode and DataBytes are intended for optional supplemental information.</span></span>  
  
 <span data-ttu-id="987f1-140">Nell'esempio di codice seguente viene implementato il metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> e vengono scritti gli eventi nel flusso aperto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="987f1-140">The following code example implements the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method, and writes the events to the stream that was opened in the previous section.</span></span>  
  
```csharp  
public override void Log(string logEntryName, string computerName, string operatorName, string sourceName, string sourceID, string executionID, string messageText, DateTime startTime, DateTime endTime, int dataCode, byte[] dataBytes)  
{  
    sw.Write(logEntryName + ",");  
    sw.Write(computerName + ",");  
    sw.Write(operatorName + ",");  
    sw.Write(sourceName + ",");  
    sw.Write(sourceID + ",");  
    sw.Write(messageText + ",");  
    sw.Write(dataBytes + ",");  
    sw.WriteLine("");  
}  
```  
  
```vb  
Public Overrides  Sub Log(ByVal logEnTryName As String, ByVal computerName As String, ByVal operatorName As String, ByVal sourceName As String, ByVal sourceID As String, ByVal executionID As String, ByVal messageText As String, ByVal startTime As DateTime, ByVal endTime As DateTime, ByVal dataCode As Integer, ByVal dataBytes() As Byte)  
    sw.Write(logEnTryName + ",")  
    sw.Write(computerName + ",")  
    sw.Write(operatorName + ",")  
    sw.Write(sourceName + ",")  
    sw.Write(sourceID + ",")  
    sw.Write(messageText + ",")  
    sw.Write(dataBytes + ",")  
    sw.WriteLine("")  
End Sub  
```  
  
### <a name="closing-the-log"></a><span data-ttu-id="987f1-141">Chiusura del log</span><span class="sxs-lookup"><span data-stu-id="987f1-141">Closing the Log</span></span>  
 <span data-ttu-id="987f1-142">Il metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> viene chiamato alla fine dell'esecuzione del pacchetto, dopo il completamento dell'esecuzione di tutti i relativi oggetti oppure quando il pacchetto viene arrestato a causa di errori.</span><span class="sxs-lookup"><span data-stu-id="987f1-142">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method is called at the end of package execution, after all the objects in the package have completed execution, or, when the package stops because of errors.</span></span>  
  
 <span data-ttu-id="987f1-143">Nell'esempio di codice seguente è illustrata un'implementazione del metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> che chiude il flusso di file aperto durante il metodo <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="987f1-143">The following code example demonstrates an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method that closes the file stream that was opened during the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method.</span></span>  
  
```csharp  
public override void CloseLog()  
{  
    if (sw != null)  
    {  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString());  
        sw.Close();  
    }  
}  
```  
  
```vb  
Public Overrides  Sub CloseLog()  
    If Not sw Is Nothing Then  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString())  
        sw.Close()  
    End If  
End Sub  
```  
  
<span data-ttu-id="987f1-144">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="987f1-144">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="987f1-145">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="987f1-145">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="987f1-146">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="987f1-146">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="987f1-147">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="987f1-147">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987f1-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="987f1-148">See Also</span></span>  
 <span data-ttu-id="987f1-149">[Creazione di un provider di log personalizzato](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="987f1-149">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="987f1-150">Sviluppo di un'interfaccia utente per un provider di log personalizzato</span><span class="sxs-lookup"><span data-stu-id="987f1-150">Developing a User Interface for a Custom Log Provider</span></span>](developing-a-user-interface-for-a-custom-log-provider.md)  
  
  
