---
title: Cmdlet Invoke-PolicyEvaluation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, Invoke-PolicyEvaluation
- Policy-Based Management, PowerShell
- Invoke-PolicyEvaluation cmdlet
- Cmdlets [SQL Server], Invoke-PolicyEvaluation
- PowerShell [SQL Server], Invoke-PolicyEvaluation
ms.assetid: 3e6d4f5a-59b7-4203-b95a-f7e692c0f131
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 656fdffea191c9cf6fc42d860164bc5af1e04561
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714560"
---
# <a name="invoke-policyevaluation-cmdlet"></a><span data-ttu-id="32c44-102">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="32c44-102">Invoke-PolicyEvaluation cmdlet</span></span>
  <span data-ttu-id="32c44-103">**Invoke-PolicyEvaluation** è un cmdlet di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] che segnala se un set di destinazioni di oggetti di SQL Server è conforme alle condizioni specificate in uno o più criteri della gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="32c44-103">**Invoke-PolicyEvaluation** is a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlet that reports whether a target set of SQL Server objects complies with the conditions specified in one or more Policy-Based Management policies.</span></span>  
  
## <a name="using-invoke-policyevaluation"></a><span data-ttu-id="32c44-104">Utilizzo di Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="32c44-104">Using Invoke-PolicyEvaluation</span></span>  
 <span data-ttu-id="32c44-105">**Invoke-PolicyEvaluation** valuta uno o più criteri rispetto a un set di oggetti di SQL Server denominato set di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="32c44-105">**Invoke-PolicyEvaluation** evaluates one or more policies against a set of SQL Server objects called the target set.</span></span> <span data-ttu-id="32c44-106">Il set di oggetti di destinazione proviene da un server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="32c44-106">The set of target objects comes from a target server.</span></span> <span data-ttu-id="32c44-107">I criteri definiscono delle condizioni, che sono gli stati consentiti per gli oggetti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="32c44-107">Each policy defines conditions, which are the allowed states for the target objects.</span></span> <span data-ttu-id="32c44-108">Ad esempio, i criteri **Database con proprietà trustworthy** dichiarano che la proprietà di database TRUSTWORTHY deve essere impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="32c44-108">For example, the **Trustworthy Database** policy states that the TRUSTWORTHY database property must be set to OFF.</span></span>  
  
 <span data-ttu-id="32c44-109">Il parametro **-AdHocPolicyEvaluationMode** specifica le azioni intraprese:</span><span class="sxs-lookup"><span data-stu-id="32c44-109">The **-AdHocPolicyEvaluationMode** parameter specifies the actions taken:</span></span>  
  
 <span data-ttu-id="32c44-110">Controllo</span><span class="sxs-lookup"><span data-stu-id="32c44-110">Check</span></span>  
 <span data-ttu-id="32c44-111">Consente di segnalare lo stato di conformità degli oggetti di destinazione utilizzando le credenziali dell'accesso corrente.</span><span class="sxs-lookup"><span data-stu-id="32c44-111">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="32c44-112">Non riconfigura alcun oggetto.</span><span class="sxs-lookup"><span data-stu-id="32c44-112">Do no reconfigure any objects.</span></span> <span data-ttu-id="32c44-113">Si tratta dell'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="32c44-113">This is the default setting.</span></span>  
  
 <span data-ttu-id="32c44-114">CheckSqlScriptAsProxy</span><span class="sxs-lookup"><span data-stu-id="32c44-114">CheckSqlScriptAsProxy</span></span>  
 <span data-ttu-id="32c44-115">Consente di segnalare lo stato di conformità degli oggetti di destinazione usando le credenziali dell'accesso proxy **##MS_PolicyTSQLExecutionLogin##** .</span><span class="sxs-lookup"><span data-stu-id="32c44-115">Report the compliance status of the target objects using the credentials of the **##MS_PolicyTSQLExecutionLogin##** proxy login.</span></span> <span data-ttu-id="32c44-116">Non riconfigura alcun oggetto.</span><span class="sxs-lookup"><span data-stu-id="32c44-116">Do no reconfigure any objects.</span></span>  
  
 <span data-ttu-id="32c44-117">Configurare</span><span class="sxs-lookup"><span data-stu-id="32c44-117">Configure</span></span>  
 <span data-ttu-id="32c44-118">Consente di segnalare lo stato di conformità degli oggetti di destinazione utilizzando le credenziali dell'accesso corrente.</span><span class="sxs-lookup"><span data-stu-id="32c44-118">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="32c44-119">Riconfigura qualsiasi opzione deterministica e configurabile che non è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="32c44-119">Reconfigure any settable and deterministic options that are not in compliance with the policies.</span></span>  
  
