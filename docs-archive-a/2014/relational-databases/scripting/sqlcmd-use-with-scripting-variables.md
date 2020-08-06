---
title: Utilizzo di sqlcmd con variabili di scripting
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- scripts [SQL Server], sqlcmd utility
- variables [SQL Server], scripts
- scripting variables [SQL Server]
- sqlcmd utility, scripts
- setvar command
ms.assetid: 793495ca-cfc9-498d-8276-c44a5d09a92c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443cb400dc099726ba75bfcec2d38cee4ee2dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636019"
---
# <a name="use-sqlcmd-with-scripting-variables"></a><span data-ttu-id="72ba5-102">Utilizzo di sqlcmd con variabili di scripting</span><span class="sxs-lookup"><span data-stu-id="72ba5-102">Use sqlcmd with Scripting Variables</span></span>
  <span data-ttu-id="72ba5-103">Per variabile di scripting si intende una variabile utilizzata negli script.</span><span class="sxs-lookup"><span data-stu-id="72ba5-103">Variables that are used in scripts are called scripting variables.</span></span> <span data-ttu-id="72ba5-104">Le variabili di scripting consentono di utilizzare uno script in più scenari.</span><span class="sxs-lookup"><span data-stu-id="72ba5-104">Scripting variables enable one script to be used in multiple scenarios.</span></span> <span data-ttu-id="72ba5-105">Se, ad esempio, si desidera eseguire uno script su più server, è possibile utilizzare una variabile di scripting per il nome del server anziché modificare lo script per ogni server.</span><span class="sxs-lookup"><span data-stu-id="72ba5-105">For example, if you want to run one script against multiple servers, instead of modifying the script for each server, you can use a scripting variable for the server name.</span></span> <span data-ttu-id="72ba5-106">È infatti sufficiente modificare il nome del server fornito alla variabile di scripting per eseguire lo stesso script su server diversi.</span><span class="sxs-lookup"><span data-stu-id="72ba5-106">By changing the server name supplied to the scripting variable, the same script can be executed on different servers.</span></span>  
  
 <span data-ttu-id="72ba5-107">Le variabili di scripting possono essere definite in modo esplicito con il comando **setvar** oppure in modo implicito con l'opzione **sqlcmd-v** .</span><span class="sxs-lookup"><span data-stu-id="72ba5-107">Scripting variables can be defined explicitly by using the **setvar** command, or implicitly by using the **sqlcmd-v** option.</span></span>  
  
 <span data-ttu-id="72ba5-108">Questo argomento presenta anche alcuni esempi in cui vengono definite variabili di ambiente al prompt dei comandi Cmd.exe con **SET**.</span><span class="sxs-lookup"><span data-stu-id="72ba5-108">This topic also includes examples defining environmental variables at the Cmd.exe command prompt by using **SET**.</span></span>  
  
