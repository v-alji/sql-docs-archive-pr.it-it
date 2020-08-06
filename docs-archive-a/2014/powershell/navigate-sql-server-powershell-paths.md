---
title: Spostarsi all'interno dei percorsi di SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: d68aca48-d161-45ed-9f4f-14122ed30218
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a605479991c3e907cd9dcae254cc1bc04a49392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724779"
---
# <a name="navigate-sql-server-powershell-paths"></a><span data-ttu-id="1c974-102">Spostarsi all'interno dei percorsi di SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c974-102">Navigate SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="1c974-103">Il provider [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell espone il set di oggetti in un'istanza di SQL Server in una struttura analoga a un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="1c974-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell provider exposes the set of objects in an instance of SQL Server in a structure similar to a file path.</span></span> <span data-ttu-id="1c974-104">È possibile utilizzare cmdlet di Windows PowerShell per spostarsi all'interno del percorso del provider e creare unità personalizzate per rendere più breve il percorso da digitare.</span><span class="sxs-lookup"><span data-stu-id="1c974-104">You can use Windows PowerShell cmdlets to navigate the provider path, and create custom drives to shorten the path you have to type.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="1c974-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1c974-105">Before You Begin</span></span>  
 <span data-ttu-id="1c974-106">Windows PowerShell implementa cmdlet per spostarsi all'interno della struttura del percorso che rappresenta la gerarchia di oggetti supportati da un provider PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c974-106">Windows PowerShell implements cmdlets to navigate the path structure that represent the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="1c974-107">Quando si passa a un nodo nel percorso, è possibile utilizzare altri cmdlet per eseguire operazioni di base sull'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="1c974-107">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span> <span data-ttu-id="1c974-108">Poiché vengono utilizzati frequentemente, i cmdlet dispongono di alias brevi e canonici.</span><span class="sxs-lookup"><span data-stu-id="1c974-108">Because the cmdlets are used frequently, they have short, canonical aliases.</span></span> <span data-ttu-id="1c974-109">È inoltre presente un set di alias che esegue il mapping dei cmdlet a comandi simili del prompt dei comandi e un altro set per i comandi della shell di UNIX.</span><span class="sxs-lookup"><span data-stu-id="1c974-109">There is also one set of aliases that maps the cmdlets to similar command prompt commands, and another set for UNIX shell commands.</span></span>  
  
 <span data-ttu-id="1c974-110">Il provider [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] implementa un subset di cmdlet del provider, illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1c974-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider implements a subset of the provider cmdlets, shown in the following table.</span></span>  
  
