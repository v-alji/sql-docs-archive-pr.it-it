---
title: Editor attività script (pagina script) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scripttask.script.f1
helpviewer_keywords:
- Script Task Editor
ms.assetid: 93da0e0d-83f5-406d-b144-4cce216571cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4eec491cc689d7d5c616e0819075e1ee5159d4e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712155"
---
# <a name="script-task-editor-script-page"></a><span data-ttu-id="6cb36-102">Editor attività Script (pagina Script)</span><span class="sxs-lookup"><span data-stu-id="6cb36-102">Script Task Editor (Script Page)</span></span>
  <span data-ttu-id="6cb36-103">Utilizzare la pagina **Script** della finestra di dialogo **Editor attività Script** per impostare le proprietà dello script e specificare le variabili accessibili per lo script.</span><span class="sxs-lookup"><span data-stu-id="6cb36-103">Use the **Script** page of the **Script Task Editor** dialog box to set script properties and specify variables that can be accessed by the script.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cb36-104">In [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] e versioni successive, tutti gli script sono precompilati.</span><span class="sxs-lookup"><span data-stu-id="6cb36-104">In [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] and later versions, all scripts are precompiled.</span></span> <span data-ttu-id="6cb36-105">Nelle versioni precedenti, si imposta una proprietà **PrecompileScriptIntoBinaryCode** per specificare che lo script è stato precompilato.</span><span class="sxs-lookup"><span data-stu-id="6cb36-105">In earlier versions, you set a **PrecompileScriptIntoBinaryCode** property to specify that the script was precompiled.</span></span>  
  
 <span data-ttu-id="6cb36-106">Per ulteriori informazioni sull'attività Script, vedere [Script Task](control-flow/script-task.md) e [Configurazione dell'attività Script nell'editor attività Script](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6cb36-106">To learn more about the Script task, see [Script Task](control-flow/script-task.md) and [Configuring the Script Task in the Script Task Editor](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span></span> <span data-ttu-id="6cb36-107">Per informazioni sulla programmazione dell'attività Script, vedere [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="6cb36-107">To learn about programming the Script task, see [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6cb36-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6cb36-108">Options</span></span>  
 <span data-ttu-id="6cb36-109">**ScriptLanguage**</span><span class="sxs-lookup"><span data-stu-id="6cb36-109">**ScriptLanguage**</span></span>  
 <span data-ttu-id="6cb36-110">Selezionare il linguaggio di scripting per l'attività, [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic o [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="6cb36-110">Select the scripting language for the task, either [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="6cb36-111">Dopo avere creato uno script per l'attività, non è possibile modificare il valore della proprietà **ScriptLanguage** .</span><span class="sxs-lookup"><span data-stu-id="6cb36-111">After you have created a script for the task, you cannot change the value of the **ScriptLanguage** property.</span></span>  
  
 <span data-ttu-id="6cb36-112">Per impostare il linguaggio di scripting predefinito per l'attività Script, utilizzare l'opzione **Linguaggio di scripting** nella pagina **Generale** della finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="6cb36-112">To set the default scripting language for the Script task, use the **Scripting language** option on **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="6cb36-113">Per ulteriori informazioni, vedere [General Page](general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="6cb36-113">For more information, see [General Page](general-page-of-integration-services-designers-options.md).</span></span>  
  
 <span data-ttu-id="6cb36-114">**EntryPoint**</span><span class="sxs-lookup"><span data-stu-id="6cb36-114">**EntryPoint**</span></span>  
 <span data-ttu-id="6cb36-115">Specificare il metodo chiamato dal runtime [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] come punto di ingresso nel codice dell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="6cb36-115">Specify the method that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] runtime calls as the entry point into the code of the Script task.</span></span> <span data-ttu-id="6cb36-116">Il metodo specificato deve essere nella classe ScriptMain del [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] progetto Tools for Applications (VSTA) la classe ScriptMain è la classe predefinita generata dai modelli di script.</span><span class="sxs-lookup"><span data-stu-id="6cb36-116">The specified method must be in the ScriptMain class of the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) project The ScriptMain class is the default class generated by the script templates.</span></span>  
  
 <span data-ttu-id="6cb36-117">Se si modifica il nome del metodo nel progetto VSTA, è necessario modificare il valore della proprietà **EntryPoint** .</span><span class="sxs-lookup"><span data-stu-id="6cb36-117">If you change the name of the method in the VSTA project, you must change the value of the **EntryPoint** property.</span></span>  
  
 <span data-ttu-id="6cb36-118">**ReadOnlyVariables**</span><span class="sxs-lookup"><span data-stu-id="6cb36-118">**ReadOnlyVariables**</span></span>  
 <span data-ttu-id="6cb36-119">Digitare un elenco delimitato da virgole di variabili di sola lettura disponibili per lo script oppure fare clic sul pulsante con i puntini di sospensione (**...**) e selezionare le variabili nella finestra di dialogo **Seleziona variabili**.</span><span class="sxs-lookup"><span data-stu-id="6cb36-119">Type a comma-separated list of read-only variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cb36-120">Per i nomi delle variabili viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="6cb36-120">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="6cb36-121">**ReadWriteVariables**</span><span class="sxs-lookup"><span data-stu-id="6cb36-121">**ReadWriteVariables**</span></span>  
 <span data-ttu-id="6cb36-122">Digitare un elenco delimitato da virgole di variabili di lettura/scrittura disponibili per lo script oppure fare clic sul pulsante con i puntini di sospensione (**...**) e selezionare le variabili nella finestra di dialogo **Seleziona variabili**.</span><span class="sxs-lookup"><span data-stu-id="6cb36-122">Type a comma-separated list of read/write variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cb36-123">Per i nomi delle variabili viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="6cb36-123">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="6cb36-124">**Modifica script**</span><span class="sxs-lookup"><span data-stu-id="6cb36-124">**Edit Script**</span></span>  
 <span data-ttu-id="6cb36-125">Apre VSTA IDE, dove è possibile creare o modificare lo script.</span><span class="sxs-lookup"><span data-stu-id="6cb36-125">Opens the VSTA IDE where you can create or modify the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb36-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cb36-126">See Also</span></span>  
 <span data-ttu-id="6cb36-127">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6cb36-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6cb36-128">[Pagina generale](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="6cb36-128">[General Page](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="6cb36-129">[Editor attività script &#40;pagina generale&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="6cb36-129">[Script Task Editor &#40;General Page&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="6cb36-130">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="6cb36-130">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="6cb36-131">[Esempi di attività script](extending-packages-scripting-task-examples/script-task-examples.md) </span><span class="sxs-lookup"><span data-stu-id="6cb36-131">[Script Task Examples](extending-packages-scripting-task-examples/script-task-examples.md) </span></span>  
 <span data-ttu-id="6cb36-132">[Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6cb36-132">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="6cb36-133">Aggiungere, eliminare o modificare l'ambito di una variabile definita dall'utente in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="6cb36-133">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
