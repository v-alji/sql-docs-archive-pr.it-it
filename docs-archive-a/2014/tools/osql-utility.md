---
title: Utilità osql | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- statements [SQL Server], command prompt
- QUIT command
- Transact-SQL statements, command prompt
- EXIT command
- operating systems [SQL Server], commands
- osql utility [SQL Server]
- stored procedures [SQL Server], command prompt
- scripts [SQL Server], command prompt
- RESET command
- GO command
- command prompt utilities [SQL Server], osql
- CTRL+C command
ms.assetid: cf530d9e-0609-4528-8975-ab8e08e40b9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 95782afe0de8567781316e3478d04a090f968ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711296"
---
# <a name="osql-utility"></a><span data-ttu-id="2f028-102">Utilità osql</span><span class="sxs-lookup"><span data-stu-id="2f028-102">osql Utility</span></span>
  <span data-ttu-id="2f028-103">L'utilità **osql** consente di immettere istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] , procedure di sistema e file script.</span><span class="sxs-lookup"><span data-stu-id="2f028-103">The **osql** utility allows you to enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements, system procedures, and script files.</span></span> <span data-ttu-id="2f028-104">Questa utilità comunica con il server tramite ODBC.</span><span class="sxs-lookup"><span data-stu-id="2f028-104">This utility uses ODBC to communicate with the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f028-105">Questa funzionalità verrà rimossa nelle versioni future di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f028-105">This feature will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f028-106">Evitare pertanto di utilizzarla in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni che attualmente utilizzano questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2f028-106">Avoid using this feature in new development work, and plan to modify applications that currently use the feature.</span></span> <span data-ttu-id="2f028-107">In alternativa, usare **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="2f028-107">Use **sqlcmd** instead.</span></span> <span data-ttu-id="2f028-108">Per altre informazioni, vedere [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2f028-108">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f028-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f028-109">Syntax</span></span>  
  
