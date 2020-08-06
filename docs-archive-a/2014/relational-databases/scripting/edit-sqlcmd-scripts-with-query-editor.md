---
title: Modifica di script SQLCMD con l'editor di query
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], SQLCMD scripts
- SQLCMD scripts
- modifying scripts
- Query Editor [Database Engine], SQLCMD scripts
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: f77b866d-c330-47c9-9e74-0b8d8dff4b31
author: rothja
ms.author: jroth
ms.openlocfilehash: a3466cfc15ea2f4f0c8de5da42f4a1c24c28a575
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629330"
---
# <a name="edit-sqlcmd-scripts-with-query-editor"></a><span data-ttu-id="0d746-102">Modifica di script SQLCMD con l'editor di query</span><span class="sxs-lookup"><span data-stu-id="0d746-102">Edit SQLCMD Scripts with Query Editor</span></span>
  <span data-ttu-id="0d746-103">L'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] consente di scrivere e modificare query come script SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="0d746-103">By using the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] you can write and edit queries as SQLCMD scripts.</span></span> <span data-ttu-id="0d746-104">Gli script SQLCMD vengono utilizzati quando è necessario elaborare comandi di sistema di Windows e istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] nello stesso script.</span><span class="sxs-lookup"><span data-stu-id="0d746-104">You use SQLCMD scripts when you have to process Windows System commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the same script.</span></span>  
  
## <a name="sqlcmd-mode"></a><span data-ttu-id="0d746-105">Modalità SQLCMD</span><span class="sxs-lookup"><span data-stu-id="0d746-105">SQLCMD Mode</span></span>  
 <span data-ttu-id="0d746-106">Per utilizzare l'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] per scrivere o modificare script SQLCMD, è necessario abilitare la modalità di scripting SQLCMD,</span><span class="sxs-lookup"><span data-stu-id="0d746-106">To use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor to write or edit SQLCMD scripts, you must enable the SQLCMD scripting mode.</span></span> <span data-ttu-id="0d746-107">che per impostazione predefinita non è abilitata nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="0d746-107">By default, SQLCMD mode is not enabled in the Query Editor.</span></span> <span data-ttu-id="0d746-108">Per attivare la modalità di scripting, fare clic sull'icona **Modalità SQLCMD** sulla barra degli strumenti oppure scegliere **Modalità SQLCMD** dal menu **Query** .</span><span class="sxs-lookup"><span data-stu-id="0d746-108">You can enable scripting mode by clicking the **SQLCMD Mode** icon in the toolbar or by selecting **SQLCMD Mode** from the **Query** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d746-109">L'abilitazione della modalità SQLCMD disattiva IntelliSense e il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d746-109">Enabling SQLCMD mode turns off IntelliSense and the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="0d746-110">Per gli script SQLCMD è possibile utilizzare nell'editor di query le stesse caratteristiche disponibili per tutti gli script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d746-110">SQLCMD scripts in the Query Editor can use the same features that all [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts use.</span></span> <span data-ttu-id="0d746-111">Di seguito vengono descritte alcune di queste caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="0d746-111">These features include the following:</span></span>  
  
-   <span data-ttu-id="0d746-112">Codifica a colori</span><span class="sxs-lookup"><span data-stu-id="0d746-112">Color Coding</span></span>  
  
-   <span data-ttu-id="0d746-113">Esecuzione di script</span><span class="sxs-lookup"><span data-stu-id="0d746-113">Executing Scripts</span></span>  
  
-   <span data-ttu-id="0d746-114">Controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="0d746-114">Source Control</span></span>  
  
-   <span data-ttu-id="0d746-115">Analisi di script</span><span class="sxs-lookup"><span data-stu-id="0d746-115">Parsing Scripts</span></span>  
  
-   <span data-ttu-id="0d746-116">Showplan</span><span class="sxs-lookup"><span data-stu-id="0d746-116">Showplan</span></span>  
  
