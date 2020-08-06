---
title: Caricamento ed esecuzione di un pacchetto locale a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Integration Services packages, running
- events [Integration Services], capturing
- packages [Integration Services], running
- loading packages programmatically
- Visual Basic [Integration Services]
- running packages [Integration Services]
- programmatically load and run packages [SSIS]
ms.assetid: 2f9fc1a8-a001-4c54-8c64-63b443725422
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a29faf623c02fea4fd8722c235f595f0fe4492e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713235"
---
# <a name="loading-and-running-a-local-package-programmatically"></a><span data-ttu-id="f869c-102">Caricamento ed esecuzione di un pacchetto locale a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f869c-102">Loading and Running a Local Package Programmatically</span></span>
  <span data-ttu-id="f869c-103">È possibile eseguire i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in base alle necessità o a orari predeterminati utilizzando i metodi descritti in [Esecuzione di pacchetti](../packages/run-integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f869c-103">You can run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages as needed or at predetermined times by using the methods described in [Running Packages](../packages/run-integration-services-ssis-packages.md).</span></span> <span data-ttu-id="f869c-104">Tuttavia, con poche righe di codice, è anche possibile eseguire un pacchetto da un'applicazione personalizzata, ad esempio un'applicazione Windows Form, un'applicazione console, un Web Form o un servizio Web ASP.NET oppure un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="f869c-104">However, with only a few lines of code, you can also run a package from a custom application such as a Windows Forms application, a console application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
 <span data-ttu-id="f869c-105">In questo argomento viene illustrato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f869c-105">This topic discusses:</span></span>  
  
-   <span data-ttu-id="f869c-106">Caricamento di un pacchetto a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f869c-106">Loading a package programmatically</span></span>  
  
-   <span data-ttu-id="f869c-107">Esecuzione di un pacchetto a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f869c-107">Running a package programmatically</span></span>  
  
 <span data-ttu-id="f869c-108">Tutti i metodi utilizzati in questo argomento per caricare ed eseguire pacchetti richiedono un riferimento all'assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="f869c-108">All of the methods used in this topic to load and run packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="f869c-109">Dopo aver aggiunto il riferimento in un nuovo progetto, importare lo spazio dei nomi <xref:Microsoft.SqlServer.Dts.Runtime> con un'istruzione `using` o `Imports`.</span><span class="sxs-lookup"><span data-stu-id="f869c-109">After adding the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="loading-a-package-programmatically"></a><span data-ttu-id="f869c-110">Caricamento di un pacchetto a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f869c-110">Loading a Package Programmatically</span></span>  
 <span data-ttu-id="f869c-111">Per caricare un pacchetto a livello di codice nel computer locale, indipendentemente dal fatto che il pacchetto sia archiviato in modalità locale o remota, chiamare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f869c-111">To load a package programmatically on the local computer, whether the package is stored locally or remotely, call one of the following methods:</span></span>  
  
|<span data-ttu-id="f869c-112">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="f869c-112">Storage Location</span></span>|<span data-ttu-id="f869c-113">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="f869c-113">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="f869c-114">File</span><span class="sxs-lookup"><span data-stu-id="f869c-114">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>|  
|<span data-ttu-id="f869c-115">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="f869c-115">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f869c-116">I metodi della classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> per l'utilizzo dell'archivio pacchetti SSIS supportano solo ".", localhost o il nome del server locale.</span><span class="sxs-lookup"><span data-stu-id="f869c-116">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="f869c-117">Non è possibile utilizzare "(local)".</span><span class="sxs-lookup"><span data-stu-id="f869c-117">You cannot use "(local)".</span></span>  
  
## <a name="running-a-package-programmatically"></a><span data-ttu-id="f869c-118">Esecuzione di un pacchetto a livello di codice</span><span class="sxs-lookup"><span data-stu-id="f869c-118">Running a Package Programmatically</span></span>  
 <span data-ttu-id="f869c-119">Lo sviluppo di un'applicazione personalizzata in codice gestito che esegue un pacchetto nel computer locale richiede l'approccio seguente.</span><span class="sxs-lookup"><span data-stu-id="f869c-119">Developing a custom application in managed code that runs a package on the local computer requires the following approach.</span></span> <span data-ttu-id="f869c-120">I passaggi riepilogati in questa sezione sono illustrati nell'applicazione console di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f869c-120">The steps summarized here are demonstrated in the sample console application that follows.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically"></a><span data-ttu-id="f869c-121">Per eseguire un pacchetto a livello di codice nel computer locale</span><span class="sxs-lookup"><span data-stu-id="f869c-121">To run a package on the local computer programmatically</span></span>  
  
1.  <span data-ttu-id="f869c-122">Avviare l'ambiente di sviluppo di Visual Studio e creare una nuova applicazione nel linguaggio di sviluppo preferito.</span><span class="sxs-lookup"><span data-stu-id="f869c-122">Start the Visual Studio development environment, and create a new application in your preferred development language.</span></span> <span data-ttu-id="f869c-123">In questo esempio viene utilizzata un'applicazione console. Tuttavia, è anche possibile eseguire un pacchetto da un'applicazione Windows Form, da un Web Form o servizio Web ASP.NET oppure da un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="f869c-123">This example uses a console application; however you can also run a package from a Windows Forms application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
2.  <span data-ttu-id="f869c-124">Scegliere **Aggiungi riferimento** dal menu **Progetto**, quindi aggiungere un riferimento a **Microsoft.SqlServer.ManagedDTS.dll**.</span><span class="sxs-lookup"><span data-stu-id="f869c-124">On the **Project** menu, click **Add Reference** and add a reference to **Microsoft.SqlServer.ManagedDTS.dll**.</span></span> <span data-ttu-id="f869c-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f869c-125">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="f869c-126">Usare l' `Imports` istruzione Visual Basic o l' `using` istruzione C# per importare lo spazio dei nomi **Microsoft. SqlServer. Dts. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="f869c-126">Use the Visual Basic `Imports` statement or the C# `using` statement to import the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
4.  <span data-ttu-id="f869c-127">Aggiungere il codice seguente nella routine principale.</span><span class="sxs-lookup"><span data-stu-id="f869c-127">Add the following code in the main routine.</span></span> <span data-ttu-id="f869c-128">L'applicazione console completata dovrebbe essere simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f869c-128">The completed console application should look like the following example.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f869c-129">Nel codice di esempio è illustrato il caricamento del pacchetto dal file system tramite il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>.</span><span class="sxs-lookup"><span data-stu-id="f869c-129">The sample code demonstrates loading the package from the file system by using the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A> method.</span></span> <span data-ttu-id="f869c-130">Tuttavia, è anche possibile caricare il pacchetto dal database MSDB chiamando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> o dall'archivio pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] chiamando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>.</span><span class="sxs-lookup"><span data-stu-id="f869c-130">However you can also load the package from the MSDB database by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> method, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> method.</span></span>  
  