```  
  
      osql  
[-?] |  
[-L] |  
[  
  {  
     {-Ulogin_id [-Ppassword]} | -E }  
     [-Sserver_name[\instance_name]] [-Hwksta_name] [-ddb_name]  
     [-ltime_out] [-ttime_out] [-hheaders]  
     [-scol_separator] [-wcolumn_width] [-apacket_size]  
     [-e] [-I] [-D data_source_name]  
     [-ccmd_end] [-q "query"] [-Q"query"]  
     [-n] [-merror_level] [-r {0 | 1}]  
     [-iinput_file] [-ooutput_file] [-p]  
     [-b] [-u] [-R] [-O]  
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f028-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2f028-110">Arguments</span></span>  
 <span data-ttu-id="2f028-111">**-?**</span><span class="sxs-lookup"><span data-stu-id="2f028-111">**-?**</span></span>  
 <span data-ttu-id="2f028-112">Visualizza il riepilogo della sintassi delle opzioni di **osql** .</span><span class="sxs-lookup"><span data-stu-id="2f028-112">Displays the syntax summary of **osql** switches.</span></span>  
  
 <span data-ttu-id="2f028-113">**-L**</span><span class="sxs-lookup"><span data-stu-id="2f028-113">**-L**</span></span>  
 <span data-ttu-id="2f028-114">Elenca i server configurati localmente e i nomi dei server che trasmettono in rete tramite broadcast.</span><span class="sxs-lookup"><span data-stu-id="2f028-114">Lists the locally configured servers and the names of the servers broadcasting on the network.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-115">A causa della natura delle trasmissioni in rete, è possibile che **osql** non riceva una risposta tempestiva da tutti i server</span><span class="sxs-lookup"><span data-stu-id="2f028-115">Due to the nature of broadcasting on networks, **osql** may not receive a timely response from all servers.</span></span> <span data-ttu-id="2f028-116">e pertanto che l'elenco di server restituito sia diverso per ogni chiamata di questa opzione.</span><span class="sxs-lookup"><span data-stu-id="2f028-116">Therefore the list of servers returned may vary for each invocation of this option.</span></span>  
  
 <span data-ttu-id="2f028-117">**-U** _login_id_</span><span class="sxs-lookup"><span data-stu-id="2f028-117">**-U** _login_id_</span></span>  
 <span data-ttu-id="2f028-118">ID di accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2f028-118">Is the user login ID.</span></span> <span data-ttu-id="2f028-119">Negli ID di accesso viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="2f028-119">Login IDs are case-sensitive.</span></span>  
  
 <span data-ttu-id="2f028-120">**-P** _password_</span><span class="sxs-lookup"><span data-stu-id="2f028-120">**-P** _password_</span></span>  
 <span data-ttu-id="2f028-121">Password specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2f028-121">Is a user-specified password.</span></span> <span data-ttu-id="2f028-122">Se si omette l'opzione **-P** , **osql** richiede una password.</span><span class="sxs-lookup"><span data-stu-id="2f028-122">If the **-P** option is not used, **osql** prompts for a password.</span></span> <span data-ttu-id="2f028-123">Se l'opzione **-P** viene specificata alla fine del prompt dei comandi senza indicare una password, **osql** usa la password predefinita (NULL).</span><span class="sxs-lookup"><span data-stu-id="2f028-123">If the **-P** option is used at the end of the command prompt without any password, **osql** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f028-124">Non usare una password vuota.</span><span class="sxs-lookup"><span data-stu-id="2f028-124">Do not use a blank password.</span></span> <span data-ttu-id="2f028-125">Usare una password complessa.</span><span class="sxs-lookup"><span data-stu-id="2f028-125">Use a strong password.</span></span> <span data-ttu-id="2f028-126">Per altre informazioni, vedere [Strong Passwords](../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="2f028-126">For more information, see [Strong Passwords](../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="2f028-127">Per le password viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="2f028-127">Passwords are case-sensitive.</span></span>  
  
 <span data-ttu-id="2f028-128">La variabile di ambiente OSQLPASSWORD consente di impostare una password predefinita per la sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="2f028-128">The OSQLPASSWORD environment variable allows you to set a default password for the current session.</span></span> <span data-ttu-id="2f028-129">Non è pertanto necessario specificare una password a livello di codice nei file batch.</span><span class="sxs-lookup"><span data-stu-id="2f028-129">Therefore, you do not have to hard code a password into batch files.</span></span>  
  
 <span data-ttu-id="2f028-130">Se si specifica l'opzione **-P** e si omette la password, **osql** verifica innanzitutto la variabile OSQLPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="2f028-130">If you do not specify a password with the **-P** option, **osql** first checks for the OSQLPASSWORD variable.</span></span> <span data-ttu-id="2f028-131">Se non viene impostato alcun valore, **osql** usa la password predefinita NULL.</span><span class="sxs-lookup"><span data-stu-id="2f028-131">If no value is set, **osql** uses the default password, NULL.</span></span> <span data-ttu-id="2f028-132">Nell'esempio seguente viene impostata la variabile OSQLPASSWORD al prompt dei comandi e quindi si accede all'utilità **osql** :</span><span class="sxs-lookup"><span data-stu-id="2f028-132">The following example sets the OSQLPASSWORD variable at a command prompt and then accesses the **osql** utility:</span></span>  
  
```  
C:\>SET OSQLPASSWORD=abracadabra  
C:\>osql   
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f028-133">Per nascondere la password, non specificare l'opzione **-P** in combinazione con l'opzione **-U** .</span><span class="sxs-lookup"><span data-stu-id="2f028-133">To mask your password, do not specify the **-P** option along with the **-U** option.</span></span> <span data-ttu-id="2f028-134">Dopo aver specificato il comando **osql** con **-U** e altre opzioni (non specificare **-P**), premere Invio. Il comando **osql** richiederà l'immissione di una password.</span><span class="sxs-lookup"><span data-stu-id="2f028-134">Instead, after specifying **osql** along with the **-U** option and other switches (do not specify **-P**), press ENTER, and **osql** will prompt you for a password.</span></span> <span data-ttu-id="2f028-135">Questo metodo garantisce che la password venga nascosta durante l'immissione.</span><span class="sxs-lookup"><span data-stu-id="2f028-135">This method ensures that your password will be masked when it is entered.</span></span>  
  
 <span data-ttu-id="2f028-136">**-E**</span><span class="sxs-lookup"><span data-stu-id="2f028-136">**-E**</span></span>  
 <span data-ttu-id="2f028-137">Utilizza una connessione trusted anziché richiedere una password.</span><span class="sxs-lookup"><span data-stu-id="2f028-137">Uses a trusted connection instead of requesting a password.</span></span>  
  
 <span data-ttu-id="2f028-138">**-S** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="2f028-138">**-S** _server_name_[ **\\**_instance_name_]</span></span>  
 <span data-ttu-id="2f028-139">Specifica l'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alla quale connettersi.</span><span class="sxs-lookup"><span data-stu-id="2f028-139">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to.</span></span> <span data-ttu-id="2f028-140">Specificare il *nome_server* per connettersi all'istanza predefinita di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] su tale server.</span><span class="sxs-lookup"><span data-stu-id="2f028-140">Specify *server_name* to connect to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="2f028-141">Specificare _server_name_ **\\** _instance_name_ per connettersi a un'istanza denominata di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in tale server.</span><span class="sxs-lookup"><span data-stu-id="2f028-141">Specify _server_name_**\\**_instance_name_ to connect to a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="2f028-142">Se non si specifica alcun server, **osql** si connette all'istanza predefinita di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="2f028-142">If no server is specified, **osql** connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="2f028-143">Questa opzione è obbligatoria per l'esecuzione di **osql** da un computer remoto sulla rete.</span><span class="sxs-lookup"><span data-stu-id="2f028-143">This option is required when executing **osql** from a remote computer on the network.</span></span>  
  
 <span data-ttu-id="2f028-144">**-H** _wksta_name_</span><span class="sxs-lookup"><span data-stu-id="2f028-144">**-H** _wksta_name_</span></span>  
 <span data-ttu-id="2f028-145">Nome della workstation.</span><span class="sxs-lookup"><span data-stu-id="2f028-145">Is a workstation name.</span></span> <span data-ttu-id="2f028-146">Il nome della workstation viene archiviato in **sysprocesses.hostname** ed è visualizzato tramite **sp_who**.</span><span class="sxs-lookup"><span data-stu-id="2f028-146">The workstation name is stored in **sysprocesses.hostname** and is displayed by **sp_who**.</span></span> <span data-ttu-id="2f028-147">Se omesso, viene utilizzato il nome del computer corrente.</span><span class="sxs-lookup"><span data-stu-id="2f028-147">If this option is not specified, the current computer name is assumed.</span></span>  
  
 <span data-ttu-id="2f028-148">**-d** _db_name_</span><span class="sxs-lookup"><span data-stu-id="2f028-148">**-d** _db_name_</span></span>  
 <span data-ttu-id="2f028-149">Esegue un'istruzione USE *db_name* all'avvio di **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-149">Issues a USE *db_name* statement when **osql**is started.</span></span>  
  
 <span data-ttu-id="2f028-150">**-l** _time_out_</span><span class="sxs-lookup"><span data-stu-id="2f028-150">**-l** _time_out_</span></span>  
 <span data-ttu-id="2f028-151">Specifica il numero di secondi prima del timeout di accesso a **osql** . Il valore predefinito per il timeout di accesso a **osql** è otto secondi.</span><span class="sxs-lookup"><span data-stu-id="2f028-151">Specifies the number of seconds before an **osql** login times out. The default time-out for login to **osql** is eight seconds.</span></span>  
  
 <span data-ttu-id="2f028-152">**-t** _time_out_</span><span class="sxs-lookup"><span data-stu-id="2f028-152">**-t** _time_out_</span></span>  
 <span data-ttu-id="2f028-153">Specifica il numero di secondi prima del timeout del comando. Se per *time_out* non viene specificato alcun valore, ai comandi non viene associato alcun timeout.</span><span class="sxs-lookup"><span data-stu-id="2f028-153">Specifies the number of seconds before a command times out. If a *time_out* value is not specified, commands do not time out.</span></span>  
  
 <span data-ttu-id="2f028-154">**-h** _headers_</span><span class="sxs-lookup"><span data-stu-id="2f028-154">**-h** _headers_</span></span>  
 <span data-ttu-id="2f028-155">Specifica il numero di righe da stampare tra le intestazioni delle colonne.</span><span class="sxs-lookup"><span data-stu-id="2f028-155">Specifies the number of rows to print between column headings.</span></span> <span data-ttu-id="2f028-156">Per impostazione predefinita, le intestazioni vengono stampate una volta per ogni set di risultati delle query.</span><span class="sxs-lookup"><span data-stu-id="2f028-156">The default is to print headings one time for each set of query results.</span></span> <span data-ttu-id="2f028-157">Utilizzare -1 per non stampare alcuna intestazione.</span><span class="sxs-lookup"><span data-stu-id="2f028-157">Use -1 to specify that no headers will be printed.</span></span> <span data-ttu-id="2f028-158">Se si usa -1, non inserire spazi tra il parametro e l'impostazione ( **-h-1**e non **-h -1**).</span><span class="sxs-lookup"><span data-stu-id="2f028-158">If -1 is used, there must be no space between the parameter and the setting (**-h-1**, not **-h -1**).</span></span>  
  
 <span data-ttu-id="2f028-159">**-s** _col_separator_</span><span class="sxs-lookup"><span data-stu-id="2f028-159">**-s** _col_separator_</span></span>  
 <span data-ttu-id="2f028-160">Specifica il carattere separatore di colonne che, per impostazione predefinita, è uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="2f028-160">Specifies the column-separator character, which is a blank space by default.</span></span> <span data-ttu-id="2f028-161">Per utilizzare caratteri con un significato speciale per il sistema operativo (ad esempio, |; & \< > ), racchiudere il carattere tra virgolette doppie (").</span><span class="sxs-lookup"><span data-stu-id="2f028-161">To use characters that have special meaning to the operating system (for example, | ; & \< >), enclose the character in double quotation marks (").</span></span>  
  
 <span data-ttu-id="2f028-162">**-w** _column_width_</span><span class="sxs-lookup"><span data-stu-id="2f028-162">**-w** _column_width_</span></span>  
 <span data-ttu-id="2f028-163">Consente di impostare la larghezza della schermata per l'output.</span><span class="sxs-lookup"><span data-stu-id="2f028-163">Allows the user to set the screen width for output.</span></span> <span data-ttu-id="2f028-164">Il valore predefinito è 80 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2f028-164">The default is 80 characters.</span></span> <span data-ttu-id="2f028-165">Se una riga di output raggiunge la larghezza massima della schermata, viene suddivisa su più righe.</span><span class="sxs-lookup"><span data-stu-id="2f028-165">When an output line has reached its maximum screen width, it is broken into multiple lines.</span></span>  
  
 <span data-ttu-id="2f028-166">**-a** _packet_size_</span><span class="sxs-lookup"><span data-stu-id="2f028-166">**-a** _packet_size_</span></span>  
 <span data-ttu-id="2f028-167">Consente di richiedere un pacchetto di dimensioni diverse.</span><span class="sxs-lookup"><span data-stu-id="2f028-167">Allows you to request a different-sized packet.</span></span> <span data-ttu-id="2f028-168">I valori validi per *packet_size* sono compresi tra 512 e 65535.</span><span class="sxs-lookup"><span data-stu-id="2f028-168">The valid values for *packet_size* are 512 through 65535.</span></span> <span data-ttu-id="2f028-169">Il valore predefinito per **osql** è il valore predefinito del server.</span><span class="sxs-lookup"><span data-stu-id="2f028-169">The default value **osql** is the server default.</span></span> <span data-ttu-id="2f028-170">Aumentando le dimensioni del pacchetto si possono ottenere miglioramenti delle prestazioni di esecuzione di script di grandi dimensioni, che includono numerose istruzioni SQL tra i comandi GO.</span><span class="sxs-lookup"><span data-stu-id="2f028-170">Increased packet size can enhance performance on larger script execution where the amount of SQL statements between GO commands is substantial.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="2f028-171">indicano che, per le operazioni di copia bulk, l'impostazione che garantisce le prestazioni più veloci è in genere 8.192.</span><span class="sxs-lookup"><span data-stu-id="2f028-171">testing indicates that 8192 is typically the fastest setting for bulk copy operations.</span></span> <span data-ttu-id="2f028-172">È possibile richiedere una dimensione maggiore del pacchetto, ma se questa non è disponibile **osql** usa il valore predefinito del server.</span><span class="sxs-lookup"><span data-stu-id="2f028-172">A larger packet size can be requested, but **osql** defaults to the server default if the request cannot be granted.</span></span>  
  
 <span data-ttu-id="2f028-173">**-e**</span><span class="sxs-lookup"><span data-stu-id="2f028-173">**-e**</span></span>  
 <span data-ttu-id="2f028-174">Esegue l'eco dell'input.</span><span class="sxs-lookup"><span data-stu-id="2f028-174">Echoes input.</span></span>  
  
 <span data-ttu-id="2f028-175">**-I**</span><span class="sxs-lookup"><span data-stu-id="2f028-175">**-I**</span></span>  
 <span data-ttu-id="2f028-176">Attiva l'opzione di connessione QUOTED_IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="2f028-176">Sets the QUOTED_IDENTIFIER connection option on.</span></span>  
  
 <span data-ttu-id="2f028-177">**-D** _data_source_name_</span><span class="sxs-lookup"><span data-stu-id="2f028-177">**-D** _data_source_name_</span></span>  
 <span data-ttu-id="2f028-178">Stabilisce una connessione a un'origine dei dati ODBC definita mediante il driver ODBC per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f028-178">Connects to an ODBC data source that is defined using the ODBC driver for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f028-179">La connessione **osql** usa le opzioni specificate nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="2f028-179">The **osql** connection uses the options specified in the data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-180">Tale opzione non può essere utilizzata con origini dei dati definite per altri driver.</span><span class="sxs-lookup"><span data-stu-id="2f028-180">This option does not work with data sources defined for other drivers.</span></span>  
  
 <span data-ttu-id="2f028-181">**-c** _cmd_end_</span><span class="sxs-lookup"><span data-stu-id="2f028-181">**-c** _cmd_end_</span></span>  
 <span data-ttu-id="2f028-182">Specifica il carattere di terminazione del comando.</span><span class="sxs-lookup"><span data-stu-id="2f028-182">Specifies the command terminator.</span></span> <span data-ttu-id="2f028-183">Per impostazione predefinita, i comandi vengono terminati e inviati a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tramite l'immissione di GO su una riga a sé stante.</span><span class="sxs-lookup"><span data-stu-id="2f028-183">By default, commands are terminated and sent to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by entering GO on a line by itself.</span></span> <span data-ttu-id="2f028-184">Se si reimposta il carattere di terminazione del comando, non utilizzare parole riservate di [!INCLUDE[tsql](../includes/tsql-md.md)] o caratteri con un significato speciale per il sistema operativo, indipendentemente dal fatto che siano preceduti da una barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="2f028-184">When you reset the command terminator, do not use [!INCLUDE[tsql](../includes/tsql-md.md)] reserved words or characters that have special meaning to the operating system, whether preceded by a backslash or not.</span></span>  
  
 <span data-ttu-id="2f028-185">**-q "** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="2f028-185">**-q "** _query_ **"**</span></span>  
 <span data-ttu-id="2f028-186">Esegue una query all'avvio di **osql** senza uscire da **osql** al termine della query.</span><span class="sxs-lookup"><span data-stu-id="2f028-186">Executes a query when **osql** starts, but does not exit **osql** when the query completes.</span></span> <span data-ttu-id="2f028-187">Si noti che l'istruzione della query non dovrebbe includere l'istruzione GO.</span><span class="sxs-lookup"><span data-stu-id="2f028-187">(Note that the query statement should not include GO).</span></span> <span data-ttu-id="2f028-188">Se si esegue una query da un file batch, è possibile utilizzare variabili in formato %variabile o variabili di ambiente in formato %variabile%.</span><span class="sxs-lookup"><span data-stu-id="2f028-188">If you issue a query from a batch file, use %variables, or environment %variables%.</span></span> <span data-ttu-id="2f028-189">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2f028-189">For example:</span></span>  
  
