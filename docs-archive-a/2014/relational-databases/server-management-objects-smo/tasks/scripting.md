---
title: Scripting | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- dependencies [SMO]
- scripts [SMO]
ms.assetid: 13a35511-3987-426b-a3b7-3b2e83900dc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: bf46798597de021976cefa943a17500e773f9274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716172"
---
# <a name="scripting"></a><span data-ttu-id="df1d0-102">Scripting</span><span class="sxs-lookup"><span data-stu-id="df1d0-102">Scripting</span></span>
  <span data-ttu-id="df1d0-103">In SMO la generazione di script è controllata dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Scripter> e dai relativi oggetti figlio oppure dal metodo `Script` in oggetti singoli.</span><span class="sxs-lookup"><span data-stu-id="df1d0-103">Scripting in SMO is controlled by the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects, or the `Script` method on individual objects.</span></span> <span data-ttu-id="df1d0-104">L' <xref:Microsoft.SqlServer.Management.Smo.Scripter> oggetto controlla il mapping tra le relazioni di dipendenza per gli oggetti in un'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df1d0-104">The <xref:Microsoft.SqlServer.Management.Smo.Scripter> object controls the mapping out of dependency relationships for objects on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="df1d0-105">La generazione di script avanzata tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Scripter> e i relativi oggetti figlio è un processo a tre fasi:</span><span class="sxs-lookup"><span data-stu-id="df1d0-105">Advanced scripting by using the <xref:Microsoft.SqlServer.Management.Smo.Scripter> object and its child objects is a three phase process:</span></span>  
  
1.  <span data-ttu-id="df1d0-106">Individuazione</span><span class="sxs-lookup"><span data-stu-id="df1d0-106">Discovery</span></span>  
  
2.  <span data-ttu-id="df1d0-107">Generazione dell'elenco</span><span class="sxs-lookup"><span data-stu-id="df1d0-107">List generation</span></span>  
  
3.  <span data-ttu-id="df1d0-108">Generazione dello script</span><span class="sxs-lookup"><span data-stu-id="df1d0-108">Script generation</span></span>  
  
 <span data-ttu-id="df1d0-109">Nella fase di individuazione viene utilizzato l'oggetto <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker>.</span><span class="sxs-lookup"><span data-stu-id="df1d0-109">The discovery phase uses the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object.</span></span> <span data-ttu-id="df1d0-110">A partire da un elenco URN di oggetti, il metodo <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> restituisce un oggetto <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> per gli oggetti presenti nell'elenco URN.</span><span class="sxs-lookup"><span data-stu-id="df1d0-110">Given an URN list of objects, the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.DiscoverDependencies%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker> object returns a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object for the objects in the URN list.</span></span> <span data-ttu-id="df1d0-111">Il parametro Boolean *fParents* viene utilizzato per indicare se gli elementi padre o gli elementi figlio dell'oggetto specificato devono essere individuati.</span><span class="sxs-lookup"><span data-stu-id="df1d0-111">The Boolean *fParents* parameter is used to select whether the parents or the children of the specified object are to be discovered.</span></span> <span data-ttu-id="df1d0-112">In questa fase è possibile modificare l'albero delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="df1d0-112">The dependency tree can be modified at this stage.</span></span>  
  
 <span data-ttu-id="df1d0-113">Nella fase di generazione dell'elenco viene passato l'albero e viene restituito l'elenco risultante.</span><span class="sxs-lookup"><span data-stu-id="df1d0-113">In the list generation phase, the tree is passed in and the resulting list is returned.</span></span> <span data-ttu-id="df1d0-114">Questo elenco di oggetti è ordinato secondo la generazione di script e può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="df1d0-114">This object list is in scripting order and can be manipulated.</span></span>  
  
 <span data-ttu-id="df1d0-115">Nelle fasi di generazione dell'elenco viene utilizzato il metodo <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> per restituire un oggetto <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span><span class="sxs-lookup"><span data-stu-id="df1d0-115">The list generation phases use the <xref:Microsoft.SqlServer.Management.Smo.DependencyWalker.WalkDependencies%2A> method to return a <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span></span> <span data-ttu-id="df1d0-116">In questa fase è possibile modificare <xref:Microsoft.SqlServer.Management.Smo.DependencyTree>.</span><span class="sxs-lookup"><span data-stu-id="df1d0-116">The <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> can be modified at this stage.</span></span>  
  
 <span data-ttu-id="df1d0-117">Nella terza e ultima fase viene generato uno script con l'elenco e le opzioni di generazione script specificate.</span><span class="sxs-lookup"><span data-stu-id="df1d0-117">In the third and final phase, a script is generated with the specified list and scripting options.</span></span> <span data-ttu-id="df1d0-118">Il risultato viene restituito come un oggetto di sistema <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="df1d0-118">The result is returned as a <xref:System.Collections.Specialized.StringCollection> system object.</span></span> <span data-ttu-id="df1d0-119">In questa fase i nomi degli oggetti dipendenti vengono estratti dalla raccolta Elementi dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> e da proprietà come <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> e <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="df1d0-119">In this phase the dependent object names are then extracted from the Items collection of the <xref:Microsoft.SqlServer.Management.Smo.DependencyTree> object and properties such as <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.NumberOfSiblings%2A> and <xref:Microsoft.SqlServer.Management.Smo.DependencyTree.FirstChild%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df1d0-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="df1d0-120">Example</span></span>  
 <span data-ttu-id="df1d0-121">Per usare qualsiasi esempio di codice fornito, è necessario scegliere l'ambiente di programmazione, il modello di programmazione e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="df1d0-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="df1d0-122">Per ulteriori informazioni, vedere [creare un Visual Basic progetto SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [creare un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="df1d0-122">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="df1d0-123">Per questo esempio di codice è necessaria un'istruzione `Imports` per lo spazio dei nomi System.Collections.Specialized.</span><span class="sxs-lookup"><span data-stu-id="df1d0-123">This code example requires an `Imports` statement for the System.Collections.Specialized namespace.</span></span> <span data-ttu-id="df1d0-124">Inserire questa istruzione con le altre istruzioni Imports prima di qualsiasi dichiarazione nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="df1d0-124">Insert this with the other Imports statements, before any declarations in the application.</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
