---
title: Finestra di dialogo Strumenti esterni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- adding external tools
- external tools [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], external tools
ms.assetid: ba797203-24d0-4922-9b97-8ab483f1db14
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5789dc150e45c1a0364b7acc0ea7fda443efcf17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717268"
---
# <a name="external-tools-dialog-box"></a><span data-ttu-id="b4ba6-102">Finestra di dialogo Strumenti esterni</span><span class="sxs-lookup"><span data-stu-id="b4ba6-102">External Tools Dialog Box</span></span>
  <span data-ttu-id="b4ba6-103">Nella finestra di dialogo **Strumenti esterni** è possibile aggiungere strumenti esterni, ad esempio SQLCMD o Blocco note, al menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-103">Use the **External Tools** dialog box to add external tools such as SQLCMD or Notepad to the **Tools** menu.</span></span> <span data-ttu-id="b4ba6-104">L'aggiunta di strumenti esterni consente di avviare facilmente altre applicazioni dall'ambiente di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4ba6-104">Adding external tools allows you to easily launch other applications while working in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span> <span data-ttu-id="b4ba6-105">Durante l'avvio dello strumento, è possibile specificare argomenti e una directory di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="b4ba6-106">L'output di alcuni strumenti può inoltre essere visualizzato nella finestra **Output** .</span><span class="sxs-lookup"><span data-stu-id="b4ba6-106">In addition, the output from some tools can be displayed in the **Output** window.</span></span> <span data-ttu-id="b4ba6-107">La finestra di dialogo **Strumenti esterni** è accessibile dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b4ba6-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b4ba6-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b4ba6-108">Options</span></span>  
 <span data-ttu-id="b4ba6-109">**Contenuto menu**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-109">**Menu contents**</span></span>  
 <span data-ttu-id="b4ba6-110">Elenca i titoli degli elementi attualmente aggiunti al menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b4ba6-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="b4ba6-111">Usare i pulsanti **Sposta su** e **Sposta giù** per cambiare l'ordine di visualizzazione delle voci nel menu.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="b4ba6-112">Usare il pulsante **Elimina** per rimuovere una voce dal menu.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="b4ba6-113">**Sposta su**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-113">**Move Up**</span></span>  
 <span data-ttu-id="b4ba6-114">Sposta lo strumento selezionato più in alto nell'elenco degli strumenti visualizzati nel menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b4ba6-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="b4ba6-115">**Sposta giù**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-115">**Move Down**</span></span>  
 <span data-ttu-id="b4ba6-116">Sposta lo strumento selezionato più in basso nell'elenco degli strumenti visualizzati nel menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b4ba6-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="b4ba6-117">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-117">**Add**</span></span>  
 <span data-ttu-id="b4ba6-118">Consente di cancellare il contenuto delle caselle di testo e quindi di specificare un nuovo strumento.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="b4ba6-119">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-119">**Delete**</span></span>  
 <span data-ttu-id="b4ba6-120">Rimuove lo strumento o il comando dall'elenco **Contenuto menu** e dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b4ba6-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="b4ba6-121">**Titolo**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-121">**Title**</span></span>  
 <span data-ttu-id="b4ba6-122">Consente di immettere il nome dello strumento o del comando che verrà visualizzato nel sottomenu **Strumenti esterni** del menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b4ba6-122">Enter the name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="b4ba6-123">Inserire una e commerciale (&) prima di una lettera contenuta nel nome dello strumento per specificare tale lettera come tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-123">Place an ampersand (&) before a letter in the name of the tool to specify that letter as a keyboard shortcut.</span></span> <span data-ttu-id="b4ba6-124">Ad esempio, "&SQLCMD" verrà visualizzato come SQLCMD nel menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-124">For example, "&SQLCMD" would display SQLCMD on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="b4ba6-125">**Comando**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-125">**Command**</span></span>  
 <span data-ttu-id="b4ba6-126">Specificare il percorso del file da avviare.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-126">Specify the path to the file to launch.</span></span>  
  
 <span data-ttu-id="b4ba6-127">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-127">**Arguments**</span></span>  
 <span data-ttu-id="b4ba6-128">Consente di specificare le variabili passate allo strumento quando questo viene selezionato dal menu.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-128">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="b4ba6-129">Negli argomenti possono essere specificati valori che vengono passati allo strumento o al comando all'avvio.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-129">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="b4ba6-130">Un valore può ad esempio specificare un nome di file o una directory.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-130">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="b4ba6-131">Per selezionare un argomento da un elenco di argomenti predefiniti, utilizzare il pulsante freccia.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-131">Use the arrow button to select from a list of predefined arguments.</span></span> <span data-ttu-id="b4ba6-132">È possibile aggiungere più argomenti.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-132">You can add more than one.</span></span> <span data-ttu-id="b4ba6-133">Per un elenco completo degli argomenti predefiniti e delle relative definizioni, vedere [Strumenti esterni - Argomenti](menu-help/external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4ba6-133">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](menu-help/external-tools.md).</span></span> <span data-ttu-id="b4ba6-134">È inoltre possibile immettere argomenti personalizzati, ad esempio opzioni della riga di comando, a seconda del comando o dello strumento utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-134">You can also enter custom arguments (for example, command line switches), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="b4ba6-135">**Usa finestra di output**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-135">**Use Output window**</span></span>  
 <span data-ttu-id="b4ba6-136">Consente di aprire la finestra di output di [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] per visualizzare l'output del comando in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-136">Opens the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Output window to display output of the command being run.</span></span> <span data-ttu-id="b4ba6-137">Non tutti gli strumenti hanno un formato di output che può essere visualizzato nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-137">Not all tools present output in a format that can be presented in the Output window.</span></span> <span data-ttu-id="b4ba6-138">Per altre informazioni, vedere [Finestra di output](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span><span class="sxs-lookup"><span data-stu-id="b4ba6-138">For more information, see [Output Window](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span></span>  
  
 <span data-ttu-id="b4ba6-139">**Considera output come Unicode**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-139">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="b4ba6-140">Interpreta output come Unicode.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-140">Interprets the output as Unicode.</span></span>  
  
 <span data-ttu-id="b4ba6-141">**Directory iniziale**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-141">**Initial directory**</span></span>  
 <span data-ttu-id="b4ba6-142">Consente di specificare la directory di lavoro dello strumento.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-142">Specify the working directory of the tool.</span></span> <span data-ttu-id="b4ba6-143">Per selezionare directory, utilizzare il pulsante freccia.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-143">Use the arrow button to select directories.</span></span> <span data-ttu-id="b4ba6-144">È possibile selezionare più directory.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-144">You can select more than one.</span></span>  
  
 <span data-ttu-id="b4ba6-145">**Richiedi argomenti**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-145">**Prompt for arguments**</span></span>  
 <span data-ttu-id="b4ba6-146">Consente di visualizzare la finestra di dialogo **Argomenti** che permette di immettere o modificare valori per gli argomenti ogni volta che si avvia uno strumento esterno.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-146">Display the **Arguments** dialog box to allow you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="b4ba6-147">**Chiudi all'uscita**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-147">**Close on exit**</span></span>  
 <span data-ttu-id="b4ba6-148">Chiude la finestra aperta dallo strumento quando viene chiuso lo strumento stesso.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-148">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4ba6-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4ba6-149">Example</span></span>  
 <span data-ttu-id="b4ba6-150">Immettendo i seguenti valori nella finestra di dialogo **Strumenti esterni** verrà creata una voce di menu con etichetta "DAC" che, quando selezionata, consentirà di aprire un prompt dei comandi e di eseguire l'utilità **sqlcmd** usando la connessione amministrativa dedicata.</span><span class="sxs-lookup"><span data-stu-id="b4ba6-150">Entering the following values in the **External Tools** dialog box will create a menu item labeled "DAC" that when selected, opens a command prompt and runs the **sqlcmd** utility using the dedicated administrator connection.</span></span>  
  
