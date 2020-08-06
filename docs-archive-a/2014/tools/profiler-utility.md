---
title: Utilità Profiler | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- command prompt utilities [SQL Server], profiler90 utility
- profiler90 utility
- Profiler [SQL Server Profiler], starting
- SQL Server Profiler, starting
- starting SQL Server Profiler
ms.assetid: e91c30a9-0d29-4f84-bcb8-e8fb62afadda
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8df3e8557bb52839d17291bae0c5ba507d0a671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711291"
---
# <a name="profiler-utility"></a><span data-ttu-id="2cda3-102">Utilità profiler</span><span class="sxs-lookup"><span data-stu-id="2cda3-102">Profiler Utility</span></span>
  <span data-ttu-id="2cda3-103">L'utilità **profiler** consente di avviare lo strumento [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cda3-103">The **profiler** utility launches the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] tool.</span></span> <span data-ttu-id="2cda3-104">Gli argomenti facoltativi elencati di seguito in questo argomento consentono di controllare la modalità di avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2cda3-104">The optional arguments listed later in this topic allow you to control how the application starts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cda3-105">L'utilità **profiler** non viene usata per lo scripting delle tracce.</span><span class="sxs-lookup"><span data-stu-id="2cda3-105">The **profiler** utility is not intended for scripting traces.</span></span> <span data-ttu-id="2cda3-106">Per altre informazioni, vedere [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="2cda3-106">For more information, see [SQL Server Profiler](sql-server-profiler/sql-server-profiler.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cda3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2cda3-107">Syntax</span></span>  
  
```  
  
      profiler  
          [ /? ] |  
[  
{  
{ /U login_id [ /P password ] }  
| /E  
}  
{[ /S sql_server_name ] | [ /A analysis_services_server_name ] }  
[ /D database ]  
[ /T "template_name" ]  
[ /B { "trace_table_name" } ]  
{ [/F "filename" ] | [ /O "filename" ] }  
[ /L locale_ID ]  
[ /M "MM-DD-YY hh:mm:ss" ]  
[ /R ]  
[ /Z file_size ]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2cda3-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2cda3-108">Arguments</span></span>  
 <span data-ttu-id="2cda3-109">**/?**</span><span class="sxs-lookup"><span data-stu-id="2cda3-109">**/?**</span></span>  
 <span data-ttu-id="2cda3-110">Visualizza il riepilogo della sintassi degli argomenti di **profiler** .</span><span class="sxs-lookup"><span data-stu-id="2cda3-110">Displays the syntax summary of **profiler** arguments.</span></span>  
  
 <span data-ttu-id="2cda3-111">**/U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="2cda3-111">**/U** *login_id*</span></span>  
 <span data-ttu-id="2cda3-112">ID di accesso utente per l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cda3-112">Is the user login ID for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="2cda3-113">Per gli ID di accesso la distinzione tra maiuscole e minuscole è rilevante.</span><span class="sxs-lookup"><span data-stu-id="2cda3-113">Login IDs are case sensitive.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]<span data-ttu-id="2cda3-114">.</span><span class="sxs-lookup"><span data-stu-id="2cda3-114">.</span></span>  
  
 <span data-ttu-id="2cda3-115">**/P** *password*</span><span class="sxs-lookup"><span data-stu-id="2cda3-115">**/P** *password*</span></span>  
 <span data-ttu-id="2cda3-116">Specifica una password definita dall'utente per l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cda3-116">Specifies a user-specified password for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="2cda3-117">**/E**</span><span class="sxs-lookup"><span data-stu-id="2cda3-117">**/E**</span></span>  
 <span data-ttu-id="2cda3-118">Specifica la connessione tramite l'autenticazione di Windows e le credenziali dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="2cda3-118">Specifies connecting with Windows Authentication with the current user's credentials.</span></span>  
  
 <span data-ttu-id="2cda3-119">**/S**  *sql_server_name*</span><span class="sxs-lookup"><span data-stu-id="2cda3-119">**/S**  *sql_server_name*</span></span>  
 <span data-ttu-id="2cda3-120">Specifica un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cda3-120">Specifies an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2cda3-121">Profiler viene automaticamente connesso al server specificato usando le informazioni di autenticazione definite nelle opzioni **/U** e **/P** o **/E** .</span><span class="sxs-lookup"><span data-stu-id="2cda3-121">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="2cda3-122">Usare **/S** *sql_server_name*\\*instance_name* per connettersi a un'istanza denominata di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cda3-122">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use **/S** *sql_server_name*\\*instance_name*.</span></span>  
  
 <span data-ttu-id="2cda3-123">**/A**  *analysis_services_server_name*</span><span class="sxs-lookup"><span data-stu-id="2cda3-123">**/A**  *analysis_services_server_name*</span></span>  
 <span data-ttu-id="2cda3-124">Consente di specificare un'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2cda3-124">Specifies an instance of Analysis Services.</span></span> <span data-ttu-id="2cda3-125">Profiler viene automaticamente connesso al server specificato usando le informazioni di autenticazione definite nelle opzioni **/U** e **/P** o **/E** .</span><span class="sxs-lookup"><span data-stu-id="2cda3-125">Profiler will automatically connect to the specified server using the authentication information specified in the **/U** and **/P** switches or the **/E** switch.</span></span> <span data-ttu-id="2cda3-126">Usare **/A** *analysis_services_server_name\instance_name* per connettersi a un'istanza denominata di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cda3-126">To connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] use **/A** *analysis_services_server_name\instance_name*.</span></span>  
  
 <span data-ttu-id="2cda3-127">**/D** *database*</span><span class="sxs-lookup"><span data-stu-id="2cda3-127">**/D** *database*</span></span>  
 <span data-ttu-id="2cda3-128">Specifica il nome del database da utilizzare con la connessione.</span><span class="sxs-lookup"><span data-stu-id="2cda3-128">Specifies the name of the database to be used with the connection.</span></span> <span data-ttu-id="2cda3-129">Se non si specifica alcun database, questa opzione selezionerà il database predefinito per l'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="2cda3-129">This option will select the default database for the specified user if no database is specified.</span></span>  
  
 <span data-ttu-id="2cda3-130">**/B "** *trace_table_name* **"**</span><span class="sxs-lookup"><span data-stu-id="2cda3-130">**/B "** *trace_table_name* **"**</span></span>  
 <span data-ttu-id="2cda3-131">Specifica una tabella di traccia da caricare all'avvio di SQL Profiler.</span><span class="sxs-lookup"><span data-stu-id="2cda3-131">Specifies a trace table to load when the profiler is launched.</span></span> <span data-ttu-id="2cda3-132">Assieme alla tabella è necessario specificare il database, l'utente oppure lo schema.</span><span class="sxs-lookup"><span data-stu-id="2cda3-132">You must specify the database, the user or schema, and the table.</span></span>  
  
 <span data-ttu-id="2cda3-133">**/T"** *template_name* **"**</span><span class="sxs-lookup"><span data-stu-id="2cda3-133">**/T"** *template_name* **"**</span></span>  
 <span data-ttu-id="2cda3-134">Specifica il modello che verrà caricato per configurare la traccia.</span><span class="sxs-lookup"><span data-stu-id="2cda3-134">Specifies the template that will be loaded to configure the trace.</span></span> <span data-ttu-id="2cda3-135">È necessario racchiudere il nome del modello tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="2cda3-135">The template name must be in quotes.</span></span> <span data-ttu-id="2cda3-136">Il nome del modello deve trovarsi nella directory dei modelli di sistema oppure in quella dei modelli utente.</span><span class="sxs-lookup"><span data-stu-id="2cda3-136">The template name must be in either the system template directory or the user template directory.</span></span> <span data-ttu-id="2cda3-137">Se in entrambe le directory esistono due modelli con lo stesso nome, verrà caricato il modello incluso nella directory di sistema.</span><span class="sxs-lookup"><span data-stu-id="2cda3-137">If two templates with the same name exist in both directories, the template from the system directory will be loaded.</span></span> <span data-ttu-id="2cda3-138">Se non esiste alcun modello con il nome specificato, verrà caricato il modello standard.</span><span class="sxs-lookup"><span data-stu-id="2cda3-138">If no template with the specified name exists, the standard template will be loaded.</span></span> <span data-ttu-id="2cda3-139">Si noti che l'estensione di file tdf del modello non dovrà essere specificata come parte del *template_name*.</span><span class="sxs-lookup"><span data-stu-id="2cda3-139">Note that the file extension for the template (.tdf) should not be specified as part of the *template_name*.</span></span> <span data-ttu-id="2cda3-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2cda3-140">For example:</span></span>  
  
```  
/T "standard"  
```  
  
 <span data-ttu-id="2cda3-141">**/F"** *filename* **"**</span><span class="sxs-lookup"><span data-stu-id="2cda3-141">**/F"** *filename* **"**</span></span>  
 <span data-ttu-id="2cda3-142">Specifica il percorso e il nome file di un file di traccia da caricare all'avvio di SQL Profiler.</span><span class="sxs-lookup"><span data-stu-id="2cda3-142">Specifies the path and filename of a trace file to load when profiler is launched.</span></span> <span data-ttu-id="2cda3-143">È necessario racchiudere l'intero percorso e il nome file tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="2cda3-143">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="2cda3-144">Questa opzione non può essere usata in combinazione con **/O**.</span><span class="sxs-lookup"><span data-stu-id="2cda3-144">This option cannot be used with **/O**.</span></span>  
  
 <span data-ttu-id="2cda3-145">**/O "** *filename*  **"**</span><span class="sxs-lookup"><span data-stu-id="2cda3-145">**/O "** *filename*  **"**</span></span>  
 <span data-ttu-id="2cda3-146">Specifica il percorso e il nome file di un file nel quale verranno scritti i risultati della traccia.</span><span class="sxs-lookup"><span data-stu-id="2cda3-146">Specifies the path and filename of a file to which trace results should be written.</span></span> <span data-ttu-id="2cda3-147">È necessario racchiudere l'intero percorso e il nome file tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="2cda3-147">The entire path and filename must be in quotes.</span></span> <span data-ttu-id="2cda3-148">Questa opzione non può essere usata in combinazione con **/F**.</span><span class="sxs-lookup"><span data-stu-id="2cda3-148">This option cannot be used with **/F.**</span></span>  
  
 <span data-ttu-id="2cda3-149">**/L** *locale_ID*</span><span class="sxs-lookup"><span data-stu-id="2cda3-149">**/L** *locale_ID*</span></span>  
 <span data-ttu-id="2cda3-150">Non disponibile.</span><span class="sxs-lookup"><span data-stu-id="2cda3-150">Not available.</span></span>  
  
 <span data-ttu-id="2cda3-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span><span class="sxs-lookup"><span data-stu-id="2cda3-151">**/M "** *MM-DD-YY hh:mm:ss* **"**</span></span>  
 <span data-ttu-id="2cda3-152">Specifica la data e l'ora in cui verrà arrestata la traccia.</span><span class="sxs-lookup"><span data-stu-id="2cda3-152">Specifies the date and time for the trace to stop.</span></span> <span data-ttu-id="2cda3-153">È necessario racchiudere l'ora di arresto tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="2cda3-153">The stop time must be in quotes.</span></span> <span data-ttu-id="2cda3-154">Specificare l'ora di arresto in base ai parametri descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2cda3-154">Specify the stop time according to the parameters in the table below:</span></span>  
  
|<span data-ttu-id="2cda3-155">Parametro</span><span class="sxs-lookup"><span data-stu-id="2cda3-155">Parameter</span></span>|<span data-ttu-id="2cda3-156">Definizione</span><span class="sxs-lookup"><span data-stu-id="2cda3-156">Definition</span></span>|  
|---------------|----------------|  
|<span data-ttu-id="2cda3-157">MM</span><span class="sxs-lookup"><span data-stu-id="2cda3-157">MM</span></span>|<span data-ttu-id="2cda3-158">Mese nel formato a 2 cifre</span><span class="sxs-lookup"><span data-stu-id="2cda3-158">Two-digit month</span></span>|  
|<span data-ttu-id="2cda3-159">GG</span><span class="sxs-lookup"><span data-stu-id="2cda3-159">DD</span></span>|<span data-ttu-id="2cda3-160">Giorno nel formato a 2 cifre</span><span class="sxs-lookup"><span data-stu-id="2cda3-160">Two-digit day</span></span>|  
|<span data-ttu-id="2cda3-161">YY</span><span class="sxs-lookup"><span data-stu-id="2cda3-161">YY</span></span>|<span data-ttu-id="2cda3-162">Anno nel formato a 2 cifre</span><span class="sxs-lookup"><span data-stu-id="2cda3-162">Two-digit year</span></span>|  
|<span data-ttu-id="2cda3-163">hh</span><span class="sxs-lookup"><span data-stu-id="2cda3-163">hh</span></span>|<span data-ttu-id="2cda3-164">Ora a 2 cifre nel formato a 24 ore</span><span class="sxs-lookup"><span data-stu-id="2cda3-164">Two-digit hour on a 24-hour clock</span></span>|  
|<span data-ttu-id="2cda3-165">MM</span><span class="sxs-lookup"><span data-stu-id="2cda3-165">mm</span></span>|<span data-ttu-id="2cda3-166">Minuti nel formato a 2 cifre</span><span class="sxs-lookup"><span data-stu-id="2cda3-166">Two-digit minute</span></span>|  
|<span data-ttu-id="2cda3-167">ss</span><span class="sxs-lookup"><span data-stu-id="2cda3-167">ss</span></span>|<span data-ttu-id="2cda3-168">Secondi nel formato a 2 cifre</span><span class="sxs-lookup"><span data-stu-id="2cda3-168">Two-digit second</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="2cda3-169">Il formato "MM-DD-YY hh:mm:ss" può essere utilizzato solo se l'opzione **Visualizza valori di data e ora in base alle impostazioni internazionali** è abilitata in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cda3-169">The "MM-DD-YY hh:mm:ss" format can only be used if the **Use regional settings to display date and time values** option is enabled in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="2cda3-170">Se questa opzione non è abilitata, è necessario utilizzare il formato di data e ora "YYYY-MM-DD hh:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="2cda3-170">If this option is not enabled, you must use the "YYYY-MM-DD hh:mm:ss" date and time format.</span></span>  
  
 <span data-ttu-id="2cda3-171">**/R**</span><span class="sxs-lookup"><span data-stu-id="2cda3-171">**/R**</span></span>  
 <span data-ttu-id="2cda3-172">Abilita il rollover del file di traccia.</span><span class="sxs-lookup"><span data-stu-id="2cda3-172">Enables trace file rollover.</span></span>  
  
 <span data-ttu-id="2cda3-173">**/Z**  *file_size*</span><span class="sxs-lookup"><span data-stu-id="2cda3-173">**/Z**  *file_size*</span></span>  
 <span data-ttu-id="2cda3-174">Specifica le dimensioni del file di traccia espresse in megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="2cda3-174">Specifies the size of the trace file in megabytes (MB).</span></span> <span data-ttu-id="2cda3-175">Le dimensioni predefinite sono pari a 5 MB.</span><span class="sxs-lookup"><span data-stu-id="2cda3-175">The default size is 5 MB.</span></span> <span data-ttu-id="2cda3-176">Se si abilita il rollover, a tutti i file di rollover verrà applicato il valore limite specificato in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2cda3-176">If rollover is enabled, all rollover files will be limited to the value specified in this argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cda3-177">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2cda3-177">Remarks</span></span>  
 <span data-ttu-id="2cda3-178">Per avviare la traccia con un modello specifico, usare contemporaneamente le opzioni **/S** e **/T** .</span><span class="sxs-lookup"><span data-stu-id="2cda3-178">To start a trace with a specific template, use the **/S** and **/T** options together.</span></span> <span data-ttu-id="2cda3-179">Per avviare una traccia utilizzando il modello Standard in MyServer\MyInstance, ad esempio, al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2cda3-179">For example, to start a trace using the Standard template on MyServer\MyInstance, enter the following at the command prompt:</span></span>  
  
```  
profiler /S MyServer\MyInstance /T "Standard"  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cda3-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cda3-180">See Also</span></span>  
 [<span data-ttu-id="2cda3-181">Guida di riferimento alle utilità del prompt dei comandi &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2cda3-181">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](command-prompt-utility-reference-database-engine.md)  
  
  
