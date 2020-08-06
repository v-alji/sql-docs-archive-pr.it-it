---
title: Utilità Ssms | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], opening
- command prompt utilities [SQL Server], sqlwb
- sqlwb utility
- Management Studio command line
- opening SQL Server Management Studio
ms.assetid: aafda520-9e2a-4e1e-b936-1b165f1684e8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0cfc9469e49e6ce3839d02a61477b8957fbc13e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637023"
---
# <a name="ssms-utility"></a><span data-ttu-id="96b0f-102">Utilità Ssms</span><span class="sxs-lookup"><span data-stu-id="96b0f-102">Ssms Utility</span></span>
  <span data-ttu-id="96b0f-103">L'utilità **Ssms** apre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96b0f-103">The **Ssms**utility opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="96b0f-104">Se specificato, **Ssms** anche una connessione a un server e apre query, script, file, progetti e soluzioni.</span><span class="sxs-lookup"><span data-stu-id="96b0f-104">If specified, **Ssms** also establishes a connection to a server, and opens queries, scripts, files, projects, and solutions.</span></span>  
  
 <span data-ttu-id="96b0f-105">È possibile specificare file che includono query, progetti o soluzioni.</span><span class="sxs-lookup"><span data-stu-id="96b0f-105">You can specify files that contain queries, projects, or solutions.</span></span> <span data-ttu-id="96b0f-106">I file contenenti query vengono automaticamente connessi a un server se si specificano le informazioni di connessione e il tipo di file è associato al tipo corrispondente di server.</span><span class="sxs-lookup"><span data-stu-id="96b0f-106">Files that contain queries are automatically connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="96b0f-107">Ad esempio, i file sql apriranno una finestra Editor di query SQL in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], mentre i file mdx apriranno una finestra Editor di query MDX in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96b0f-107">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="96b0f-108">**Soluzioni e progetti di SQL Server** si aprirà in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96b0f-108">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96b0f-109">L'utilità **Ssms** non esegue query.</span><span class="sxs-lookup"><span data-stu-id="96b0f-109">The **Ssms** utility does not run queries.</span></span> <span data-ttu-id="96b0f-110">Per eseguire query dalla riga di comando, usare l'utilità **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="96b0f-110">To run queries from the command line, use the **sqlcmd** utility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96b0f-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96b0f-111">Syntax</span></span>  
  
```  
  
      Ssms  
    [scriptfile] [projectfile] [solutionfile]  
    [-Sservername] [-ddatabasename] [-Uusername] [-Ppassword]   
    [-E] [-nosplash] [-log[filename]?] [-?]  
```  
  
