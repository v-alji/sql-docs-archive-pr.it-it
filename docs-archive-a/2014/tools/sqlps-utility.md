---
title: Utilità sqlps | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- sqlps utility
- PowerShell [SQL Server], sqlps utility
ms.assetid: 4b2515a6-12c3-44fb-b263-1c567681cd2b
author: stevestein
ms.author: sstein
ms.openlocfilehash: b445366b3fb99ad4beebdf7b203ada77afe90c8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711212"
---
# <a name="sqlps-utility"></a><span data-ttu-id="6a579-102">sqlps - utilità</span><span class="sxs-lookup"><span data-stu-id="6a579-102">sqlps Utility</span></span>
  <span data-ttu-id="6a579-103">Tramite l'utilità `sqlps` viene avviata una sessione di Windows PowerShell 2.0 con il provider PowerShell per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e i cmdlet caricati e registrati.</span><span class="sxs-lookup"><span data-stu-id="6a579-103">The `sqlps` utility starts a Windows PowerShell 2.0 session with the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and cmdlets loaded and registered.</span></span> <span data-ttu-id="6a579-104">È possibile immettere comandi o script di PowerShell che utilizzano componenti di PowerShell per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per utilizzare istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e i relativi oggetti.</span><span class="sxs-lookup"><span data-stu-id="6a579-104">You can enter PowerShell commands or scripts that use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components to work with instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and their objects.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="6a579-105">Utilizzare invece il modulo di PowerShell `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="6a579-105">Use the `sqlps` PowerShell module instead.</span></span> <span data-ttu-id="6a579-106">Per ulteriori informazioni sul `sqlps` modulo, vedere [importare il modulo sqlps](../database-engine/import-the-sqlps-module.md).</span><span class="sxs-lookup"><span data-stu-id="6a579-106">For more information about the `sqlps` module, see [Import the SQLPS Module](../database-engine/import-the-sqlps-module.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a579-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a579-107">Syntax</span></span>  
  
