---
title: Utilizzo dell'utilità sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL statements, executing
- command prompt utilities [SQL Server], sqlcmd
- statements [SQL Server], executing
- sqlcmd utility, about sqlcmd utility
ms.assetid: 3ec89119-7314-43ef-9e91-12e72bb63d62
author: rothja
ms.author: jroth
ms.openlocfilehash: 922f9915272fb2d7fc63487ec135ce44ee91e88b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635472"
---
# <a name="use-the-sqlcmd-utility"></a><span data-ttu-id="0cbe0-102">Utilizzo dell'utilità sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0cbe0-102">Use the sqlcmd Utility</span></span>
  <span data-ttu-id="0cbe0-103">L'utilità `sqlcmd` è un'utilità della riga di comando per l'esecuzione interattiva ad hoc di istruzioni e script [!INCLUDE[tsql](../../includes/tsql-md.md)], nonché per l'automazione di attività di scripting [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cbe0-103">The `sqlcmd` utility is a command-line utility for ad hoc, interactive execution of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and scripts and for automating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripting tasks.</span></span> <span data-ttu-id="0cbe0-104">Per utilizzare `sqlcmd` in modo interattivo o per compilare file script da eseguire tramite `sqlcmd`, è necessario conoscano [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cbe0-104">To use `sqlcmd` interactively, or to build script files to be run using `sqlcmd`, users must understand [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0cbe0-105">L'utilità `sqlcmd` viene in genere utilizzata nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-105">The `sqlcmd` utility is typically used in the following ways:</span></span>  
  
-   <span data-ttu-id="0cbe0-106">Gli utenti immettono interattivamente istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] in modo analogo all'utilizzo del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-106">Users interactively enter [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a manner similar to working at the command prompt.</span></span> <span data-ttu-id="0cbe0-107">I risultati vengono visualizzati al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-107">The results are displayed at the command prompt.</span></span> <span data-ttu-id="0cbe0-108">Per aprire una finestra del prompt dei comandi, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Accessori**e quindi su **Prompt dei comandi**.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-108">To open a Command Prompt window, click **Start**, click **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span> <span data-ttu-id="0cbe0-109">Al prompt dei comandi digitare `sqlcmd` seguito da un elenco delle opzioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-109">At the command prompt, type `sqlcmd` followed by a list of options that you want.</span></span> <span data-ttu-id="0cbe0-110">Per un elenco completo delle opzioni supportate da `sqlcmd` , vedere [utilità sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="0cbe0-110">For a complete list of the options that are supported by `sqlcmd`, see [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="0cbe0-111">Gli utenti inviano un processo `sqlcmd` specificando una singola istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] da eseguire o facendo in modo che l'utilità punti a un file di testo contenente istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] da eseguire.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-111">Users submit a `sqlcmd` job either by specifying a single [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to execute, or by pointing the utility to a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to execute.</span></span> <span data-ttu-id="0cbe0-112">L'output viene in genere indirizzato a un file di testo, ma può essere anche visualizzato al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-112">The output is usually directed to a text file, but it can also be displayed at the command prompt.</span></span>  
  
-   <span data-ttu-id="0cbe0-113">[Modalità SQLCMD](edit-sqlcmd-scripts-with-query-editor.md) nell'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cbe0-113">[SQLCMD mode](edit-sqlcmd-scripts-with-query-editor.md) in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="0cbe0-114">Oggetti SMO (SQL Server Management Objects)</span><span class="sxs-lookup"><span data-stu-id="0cbe0-114">SQL Server Management Objects (SMO)</span></span>  
  
-   <span data-ttu-id="0cbe0-115">Processi CmdExec di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-115">SQL Server Agent CmdExec jobs.</span></span>  
  
## <a name="typically-used-sqlcmd-options"></a><span data-ttu-id="0cbe0-116">Opzioni di sqlcmd utilizzate di frequente</span><span class="sxs-lookup"><span data-stu-id="0cbe0-116">Typically Used sqlcmd Options</span></span>  
 <span data-ttu-id="0cbe0-117">Le opzioni seguenti sono quelle utilizzate più di frequente:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-117">The following options are used most frequently:</span></span>  
  
-   <span data-ttu-id="0cbe0-118">Opzione Server (**-S**) che identifica l'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui si `sqlcmd` connette.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-118">The server option (**-S**) that identifies the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to which `sqlcmd` connects.</span></span>  
  
-   <span data-ttu-id="0cbe0-119">Opzioni di autenticazione (**-e**, **-U**e **-P**) che specificano le credenziali `sqlcmd` utilizzate da per la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cbe0-119">Authentication options (**-E**, **-U**, and **-P**) that specify the credentials that `sqlcmd` uses to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0cbe0-120">Opzione **-E** che è l'opzione predefinita e non è necessario specificarla.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-120">The **-E** option is the default and does not have to be specified.</span></span>  
  
-   <span data-ttu-id="0cbe0-121">Opzioni di input (**-q**, **-q**e **-i**) che identificano la posizione dell'input per `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="0cbe0-121">Input options (**-Q**, **-q**, and **-i**) that identify the location of the input to `sqlcmd`.</span></span>  
  
-   <span data-ttu-id="0cbe0-122">Opzione di output (**-o**) che specifica il file in cui deve `sqlcmd` essere inserito l'output.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-122">The output option (**-o**) that specifies the file in which `sqlcmd` is to put its output.</span></span>  
  