## <a name="specifying-polices"></a><span data-ttu-id="32c44-120">Definizione di criteri</span><span class="sxs-lookup"><span data-stu-id="32c44-120">Specifying Polices</span></span>  
 <span data-ttu-id="32c44-121">La modalità utilizzata per specificare i criteri dipende dalla posizione di archiviazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="32c44-121">How you specify a policy depends on where the policy is stored.</span></span> <span data-ttu-id="32c44-122">I criteri possono essere archiviati in due formati:</span><span class="sxs-lookup"><span data-stu-id="32c44-122">Policies can be stored in two formats:</span></span>  
  
-   <span data-ttu-id="32c44-123">Possono essere oggetti archiviati in un archivio criteri, ad esempio un'istanza del Motore di database.</span><span class="sxs-lookup"><span data-stu-id="32c44-123">They can be objects stored in a policy store, such as an instance of the Database Engine.</span></span> <span data-ttu-id="32c44-124">È possibile utilizzare la cartella SQLSERVER:\SQLPolicy per specificare il percorso di criteri in un archivio criteri.</span><span class="sxs-lookup"><span data-stu-id="32c44-124">You can use the SQLSERVER:\SQLPolicy folder to specify the location of policies in a policy store.</span></span> <span data-ttu-id="32c44-125">È possibile utilizzare i cmdlet di Windows PowerShell per filtrare i criteri di input in base alle relative proprietà, ad esempio utilizzando Where-Object per applicare il filtro in base alla categoria di criteri oppure Get-Item per applicare il filtro in base al nome dei criteri.</span><span class="sxs-lookup"><span data-stu-id="32c44-125">You can use Windows PowerShell cmdlets to filter the input polices based on their properties, such as using Where-Object to filter on the policy category or Get-Item to filter on policy name.</span></span>  
  
-   <span data-ttu-id="32c44-126">I criteri possono essere esportati come file XML.</span><span class="sxs-lookup"><span data-stu-id="32c44-126">They can be exported as XML files.</span></span> <span data-ttu-id="32c44-127">È possibile utilizzare un'unità del file system, ad esempio D:, per specificare il percorso dei file XML.</span><span class="sxs-lookup"><span data-stu-id="32c44-127">You can use a file system drive, such as D:, to specify the location of the XML files.</span></span> <span data-ttu-id="32c44-128">È possibile utilizzare i cmdlet di Windows PowerShell, ad esempio Where-Object, per filtrare i criteri in base alle proprietà dei file, ad esempio il nome del file.</span><span class="sxs-lookup"><span data-stu-id="32c44-128">You can use Windows PowerShell cmdlets such as Where-Object to filter the policies on their file properties, such as file name.</span></span>  
  
 <span data-ttu-id="32c44-129">Se i criteri vengono archiviati in un archivio criteri, è necessario passare un set di oggetti PSObject che punta ai criteri da valutare.</span><span class="sxs-lookup"><span data-stu-id="32c44-129">If the policies are stored in a policy store, you must pass in a set of PSObjects pointing to the policies to be evaluated.</span></span> <span data-ttu-id="32c44-130">Questo avviene in genere inoltrando tramite pipe a **Invoke-PolicyEvaluation**l'output di un cmdlet, ad esempio Get-Item, e non richiede la specifica del parametro **-Policy** .</span><span class="sxs-lookup"><span data-stu-id="32c44-130">This is typically done by piping the output of a cmdlet such as Get-Item to **Invoke-PolicyEvaluation**, and does not require that you specify the **-Policy** parameter.</span></span> <span data-ttu-id="32c44-131">Ad esempio, se sono stati importati i criteri delle procedure consigliate Microsoft nell'istanza del motore di database, questo comando valuta i criteri **Stato del database** :</span><span class="sxs-lookup"><span data-stu-id="32c44-131">For example, if you have imported the Microsoft Best Practices policies into your instance of the database engine, this command evaluates the **Database Status** policy:</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Get-Item "Database Status" | Invoke-PolicyEvaluation -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="32c44-132">Questo esempio illustra l'uso di Where-Object per filtrare più criteri da un archivio criteri in base alla relativa proprietà **PolicyCategory** .</span><span class="sxs-lookup"><span data-stu-id="32c44-132">This example shows using Where-Object to filter multiple policies from a policy store based on their **PolicyCategory** property.</span></span> <span data-ttu-id="32c44-133">Gli oggetti dall'output inoltrato tramite pipe di **Where-Object** vengono usati da **Invoke-PolicyEvaluation**.</span><span class="sxs-lookup"><span data-stu-id="32c44-133">The objects from the piped output of **Where-Object** is consumed by **Invoke-PolicyEvaluation**.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