## <a name="setting-scripting-variables-by-using-the-setvar-command"></a><span data-ttu-id="72ba5-109">Impostazione delle variabili di scripting tramite il comando setvar</span><span class="sxs-lookup"><span data-stu-id="72ba5-109">Setting Scripting Variables by Using the setvar Command</span></span>  
 <span data-ttu-id="72ba5-110">Il comando **setvar** consente di definire variabili di scripting.</span><span class="sxs-lookup"><span data-stu-id="72ba5-110">The **setvar** command is used to define scripting variables.</span></span> <span data-ttu-id="72ba5-111">Le variabili definite con il comando **setvar** vengono archiviate internamente.</span><span class="sxs-lookup"><span data-stu-id="72ba5-111">Variables that are defined by using the **setvar** command are stored internally.</span></span> <span data-ttu-id="72ba5-112">Le variabili di scripting non devono essere confuse con le variabili di ambiente che vengono definite al prompt dei comandi con **SET**.</span><span class="sxs-lookup"><span data-stu-id="72ba5-112">Scripting variables should not be confused with environment variables that are defined at the command prompt by using **SET**.</span></span> <span data-ttu-id="72ba5-113">Se uno script fa riferimento a una variabile che non corrisponde a una variabile di ambiente oppure che non è stata definita con il comando **setvar**, verrà restituito un messaggio di errore e l'esecuzione dello script verrà arrestata.</span><span class="sxs-lookup"><span data-stu-id="72ba5-113">If a script references a variable that is not an environment variable or is not defined by using **setvar**, an error message is returned and the execution of the script will stop.</span></span> <span data-ttu-id="72ba5-114">Per altre informazioni, vedere l'opzione **-b** in [Utilità sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="72ba5-114">For more information, see the **-b** option in [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span>  
  
## <a name="variable-precedence-low-to-high"></a><span data-ttu-id="72ba5-115">Precedenza delle variabili (in ordine crescente)</span><span class="sxs-lookup"><span data-stu-id="72ba5-115">Variable Precedence (Low to High)</span></span>  
 <span data-ttu-id="72ba5-116">Se è stato assegnato lo stesso nome a più tipi di variabile, verrà utilizzata la variabile con la precedenza più alta.</span><span class="sxs-lookup"><span data-stu-id="72ba5-116">If more than one type of variable has the same name, the variable with the highest precedence is used.</span></span>  
  
1.  <span data-ttu-id="72ba5-117">Variabili di ambiente a livello di sistema</span><span class="sxs-lookup"><span data-stu-id="72ba5-117">System level environmental variables</span></span>  
  
2.  <span data-ttu-id="72ba5-118">Variabili di ambiente a livello di utente</span><span class="sxs-lookup"><span data-stu-id="72ba5-118">User level environmental variables</span></span>  
  
3.  <span data-ttu-id="72ba5-119">Shell dei comandi (**SET X=Y**) impostata al prompt dei comandi prima dell'avvio di **sqlcmd**</span><span class="sxs-lookup"><span data-stu-id="72ba5-119">Command shell (**SET X=Y**) set at command prompt before starting **sqlcmd**</span></span>  
  
4.  <span data-ttu-id="72ba5-120">**sqlcmd-v** X=Y</span><span class="sxs-lookup"><span data-stu-id="72ba5-120">**sqlcmd-v** X=Y</span></span>  
  
5.  <span data-ttu-id="72ba5-121">**:Setvar** X Y</span><span class="sxs-lookup"><span data-stu-id="72ba5-121">**:Setvar** X Y</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72ba5-122">Per visualizzare le variabili di ambiente, nel **Pannello di controllo**aprire **Sistema**quindi fare clic sulla scheda **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="72ba5-122">To view the environmental variables, in **Control Panel**, open **System**, and then click the **Advanced** tab.</span></span>  
  
## <a name="implicitly-setting-scripting-variables"></a><span data-ttu-id="72ba5-123">Impostazione implicita delle variabili di scripting</span><span class="sxs-lookup"><span data-stu-id="72ba5-123">Implicitly Setting Scripting Variables</span></span>  
 <span data-ttu-id="72ba5-124">Quando si avvia **sqlcmd** con un'opzione cui è correlata una variabile **sqlcmd** , la variabile **sqlcmd** viene impostata in modo implicito sul valore specificato con l'opzione.</span><span class="sxs-lookup"><span data-stu-id="72ba5-124">When you start **sqlcmd** with an option that has a related **sqlcmd** variable, the **sqlcmd** variable is set implicitly to the value that is specified by using the option.</span></span> <span data-ttu-id="72ba5-125">Nell'esempio seguente `sqlcmd` viene avviato con l'opzione `-l` .</span><span class="sxs-lookup"><span data-stu-id="72ba5-125">In the following example, `sqlcmd` is started with the `-l` option.</span></span> <span data-ttu-id="72ba5-126">La variabile SQLLOGINTIMEOUT viene quindi impostata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="72ba5-126">This implicitly sets the SQLLOGINTIMEOUT variable.</span></span>  
  
 `c:\> sqlcmd -l 60`  
  
 <span data-ttu-id="72ba5-127">È anche possibile usare l'opzione **-v** per impostare una variabile di scripting presente in uno script.</span><span class="sxs-lookup"><span data-stu-id="72ba5-127">You can also use the **-v** option to set a scripting variable that exists in a script.</span></span> <span data-ttu-id="72ba5-128">Nello script seguente (il nome di file è `testscript.sql`) `ColumnName` è una variabile di scripting.</span><span class="sxs-lookup"><span data-stu-id="72ba5-128">In the following script (the file name is `testscript.sql`), `ColumnName` is a scripting variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `SELECT x.$(ColumnName)`  
  
 `FROM Person.Person x`  
  
 <span data-ttu-id="72ba5-129">`WHERE c.`BusinessEntityID `< 5;`</span><span class="sxs-lookup"><span data-stu-id="72ba5-129">`WHERE c.`BusinessEntityID `< 5;`</span></span>  
  
 <span data-ttu-id="72ba5-130">È quindi possibile specificare il nome della colonna che si desidera restituire utilizzando l'opzione `-v` :</span><span class="sxs-lookup"><span data-stu-id="72ba5-130">You can then specify the name of the column that you want returned by using the `-v` option:</span></span>  
  
 `sqlcmd -v ColumnName ="FirstName" -i c:\testscript.sql`  
  
 <span data-ttu-id="72ba5-131">Per restituire una colonna diversa utilizzando lo stesso script, modificare il valore della variabile di scripting `ColumnName` .</span><span class="sxs-lookup"><span data-stu-id="72ba5-131">To return a different column by using the same script, change the value of the `ColumnName` scripting variable.</span></span>  
  
 `sqlcmd -v ColumnName ="LastName" -i c:\testscript.sql`  
  
## <a name="guidelines-for-scripting-variable-names-and-values"></a><span data-ttu-id="72ba5-132">Linee guida relative ai nomi e ai valori delle variabili di scripting</span><span class="sxs-lookup"><span data-stu-id="72ba5-132">Guidelines for Scripting Variable Names and Values</span></span>  
 <span data-ttu-id="72ba5-133">Quando si assegna un nome alle variabili di scripting, è necessario tenere presenti le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="72ba5-133">Consider the following guidelines when you name scripting variables:</span></span>  
  
-   <span data-ttu-id="72ba5-134">I nomi delle variabili non devono contenere spazi vuoti o virgolette.</span><span class="sxs-lookup"><span data-stu-id="72ba5-134">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="72ba5-135">Il formato dei nomi delle variabili non deve essere identico a quello di un'espressione con variabili, ad esempio *$(var)*.</span><span class="sxs-lookup"><span data-stu-id="72ba5-135">Variable names must not have the same form as a variable expression, such as *$(var)*.</span></span>  
  
-   <span data-ttu-id="72ba5-136">Per le variabili di scripting non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="72ba5-136">Scripting variables are case-insensitive</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="72ba5-137">Se non viene assegnato alcun valore a una variabile di ambiente **sqlcmd** , la variabile viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="72ba5-137">If no value is assigned to a **sqlcmd** environment variable, the variable is removed.</span></span> <span data-ttu-id="72ba5-138">Se si usa **:setvar VarName** senza un valore, la variabile viene cancellata.</span><span class="sxs-lookup"><span data-stu-id="72ba5-138">Using **:setvar VarName** without a value clears the variable.</span></span>  
  
 <span data-ttu-id="72ba5-139">Quando si specifica un valore per le variabili di scripting, è necessario tenere presenti le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="72ba5-139">Consider the following guidelines when you specify values for scripting variables:</span></span>  
  
-   <span data-ttu-id="72ba5-140">I valori delle variabili definiti con **setvar** o l'opzione **-v** devono essere racchiusi tra virgolette se il valore stringa contiene spazi.</span><span class="sxs-lookup"><span data-stu-id="72ba5-140">Variable values that are defined by using **setvar** or the **-v** option must be enclosed by quotation marks if the string value contains spaces.</span></span>  
  
-   <span data-ttu-id="72ba5-141">Se le virgolette fanno parte del valore della variabile, è necessario utilizzare i caratteri di escape.</span><span class="sxs-lookup"><span data-stu-id="72ba5-141">If quotation marks are part of the variable value, they must be escaped.</span></span> <span data-ttu-id="72ba5-142">Ad esempio, :`setvar MyVar "spac""e"`.</span><span class="sxs-lookup"><span data-stu-id="72ba5-142">For example: :`setvar MyVar "spac""e"`.</span></span>  
  
## <a name="guidelines-for-cmdexe-set-variable-values-and-names"></a><span data-ttu-id="72ba5-143">Linee guida relative ai valori e ai nomi delle variabili definite tramite SET in Cmd.exe</span><span class="sxs-lookup"><span data-stu-id="72ba5-143">Guidelines for Cmd.exe SET Variable Values and Names</span></span>  
 <span data-ttu-id="72ba5-144">Le variabili definite con SET fanno parte dell'ambiente Cmd.exe e **sqlcmd**può farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="72ba5-144">Variables that are defined by using SET are part of the Cmd.exe environment and can be referenced by **sqlcmd**.</span></span> <span data-ttu-id="72ba5-145">Considerare le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="72ba5-145">Consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="72ba5-146">I nomi delle variabili non devono contenere spazi vuoti o virgolette.</span><span class="sxs-lookup"><span data-stu-id="72ba5-146">Variable names must not contain white space characters or quotation marks.</span></span>  
  
-   <span data-ttu-id="72ba5-147">I valori delle variabili possono contenere spazi o virgolette.</span><span class="sxs-lookup"><span data-stu-id="72ba5-147">Variable values may contain spaces or quotation marks.</span></span>  
  
## <a name="sqlcmd-scripting-variables"></a><span data-ttu-id="72ba5-148">Variabili di scripting di sqlcmd</span><span class="sxs-lookup"><span data-stu-id="72ba5-148">sqlcmd Scripting Variables</span></span>  
 <span data-ttu-id="72ba5-149">Le variabili definite con **sqlcmd** sono note come variabili di scripting.</span><span class="sxs-lookup"><span data-stu-id="72ba5-149">Variables that are defined by **sqlcmd** are known as scripting variables.</span></span> <span data-ttu-id="72ba5-150">Nella tabella seguente sono elencate le variabili di scripting di **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="72ba5-150">The following table lists **sqlcmd** scripting variables.</span></span>  
  
|<span data-ttu-id="72ba5-151">Variabile</span><span class="sxs-lookup"><span data-stu-id="72ba5-151">Variable</span></span>|<span data-ttu-id="72ba5-152">Opzione correlata</span><span class="sxs-lookup"><span data-stu-id="72ba5-152">Related option</span></span>|<span data-ttu-id="72ba5-153">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-153">R/W</span></span>|<span data-ttu-id="72ba5-154">Predefinito</span><span class="sxs-lookup"><span data-stu-id="72ba5-154">Default</span></span>|  
|--------------|--------------------|----------|-------------|  
|<span data-ttu-id="72ba5-155">SQLCMDUSER\*</span><span class="sxs-lookup"><span data-stu-id="72ba5-155">SQLCMDUSER\*</span></span>|<span data-ttu-id="72ba5-156">-U</span><span class="sxs-lookup"><span data-stu-id="72ba5-156">-U</span></span>|<span data-ttu-id="72ba5-157">R</span><span class="sxs-lookup"><span data-stu-id="72ba5-157">R</span></span>|<span data-ttu-id="72ba5-158">""</span><span class="sxs-lookup"><span data-stu-id="72ba5-158">""</span></span>|  
|<span data-ttu-id="72ba5-159">SQLCMDPASSWORD\*</span><span class="sxs-lookup"><span data-stu-id="72ba5-159">SQLCMDPASSWORD\*</span></span>|<span data-ttu-id="72ba5-160">-P</span><span class="sxs-lookup"><span data-stu-id="72ba5-160">-P</span></span>|--|<span data-ttu-id="72ba5-161">""</span><span class="sxs-lookup"><span data-stu-id="72ba5-161">""</span></span>|  
|<span data-ttu-id="72ba5-162">SQLCMDSERVER\*</span><span class="sxs-lookup"><span data-stu-id="72ba5-162">SQLCMDSERVER\*</span></span>|<span data-ttu-id="72ba5-163">-S</span><span class="sxs-lookup"><span data-stu-id="72ba5-163">-S</span></span>|<span data-ttu-id="72ba5-164">R</span><span class="sxs-lookup"><span data-stu-id="72ba5-164">R</span></span>|<span data-ttu-id="72ba5-165">"DefaultLocalInstance"</span><span class="sxs-lookup"><span data-stu-id="72ba5-165">"DefaultLocalInstance"</span></span>|  
|<span data-ttu-id="72ba5-166">SQLCMDWORKSTATION</span><span class="sxs-lookup"><span data-stu-id="72ba5-166">SQLCMDWORKSTATION</span></span>|<span data-ttu-id="72ba5-167">-H</span><span class="sxs-lookup"><span data-stu-id="72ba5-167">-H</span></span>|<span data-ttu-id="72ba5-168">R</span><span class="sxs-lookup"><span data-stu-id="72ba5-168">R</span></span>|<span data-ttu-id="72ba5-169">"ComputerName"</span><span class="sxs-lookup"><span data-stu-id="72ba5-169">"ComputerName"</span></span>|  
|<span data-ttu-id="72ba5-170">SQLCMDDBNAME</span><span class="sxs-lookup"><span data-stu-id="72ba5-170">SQLCMDDBNAME</span></span>|<span data-ttu-id="72ba5-171">-d</span><span class="sxs-lookup"><span data-stu-id="72ba5-171">-d</span></span>|<span data-ttu-id="72ba5-172">R</span><span class="sxs-lookup"><span data-stu-id="72ba5-172">R</span></span>|<span data-ttu-id="72ba5-173">""</span><span class="sxs-lookup"><span data-stu-id="72ba5-173">""</span></span>|  
|<span data-ttu-id="72ba5-174">SQLCMDLOGINTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="72ba5-174">SQLCMDLOGINTIMEOUT</span></span>|<span data-ttu-id="72ba5-175">-l</span><span class="sxs-lookup"><span data-stu-id="72ba5-175">-l</span></span>|<span data-ttu-id="72ba5-176">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-176">R/W</span></span>|<span data-ttu-id="72ba5-177">"8" (secondi)</span><span class="sxs-lookup"><span data-stu-id="72ba5-177">"8" (seconds)</span></span>|  
|<span data-ttu-id="72ba5-178">SQLCMDSTATTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="72ba5-178">SQLCMDSTATTIMEOUT</span></span>|<span data-ttu-id="72ba5-179">-T</span><span class="sxs-lookup"><span data-stu-id="72ba5-179">-t</span></span>|<span data-ttu-id="72ba5-180">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-180">R/W</span></span>|<span data-ttu-id="72ba5-181">"0" = attesa illimitata</span><span class="sxs-lookup"><span data-stu-id="72ba5-181">"0" = wait indefinitely</span></span>|  
|<span data-ttu-id="72ba5-182">SQLCMDHEADERS</span><span class="sxs-lookup"><span data-stu-id="72ba5-182">SQLCMDHEADERS</span></span>|<span data-ttu-id="72ba5-183">-H</span><span class="sxs-lookup"><span data-stu-id="72ba5-183">-h</span></span>|<span data-ttu-id="72ba5-184">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-184">R/W</span></span>|<span data-ttu-id="72ba5-185">"0"</span><span class="sxs-lookup"><span data-stu-id="72ba5-185">"0"</span></span>|  
|<span data-ttu-id="72ba5-186">SQLCMDCOLSEP</span><span class="sxs-lookup"><span data-stu-id="72ba5-186">SQLCMDCOLSEP</span></span>|<span data-ttu-id="72ba5-187">-S</span><span class="sxs-lookup"><span data-stu-id="72ba5-187">-s</span></span>|<span data-ttu-id="72ba5-188">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-188">R/W</span></span>|<span data-ttu-id="72ba5-189">" "</span><span class="sxs-lookup"><span data-stu-id="72ba5-189">" "</span></span>|  
|<span data-ttu-id="72ba5-190">SQLCMDCOLWIDTH</span><span class="sxs-lookup"><span data-stu-id="72ba5-190">SQLCMDCOLWIDTH</span></span>|<span data-ttu-id="72ba5-191">-w</span><span class="sxs-lookup"><span data-stu-id="72ba5-191">-w</span></span>|<span data-ttu-id="72ba5-192">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-192">R/W</span></span>|<span data-ttu-id="72ba5-193">"0"</span><span class="sxs-lookup"><span data-stu-id="72ba5-193">"0"</span></span>|  
|<span data-ttu-id="72ba5-194">SQLCMDPACKETSIZE</span><span class="sxs-lookup"><span data-stu-id="72ba5-194">SQLCMDPACKETSIZE</span></span>|<span data-ttu-id="72ba5-195">-a</span><span class="sxs-lookup"><span data-stu-id="72ba5-195">-a</span></span>|<span data-ttu-id="72ba5-196">R</span><span class="sxs-lookup"><span data-stu-id="72ba5-196">R</span></span>|<span data-ttu-id="72ba5-197">"4096"</span><span class="sxs-lookup"><span data-stu-id="72ba5-197">"4096"</span></span>|  
|<span data-ttu-id="72ba5-198">SQLCMDERRORLEVEL</span><span class="sxs-lookup"><span data-stu-id="72ba5-198">SQLCMDERRORLEVEL</span></span>|<span data-ttu-id="72ba5-199">-M</span><span class="sxs-lookup"><span data-stu-id="72ba5-199">-m</span></span>|<span data-ttu-id="72ba5-200">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-200">R/W</span></span>|<span data-ttu-id="72ba5-201">"0"</span><span class="sxs-lookup"><span data-stu-id="72ba5-201">"0"</span></span>|  
|<span data-ttu-id="72ba5-202">SQLCMDMAXVARTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="72ba5-202">SQLCMDMAXVARTYPEWIDTH</span></span>|<span data-ttu-id="72ba5-203">-y</span><span class="sxs-lookup"><span data-stu-id="72ba5-203">-y</span></span>|<span data-ttu-id="72ba5-204">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-204">R/W</span></span>|<span data-ttu-id="72ba5-205">"256"</span><span class="sxs-lookup"><span data-stu-id="72ba5-205">"256"</span></span>|  
|<span data-ttu-id="72ba5-206">SQLCMDMAXFIXEDTYPEWIDTH</span><span class="sxs-lookup"><span data-stu-id="72ba5-206">SQLCMDMAXFIXEDTYPEWIDTH</span></span>|<span data-ttu-id="72ba5-207">-y</span><span class="sxs-lookup"><span data-stu-id="72ba5-207">-Y</span></span>|<span data-ttu-id="72ba5-208">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-208">R/W</span></span>|<span data-ttu-id="72ba5-209">"0" = numero illimitato</span><span class="sxs-lookup"><span data-stu-id="72ba5-209">"0" = unlimited</span></span>|  
|<span data-ttu-id="72ba5-210">SQLCMDEDITOR</span><span class="sxs-lookup"><span data-stu-id="72ba5-210">SQLCMDEDITOR</span></span>||<span data-ttu-id="72ba5-211">L/S</span><span class="sxs-lookup"><span data-stu-id="72ba5-211">R/W</span></span>|<span data-ttu-id="72ba5-212">"edit.com"</span><span class="sxs-lookup"><span data-stu-id="72ba5-212">"edit.com"</span></span>|  
|<span data-ttu-id="72ba5-213">SQLCMDINI</span><span class="sxs-lookup"><span data-stu-id="72ba5-213">SQLCMDINI</span></span>||<span data-ttu-id="72ba5-214">R</span><span class="sxs-lookup"><span data-stu-id="72ba5-214">R</span></span>|<span data-ttu-id="72ba5-215">""</span><span class="sxs-lookup"><span data-stu-id="72ba5-215">""</span></span>|  
  
 <span data-ttu-id="72ba5-216">\*SQLCMDUSER, SQLCMDPASSWORD e SQLCMDSERVER vengono impostati quando si usa **: Connect** .</span><span class="sxs-lookup"><span data-stu-id="72ba5-216">\* SQLCMDUSER, SQLCMDPASSWORD and SQLCMDSERVER are set when **:Connect** is used.</span></span>  
  
 <span data-ttu-id="72ba5-217">La lettera L indica che il valore può essere impostato una sola volta durante l'inizializzazione del programma.</span><span class="sxs-lookup"><span data-stu-id="72ba5-217">R indicates the value can only be set one time during program initialization.</span></span>  
  
 <span data-ttu-id="72ba5-218">L/S indica che il valore può essere reimpostato con il comando **setvar** e i comandi successivi useranno il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="72ba5-218">R/W indicates that the value can be reset by using the **setvar** command and subsequent commands will use the new value.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="72ba5-219">Esempi</span><span class="sxs-lookup"><span data-stu-id="72ba5-219">Examples</span></span>  
  
### <a name="a-using-the-setvar-command-in-a-script"></a><span data-ttu-id="72ba5-220">R.</span><span class="sxs-lookup"><span data-stu-id="72ba5-220">A.</span></span> <span data-ttu-id="72ba5-221">Utilizzo del comando setvar in uno script</span><span class="sxs-lookup"><span data-stu-id="72ba5-221">Using the setvar command in a script</span></span>  
 <span data-ttu-id="72ba5-222">Molte opzioni di **sqlcmd** possono essere controllate in uno script usando il comando **setvar** .</span><span class="sxs-lookup"><span data-stu-id="72ba5-222">Many **sqlcmd** options can be controlled in a script by using the **setvar** command.</span></span> <span data-ttu-id="72ba5-223">Nell'esempio seguente viene creato lo script `test.sql` , in cui la variabile `SQLCMDLOGINTIMEOUT` viene impostata su `60` secondi e un'altra variabile di scripting, `server`, viene impostata su `testserver`.</span><span class="sxs-lookup"><span data-stu-id="72ba5-223">In the following example, the script `test.sql` is created in which the `SQLCMDLOGINTIMEOUT` variable is set to `60` seconds and another scripting variable, `server`, is set to `testserver`.</span></span> <span data-ttu-id="72ba5-224">Il codice seguente è incluso in `test.sql`.</span><span class="sxs-lookup"><span data-stu-id="72ba5-224">The following code is in `test.sql`.</span></span>  
  
 `:setvar SQLCMDLOGINTIMEOUT 60`  
  
 `:setvar server "testserver"`  
  
 `:connect $(server) -l $(SQLCMDLOGINTIMEOUT)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName, LastName`  
  
 `FROM Person.Person;`  
  
 `The script is then called by using sqlcmd:`  
  
 `sqlcmd -i c:\test.sql`  
  
### <a name="b-using-the-setvar-command-interactively"></a><span data-ttu-id="72ba5-225">B.</span><span class="sxs-lookup"><span data-stu-id="72ba5-225">B.</span></span> <span data-ttu-id="72ba5-226">Utilizzo interattivo del comando setvar</span><span class="sxs-lookup"><span data-stu-id="72ba5-226">Using the setvar command interactively</span></span>  
 <span data-ttu-id="72ba5-227">Nell'esempio seguente viene illustrato come impostare una variabile di scripting in modo interattivo tramite il comando `setvar` .</span><span class="sxs-lookup"><span data-stu-id="72ba5-227">The following example shows how to set a scripting variable interactively by using the `setvar` command.</span></span>  
  
 `sqlcmd`  
  
 `:setvar  MYDATABASE AdventureWorks2012`  
  
 `USE $(MYDATABASE);`  
  
 `GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Changed database context to 'AdventureWorks2012'`  
  
 `1>`  
  
### <a name="c-using-command-prompt-environment-variables-within-sqlcmd"></a><span data-ttu-id="72ba5-228">C.</span><span class="sxs-lookup"><span data-stu-id="72ba5-228">C.</span></span> <span data-ttu-id="72ba5-229">Utilizzo delle variabili di ambiente dal prompt del comandi all'interno di sqlcmd</span><span class="sxs-lookup"><span data-stu-id="72ba5-229">Using command prompt environment variables within sqlcmd</span></span>  
 <span data-ttu-id="72ba5-230">Nell'esempio seguente vengono impostate quattro variabili di ambiente `are` , che vengono quindi chiamate da `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="72ba5-230">In the following example, four environment variables `are` set and then called from `sqlcmd`.</span></span>  
  
 `C:\>SET tablename=Person.Person`  
  
 `C:\>SET col1=FirstName`  
  
 `C:\>SET col2=LastName`  
  
 `C:\>SET title=Ms.`  
  
 `C:\>sqlcmd -d AdventureWorks2012`  
  
 `1> SELECT TOP 5 $(col1) + ' ' + $(col2) AS Name`  
  
 `2> FROM $(tablename)`  
  
 `3> WHERE Title ='$(title)'`  
  
 `4> GO`  
  
### <a name="d-using-user-level-environment-variables-within-sqlcmd"></a><span data-ttu-id="72ba5-231">D.</span><span class="sxs-lookup"><span data-stu-id="72ba5-231">D.</span></span> <span data-ttu-id="72ba5-232">Utilizzo di variabili di ambiente a livello di utente all'interno di sqlcmd</span><span class="sxs-lookup"><span data-stu-id="72ba5-232">Using user-level environment variables within sqlcmd</span></span>  
 <span data-ttu-id="72ba5-233">Nell'esempio seguente viene impostata al prompt dei comandi la variabile di ambiente a livello di utente `%Temp%` , che viene quindi passata al file di input `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="72ba5-233">In the following example the user-level environmental variable `%Temp%` is set at the command prompt and passed to the `sqlcmd` input file.</span></span> <span data-ttu-id="72ba5-234">Per ottenere la variabile di ambiente a livello di utente, nel **Pannello di controllo**fare doppio clic su **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="72ba5-234">To obtain the user-level environment variable, in **Control Panel**, double-click **System**.</span></span> <span data-ttu-id="72ba5-235">Fare clic sulla scheda **Avanzate** e quindi fare clic sul pulsante **Variabili d'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="72ba5-235">Click the **Advance** tab, and then click **Environment Variables**.</span></span>  
  
 <span data-ttu-id="72ba5-236">Il codice seguente è presente nel file di input `c:\testscript.txt`:</span><span class="sxs-lookup"><span data-stu-id="72ba5-236">The following code is in the input file `c:\testscript.txt`:</span></span>  
  
 `:OUT $(MyTempDirectory)`  
  
 `USE AdventureWorks2012;`  
  
 `SELECT FirstName`  
  
 `FROM AdventureWorks2012.Person.Person`  
  
 <span data-ttu-id="72ba5-237">`WHERE BusinessEntityID` `< 5;`</span><span class="sxs-lookup"><span data-stu-id="72ba5-237">`WHERE BusinessEntityID` `< 5;`</span></span>  
  
 <span data-ttu-id="72ba5-238">Il codice seguente viene immesso al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="72ba5-238">This following code is entered at the command prompt:</span></span>  
  
 `C:\ >SET MyTempDirectory=%Temp%\output.txt`  
  
 `C:\ >sqlcmd -i C:\testscript.txt`  
  
 <span data-ttu-id="72ba5-239">Il risultato seguente viene inviato al file di output C:\Documents and Settings\\<utente>\>\Local Settings\Temp\output.txt.</span><span class="sxs-lookup"><span data-stu-id="72ba5-239">The following result is sent to the output file C:\Documents and Settings\\<user\>\Local Settings\Temp\output.txt.</span></span>  
  
 `Changed database context to 'AdventureWorks2012'.`  
  
 `FirstName`  
  
 `--------------------------------------------------`  
  
 `Gustavo`  
  
 `Catherine`  
  
 `Kim`  
  
 `Humberto`  
  
 `(4 rows affected)`  
  
### <a name="e-using-a-startup-script"></a><span data-ttu-id="72ba5-240">E.</span><span class="sxs-lookup"><span data-stu-id="72ba5-240">E.</span></span> <span data-ttu-id="72ba5-241">Utilizzo di uno script di avvio</span><span class="sxs-lookup"><span data-stu-id="72ba5-241">Using a startup script</span></span>  
 <span data-ttu-id="72ba5-242">Uno script di avvio di **sqlcmd** viene eseguito all'avvio di **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="72ba5-242">A **sqlcmd** startup script is executed when **sqlcmd** is started.</span></span> <span data-ttu-id="72ba5-243">Nell'esempio seguente viene impostata la variabile di ambiente `SQLCMDINI`.</span><span class="sxs-lookup"><span data-stu-id="72ba5-243">The following example sets the environment variable `SQLCMDINI`.</span></span> <span data-ttu-id="72ba5-244">Di seguito è riportato il contenuto di `init.sql.`</span><span class="sxs-lookup"><span data-stu-id="72ba5-244">This is the contents of `init.sql.`</span></span>  
  
 `SET NOCOUNT ON`  
  
 `GO`  
  
 `DECLARE @nt_username nvarchar(128)`  
  
 `SET @nt_username = (SELECT rtrim(convert(nvarchar(128), nt_username))`  
  
 `FROM sys.dm_exec_sessions WHERE spid = @@SPID)`  
  
 `SELECT  @nt_username + ' is connected to ' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('servername'))) +`  
  
 `' (' +`  
  
 `rtrim(CONVERT(nvarchar(20), SERVERPROPERTY('productversion'))) +`  
  
 `')'`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH 100`  
  
 `SET NOCOUNT OFF`  
  
 `GO`  
  
 `:setvar SQLCMDMAXFIXEDTYPEWIDTH`  
  
 <span data-ttu-id="72ba5-245">Di conseguenza, viene chiamato il file `init.sql` all'avvio di `sqlcmd` .</span><span class="sxs-lookup"><span data-stu-id="72ba5-245">This calls the `init.sql` file when `sqlcmd` is started.</span></span>  
  
 `C:\> SET sqlcmdini=c:\init.sql`  
  
 `>1 Sqlcmd`  
  
 <span data-ttu-id="72ba5-246">Di seguito è riportato l'output.</span><span class="sxs-lookup"><span data-stu-id="72ba5-246">This is the output.</span></span>  
  
 `>1 < user > is connected to < server > (9.00.2047.00)`  
  
> [!NOTE]  
>  <span data-ttu-id="72ba5-247">L'opzione **-X** disabilita la funzionalità degli script di avvio.</span><span class="sxs-lookup"><span data-stu-id="72ba5-247">The **-X** option disables the startup script feature.</span></span>  
  
### <a name="f-variable-expansion"></a><span data-ttu-id="72ba5-248">F.</span><span class="sxs-lookup"><span data-stu-id="72ba5-248">F.</span></span> <span data-ttu-id="72ba5-249">Espansione delle variabili</span><span class="sxs-lookup"><span data-stu-id="72ba5-249">Variable expansion</span></span>  
 <span data-ttu-id="72ba5-250">L'esempio seguente illustra l'uso dei dati sotto forma di variabile di **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="72ba5-250">The following example shows working with data in the form of a **sqlcmd** variable.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `CREATE TABLE AdventureWorks2012.dbo.VariableTest`  
  
 `(`  
  
 `Col1 nvarchar(50)`  
  
 `);`  
  
 `GO`  
  
 <span data-ttu-id="72ba5-251">Inserire una riga nella colonna `Col1` di `dbo.VariableTest` contenente il valore `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="72ba5-251">Insert one row into `Col1` of `dbo.VariableTest` that contains the value `$(tablename)`.</span></span>  
  
 `INSERT INTO AdventureWorks2012.dbo.VariableTest(Col1)`  
  
 `VALUES('$(tablename)');`  
  
 `GO`  
  
 <span data-ttu-id="72ba5-252">Nel prompt di `sqlcmd` , se non viene impostata alcuna variabile su `$(tablename)`, la riga viene restituita dalle istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="72ba5-252">At the `sqlcmd` prompt, when no variable is set equal to `$(tablename)`, the following statements return the row.</span></span>  
  
 `C:\> sqlcmd`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>2 GO`  
  
 `>3 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>4 GO`  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `>1 Col1`  
  
 `>2 ------------------`  
  
 `>3 $(tablename)`  
  
 `>4`  
  
 `>5 (1 rows affected)`  
  
 <span data-ttu-id="72ba5-253">A condizione che la variabile `MyVar` sia impostata su `$(tablename)`.</span><span class="sxs-lookup"><span data-stu-id="72ba5-253">Given the variable `MyVar` is set to `$(tablename)`.</span></span>  
  
 `>6 :setvar MyVar $(tablename)`  
  
 <span data-ttu-id="72ba5-254">Queste istruzioni restituiscono la riga e il messaggio "Variabile di scripting 'tablename' non definita".</span><span class="sxs-lookup"><span data-stu-id="72ba5-254">These statements return the row and also return the message "'tablename' scripting variable not defined."</span></span>  
  
 `>6 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(tablename)';`  
  
 `>7 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(tablename)';`  
  
 `>2 GO`  
  
 <span data-ttu-id="72ba5-255">La riga viene restituita dalle istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="72ba5-255">These statements return the row.</span></span>  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = '$(MyVar)';`  
  
 `>2 GO`  
  
 `>1 SELECT Col1 FROM dbo.VariableTest WHERE Col1 = N'$(MyVar)';`  
  
 `>2 GO`  
  
## <a name="see-also"></a><span data-ttu-id="72ba5-256">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72ba5-256">See Also</span></span>  
 <span data-ttu-id="72ba5-257">[Utilizzo dell'utilità sqlcmd](sqlcmd-use-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="72ba5-257">[Use the sqlcmd Utility](sqlcmd-use-the-utility.md) </span></span>  
 <span data-ttu-id="72ba5-258">[Utilità sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="72ba5-258">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="72ba5-259">Guida di riferimento alle utilità del prompt dei comandi &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="72ba5-259">Command Prompt Utility Reference &#40;Database Engine&#41;</span></span>](../../tools/command-prompt-utility-reference-database-engine.md)  
  
  
