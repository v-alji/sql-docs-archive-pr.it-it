---
title: Gestione degli eventi a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services packages, events
- SQL Server Integration Services packages, events
- SSIS events, programmatically handling
- packages [Integration Services], events
- DtsEventHandler object
- SSIS packages, events
- SSIS events
- events [Integration Services], programmatically
- tasks [Integration Services], events
- IDTSEvents interface
ms.assetid: 0f00bd66-efd5-4f12-9e1c-36195f739332
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70d2d8909df65f775fc3a3034931bb599597068
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626848"
---
# <a name="handling-events-programmatically"></a><span data-ttu-id="851b8-102">Gestione degli eventi a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="851b8-102">Handling Events Programmatically</span></span>
  <span data-ttu-id="851b8-103">Il runtime di [!INCLUDE[ssIS](../../includes/ssis-md.md)] fornisce una raccolta di eventi che si verificano prima, durante e dopo la convalida e l'esecuzione di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="851b8-103">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] runtime provides a collection of events that occur before, during, and after the validation and execution of a package.</span></span> <span data-ttu-id="851b8-104">Tali eventi possono essere acquisiti in due modi.</span><span class="sxs-lookup"><span data-stu-id="851b8-104">These events can be captured in two ways.</span></span> <span data-ttu-id="851b8-105">Il primo metodo prevede di implementare l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> in una classe e specificare la classe come parametro per i metodi `Execute` e `Validate` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="851b8-105">The first method is by implementing the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface in a class, and supplying the class as a parameter to the `Execute` and `Validate` methods of the package.</span></span> <span data-ttu-id="851b8-106">Il secondo metodo consiste nella creazione di oggetti <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> che possono contenere altri oggetti di [!INCLUDE[ssIS](../../includes/ssis-md.md)], ad esempio attività e cicli, eseguiti quando si verifica un evento in <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="851b8-106">The second method is by creating <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects, which can contain other [!INCLUDE[ssIS](../../includes/ssis-md.md)] objects, such as tasks and loops, that are executed when an event in <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> occurs.</span></span> <span data-ttu-id="851b8-107">In questa sezione vengono descritti questi due metodi e vengono forniti esempi di codice per dimostrarne l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="851b8-107">This section describes these two methods and provides code examples to demonstrate their use.</span></span>  
  