5.  <span data-ttu-id="f869c-131">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="f869c-131">Run the project.</span></span> <span data-ttu-id="f869c-132">Nel codice di esempio viene eseguito il pacchetto di esempio CalculatedColumns, installato con gli esempi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f869c-132">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="f869c-133">Il risultato dell'esecuzione del pacchetto è visualizzato nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="f869c-133">The result of package execution is displayed in the console window.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="f869c-134">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="f869c-134">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, Nothing)  
    pkgResults = pkg.Execute()  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, null);  
      pkgResults = pkg.Execute();  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
## <a name="capturing-events-from-a-running-package"></a><span data-ttu-id="f869c-135">Acquisizione di eventi da un pacchetto in esecuzione</span><span class="sxs-lookup"><span data-stu-id="f869c-135">Capturing Events from a Running Package</span></span>  
 <span data-ttu-id="f869c-136">Quando si esegue un pacchetto a livello di codice, come illustrato nell'esempio precedente, è anche possibile acquisire errori e altri eventi che si verificano durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f869c-136">When you run a package programmatically as shown in the preceding sample, you may also want to capture errors and other events that occur as the package executes.</span></span> <span data-ttu-id="f869c-137">A tale scopo, aggiungere una classe che eredita dalla classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> e passare un riferimento a tale classe quando si carica il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f869c-137">You can accomplish this by adding a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class, and by passing a reference to that class when you load the package.</span></span> <span data-ttu-id="f869c-138">Anche se nell'esempio seguente viene acquisito solo l'evento <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A>, la classe <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> consente di acquisire molti altri eventi.</span><span class="sxs-lookup"><span data-stu-id="f869c-138">Although the following example captures only the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A> event, there are many other events that the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class lets you capture.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically-and-capture-package-events"></a><span data-ttu-id="f869c-139">Per eseguire un pacchetto a livello di codice nel computer locale e acquisire gli eventi del pacchetto</span><span class="sxs-lookup"><span data-stu-id="f869c-139">To run a package on the local computer programmatically and capture package events</span></span>  
  