|<span data-ttu-id="1c974-111">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1c974-111">cmdlet</span></span>|<span data-ttu-id="1c974-112">Alias canonico</span><span class="sxs-lookup"><span data-stu-id="1c974-112">Canonical alias</span></span>|<span data-ttu-id="1c974-113">Alias cmd</span><span class="sxs-lookup"><span data-stu-id="1c974-113">cmd alias</span></span>|<span data-ttu-id="1c974-114">Alias di shell di UNIX</span><span class="sxs-lookup"><span data-stu-id="1c974-114">UNIX shell alias</span></span>|<span data-ttu-id="1c974-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c974-115">Description</span></span>|  
|------------|---------------------|---------------|----------------------|-----------------|  
|<span data-ttu-id="1c974-116">**Get-Location**</span><span class="sxs-lookup"><span data-stu-id="1c974-116">**Get-Location**</span></span>|<span data-ttu-id="1c974-117">**gl**</span><span class="sxs-lookup"><span data-stu-id="1c974-117">**gl**</span></span>|<span data-ttu-id="1c974-118">**pwd**</span><span class="sxs-lookup"><span data-stu-id="1c974-118">**pwd**</span></span>|<span data-ttu-id="1c974-119">**pwd**</span><span class="sxs-lookup"><span data-stu-id="1c974-119">**pwd**</span></span>|<span data-ttu-id="1c974-120">Consente di ottenere il nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="1c974-120">Gets the current node.</span></span>|  
|`Set-Location`|<span data-ttu-id="1c974-121">**SL**</span><span class="sxs-lookup"><span data-stu-id="1c974-121">**sl**</span></span>|<span data-ttu-id="1c974-122">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="1c974-122">**cd, chdir**</span></span>|<span data-ttu-id="1c974-123">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="1c974-123">**cd, chdir**</span></span>|<span data-ttu-id="1c974-124">Consente di modificare il nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="1c974-124">Changes the current node.</span></span>|  
|<span data-ttu-id="1c974-125">**Get-ChildItem**</span><span class="sxs-lookup"><span data-stu-id="1c974-125">**Get-ChildItem**</span></span>|<span data-ttu-id="1c974-126">**gci**</span><span class="sxs-lookup"><span data-stu-id="1c974-126">**gci**</span></span>|<span data-ttu-id="1c974-127">**dir**</span><span class="sxs-lookup"><span data-stu-id="1c974-127">**dir**</span></span>|<span data-ttu-id="1c974-128">**LS**</span><span class="sxs-lookup"><span data-stu-id="1c974-128">**ls**</span></span>|<span data-ttu-id="1c974-129">Consente di visualizzare un elenco degli oggetti archiviati nel nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="1c974-129">Lists the objects stored at the current node.</span></span>|  
|<span data-ttu-id="1c974-130">**Get-Item**</span><span class="sxs-lookup"><span data-stu-id="1c974-130">**Get-Item**</span></span>|<span data-ttu-id="1c974-131">**gi**</span><span class="sxs-lookup"><span data-stu-id="1c974-131">**gi**</span></span>|||<span data-ttu-id="1c974-132">Restituisce le proprietà dell'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="1c974-132">Returns the properties of the current item.</span></span>|  
|<span data-ttu-id="1c974-133">**Rename-Item**</span><span class="sxs-lookup"><span data-stu-id="1c974-133">**Rename-Item**</span></span>|<span data-ttu-id="1c974-134">**rni**</span><span class="sxs-lookup"><span data-stu-id="1c974-134">**rni**</span></span>|<span data-ttu-id="1c974-135">**RN**</span><span class="sxs-lookup"><span data-stu-id="1c974-135">**rn**</span></span>|<span data-ttu-id="1c974-136">**ren**</span><span class="sxs-lookup"><span data-stu-id="1c974-136">**ren**</span></span>|<span data-ttu-id="1c974-137">Consente di rinominare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1c974-137">Renames an object.</span></span>|  
|<span data-ttu-id="1c974-138">**Remove-Item**</span><span class="sxs-lookup"><span data-stu-id="1c974-138">**Remove-Item**</span></span>|<span data-ttu-id="1c974-139">**ri**</span><span class="sxs-lookup"><span data-stu-id="1c974-139">**ri**</span></span>|<span data-ttu-id="1c974-140">**del, rd**</span><span class="sxs-lookup"><span data-stu-id="1c974-140">**del, rd**</span></span>|<span data-ttu-id="1c974-141">**rm, rmdir**</span><span class="sxs-lookup"><span data-stu-id="1c974-141">**rm, rmdir**</span></span>|<span data-ttu-id="1c974-142">Consente di rimuovere un oggetto.</span><span class="sxs-lookup"><span data-stu-id="1c974-142">Removes an object.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1c974-143">Alcuni identificatori (nomi di oggetto) di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] contengono caratteri non supportati da Windows PowerShell nei nomi dei percorsi.</span><span class="sxs-lookup"><span data-stu-id="1c974-143">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers (object names) contain characters that Windows PowerShell does not support in path names.</span></span> <span data-ttu-id="1c974-144">Per altre informazioni sull'uso dei nomi che contengono questi caratteri, vedere [Identificatori di SQL Server in PowerShell](sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1c974-144">For more information about how to use names that contain these characters, see [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span></span>  
  
### <a name="sql-server-information-returned-by-get-childitem"></a><span data-ttu-id="1c974-145">Informazioni su SQL Server restituite da Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1c974-145">SQL Server Information Returned by Get-ChildItem</span></span>  
 <span data-ttu-id="1c974-146">Le informazioni restituite da **Get-ChildItem** (o dai relativi alias **dir** e **ls** ) dipendono dalla posizione in un percorso SQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="1c974-146">The information returned by **Get-ChildItem** (or its **dir** and **ls** aliases) depends on your location in a SQLSERVER: path.</span></span>  
  
|<span data-ttu-id="1c974-147">Posizione nel percorso</span><span class="sxs-lookup"><span data-stu-id="1c974-147">Path location</span></span>|<span data-ttu-id="1c974-148">Risultati di Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1c974-148">Get-ChildItem results</span></span>|  
|-------------------|----------------------------|  
|<span data-ttu-id="1c974-149">SQLSERVER:\SQL</span><span class="sxs-lookup"><span data-stu-id="1c974-149">SQLSERVER:\SQL</span></span>|<span data-ttu-id="1c974-150">Restituisce il nome del computer locale.</span><span class="sxs-lookup"><span data-stu-id="1c974-150">Returns the name of the local computer.</span></span> <span data-ttu-id="1c974-151">Se è stato utilizzato SMO o WMI per connettersi a istanze del [!INCLUDE[ssDE](../includes/ssde-md.md)] in altri computer, vengono elencati anche tali computer.</span><span class="sxs-lookup"><span data-stu-id="1c974-151">If you have used the SMO or WMI to connect to instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on other computers, those computers are also listed.</span></span>|  
|<span data-ttu-id="1c974-152">SQLSERVER: \ SQL \\ *nomecomputer*</span><span class="sxs-lookup"><span data-stu-id="1c974-152">SQLSERVER:\SQL\\*ComputerName*</span></span>|<span data-ttu-id="1c974-153">Elenco delle istanze di [!INCLUDE[ssDE](../includes/ssde-md.md)] nel computer.</span><span class="sxs-lookup"><span data-stu-id="1c974-153">The list of instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on the computer.</span></span>|  
|<span data-ttu-id="1c974-154">SqlServer: \ SQL \\ *nomecomputer* \\ *NomeIstanza*</span><span class="sxs-lookup"><span data-stu-id="1c974-154">SQLSERVER:\SQL\\*ComputerName*\\*InstanceName*</span></span>|<span data-ttu-id="1c974-155">Elenco dei tipi di oggetto di primo livello nell'istanza, ad esempio Endpoint, Certificati e Database.</span><span class="sxs-lookup"><span data-stu-id="1c974-155">The list of top-level object types in the instance, such as Endpoints, Certificates, and Databases.</span></span>|  
|<span data-ttu-id="1c974-156">Nodo della classe di oggetto, ad esempio Database</span><span class="sxs-lookup"><span data-stu-id="1c974-156">Object class node, such as Databases</span></span>|<span data-ttu-id="1c974-157">Elenco di oggetti del tipo, ad esempio l'elenco di database: master, model, AdventureWorks2008R2.</span><span class="sxs-lookup"><span data-stu-id="1c974-157">The list of objects of that type, such as the list of databases: master, model, AdventureWorks20008R2.</span></span>|  
|<span data-ttu-id="1c974-158">Nodo del nome dell'oggetto, ad esempio AdventureWorks2012</span><span class="sxs-lookup"><span data-stu-id="1c974-158">Object name node, such as AdventureWorks2012</span></span>|<span data-ttu-id="1c974-159">Elenco dei tipi di oggetto contenuti all'interno dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1c974-159">The list of object types contained within the object.</span></span> <span data-ttu-id="1c974-160">Per un database, ad esempio, vengono elencati tipi di oggetto come tabelle e viste.</span><span class="sxs-lookup"><span data-stu-id="1c974-160">For example, a database would list object types such as tables and views.</span></span>|  
  
 <span data-ttu-id="1c974-161">Per impostazione predefinita, **Get-ChildItem** non elenca oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="1c974-161">By default, **Get-ChildItem** does not list any system objects.</span></span> <span data-ttu-id="1c974-162">Usare il parametro *Force* per visualizzare gli oggetti di sistema, ad esempio gli oggetti nello schema **sys** .</span><span class="sxs-lookup"><span data-stu-id="1c974-162">Use the *Force* parameter to see system objects, such as the objects in the **sys** schema.</span></span>  
  
### <a name="custom-drives"></a><span data-ttu-id="1c974-163">Unità personalizzate</span><span class="sxs-lookup"><span data-stu-id="1c974-163">Custom Drives</span></span>  
 <span data-ttu-id="1c974-164">Windows PowerShell consente agli utenti di definire unità virtuali, definite come unità di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c974-164">Windows PowerShell lets users define virtual drives, which are referred to as PowerShell drives.</span></span> <span data-ttu-id="1c974-165">Per tali unità viene eseguito il mapping ai nodi iniziali di un'istruzione di percorso.</span><span class="sxs-lookup"><span data-stu-id="1c974-165">These map over the starting nodes of a path statement.</span></span> <span data-ttu-id="1c974-166">Tali unità vengono in genere utilizzate per abbreviare percorsi digitati con frequenza.</span><span class="sxs-lookup"><span data-stu-id="1c974-166">They are typically used to shorten paths that are typed frequently.</span></span> <span data-ttu-id="1c974-167">I percorsi SQLSERVER: possono diventare lunghi, occupando spazio nella finestra di Windows PowerShell e richiedendo molta digitazione.</span><span class="sxs-lookup"><span data-stu-id="1c974-167">SQLSERVER: paths can get long, taking space in the Windows PowerShell window and requiring a lot of typing.</span></span> <span data-ttu-id="1c974-168">Se si prevede di lavorare molto in un particolare nodo del percorso, è possibile definire un'unità di Windows PowerShell personalizzata di cui è stato eseguito il mapping a tale nodo.</span><span class="sxs-lookup"><span data-stu-id="1c974-168">If you are going to do a lot of work at a particular path node, you can define a custom Windows PowerShell drive that maps to that node.</span></span>  
  
## <a name="use-powershell-cmdlet-aliases"></a><span data-ttu-id="1c974-169">Utilizzare alias di cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c974-169">Use PowerShell Cmdlet Aliases</span></span>  
 <span data-ttu-id="1c974-170">**Utilizzare un alias di cmdlet**</span><span class="sxs-lookup"><span data-stu-id="1c974-170">**Use a cmdlet alias**</span></span>  
  
-   <span data-ttu-id="1c974-171">Anziché digitare il nome completo di un cmdlet, digitare un alias più breve o uno con mapping a un comando comune del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="1c974-171">Instead of typing a full cmdlet name, type a shorter alias, or one that maps to a familiar commend prompt command.</span></span>  
  
### <a name="alias-example-powershell"></a><span data-ttu-id="1c974-172">Esempio di alias (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1c974-172">Alias Example (PowerShell)</span></span>  
 <span data-ttu-id="1c974-173">È ad esempio possibile utilizzare uno dei set di cmdlet o alias seguenti per recuperare un elenco delle istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] disponibili passando alla cartella SQLSERVER:\SQL e richiedendo l'elenco di elementi figlio per la cartella:</span><span class="sxs-lookup"><span data-stu-id="1c974-173">For example, you can use one of the following sets of cmdlets or aliases to retrieve a listing of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instances available to you by navigating to the SQLSERVER:\SQL folder and requesting the list of child items for the folder:</span></span>  
  
