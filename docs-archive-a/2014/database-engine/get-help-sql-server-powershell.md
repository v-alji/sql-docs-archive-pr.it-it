---
title: Visualizzare la Guida di SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Help [PowerShell]
- Help [SQL Server], PowerShell
- PowerShell [SQL Server], help
ms.assetid: 968c316d-db83-4c24-8ea6-9f18736842f7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f1d97a3b694eebb924f9e1ff228d4d38da4f45ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716611"
---
# <a name="get-help-sql-server-powershell"></a><span data-ttu-id="20c82-102">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="20c82-102">Get Help SQL Server PowerShell</span></span>
  <span data-ttu-id="20c82-103">Vi sono diverse fonti di informazione per l'utilizzo dei cmdlet e del provider di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20c82-103">There are several sources of information about using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell and cmdlets.</span></span> <span data-ttu-id="20c82-104">Tra queste è inclusa la Guida disponibile nell'ambiente di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20c82-104">This includes the help that is available in the Windows PowerShell environment.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="20c82-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="20c82-105">Before You Begin</span></span>  
 <span data-ttu-id="20c82-106">Per informazioni su Windows PowerShell, vedere la [Guida introduttiva a Windows PowerShell](https://technet.microsoft.com/library/hh857337.aspx).</span><span class="sxs-lookup"><span data-stu-id="20c82-106">To learn about Windows PowerShell, see [Windows PowerShell Getting Started Guide](https://technet.microsoft.com/library/hh857337.aspx).</span></span>  
  
 <span data-ttu-id="20c82-107">Per una panoramica dei cmdlet e del provider di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vedere [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="20c82-107">For an overview of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets and provider, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="help-in-the-windows-powershell-environment"></a><span data-ttu-id="20c82-108">Guida all'ambiente di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20c82-108">Help in the Windows PowerShell Environment</span></span>  
 <span data-ttu-id="20c82-109">Usare il cmdlet **Get-Help** per ottenere informazioni sull'ambiente di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20c82-109">Use the **Get-Help** cmdlet to get help in the Windows PowerShell environment.</span></span> <span data-ttu-id="20c82-110">**Get-Help** fornisce informazioni di base sul linguaggio di Windows PowerShell e sui vari cmdlet e provider disponibili in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20c82-110">**Get-Help** provides basic help for the Windows PowerShell language and the various cmdlets and providers available in Windows PowerShell.</span></span>  
  
 <span data-ttu-id="20c82-111">Per altre informazioni su come usare **Get-Help**, vedere [Visualizzazione della Guida: Get-Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span><span class="sxs-lookup"><span data-stu-id="20c82-111">For more information on the ways you can use **Get-Help**, see [Get-Help: Getting Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span></span>  
  
### <a name="sql-server-powershell-provider-help"></a><span data-ttu-id="20c82-112">Guida del provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="20c82-112">SQL Server PowerShell Provider Help</span></span>  
 <span data-ttu-id="20c82-113">Il provider PowerShell di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] implementa diverse cartelle su un'unità virtuale SQLSERVER, come ad esempio le cartelle SQLSERVER:\SQL e SQLSERVER:\DAC.</span><span class="sxs-lookup"><span data-stu-id="20c82-113">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider implements several folders on a SQLSERVER virtual drive, such as the SQLSERVER:\SQL and SQLSERVER:\DAC folders.</span></span> <span data-ttu-id="20c82-114">Ogni cartella è associata a uno dei modelli a oggetti per la gestione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20c82-114">Each folder is associated with one of the SQL Server manageability object models.</span></span> <span data-ttu-id="20c82-115">È possibile elencare i metodi e le proprietà associati a ogni nodo in un percorso di SQL Server, ma non è possibile ottenerne la guida nell'ambiente PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20c82-115">While you can list the methods and properties associated with each node in a SQL Server path, you cannot get help for them in the PowerShell environment.</span></span> <span data-ttu-id="20c82-116">Per una tabella delle cartelle con i collegamenti al riferimento di programmazione associato, vedere [Provider PowerShell per SQL Server](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="20c82-116">For a table of the folders with links to the associated programming reference, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
### <a name="invoke-sqlcmd-help"></a><span data-ttu-id="20c82-117">Guida di Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="20c82-117">Invoke-Sqlcmd Help</span></span>  
 <span data-ttu-id="20c82-118">Il cmdlet **Invoke-Sqlcmd** accetta come input qualsiasi query o file script che può essere eseguito dall'utilità **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="20c82-118">The **Invoke-Sqlcmd** cmdlet takes as input any query or script file that can be run by the **sqlcmd** utility.</span></span> <span data-ttu-id="20c82-119">È possibile usare **Get-Help** per ottenere informazioni su **Invoke-Sqlcmd** e i relativi parametri, ma **Get-Help** non fornisce informazioni sulle query **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="20c82-119">You can use **Get-Help** to get information about **Invoke-Sqlcmd** and its parameters, but there is no **Get-Help** coverage for the **sqlcmd** queries.</span></span>  
  
 <span data-ttu-id="20c82-120">L'input *-Query* o *-QueryFromFile* può contenere:</span><span class="sxs-lookup"><span data-stu-id="20c82-120">The *-Query* or *-QueryFromFile* input can contain:</span></span>  
  
-   <span data-ttu-id="20c82-121">Variabili e comandi di**sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="20c82-121">**sqlcmd** variables and commands.</span></span> <span data-ttu-id="20c82-122">Per informazioni su variabili e comandi, vedere la sezione Osservazioni di [Utilità sqlcmd](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="20c82-122">For information about these variables and commands, see the Remarks section of [sqlcmd Utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="20c82-123">Istruzioni[!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20c82-123">[!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="20c82-124">Per altre informazioni sul linguaggio [!INCLUDE[tsql](../includes/tsql-md.md)], vedere [Guida di riferimento a Transact-SQL &#40;Motore di database&#41;](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="20c82-124">For more information about the [!INCLUDE[tsql](../includes/tsql-md.md)] language, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference).</span></span>  
  
-   <span data-ttu-id="20c82-125">Istruzioni XQuery.</span><span class="sxs-lookup"><span data-stu-id="20c82-125">XQuery statements.</span></span> <span data-ttu-id="20c82-126">Per altre informazioni sul linguaggio XQuery supportato da [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vedere [Riferimento al linguaggio XQuery &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span><span class="sxs-lookup"><span data-stu-id="20c82-126">For more information about the XQuery language supported by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span></span>  
  
## <a name="get-help-for-a-sql-server-cmdlet"></a><span data-ttu-id="20c82-127">Ottenere la Guida per un cmdlet di SQL Server</span><span class="sxs-lookup"><span data-stu-id="20c82-127">Get Help for a SQL Server cmdlet</span></span>  
 <span data-ttu-id="20c82-128">**Per ottenere la guida per un cmdlet**</span><span class="sxs-lookup"><span data-stu-id="20c82-128">**To get help for a cmdlet**</span></span>  
  
-   <span data-ttu-id="20c82-129">Eseguire Get-Help specificando il nome del cmdlet e il livello della Guida da restituire.</span><span class="sxs-lookup"><span data-stu-id="20c82-129">Run Get-Help specifying the name of the cmdlet and the level of help to be returned.</span></span>  
  
### <a name="example-cmdlet-get-help"></a><span data-ttu-id="20c82-130">Esempio: cmdlet Get-Help</span><span class="sxs-lookup"><span data-stu-id="20c82-130">Example: cmdlet Get-Help</span></span>  
 <span data-ttu-id="20c82-131">Negli esempi seguenti vengono restituiti vari livelli della Guida per **Invoke-Sqlcmd**:</span><span class="sxs-lookup"><span data-stu-id="20c82-131">The following examples return various levels of help for **Invoke-Sqlcmd**:</span></span>  
  
```powershell
## Get the basic help.  
Get-Help Invoke-Sqlcmd  
  
## Get the full help.  
Get-Help Invoke-Sqlcmd -Full  
  
## Get the parameter descriptions.  
Get-Help Invoke-Sqlcmd -Parameter *  
  
## Get the code examples.  
Get-Help Invoke-Sqlcmd -Examples  
  
## Get the syntax diagram.  
Get-Help Invoke-Sqlcmd -Syntax  
```  
  
## <a name="get-a-list-of-providers"></a><span data-ttu-id="20c82-132">Ottenere un elenco di provider</span><span class="sxs-lookup"><span data-stu-id="20c82-132">Get a List of Providers</span></span>  

### <a name="to-get-a-list-of-active-providers"></a><span data-ttu-id="20c82-133">Per ottenere un elenco di provider attivi</span><span class="sxs-lookup"><span data-stu-id="20c82-133">To get a list of active providers</span></span>
  
1.  <span data-ttu-id="20c82-134">Eseguire Get-Help specificando la categoria del provider.</span><span class="sxs-lookup"><span data-stu-id="20c82-134">Run Get-Help specifying the provider category.</span></span>  
  
 <span data-ttu-id="20c82-135">Per altre informazioni su come ottenere informazioni sul provider in Windows PowerShell, vedere [Unità e provider](https://go.microsoft.com/fwlink/?LinkId=102137).</span><span class="sxs-lookup"><span data-stu-id="20c82-135">For more information about getting provider help in Windows PowerShell, see [Drives and Providers](https://go.microsoft.com/fwlink/?LinkId=102137).</span></span>  
  
### <a name="example-get-a-list-of-providers"></a><span data-ttu-id="20c82-136">Esempio: ottenere un elenco di provider</span><span class="sxs-lookup"><span data-stu-id="20c82-136">Example: Get a List of Providers</span></span>  
 <span data-ttu-id="20c82-137">Questo codice restituisce un elenco dei provider attualmente abilitati nella sessione di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="20c82-137">This code returns a list of the providers currently enabled in your Windows PowerShell session:</span></span>  
  
```powershell
Get-Help -Category provider  
```  
  
## <a name="get-help-about-the-sql-server-provider"></a><span data-ttu-id="20c82-138">Ottenere la Guida sul provider SQL Server</span><span class="sxs-lookup"><span data-stu-id="20c82-138">Get Help About the SQL Server Provider</span></span>  
 <span data-ttu-id="20c82-139">**Per ottenere la Guida sul provider**</span><span class="sxs-lookup"><span data-stu-id="20c82-139">**To get help about the provider**</span></span>  
  
1.  <span data-ttu-id="20c82-140">Eseguire Get-Help specificando il nome SQLServer</span><span class="sxs-lookup"><span data-stu-id="20c82-140">Run Get-Help specifying the name SQLServer</span></span>  
  
### <a name="example-get-sql-server-provider-help"></a><span data-ttu-id="20c82-141">Esempio: ottenere la Guida del provider SQL Server</span><span class="sxs-lookup"><span data-stu-id="20c82-141">Example: Get SQL Server Provider Help</span></span>  
 <span data-ttu-id="20c82-142">In questo esempio vengono restituite informazioni di base sul provider di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="20c82-142">This example returns basic information about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider:</span></span>  
  
```powershell
Get-Help SQLServer  
```  
  
## <a name="list-methods-and-properties"></a><span data-ttu-id="20c82-143">Elencare metodi e proprietà</span><span class="sxs-lookup"><span data-stu-id="20c82-143">List Methods and Properties</span></span>  
 <span data-ttu-id="20c82-144">**Per elencare i metodi e le proprietà per un nodo in un percorso del provider SQL Server**</span><span class="sxs-lookup"><span data-stu-id="20c82-144">**To list the methods and properties for a node in a SQL Server provider path**</span></span>  
  
1.  <span data-ttu-id="20c82-145">Usare il comando CD in un nodo nel percorso di SQL Server o creare un set di variabili nel percorso.</span><span class="sxs-lookup"><span data-stu-id="20c82-145">Either CD to a node in the SQL Server path, or create a variable set to that location.</span></span>  
  
2.  <span data-ttu-id="20c82-146">Eseguire il cmdlet **Get-Member** con il parametro-type impostato su Methods o Properties</span><span class="sxs-lookup"><span data-stu-id="20c82-146">Run the **Get-Member** cmdlet with the -Type parameter set to either Methods or Properties</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="20c82-147">Esempi: elencare metodi e proprietà</span><span class="sxs-lookup"><span data-stu-id="20c82-147">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="20c82-148">In questo esempio vengono elencati i metodi supportati per il nodo Database:</span><span class="sxs-lookup"><span data-stu-id="20c82-148">This example lists the methods supported for the Databases node:</span></span>  
  
```powershell
Set-Location SQL:\MyComputer\DEFAULT\Databases  
Get-Item . | Get-Member -Type Methods  
```  
  
 <span data-ttu-id="20c82-149">In questo esempio vengono elencate le proprietà di una variabile impostata su un oggetto della tabella SMO:</span><span class="sxs-lookup"><span data-stu-id="20c82-149">This example lists the properties for a variable that has been set to an SMO Table object:</span></span>  
  
```powershell
$MyVar = New-Object Microsoft.SqlServer.Management.SMO.Table  
$MyVar | Get-Member -Type Properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="20c82-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20c82-150">See Also</span></span>  
 <span data-ttu-id="20c82-151">[Provider di SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="20c82-151">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="20c82-152">Utilizzo di cmdlet del motore di database</span><span class="sxs-lookup"><span data-stu-id="20c82-152">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
