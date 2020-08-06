---
title: Usare i percorsi di SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f31d8e2c-8d59-4fee-ac2a-324668e54262
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d2647251eb1c8843d4ab7a95d2c439e47f5bb6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715452"
---
# <a name="work-with-sql-server-powershell-paths"></a><span data-ttu-id="edfd9-102">Utilizzo di percorsi di SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="edfd9-102">Work With SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="edfd9-103">Dopo essere passati a un nodo in un percorso di provider [!INCLUDE[ssDE](../includes/ssde-md.md)] , è possibile eseguire operazioni o recuperare informazioni utilizzando i metodi e le proprietà dell'oggetto di gestione di [!INCLUDE[ssDE](../includes/ssde-md.md)] associato al nodo in questione.</span><span class="sxs-lookup"><span data-stu-id="edfd9-103">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform work or retrieve information by using the methods and properties from the [!INCLUDE[ssDE](../includes/ssde-md.md)] management object associated with the node.</span></span>  
  
1.  [<span data-ttu-id="edfd9-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="edfd9-104">Before You Begin</span></span>](#BeforeYouBegin)  
  
2.  <span data-ttu-id="edfd9-105">**Per utilizzare un nodo di percorso:**  [Elenco di metodi e proprietà](#ListPropMeth), [Utilizzo di metodi e proprietà](#UsePropMeth)</span><span class="sxs-lookup"><span data-stu-id="edfd9-105">**To work on a path node:**  [Listing Methods and Properties](#ListPropMeth), [Using Methods and Properties](#UsePropMeth)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="edfd9-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="edfd9-106">Before You Begin</span></span>  
 <span data-ttu-id="edfd9-107">Dopo essere passati a un nodo in un percorso di provider [!INCLUDE[ssDE](../includes/ssde-md.md)] è possibile eseguire due tipi di azioni:</span><span class="sxs-lookup"><span data-stu-id="edfd9-107">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform two types of actions:</span></span>  
  
-   <span data-ttu-id="edfd9-108">È possibile eseguire i cmdlet di Windows PowerShell che operano sui nodi, ad esempio **Rename-Item**.</span><span class="sxs-lookup"><span data-stu-id="edfd9-108">You can run Windows PowerShell cmdlets that operate on nodes, such as **Rename-Item**.</span></span>  
  
-   <span data-ttu-id="edfd9-109">È possibile chiamare i metodi dal modello a oggetti di gestione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] associato, ad esempio SMO.</span><span class="sxs-lookup"><span data-stu-id="edfd9-109">You can call the methods from the associated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] management object model, such as SMO.</span></span> <span data-ttu-id="edfd9-110">Ad esempio, se si passa al nodo Databases in un percorso, è possibile usare i metodi e le proprietà della classe <xref:Microsoft.SqlServer.Management.Smo.Database> .</span><span class="sxs-lookup"><span data-stu-id="edfd9-110">For example, if you navigate to the Databases node in a path, you can use the methods and properties of the <xref:Microsoft.SqlServer.Management.Smo.Database> class.</span></span>  
  
 <span data-ttu-id="edfd9-111">Il provider [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] viene utilizzato per gestire gli oggetti in un'istanza del [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edfd9-111">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider is used to manage the objects in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="edfd9-112">Non viene utilizzato per i dati nei database.</span><span class="sxs-lookup"><span data-stu-id="edfd9-112">It is not used to work with the data in databases.</span></span> <span data-ttu-id="edfd9-113">Se si è passati a una tabella o una vista, non è possibile utilizzare il provider per selezionare, inserire, aggiornare o eliminare i dati.</span><span class="sxs-lookup"><span data-stu-id="edfd9-113">If you have navigated to a table or view, you cannot use the provider to select, insert, update, or delete data.</span></span> <span data-ttu-id="edfd9-114">Usare il cmdlet **Invoke-Sqlcmd** per eseguire una query o per modificare dati in tabelle e viste nell'ambiente di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edfd9-114">Use the **Invoke-Sqlcmd** cmdlet to query or change data in tables and views from the Windows PowerShell environment.</span></span> <span data-ttu-id="edfd9-115">Per altre informazioni, vedere [cmdlet Invoke-Sqlcmd](../database-engine/invoke-sqlcmd-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="edfd9-115">For more information, see [Invoke-Sqlcmd cmdlet](../database-engine/invoke-sqlcmd-cmdlet.md).</span></span>  
  