```  
SET table=sys.objects  
osql -E -q "select name, object_id from %table%"  
```  
  
 <span data-ttu-id="2f028-190">Racchiudere la query tra virgolette doppie e utilizzare le virgolette singole per altri elementi inclusi nella query.</span><span class="sxs-lookup"><span data-stu-id="2f028-190">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="2f028-191">**-Q"** _query_ **"**</span><span class="sxs-lookup"><span data-stu-id="2f028-191">**-Q"** _query_ **"**</span></span>  
 <span data-ttu-id="2f028-192">Esegue una query ed esce immediatamente da **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-192">Executes a query and immediately exits **osql**.</span></span> <span data-ttu-id="2f028-193">Racchiudere la query tra virgolette doppie e utilizzare le virgolette singole per altri elementi inclusi nella query.</span><span class="sxs-lookup"><span data-stu-id="2f028-193">Use double quotation marks around the query and single quotation marks around anything embedded in the query.</span></span>  
  
 <span data-ttu-id="2f028-194">**-n**</span><span class="sxs-lookup"><span data-stu-id="2f028-194">**-n**</span></span>  
 <span data-ttu-id="2f028-195">Rimuove la numerazione e il simbolo del prompt (>) dalle righe di input.</span><span class="sxs-lookup"><span data-stu-id="2f028-195">Removes numbering and the prompt symbol (>) from input lines.</span></span>  
  
 <span data-ttu-id="2f028-196">**-m** _error_level_</span><span class="sxs-lookup"><span data-stu-id="2f028-196">**-m** _error_level_</span></span>  
 <span data-ttu-id="2f028-197">Personalizza la visualizzazione dei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="2f028-197">Customizes the display of error messages.</span></span> <span data-ttu-id="2f028-198">Per gli errori con livello di gravità pari o superiore a quello specificato vengono visualizzati il numero, lo stato e il livello di errore del messaggio.</span><span class="sxs-lookup"><span data-stu-id="2f028-198">The message number, state, and error level are displayed for errors of the specified severity level or higher.</span></span> <span data-ttu-id="2f028-199">Per gli errori con livelli di gravità inferiori a quello specificato non viene visualizzato nulla.</span><span class="sxs-lookup"><span data-stu-id="2f028-199">Nothing is displayed for errors of levels lower than the specified level.</span></span> <span data-ttu-id="2f028-200">Usare **-1** per specificare che con i messaggi, anche quelli informativi, devono essere restituite anche tutte le rispettive intestazioni.</span><span class="sxs-lookup"><span data-stu-id="2f028-200">Use **-1** to specify that all headers are returned with messages, even informational messages.</span></span> <span data-ttu-id="2f028-201">Se si usa **-1**, non inserire spazi tra il parametro e l'impostazione ( **-m-1**e non **-m -1**).</span><span class="sxs-lookup"><span data-stu-id="2f028-201">If using **-1**, there must be no space between the parameter and the setting (**-m-1**, not **-m -1**).</span></span>  
  
 <span data-ttu-id="2f028-202">**-r** { **0**| **1**}</span><span class="sxs-lookup"><span data-stu-id="2f028-202">**-r** { **0**| **1**}</span></span>  
 <span data-ttu-id="2f028-203">Reindirizza l'output dei messaggi sullo schermo (**stderr**).</span><span class="sxs-lookup"><span data-stu-id="2f028-203">Redirects message output to the screen (**stderr**).</span></span> <span data-ttu-id="2f028-204">Se il parametro viene omesso o si specifica **0**, vengono reindirizzati solo i messaggi di errore con gravità pari o superiore a 11.</span><span class="sxs-lookup"><span data-stu-id="2f028-204">If you do not specify a parameter, or if you specify **0**, only error messages with a severity level 11 or higher are redirected.</span></span> <span data-ttu-id="2f028-205">Se si specifica **1**, viene reindirizzato l'output di tutti i messaggi (incluso quello dell'istruzione "print").</span><span class="sxs-lookup"><span data-stu-id="2f028-205">If you specify **1**, all message output (including "print") is redirected.</span></span>  
  
 <span data-ttu-id="2f028-206">**-i** _input_file_</span><span class="sxs-lookup"><span data-stu-id="2f028-206">**-i** _input_file_</span></span>  
 <span data-ttu-id="2f028-207">Identifica il file che include un batch di istruzioni SQL o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="2f028-207">Identifies the file that contains a batch of SQL statements or stored procedures.</span></span> <span data-ttu-id="2f028-208">Anziché **\<** -i **, è possibile utilizzare l'operatore di confronto minore di (** ).</span><span class="sxs-lookup"><span data-stu-id="2f028-208">The less than (**\<**) comparison operator can be used in place of **-i**.</span></span>  
  
 <span data-ttu-id="2f028-209">**-o** _output_file_</span><span class="sxs-lookup"><span data-stu-id="2f028-209">**-o** _output_file_</span></span>  
 <span data-ttu-id="2f028-210">Identifica il file che riceve l'output di **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-210">Identifies the file that receives output from **osql**.</span></span> <span data-ttu-id="2f028-211">Anziché **>** -o **, è possibile usare l'operatore di confronto maggiore di (** ).</span><span class="sxs-lookup"><span data-stu-id="2f028-211">The greater than (**>**) comparison operator can be used in place of **-o**.</span></span>  
  
 <span data-ttu-id="2f028-212">Se *input_file* non è un file Unicode e l'opzione **-u** non è specificata, *output_file* viene archiviato in formato OEM.</span><span class="sxs-lookup"><span data-stu-id="2f028-212">If *input_file* is not Unicode and **-u** is not specified, *output_file* is stored in OEM format.</span></span> <span data-ttu-id="2f028-213">Se *input_file* è un file Unicode o l'opzione **-u** è specificata, *output_file* viene archiviato in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="2f028-213">If *input_file* is Unicode or **-u** is specified, *output_file* is stored in Unicode format.</span></span>  
  
 <span data-ttu-id="2f028-214">**-p**</span><span class="sxs-lookup"><span data-stu-id="2f028-214">**-p**</span></span>  
 <span data-ttu-id="2f028-215">Stampa le statistiche sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2f028-215">Prints performance statistics.</span></span>  
  
 <span data-ttu-id="2f028-216">**-b**</span><span class="sxs-lookup"><span data-stu-id="2f028-216">**-b**</span></span>  
 <span data-ttu-id="2f028-217">Specifica che, in caso di errore, **osql** termini, restituendo un valore DOS ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="2f028-217">Specifies that **osql** exits and returns a DOS ERRORLEVEL value when an error occurs.</span></span> <span data-ttu-id="2f028-218">Il valore restituito alla variabile DOS ERRORLEVEL è 1 se al messaggio di errore di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è associato un livello di gravità maggiore o uguale a 11. In caso contrario, il valore restituito è 0.</span><span class="sxs-lookup"><span data-stu-id="2f028-218">The value returned to the DOS ERRORLEVEL variable is 1 when the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] error message has a severity of 11 or greater; otherwise, the value returned is 0.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="2f028-219">I file batch MS-DOS consentono di verificare il valore di DOS ERRORLEVEL, nonché di gestire correttamente l'errore.</span><span class="sxs-lookup"><span data-stu-id="2f028-219">MS-DOS batch files can test the value of DOS ERRORLEVEL and handle the error appropriately.</span></span>  
  
 <span data-ttu-id="2f028-220">**-u**</span><span class="sxs-lookup"><span data-stu-id="2f028-220">**-u**</span></span>  
 <span data-ttu-id="2f028-221">Specifica l'archiviazione di *output_file* in formato Unicode, indipendentemente dal formato di *input_file*.</span><span class="sxs-lookup"><span data-stu-id="2f028-221">Specifies that *output_file* is stored in Unicode format, regardless of the format of the *input_file*.</span></span>  
  
 <span data-ttu-id="2f028-222">**-R**</span><span class="sxs-lookup"><span data-stu-id="2f028-222">**-R**</span></span>  
 <span data-ttu-id="2f028-223">Specifica che il driver ODBC di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizza le impostazioni del client per convertire i dati relativi a valuta, data e ora in dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="2f028-223">Specifies that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver use client settings when converting currency, date, and time data to character data.</span></span>  
  
 <span data-ttu-id="2f028-224">**-O**</span><span class="sxs-lookup"><span data-stu-id="2f028-224">**-O**</span></span>  
 <span data-ttu-id="2f028-225">Disattiva determinate caratteristiche di **osql** in modo che il funzionamento dell'utilità corrisponda a quello delle precedenti versioni di **isql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-225">Specifies that certain **osql** features be deactivated to match the behavior of earlier versions of **isql**.</span></span> <span data-ttu-id="2f028-226">Vengono disattivate le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f028-226">These features are deactivated:</span></span>  
  
