---
title: Implementazione della ricerca full-text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- full-text search [SMO]
ms.assetid: 9ce9ad9c-f671-4760-90b5-e0c8ca051473
author: stevestein
ms.author: sstein
ms.openlocfilehash: f8b797e2a38c9136c34b7058b539fca522e03229
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711839"
---
# <a name="implementing-full-text-search"></a><span data-ttu-id="73481-102">Implementazione della ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="73481-102">Implementing Full-Text Search</span></span>
  <span data-ttu-id="73481-103">La ricerca full-text è disponibile per istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ed è rappresentata in SMO dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server.FullTextService%2A>.</span><span class="sxs-lookup"><span data-stu-id="73481-103">Full-text search is available per instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and is represented in SMO by the <xref:Microsoft.SqlServer.Management.Smo.Server.FullTextService%2A> object.</span></span> <span data-ttu-id="73481-104">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.FullTextService> si trova sotto l'oggetto `Server`.</span><span class="sxs-lookup"><span data-stu-id="73481-104">The <xref:Microsoft.SqlServer.Management.Smo.FullTextService> object resides under the `Server` object.</span></span> <span data-ttu-id="73481-105">Viene utilizzato per gestire le opzioni di configurazione per il servizio di ricerca full-text di [!INCLUDE[msCoName](../../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73481-105">It is used to manage the configuration options for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Full Text Search service.</span></span> <span data-ttu-id="73481-106">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalogCollection> appartiene all'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> e si tratta di una raccolta di oggetti <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> che rappresentano cataloghi full-text definiti per il database.</span><span class="sxs-lookup"><span data-stu-id="73481-106">The <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalogCollection> object belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object and it is a collection of <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> objects that represent full-text catalogs defined for the database.</span></span> <span data-ttu-id="73481-107">È possibile disporre di un solo indice full-text definito per ogni tabella, a differenza degli indici normali.</span><span class="sxs-lookup"><span data-stu-id="73481-107">You can only have one full-text index defined for each table, unlike normal indexes.</span></span> <span data-ttu-id="73481-108">Questo indice è rappresentato da un oggetto <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> nell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="73481-108">This is represented by a <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> object in the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
 <span data-ttu-id="73481-109">Per creare un servizio di ricerca full-text, è necessario disporre di un catalogo full-text definito nel database e di un indice di ricerca full-text definito in una delle tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="73481-109">To create a full-text search service, you must have a full-text catalog defined on the database and a full-text search index defined on one of the tables in the database.</span></span>  
  
 <span data-ttu-id="73481-110">Creare innanzitutto un catalogo full-text nel database chiamando il costruttore <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> e specificando il nome del catalogo.</span><span class="sxs-lookup"><span data-stu-id="73481-110">First, create a full-text catalog on the database by calling the <xref:Microsoft.SqlServer.Management.Smo.FullTextCatalog> constructor and specifying the catalog name.</span></span> <span data-ttu-id="73481-111">Successivamente, creare l'indice full-text chiamando il costruttore e specificando la tabella nella quale deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="73481-111">Then, create the full-text index by calling the constructor and specifying the table on which it is to be created.</span></span> <span data-ttu-id="73481-112">È quindi possibile aggiungere colonne per l'indice full-text tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> e fornendo il nome della colonna all'interno della tabella.</span><span class="sxs-lookup"><span data-stu-id="73481-112">You can then add index columns for the full-text index, by using the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndexColumn> object and providing the name of the column within the table.</span></span> <span data-ttu-id="73481-113">Successivamente, impostare la proprietà <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.CatalogName%2A> sul catalogo creato.</span><span class="sxs-lookup"><span data-stu-id="73481-113">Then, set the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.CatalogName%2A> property to the catalog you have created.</span></span> <span data-ttu-id="73481-114">Infine, chiamare il metodo <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.Create%2A> e creare l'indice full-text nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73481-114">Finally, call the <xref:Microsoft.SqlServer.Management.Smo.FullTextIndex.Create%2A> method and create the full-text index on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="73481-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="73481-115">Example</span></span>  
 <span data-ttu-id="73481-116">Per usare qualsiasi esempio di codice fornito, è necessario scegliere l'ambiente di programmazione, il modello di programmazione e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="73481-116">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="73481-117">Per ulteriori informazioni, vedere [creare un Visual Basic progetto SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [creare un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="73481-117">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-full-text-search-service-in-visual-basic"></a><span data-ttu-id="73481-118">Creazione di un servizio di ricerca full-text in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73481-118">Creating a Full-Text Search Service in Visual Basic</span></span>  
 <span data-ttu-id="73481-119">Nel codice di esempio seguente viene creato un catalogo di ricerca full-text per la tabella `ProductCategory` nel database di esempio [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73481-119">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="73481-120">Successivamente, viene creato un indice di ricerca full-text nella colonna Name della tabella `ProductCategory`.</span><span class="sxs-lookup"><span data-stu-id="73481-120">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="73481-121">Per l'indice di ricerca full-text è necessario che nella colonna sia già definito un indice univoco.</span><span class="sxs-lookup"><span data-stu-id="73481-121">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```vb
' compile with:   
' /r:Microsoft.SqlServer.SqlEnum.dll   
' /r:Microsoft.SqlServer.Smo.dll   
' /r:Microsoft.SqlServer.ConnectionInfo.dll   
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Sdk.Sfc  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      ' Connect to the local, default instance of SQL Server.  
      Dim srv As Server = Nothing  
      srv = New Server()  
  
      ' Reference the AdventureWorks database.  
      Dim db As Database = Nothing  
      db = srv.Databases("AdventureWorks")  
  
      ' Reference the ProductCategory table.  
      Dim tb As Table = Nothing  
      tb = db.Tables("ProductCategory", "Production")  
  
      ' Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
      Dim ftc As FullTextCatalog = Nothing  
      ftc = New FullTextCatalog(db, "Test_Catalog")  
      ftc.IsDefault = True  
  
      ' Create the Full-Text Search catalog on the instance of SQL Server.  
      ftc.Create()  
  
      ' Define a FullTextIndex object varaible by supplying the parent table argument in the constructor.  
      Dim fti As FullTextIndex = Nothing  
      fti = New FullTextIndex(tb)  
  
      ' Define a FullTextIndexColumn object variable by supplying the parent index and column name arguments in the constructor.  
      Dim ftic As FullTextIndexColumn = Nothing  
      ftic = New FullTextIndexColumn(fti, "Name")  
  
      ' Add the indexed column to the index.  
      fti.IndexedColumns.Add(ftic)  
      fti.ChangeTracking = ChangeTracking.Automatic  
  
      ' Specify the unique index on the table that is required by the Full Text Search index.  
      fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
      ' Specify the catalog associated with the index.  
      fti.CatalogName = "Test_Catalog"  
  
      ' Create the Full Text Search index on the instance of SQL Server.  
      fti.Create()  
   End Sub  
End Class  
```  
  
## <a name="creating-a-full-text-search-service-in-visual-c"></a><span data-ttu-id="73481-122">Creazione di un servizio di ricerca full-text in Visual C#</span><span class="sxs-lookup"><span data-stu-id="73481-122">Creating a Full-Text Search Service in Visual C#</span></span>  
 <span data-ttu-id="73481-123">Nel codice di esempio seguente viene creato un catalogo di ricerca full-text per la tabella `ProductCategory` nel database di esempio [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73481-123">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="73481-124">Successivamente, viene creato un indice di ricerca full-text nella colonna Name della tabella `ProductCategory`.</span><span class="sxs-lookup"><span data-stu-id="73481-124">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="73481-125">Per l'indice di ricerca full-text è necessario che nella colonna sia già definito un indice univoco.</span><span class="sxs-lookup"><span data-stu-id="73481-125">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```csharp
// compile with:   
// /r:Microsoft.SqlServer.SqlEnum.dll   
// /r:Microsoft.SqlServer.Smo.dll   
// /r:Microsoft.SqlServer.ConnectionInfo.dll   
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Sdk.Sfc;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {  
      // Connect to the local, default instance of SQL Server.  
      Server srv = default(Server);  
      srv = new Server();  
  
      // Reference the AdventureWorks database.  
      Database db = default(Database);  
      db = srv.Databases ["AdventureWorks"];  
  
      // Reference the ProductCategory table.  
      Table tb = default(Table);  
      tb = db.Tables["ProductCategory", "Production"];  
  
      // Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
      FullTextCatalog ftc = default(FullTextCatalog);  
      ftc = new FullTextCatalog(db, "Test_Catalog");  
      ftc.IsDefault = true;  
  
      // Create the Full-Text Search catalog on the instance of SQL Server.  
      ftc.Create();  
  
      // Define a FullTextIndex object varaible by supplying the parent table argument in the constructor.  
      FullTextIndex fti = default(FullTextIndex);  
      fti = new FullTextIndex(tb);  
  
      // Define a FullTextIndexColumn object variable by supplying the parent index and column name arguments in the constructor.  
      FullTextIndexColumn ftic = default(FullTextIndexColumn);  
      ftic = new FullTextIndexColumn(fti, "Name");  
  
      // Add the indexed column to the index.  
      fti.IndexedColumns.Add(ftic);  
      fti.ChangeTracking = ChangeTracking.Automatic;  
  
      // Specify the unique index on the table that is required by the Full Text Search index.  
      fti.UniqueIndexName = "AK_ProductCategory_Name";  
  
      // Specify the catalog associated with the index.  
      fti.CatalogName = "Test_Catalog";  
  
      // Create the Full Text Search index on the instance of SQL Server.  
      fti.Create();  
   }  
}  
```  
  
## <a name="creating-a-full-text-search-service-in-powershell"></a><span data-ttu-id="73481-126">Creazione di un servizio di ricerca full-text in PowerShell</span><span class="sxs-lookup"><span data-stu-id="73481-126">Creating a Full-Text Search Service in PowerShell</span></span>  
 <span data-ttu-id="73481-127">Nel codice di esempio seguente viene creato un catalogo di ricerca full-text per la tabella `ProductCategory` nel database di esempio [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73481-127">This code example creates a full-text search catalog for the `ProductCategory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="73481-128">Successivamente, viene creato un indice di ricerca full-text nella colonna Name della tabella `ProductCategory`.</span><span class="sxs-lookup"><span data-stu-id="73481-128">It then creates a full-text search index on the Name column in the `ProductCategory` table.</span></span> <span data-ttu-id="73481-129">Per l'indice di ricerca full-text è necessario che nella colonna sia già definito un indice univoco.</span><span class="sxs-lookup"><span data-stu-id="73481-129">The full-text search index requires that there is a unique index already defined on the column.</span></span>  
  