## <a name="enable-sqlcmd-scripting-in-query-editor"></a><span data-ttu-id="0d746-117">Attivazione di scripting SQLCMD nell'editor di query</span><span class="sxs-lookup"><span data-stu-id="0d746-117">Enable SQLCMD Scripting in Query Editor</span></span>  
 <span data-ttu-id="0d746-118">Per attivare script SQLCMD per una finestra dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] attiva, utilizzare la procedura descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d746-118">To turn SQLCMD scripting on for an active [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, use the following procedure.</span></span>  
  
#### <a name="to-switch-a-database-engine-query-editor-window-to-sqlcmd-mode"></a><span data-ttu-id="0d746-119">Per attivare la modalità SQLCMD per una finestra dell'editor di query del Motore di database</span><span class="sxs-lookup"><span data-stu-id="0d746-119">To switch a Database Engine Query Editor window to SQLCMD mode</span></span>  
  
1.  <span data-ttu-id="0d746-120">In Esplora oggetti fare clic con il pulsante destro del mouse sul server, quindi scegliere **Nuova query**per aprire una nuova finestra dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d746-120">In Object Explorer, right-click the server, and then click **New Query**, to open a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span>  
  
2.  <span data-ttu-id="0d746-121">Scegliere **Modalità SQLCMD** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="0d746-121">On the **Query** menu, click **SQLCMD Mode**.</span></span>  
  
     <span data-ttu-id="0d746-122">Nel contesto dell'editor di query vengono eseguite le istruzioni **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="0d746-122">The Query Editor executes **sqlcmd** statements in the context of the Query Editor.</span></span>  
  
3.  <span data-ttu-id="0d746-123">Sulla barra degli strumenti **Editor SQL** , nell'elenco **Database disponibili** , selezionare [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d746-123">On the **SQL Editor** toolbar, in the **Available Databases** list, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
4.  <span data-ttu-id="0d746-124">Nella finestra dell'editor di query digitare le due istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] e l'istruzione `!!DIR` **sqlcmd** seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d746-124">In the Query Editor window, type the following two [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and the `!!DIR` **sqlcmd** statement:</span></span>  
  
    ```  
    SELECT DISTINCT Type FROM Sales.SpecialOffer;  
    GO  
    !!DIR  
    GO  
    SELECT ProductCategoryID, Name FROM Production.ProductCategory;  
    GO  
    ```  
  
5.  <span data-ttu-id="0d746-125">Premere F5 per eseguire l'intera sezione di istruzioni miste [!INCLUDE[tsql](../../includes/tsql-md.md)] e MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="0d746-125">Press F5 to execute the whole section of mixed [!INCLUDE[tsql](../../includes/tsql-md.md)] and MS-DOS statements.</span></span>  
  
     <span data-ttu-id="0d746-126">Si notino i due riquadri dei risultati SQL relativi alla prima e alla terza istruzione.</span><span class="sxs-lookup"><span data-stu-id="0d746-126">Notice the two SQL result panes from the first and third statements.</span></span>  
  
6.  <span data-ttu-id="0d746-127">Nel riquadro **Risultati** fare clic sulla scheda **Messaggi** per visualizzare i messaggi relativi alle tre istruzioni:</span><span class="sxs-lookup"><span data-stu-id="0d746-127">In the **Results** pane, click the **Messages** tab to see the messages from all three statements:</span></span>  
  
    -   <span data-ttu-id="0d746-128">(Righe interessate: 6)</span><span class="sxs-lookup"><span data-stu-id="0d746-128">(6 row(s) affected)</span></span>  
  
    -   \<The directory information>  
  
    -   <span data-ttu-id="0d746-129">(Righe interessate: 4)</span><span class="sxs-lookup"><span data-stu-id="0d746-129">(4 row(s) affected)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0d746-130">Quando viene eseguita dalla riga di comando, l'utilità **sqlcmd** consente un'interazione completa con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0d746-130">When executed from the command line, the **sqlcmd** utility permits full interaction with the operating system.</span></span> <span data-ttu-id="0d746-131">Quando si usa l'editor di query in **Modalità SQLCMD**, è necessario assicurarsi che non vengano eseguite istruzioni interattive.</span><span class="sxs-lookup"><span data-stu-id="0d746-131">When you use the Query Editor in **SQLCMD Mode**, you must be careful not to execute interactive statements.</span></span> <span data-ttu-id="0d746-132">L'editor di query non è in grado di rispondere alle richieste del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0d746-132">The Query Editor cannot respond to operating system prompts.</span></span>  
  
 <span data-ttu-id="0d746-133">Per altre informazioni sull'esecuzione di SQLCMD, vedere [Utilità sqlcmd](../../tools/sqlcmd-utility.md)oppure eseguire l'esercitazione relativa a SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="0d746-133">For more information about how to run SQLCMD, see [sqlcmd Utility](../../tools/sqlcmd-utility.md), or take the SQLCMD tutorial.</span></span>  
  