```powershell
## Shows using the full cmdet name.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## Shows using canonical aliases.  
sl SQLSERVER:\SQL  
gci  
  
## Shows using command prompt aliases.  
cd SQLSERVER:\SQL  
dir  
  
## Shows using Unix shell aliases.  
cd SQLSERVER:\SQL  
ls  
```  
  
## <a name="use-get-childitem"></a><span data-ttu-id="1c974-174">Utilizzare Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1c974-174">Use Get-ChildItem</span></span>  

### <a name="return-information-by-using-get-childitem"></a><span data-ttu-id="1c974-175">Restituire informazioni utilizzando Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1c974-175">Return information by using Get-Childitem</span></span>
  
1.  <span data-ttu-id="1c974-176">Passare al nodo per il quale si desidera un elenco di childrem</span><span class="sxs-lookup"><span data-stu-id="1c974-176">Navigate to the node for which you want a list of childrem</span></span>  
  
2.  <span data-ttu-id="1c974-177">Eseguire Get-ChildItem per ottenere l'elenco.</span><span class="sxs-lookup"><span data-stu-id="1c974-177">Run Get-Childitem to get the list.</span></span>  
  
### <a name="get-childitem-example-powershell"></a><span data-ttu-id="1c974-178">Esempio di Get-ChildItem (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1c974-178">Get-ChildItem Example (PowerShell)</span></span>  
 <span data-ttu-id="1c974-179">In questi esempi sono illustrate le informazioni restituite da Get-ChildItem per i nodi diversi in un percorso del provider SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1c974-179">These examples illustrate the information returned by Get-Childitem for different nodes in a SQL Server provider path.</span></span>  
  