## <a name="arguments"></a><span data-ttu-id="96b0f-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="96b0f-112">Arguments</span></span>  
 <span data-ttu-id="96b0f-113">*scriptfile*</span><span class="sxs-lookup"><span data-stu-id="96b0f-113">*scriptfile*</span></span>  
 <span data-ttu-id="96b0f-114">Specifica uno o più file script da aprire.</span><span class="sxs-lookup"><span data-stu-id="96b0f-114">Specifies one or more script files to open.</span></span> <span data-ttu-id="96b0f-115">Il parametro deve includere il percorso completo dei file.</span><span class="sxs-lookup"><span data-stu-id="96b0f-115">The parameter must contain the full path to the files.</span></span>  
  
 <span data-ttu-id="96b0f-116">*projectfile*</span><span class="sxs-lookup"><span data-stu-id="96b0f-116">*projectfile*</span></span>  
 <span data-ttu-id="96b0f-117">Specifica un progetto script da aprire.</span><span class="sxs-lookup"><span data-stu-id="96b0f-117">Specifies a script project to open.</span></span> <span data-ttu-id="96b0f-118">Il parametro deve includere il percorso completo del file del progetto script.</span><span class="sxs-lookup"><span data-stu-id="96b0f-118">The parameter must contain the full path to the script project file.</span></span>  
  
 <span data-ttu-id="96b0f-119">*solutionfile*</span><span class="sxs-lookup"><span data-stu-id="96b0f-119">*solutionfile*</span></span>  
 <span data-ttu-id="96b0f-120">Specifica una soluzione da aprire.</span><span class="sxs-lookup"><span data-stu-id="96b0f-120">Specifies a solution to open.</span></span> <span data-ttu-id="96b0f-121">Il parametro deve includere il percorso completo del file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="96b0f-121">The parameter must contain the full path to the solution file.</span></span>  
  
 <span data-ttu-id="96b0f-122">[**-S** _nomeserver_]</span><span class="sxs-lookup"><span data-stu-id="96b0f-122">[**-S** _servername_]</span></span>  
 <span data-ttu-id="96b0f-123">Nome server</span><span class="sxs-lookup"><span data-stu-id="96b0f-123">Server name</span></span>  
  
 <span data-ttu-id="96b0f-124">[**-d** _DatabaseName_]</span><span class="sxs-lookup"><span data-stu-id="96b0f-124">[**-d** _databasename_]</span></span>  
 <span data-ttu-id="96b0f-125">Nome database</span><span class="sxs-lookup"><span data-stu-id="96b0f-125">Database name</span></span>  
  
 <span data-ttu-id="96b0f-126">[**-U** _username_]</span><span class="sxs-lookup"><span data-stu-id="96b0f-126">[**-U** _username_]</span></span>  
 <span data-ttu-id="96b0f-127">Nome utente utilizzato per la connessione tramite l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96b0f-127">User name when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="96b0f-128">[**-P** _password_]</span><span class="sxs-lookup"><span data-stu-id="96b0f-128">[**-P** _password_]</span></span>  
 <span data-ttu-id="96b0f-129">Password utilizzata per la connessione tramite l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96b0f-129">Password when connecting with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication</span></span>  
  
 <span data-ttu-id="96b0f-130">[**-E**]</span><span class="sxs-lookup"><span data-stu-id="96b0f-130">[**-E**]</span></span>  
 <span data-ttu-id="96b0f-131">Stabilisce la connessione utilizzando l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="96b0f-131">Connect using Windows Authentication</span></span>  
  
 <span data-ttu-id="96b0f-132">[**-nosplash**]</span><span class="sxs-lookup"><span data-stu-id="96b0f-132">[**-nosplash**]</span></span>  
 <span data-ttu-id="96b0f-133">Se si specifica questa opzione, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] non viene visualizzata la grafica della schermata iniziale all'apertura.</span><span class="sxs-lookup"><span data-stu-id="96b0f-133">Prevents [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from displaying the splash screen graphic while opening.</span></span> <span data-ttu-id="96b0f-134">Utilizzare questa opzione in caso di connessione al computer che esegue [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per mezzo di Servizi terminal tramite una connessione a larghezza di banda limitata.</span><span class="sxs-lookup"><span data-stu-id="96b0f-134">Use this option when connecting to the computer running [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] by means of Terminal Services over a connection with a limited bandwidth.</span></span> <span data-ttu-id="96b0f-135">Questo argomento non supporta la distinzione tra maiuscole e minuscole e può trovarsi prima o dopo altri argomenti.</span><span class="sxs-lookup"><span data-stu-id="96b0f-135">This argument is not case-sensitive and may appear before or after other arguments</span></span>  
  
 <span data-ttu-id="96b0f-136">[**-log**_[nomefile]?_]</span><span class="sxs-lookup"><span data-stu-id="96b0f-136">[**-log**_[filename]?_]</span></span>  
 <span data-ttu-id="96b0f-137">L'attività [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] viene registrata nel file specificato per la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="96b0f-137">Logs [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] activity to the specified file for troubleshooting</span></span>  
  
 <span data-ttu-id="96b0f-138">[**-?**]</span><span class="sxs-lookup"><span data-stu-id="96b0f-138">[**-?**]</span></span>  
 <span data-ttu-id="96b0f-139">Visualizza informazioni della Guida relative alla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="96b0f-139">Displays command line help</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96b0f-140">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="96b0f-140">Remarks</span></span>  
 <span data-ttu-id="96b0f-141">Tutte le opzioni sono facoltative e devono essere separate da uno spazio, a differenza dei file che devono essere separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="96b0f-141">All of the switches are optional and separated by a space except files which are separated by commas.</span></span> <span data-ttu-id="96b0f-142">Se non viene specificata alcuna opzione, **Ssms** apre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] in base alle impostazioni definite in **Opzioni** nel menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="96b0f-142">If you do not specify any switches, **Ssms** opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as specified in the **Options** settings on the **Tools** menu.</span></span> <span data-ttu-id="96b0f-143">Ad esempio, se l'opzione **All'avvio** della pagina **Ambiente/Generale** specifica **Apri nuova finestra Query**, **Ssms** viene aperto con un editor di query vuoto.</span><span class="sxs-lookup"><span data-stu-id="96b0f-143">For example, if the **Environment/General** page **At startup** option specifies **Open new query window**, **Ssms** will open with a blank Query Editor.</span></span>  
  
 <span data-ttu-id="96b0f-144">L'opzione **-log** deve essere visualizzata alla fine della riga di comando, dopo tutte le altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="96b0f-144">The **-log** switch must appear at the end of the command line, after all other switches.</span></span> <span data-ttu-id="96b0f-145">L'argomento del nome del file è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="96b0f-145">The filename argument is optional.</span></span> <span data-ttu-id="96b0f-146">Se il nome del file è specificato e il file non esiste, il file viene creato.</span><span class="sxs-lookup"><span data-stu-id="96b0f-146">If a filename is specified, and the file does not exist, the file is created.</span></span> <span data-ttu-id="96b0f-147">Se non è possibile creare il file, ad esempio a causa dell'accesso in scrittura insufficiente, il log viene invece scritto nella posizione APPDATA non localizzata (vedere di seguito).</span><span class="sxs-lookup"><span data-stu-id="96b0f-147">If the file cannot be created - for example, due to insufficient write access, the log is written to the nonlocalized APPDATA location instead (See below).</span></span> <span data-ttu-id="96b0f-148">Se l'argomento del nome del file non viene specificato, i file vengono scritti nella cartella di dati dell'applicazione non localizzata dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="96b0f-148">If the filename argument is not specified, two files are written to the current user's nonlocalized application data folder.</span></span> <span data-ttu-id="96b0f-149">La cartella di dati dell'applicazione non localizzata per SQL Server può essere individuata tramite la variabile di ambiente APPDATA.</span><span class="sxs-lookup"><span data-stu-id="96b0f-149">The nonlocalized application data folder for SQL Server can be found from the APPDATA environment variable.</span></span> <span data-ttu-id="96b0f-150">Ad esempio, per SQL Server 2012, la cartella è \<system drive> : \Users \\<nomeutente \> \AppData\Roaming\Microsoft\AppEnv\10.0 \\ .</span><span class="sxs-lookup"><span data-stu-id="96b0f-150">For example, for SQL Server 2012, the folder is \<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\\.</span></span> <span data-ttu-id="96b0f-151">Per impostazione predefinita, i due file sono denominati ActivityLog.xml e ActivityLog.xsl.</span><span class="sxs-lookup"><span data-stu-id="96b0f-151">The two files are, by default, named ActivityLog.xml and ActivityLog.xsl.</span></span> <span data-ttu-id="96b0f-152">Nel primo sono contenuti i dati del log attività e il secondo è un foglio di stile XML tramite cui risulta più semplice la visualizzazione del file XML.</span><span class="sxs-lookup"><span data-stu-id="96b0f-152">The former contains the activity log data and the latter is an XML style sheet which provides a more convenient way to view the XML file.</span></span> <span data-ttu-id="96b0f-153">Utilizzare la procedura seguente per visualizzare il file di log nel Visualizzatore XML predefinito, ad esempio Internet Explorer. fare clic sul pulsante Start, scegliere Esegui... ", quindi digitare" \<system drive> : \Users \\<username \>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml "nel campo fornito, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="96b0f-153">Use the following steps to view the log file in your default XML viewer, like Internet Explorer:  Click Start, then click Run...", then type "\<system drive>:\Users\\<username\>\AppData\Roaming\Microsoft\AppEnv\10.0\ActivityLog.xml" into the field provided, and then press Enter.</span></span>  
  
 <span data-ttu-id="96b0f-154">Verrà richiesto di connettere i file contenenti query a un server se si specificano le informazioni di connessione e il tipo di file è associato al tipo corrispondente di server.</span><span class="sxs-lookup"><span data-stu-id="96b0f-154">Files that contain queries will prompt to be connected to a server if connection information is provided and the file type is associated with that type of server.</span></span> <span data-ttu-id="96b0f-155">Ad esempio, i file sql apriranno una finestra Editor di query SQL in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], mentre i file mdx apriranno una finestra Editor di query MDX in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96b0f-155">For instance, .sql files will open a SQL Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and .mdx files will open an MDX Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="96b0f-156">**Soluzioni e progetti di SQL Server** si aprirà in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96b0f-156">**SQL Server Solutions and Projects** will open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="96b0f-157">Nella tabella seguente viene eseguito il mapping dei tipi di server alle estensioni di file.</span><span class="sxs-lookup"><span data-stu-id="96b0f-157">The following table maps server types to file extensions.</span></span>  
  
