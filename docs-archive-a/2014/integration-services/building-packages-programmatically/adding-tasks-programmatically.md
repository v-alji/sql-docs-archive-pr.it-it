---
title: Aggiunta di attività a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], packages
- adding package tasks
ms.assetid: 5d4652d5-228c-4238-905c-346dd8503fdf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa61eb2fb87f45fe5b534b96280b8b4e2c21788d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627356"
---
# <a name="adding-tasks-programmatically"></a><span data-ttu-id="705f7-102">Aggiunta di attività a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="705f7-102">Adding Tasks Programmatically</span></span>
  <span data-ttu-id="705f7-103">È possibile aggiungere attività ai tipi di oggetti seguenti nel motore di runtime:</span><span class="sxs-lookup"><span data-stu-id="705f7-103">Tasks can be added to the following types of objects in the run-time engine:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Package>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Sequence>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>  
  
 <span data-ttu-id="705f7-104">Queste classi vengono considerate contenitori ed ereditano tutte la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A>.</span><span class="sxs-lookup"><span data-stu-id="705f7-104">These classes are considered containers, and they all inherit the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A> property.</span></span> <span data-ttu-id="705f7-105">I contenitori possono contenere una raccolta di attività, ovvero oggetti eseguibili elaborati dal runtime durante l'esecuzione del contenitore.</span><span class="sxs-lookup"><span data-stu-id="705f7-105">Containers can contain a collection of tasks, which are executable objects processed by the runtime during execution of the container.</span></span> <span data-ttu-id="705f7-106">L'ordine di esecuzione degli oggetti nella raccolta è determinato da qualsiasi oggetto <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> impostato su ogni attività nei contenitori.</span><span class="sxs-lookup"><span data-stu-id="705f7-106">The order of execution of the objects in the collection is determined any <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> set on each task in the containers.</span></span> <span data-ttu-id="705f7-107">I vincoli di precedenza rendono possibile la diramazione dell'esecuzione in base all'esito positivo, all'esito negativo o al completamento di un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.Executable> nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="705f7-107">Precedence constraints enable execution branching based on the success, failure, or completion of an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> in the collection.</span></span>  
  
 <span data-ttu-id="705f7-108">Ogni contenitore include una raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Executables> che contiene i singoli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="705f7-108">Each container has an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection that contains the individual <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects.</span></span> <span data-ttu-id="705f7-109">Ogni attività eseguibile eredita e implementa il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> e il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="705f7-109">Each executable task inherits and implements the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> method and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> method.</span></span> <span data-ttu-id="705f7-110">Questi due metodi vengono chiamati dal motore di runtime per elaborare ogni oggetto <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="705f7-110">These two methods are called by the run-time engine to process each <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span></span>  
  
 <span data-ttu-id="705f7-111">Per aggiungere un'attività a un pacchetto, è necessario un contenitore con una raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Executables> esistente.</span><span class="sxs-lookup"><span data-stu-id="705f7-111">To add a task to a package, you need a container with an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> existing collection.</span></span> <span data-ttu-id="705f7-112">Nella maggior parte dei casi, l'attività che verrà aggiunta alla raccolta è un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="705f7-112">Most of the time, the task that you will add to the collection is a package.</span></span> <span data-ttu-id="705f7-113">Per aggiungere l'eseguibile della nuova attività nella raccolta per tale contenitore, chiamare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="705f7-113">To add the new task executable into the collection for that container, you call the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method .</span></span> <span data-ttu-id="705f7-114">Il metodo include un solo parametro, ovvero una stringa che contiene il CLSID, il PROGID, il moniker STOCK o l'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> dell'attività da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="705f7-114">The method has a single parameter, a string, that contains the CLSID, PROGID, STOCK moniker, or <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> of the task you are adding.</span></span>  
  