## <a name="connecting-to-the-sqlcmd-utility"></a><span data-ttu-id="0cbe0-123">Connessione all'utilità sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0cbe0-123">Connecting to the sqlcmd Utility</span></span>  
 <span data-ttu-id="0cbe0-124">Vengono di seguito riportati alcuni utilizzi comuni dell'utilità `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-124">The following are common uses of the `sqlcmd` utility:</span></span>  
  
-   <span data-ttu-id="0cbe0-125">Connessione a un'istanza predefinita utilizzando l'autenticazione di Windows per eseguire in modo interattivo le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="0cbe0-125">Connecting to a default instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="0cbe0-126">Nell'esempio precedente l'opzione **-E** non è specificata perché è l'impostazione predefinita e si `sqlcmd` connette all'istanza predefinita usando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-126">In the previous example, **-E** is not specified because it is the default and `sqlcmd` connects to the default instance by using Windows Authentication.</span></span>  
  
-   <span data-ttu-id="0cbe0-127">Connessione a un'istanza denominata utilizzando l'autenticazione di Windows per eseguire in modo interattivo istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="0cbe0-127">Connecting to a named instance by using Windows Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName>  
    ```  
  
     <span data-ttu-id="0cbe0-128">oppure</span><span class="sxs-lookup"><span data-stu-id="0cbe0-128">or</span></span>  
  
    ```  
    sqlcmd -S .\<InstanceName>  
    ```  
  
-   <span data-ttu-id="0cbe0-129">Connessione a un'istanza denominata utilizzando l'autenticazione di Windows e specificando i file di input e di output:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-129">Connecting to a named instance by using Windows Authentication and specifying input and output files:</span></span>  
  
    ```  
    sqlcmd -S <ComputerName>\<InstanceName> -i <MyScript.sql> -o <MyOutput.rpt>  
    ```  
  
-   <span data-ttu-id="0cbe0-130">Connessione all'istanza predefinita nel computer locale utilizzando l'autenticazione di Windows, esecuzione di una query e impostazione di `sqlcmd` in modo che rimanga in esecuzione al termine dell'esecuzione della query:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-130">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, and having `sqlcmd` remain running after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -q "SELECT * FROM AdventureWorks2012.Person.Person"  
    ```  
  
-   <span data-ttu-id="0cbe0-131">Connessione all'istanza predefinita nel computer locale utilizzando l'autenticazione di Windows, esecuzione di una query, indirizzamento dell'output a un file e impostazione di `sqlcmd` in modo che venga chiuso al termine dell'esecuzione della query:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-131">Connecting to the default instance on the local computer by using Windows Authentication, executing a query, directing the output to a file, and having `sqlcmd` exit after the query has finished running:</span></span>  
  
    ```  
    sqlcmd -Q "SELECT * FROM AdventureWorks2012.Person.Person" -o MyOutput.txt  
    ```  
  