|<span data-ttu-id="96b0f-158">Tipo di server</span><span class="sxs-lookup"><span data-stu-id="96b0f-158">Server type</span></span>|<span data-ttu-id="96b0f-159">Estensione</span><span class="sxs-lookup"><span data-stu-id="96b0f-159">Extension</span></span>|  
|-----------------|---------------|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]|<span data-ttu-id="96b0f-160">sql</span><span class="sxs-lookup"><span data-stu-id="96b0f-160">.sql</span></span>|  
|<span data-ttu-id="96b0f-161">SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="96b0f-161">SQL Server Analysis Services</span></span>|<span data-ttu-id="96b0f-162">mdx</span><span class="sxs-lookup"><span data-stu-id="96b0f-162">.mdx</span></span><br /><br /> <span data-ttu-id="96b0f-163">xmla</span><span class="sxs-lookup"><span data-stu-id="96b0f-163">.xmla</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="96b0f-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="96b0f-164">Examples</span></span>  
 <span data-ttu-id="96b0f-165">Lo script seguente apre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] da un prompt dei comandi in base alle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="96b0f-165">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt with the default settings:</span></span>  
  
```  
Ssms  
  
```  
  
 <span data-ttu-id="96b0f-166">Lo script seguente apre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] da un prompt dei comandi utilizzando l'autenticazione di Windows, con l'editor del codice impostato sul server `ACCTG and the database AdventureWorks2012,` senza visualizzare la schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="96b0f-166">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, with Windows Authentication, with the Code Editor set to the server `ACCTG and the database AdventureWorks2012,` without showing the splash screen:</span></span>  
  
