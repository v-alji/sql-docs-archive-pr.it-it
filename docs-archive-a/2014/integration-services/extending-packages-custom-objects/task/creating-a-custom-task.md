---
title: Creazione di un'attività personalizzata | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom tasks [Integration Services], creating
ms.assetid: 42965c09-1782-4cdb-9ce1-216af4c23e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f752acad7a442a8e0aad2d24e94938c14195a35d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629926"
---
# <a name="creating-a-custom-task"></a><span data-ttu-id="ed27c-102">Creazione di un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ed27c-102">Creating a Custom Task</span></span>
  <span data-ttu-id="ed27c-103">I passaggi per la creazione di un'attività personalizzata sono simili a quelli richiesti per la creazione di qualsiasi altro oggetto personalizzato per [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ed27c-103">The steps involved in creating a custom task are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="ed27c-104">Creare una nuova classe che eredita dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="ed27c-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="ed27c-105">Per un'attività, la classe di base è [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span><span class="sxs-lookup"><span data-stu-id="ed27c-105">For a task, the base class is [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span></span>  
  
-   <span data-ttu-id="ed27c-106">Applicare alla classe l'attributo che identifica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="ed27c-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="ed27c-107">Per un'attività, l'attributo è <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ed27c-107">For a task, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span></span>  
  
-   <span data-ttu-id="ed27c-108">Eseguire l'override dell'implementazione dei metodi e delle proprietà della classe di base.</span><span class="sxs-lookup"><span data-stu-id="ed27c-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="ed27c-109">Per un'attività, questi includono i metodi <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed27c-109">For a task, these include the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
-   <span data-ttu-id="ed27c-110">Se si desidera, sviluppare un'interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ed27c-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="ed27c-111">Per un'attività, è richiesta una classe tramite cui venga implementata l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>.</span><span class="sxs-lookup"><span data-stu-id="ed27c-111">For a task, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface.</span></span>  
  
## <a name="getting-started-with-a-custom-task"></a><span data-ttu-id="ed27c-112">Introduzione alle attività personalizzate</span><span class="sxs-lookup"><span data-stu-id="ed27c-112">Getting Started with a Custom Task</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="ed27c-113">Creazione di progetti e classi</span><span class="sxs-lookup"><span data-stu-id="ed27c-113">Creating Projects and Classes</span></span>  
 <span data-ttu-id="ed27c-114">Poiché tutte le attività gestite derivano dalla classe di base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), il primo passaggio da completare quando si crea un'attività personalizzata consiste nel creare un progetto di libreria di classi nel linguaggio di programmazione gestito preferito e creare una classe che eredita dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="ed27c-114">Because all managed tasks derive from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, the first step when you create a custom task is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="ed27c-115">In questa classe derivata si eseguirà l'override dei metodi e delle proprietà della classe di base per implementare la funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ed27c-115">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="ed27c-116">Nella stessa soluzione creare un secondo progetto di libreria di classi per l'interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ed27c-116">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="ed27c-117">Per semplificare lo sviluppo, si consiglia di utilizzare un assembly distinto per l'interfaccia utente, perché in questo modo è possibile e ridistribuire la gestione connessione o la relativa interfaccia utente in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="ed27c-117">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="ed27c-118">Configurare entrambi i progetti per firmare gli assembly che verranno generati durante la compilazione utilizzando un file di chiave con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="ed27c-118">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtstask-attribute"></a><span data-ttu-id="ed27c-119">Applicazione dell'attributo DtsTask</span><span class="sxs-lookup"><span data-stu-id="ed27c-119">Applying the DtsTask Attribute</span></span>  
 <span data-ttu-id="ed27c-120">Applicare l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> alla classe creata per identificarla come attività.</span><span class="sxs-lookup"><span data-stu-id="ed27c-120">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class that you have created to identify it as a task.</span></span> <span data-ttu-id="ed27c-121">Questo attributo fornisce informazioni in fase di progettazione, ad esempio il nome, la descrizione e il tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="ed27c-121">This attribute provides design-time information such as the name, description, and task type of the task.</span></span>  
  
 <span data-ttu-id="ed27c-122">Utilizzare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> per collegare l'attività alla relativa interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ed27c-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property to link the task to its custom user interface.</span></span> <span data-ttu-id="ed27c-123">Per ottenere il token di chiave pubblica richiesto per questa proprietà, è possibile usare **sn.exe -t** per visualizzare il token di chiave pubblica dal file della coppia di chiavi (con estensione snk) che si intende usare per firmare l'assembly dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ed27c-123">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
## <a name="building-deploying-and-debugging-a-custom-task"></a><span data-ttu-id="ed27c-124">Compilazione, distribuzione e debug di attività personalizzate</span><span class="sxs-lookup"><span data-stu-id="ed27c-124">Building, Deploying, and Debugging a Custom Task</span></span>  
 <span data-ttu-id="ed27c-125">I passaggi per la compilazione, la distribuzione e il debug di un'attività personalizzata in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sono simili a quelli richiesti per altri tipi di oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ed27c-125">The steps for building, deploying, and debugging a custom task in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="ed27c-126">Per altre informazioni, vedere [Compilazione, distribuzione e debug di oggetti personalizzati](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="ed27c-126">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="ed27c-127">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ed27c-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ed27c-128">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="ed27c-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ed27c-129">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="ed27c-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ed27c-130">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="ed27c-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed27c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed27c-131">See Also</span></span>  
 <span data-ttu-id="ed27c-132">[Creazione di un'attività personalizzata](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="ed27c-132">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="ed27c-133">[Scrittura del codice di un'attività personalizzata](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="ed27c-133">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="ed27c-134">Sviluppo di un'interfaccia utente per un'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="ed27c-134">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