## <a name="task-names"></a><span data-ttu-id="705f7-115">Nomi delle attività</span><span class="sxs-lookup"><span data-stu-id="705f7-115">Task Names</span></span>  
 <span data-ttu-id="705f7-116">Anche se è possibile specificare un'attività in base al nome o all'ID, il moniker `STOCK` è il parametro utilizzato più di frequente nel metodo <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="705f7-116">Although you can specify a task by name or by ID, the `STOCK` moniker is the parameter used most often in the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method.</span></span> <span data-ttu-id="705f7-117">Per aggiungere un'attività a un eseguibile identificato dal moniker `STOCK`, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="705f7-117">To add a task to an executable identified by the `STOCK` moniker, use the following syntax:</span></span>  
  
```csharp  
Executable exec = package.Executables.Add("STOCK:BulkInsertTask");  
  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add("STOCK:BulkInsertTask")  
  
```  
  
 <span data-ttu-id="705f7-118">Nell'elenco seguente sono illustrati i nomi di ogni attività utilizzati dopo il moniker `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="705f7-118">The following list shows the names for each task that are used after the `STOCK` moniker.</span></span>  
  
-   <span data-ttu-id="705f7-119">ActiveXScriptTask</span><span class="sxs-lookup"><span data-stu-id="705f7-119">ActiveXScriptTask</span></span>  
  
-   <span data-ttu-id="705f7-120">BulkInsertTask</span><span class="sxs-lookup"><span data-stu-id="705f7-120">BulkInsertTask</span></span>  
  
-   <span data-ttu-id="705f7-121">ExecuteProcessTask</span><span class="sxs-lookup"><span data-stu-id="705f7-121">ExecuteProcessTask</span></span>  
  
-   <span data-ttu-id="705f7-122">ExecutePackageTask</span><span class="sxs-lookup"><span data-stu-id="705f7-122">ExecutePackageTask</span></span>  
  
-   <span data-ttu-id="705f7-123">Exec80PackageTask</span><span class="sxs-lookup"><span data-stu-id="705f7-123">Exec80PackageTask</span></span>  
  
-   <span data-ttu-id="705f7-124">FileSystemTask</span><span class="sxs-lookup"><span data-stu-id="705f7-124">FileSystemTask</span></span>  
  
-   <span data-ttu-id="705f7-125">FTPTask</span><span class="sxs-lookup"><span data-stu-id="705f7-125">FTPTask</span></span>  
  
-   <span data-ttu-id="705f7-126">MSMQTask</span><span class="sxs-lookup"><span data-stu-id="705f7-126">MSMQTask</span></span>  
  
-   <span data-ttu-id="705f7-127">PipelineTask</span><span class="sxs-lookup"><span data-stu-id="705f7-127">PipelineTask</span></span>  
  
-   <span data-ttu-id="705f7-128">ScriptTask</span><span class="sxs-lookup"><span data-stu-id="705f7-128">ScriptTask</span></span>  
  
-   <span data-ttu-id="705f7-129">SendMailTask</span><span class="sxs-lookup"><span data-stu-id="705f7-129">SendMailTask</span></span>  
  
-   <span data-ttu-id="705f7-130">SQLTask</span><span class="sxs-lookup"><span data-stu-id="705f7-130">SQLTask</span></span>  
  
-   <span data-ttu-id="705f7-131">TransferStoredProceduresTask</span><span class="sxs-lookup"><span data-stu-id="705f7-131">TransferStoredProceduresTask</span></span>  
  
-   <span data-ttu-id="705f7-132">TransferLoginsTask</span><span class="sxs-lookup"><span data-stu-id="705f7-132">TransferLoginsTask</span></span>  
  
-   <span data-ttu-id="705f7-133">TransferErrorMessagesTask</span><span class="sxs-lookup"><span data-stu-id="705f7-133">TransferErrorMessagesTask</span></span>  
  
-   <span data-ttu-id="705f7-134">TransferJobsTask</span><span class="sxs-lookup"><span data-stu-id="705f7-134">TransferJobsTask</span></span>  
  