```powershell
## Return the current computer and any computer  
## to which you have made a SQL or WMI connection.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## List the instances of the Database Engine on the local computer.  
Set-Location SQLSERVER:\SQL\localhost  
Get-ChildItem  
  
## Lists the categories of objects available in the  
## default instance on the local computer.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT  
Get-ChildItem  
  
## Lists the databases from the local default instance.  
## The force parameter is used to include the system databases.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-ChildItem -force  
```  
  
## <a name="create-a-custom-drive"></a><span data-ttu-id="1c974-180">Creare un'unità personalizzata</span><span class="sxs-lookup"><span data-stu-id="1c974-180">Create a Custom Drive</span></span>  

### <a name="create-and-use-a-custom-drive"></a><span data-ttu-id="1c974-181">Creare e utilizzare un'unità personalizzata</span><span class="sxs-lookup"><span data-stu-id="1c974-181">Create and use a custom drive</span></span>
  
1.  <span data-ttu-id="1c974-182">Utilizzare `New-PSDrive` per definire un'unità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1c974-182">Use `New-PSDrive` to define a custom drive.</span></span> <span data-ttu-id="1c974-183">Utilizzare il parametro `Root` per specificare il percorso rappresentato dal nome di unità personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1c974-183">Use the `Root` parameter to specify the path that is represented by the custom drive name.</span></span>  
  