## <a name="enable-sqlcmd-scripting-by-default"></a><span data-ttu-id="0d746-134">Attivazione di scripting SQLCMD per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="0d746-134">Enable SQLCMD Scripting by Default</span></span>  
 <span data-ttu-id="0d746-135">Per attivare la modalità di scripting SQLCMD per impostazione predefinita, scegliere **Opzioni** dal menu **Strumenti**, espandere **Esecuzione query**e **SSQL Server**, fare clic sulla pagina **Generale** e quindi selezionare la casella di controllo **Per impostazione predefinita, apri le nuove query in modalità SQLCMD** .</span><span class="sxs-lookup"><span data-stu-id="0d746-135">To turn SQLCMD scripting on by default, on the **Tools** menu select **Options**, expand **Query Execution**, and **SQL Server**, click the **General** page, and then check the **By default open new queries in SQLCMD Mode** box.</span></span>  
  
## <a name="writing-and-editing-sqlcmd-scripts"></a><span data-ttu-id="0d746-136">Scrittura e modifica di script SQLCMD</span><span class="sxs-lookup"><span data-stu-id="0d746-136">Writing and Editing SQLCMD Scripts</span></span>  
 <span data-ttu-id="0d746-137">Dopo avere attivato la modalità di scripting, sarà possibile immettere comandi SQLCMD e istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d746-137">After enabling scripting mode you may write SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="0d746-138">Sono applicabili le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d746-138">The following rules apply:</span></span>  
  
-   <span data-ttu-id="0d746-139">I comandi SQLCMD devono essere specificati come prima istruzione di una riga.</span><span class="sxs-lookup"><span data-stu-id="0d746-139">SQLCMD commands must be the first statement on a line.</span></span>  
  
-   <span data-ttu-id="0d746-140">È consentito un solo comando SQLCMD per riga.</span><span class="sxs-lookup"><span data-stu-id="0d746-140">Only one SQLCMD command is permitted on each line.</span></span>  
  
-   <span data-ttu-id="0d746-141">I comandi SQLCMD possono essere preceduti da commenti o da spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="0d746-141">SQLCMD commands can be preceded by comments or white space.</span></span>  
  
-   <span data-ttu-id="0d746-142">I comandi SQLCMD all'interno di commenti non vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="0d746-142">SQLCMD commands within comment characters are not executed.</span></span>  
  