gci | Where-Object {$_.PolicyCategory -eq "Microsoft Best Practices: Maintenance"} | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
 <span data-ttu-id="32c44-134">Se i criteri sono archiviati come file XML, è necessario usare il parametro **-Policy** per specificare il percorso e il nome per tutti i criteri.</span><span class="sxs-lookup"><span data-stu-id="32c44-134">If the policies are stored as XML files, you must use the **-Policy** parameter to supply both the path and name for each policy.</span></span> <span data-ttu-id="32c44-135">Se non si specifica un percorso nel parametro **-Policy** , **Invoke-PolicyEvaulation** usa l'impostazione corrente del percorso **sqlps** .</span><span class="sxs-lookup"><span data-stu-id="32c44-135">If you do not specify a path in the **-Policy** parameter, **Invoke-PolicyEvaulation** uses the current setting of the **sqlps** path.</span></span> <span data-ttu-id="32c44-136">Ad esempio, questo comando valuta uno dei criteri di Procedura consigliata di Microsoft installato con SQL Server rispetto al database predefinito per l'accesso:</span><span class="sxs-lookup"><span data-stu-id="32c44-136">For example, this command evaluates one of the Microsoft Best Practice policies installed with SQL Server against the default database for your login:</span></span>  
  
```powershell
Invoke-PolicyEvaluation -Policy "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033\Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="32c44-137">Questo comando consente di eseguire la stessa operazione, solo che usa il percorso **sqlps** corrente per stabilire il percorso del file XML dei criteri:</span><span class="sxs-lookup"><span data-stu-id="32c44-137">This command does the same thing, only it uses the current **sqlps** path to establish the location of the policy XML file:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="32c44-138">Questo esempio illustra l'uso del cmdlet **Get-ChildItem** per recuperare più file XML di criteri e inoltrare tramite pipe gli oggetti in **Invoke-PolicyEvaluation**:</span><span class="sxs-lookup"><span data-stu-id="32c44-138">This example shows using the **Get-ChildItem** cmdlet to retrieve multiple policy XML files and pipe the objects into **Invoke-PolicyEvaluation**:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
gci "Database Status.xml", "Trustworthy Database.xml" | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
## <a name="specifying-the-target-set"></a><span data-ttu-id="32c44-139">Specifica del set di destinazioni</span><span class="sxs-lookup"><span data-stu-id="32c44-139">Specifying the Target Set</span></span>  
 <span data-ttu-id="32c44-140">Utilizzare tre parametri per specificare il set di oggetti di destinazione:</span><span class="sxs-lookup"><span data-stu-id="32c44-140">Use three parameters to specify the set of target objects:</span></span>  
  
-   <span data-ttu-id="32c44-141">**-TargetServerName** consente di specificare l'istanza di SQL Server che contiene gli oggetti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="32c44-141">**-TargetServerName** specifies the instance of SQL Server containing the target objects.</span></span> <span data-ttu-id="32c44-142">È possibile specificare le informazioni in una stringa che utilizza il formato definito per la proprietà ConnectionString della classe <xref:System.Data.SqlClient.SqlConnection> .</span><span class="sxs-lookup"><span data-stu-id="32c44-142">You can specify the information in a string that uses the format defined for the ConnectionString property of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="32c44-143">È possibile usare la classe <xref:System.Data.SqlClient.SqlConnectionStringBuilder> per compilare una stringa di connessione con formato corretto.</span><span class="sxs-lookup"><span data-stu-id="32c44-143">You can use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to build a correctly formatted connection string.</span></span> <span data-ttu-id="32c44-144">È inoltre possibile creare un oggetto <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> e passarlo a **-TargetServer**.</span><span class="sxs-lookup"><span data-stu-id="32c44-144">You can also create a <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> object and pass it to **-TargetServer**.</span></span> <span data-ttu-id="32c44-145">Se si specifica una stringa che contiene solo il nome del server, **Invoke-PolicyEvaluation** userà l'autenticazione di Windows per connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="32c44-145">If you supply a string that has only the name of the server, **Invoke-PolicyEvaluation** uses Windows Authentication to connect to the server.</span></span>  
  
-   <span data-ttu-id="32c44-146">**-TargetObjects** accetta un oggetto o una matrice di oggetti che rappresenta gli oggetti di SQL Server nel set di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="32c44-146">**-TargetObjects** takes an object or array of objects that represent the SQL Server objects in the target set.</span></span> <span data-ttu-id="32c44-147">È possibile ad esempio creare una matrice di oggetti di classe <xref:Microsoft.SqlServer.Management.Smo.Database> da passare in **-TargetObjects**.</span><span class="sxs-lookup"><span data-stu-id="32c44-147">For example, you could create an array of <xref:Microsoft.SqlServer.Management.Smo.Database> class objects to pass in to **-TargetObjects**.</span></span>  
  
-   <span data-ttu-id="32c44-148">**-TargetExpressions** consente di prendere una stringa contenente un'espressione di query che specifica gli oggetti nel set di destinazioni.</span><span class="sxs-lookup"><span data-stu-id="32c44-148">**-TargetExpressions** takes a string containing a query expression that specifies the objects in the target set.</span></span> <span data-ttu-id="32c44-149">L'espressione di query è nel formato di nodi separati dal carattere barra (/).</span><span class="sxs-lookup"><span data-stu-id="32c44-149">The query expression is in the form of nodes separated by the '/' character.</span></span> <span data-ttu-id="32c44-150">Ogni nodo è nel formato ObjectType[Filter].</span><span class="sxs-lookup"><span data-stu-id="32c44-150">Each node is in the form ObjectType[Filter].</span></span> <span data-ttu-id="32c44-151">Il tipo di oggetto è uno degli oggetti in una gerarchia di oggetti SMO (SQL Server Management Object).</span><span class="sxs-lookup"><span data-stu-id="32c44-151">Object type is one of the objects in a SQL Server Management Object (SMO) object hierarchy.</span></span> <span data-ttu-id="32c44-152">Filter è un'espressione che filtra gli oggetti in corrispondenza di quel nodo.</span><span class="sxs-lookup"><span data-stu-id="32c44-152">Filter is an expression that filters for objects at that node.</span></span> <span data-ttu-id="32c44-153">Per altre informazioni, vedere [Espressioni di query e Uniform Resource Name](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="32c44-153">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
 <span data-ttu-id="32c44-154">Specificare il parametro **-TargetObjects** o **-TargetExpression**, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="32c44-154">Specify either **-TargetObjects** or **-TargetExpression**, not both.</span></span>  
  
 <span data-ttu-id="32c44-155">In questo esempio viene utilizzato un oggetto Sfc.SqlStoreConnection per specificare il server di destinazione:</span><span class="sxs-lookup"><span data-stu-id="32c44-155">This example uses an Sfc.SqlStoreConnection object to specify the target server:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
$conn = New-Object Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection("server='MYCOMPUTER';Trusted_Connection=True")  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName $conn  
```  
  
 <span data-ttu-id="32c44-156">In questo esempio viene usato **-TargetExpression** per identificare il database specifico da valutare:</span><span class="sxs-lookup"><span data-stu-id="32c44-156">This example uses **-TargetExpression** to identify the specific database to evaluate:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MyComputer" -TargetExpression "Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']"  