2.  <span data-ttu-id="1c974-184">Fare riferimento al nome di unità personalizzata nei cmdlet di navigazione come `Set-Location`.</span><span class="sxs-lookup"><span data-stu-id="1c974-184">Reference the custom drive name in path navigation cmdlets such as `Set-Location`.</span></span>  
  
### <a name="custom-drive-example-powershell"></a><span data-ttu-id="1c974-185">Esempio di unità personalizzata (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1c974-185">Custom Drive Example (PowerShell)</span></span>  
 <span data-ttu-id="1c974-186">Questo esempio crea un'unità virtuale denominata AWDB con mapping al nodo di una copia distribuita del database di esempio di AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="1c974-186">This example creates a virtual drive named AWDB that maps to the node for a deployed copy of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="1c974-187">L'unità virtuale è utilizzata quindi per passare a una tabella nel database.</span><span class="sxs-lookup"><span data-stu-id="1c974-187">The virtual drive is then used to navigate to a table in the database.</span></span>  
  
```powershell
## Create a new virtual drive.  
New-PSDrive -Name AWDB -Root SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
  
## Use AWDB: to navigate to a specific table.  
Set-Location AWDB:\Tables\Purchasing.Vendor  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c974-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c974-188">See Also</span></span>  
 <span data-ttu-id="1c974-189">[Provider di SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="1c974-189">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="1c974-190">[Usare i percorsi di SQL Server PowerShell](work-with-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="1c974-190">[Work With SQL Server PowerShell Paths](work-with-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="1c974-191">[Converti URN in percorsi di provider SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="1c974-191">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="1c974-192">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c974-192">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