```powershell
# Example of implementing a full text search on the default instance.  
# Set the path context to the local, default instance of SQL Server and database tables  
  
CD \sql\localhost\default\databases  
$db = Get-Item AdventureWorks2012  
  
CD AdventureWorks\tables  
  
#Get a reference to the table  
$tb = Get-Item Production.ProductCategory  
  
# Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
  
$ftc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextCatalog -ArgumentList $db, "Test_Catalog2"  
$ftc.IsDefault = $true  
  
# Create the Full Text Search catalog on the instance of SQL Server.  
$ftc.Create()  
  
# Define a FullTextIndex object variable by supplying the parent table argument in the constructor.  
$fti = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndex -ArgumentList $tb  
  
#  Define a FullTextIndexColumn object variable by supplying the parent index
#  and column name arguments in the constructor.  
  
$ftic = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndexColumn -ArgumentList $fti, "Name"  
  
# Add the indexed column to the index.  
$fti.IndexedColumns.Add($ftic)  
  
# Set change tracking  
$fti.ChangeTracking = [Microsoft.SqlServer.Management.SMO.ChangeTracking]::Automatic  
  
# Specify the unique index on the table that is required by the Full Text Search index.  
$fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
# Specify the catalog associated with the index.  
$fti.CatalogName = "Test_Catalog2"  
  
# Create the Full Text Search Index  
$fti.Create()  
```  
