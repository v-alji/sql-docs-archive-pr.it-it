---
title: Creazione di un pacchetto a livello di programmazione | Microsoft Docs
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
- SSIS packages, creating
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
ms.assetid: e44bcc70-32d3-43e8-a84b-29aef819d5d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1159784fc95dd86d9d33c4354291cc7c52812982
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715655"
---
# <a name="creating-a-package-programmatically"></a><span data-ttu-id="d1cfc-102">Creazione di un pacchetto a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="d1cfc-102">Creating a Package Programmatically</span></span>
  <span data-ttu-id="d1cfc-103">L'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.Package> rappresenta il contenitore di livello principale per tutti gli altri oggetti di una soluzione di progetto di [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1cfc-103">The <xref:Microsoft.SqlServer.Dts.Runtime.Package> object is the top-level container for all other objects in an [!INCLUDE[ssIS](../../includes/ssis-md.md)] project solution.</span></span> <span data-ttu-id="d1cfc-104">Essendo il contenitore di livello principale, il pacchetto è il primo oggetto creato. Gli oggetti successivi vengono aggiunti e quindi eseguiti nel contesto del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-104">As the top-level container, the package is the first object created, and subsequent objects are added to it, and then executed within the context of the package.</span></span> <span data-ttu-id="d1cfc-105">Il pacchetto non sposta né trasforma dati,</span><span class="sxs-lookup"><span data-stu-id="d1cfc-105">The package itself does not move or transform data.</span></span> <span data-ttu-id="d1cfc-106">ma si basa sulle attività che contiene per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-106">The package relies on the tasks it contains to perform the work.</span></span> <span data-ttu-id="d1cfc-107">Le attività eseguono la maggior parte delle operazioni del pacchetto e ne definiscono la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-107">Tasks perform most of the work performed by a package, and define the functionality of a package.</span></span> <span data-ttu-id="d1cfc-108">Per creare un pacchetto sono sufficienti tre righe di codice, ma vengono aggiunti vari oggetti <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e attività per fornire funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-108">A package is created and executed with just three lines of code, but various tasks and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects are added to give additional functionality to your package.</span></span> <span data-ttu-id="d1cfc-109">In questa sezione viene descritto come creare un pacchetto a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-109">This section discusses how to programmatically create a package.</span></span> <span data-ttu-id="d1cfc-110">Non vengono fornite informazioni sulla creazione di attività o di oggetti <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>,</span><span class="sxs-lookup"><span data-stu-id="d1cfc-110">It does not provide information about how to create the tasks or the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span> <span data-ttu-id="d1cfc-111">che verranno descritti nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-111">These are covered in later sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1cfc-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1cfc-112">Example</span></span>  
 <span data-ttu-id="d1cfc-113">Per scrivere codice utilizzando l'IDE di Visual Studio, è necessario un riferimento a Microsoft.SqlServer.ManagedDTS.dll per creare un'istruzione `using` (`Imports` in Visual Basic .NET) in Microsoft.SqlServer.Dts.Runtime.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-113">To write code using the Visual Studio IDE, a reference to Microsoft.SqlServer.ManagedDTS.DLL is required in order to create a `using` statement (`Imports` in Visual Basic .NET) to the Microsoft.SqlServer.Dts.Runtime.</span></span> <span data-ttu-id="d1cfc-114">Nell'esempio di codice seguente è illustrata la creazione di un pacchetto vuoto.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-114">The following code sample demonstrates creating an empty package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package;  
      package = new Package();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package  
    package = New Package  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="d1cfc-115">Per compilare ed eseguire l'esempio, premere F5 in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-115">To compile and run the sample, press F5 in Visual Studio.</span></span> <span data-ttu-id="d1cfc-116">Per compilare il codice usando il compilatore C#, **csc.exe**, dal prompt dei comandi per la compilazione usare il comando e i riferimenti di file seguenti, sostituendo *\<filename>* con il nome del file con estensione cs o vb e assegnando un *\<outputfilename>* a scelta.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-116">To build the code using the C# compiler, **csc.exe**, at the command prompt to compile, use the following command and file references, replacing the *\<filename>* with the name of the .cs or .vb file, and giving it an *\<outputfilename>* of your choice.</span></span>  
  
 <span data-ttu-id="d1cfc-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="d1cfc-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="d1cfc-118">Per compilare il codice usando il compilatore Visual Basic .NET, **vbc.exe**, dal prompt dei comandi per la compilazione usare il comando e i riferimenti di file seguenti.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-118">To build the code using the Visual Basic .NET compiler, **vbc.exe**, at the command prompt to compile, use the following command and file references.</span></span>  
  
 <span data-ttu-id="d1cfc-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="d1cfc-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="d1cfc-120">È anche possibile creare un pacchetto caricando un pacchetto esistente salvato su disco, nel file system o in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1cfc-120">You can also create a package by loading an existing package that was saved on disk, in the file system, or to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d1cfc-121">La differenza è che viene dapprima creato l'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.Application> e quindi nell'oggetto del pacchetto viene inserito uno dei metodi di overload dell'applicazione: `LoadPackage` per i file flat, `LoadFromSQLServer` per i pacchetti salvati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> per i pacchetti salvati nel file system.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-121">The difference is that the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object is first created, and then the package object is filled by one of the Application's overloaded methods: `LoadPackage` for flat files, `LoadFromSQLServer` for packages saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> for packages saved to the file system.</span></span> <span data-ttu-id="d1cfc-122">Nell'esempio seguente viene caricato un pacchetto esistente da disco, quindi vengono visualizzate diverse proprietà del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-122">The following example loads an existing package from disk, and then views several properties on the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class ApplicationTests  
  {  
    static void Main(string[] args)  
    {  
      // The variable pkg points to the location of the  
      // ExecuteProcess package sample that was installed with  
      // the SSIS samples.  
      string pkg = @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx";  
  
      Application app = new Application();  
      Package p = app.LoadPackage(pkg, null);  
  
      // Now that the package is loaded, we can query on  
      // its properties.  
      int n = p.Configurations.Count;  
      DtsProperty p2 = p.Properties["VersionGUID"];  
      DTSProtectionLevel pl = p.ProtectionLevel;  
  
      Console.WriteLine("Number of configurations = " + n.ToString());  
      Console.WriteLine("VersionGUID = " + (string)p2.GetValue(p));  
      Console.WriteLine("ProtectionLevel = " + pl.ToString());  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module ApplicationTests  
  
  Sub Main()  
  
    ' The variable pkg points to the location of the  
    ' ExecuteProcess package sample that was installed with  
    ' the SSIS samples.  
    Dim pkg As String = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx"  
  
    Dim app As Application = New Application()  
    Dim p As Package = app.LoadPackage(pkg, Nothing)  
  
    ' Now that the package is loaded, we can query on  
    ' its properties.  
    Dim n As Integer = p.Configurations.Count  
    Dim p2 As DtsProperty = p.Properties("VersionGUID")  
    Dim pl As DTSProtectionLevel = p.ProtectionLevel  
  
    Console.WriteLine("Number of configurations = " & n.ToString())  
    Console.WriteLine("VersionGUID = " & CType(p2.GetValue(p), String))  
    Console.WriteLine("ProtectionLevel = " & pl.ToString())  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="d1cfc-123">**Esempio di output**</span><span class="sxs-lookup"><span data-stu-id="d1cfc-123">**Sample Output:**</span></span>  
  
 `Number of configurations = 2`  
  
 `VersionGUID = {09016682-89B8-4406-AAC9-AF1E527FF50F}`  
  
 `ProtectionLevel = DontSaveSensitive`  
  
## <a name="external-resources"></a><span data-ttu-id="d1cfc-124">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="d1cfc-124">External Resources</span></span>  
  
-   <span data-ttu-id="d1cfc-125">Intervento nel blog su un [esempio di API relativo all'origine e alla destinazione OleDB](https://go.microsoft.com/fwlink/?LinkId=220824) sul sito Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-125">Blog entry, [API Sample - OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), on blogs.msdn.com.</span></span>  
  
-   <span data-ttu-id="d1cfc-126">Intervento nel blog sull'[aggiornamento di EzAPI per SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) sul sito Web blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-126">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="d1cfc-127">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d1cfc-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d1cfc-128">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="d1cfc-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d1cfc-129">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="d1cfc-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d1cfc-130">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="d1cfc-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1cfc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1cfc-131">See Also</span></span>  
 [<span data-ttu-id="d1cfc-132">Aggiunta di attività a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="d1cfc-132">Adding Tasks Programmatically</span></span>](../building-packages-programmatically/adding-tasks-programmatically.md)  
  
  