-   <span data-ttu-id="0d746-143">I caratteri per i commenti a riga singola sono due segni meno (`--)` e devono essere visualizzati all'inizio della riga.</span><span class="sxs-lookup"><span data-stu-id="0d746-143">Single line comment characters are two hyphens (`--)` and must appear at the beginning of a line.</span></span>  
  
-   <span data-ttu-id="0d746-144">I comandi del sistema operativo devono essere preceduti da due punti esclamativi (`!!`).</span><span class="sxs-lookup"><span data-stu-id="0d746-144">Operating system commands must be preceded by two exclamation points (`!!`).</span></span> <span data-ttu-id="0d746-145">Il comando formato da due punti esclamativi attiva l'esecuzione dell'istruzione immediatamente seguente tramite il processore dei comandi `cmd.exe` .</span><span class="sxs-lookup"><span data-stu-id="0d746-145">The double-exclamation points command causes the statement that follows the exclamation points to be executed using the `cmd.exe` command processor.</span></span> <span data-ttu-id="0d746-146">Il testo dopo `!!` viene passato a `cmd.exe`come parametro e pertanto la riga di comando finale verrà eseguita come: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`</span><span class="sxs-lookup"><span data-stu-id="0d746-146">The text after `!!` is passed in as a parameter to `cmd.exe`, so the final command line will execute as: `"%SystemRoot%\system32\cmd.exe /c <text after !!>"`.</span></span>  
  
-   <span data-ttu-id="0d746-147">Per una chiara distinzione tra i comandi SQLCMD e [!INCLUDE[tsql](../../includes/tsql-md.md)], è necessario che tutti i comandi SQLCMD utilizzino come prefisso un carattere due punti (`:`).</span><span class="sxs-lookup"><span data-stu-id="0d746-147">To make a clear distinction between SQLCMD commands and [!INCLUDE[tsql](../../includes/tsql-md.md)], all SQLCMD commands, need to be prefixed with a colon (`:`).</span></span>  
  
-   <span data-ttu-id="0d746-148">Il comando `GO` può essere usato senza prefisso oppure può essere preceduto da `!!:`</span><span class="sxs-lookup"><span data-stu-id="0d746-148">The `GO` command may be used without preface, or preceded by `!!:`</span></span>  
  
-   <span data-ttu-id="0d746-149">L'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] supporta variabili di ambiente e variabili definite come parte di uno script SQLCMD, ma non supporta variabili **osql** o SQLCMD predefinite.</span><span class="sxs-lookup"><span data-stu-id="0d746-149">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports environment variables and variables that are defined as part of a SQLCMD script, but does not support built-in SQLCMD or **osql** variables.</span></span> <span data-ttu-id="0d746-150">L'elaborazione di SQLCMD da parte di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] distingue tra maiuscole e minuscole nelle variabili.</span><span class="sxs-lookup"><span data-stu-id="0d746-150">SQLCMD processing by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is case sensitive for variables.</span></span> <span data-ttu-id="0d746-151">Ad esempio, PRINT '$ (COMPUTERNAME)' produce il risultato corretto, ma PRINT '$ (ComputerName)' restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="0d746-151">For example, PRINT '$(COMPUTERNAME)' produces the correct result, but PRINT '$(ComputerName)' returns an error.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0d746-152">usa [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient per l'esecuzione in modalità regolare e SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="0d746-152">uses [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]SqlClient for execution in regular and SQLCMD mode.</span></span> <span data-ttu-id="0d746-153">Quando viene eseguito dalla riga di comando, SQLCMD utilizza il provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0d746-153">When run from the command line, SQLCMD uses the OLE DB provider.</span></span> <span data-ttu-id="0d746-154">Poiché le opzioni predefinite che è possibile applicare sono diverse, l'esecuzione della stessa query in modalità SQLCMD di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e nell'utilità SQLCMD potrebbe generare risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="0d746-154">Because different default options may apply, it is possible to get different behavior while executing the same query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] SQLCMD Mode, and in the SQLCMD utility.</span></span>  
  
## <a name="supported-sqlcmd-syntax"></a><span data-ttu-id="0d746-155">Sintassi SQLCMD supportata</span><span class="sxs-lookup"><span data-stu-id="0d746-155">Supported SQLCMD Syntax</span></span>  
 <span data-ttu-id="0d746-156">L'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] supporta le parole chiave degli script SQLCMD seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d746-156">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following SQLCMD script keywords:</span></span>  
  
 `[!!:]GO[count]`  
  
 `!! <command>`  
  
 `:exit(statement)`  
  
 `:Quit`  
  
 `:r <filename>`  
  
 `:setvar <var> <value>`  
  
 `:connect server[\instance] [-l login_timeout] [-U user [-P password]]`  
  
 `:on error [ignore|exit]`  
  
 `:error <filename>|stderr|stdout`  
  
 `:out <filename>|stderr|stdout`  
  
> [!NOTE]  
>  <span data-ttu-id="0d746-157">Sia per `:error` sia per `:out`, `stderr` e `stdout` inviano l'output alla scheda Messaggi.</span><span class="sxs-lookup"><span data-stu-id="0d746-157">For both `:error` and `:out`, `stderr` and `stdout` send output to the messages tab.</span></span>  
  
 <span data-ttu-id="0d746-158">I comandi SQLCMD non inclusi nell'elenco precedente non sono supportati nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="0d746-158">SQLCMD commands not listed above are not supported in Query Editor.</span></span> <span data-ttu-id="0d746-159">Quando viene eseguito uno script contenente parole chiave SQLCMD non supportate, l'editor di query invierà un messaggio "ignorando il comando \* \<ignored command*> " alla destinazione per ogni parola chiave non supportata.</span><span class="sxs-lookup"><span data-stu-id="0d746-159">When a script containing SQLCMD keywords that are not supported is executed, the Query Editor will send an "Ignoring command \*\<ignored command*>" message to the destination for each unsupported keyword.</span></span> <span data-ttu-id="0d746-160">Lo script verrà eseguito, ma i comandi non supportati verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="0d746-160">The script will execute successfully, but the unsupported commands will be ignored.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="0d746-161">Poiché SQLCMD non viene avviato dalla riga di comando, l'esecuzione dell'editor di query in modalità SQLCMD presenta alcune limitazioni.</span><span class="sxs-lookup"><span data-stu-id="0d746-161">Because you are not starting SQLCMD from the command line, there are some limitations when running Query Editor in SQLCMD Mode.</span></span> <span data-ttu-id="0d746-162">Non è possibile passare parametri della riga di comando come variabili e poiché l'editor di query non è in grado di rispondere ai prompt del sistema operativo, evitare di eseguire istruzioni interattive.</span><span class="sxs-lookup"><span data-stu-id="0d746-162">You cannot pass in command-line parameters such as variables, and, because the Query Editor does not have the ability to respond to operating system prompts, you must be careful not to execute interactive statements.</span></span>  
  
## <a name="color-coding-in-sqlcmd-scripts"></a><span data-ttu-id="0d746-163">Codifica a colori negli script SQLCMD</span><span class="sxs-lookup"><span data-stu-id="0d746-163">Color Coding in SQLCMD Scripts</span></span>  
 <span data-ttu-id="0d746-164">Quando è attivata la modalità di scripting SQLCMD, gli script avranno codifica a colori.</span><span class="sxs-lookup"><span data-stu-id="0d746-164">With SQLCMD scripting enabled, scripts will be color coded.</span></span> <span data-ttu-id="0d746-165">La codifica a colori per le parole chiave [!INCLUDE[tsql](../../includes/tsql-md.md)] rimarrà invariata.</span><span class="sxs-lookup"><span data-stu-id="0d746-165">The color coding for [!INCLUDE[tsql](../../includes/tsql-md.md)] keywords will remain the same.</span></span> <span data-ttu-id="0d746-166">I comandi SQLCMD vengono presentati con uno sfondo ombreggiato.</span><span class="sxs-lookup"><span data-stu-id="0d746-166">SQLCMD commands are presented with a shaded background.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d746-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d746-167">Example</span></span>  
 <span data-ttu-id="0d746-168">L'esempio seguente usa un'istruzione **sqlcmd** per creare un file di output denominato testoutput.txt ed esegue due istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT insieme a un comando del sistema operativo (per stampare la directory corrente).</span><span class="sxs-lookup"><span data-stu-id="0d746-168">The following example uses a **sqlcmd** statement to create an output file called testoutput.txt, executes two [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statements along with one operating system command (to print out the current directory).</span></span> <span data-ttu-id="0d746-169">Il file risultante contiene l'output del messaggio dall'istruzione `DIR` , seguito dall'output dei risultati dalle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d746-169">The resultant file contains the message output from the `DIR` statement, followed by the results output from the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
:out C:\testoutput.txt  
SELECT @@VERSION As 'Server Version'  
!!DIR  
!!:GO  
SELECT @@SERVERNAME AS 'Server Name'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d746-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d746-170">See Also</span></span>  
 [<span data-ttu-id="0d746-171">Utilità sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0d746-171">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