```  
Ssms -E -S ACCTG -d AdventureWorks2012 -nosplash  
  
```  
  
 <span data-ttu-id="96b0f-167">Lo script seguente apre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] da un prompt dei comandi e quindi apre lo script MonthEndQuery.</span><span class="sxs-lookup"><span data-stu-id="96b0f-167">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthEndQuery script.</span></span>  
  
```  
Ssms "C:\Documents and Settings\username\My Documents\SQL Server Management Studio Projects\FinanceScripts\FinanceScripts\MonthEndQuery.sql"  
  
```  
  
 <span data-ttu-id="96b0f-168">Lo script seguente apre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] da un prompt dei comandi e quindi apre il progetto NewReportsProject nel computer denominato `developer`.</span><span class="sxs-lookup"><span data-stu-id="96b0f-168">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the NewReportsProject project on the computer named `developer`:</span></span>  
  
```  
Ssms "\\developer\fin\ReportProj\ReportProj\NewReportProj.ssmssqlproj"  
  
```  
  
 <span data-ttu-id="96b0f-169">Lo script seguente apre [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] da un prompt dei comandi e quindi apre la soluzione MonthlyReports.</span><span class="sxs-lookup"><span data-stu-id="96b0f-169">The following script opens [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from a command prompt, and opens the MonthlyReports solution:</span></span>  
  
```  
Ssms "C:\solutionsfolder\ReportProj\MonthlyReports.ssmssln"  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="96b0f-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96b0f-170">See Also</span></span>  
 [<span data-ttu-id="96b0f-171">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96b0f-171">Use SQL Server Management Studio</span></span>](../database-engine/use-sql-server-management-studio.md)  
  
  