```  
  
      sqlps   
[ [ [ -NoLogo ][ -NoExit ][ -NoProfile ]  
    [ -OutPutFormat { Text | XML } ] [ -InPutFormat { Text | XML } ]  
  ]  
  [ -Command { -  
             | script_block [ -argsargument_array ]  
             | string [ command_parameters ]  
             }  
  ]  
]  
[ -? | -Help ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6a579-108">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6a579-108">Arguments</span></span>  
 <span data-ttu-id="6a579-109">**-NoLogo**</span><span class="sxs-lookup"><span data-stu-id="6a579-109">**-NoLogo**</span></span>  
 <span data-ttu-id="6a579-110">Specifica che l'utilità `sqlps` deve nascondere le informazioni sul copyright all'avvio.</span><span class="sxs-lookup"><span data-stu-id="6a579-110">Specifies that the `sqlps` utility hide the copyright banner when it starts.</span></span>  
  
 <span data-ttu-id="6a579-111">**-NoExit**</span><span class="sxs-lookup"><span data-stu-id="6a579-111">**-NoExit**</span></span>  
 <span data-ttu-id="6a579-112">Specifica che l'esecuzione dell'utilità `sqlps` deve proseguire una volta completati i comandi di avvio.</span><span class="sxs-lookup"><span data-stu-id="6a579-112">Specifies that the `sqlps` utility continue running after the startup commands have completed.</span></span>  
  
 <span data-ttu-id="6a579-113">**-NoProfile**</span><span class="sxs-lookup"><span data-stu-id="6a579-113">**-NoProfile**</span></span>  
 <span data-ttu-id="6a579-114">Specifica che l'utilità `sqlps` non deve caricare un profilo utente.</span><span class="sxs-lookup"><span data-stu-id="6a579-114">Specifies that the `sqlps` utility not load a user profile.</span></span> <span data-ttu-id="6a579-115">I profili utente registrano alias, funzioni e variabili di uso comune per l'utilizzo nelle sessioni di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a579-115">User profiles record commonly used aliases, functions, and variables for use across PowerShell sessions.</span></span>  
  
 <span data-ttu-id="6a579-116">**-OutPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="6a579-116">**-OutPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="6a579-117">Specifica che l' `sqlps` output dell'utilità deve essere formattato come stringhe di testo (**testo**) o in un formato CLIXML serializzato (**XML**).</span><span class="sxs-lookup"><span data-stu-id="6a579-117">Specifies that the `sqlps` utility output be formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="6a579-118">**-InPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="6a579-118">**-InPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="6a579-119">Specifica che l'input per l' `sqlps` utilità è formattato come stringhe di testo (**testo**) o in un formato CLIXML serializzato (**XML**).</span><span class="sxs-lookup"><span data-stu-id="6a579-119">Specifies that input to the `sqlps` utility is formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="6a579-120">**-Command**</span><span class="sxs-lookup"><span data-stu-id="6a579-120">**-Command**</span></span>  
 <span data-ttu-id="6a579-121">Specifica il comando per l'esecuzione dell'utilità `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="6a579-121">Specifies the command for the `sqlps` utility to run.</span></span> <span data-ttu-id="6a579-122">L' `sqlps` utilità esegue il comando e quindi viene chiusa, a meno che non venga specificato anche **-NoExit** .</span><span class="sxs-lookup"><span data-stu-id="6a579-122">The `sqlps` utility runs the command and then exits, unless **-NoExit** is also specified.</span></span> <span data-ttu-id="6a579-123">Non specificare altre opzioni dopo **-Command**, in quanto verranno lette come parametri del comando.</span><span class="sxs-lookup"><span data-stu-id="6a579-123">Do not specify any other switches after **-Command**, they will be read as command parameters.</span></span>  
  
 **-**  
 <span data-ttu-id="6a579-124">**-Command-** specifica che l' `sqlps` utilità legge l'input dall'input standard.</span><span class="sxs-lookup"><span data-stu-id="6a579-124">**-Command-** specifies that the `sqlps` utility read the input from the standard input.</span></span>  
  
 <span data-ttu-id="6a579-125">*script_block* [ **-args**_argument_array_ ]</span><span class="sxs-lookup"><span data-stu-id="6a579-125">*script_block* [ **-args**_argument_array_ ]</span></span>  
 <span data-ttu-id="6a579-126">Specifica un blocco di comandi di PowerShell da eseguire. Il blocco deve essere incluso tra parentesi graffe: {}.</span><span class="sxs-lookup"><span data-stu-id="6a579-126">Specifies a block of PowerShell commands to run, the block must be enclosed in braces: {}.</span></span> <span data-ttu-id="6a579-127">*Script_block* può essere specificato solo quando l' `sqlps` utilità viene chiamata da **PowerShell** o da un'altra `sqlps` sessione dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="6a579-127">*Script_block* can only be specified when the `sqlps` utility is called from either **PowerShell** or another `sqlps` utility session.</span></span> <span data-ttu-id="6a579-128">*argument_array* è una matrice di variabili PowerShell che contiene gli argomenti per i comandi di PowerShell in *script_block*.</span><span class="sxs-lookup"><span data-stu-id="6a579-128">The *argument_array* is an array of PowerShell variables containing the arguments for the PowerShell commands in the *script_block*.</span></span>  
  
 <span data-ttu-id="6a579-129">*string* [ *command_parameters* ]</span><span class="sxs-lookup"><span data-stu-id="6a579-129">*string* [ *command_parameters* ]</span></span>  
 <span data-ttu-id="6a579-130">Specifica una stringa che contiene i comandi di PowerShell da eseguire.</span><span class="sxs-lookup"><span data-stu-id="6a579-130">Specifies a string that contains the PowerShell commands to be run.</span></span> <span data-ttu-id="6a579-131">Usare il formato **"& { *`command`* }"**.</span><span class="sxs-lookup"><span data-stu-id="6a579-131">Use the format **"&{*`command`*}"**.</span></span> <span data-ttu-id="6a579-132">Le virgolette indicano una stringa e l'operatore Invoke (&) fa `sqlps` in modo che l'utilità esegua il comando.</span><span class="sxs-lookup"><span data-stu-id="6a579-132">The quotation marks indicate a string, and the invoke operator (&) causes the `sqlps` utility to run the command.</span></span>  
  
 <span data-ttu-id="6a579-133">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="6a579-133">[ **-?**</span></span><span data-ttu-id="6a579-134"> |  **-Help** ]</span><span class="sxs-lookup"><span data-stu-id="6a579-134"> | **-Help** ]</span></span>  
 <span data-ttu-id="6a579-135">Visualizza il riepilogo della sintassi delle opzioni dell'utilità `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="6a579-135">Shows the syntax summary of the `sqlps` utility options.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a579-136">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6a579-136">Remarks</span></span>  
 <span data-ttu-id="6a579-137">L' `sqlps` utilità avvia l'ambiente di PowerShell (PowerShell.exe) e carica il [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] modulo di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a579-137">The `sqlps` utility starts the PowerShell environment (PowerShell.exe) and loads the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell module.</span></span> <span data-ttu-id="6a579-138">Il modulo, denominato anche `sqlps` , carica e registra gli [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-in di PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a579-138">The module, also named `sqlps`, loads and registers these [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins:</span></span>  
  
-   <span data-ttu-id="6a579-139">Microsoft.SqlServer.Management.PSProvider.dll</span><span class="sxs-lookup"><span data-stu-id="6a579-139">Microsoft.SqlServer.Management.PSProvider.dll</span></span>  
  
     <span data-ttu-id="6a579-140">Implementa il provider PowerShell per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e i cmdlet associati, ad esempio **Encode-SqlName** e **Decode-SqlName**.</span><span class="sxs-lookup"><span data-stu-id="6a579-140">Implements the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and associated cmdlets such as **Encode-SqlName** and **Decode-SqlName**.</span></span>  
  
-   <span data-ttu-id="6a579-141">Microsoft.SqlServer.Management.PSSnapin.dll</span><span class="sxs-lookup"><span data-stu-id="6a579-141">Microsoft.SqlServer.Management.PSSnapin.dll</span></span>  
  
     <span data-ttu-id="6a579-142">Implementa i cmdlet **Invoke-Sqlcmd** e **Invoke-PolicyEvaluation** .</span><span class="sxs-lookup"><span data-stu-id="6a579-142">Implements the **Invoke-Sqlcmd** and **Invoke-PolicyEvaluation** cmdlets.</span></span>  
  
 <span data-ttu-id="6a579-143">È possibile utilizzare l'utilità `sqlps` per effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a579-143">You can use the `sqlps` utility to do the following:</span></span>  
  
-   <span data-ttu-id="6a579-144">Eseguire in modo interattivo comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a579-144">Interactively run PowerShell commands.</span></span>  
  
-   <span data-ttu-id="6a579-145">Eseguire file script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a579-145">Run PowerShell script files.</span></span>  
  
-   <span data-ttu-id="6a579-146">Eseguire cmdlet di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a579-146">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="6a579-147">Utilizzare i percorsi del provider di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per spostarsi nella gerarchia degli oggetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a579-147">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="6a579-148">Per impostazione predefinita, l' `sqlps` utilità viene eseguita con i criteri di esecuzione degli script impostati su **Restricted**.</span><span class="sxs-lookup"><span data-stu-id="6a579-148">By default, the `sqlps` utility runs with the scripting execution policy set to **Restricted**.</span></span> <span data-ttu-id="6a579-149">Questa impostazione impedisce l'esecuzione di qualsiasi script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a579-149">This prevents running any PowerShell scripts.</span></span> <span data-ttu-id="6a579-150">Per abilitare l'esecuzione di script firmati o di qualsiasi script, è possibile usare il cmdlet **Set-ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="6a579-150">You can use the **Set-ExecutionPolicy** cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="6a579-151">Eseguire solo script provenienti da origini attendibili e proteggere tutti i file di input e di output utilizzando le autorizzazioni NTFS appropriate.</span><span class="sxs-lookup"><span data-stu-id="6a579-151">Only run scripts from trusted sources, and secure all input and output files by using the appropriate NTFS permissions.</span></span> <span data-ttu-id="6a579-152">Per ulteriori informazioni sull'abilitazione degli script di PowerShell, vedere la pagina relativa all' [esecuzione di script di Windows PowerShell](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span><span class="sxs-lookup"><span data-stu-id="6a579-152">For more information about enabling PowerShell scripts, see [Running Windows PowerShell Scripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span></span>  
  
 <span data-ttu-id="6a579-153">La versione dell'utilità `sqlps` in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] e [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] viene implementata come minishell di Windows PowerShell 1.0.</span><span class="sxs-lookup"><span data-stu-id="6a579-153">The version of the `sqlps` utility in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] and [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] was implemented as a Windows PowerShell 1.0 mini-shell.</span></span> <span data-ttu-id="6a579-154">Alle minishell si applicano alcune restrizioni, ad esempio agli utenti non è consentito caricare snap-in diversi da quelli caricati dalla minishell.</span><span class="sxs-lookup"><span data-stu-id="6a579-154">Mini-shells have certain restrictions, such as not allowing users to load snap-ins other than those loaded by the mini-shell.</span></span> <span data-ttu-id="6a579-155">Queste restrizioni non si applicano a [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] e versioni successive dell'utilità, modificate per utilizzare il modulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="6a579-155">These restrictions do not apply to the [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] and higher versions of the utility, which have been changed to use the `sqlps` module.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6a579-156">Esempi</span><span class="sxs-lookup"><span data-stu-id="6a579-156">Examples</span></span>  

### <a name="a-run-the-sqlps-utility-in-default-interactive-mode-without-the-copyright-banner"></a><span data-ttu-id="6a579-157">R.</span><span class="sxs-lookup"><span data-stu-id="6a579-157">A.</span></span> <span data-ttu-id="6a579-158">Eseguire l'utilità sqlps in modalità interattiva predefinita senza le informazioni sul copyright</span><span class="sxs-lookup"><span data-stu-id="6a579-158">Run the sqlps utility in default, interactive mode without the copyright banner</span></span>
  
```cmd
sqlps -NoLogo  
```  
  
### <a name="b-run-a-sql-server-powershell-script-from-the-command-prompt"></a><span data-ttu-id="6a579-159">B.</span><span class="sxs-lookup"><span data-stu-id="6a579-159">B.</span></span> <span data-ttu-id="6a579-160">Esecuzione di uno script di PowerShell per SQL Server dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="6a579-160">Run a SQL Server PowerShell script from the command prompt</span></span>
  
```cmd
sqlps -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
### <a name="c-run-a-sql-server-powershell-script-from-the-command-prompt-and-keep-running-after-the-script-completes"></a><span data-ttu-id="6a579-161">C.</span><span class="sxs-lookup"><span data-stu-id="6a579-161">C.</span></span> <span data-ttu-id="6a579-162">Esecuzione di uno script di PowerShell per SQL Server dal prompt dei comandi e proseguimento dell'esecuzione al termine dell'esecuzione dello script</span><span class="sxs-lookup"><span data-stu-id="6a579-162">Run a SQL Server PowerShell script from the command prompt, and keep running after the script completes</span></span>
  
```cmd
sqlps -NoExit -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a579-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a579-163">See Also</span></span>  
 <span data-ttu-id="6a579-164">[Abilitare o disabilitare un protocollo di rete del server](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="6a579-164">[Enable or Disable a Server Network Protocol](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 [<span data-ttu-id="6a579-165">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a579-165">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
