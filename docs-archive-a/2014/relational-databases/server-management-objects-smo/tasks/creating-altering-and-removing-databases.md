---
title: Creazione, modifica e rimozione di database | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- databases [SMO]
- databases [SMO], creating
- databases [SMO], modifying
- databases [SMO], deleting
ms.assetid: fcfb3ec2-7556-4f72-971a-501295892cb0
author: stevestein
ms.author: sstein
ms.openlocfilehash: e8bd34e939fcbc1ecfc5238f5fc4524d187d3f30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723663"
---
# <a name="creating-altering-and-removing-databases"></a><span data-ttu-id="4bba1-102">Creazione, modifica e rimozione di database</span><span class="sxs-lookup"><span data-stu-id="4bba1-102">Creating, Altering, and Removing Databases</span></span>
  <span data-ttu-id="4bba1-103">In SMO un database è rappresentato dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="4bba1-103">In SMO, a database is represented by the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
 <span data-ttu-id="4bba1-104">Non è necessario creare un oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> per modificarlo o rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="4bba1-104">It is not necessary to create a <xref:Microsoft.SqlServer.Management.Smo.Database> object to modify or remove it.</span></span> <span data-ttu-id="4bba1-105">È possibile fare riferimento al database tramite una raccolta.</span><span class="sxs-lookup"><span data-stu-id="4bba1-105">The database can be referenced by using a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bba1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bba1-106">Example</span></span>  
 <span data-ttu-id="4bba1-107">Per usare qualsiasi esempio di codice fornito, è necessario scegliere l'ambiente di programmazione, il modello di programmazione e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4bba1-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="4bba1-108">Per ulteriori informazioni, vedere [creare un Visual Basic progetto SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [creare un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="4bba1-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-database-in-visual-basic"></a><span data-ttu-id="4bba1-109">Creazione, modifica e rimozione di un database in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4bba1-109">Creating, Altering, and Removing a Database in Visual Basic</span></span>  
 <span data-ttu-id="4bba1-110">In questo esempio di codice viene creato un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="4bba1-110">This code example creates a new database.</span></span> <span data-ttu-id="4bba1-111">I file e i filegroup del database vengono creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4bba1-111">Files and file groups are automatically created for the database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDatabase1](SMO How to#SMO_VBDatabase1)]  -->  
  
## <a name="creating-altering-and-removing-a-database-in-visual-c"></a><span data-ttu-id="4bba1-112">Creazione, modifica e rimozione di un database in Visual C#</span><span class="sxs-lookup"><span data-stu-id="4bba1-112">Creating, Altering, and Removing a Database in Visual C#</span></span>  
 <span data-ttu-id="4bba1-113">In questo esempio di codice viene creato un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="4bba1-113">This code example creates a new database.</span></span> <span data-ttu-id="4bba1-114">I file e i filegroup del database vengono creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4bba1-114">Files and file groups are automatically created for the database.</span></span>  
  
```csharp
{  
                //Connect to the local, default instance of SQL Server.   
                Server srv;  
                srv = new Server();  
                //Define a Database object variable by supplying the server and the database name arguments in the constructor.   
                Database db;  
                db = new Database(srv, "Test_SMO_Database");  
                //Create the database on the instance of SQL Server.   
                db.Create();  
                //Reference the database and display the date when it was created.   
                db = srv.Databases["Test_SMO_Database"];  
                Console.WriteLine(db.CreateDate);  
                //Remove the database.   
                db.Drop();  
            }  
```  
  
## <a name="creating-altering-and-removing-a-database-in-powershell"></a><span data-ttu-id="4bba1-115">Creazione, modifica e rimozione di un database in PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bba1-115">Creating, Altering, and Removing a Database in PowerShell</span></span>  
 <span data-ttu-id="4bba1-116">In questo esempio di codice viene creato un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="4bba1-116">This code example creates a new database.</span></span> <span data-ttu-id="4bba1-117">I file e i filegroup del database vengono creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4bba1-117">Files and file groups are automatically created for the database.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
cd \sql\localhost\  
$srv = Get-Item default  
  
#Create a new database  
$db = New-Object -TypeName Microsoft.SqlServer.Management.Smo.Database -argumentlist $srv, "Test_SMO_Database"  
$db.Create()  
  
#Reference the database and display the date when it was created.
$db = $srv.Databases["Test_SMO_Database"]  
$db.CreateDate  
  
#Drop the database  
$db.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bba1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bba1-118">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Database>  
