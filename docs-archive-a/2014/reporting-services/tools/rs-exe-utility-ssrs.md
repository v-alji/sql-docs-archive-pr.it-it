---
title: Utilità RS.exe (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- automatic report server tasks
- rs utility
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], automating tasks
- command prompt utilities [SQL Server], rs
- scripts [Reporting Services], command prompt
- deploying reports [Reporting Services]
ms.assetid: bd6f958f-cce6-4e79-8a0f-9475da2919ce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bcf21a1bf2453d2bd1f0644e31ca46f3f94e6884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721024"
---
# <a name="rsexe-utility-ssrs"></a><span data-ttu-id="4d6a2-102">RS.exe Utility (SSRS)</span><span class="sxs-lookup"><span data-stu-id="4d6a2-102">RS.exe Utility (SSRS)</span></span>
  <span data-ttu-id="4d6a2-103">L'utilità rs.exe elabora lo script fornito in un file di input.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-103">The rs.exe utility processes script that you provide in an input file.</span></span> <span data-ttu-id="4d6a2-104">Utilizzare questa utilità per automatizzare le attività di amministrazione e distribuzione dei server di report.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-104">Use this utility to automate report server deployment and administration tasks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d6a2-105">A partire da [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], l'utilità **rs** è supportata sia nei server di report configurati per la modalità integrata SharePoint che in quelli configurati in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-105">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], the **rs** utility is supported against report servers that are configured for SharePoint integrated mode as well as servers configured in native mode.</span></span> <span data-ttu-id="4d6a2-106">Le versioni precedenti supportano solo le configurazioni in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-106">Previous versions only supported native mode configurations.</span></span>  
  
 <span data-ttu-id="4d6a2-107">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="4d6a2-107">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="4d6a2-108">Percorso file</span><span class="sxs-lookup"><span data-stu-id="4d6a2-108">File Location</span></span>](#bkmk_filelocation)  
  
-   [<span data-ttu-id="4d6a2-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4d6a2-109">Arguments</span></span>](#bkmk_arguments)  
  
-   [<span data-ttu-id="4d6a2-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4d6a2-110">Permissions</span></span>](#bkmk_permissions)  
  
-   [<span data-ttu-id="4d6a2-111">esempi</span><span class="sxs-lookup"><span data-stu-id="4d6a2-111">Examples</span></span>](#bkmk_examples)  
  
## <a name="syntax"></a><span data-ttu-id="4d6a2-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d6a2-112">Syntax</span></span>  
  
```  
  
      rs {-?}  
{-i input_file=}  
{-s serverURL}  
{-u username}  
{-p password}  
{-e endpoint}  
{-l time_out}  
{-b batchmode}  
{-v globalvars=}  
{-t trace}  
```  
  
##  <a name="file-location"></a><a name="bkmk_filelocation"></a> <span data-ttu-id="4d6a2-113">Percorso del file</span><span class="sxs-lookup"><span data-stu-id="4d6a2-113">File Location</span></span>  
 <span data-ttu-id="4d6a2-114">**RS.exe** si trova in **\Programmi\Microsoft SQL Server\110\Tools\Binn**.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-114">**RS.exe** is located at **\Program Files\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="4d6a2-115">È possibile eseguire l'utilità da qualsiasi cartella del file system.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-115">You can run the utility from any folder on your file system.</span></span>  
  
##  <a name="arguments"></a><a name="bkmk_arguments"></a> <span data-ttu-id="4d6a2-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4d6a2-116">Arguments</span></span>  
 <span data-ttu-id="4d6a2-117">**-?**</span><span class="sxs-lookup"><span data-stu-id="4d6a2-117">**-?**</span></span>  
 <span data-ttu-id="4d6a2-118">(Facoltativo) Visualizza la sintassi degli argomenti **rs** .</span><span class="sxs-lookup"><span data-stu-id="4d6a2-118">(Optional) Displays the syntax of **rs** arguments.</span></span>  
  
 <span data-ttu-id="4d6a2-119">`-i`*input_file*</span><span class="sxs-lookup"><span data-stu-id="4d6a2-119">`-i` *input_file*</span></span>  
 <span data-ttu-id="4d6a2-120">(Obbligatorio) Consente di specificare il file con estensione rss da eseguire.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-120">(Required) Specifies the .rss file to execute.</span></span> <span data-ttu-id="4d6a2-121">Come valore è possibile indicare il percorso relativo o completo di tale file.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-121">This value can be a relative or fully qualified path to the .rss file.</span></span>  
  
 <span data-ttu-id="4d6a2-122">`-s`*ServerURL*</span><span class="sxs-lookup"><span data-stu-id="4d6a2-122">`-s` *serverURL*</span></span>  
 <span data-ttu-id="4d6a2-123">(Obbligatorio) Consente di specificare il nome del server Web e il nome della directory virtuale del server di report in cui eseguire il file.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-123">(Required) Specifies the Web server name and report server virtual directory name to execute the file against.</span></span> <span data-ttu-id="4d6a2-124">Un esempio di URL del server di report è `http://examplewebserver/reportserver`.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-124">An example of a report server URL is `http://examplewebserver/reportserver`.</span></span> <span data-ttu-id="4d6a2-125">Il prefisso http:// o https:// all'inizio del nome del server è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-125">The prefix http:// or https:// at the beginning of the server name is optional.</span></span> <span data-ttu-id="4d6a2-126">Se si omette il prefisso, lo script del server di report prima tenta di utilizzare https e, qualora non funzionasse, utilizza http.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-126">If you omit the prefix, the report server script host tries to use https first, and then uses http if https does not work.</span></span>  
  
 <span data-ttu-id="4d6a2-127">`-u`[*dominio* \\ ] *nome utente*</span><span class="sxs-lookup"><span data-stu-id="4d6a2-127">`-u` [*domain*\\]*username*</span></span>  
 <span data-ttu-id="4d6a2-128">(Facoltativo) Consente di specificare l'account utente utilizzato per connettersi al server di report.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-128">(Optional) Specifies a user account used to connect to the report server.</span></span> <span data-ttu-id="4d6a2-129">Se si omettono `-u` e `-p`, verrà utilizzato l'account utente di Windows corrente.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-129">If `-u` and `-p` are omitted, the current Windows user account is used.</span></span>  
  
 <span data-ttu-id="4d6a2-130">`-p`*password* di</span><span class="sxs-lookup"><span data-stu-id="4d6a2-130">`-p` *password*</span></span>  
 <span data-ttu-id="4d6a2-131">(Obbligatorio se si specifica `-u`) Consente di specificare la password da utilizzare con l'argomento `-u`.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-131">(Required if `-u` is specified) Specifies the password to use with the `-u` argument.</span></span> <span data-ttu-id="4d6a2-132">Per questo valore viene applicata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-132">This value is case-sensitive.</span></span>  
  
 `-e`  
 <span data-ttu-id="4d6a2-133">(Facoltativo) Specifica l'endpoint SOAP in base al quale eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-133">(Optional) Specifies the SOAP endpoint against which the script should run.</span></span> <span data-ttu-id="4d6a2-134">Di seguito sono riportati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="4d6a2-134">Valid values are the following:</span></span>  
  
-   <span data-ttu-id="4d6a2-135">Mgmt2010</span><span class="sxs-lookup"><span data-stu-id="4d6a2-135">Mgmt2010</span></span>  
  
-   <span data-ttu-id="4d6a2-136">Mgmt2006</span><span class="sxs-lookup"><span data-stu-id="4d6a2-136">Mgmt2006</span></span>  
  
-   <span data-ttu-id="4d6a2-137">Mgmt2005</span><span class="sxs-lookup"><span data-stu-id="4d6a2-137">Mgmt2005</span></span>  
  
-   <span data-ttu-id="4d6a2-138">Exec2005</span><span class="sxs-lookup"><span data-stu-id="4d6a2-138">Exec2005</span></span>  
  
 <span data-ttu-id="4d6a2-139">Se non si specifica alcun valore, viene utilizzato l'endpoint Mgmt2005.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-139">If a value is not specified, the Mgmt2005 endpoint is used.</span></span> <span data-ttu-id="4d6a2-140">Per ulteriori informazioni sugli endpoint SOAP, vedere [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a2-140">For more information about the SOAP endpoints, see [Report Server Web Service Endpoints](../report-server-web-service/methods/report-server-web-service-endpoints.md).</span></span>  
  
 <span data-ttu-id="4d6a2-141">`-l`*time_out*</span><span class="sxs-lookup"><span data-stu-id="4d6a2-141">`-l` *time_out*</span></span>  
 <span data-ttu-id="4d6a2-142">Opzionale Specifica il numero di secondi che devono trascorrere prima che si verifichi il timeout della connessione al server. Il valore predefinito è 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-142">(Optional) Specifies the number of seconds that elapse before the connection to the server times out. The default is 60 seconds.</span></span> <span data-ttu-id="4d6a2-143">Se non si specifica un valore per il timeout, verrà utilizzato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-143">If you do not specify a time-out value, the default is used.</span></span> <span data-ttu-id="4d6a2-144">Se si specifica il valore `0`, non si verificherà mai il timeout della connessione.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-144">A value of `0` specifies that the connection never times out.</span></span>  
  
 <span data-ttu-id="4d6a2-145">**-b**</span><span class="sxs-lookup"><span data-stu-id="4d6a2-145">**-b**</span></span>  
 <span data-ttu-id="4d6a2-146">(Facoltativo) Specifica che i comandi del file di script vengano eseguiti come batch.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-146">(Optional) Specifies that the commands in the script file run in a batch.</span></span> <span data-ttu-id="4d6a2-147">Se uno o più comandi hanno esito negativo, verrà eseguito il rollback dell'intero batch.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-147">If any commands fail, the batch is rolled back.</span></span> <span data-ttu-id="4d6a2-148">Vi sono tuttavia comandi non eseguibili in batch. Tali comandi verranno eseguiti normalmente</span><span class="sxs-lookup"><span data-stu-id="4d6a2-148">Some commands cannot be batched, and those run as usual.</span></span> <span data-ttu-id="4d6a2-149">e verrà eseguito un rollback solo in caso di eccezioni generate e non gestite nell'ambito dello script.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-149">Only exceptions that are thrown and are not handled within the script result in a rollback.</span></span> <span data-ttu-id="4d6a2-150">Se lo script gestisce un'eccezione e completa normalmente la routine `Main`, verrà eseguito il commit del batch.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-150">If the script handles an exception and returns normally from `Main`, the batch is committed.</span></span> <span data-ttu-id="4d6a2-151">Se si omette questo parametro, i comandi verranno eseguiti senza la creazione di un batch.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-151">If you omit this parameter, the commands run without creating a batch.</span></span> <span data-ttu-id="4d6a2-152">Per altre informazioni, vedere [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a2-152">For more information, see [Batching Methods](../report-server-web-service-net-framework-soap-headers/batching-methods.md).</span></span>  
  
 <span data-ttu-id="4d6a2-153">`-v`*GlobalVar (*</span><span class="sxs-lookup"><span data-stu-id="4d6a2-153">`-v` *globalvar*</span></span>  
 <span data-ttu-id="4d6a2-154">(Facoltativo) Consente di specificare le variabili globali utilizzate nello script.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-154">(Optional) Specifies global variables that are used in the script.</span></span> <span data-ttu-id="4d6a2-155">Se lo script utilizza variabili globali, è necessario specificare questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-155">If the script uses global variables, you must specify this argument.</span></span> <span data-ttu-id="4d6a2-156">Il valore specificato deve essere valido per la variabile globale definita nel file con estensione rss.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-156">The value that you specify must be valid for global variable defined in the .rss file.</span></span> <span data-ttu-id="4d6a2-157">È necessario specificare una variabile globale per ogni argomento **-v** .</span><span class="sxs-lookup"><span data-stu-id="4d6a2-157">You must specify one global variable for each **-v** argument.</span></span>  
  
 <span data-ttu-id="4d6a2-158">L'argomento `-v` viene specificato nella riga di comando ed è utilizzato per impostare il valore per una variabile globale definita in fase di esecuzione nello script.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-158">The `-v` argument is specified on the command line and is used to set the value for a global variable that is defined in your script at run time.</span></span> <span data-ttu-id="4d6a2-159">Se, ad esempio, lo script contiene un variabile denominata *parentFolder*, è possibile specificare un nome per la cartella nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="4d6a2-159">For example, if your script contains a variable named *parentFolder*, you can specify a name for that folder on the command line:</span></span>  
  
 `rs.exe -i myScriptFile.rss -s http://myServer/reportserver -v parentFolder="Financial Reports"`  
  
 <span data-ttu-id="4d6a2-160">Le variabili globali vengono create con i nomi indicati e impostate sui valori specificati.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-160">Global variables are created with the names given and set to the values supplied.</span></span> <span data-ttu-id="4d6a2-161">Ad esempio, **-v a =**" `1` " **-v b =**" `2` " restituisce una variabile denominata `a` con un valore di " `1` " e una variabile **b** con un valore " `2` ".</span><span class="sxs-lookup"><span data-stu-id="4d6a2-161">For example, **-v a=**"`1`" **-v b=**"`2`" results in a variable named `a` with a value of"`1`" and a variable **b** with a value of "`2`".</span></span>  
  
 <span data-ttu-id="4d6a2-162">Le variabili globali sono disponibili per qualsiasi funzione nello script.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-162">Global variables are available to any function in the script.</span></span> <span data-ttu-id="4d6a2-163">Una barra rovesciata e le virgolette (\*\* \\ "\*\*) vengono interpretate come virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-163">A backslash and quotation mark (**\\"**) is interpreted as a double quotation mark.</span></span> <span data-ttu-id="4d6a2-164">Le virgolette sono necessarie solo se la stringa contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-164">The quotation marks are required only if the string contains a space.</span></span> <span data-ttu-id="4d6a2-165">I nomi delle variabili devono essere validi per [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ; devono iniziare con un carattere alfabetico o un carattere di sottolineatura e contenere caratteri alfabetici, cifre o caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-165">Variable names must be valid for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]; they must start with alphabetical character or underscore and contain alphabetical characters, digits, or underscores.</span></span> <span data-ttu-id="4d6a2-166">Le parole riservate non possono essere utilizzate come nomi di variabili.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-166">Reserved words cannot be used as variable names.</span></span> <span data-ttu-id="4d6a2-167">Per altre informazioni sull'uso delle variabili globali, vedere [Raccolte predefinite nelle espressioni &#40;Generatore report e SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a2-167">For more information about using global variables, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
 <span data-ttu-id="4d6a2-168">**-t**</span><span class="sxs-lookup"><span data-stu-id="4d6a2-168">**-t**</span></span>  
 <span data-ttu-id="4d6a2-169">(Facoltativo) Crea l'output dei messaggi di errore nel log di traccia.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-169">(Optional) Outputs error messages to the trace log.</span></span> <span data-ttu-id="4d6a2-170">Questo argomento non accetta un valore.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-170">This argument does not take a value.</span></span> <span data-ttu-id="4d6a2-171">Per altre informazioni, vedere [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a2-171">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
##  <a name="permissions"></a><a name="bkmk_permissions"></a> <span data-ttu-id="4d6a2-172">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4d6a2-172">Permissions</span></span>  
 <span data-ttu-id="4d6a2-173">Per eseguire questo strumento, è necessario disporre dell'autorizzazione per connettersi all'istanza del server di report in cui lo script è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-173">To run the tool, you must have permission to connect to the report server instance you are running the script against.</span></span> <span data-ttu-id="4d6a2-174">È possibile eseguire script per apportare modifiche nel computer locale o in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-174">You can run scripts to make changes to the local computer or a remote computer.</span></span> <span data-ttu-id="4d6a2-175">Per apportare modifiche a un server di report installato in un computer remoto, specificare il computer remoto nell'argomento `-s`.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-175">To make changes to a report server installed on a remote computer, specify the remote computer in the `-s` argument.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="4d6a2-176">Esempi</span><span class="sxs-lookup"><span data-stu-id="4d6a2-176">Examples</span></span>  
 <span data-ttu-id="4d6a2-177">Nell'esempio seguente viene illustrato come specificare il file script contenente lo script di [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET e i metodi del servizio Web che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-177">The following example illustrates how to specify the script file that contains [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET script and Web service methods that you want to execute.</span></span>  
  
```  
rs -i c:\scriptfiles\script_copycontent.rss -s http://localhost/reportserver  
```  
  
 <span data-ttu-id="4d6a2-178"> Per un esempio dettagliato, vedere [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a2-178">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="4d6a2-179">Per ulteriori esempi, vedere [Eseguire un file script di Reporting Services](run-a-reporting-services-script-file.md)</span><span class="sxs-lookup"><span data-stu-id="4d6a2-179">For additional examples, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d6a2-180">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4d6a2-180">Remarks</span></span>  
 <span data-ttu-id="4d6a2-181">È possibile definire script per impostare le proprietà di sistema, pubblicare report e così via.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-181">You can define scripts to set system properties, publish reports, and so forth.</span></span> <span data-ttu-id="4d6a2-182">Gli script creati possono includere qualsiasi metodo dell'API di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d6a2-182">The scripts that you create can include any methods of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="4d6a2-183">Per ulteriori informazioni sui metodi e sulle proprietà disponibili, vedere [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a2-183">For more information about the methods and properties available to you, see [Report Server Web Service](../report-server-web-service/report-server-web-service.md).</span></span>  
  
 <span data-ttu-id="4d6a2-184">Lo script deve essere scritto in codice [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET e archiviato in un file di testo Unicode o UTF-8 con estensione di file rss.</span><span class="sxs-lookup"><span data-stu-id="4d6a2-184">The script must be written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET code, and stored in a Unicode or UTF-8 text file with an .rss file name extension.</span></span> <span data-ttu-id="4d6a2-185">Non è possibile eseguire il debug degli script con l'utilità **rs** .</span><span class="sxs-lookup"><span data-stu-id="4d6a2-185">You cannot debug scripts with the **rs** utility.</span></span> <span data-ttu-id="4d6a2-186">Per eseguire il debug di uno script, eseguire il codice all'interno di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d6a2-186">To debug a script, run the code within [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="4d6a2-187"> Per un esempio dettagliato, vedere [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="4d6a2-187">For a detailed example, see [Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6a2-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d6a2-188">See Also</span></span>  
 <span data-ttu-id="4d6a2-189">[Eseguire un file script di Reporting Services](run-a-reporting-services-script-file.md) </span><span class="sxs-lookup"><span data-stu-id="4d6a2-189">[Run a Reporting Services Script File](run-a-reporting-services-script-file.md) </span></span>  
 <span data-ttu-id="4d6a2-190">[Script per distribuzione e attività amministrative](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="4d6a2-190">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="4d6a2-191">[Script con l'utilità rs.exe e il servizio Web](script-with-the-rs-exe-utility-and-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="4d6a2-191">[Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md) </span></span>  
 [<span data-ttu-id="4d6a2-192">Utilità della riga di comando del server di report &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4d6a2-192">Report Server Command Prompt Utilities &#40;SSRS&#41;</span></span>](report-server-command-prompt-utilities-ssrs.md)  
  
  