-   <span data-ttu-id="0cbe0-132">Connessione a un'istanza denominata utilizzando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per eseguire in modo interattivo istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] con richiesta di password da parte di `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-132">Connecting to a named instance using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to interactively run [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, with `sqlcmd` prompting for a password:</span></span>  
  
    ```  
    sqlcmd -U MyLogin -S <ComputerName>\<InstanceName>  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="0cbe0-133">Per un elenco delle opzioni supportate dall'utilità `sqlcmd`, eseguire: `sqlcmd -?`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-133">To see a list of the options that are supported by the `sqlcmd` utility run: `sqlcmd -?`.</span></span>  
  
## <a name="running-transact-sql-statements-interactively-by-using-sqlcmd"></a><span data-ttu-id="0cbe0-134">Esecuzione interattiva di istruzioni Transact-SQL utilizzando sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0cbe0-134">Running Transact-SQL Statements Interactively by Using sqlcmd</span></span>  
 <span data-ttu-id="0cbe0-135">È possibile utilizzare l'utilità `sqlcmd` in modo interattivo per eseguire istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] in una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-135">You can use the `sqlcmd` utility interactively to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in a Command Prompt window.</span></span> <span data-ttu-id="0cbe0-136">Per eseguire in modo interattivo [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzioni utilizzando `sqlcmd` , eseguire l'utilità senza utilizzare le opzioni **-q**, **-q**, **-Z**o **-i** per specificare eventuali file di input o query.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-136">To interactively execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using `sqlcmd`, run the utility without using the **-Q**, **-q**, **-Z**, or **-i** options to specify any input files or queries.</span></span> <span data-ttu-id="0cbe0-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-137">For example:</span></span>  
  
 `sqlcmd -S <ComputerName>\<InstanceName>`  
  
 <span data-ttu-id="0cbe0-138">Quando il comando viene eseguito senza file di input o query, `sqlcmd` si connette all'istanza specificata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e quindi visualizza una nuova riga con il valore `1>` seguito da un carattere di sottolineatura intermittente denominato prompt di `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-138">When the command is executed without input files or queries, `sqlcmd` connects to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then displays a new line with a `1>` followed by a blinking underscore that is named the `sqlcmd` prompt.</span></span> <span data-ttu-id="0cbe0-139">Il valore `1` indica che si tratta della prima riga di un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)], mentre il prompt di `sqlcmd` è il punto in cui inizia l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] quando la si digita.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-139">The `1` signifies that this is the first line of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, and the `sqlcmd` prompt is the point at which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will start when you type it in.</span></span>  
  
 <span data-ttu-id="0cbe0-140">Al prompt di `sqlcmd` è possibile digitare istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] e comandi di `sqlcmd`, ad esempio `GO` e `EXIT`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-140">At the `sqlcmd` prompt, you can type both [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands, such as `GO` and `EXIT`.</span></span> <span data-ttu-id="0cbe0-141">Ogni istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] viene inserita in un buffer denominato cache dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-141">Each [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is put in a buffer called the statement cache.</span></span> <span data-ttu-id="0cbe0-142">Dopo aver digitato il comando `GO` e premuto di INVIO, queste istruzioni vengono inviate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cbe0-142">These statements are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] after you type the `GO` command and press ENTER.</span></span> <span data-ttu-id="0cbe0-143">Per uscire `sqlcmd` , digitare `EXIT` o `QUIT` all'inizio di una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-143">To exit `sqlcmd`, type `EXIT` or `QUIT` at the start of a new line.</span></span>  
  
 <span data-ttu-id="0cbe0-144">Per cancellare il contenuto della cache delle istruzioni, digitare `:RESET`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-144">To clear the statement cache, type `:RESET`.</span></span> <span data-ttu-id="0cbe0-145">La digitazione `^C` causa l' `sqlcmd` uscita.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-145">Typing `^C` causes `sqlcmd` to exit.</span></span> <span data-ttu-id="0cbe0-146">È inoltre possibile utilizzare `^C` per arrestare l'esecuzione della cache delle istruzioni dopo l'esecuzione di un comando `GO`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-146">`^C` can also be used to stop the execution of the statement cache after a `GO` command has been issued.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="0cbe0-147">le istruzioni immesse in una sessione interattiva possono essere modificate immettendo il comando **: ed** e il `sqlcmd` prompt.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-147">statements that are entered in an interactive session can edited by entering the **:ED** command and the `sqlcmd` prompt.</span></span> <span data-ttu-id="0cbe0-148">Verrà aperto l'editor. Dopo aver modificato l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] e chiuso l'editor, l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] modificata verrà visualizzata nella finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-148">The editor will open and, after editing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement and closing the editor, the revised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will appear in the command window.</span></span> <span data-ttu-id="0cbe0-149">Immettere `GO` per eseguire l' [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzione modificata.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-149">Enter `GO` to run therevised [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="quoted-strings"></a><span data-ttu-id="0cbe0-150">Stringhe tra virgolette</span><span class="sxs-lookup"><span data-stu-id="0cbe0-150">Quoted Strings</span></span>  
 <span data-ttu-id="0cbe0-151">I caratteri racchiusi tra virgolette vengono utilizzati senza alcuna pre-elaborazione aggiuntiva, fatta eccezione per il fatto che è possibile inserire virgolette in una stringa immettendo due virgolette consecutive.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-151">Characters that are enclosed in quotation marks are used without any additional preprocessing, except that quotations marks can be inserted into a string by entering two consecutive quotation marks.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0cbe0-152">tratta questa sequenza di caratteri come virgoletta.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-152">treats this character sequence as one quotation mark.</span></span> <span data-ttu-id="0cbe0-153">La traduzione avviene tuttavia nel server. Le variabili di scripting non vengono espanse se sono incluse all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-153">(However, the translation occurs in the server.) Scripting variables will not be expanded when they appear within a string.</span></span>  
  
 <span data-ttu-id="0cbe0-154">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-154">For example:</span></span>  
  
 `sqlcmd`  
  
 `PRINT "Length: 5"" 7'";`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Length: 5" 7'`  
  
## <a name="strings-that-span-multiple-lines"></a><span data-ttu-id="0cbe0-155">Stringhe che si estendono su più righe</span><span class="sxs-lookup"><span data-stu-id="0cbe0-155">Strings That Span Multiple Lines</span></span>  
 <span data-ttu-id="0cbe0-156">`sqlcmd` supporta script con stringhe che si estendono su più righe.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-156">`sqlcmd` supports scripts that have strings that span multiple lines.</span></span> <span data-ttu-id="0cbe0-157">Ad esempio, l'istruzione `SELECT` seguente si estende su più righe ma rappresenta una stringa singola eseguita quando si preme INVIO dopo aver digitato `GO`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-157">For example, the following `SELECT` statement spans multiple lines but is a single string executed when you press the ENTER key after typing `GO`.</span></span>  
  
 `SELECT First line`  
  
 `FROM Second line`  
  
 `WHERE Third line;`  
  
 `GO`  
  
## <a name="interactive-sqlcmd-example"></a><span data-ttu-id="0cbe0-158">Esempio di esecuzione interattiva dell'utilità sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0cbe0-158">Interactive sqlcmd Example</span></span>  
 <span data-ttu-id="0cbe0-159">Nell'esempio seguente viene illustrato il contenuto della finestra del prompt dei comandi quando si esegue `sqlcmd` in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-159">This is an example of what you see when you run `sqlcmd` interactively.</span></span>  
  
 <span data-ttu-id="0cbe0-160">Quando si apre la finestra del prompt dei comandi, è presente una riga simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-160">When you open a Command Prompt window, there is one line similar to:</span></span>  
  
 `C:\> _`  
  
 <span data-ttu-id="0cbe0-161">Questo significa che la cartella `C:\` è la cartella corrente. Se si specifica un nome di file, Windows cercherà il file in tale cartella.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-161">This means the folder `C:\` is the current folder, and if you specify a file name, Windows will look for the file in that folder.</span></span>  
  
 <span data-ttu-id="0cbe0-162">Digitare `sqlcmd` per connettersi all'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel computer locale. Il contenuto della finestra del prompt dei comandi sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-162">Type `sqlcmd` to connect to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the local computer, and the contents of the Command Prompt window will be:</span></span>  
  
 `C:\>sqlcmd`  
  
 `1> _`  
  
 <span data-ttu-id="0cbe0-163">Questo significa che è stata eseguita la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e `sqlcmd` è ora pronto ad accettare istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] e comandi `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="0cbe0-163">This means you have connected to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and `sqlcmd` is now ready to accept [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and `sqlcmd` commands.</span></span> <span data-ttu-id="0cbe0-164">Il carattere di sottolineatura intermittente dopo il valore `1>` è il prompt di `sqlcmd` che contrassegna la posizione in cui verranno visualizzati le istruzioni e i comandi digitati.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-164">The flashing underscore after the `1>` is the `sqlcmd` prompt that marks the location at which the statements and commands you type will be displayed.</span></span> <span data-ttu-id="0cbe0-165">A questo punto, digitare `USE AdventureWorks2012` e premere INVIO, quindi digitare `GO` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-165">Now, type `USE AdventureWorks2012` and press ENTER, and then type `GO` and press ENTER.</span></span> <span data-ttu-id="0cbe0-166">Il contenuto della finestra del prompt dei comandi sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-166">The contents of the Command Prompt window will be:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `1> _`  
  
 <span data-ttu-id="0cbe0-167">La pressione di INVIO dopo aver immesso `USE AdventureWorks2012` segnala all'utilità `sqlcmd` di iniziare una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-167">Pressing ENTER after entering `USE AdventureWorks2012` signaled `sqlcmd` to start a new line.</span></span> <span data-ttu-id="0cbe0-168">Premendo INVIO, dopo avere digitato `GO,` viene segnalato a `sqlcmd` di inviare l'istruzione `USE AdventureWorks2012` all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cbe0-168">Pressing ENTER, after you type `GO,` signaled `sqlcmd` to send the `USE AdventureWorks2012` statement to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0cbe0-169">`sqlcmd` restituisce quindi un messaggio per indicare che l'istruzione `USE` è stata completata correttamente e visualizza un nuovo prompt di `1>` per indicare che è possibile immettere un nuovo comando o istruzione.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-169">`sqlcmd` then returned a message to indicate that the `USE` statement completed successfully and displayed a new `1>` prompt as a signal to enter a new statement or command.</span></span>  
  
 <span data-ttu-id="0cbe0-170">Nell'esempio seguente viene illustrato il contenuto della finestra del prompt dei comandi quando si digita un'istruzione `SELECT` , un comando `GO` per eseguire l'istruzione `SELECT`e un comando `EXIT` per uscire da `sqlcmd`:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-170">The following example shows what the Command Prompt window contains if you type a `SELECT` statement, a `GO` to execute the `SELECT`, and an `EXIT` to exit `sqlcmd`:</span></span>  
  
 `sqlcmd`  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `BusinessEntityID   FirstName                 LastName`  
  
 `----------- -------------------------------- -----------`  
  
 `1           Syed                             Abbas`  
  
 `2           Catherine                        Abel`  
  
 `3           Kim                              Abercrombie`  
  
 `(3 rows affected)`  
  
 `1> EXIT`  
  
 `C:\>`  
  
 <span data-ttu-id="0cbe0-171">Le righe successive alla riga `3> GO` costituiscono l'output di un'istruzione `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="0cbe0-171">The lines after line `3> GO` are the output of a `SELECT` statement.</span></span> <span data-ttu-id="0cbe0-172">Dopo la generazione dell'output, `sqlcmd` reimposta il prompt di `sqlcmd` e visualizza `1>`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-172">After you generate output, `sqlcmd` resets the `sqlcmd` prompt and displays `1>`.</span></span> <span data-ttu-id="0cbe0-173">Dopo aver immesso `EXIT` nella riga `1>`, nella finestra del prompt dei comandi viene visualizzata la stessa riga presente alla prima apertura di tale finestra.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-173">After entering `EXIT` at line `1>`, the Command Prompt window displays the same line it did when you first opened it.</span></span> <span data-ttu-id="0cbe0-174">Ciò indica che la sessione di `sqlcmd` è terminata.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-174">This indicates that `sqlcmd` has exited its session.</span></span> <span data-ttu-id="0cbe0-175">È ora possibile chiudere la finestra del prompt dei comandi digitando un altro comando `EXIT` .</span><span class="sxs-lookup"><span data-stu-id="0cbe0-175">You can now close the Command Prompt window by typing another `EXIT` command.</span></span>  
  
## <a name="running-transact-sql-script-files-by-using-sqlcmd"></a><span data-ttu-id="0cbe0-176">Esecuzione di file script Transact-SQL utilizzando sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0cbe0-176">Running Transact-SQL Script Files by Using sqlcmd</span></span>  
 <span data-ttu-id="0cbe0-177">È possibile utilizzare `sqlcmd` per eseguire file script del database.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-177">You can use `sqlcmd` to execute database script files.</span></span> <span data-ttu-id="0cbe0-178">I file script sono file di testo che contengono una combinazione di [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzioni, `sqlcmd` comandi e variabili di scripting.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-178">Script files are text files that contain a mix of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span> <span data-ttu-id="0cbe0-179">Per altre informazioni sullo scripting di variabili, vedere [Utilizzo di sqlcmd con variabili di scripting](sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="0cbe0-179">For more information about how to script variables, see [Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md).</span></span> <span data-ttu-id="0cbe0-180">Il funzionamento di `sqlcmd` con le istruzioni, i comandi e le variabili di scripting presenti in un file script è analogo al funzionamento con le istruzioni e i comandi immessi in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-180">`sqlcmd` works with the statements, commands, and scripting variables in a script file in a manner similar to how it works with statements and commands that are entered interactively.</span></span> <span data-ttu-id="0cbe0-181">La principale differenza sta nel fatto che `sqlcmd` legge il file di input senza pause anziché attendere l'immissione di istruzioni, comandi e variabili di scripting da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-181">The main difference is that `sqlcmd` reads through the input file without pause instead of waiting for a user to enter the statements, commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="0cbe0-182">I file script di database possono essere creati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-182">There are different ways to create database script files:</span></span>  
  
-   <span data-ttu-id="0cbe0-183">È possibile compilare ed eseguire il debug di un set di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] in modo interattivo in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]e quindi salvare il contenuto della finestra Query come file script.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-183">You can interactively build and debug a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then save the contents of the Query window as a script file.</span></span>  
  
-   <span data-ttu-id="0cbe0-184">È possibile creare un file di testo contenente istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] utilizzando un editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-184">You can create a text file that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] statements by using a text editor, such as Notepad.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0cbe0-185">Esempi</span><span class="sxs-lookup"><span data-stu-id="0cbe0-185">Examples</span></span>  
  
### <a name="a-running-a-script-by-using-sqlcmd"></a><span data-ttu-id="0cbe0-186">R.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-186">A.</span></span> <span data-ttu-id="0cbe0-187">Esecuzione di uno script utilizzando sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0cbe0-187">Running a script by using sqlcmd</span></span>  
 <span data-ttu-id="0cbe0-188">Avviare Blocco note e digitare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-188">Start Notepad, and type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `SELECT TOP (3) BusinessEntityID, FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `GO`  
  
 <span data-ttu-id="0cbe0-189">Creare una cartella denominata `MyFolder` e quindi salvare lo script come file `MyScript.sql` nella cartella `C:\MyFolder`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-189">Create a folder named `MyFolder` and then save the script as the file `MyScript.sql` in the folder `C:\MyFolder`.</span></span> <span data-ttu-id="0cbe0-190">Al prompt dei comandi immettere quanto segue per eseguire lo script e inserire l'output nel file `MyOutput.txt` della cartella `MyFolder`:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-190">Enter the following at the command prompt to run the script and put the output in `MyOutput.txt` in `MyFolder`:</span></span>  
  
 `sqlcmd -i C:\MyFolder\MyScript.sql -o C:\MyFolder\MyOutput.txt`  
  
 <span data-ttu-id="0cbe0-191">Il contenuto di `MyOutput.txt` visualizzato in Blocco note sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-191">When you view the contents of `MyOutput.txt` in Notepad, you will see the following:</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `BusinessEntityID FirstName   LastName`  
  
 `---------------- ----------- -----------`  
  
 `1                Syed        Abbas`  
  
 `2                Catherine   Abel`  
  
 `3                Kim         Abercrombie`  
  
 `(3 rows affected)`  
  
### <a name="b-using-sqlcmd-with-a-dedicated-administrative-connection"></a><span data-ttu-id="0cbe0-192">B.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-192">B.</span></span> <span data-ttu-id="0cbe0-193">Utilizzo di sqlcmd con una connessione amministrativa dedicata</span><span class="sxs-lookup"><span data-stu-id="0cbe0-193">Using sqlcmd with a dedicated administrative connection</span></span>  
 <span data-ttu-id="0cbe0-194">Nell'esempio seguente `sqlcmd` viene utilizzato per connettersi a un server in cui si è verificato un problema di blocco utilizzando la connessione amministrativa dedicata (DAC, Dedicated Administration Connection).</span><span class="sxs-lookup"><span data-stu-id="0cbe0-194">In the following example, `sqlcmd` is used to connect to a server that has a blocking problem by using the dedicated administrator connection (DAC).</span></span>  
  
 `C:\>sqlcmd -S ServerName -A`  
  
 `1> SELECT blocked FROM sys.dm_exec_requests WHERE blocked <> 0;`  
  
 `2> GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `spid   blocked`  
  
 `------ -------`  
  
 `62       64`  
  
 `(1 rows affected)`  
  
 <span data-ttu-id="0cbe0-195">Utilizzare `sqlcmd` per terminare il processo di blocco.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-195">Use `sqlcmd` to end the blocking process.</span></span>  
  
 `1> KILL 64;`  
  
 `2> GO`  
  
### <a name="c-using-sqlcmd-to-execute-a-stored-procedure"></a><span data-ttu-id="0cbe0-196">C.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-196">C.</span></span> <span data-ttu-id="0cbe0-197">Utilizzo di sqlcmd per eseguire una stored procedure</span><span class="sxs-lookup"><span data-stu-id="0cbe0-197">Using sqlcmd to execute a stored procedure</span></span>  
 <span data-ttu-id="0cbe0-198">Nell'esempio seguente viene illustrata la modalità di esecuzione di una stored procedure mediante `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-198">The following example shows how to execute a stored procedure by using `sqlcmd`.</span></span> <span data-ttu-id="0cbe0-199">Creare la stored procedure seguente.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-199">Create the following stored procedure.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `IF OBJECT_ID ( ' dbo.ContactEmailAddress, 'P' ) IS NOT NULL`  
  
 `DROP PROCEDURE dbo.ContactEmailAddress;`  
  
 `GO`  
  
 `CREATE PROCEDURE dbo.ContactEmailAddress`  
  
 `(`  
  
 `@FirstName nvarchar(50)`  
  
 `,@LastName nvarchar(50)`  
  
 `)`  
  
 `AS`  
  
 `SET NOCOUNT ON`  
  
 `SELECT EmailAddress`  
  
 `FROM Person.Person`  
  
 `WHERE FirstName = @FirstName`  
  
 `AND LastName = @LastName;`  
  
 `SET NOCOUNT OFF`  
  
 <span data-ttu-id="0cbe0-200">Al prompt di `sqlcmd` digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-200">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\sqlcmd`  
  
 `1> :Setvar FirstName Gustavo`  
  
 `1> :Setvar LastName Achong`  
  
 `1> EXEC dbo.ContactEmailAddress $(Gustavo),$(Achong)`  
  
 `2> GO`  
  
 `EmailAddress`  
  
 `-----------------------------`  
  
 `gustavo0@adventure-works.com`  
  
### <a name="d-using-sqlcmd-for-database-maintenance"></a><span data-ttu-id="0cbe0-201">D.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-201">D.</span></span> <span data-ttu-id="0cbe0-202">Utilizzo di sqlcmd per la manutenzione del database</span><span class="sxs-lookup"><span data-stu-id="0cbe0-202">Using sqlcmd for database maintenance</span></span>  
 <span data-ttu-id="0cbe0-203">Nell'esempio seguente viene illustrato l'utilizzo di `sqlcmd` per un'attività di manutenzione del database.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-203">The following example shows how to use `sqlcmd` for a database maintenance task.</span></span> <span data-ttu-id="0cbe0-204">Creare `C:\BackupTemplate.sql` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-204">Create `C:\BackupTemplate.sql` with the following code.</span></span>  
  
 `USE master;`  
  
 `BACKUP DATABASE [$(db)] TO DISK='$(bakfile)';`  
  
 <span data-ttu-id="0cbe0-205">Al prompt di `sqlcmd` digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-205">At the `sqlcmd` prompt, enter the following:</span></span>  
  
 `C:\ >sqlcmd`  
  
 `1> :connect <server>`  
  
 `Sqlcmd: Successfully connected to server <server>.`  
  
 `1> :setvar db msdb`  
  
 `1> :setvar bakfile c:\msdb.bak`  
  
 `1> :r c:\BackupTemplate.sql`  
  
 `2> GO`  
  
 `Changed database context to 'master'.`  
  
 `Processed 688 pages for database 'msdb', file 'MSDBData' on file 2.`  
  
 `Processed 5 pages for database 'msdb', file 'MSDBLog' on file 2.`  
  
 `BACKUP DATABASE successfully processed 693 pages in 0.725 seconds (7.830 MB/sec)`  
  
### <a name="e-using-sqlcmd-to-execute-code-on-multiple-instances"></a><span data-ttu-id="0cbe0-206">E.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-206">E.</span></span> <span data-ttu-id="0cbe0-207">Utilizzo di sqlcmd per eseguire codice su più istanze</span><span class="sxs-lookup"><span data-stu-id="0cbe0-207">Using sqlcmd to execute code on multiple instances</span></span>  
 <span data-ttu-id="0cbe0-208">Il codice seguente in un file rappresenta un esempio di script che si connette a due istanze.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-208">The following code in a file shows a script that connects to two instances.</span></span> <span data-ttu-id="0cbe0-209">Si noti il comando `GO` prima della connessione alla seconda istanza.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-209">Notice the `GO` before the connection to the second instance.</span></span>  
  
 `:CONNECT <server>\,<instance1>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
 `:CONNECT <server>\,<instance2>`  
  
 `EXEC dbo.SomeProcedure`  
  
 `GO`  
  
### <a name="e-returning-xml-output"></a><span data-ttu-id="0cbe0-210">E.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-210">E.</span></span> <span data-ttu-id="0cbe0-211">Restituzione di output XML</span><span class="sxs-lookup"><span data-stu-id="0cbe0-211">Returning XML output</span></span>  
 <span data-ttu-id="0cbe0-212">Nell'esempio seguente viene illustrato come l'output XML venga restituito non formattato in un flusso continuo.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-212">The following example shows how XML output is returned unformatted, in a continuous stream.</span></span>  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> :XML ON`  
  
 `1> SELECT TOP 3 FirstName + ' ' + LastName + ', '`  
  
 `2> FROM Person.Person`  
  
 `3> GO`  
  
 `Syed Abbas, Catherine Abel, Kim Abercrombie,`  
  
### <a name="f-using-sqlcmd-in-a-windows-script-file"></a><span data-ttu-id="0cbe0-213">F.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-213">F.</span></span> <span data-ttu-id="0cbe0-214">Utilizzo di sqlcmd in un file script di Windows</span><span class="sxs-lookup"><span data-stu-id="0cbe0-214">Using sqlcmd in a Windows script file</span></span>  
 <span data-ttu-id="0cbe0-215">Un `sqlcmd` comando come `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` può essere eseguito in un file con estensione bat insieme a VBScript.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-215">A `sqlcmd`command such as `sqlcmd -i C:\InputFile.txt -o C:\OutputFile.txt,` can be executed in a .bat file together with VBScript.</span></span> <span data-ttu-id="0cbe0-216">In questo caso, non utilizzare opzioni interattive.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-216">In this case, do not use interactive options.</span></span> <span data-ttu-id="0cbe0-217">Nel computer che esegue il file con estensione bat deve essere installato `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-217">`sqlcmd` must be installed on the computer that is executing the .bat file.</span></span>  
  
 <span data-ttu-id="0cbe0-218">Creare innanzitutto i quattro file seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-218">First, create the following four files:</span></span>  
  
-   <span data-ttu-id="0cbe0-219">C:\badscript.sql</span><span class="sxs-lookup"><span data-stu-id="0cbe0-219">C:\badscript.sql</span></span>  
  
    ```  
    SELECT batch_1_this_is_an_error  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="0cbe0-220">C:\goodscript.sql</span><span class="sxs-lookup"><span data-stu-id="0cbe0-220">C:\goodscript.sql</span></span>  
  
    ```  
    SELECT 'batch #1'  
    GO  
    SELECT 'batch #2'  
    GO  
    ```  
  
-   <span data-ttu-id="0cbe0-221">C:\returnvalue.sql</span><span class="sxs-lookup"><span data-stu-id="0cbe0-221">C:\returnvalue.sql</span></span>  
  
    ```  
    :exit(select 100)  
    @echo off  
    C:\windowsscript.bat  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
-   <span data-ttu-id="0cbe0-222">C:\windowsscript.bat</span><span class="sxs-lookup"><span data-stu-id="0cbe0-222">C:\windowsscript.bat</span></span>  
  
    ```  
    @echo off  
  
    echo Running badscript.sql  
    sqlcmd -i badscript.sql -b -o out.log  
    if not errorlevel 1 goto next1  
    echo == An error occurred   
  
    :next1  
  
    echo Running goodscript.sql  
    sqlcmd -i goodscript.sql -b -o out.log  
    if not errorlevel 1 goto next2  
    echo == An error occurred   
  
    :next2  
    echo Running returnvalue.sql  
    sqlcmd -i returnvalue.sql -o out.log  
    echo SQLCMD returned %errorlevel% to the command shell  
  
    :exit  
    ```  
  
 <span data-ttu-id="0cbe0-223">Quindi, al prompt dei comandi eseguire `C:\windowsscript.bat`:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-223">Then, at the command prompt, run `C:\windowsscript.bat`:</span></span>  
  
 `C:\>windowsscript.bat`  
  
 `Running badscript.sql`  
  
 `== An error occurred`  
  
 `Running goodscript.sql`  
  
 `Running returnvalue.sql`  
  
 `SQLCMD returned 100 to the command shell`  
  
### <a name="g-using-sqlcmd-to-set-encryption-on-azure-sql-database"></a><span data-ttu-id="0cbe0-224">G.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-224">G.</span></span> <span data-ttu-id="0cbe0-225">Utilizzo di sqlcmd per impostare la crittografia in database SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="0cbe0-225">Using sqlcmd to set encryption on Azure SQL Database</span></span>  
 <span data-ttu-id="0cbe0-226">Un oggetto `sqlcmd` può essere eseguito in una connessione ai [!INCLUDE[ssSDS](../../includes/sssds-md.md)] dati in per specificare la crittografia e l'attendibilità del certificato.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-226">A `sqlcmd`can be executed on a connection to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] data on to specify encryption and certificate trust.</span></span> <span data-ttu-id="0cbe0-227">Sono disponibili due opzioni ' sqlcmd ''':</span><span class="sxs-lookup"><span data-stu-id="0cbe0-227">Two \`sqlcmd\`\`\`options are available:</span></span>  
  
-   <span data-ttu-id="0cbe0-228">L'opzione -N viene utilizzata dal client per richiedere una connessione crittografata.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-228">The -N switch is used by the client to request an encrypted connection.</span></span> <span data-ttu-id="0cbe0-229">Equivale all'opzione ADO.net `ENCRYPT = true`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-229">This option is equivalent to the ADO.net option `ENCRYPT = true`.</span></span>  
  
-   <span data-ttu-id="0cbe0-230">L'opzione -C viene usata dal client per configurare l'attendibilità implicita del certificato del server senza necessità di convalida.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-230">The -C switch is used by the client to configure it to implicitly the trust server certificate and not validate it.</span></span> <span data-ttu-id="0cbe0-231">Equivale all'opzione ADO.net `TRUSTSERVERCERTIFICATE = true`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-231">This option is equivalent to the ADO.net option `TRUSTSERVERCERTIFICATE = true`.</span></span>  
  
 <span data-ttu-id="0cbe0-232">Il servizio [!INCLUDE[ssSDS](../../includes/sssds-md.md)] non supporta tutte le opzioni `SET` disponibili in un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-232">The [!INCLUDE[ssSDS](../../includes/sssds-md.md)] service does not support all the `SET` options available on a SQL Server instance.</span></span> <span data-ttu-id="0cbe0-233">Nelle opzioni seguenti viene generato un errore quando l'opzione `SET` corrispondente è impostata su `ON` o `OFF`:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-233">The following options throw an error when the corresponding `SET` option is set to `ON` or `OFF`:</span></span>  
  
-   <span data-ttu-id="0cbe0-234">SET ANSI_DEFAULTS</span><span class="sxs-lookup"><span data-stu-id="0cbe0-234">SET ANSI_DEFAULTS</span></span>  
  
-   <span data-ttu-id="0cbe0-235">SET ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="0cbe0-235">SET ANSI_NULLS</span></span>  
  
-   <span data-ttu-id="0cbe0-236">SET REMOTE_PROC_TRANSACTIONS</span><span class="sxs-lookup"><span data-stu-id="0cbe0-236">SET REMOTE_PROC_TRANSACTIONS</span></span>  
  
-   <span data-ttu-id="0cbe0-237">SET ANSI_NULL_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0cbe0-237">SET ANSI_NULL_DEFAULT</span></span>  
  
 <span data-ttu-id="0cbe0-238">Le opzioni SET seguenti non generano eccezioni ma non possono essere utilizzate,</span><span class="sxs-lookup"><span data-stu-id="0cbe0-238">The following SET options do not throw exceptions but cannot be used.</span></span> <span data-ttu-id="0cbe0-239">in quanto deprecate:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-239">They are deprecated:</span></span>  
  
-   <span data-ttu-id="0cbe0-240">SET CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="0cbe0-240">SET CONCAT_NULL_YIELDS_NULL</span></span>  
  
-   <span data-ttu-id="0cbe0-241">SET ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="0cbe0-241">SET ANSI_PADDING</span></span>  
  
-   <span data-ttu-id="0cbe0-242">SET QUERY_GOVERNOR_COST_LIMIT</span><span class="sxs-lookup"><span data-stu-id="0cbe0-242">SET QUERY_GOVERNOR_COST_LIMIT</span></span>  
  
#### <a name="syntax"></a><span data-ttu-id="0cbe0-243">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cbe0-243">Syntax</span></span>  
 <span data-ttu-id="0cbe0-244">Gli esempi seguenti si riferiscono ai casi in cui le impostazioni del provider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client includono: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span><span class="sxs-lookup"><span data-stu-id="0cbe0-244">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = False`, `Trust Server Certificate = No`</span></span>  
  
 <span data-ttu-id="0cbe0-245">Effettuare la connessione utilizzando le credenziali di Windows e la comunicazione crittografata:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-245">Connect using Windows credentials and encrypt communication:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="0cbe0-246">Effettuare la connessione utilizzando le credenziali di Windows e un certificato server attendibile:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-246">Connect using Windows credentials and trust server certificate:</span></span>  
  
```  
SQLCMD -E -C  
  
```  
  
 <span data-ttu-id="0cbe0-247">Effettuare la connessione utilizzando le credenziali di Windows, la comunicazione crittografata e un certificato server attendibile:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-247">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="0cbe0-248">Gli esempi seguenti si riferiscono ai casi in cui le impostazioni del provider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client includono: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span><span class="sxs-lookup"><span data-stu-id="0cbe0-248">The following examples refer to cases where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Provider settings include: `ForceProtocolEncryption = True`, `TrustServerCertificate = Yes`.</span></span>  
  
 <span data-ttu-id="0cbe0-249">Effettuare la connessione utilizzando le credenziali di Windows, la comunicazione crittografata e un certificato server attendibile:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-249">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E  
  
```  
  
 <span data-ttu-id="0cbe0-250">Effettuare la connessione utilizzando le credenziali di Windows, la comunicazione crittografata e un certificato server attendibile:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-250">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N  
  
```  
  
 <span data-ttu-id="0cbe0-251">Effettuare la connessione utilizzando le credenziali di Windows, la comunicazione crittografata e un certificato server attendibile:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-251">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -T  
  
```  
  
 <span data-ttu-id="0cbe0-252">Effettuare la connessione utilizzando le credenziali di Windows, la comunicazione crittografata e un certificato server attendibile:</span><span class="sxs-lookup"><span data-stu-id="0cbe0-252">Connect using Windows credentials, encrypt communication and trust server certificate:</span></span>  
  
```  
SQLCMD -E -N -C  
  
```  
  
 <span data-ttu-id="0cbe0-253">Se il provider specifica `ForceProtocolEncryption = True` la crittografia è abilitata anche se nella stringa di connessione è impostato `Encrypt=No` .</span><span class="sxs-lookup"><span data-stu-id="0cbe0-253">If the provider specifies `ForceProtocolEncryption = True` then encryption is enabled even if `Encrypt=No` in the connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbe0-254">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cbe0-254">See Also</span></span>  
 <span data-ttu-id="0cbe0-255">[Utilità sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0cbe0-255">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="0cbe0-256">[Utilizzo di sqlcmd con variabili di scripting](sqlcmd-use-with-scripting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="0cbe0-256">[Use sqlcmd with Scripting Variables](sqlcmd-use-with-scripting-variables.md) </span></span>  
 <span data-ttu-id="0cbe0-257">[Modifica di script SQLCMD con l'editor di query](edit-sqlcmd-scripts-with-query-editor.md) </span><span class="sxs-lookup"><span data-stu-id="0cbe0-257">[Edit SQLCMD Scripts with Query Editor](edit-sqlcmd-scripts-with-query-editor.md) </span></span>  
 <span data-ttu-id="0cbe0-258">[Gestire passaggi di processo](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="0cbe0-258">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 [<span data-ttu-id="0cbe0-259">Creare un passaggio di processo CmdExec</span><span class="sxs-lookup"><span data-stu-id="0cbe0-259">Create a CmdExec Job Step</span></span>](../../ssms/agent/create-a-cmdexec-job-step.md)  
  
  