|<span data-ttu-id="b4ba6-151">Box</span><span class="sxs-lookup"><span data-stu-id="b4ba6-151">Box</span></span>|<span data-ttu-id="b4ba6-152">valore</span><span class="sxs-lookup"><span data-stu-id="b4ba6-152">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="b4ba6-153">**Titolo**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-153">**Title**</span></span>|<span data-ttu-id="b4ba6-154">DAC</span><span class="sxs-lookup"><span data-stu-id="b4ba6-154">DAC</span></span>|  
|<span data-ttu-id="b4ba6-155">**Comando**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-155">**Command**</span></span>|[!INCLUDE[ssInstallPath](../includes/ssinstallpath-md.md)]<span data-ttu-id="b4ba6-156">Tools\Binn\SQLCMD.exe</span><span class="sxs-lookup"><span data-stu-id="b4ba6-156">Tools\Binn\SQLCMD.exe</span></span>|  
|<span data-ttu-id="b4ba6-157">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="b4ba6-157">**Arguments**</span></span>|<span data-ttu-id="b4ba6-158">-A</span><span class="sxs-lookup"><span data-stu-id="b4ba6-158">-A</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4ba6-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4ba6-159">See Also</span></span>  
 <span data-ttu-id="b4ba6-160">[Argomenti per gli strumenti esterni](menu-help/external-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b4ba6-160">[Arguments for External Tools](menu-help/external-tools.md) </span></span>  
 [<span data-ttu-id="b4ba6-161">Elementi generali dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b4ba6-161">General User Interface Elements</span></span>](general-user-interface-elements.md)  
  
  