-   <span data-ttu-id="705f7-135">TransferObjectsTask</span><span class="sxs-lookup"><span data-stu-id="705f7-135">TransferObjectsTask</span></span>  
  
-   <span data-ttu-id="705f7-136">TransferDatabaseTask</span><span class="sxs-lookup"><span data-stu-id="705f7-136">TransferDatabaseTask</span></span>  
  
-   <span data-ttu-id="705f7-137">WebServiceTask</span><span class="sxs-lookup"><span data-stu-id="705f7-137">WebServiceTask</span></span>  
  
-   <span data-ttu-id="705f7-138">WmiDataReaderTask</span><span class="sxs-lookup"><span data-stu-id="705f7-138">WmiDataReaderTask</span></span>  
  
-   <span data-ttu-id="705f7-139">WmiEventWatcherTask</span><span class="sxs-lookup"><span data-stu-id="705f7-139">WmiEventWatcherTask</span></span>  
  
-   <span data-ttu-id="705f7-140">XMLTask</span><span class="sxs-lookup"><span data-stu-id="705f7-140">XMLTask</span></span>  
  
 <span data-ttu-id="705f7-141">Se si preferisce una sintassi più esplicita o se l'attività che si desidera aggiungere non include un moniker STOCK, è possibile aggiungere l'attività all'eseguibile utilizzandone il nome lungo.</span><span class="sxs-lookup"><span data-stu-id="705f7-141">If you prefer a more explicit syntax, or if the task that you want to add does not have a STOCK moniker, you can add the task to the executable using its long name.</span></span> <span data-ttu-id="705f7-142">Questa sintassi richiede anche la specifica del numero di versione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="705f7-142">This syntax requires that you also specify the version number of the task.</span></span>  
  
```csharp  
Executable exec = package.Executables.Add(  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " +  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " +  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91");  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add( _  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " & _  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " & _  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91")  
```  
  
 <span data-ttu-id="705f7-143">È possibile ottenere il nome lungo dell'attività a livello di programmazione, senza la necessità di specificare la versione dell'attività, usando la proprietà **AssemblyQualifiedName** della classe, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="705f7-143">You can obtain the long name for the task programmatically, without having to specify the task version, by using the **AssemblyQualifiedName** property of the class, as shown in the following example.</span></span> <span data-ttu-id="705f7-144">Per questo esempio è richiesto un riferimento all'assembly Microsoft.SqlServer.SQLTask.</span><span class="sxs-lookup"><span data-stu-id="705f7-144">This example requires a reference to the Microsoft.SqlServer.SQLTask assembly.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask;  