1.  <span data-ttu-id="f869c-140">Attenersi alla procedura descritta nell'esempio precedente per creare un progetto.</span><span class="sxs-lookup"><span data-stu-id="f869c-140">Follow the steps in the preceding example to create a project for this example.</span></span>  
  
2.  <span data-ttu-id="f869c-141">Aggiungere il codice seguente nella routine principale.</span><span class="sxs-lookup"><span data-stu-id="f869c-141">Add the following code in the main routine.</span></span> <span data-ttu-id="f869c-142">L'applicazione console completata dovrebbe essere simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f869c-142">The completed console application should look like the following example.</span></span>  
  
3.  <span data-ttu-id="f869c-143">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="f869c-143">Run the project.</span></span> <span data-ttu-id="f869c-144">Nel codice di esempio viene eseguito il pacchetto di esempio CalculatedColumns, installato con gli esempi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f869c-144">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="f869c-145">Il risultato dell'esecuzione del pacchetto è visualizzato nella finestra della console, insieme agli eventuali errori che si verificano.</span><span class="sxs-lookup"><span data-stu-id="f869c-145">The result of package execution is displayed in the console window, along with any errors that occur.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="f869c-146">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="f869c-146">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    Dim eventListener As New EventListener()  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, eventListener)  
    pkgResults = pkg.Execute(Nothing, Nothing, eventListener, Nothing, Nothing)  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
  
Class EventListener  
  Inherits DefaultEvents  
  
  Public Overrides Function OnError(ByVal source As Microsoft.SqlServer.Dts.Runtime.DtsObject, _  
    ByVal errorCode As Integer, ByVal subComponent As String, ByVal description As String, _  
    ByVal helpFile As String, ByVal helpContext As Integer, _  
    ByVal idofInterfaceWithError As String) As Boolean  
  
    ' Add application-specific diagnostics here.  
    Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description)  
    Return False  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppWithEventsCS  
{  
  class MyEventListener : DefaultEvents  
  {  
    public override bool OnError(DtsObject source, int errorCode, string subComponent,   
      string description, string helpFile, int helpContext, string idofInterfaceWithError)  
    {  
      // Add application-specific diagnostics here.  
      Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description);  
      return false;  
    }  
  }  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      MyEventListener eventListener = new MyEventListener();  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, eventListener);  
      pkgResults = pkg.Execute(null, null, eventListener, null, null);  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
<span data-ttu-id="f869c-147">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f869c-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f869c-148">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="f869c-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f869c-149">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="f869c-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f869c-150">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f869c-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f869c-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f869c-151">See Also</span></span>  
 <span data-ttu-id="f869c-152">[Informazioni sulle differenze tra l'esecuzione locale e remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="f869c-152">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="f869c-153">[Caricamento ed esecuzione di un pacchetto remoto a livello di programmazione](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="f869c-153">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="f869c-154">Caricamento dell'output di un pacchetto locale</span><span class="sxs-lookup"><span data-stu-id="f869c-154">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