Imports System.Collections.Specialized  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-basic"></a><span data-ttu-id="df1d0-125">Generazione di script delle dipendenze per un database in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df1d0-125">Scripting Out the Dependencies for a Database in Visual Basic</span></span>  
 <span data-ttu-id="df1d0-126">In questo esempio di codice viene illustrato come individuare le dipendenze e scorrere l'elenco per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="df1d0-126">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
  
Public Class A  
   Public Shared Sub Main()  
      ' database name  
      Dim dbName As [String] = "AdventureWorksLT2012"   ' database name  
  
      ' Connect to the local, default instance of SQL Server.   
      Dim srv As New Server()  
  
      ' Reference the database.    
      Dim db As Database = srv.Databases(dbName)  
  
      ' Define a Scripter object and set the required scripting options.   
      Dim scrp As New Scripter(srv)  
      scrp.Options.ScriptDrops = False  
      scrp.Options.WithDependencies = True  
      scrp.Options.Indexes = True   ' To include indexes  
      scrp.Options.DriAllConstraints = True   ' to include referential constraints in the script  
  
      ' Iterate through the tables in database and script each one. Display the script.  
      For Each tb As Table In db.Tables  
         ' check if the table is not a system table  
         If tb.IsSystemObject = False Then  
            Console.WriteLine("-- Scripting for table " + tb.Name)  
  
            ' Generating script for table tb  
            Dim sc As System.Collections.Specialized.StringCollection = scrp.Script(New Urn() {tb.Urn})  
            For Each st As String In sc  
               Console.WriteLine(st)  
            Next  
            Console.WriteLine("--")  
         End If  
      Next  
   End Sub  
End Class  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-visual-c"></a><span data-ttu-id="df1d0-127">Generazione di script delle dipendenze per un database in Visual C#</span><span class="sxs-lookup"><span data-stu-id="df1d0-127">Scripting Out the Dependencies for a Database in Visual C#</span></span>  
 <span data-ttu-id="df1d0-128">In questo esempio di codice viene illustrato come individuare le dipendenze e scorrere l'elenco per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="df1d0-128">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
  
public class A {  
   public static void Main() {   
      String dbName = "AdventureWorksLT2012"; // database name  
  
      // Connect to the local, default instance of SQL Server.   
      Server srv = new Server();  
  
      // Reference the database.    
      Database db = srv.Databases[dbName];  
  
      // Define a Scripter object and set the required scripting options.   
      Scripter scrp = new Scripter(srv);  
      scrp.Options.ScriptDrops = false;  
      scrp.Options.WithDependencies = true;  
      scrp.Options.Indexes = true;   // To include indexes  
      scrp.Options.DriAllConstraints = true;   // to include referential constraints in the script  
  
      // Iterate through the tables in database and script each one. Display the script.     
      foreach (Table tb in db.Tables) {   
         // check if the table is not a system table  
         if (tb.IsSystemObject == false) {  
            Console.WriteLine("-- Scripting for table " + tb.Name);  
  
            // Generating script for table tb  
            System.Collections.Specialized.StringCollection sc = scrp.Script(new Urn[]{tb.Urn});  
            foreach (string st in sc) {  
               Console.WriteLine(st);  
            }  
            Console.WriteLine("--");  
         }  
      }   
   }  
}  
```  
  
## <a name="scripting-out-the-dependencies-for-a-database-in-powershell"></a><span data-ttu-id="df1d0-129">Generazione di script delle dipendenze per un database in PowerShell</span><span class="sxs-lookup"><span data-stu-id="df1d0-129">Scripting Out the Dependencies for a Database in PowerShell</span></span>  
 <span data-ttu-id="df1d0-130">In questo esempio di codice viene illustrato come individuare le dipendenze e scorrere l'elenco per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="df1d0-130">This code example shows how to discover the dependencies and iterate through the list to display the results.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
# Create a Scripter object and set the required scripting options.  
$scrp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Scripter -ArgumentList (Get-Item .)  
$scrp.Options.ScriptDrops = $false  
$scrp.Options.WithDependencies = $true  
$scrp.Options.IncludeIfNotExists = $true  
  
# Set the path context to the tables in AdventureWorks2012.  
CD Databases\AdventureWorks2012\Tables  
  
foreach ($Item in Get-ChildItem)  
 {    
 $scrp.Script($Item)  
 }  
```  