##  <a name="listing-methods-and-properties"></a><a name="ListPropMeth"></a> <span data-ttu-id="edfd9-116">Elenco di metodi e proprietà</span><span class="sxs-lookup"><span data-stu-id="edfd9-116">Listing Methods and Properties</span></span>
  
 <span data-ttu-id="edfd9-117">Per visualizzare i metodi e le proprietà disponibili per specifici oggetti o classi di oggetti, usare il cmdlet **Get-Member** .</span><span class="sxs-lookup"><span data-stu-id="edfd9-117">To view the methods and properties available for specific objects or object classes, use the **Get-Member** cmdlet.</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="edfd9-118">Esempi: elencare metodi e proprietà</span><span class="sxs-lookup"><span data-stu-id="edfd9-118">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="edfd9-119">In questo esempio viene impostata una variabile di Windows PowerShell sulla classe SMO <xref:Microsoft.SqlServer.Management.Smo.Database> e vengono elencati i metodi e le proprietà:</span><span class="sxs-lookup"><span data-stu-id="edfd9-119">This example sets a Windows PowerShell variable to the SMO <xref:Microsoft.SqlServer.Management.Smo.Database> class and lists the methods and properties:</span></span>  
  
```powershell
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar | Get-Member -Type Methods  
$MyDBVar | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="edfd9-120">Si può anche usare **Get-Member** per visualizzare un elenco di proprietà e metodi associati al nodo finale di un percorso di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edfd9-120">You can also use **Get-Member** to list the methods and properties that are associated with the end node of a Windows PowerShell path.</span></span>  
  
 <span data-ttu-id="edfd9-121">In questo esempio si passa al nodo Databases in un percorso SQLSERVER: e vengono elencate le proprietà della raccolta:</span><span class="sxs-lookup"><span data-stu-id="edfd9-121">This example navigates to the Databases node in a SQLSERVER: path and lists the collection properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-Item . | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="edfd9-122">In questo esempio si passa al nodo AdventureWorks2012 in un percorso SQLSERVER: e vengono elencate le proprietà dell'oggetto:</span><span class="sxs-lookup"><span data-stu-id="edfd9-122">This example navigates to the AdventureWorks2012 node in a SQLSERVER: path and lists the object properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
Get-Item . | Get-Member -Type Properties  
```  
  
##  <a name="using-smo-methods-and-properties"></a><a name="UsePropMeth"></a><span data-ttu-id="edfd9-123">Utilizzo di metodi e proprietà SMO</span><span class="sxs-lookup"><span data-stu-id="edfd9-123">Using SMO Methods and Properties</span></span>  
  
 <span data-ttu-id="edfd9-124">Per eseguire operazioni su oggetti di un percorso di provider [!INCLUDE[ssDE](../includes/ssde-md.md)] è possibile utilizzare metodi e proprietà SMO.</span><span class="sxs-lookup"><span data-stu-id="edfd9-124">To perform work on objects from a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can use SMO methods and properties.</span></span>  
  
### <a name="examples-using-methods-and-properties"></a><span data-ttu-id="edfd9-125">Esempi: utilizzo di metodi e proprietà</span><span class="sxs-lookup"><span data-stu-id="edfd9-125">Examples: Using Methods and Properties</span></span>  
 <span data-ttu-id="edfd9-126">In questo esempio viene usata la proprietà dello **schema** SMO per ottenere un elenco delle tabelle dallo schema Sales di AdventureWorks2012:</span><span class="sxs-lookup"><span data-stu-id="edfd9-126">This example uses the SMO **Schema** property to get a list of the tables from the Sales schema in AdventureWorks2012:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Tables  
Get-ChildItem | Where {$_.Schema -eq "Sales"}  
```  
  
 <span data-ttu-id="edfd9-127">In questo esempio viene utilizzato il metodo di **script** SMO per generare uno script che contiene le `CREATE VIEW` istruzioni necessarie per ricreare le viste in AdventureWorks2012:</span><span class="sxs-lookup"><span data-stu-id="edfd9-127">This example uses the SMO **Script** method to generate a script that contains the `CREATE VIEW` statements you must have to re-create the views in AdventureWorks2012:</span></span>  
  
```powershell
Remove-Item C:\PowerShell\CreateViews.sql  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Views  
foreach ($Item in Get-ChildItem) { $Item.Script() | Out-File -Filepath C:\PowerShell\CreateViews.sql -append }  
```  
  
 <span data-ttu-id="edfd9-128">In questo esempio viene utilizzato il metodo **Create** SMO per creare un database e quindi viene utilizzata la proprietà **State** per indicare se il database esiste:</span><span class="sxs-lookup"><span data-stu-id="edfd9-128">This example uses the SMO **Create** method to create a database, and then uses the **State** property to show whether the database exists:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar.Parent = (Get-Item ..)  
$MyDBVar.Name = "NewDB"  
$MyDBVar.Create()  
$MyDBVar.State  
```  
  
## <a name="see-also"></a><span data-ttu-id="edfd9-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edfd9-129">See Also</span></span>  
 <span data-ttu-id="edfd9-130">[Provider di SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="edfd9-130">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="edfd9-131">[Esplora percorsi SQL Server PowerShell](navigate-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="edfd9-131">[Navigate SQL Server PowerShell Paths](navigate-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="edfd9-132">[Converti URN in percorsi di provider SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="edfd9-132">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="edfd9-133">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="edfd9-133">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