-   <span data-ttu-id="2f028-227">Elaborazione batch EOF</span><span class="sxs-lookup"><span data-stu-id="2f028-227">EOF batch processing</span></span>  
  
-   <span data-ttu-id="2f028-228">Adattamento automatico della larghezza della console</span><span class="sxs-lookup"><span data-stu-id="2f028-228">Automatic console width scaling</span></span>  
  
-   <span data-ttu-id="2f028-229">Messaggi estesi</span><span class="sxs-lookup"><span data-stu-id="2f028-229">Wide messages</span></span>  
  
 <span data-ttu-id="2f028-230">L'opzione imposta inoltre il valore predefinito di DOS ERRORLEVEL su -1.</span><span class="sxs-lookup"><span data-stu-id="2f028-230">It also sets the default DOS ERRORLEVEL value to -1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-231">Le opzioni **-n**, **-O** e **-D** non sono più supportate da **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-231">The **-n**, **-O** and **-D** options are no longer supported by **osql**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f028-232">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2f028-232">Remarks</span></span>  
 <span data-ttu-id="2f028-233">L'utilità **osql** viene avviata direttamente dal sistema operativo con le opzioni elencate di seguito per le quali la distinzione tra maiuscole e minuscole è rilevante.</span><span class="sxs-lookup"><span data-stu-id="2f028-233">The **osql** utility is started directly from the operating system with the case-sensitive options listed here.</span></span> <span data-ttu-id="2f028-234">Dopo l'avvio, **osql**accetta istruzioni SQL e le invia a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="2f028-234">After **osql**starts, it accepts SQL statements and sends them to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] interactively.</span></span> <span data-ttu-id="2f028-235">I risultati vengono formattati e visualizzati sullo schermo (**stdout**).</span><span class="sxs-lookup"><span data-stu-id="2f028-235">The results are formatted and displayed on the screen (**stdout**).</span></span> <span data-ttu-id="2f028-236">Per uscire da **osql**usare QUIT o EXIT.</span><span class="sxs-lookup"><span data-stu-id="2f028-236">Use QUIT or EXIT to exit from **osql**.</span></span>  
  
 <span data-ttu-id="2f028-237">Se non si specifica un nome utente quando si avvia **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Verifica le variabili di ambiente e le utilizza, ad esempio **osqluser = ( *`user`* )** o **osqlserver = ( *`server`* )**.</span><span class="sxs-lookup"><span data-stu-id="2f028-237">If you do not specify a user name when you start **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] checks for the environment variables and uses those, for example, **osqluser=(*`user`*)** or **osqlserver=(*`server`*)**.</span></span> <span data-ttu-id="2f028-238">Se non sono state impostate variabili di ambiente, viene utilizzato il nome utente della workstation.</span><span class="sxs-lookup"><span data-stu-id="2f028-238">If no environment variables are set, the workstation user name is used.</span></span> <span data-ttu-id="2f028-239">Se non si specifica un server, viene utilizzato il nome della workstation.</span><span class="sxs-lookup"><span data-stu-id="2f028-239">If you do not specify a server, the name of the workstation is used.</span></span>  
  
 <span data-ttu-id="2f028-240">Se non si specifica l'opzione **-U** né l'opzione **-P** , [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cerca di stabilire la connessione tramite la modalità di autenticazione di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="2f028-240">If neither the **-U** or **-P** options are used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] attempts to connect using [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication Mode.</span></span> <span data-ttu-id="2f028-241">L'autenticazione si basa sull'account di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows dell'utente che esegue **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-241">Authentication is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows account of the user running **osql**.</span></span>  
  
 <span data-ttu-id="2f028-242">L'utilità **osql** usa l'API ODBC.</span><span class="sxs-lookup"><span data-stu-id="2f028-242">The **osql** utility uses the ODBC API.</span></span> <span data-ttu-id="2f028-243">Le impostazioni predefinite del driver ODBC di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per le opzioni di connessione ISO di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f028-243">The utility uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ODBC driver default settings for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ISO connection options.</span></span> <span data-ttu-id="2f028-244">Per ulteriori informazioni, vedere Effects of ANSI Options (informazioni in lingua inglese).</span><span class="sxs-lookup"><span data-stu-id="2f028-244">For more information, see Effects of ANSI Options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-245">L'utilità **osql** non supporta i tipi di dati CLR definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2f028-245">The **osql** utility does not support CLR user-defined data types.</span></span> <span data-ttu-id="2f028-246">Per elaborare questi tipi di dati, è necessario usare l'utilità **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="2f028-246">To process these data types, you must use the **sqlcmd** utility.</span></span> <span data-ttu-id="2f028-247">Per altre informazioni, vedere [sqlcmd Utility](sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2f028-247">For more information, see [sqlcmd Utility](sqlcmd-utility.md).</span></span>  
  
## <a name="osql-commands"></a><span data-ttu-id="2f028-248">Comandi OSQL</span><span class="sxs-lookup"><span data-stu-id="2f028-248">OSQL Commands</span></span>  
 <span data-ttu-id="2f028-249">Oltre alle istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] all'interno di **osql**, sono disponibili anche i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2f028-249">In addition to [!INCLUDE[tsql](../includes/tsql-md.md)] statements within **osql**, these commands are also available.</span></span>  
  
|<span data-ttu-id="2f028-250">Comando</span><span class="sxs-lookup"><span data-stu-id="2f028-250">Command</span></span>|<span data-ttu-id="2f028-251">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f028-251">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f028-252">GO</span><span class="sxs-lookup"><span data-stu-id="2f028-252">GO</span></span>|<span data-ttu-id="2f028-253">Esegue tutte le istruzioni immesse dopo l'ultimo comando GO.</span><span class="sxs-lookup"><span data-stu-id="2f028-253">Executes all statements entered after the last GO.</span></span>|  
|<span data-ttu-id="2f028-254">RESET</span><span class="sxs-lookup"><span data-stu-id="2f028-254">RESET</span></span>|<span data-ttu-id="2f028-255">Cancella tutte le istruzioni immesse.</span><span class="sxs-lookup"><span data-stu-id="2f028-255">Clears any statements you have entered.</span></span>|  
|<span data-ttu-id="2f028-256">QUIT o EXIT( )</span><span class="sxs-lookup"><span data-stu-id="2f028-256">QUIT or EXIT( )</span></span>|<span data-ttu-id="2f028-257">Consente di uscire da **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-257">Exits from **osql**.</span></span>|  
|<span data-ttu-id="2f028-258">CTRL+C</span><span class="sxs-lookup"><span data-stu-id="2f028-258">CTRL+C</span></span>|<span data-ttu-id="2f028-259">Termina una query senza uscire da **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-259">Ends a query without exiting from **osql**.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-260">I comandi !!</span><span class="sxs-lookup"><span data-stu-id="2f028-260">The !!</span></span> <span data-ttu-id="2f028-261">ed ED non sono più supportati da **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-261">and ED commands are no longer supported by **osql**.</span></span>  
  
 <span data-ttu-id="2f028-262">I caratteri di terminazione dei comandi GO (predefinito), RESET, EXIT, QUIT e CTRL+C vengono riconosciuti solo se specificati all'inizio della riga, subito dopo il prompt **osql** .</span><span class="sxs-lookup"><span data-stu-id="2f028-262">The command terminators GO (by default), RESET EXIT, QUIT, and CTRL+C, are recognized only if they appear at the beginning of a line, immediately following the **osql** prompt.</span></span>  
  
 <span data-ttu-id="2f028-263">GO indica sia la fine di un batch che l'esecuzione di eventuali istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="2f028-263">GO signals both the end of a batch and the execution of any cached [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="2f028-264">Quando si preme INVIO alla fine di ogni riga di input, **osql** memorizza nella cache le istruzioni della riga.</span><span class="sxs-lookup"><span data-stu-id="2f028-264">When you press ENTER at the end of each input line, **osql** caches the statements on that line.</span></span> <span data-ttu-id="2f028-265">Quando si preme INVIO dopo aver digitato GO, tutte le istruzioni memorizzate nella cache vengono inviate in batch a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f028-265">When you press ENTER after typing GO, all of the currently cached statements are sent as a batch to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2f028-266">La versione corrente dell'utilità **osql** funziona come se alla fine di tutti gli script eseguiti fosse presente un comando GO implicito. Di conseguenza vengono eseguite tutte le istruzioni dello script.</span><span class="sxs-lookup"><span data-stu-id="2f028-266">The current **osql** utility works as if there is an implied GO at the end of any script executed, therefore all statements in the script execute.</span></span>  
  
 <span data-ttu-id="2f028-267">Terminare un comando digitando una riga che inizia con un carattere di terminazione del comando.</span><span class="sxs-lookup"><span data-stu-id="2f028-267">End a command by typing a line beginning with a command terminator.</span></span> <span data-ttu-id="2f028-268">Per specificare quante volte eseguire il comando, digitare un numero dopo il carattere di terminazione.</span><span class="sxs-lookup"><span data-stu-id="2f028-268">You can follow the command terminator with an integer to specify how many times the command should be run.</span></span> <span data-ttu-id="2f028-269">Ad esempio, per eseguire il comando seguente 100 volte, digitare:</span><span class="sxs-lookup"><span data-stu-id="2f028-269">For example, to execute this command 100 times, type:</span></span>  
  
```  
SELECT x = 1  
GO 100  
```  
  
 <span data-ttu-id="2f028-270">I risultati vengono stampati solo una volta al termine dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2f028-270">The results are printed once at the end of execution.</span></span> <span data-ttu-id="2f028-271">**osql** non accetta più di 1.000 caratteri per riga.</span><span class="sxs-lookup"><span data-stu-id="2f028-271">**osql** does not accept more than 1,000 characters per line.</span></span> <span data-ttu-id="2f028-272">Le istruzioni di grandi dimensioni devono essere suddivise su più righe.</span><span class="sxs-lookup"><span data-stu-id="2f028-272">Large statements should be spread across multiple lines.</span></span>  
  
 <span data-ttu-id="2f028-273">Le funzionalità per la chiamata di comandi di Windows consentono di richiamare e modificare le istruzioni **osql** .</span><span class="sxs-lookup"><span data-stu-id="2f028-273">The command recall facilities of Windows can be used to recall and modify **osql** statements.</span></span> <span data-ttu-id="2f028-274">Per cancellare il buffer di query esistente digitare RESET.</span><span class="sxs-lookup"><span data-stu-id="2f028-274">The existing query buffer can be cleared by typing RESET.</span></span>  
  
 <span data-ttu-id="2f028-275">Durante l'esecuzione di stored procedure, **osql** stampa una riga vuota tra ogni set di risultati di un batch.</span><span class="sxs-lookup"><span data-stu-id="2f028-275">When running stored procedures, **osql** prints a blank line between each set of results in a batch.</span></span> <span data-ttu-id="2f028-276">Inoltre, il messaggio "Righe interessate: 0" non viene visualizzato se non è riferibile all'istruzione eseguita.</span><span class="sxs-lookup"><span data-stu-id="2f028-276">In addition, the "0 rows affected" message does not appear when it does not apply to the statement executed.</span></span>  
  
## <a name="using-osql-interactively"></a><span data-ttu-id="2f028-277">Uso interattivo di osql</span><span class="sxs-lookup"><span data-stu-id="2f028-277">Using osql Interactively</span></span>  
 <span data-ttu-id="2f028-278">Per usare **osql** interattivamente, al prompt dei comandi digitare il comando **osql** e le opzioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="2f028-278">To use **osql** interactively, type the **osql** command (and any of the options) at a command prompt.</span></span>  
  
 <span data-ttu-id="2f028-279">Per leggere un file contenente una query, ad esempio Stores.qry, da eseguire con **osql** , digitare un comando analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="2f028-279">You can read in a file containing a query (such as Stores.qry) for execution by **osql** by typing a command similar to this:</span></span>  
  
```  
osql -E -i stores.qry  
```  
  
 <span data-ttu-id="2f028-280">Per leggere un file contenente una query, ad esempio Titles.qry, e indirizzare i risultati a un altro file, digitare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2f028-280">You can read in a file containing a query (such as Titles.qry) and direct the results to another file by typing a command similar to this:</span></span>  
  
```  
osql -E -i titles.qry -o titles.res  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f028-281">Se possibile, usare l'opzione **-E**(connessione trusted).</span><span class="sxs-lookup"><span data-stu-id="2f028-281">When possible, use the **-E**option (trusted connection).</span></span>  
  
 <span data-ttu-id="2f028-282">Quando si usa **osql** in modo interattivo, è possibile leggere un file del sistema operativo nel buffer dei comandi con **: r**_file_name_.</span><span class="sxs-lookup"><span data-stu-id="2f028-282">When using **osql** interactively, you can read an operating-system file into the command buffer with **:r**_file_name_.</span></span> <span data-ttu-id="2f028-283">In questo modo lo script SQL in *file_name* viene inviato direttamente al server come batch singolo.</span><span class="sxs-lookup"><span data-stu-id="2f028-283">This sends the SQL script in *file_name* directly to the server as a single batch.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-284">Quando si usa **osql**, in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] la presenza del separatore di batch GO in un file script SQL viene considerata un errore di sintassi.</span><span class="sxs-lookup"><span data-stu-id="2f028-284">When using **osql**, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] treats the batch separator GO, if it appears in a SQL script file, as a syntax error.</span></span>  
  
## <a name="inserting-comments"></a><span data-ttu-id="2f028-285">Inserimento di commenti</span><span class="sxs-lookup"><span data-stu-id="2f028-285">Inserting Comments</span></span>  
 <span data-ttu-id="2f028-286">L'utilità [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] osql **consente di inserire commenti in un'istruzione Transact-SQL inviata a**.</span><span class="sxs-lookup"><span data-stu-id="2f028-286">You can include comments in a Transact-SQL statement submitted to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by **osql**.</span></span> <span data-ttu-id="2f028-287">Sono supportati due tipi di indicatori di commento: -- and /\*...\*/.</span><span class="sxs-lookup"><span data-stu-id="2f028-287">Two types of commenting styles are allowed: -- and /\*...\*/.</span></span>  
  
## <a name="using-exit-to-return-results-in-osql"></a><span data-ttu-id="2f028-288">Utilizzo di EXIT per la restituzione dei risultati in osql</span><span class="sxs-lookup"><span data-stu-id="2f028-288">Using EXIT to Return Results in osql</span></span>  
 <span data-ttu-id="2f028-289">Il risultato di un'istruzione SELECT può essere usato come valore restituito da **osql**.</span><span class="sxs-lookup"><span data-stu-id="2f028-289">You can use the result of a SELECT statement as the return value from **osql**.</span></span> <span data-ttu-id="2f028-290">Se numerica, l'ultima colonna dell'ultima riga di risultati viene convertita in un valore integer di 4 byte (long).</span><span class="sxs-lookup"><span data-stu-id="2f028-290">If it is numeric, the last column of the last result row is converted to a 4-byte integer (long).</span></span> <span data-ttu-id="2f028-291">MS-DOS passa il byte di ordine inferiore al processo padre o al livello di errore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2f028-291">MS-DOS passes the low byte to the parent process or operating system error level.</span></span> <span data-ttu-id="2f028-292">Windows passa l'intero valore intero di 4 byte.</span><span class="sxs-lookup"><span data-stu-id="2f028-292">Windows passes the entire 4-byte integer.</span></span> <span data-ttu-id="2f028-293">La sintassi è:</span><span class="sxs-lookup"><span data-stu-id="2f028-293">The syntax is:</span></span>  
  
```  
EXIT ( < query > )  
```  
  
 <span data-ttu-id="2f028-294">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2f028-294">For example:</span></span>  
  
```  
EXIT(SELECT @@ROWCOUNT)  
```  
  
 <span data-ttu-id="2f028-295">È inoltre possibile includere il parametro EXIT in un file batch.</span><span class="sxs-lookup"><span data-stu-id="2f028-295">You can also include the EXIT parameter as part of a batch file.</span></span> <span data-ttu-id="2f028-296">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2f028-296">For example:</span></span>  
  
```  
osql -E -Q "EXIT(SELECT COUNT(*) FROM '%1')"  
```  
  
 <span data-ttu-id="2f028-297">L'utilità **osql** passa al server tutti gli elementi racchiusi tra parentesi **()** senza modificarli.</span><span class="sxs-lookup"><span data-stu-id="2f028-297">The **osql** utility passes everything between the parentheses **()** to the server exactly as entered.</span></span> <span data-ttu-id="2f028-298">Se una stored procedure di sistema seleziona un set e restituisce un valore, viene restituita solo la selezione.</span><span class="sxs-lookup"><span data-stu-id="2f028-298">If a stored system procedure selects a set and returns a value, only the selection is returned.</span></span> <span data-ttu-id="2f028-299">Se non si specifica alcun elemento tra le parentesi dell'istruzione EXIT **()** , viene eseguito tutto ciò che la precede nel batch e l'operazione viene quindi terminata senza restituire alcun valore.</span><span class="sxs-lookup"><span data-stu-id="2f028-299">The EXIT **()** statement with nothing between the parentheses executes everything preceding it in the batch and then exits with no return value.</span></span>  
  
 <span data-ttu-id="2f028-300">L'istruzione EXIT può avere quattro formati:</span><span class="sxs-lookup"><span data-stu-id="2f028-300">There are four EXIT formats:</span></span>  
  
-   <span data-ttu-id="2f028-301">EXIT</span><span class="sxs-lookup"><span data-stu-id="2f028-301">EXIT</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-302">L'utilità non esegue il batch, viene chiusa immediatamente e non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="2f028-302">Does not execute the batch; quits immediately and returns no value.</span></span>  
  
-   <span data-ttu-id="2f028-303">EXIT **()**</span><span class="sxs-lookup"><span data-stu-id="2f028-303">EXIT **()**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-304">L'utilità esegue il batch, viene chiusa e non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="2f028-304">Executes the batch, and then quits and returns no value.</span></span>  
  
-   <span data-ttu-id="2f028-305">EXIT **( *`query`* )**</span><span class="sxs-lookup"><span data-stu-id="2f028-305">EXIT **(*`query`*)**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-306">L'utilità esegue il batch, inclusa la query, quindi viene chiusa dopo aver restituito i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="2f028-306">Executes the batch, including the query, and then quits after returning the results of the query.</span></span>  
  
-   <span data-ttu-id="2f028-307">RAISERROR con stato 127.</span><span class="sxs-lookup"><span data-stu-id="2f028-307">RAISERROR with a state of 127</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f028-308">Se in uno script **osql** si usa RAISERROR e viene generato un errore con stato 127, l'utilità **osql** viene chiusa e al client viene restituito l'ID di messaggio.</span><span class="sxs-lookup"><span data-stu-id="2f028-308">If RAISERROR is used within an **osql** script and a state of 127 is raised, **osql** will quit and return the message ID back to the client.</span></span> <span data-ttu-id="2f028-309">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2f028-309">For example:</span></span>  
  
```  
RAISERROR(50001, 10, 127)  
```  
  
 <span data-ttu-id="2f028-310">Questo errore provoca l'interruzione dello script **osql** e la restituzione dell'ID di messaggio 50001 al client.</span><span class="sxs-lookup"><span data-stu-id="2f028-310">This error will cause the **osql** script to end and the message ID 50001 will be returned to the client.</span></span>  
  
 <span data-ttu-id="2f028-311">I valori restituiti compresi tra -1 e -99 sono riservati a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. In **osql** vengono usati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f028-311">The return values -1 to -99 are reserved by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]; **osql** defines these values:</span></span>  
  
-   <span data-ttu-id="2f028-312">-100</span><span class="sxs-lookup"><span data-stu-id="2f028-312">-100</span></span>  
  
     <span data-ttu-id="2f028-313">Si è verificato un errore prima di selezionare il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="2f028-313">Error encountered prior to selecting return value.</span></span>  
  
-   <span data-ttu-id="2f028-314">-101</span><span class="sxs-lookup"><span data-stu-id="2f028-314">-101</span></span>  
  
     <span data-ttu-id="2f028-315">Selezionando il valore restituito non si sono trovate righe.</span><span class="sxs-lookup"><span data-stu-id="2f028-315">No rows found when selecting return value.</span></span>  
  
-   <span data-ttu-id="2f028-316">-102</span><span class="sxs-lookup"><span data-stu-id="2f028-316">-102</span></span>  
  
     <span data-ttu-id="2f028-317">Si è verificato un errore di conversione durante la selezione del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="2f028-317">Conversion error occurred when selecting return value.</span></span>  
  
## <a name="displaying-money-and-smallmoney-data-types"></a><span data-ttu-id="2f028-318">Visualizzazione dei tipi di dati money e smallmoney</span><span class="sxs-lookup"><span data-stu-id="2f028-318">Displaying money and smallmoney Data Types</span></span>  
 <span data-ttu-id="2f028-319">**osql** Visualizza i `money` `smallmoney` tipi di dati e con due posizioni decimali, sebbene [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] archivia il valore internamente con quattro posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="2f028-319">**osql** displays the `money` and `smallmoney` data types with two decimal places although [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stores the value internally with four decimal places.</span></span> <span data-ttu-id="2f028-320">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2f028-320">Consider the example:</span></span>  
  
```  
SELECT CAST(CAST(10.3496 AS money) AS decimal(6, 4))  
GO  
```  
  
 <span data-ttu-id="2f028-321">Questa istruzione restituisce il risultato `10.3496`, che indica che il valore viene archiviato con tutte le cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="2f028-321">This statement produces a result of `10.3496`, which indicates that the value is stored with all decimal places intact.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f028-322">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f028-322">See Also</span></span>  
 <span data-ttu-id="2f028-323">[Commento &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="2f028-323">[Comment &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="2f028-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span><span class="sxs-lookup"><span data-stu-id="2f028-324">[-- &#40;Comment&#41; &#40;MDX&#41;](/sql/mdx/comment-mdx) </span></span>  
 <span data-ttu-id="2f028-325">[CAST e CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f028-325">[CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql) </span></span>  
 [<span data-ttu-id="2f028-326">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f028-326">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