```  
  
## <a name="evaluating-analysis-services-policies"></a><span data-ttu-id="32c44-157">Valutazione di criteri di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="32c44-157">Evaluating Analysis Services Policies</span></span>  
 <span data-ttu-id="32c44-158">Per valutare i criteri rispetto a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], è necessario caricare e registrare un assembly in PowerShell, creare una variabile con un oggetto di connessione di Analysis Services e passarla al parametro **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="32c44-158">To evaluate policies against an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you must load and register an assembly into PowerShell, create a variable with an Analysis Services connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="32c44-159">In questo esempio viene illustrata la valutazione dei criteri di configurazione della superficie di attacco di Procedure consigliate per [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="32c44-159">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\AnalysisServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.AnalysisServices")  
$SSASsvr = New-Object Microsoft.AnalysisServices.Server  
$SSASsvr.Connect("Data Source=Localhost")  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Analysis Services Features.xml" -TargetObject $SSASsvr  
```  
  
## <a name="evaluating-reporting-services-policies"></a><span data-ttu-id="32c44-160">Valutazione di criteri di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="32c44-160">Evaluating Reporting Services Policies</span></span>  
 <span data-ttu-id="32c44-161">Per valutare criteri di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , è necessario caricare e registrare un assembly in PowerShell, creare una variabile con un oggetto di connessione di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e passarla al parametro **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="32c44-161">To evaluate [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] policies, you must load and register an assembly into PowerShell, create a variable with a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="32c44-162">In questo esempio viene illustrata la valutazione dei criteri di configurazione della superficie di attacco di Procedure consigliate per [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="32c44-162">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\ReportingServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Dmf.Adapters")  
$SSRSsvr = new-object Microsoft.SqlServer.Management.Adapters.RSContainer('MyComputer')  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Reporting Services 2008 Features.xml" -TargetObject $SSRSsvr  
```  
  
## <a name="formatting-output"></a><span data-ttu-id="32c44-163">Formattazione dell'output</span><span class="sxs-lookup"><span data-stu-id="32c44-163">Formatting Output</span></span>  
 <span data-ttu-id="32c44-164">Per impostazione predefinita, l'output di **Invoke-PolicyEvaluation** viene visualizzato nella finestra del prompt dei comandi sotto forma di breve report in formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="32c44-164">By default, the output of **Invoke-PolicyEvaluation** is displayed in the command prompt window as a concise report in human-readable format.</span></span> <span data-ttu-id="32c44-165">Usare il parametro **-OutputXML** per specificare che dal cmdlet venga generato invece un report dettagliato come file XML.</span><span class="sxs-lookup"><span data-stu-id="32c44-165">You can use the **-OutputXML** parameter to specify that the cmdlet instead produce a detailed report as an XML file.</span></span> <span data-ttu-id="32c44-166">**Invoke-PolicyEvaluation** usa lo schema SML-IF (Systems Modeling Language Interchange Format) affinché il file sia leggibile tramite i lettori SML-IF.</span><span class="sxs-lookup"><span data-stu-id="32c44-166">**Invoke-PolicyEvaluation** uses the Systems Modeling Language Interchange Format (SML-IF) schema so the file can be read by SML-IF readers.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Invoke-PolicyEvaluation -Policy "Datbase Status" -TargetServer "MYCOMPUTER" -OutputXML > C:\MyReports\DatabaseStatusReport.xml  
```  
  
## <a name="see-also"></a><span data-ttu-id="32c44-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32c44-167">See Also</span></span>  
 [<span data-ttu-id="32c44-168">Utilizzo di cmdlet del motore di database</span><span class="sxs-lookup"><span data-stu-id="32c44-168">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