## <a name="receiving-idtsevents-callbacks"></a><span data-ttu-id="851b8-108">Ricezione di callback IDTSEvents</span><span class="sxs-lookup"><span data-stu-id="851b8-108">Receiving IDTSEvents Callbacks</span></span>  
 <span data-ttu-id="851b8-109">Gli sviluppatori che compilano ed eseguono pacchetti a livello di programmazione possono ricevere notifiche di eventi durante il processo di convalida ed esecuzione tramite l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="851b8-109">Developers who build and execute packages programmatically can receive event notifications during the validation and execution process using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface.</span></span> <span data-ttu-id="851b8-110">A tale scopo, è possibile creare una classe che implementa l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> in una classe e specificare tale classe come parametro per i metodi `Validate` e `Execute` di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="851b8-110">This is done by creating a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface and providing this class as a parameter to the `Validate` and `Execute` methods of a package.</span></span> <span data-ttu-id="851b8-111">I metodi della classe vengono quindi chiamati dal motore di run-time quando si verificano gli eventi.</span><span class="sxs-lookup"><span data-stu-id="851b8-111">The methods of the class are then called by the run-time engine when the events occur.</span></span>  
  
 <span data-ttu-id="851b8-112">La classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> è una classe che implementa già l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>; pertanto, un'alternativa all'implementazione diretta di <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> consiste nel derivare da <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> ed eseguire l'override degli eventi specifici ai quali si desidera rispondere.</span><span class="sxs-lookup"><span data-stu-id="851b8-112">The <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class is a class that already implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface; therefore, another alternative to implementing <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> directly is to derive from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> and override the specific events that you want to respond to.</span></span> <span data-ttu-id="851b8-113">Specificare quindi la classe come parametro per i metodi `Validate` e `Execute` di <xref:Microsoft.SqlServer.Dts.Runtime.Package> per ricevere i callback degli eventi.</span><span class="sxs-lookup"><span data-stu-id="851b8-113">You then provide your class as a parameter to the `Validate` and `Execute` methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Package> to receive event callbacks.</span></span>  
  
 <span data-ttu-id="851b8-114">Nell'esempio di codice seguente viene illustrata una classe che deriva da <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> ed esegue l'override del metodo <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="851b8-114">The following code sample demonstrates a class that derives from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>, and overrides the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A> method.</span></span> <span data-ttu-id="851b8-115">La classe viene quindi fornita come parametro ai `Validate` metodi e `Execute` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="851b8-115">The class is then provided as aparameter to the `Validate` and `Execute` methods of the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      MyEventsClass eventsClass = new MyEventsClass();  
  
      p.Validate(null, null, eventsClass, null);  
      p.Execute(null, null, eventsClass, null, null);  
  
      Console.Read();  
    }  
  }  
  class MyEventsClass : DefaultEvents  
  {  
    public override void OnPreExecute(Executable exec, ref bool fireAgain)  
    {  
      // TODO: Add custom code to handle the event.  
      Console.WriteLine("The PreExecute event of the " +  
        exec.ToString() + " has been raised.");  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim eventsClass As MyEventsClass = New MyEventsClass()  
  
    p.Validate(Nothing, Nothing, eventsClass, Nothing)  
    p.Execute(Nothing, Nothing, eventsClass, Nothing, Nothing)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
Class MyEventsClass  
  Inherits DefaultEvents  
  
  Public Overrides Sub OnPreExecute(ByVal exec As Executable, ByRef fireAgain As Boolean)  
  
    ' TODO: Add custom code to handle the event.  
    Console.WriteLine("The PreExecute event of the " & _  
      exec.ToString() & " has been raised.")  
  
  End Sub  
  
End Class  
```  
  
## <a name="creating-dtseventhandler-objects"></a><span data-ttu-id="851b8-116">Creazione di oggetti DtsEventHandler</span><span class="sxs-lookup"><span data-stu-id="851b8-116">Creating DtsEventHandler Objects</span></span>  
 <span data-ttu-id="851b8-117">Il motore di run-time fornisce un sistema di gestione e notifica degli eventi stabile e ampiamente flessibile tramite l'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="851b8-117">The run-time engine provides a robust, highly flexible event handling and notification system through the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="851b8-118">Questi oggetti consentono di progettare interi flussi di lavoro dall'interno del gestore eventi, che vengono eseguiti solo quando si verifica l'evento cui appartiene il gestore.</span><span class="sxs-lookup"><span data-stu-id="851b8-118">These objects let you design whole workflows within the event handler, which execute only when the event that the event handler belongs to occurs.</span></span> <span data-ttu-id="851b8-119">L'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> è un contenitore eseguito quando viene generato l'evento corrispondente nel relativo oggetto padre.</span><span class="sxs-lookup"><span data-stu-id="851b8-119">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object is a container that is executed when the corresponding event on its parent object fires.</span></span> <span data-ttu-id="851b8-120">Questa architettura consente di creare flussi di lavoro isolati eseguiti in risposta a eventi che si verificano in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="851b8-120">This architecture lets you create isolated workflows that are executed in response to events that occur on a container.</span></span> <span data-ttu-id="851b8-121">Poiché gli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> sono sincroni, l'esecuzione riprende solo dopo che sono stati restituiti i gestori eventi collegati all'evento.</span><span class="sxs-lookup"><span data-stu-id="851b8-121">Because <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are synchronous, execution does not resume until the event handlers that are attached to the event have returned.</span></span>  
  
 <span data-ttu-id="851b8-122">Nell'esempio di codice seguente viene illustrato come creare un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="851b8-122">The following code demonstrates how to create a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="851b8-123">Nel codice viene aggiunto <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> alla raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> del pacchetto, quindi viene creato un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> per l'evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> dell'attività.</span><span class="sxs-lookup"><span data-stu-id="851b8-123">The code adds a <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> collection of the package, and then creates a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object for the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event of the task.</span></span> <span data-ttu-id="851b8-124">Un oggetto <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> viene aggiunto al gestore eventi, che viene eseguito quando si verifica l'evento <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> per il primo oggetto <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span><span class="sxs-lookup"><span data-stu-id="851b8-124">A <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> is added to the event handler, which is executed when the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event occurs for the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span></span> <span data-ttu-id="851b8-125">In questo esempio si presuppone che si disponga di un file denominato C:\Windows\Temp\DemoFile.txt per il test.</span><span class="sxs-lookup"><span data-stu-id="851b8-125">This example assumes that you have a file that is named C:\Windows\Temp\DemoFile.txt for testing.</span></span> <span data-ttu-id="851b8-126">La prima volta che si esegue l'esempio, il file viene copiato correttamente e il gestore eventi non viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="851b8-126">The first time that you run the sample, if copies the file successfully and the event handler is not called.</span></span> <span data-ttu-id="851b8-127">La seconda volta che si esegue l'evento, il primo oggetto <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> non riesce a copiare il file (perché il valore di <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> è `false`), viene chiamato il gestore eventi, il secondo oggetto <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> elimina il file di origine, quindi il pacchetto segnala un problema a causa dell'errore che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="851b8-127">The second time you run the sample, the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> fails to copy the file (because the value of <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> is `false`), the event handler is called, the second <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> deletes the source file, and the package reports failure because of the error that occurred.</span></span>  
  
## <a name="example"></a><span data-ttu-id="851b8-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="851b8-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string f = "DemoFile.txt";  
      Executable e;  
      TaskHost th;  
      FileSystemTask fst;  
  
      Package p = new Package();  
  
      p.Variables.Add("sourceFile", true, String.Empty,  
        @"C:\Windows\Temp\" + f);  
      p.Variables.Add("destinationFile", true, String.Empty,  
        Path.Combine(Directory.GetCurrentDirectory(), f));  
  
      // Create a first File System task and add it to the package.  
      // This task tries to copy a file from one folder to another.  
      e = p.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask1";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.CopyFile;  
      fst.OverwriteDestinationFile = false;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
      fst.Destination = "destinationFile";  
      fst.IsDestinationPathVariable = true;  
  
      // Add an event handler for the FileSystemTask's OnError event.  
      DtsEventHandler ehOnError = (DtsEventHandler)th.EventHandlers.Add("OnError");  
  
      // Create a second File System task and add it to the event handler.  
      // This task deletes the source file if the event handler is called.  
      e = ehOnError.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask2";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.DeleteFile;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
  
      DTSExecResult vr = p.Validate(null, null, null, null);  
      Console.WriteLine("ValidationResult = " + vr.ToString());  
      if (vr == DTSExecResult.Success)  
      {  
        DTSExecResult er = p.Execute(null, null, null, null, null);  
        Console.WriteLine("ExecutionResult = " + er.ToString());  
        if (er == DTSExecResult.Failure)  
          if (!File.Exists(@"C:\Windows\Temp\" + f))  
            Console.WriteLine("Source file has been deleted by the event handler.");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim f As String = "DemoFile.txt"  
    Dim e As Executable  
    Dim th As TaskHost  
    Dim fst As FileSystemTask  
  
    Dim p As Package = New Package()  
  
    p.Variables.Add("sourceFile", True, String.Empty, _  
      "C:\Windows\Temp\" & f)  
    p.Variables.Add("destinationFile", True, String.Empty, _  
      Path.Combine(Directory.GetCurrentDirectory(), f))  
  
    ' Create a first File System task and add it to the package.  
    ' This task tries to copy a file from one folder to another.  
    e = p.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.CopyFile  
    fst.OverwriteDestinationFile = False  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
    fst.Destination = "destinationFile"  
    fst.IsDestinationPathVariable = True  
  
    ' Add an event handler for the FileSystemTask's OnError event.  
    Dim ehOnError As DtsEventHandler = CType(th.EventHandlers.Add("OnError"), DtsEventHandler)  
  
    ' Create a second File System task and add it to the event handler.  
    ' This task deletes the source file if the event handler is called.  
    e = ehOnError.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.DeleteFile  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
  
    Dim vr As DTSExecResult = p.Validate(Nothing, Nothing, Nothing, Nothing)  
    Console.WriteLine("ValidationResult = " + vr.ToString())  
    If vr = DTSExecResult.Success Then  
      Dim er As DTSExecResult = p.Execute(Nothing, Nothing, Nothing, Nothing, Nothing)  
      Console.WriteLine("ExecutionResult = " + er.ToString())  
      If er = DTSExecResult.Failure Then  
        If Not File.Exists("C:\Windows\Temp\" + f) Then  
          Console.WriteLine("Source file has been deleted by the event handler.")  
        End If  
      End If  
    End If  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="851b8-129">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="851b8-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="851b8-130">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="851b8-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="851b8-131">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="851b8-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="851b8-132">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="851b8-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="851b8-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="851b8-133">See Also</span></span>  
 <span data-ttu-id="851b8-134">[Gestori eventi di Integration Services &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="851b8-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="851b8-135">Aggiunta di un gestore eventi a un pacchetto</span><span class="sxs-lookup"><span data-stu-id="851b8-135">Add an Event Handler to a Package</span></span>](../add-an-event-handler-to-a-package.md)  
  
  