...  
      Executable exec = package.Executables.Add(  
        typeof(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName);  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask  
...  
    Dim exec As Executable = package.Executables.Add( _  
      GetType(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName)  
```  
  
 <span data-ttu-id="705f7-145">Nell'esempio di codice seguente è illustrato come creare una raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Executables> da un nuovo pacchetto, quindi aggiungere un'attività File system e un'attività Inserimento bulk alla raccolta, tramite i relativi moniker `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="705f7-145">The following code example shows how to create an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection from a new package, and then add a File System task and a Bulk Insert task to the collection, by using their `STOCK` monikers.</span></span> <span data-ttu-id="705f7-146">Per questo esempio è richiesto un riferimento agli assembly Microsoft.SqlServer.FileSystemTask e Microsoft.SqlServer.BulkInsertTask.</span><span class="sxs-lookup"><span data-stu-id="705f7-146">This example requires a reference to the Microsoft.SqlServer.FileSystemTask and Microsoft.SqlServer.BulkInsertTask assemblies.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thBulkInsertTask = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        Console.WriteLine("Type {0}", taskHost.InnerObject.ToString());  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thBulkInsertTask As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      Console.WriteLine("Type {0}", taskHost.InnerObject.ToString())  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="705f7-147">**Esempio di output**</span><span class="sxs-lookup"><span data-stu-id="705f7-147">**Sample Output:**</span></span>  
  
 `Type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
## <a name="taskhost-container"></a><span data-ttu-id="705f7-148">Contenitore TaskHost</span><span class="sxs-lookup"><span data-stu-id="705f7-148">TaskHost Container</span></span>  
 <span data-ttu-id="705f7-149">La classe <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> è un contenitore che non viene visualizzato nell'interfaccia utente grafica, ma è molto importante nella programmazione.</span><span class="sxs-lookup"><span data-stu-id="705f7-149">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class is a container that does not appear in the graphical user interface, but is very important in programming.</span></span> <span data-ttu-id="705f7-150">Questa classe è un wrapper per ogni attività.</span><span class="sxs-lookup"><span data-stu-id="705f7-150">This class is a wrapper for every task.</span></span> <span data-ttu-id="705f7-151">Le attività aggiunte al pacchetto utilizzando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> come oggetto <xref:Microsoft.SqlServer.Dts.Runtime.Executable> possono essere sottoposte a cast come oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="705f7-151">Tasks that are added to the package by using the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object can be cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object.</span></span> <span data-ttu-id="705f7-152">Quando si esegue il cast di un'attività come <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, è possibile utilizzare proprietà e metodi aggiuntivi sull'attività.</span><span class="sxs-lookup"><span data-stu-id="705f7-152">When a task is cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, you can use additional properties and methods on the task.</span></span> <span data-ttu-id="705f7-153">È inoltre possibile accedere all'attività stessa tramite la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> di <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="705f7-153">Also, the task itself can be accessed through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="705f7-154">A seconda delle esigenze, è possibile decidere di mantenere l'attività come oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> in modo da poterne utilizzare le proprietà tramite la raccolta <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="705f7-154">Depending on your needs, you may decide to keep the task as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object so that you can use the properties of the task through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection.</span></span> <span data-ttu-id="705f7-155">Il vantaggio dell'utilizzo di <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> è la possibilità di scrivere codice più generico.</span><span class="sxs-lookup"><span data-stu-id="705f7-155">The advantage of using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> is that you can write more generic code.</span></span> <span data-ttu-id="705f7-156">Se è necessario codice molto specifico per un'attività, è consigliabile eseguire il cast dell'attività nell'oggetto appropriato.</span><span class="sxs-lookup"><span data-stu-id="705f7-156">If you need very specific code for a task, then you should cast the task to its appropriate object.</span></span>  
  
 <span data-ttu-id="705f7-157">Nell'esempio di codice seguente è illustrato come eseguire il cast di un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, che contiene <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, in un oggetto <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>.</span><span class="sxs-lookup"><span data-stu-id="705f7-157">The following code example shows how to cast a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, that contains a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> object.</span></span>  
  
```csharp  
BulkInsertTask myTask = thBulkInsertTask.InnerObject as BulkInsertTask;  
```  
  
```vb  
Dim myTask As BulkInsertTask = CType(thBulkInsertTask.InnerObject, BulkInsertTask)  
```  
  
 <span data-ttu-id="705f7-158">Nell'esempio di codice seguente è illustrato come eseguire il cast dell'eseguibile in <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, quindi utilizzare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> per determinare quale tipo di eseguibile è contenuto nell'host.</span><span class="sxs-lookup"><span data-stu-id="705f7-158">The following code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property to determine which type of executable is contained by the host.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask1 = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thFileSystemTask2 = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask)  
        {  
          // Do work with FileSystemTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        else if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask)  
        {  
          // Do work with BulkInsertTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        // Add additional statements to check InnerObject, if desired.  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask1 As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thFileSystemTask2 As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      If TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask Then  
        ' Do work with FileSystemTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      ElseIf TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask Then  
        ' Do work with BulkInsertTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      End If  
      ' Add additional statements to check InnerObject, if desired.  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="705f7-159">**Esempio di output**</span><span class="sxs-lookup"><span data-stu-id="705f7-159">**Sample Output:**</span></span>  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
 <span data-ttu-id="705f7-160">L'istruzione <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> restituisce un eseguibile di cui viene eseguito il cast in un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> dall'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.Executable> appena creato.</span><span class="sxs-lookup"><span data-stu-id="705f7-160">The <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> statement returns an executable that is cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object from the newly created <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object.</span></span>  
  
 <span data-ttu-id="705f7-161">Per impostare proprietà o chiamare metodi sul nuovo oggetto, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="705f7-161">To set properties or to call methods on the new object, you have two options:</span></span>  
  
1.  <span data-ttu-id="705f7-162">Utilizzare la raccolta <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> di <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="705f7-162">Use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="705f7-163">Ad esempio, per ottenere una proprietà dall'oggetto, utilizzare `th.Properties["propertyname"].GetValue(th))`.</span><span class="sxs-lookup"><span data-stu-id="705f7-163">For example, to obtain a property from the object, use `th.Properties["propertyname"].GetValue(th))`.</span></span> <span data-ttu-id="705f7-164">Per impostare una proprietà, utilizzare `th.Properties["propertyname"].SetValue(th, <value>);`.</span><span class="sxs-lookup"><span data-stu-id="705f7-164">To set a property, use `th.Properties["propertyname"].SetValue(th, <value>);`.</span></span>  
  
2.  <span data-ttu-id="705f7-165">Eseguire il cast di <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> di <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> nella classe dell'attività.</span><span class="sxs-lookup"><span data-stu-id="705f7-165">Cast the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task class.</span></span> <span data-ttu-id="705f7-166">Ad esempio, per eseguire il cast dell'attività Inserimento bulk in <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> dopo che è stata aggiunta a un pacchetto come <xref:Microsoft.SqlServer.Dts.Runtime.Executable> e successivamente ne è stato eseguito il cast in <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, utilizzare `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span><span class="sxs-lookup"><span data-stu-id="705f7-166">For example, to cast the Bulk Insert task to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> after it has been added to a package as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> and subsequently cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, use `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span></span>  
  
 <span data-ttu-id="705f7-167">L'utilizzo della classe <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> nel codice, invece dell'esecuzione del cast nella classe specifica dell'attività, presenta i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="705f7-167">Using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class in code, instead of casting to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="705f7-168">Il provider <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> non richiede un riferimento all'assembly nel codice.</span><span class="sxs-lookup"><span data-stu-id="705f7-168">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> provider does not require a reference to the assembly in the code.</span></span>  
  
-   <span data-ttu-id="705f7-169">È possibile progettare routine generiche che funzionano per qualsiasi attività, perché non è necessario conoscere il nome dell'attività in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="705f7-169">You can code generic routines that work for any task, because you do not have to know the name of the task at compile time.</span></span> <span data-ttu-id="705f7-170">Tali routine generiche includono i metodi in cui si passa il nome dell'attività al metodo e il codice del metodo funziona per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="705f7-170">Such generic routines include methods where you pass in the name of the task to the method, and the method code works for all tasks.</span></span> <span data-ttu-id="705f7-171">Si tratta di un metodo efficace per la scrittura di codice di test.</span><span class="sxs-lookup"><span data-stu-id="705f7-171">This is a good method for writing test code.</span></span>  
  
 <span data-ttu-id="705f7-172">L'esecuzione del cast da <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> nella classe specifica dell'attività presenta i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="705f7-172">Casting from the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="705f7-173">Il progetto di Visual Studio rende disponibile il completamento delle istruzioni (IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="705f7-173">The Visual Studio project gives you statement completion (IntelliSense).</span></span>  
  
-   <span data-ttu-id="705f7-174">È possibile che il codice venga eseguito più velocemente.</span><span class="sxs-lookup"><span data-stu-id="705f7-174">The code may run faster.</span></span>  
  
-   <span data-ttu-id="705f7-175">Gli oggetti specifici dell'attività consentono l'associazione anticipata e le risultanti ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="705f7-175">Task-specific objects enable early binding and the resulting optimizations.</span></span> <span data-ttu-id="705f7-176">Per ulteriori informazioni sull'associazione anticipata e tardiva, vedere l'argomento corrispondente in Concetti sul linguaggio Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="705f7-176">For more information about early and late binding, see the topic "Early and Late Binding" in Visual Basic Language Concepts.</span></span>  
  
 <span data-ttu-id="705f7-177">L'esempio di codice seguente si basa sul concetto di riutilizzo del codice dell'attività.</span><span class="sxs-lookup"><span data-stu-id="705f7-177">The following code example expands on the concept of reusing task code.</span></span> <span data-ttu-id="705f7-178">Anziché eseguire il cast delle attività negli equivalenti specifici della classe, nell'esempio di codice viene illustrato come eseguire il cast dell'eseguibile in un oggetto <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, quindi viene utilizzato <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> per scrivere codice generico per tutte le attività.</span><span class="sxs-lookup"><span data-stu-id="705f7-178">Instead of casting tasks to their specific class equivalents, the code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then uses the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> to write generic code against all the tasks.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
  
      string[] tasks = { "STOCK:SQLTask", "STOCK:ScriptTask",   
        "STOCK:ExecuteProcessTask", "STOCK:PipelineTask",   
        "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask" };  
  
      foreach (string s in tasks)  
      {  
        TaskHost taskhost = package.Executables.Add(s) as TaskHost;  
        DtsProperties props = taskhost.Properties;  
        Console.WriteLine("Enumerating properties on " + taskhost.Name);  
        Console.WriteLine(" TaskHost.InnerObject is " + taskhost.InnerObject.ToString());  
        Console.WriteLine();  
  
        foreach (DtsProperty prop in props)  
        {  
          Console.WriteLine("Properties for " + prop.Name);  
          Console.WriteLine("Name : " + prop.Name);  
          Console.WriteLine("Type : " + prop.Type.ToString());  
          Console.WriteLine("Readable : " + prop.Get.ToString());  
          Console.WriteLine("Writable : " + prop.Set.ToString());  
          Console.WriteLine();  
        }  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package = New Package()  
  
    Dim tasks() As String = New String() {"STOCK:SQLTask", "STOCK:ScriptTask", _  
              "STOCK:ExecuteProcessTask", "STOCK:PipelineTask", _  
              "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask"}  
  
    For Each s As String In tasks  
  
      Dim taskhost As TaskHost = CType(package.Executables.Add(s), TaskHost)  
      Dim props As DtsProperties = taskhost.Properties  
      Console.WriteLine("Enumerating properties on " & taskhost.Name)  
      Console.WriteLine(" TaskHost.InnerObject is " & taskhost.InnerObject.ToString())  
      Console.WriteLine()  
  
      For Each prop As DtsProperty In props  
        Console.WriteLine("Properties for " + prop.Name)  
        Console.WriteLine(" Name : " + prop.Name)  
        Console.WriteLine(" Type : " + prop.Type.ToString())  
        Console.WriteLine(" Readable : " + prop.Get.ToString())  
        Console.WriteLine(" Writable : " + prop.Set.ToString())  
        Console.WriteLine()  
      Next  
  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="705f7-179">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="705f7-179">External Resources</span></span>  
 <span data-ttu-id="705f7-180">Intervento nel blog sull'[aggiornamento di EzAPI per SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) sul sito Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="705f7-180">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="705f7-181">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="705f7-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="705f7-182">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="705f7-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="705f7-183">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="705f7-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="705f7-184">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="705f7-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="705f7-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="705f7-185">See Also</span></span>  
 [<span data-ttu-id="705f7-186">Connessione di attività a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="705f7-186">Connecting Tasks Programmatically</span></span>](../building-packages-programmatically/connecting-tasks-programmatically.md)  
  
  
