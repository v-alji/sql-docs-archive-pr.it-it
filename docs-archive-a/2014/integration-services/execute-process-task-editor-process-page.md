---
title: Editor attività Esegui processo (pagina processo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executeprocesstask.process.f1
helpviewer_keywords:
- Execute Process Task Editor
ms.assetid: 0fc22406-e79b-47a4-a7e4-108d4ce6202f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ce8629be2c07ae4caac4586b266936a908e71499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710983"
---
# <a name="execute-process-task-editor-process-page"></a><span data-ttu-id="dce1f-102">Execute Process Task Editor (Process Page)</span><span class="sxs-lookup"><span data-stu-id="dce1f-102">Execute Process Task Editor (Process Page)</span></span>
  <span data-ttu-id="dce1f-103">Utilizzare la pagina **Processo** della finestra di dialogo **Editor attività Esegui processo** per configurare le opzioni di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="dce1f-103">Use the **Process** page of the **Execute Process Task Editor** dialog box to configure the options that execute the process.</span></span> <span data-ttu-id="dce1f-104">Tali opzioni includono il file eseguibile da avviare, il relativo percorso, gli argomenti del prompt dei comandi, nonché le variabili per la generazione dell'input e l'acquisizione dell'output.</span><span class="sxs-lookup"><span data-stu-id="dce1f-104">These options include the executable to run, its location, command prompt arguments, and the variables that provide input and capture output.</span></span>  
  
 <span data-ttu-id="dce1f-105">Per ulteriori informazioni su questa attività, vedere [Execute Process Task](control-flow/execute-process-task.md).</span><span class="sxs-lookup"><span data-stu-id="dce1f-105">To learn about this task, see [Execute Process Task](control-flow/execute-process-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dce1f-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="dce1f-106">Options</span></span>  
 <span data-ttu-id="dce1f-107">**RequireFullFileName**</span><span class="sxs-lookup"><span data-stu-id="dce1f-107">**RequireFullFileName**</span></span>  
 <span data-ttu-id="dce1f-108">Consente di indicare se l'attività deve avere esito negativo nel caso in cui il file eseguibile non venga trovato nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="dce1f-108">Indicate whether the task should fail if the executable is not found at the specified location.</span></span>  
  
 <span data-ttu-id="dce1f-109">**File eseguibile**</span><span class="sxs-lookup"><span data-stu-id="dce1f-109">**Executable**</span></span>  
 <span data-ttu-id="dce1f-110">Consente di digitare il nome del file eseguibile da avviare.</span><span class="sxs-lookup"><span data-stu-id="dce1f-110">Type the name of the executable to run.</span></span>  
  
 <span data-ttu-id="dce1f-111">**Argomenti**</span><span class="sxs-lookup"><span data-stu-id="dce1f-111">**Arguments**</span></span>  
 <span data-ttu-id="dce1f-112">Consente di specificare gli argomenti del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="dce1f-112">Provide command prompt arguments.</span></span>  
  
 <span data-ttu-id="dce1f-113">**WorkingDirectory**</span><span class="sxs-lookup"><span data-stu-id="dce1f-113">**WorkingDirectory**</span></span>  
 <span data-ttu-id="dce1f-114">Digitare il percorso della cartella contenente il file eseguibile oppure fare clic sul pulsante sfoglia **(...)** per individuare la cartella.</span><span class="sxs-lookup"><span data-stu-id="dce1f-114">Type the path of the folder that contains the executable, or click the browse button **(...)** and locate the folder.</span></span>  
  
 <span data-ttu-id="dce1f-115">**StandardInputVariable**</span><span class="sxs-lookup"><span data-stu-id="dce1f-115">**StandardInputVariable**</span></span>  
 <span data-ttu-id="dce1f-116">Consente di selezionare una variabile per l'invio dell'input al processo. È anche possibile fare clic su \<**New variable...**> per crearne una nuova:</span><span class="sxs-lookup"><span data-stu-id="dce1f-116">Select a variable to provide the input to the process, or click \<**New variable...**> to create a new variable:</span></span>  
  
 <span data-ttu-id="dce1f-117">**Argomenti correlati:**  [aggiungere una variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="dce1f-117">**Related Topics:**  [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="dce1f-118">**StandardOutputVariable**</span><span class="sxs-lookup"><span data-stu-id="dce1f-118">**StandardOutputVariable**</span></span>  
 <span data-ttu-id="dce1f-119">Consente di selezionare una variabile per l'acquisizione dell'output del processo. È anche possibile fare clic su \<**New variable...**> per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="dce1f-119">Select a variable to capture the output of the process, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="dce1f-120">**StandardErrorVariable**</span><span class="sxs-lookup"><span data-stu-id="dce1f-120">**StandardErrorVariable**</span></span>  
 <span data-ttu-id="dce1f-121">Consente di selezionare una variabile per l'acquisizione dell'output degli errori del processore. È anche possibile fare clic su \<**New variable...**> per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="dce1f-121">Select a variable to capture the error output of the processor, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="dce1f-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span><span class="sxs-lookup"><span data-stu-id="dce1f-122">**FailTaskIfReturnCodeIsNotSuccessValue**</span></span>  
 <span data-ttu-id="dce1f-123">Consente di indicare se l'attività deve avere esito negativo nel caso in cui il codice di uscita del processo non corrisponda al valore specificato in **SuccessValue**.</span><span class="sxs-lookup"><span data-stu-id="dce1f-123">Indicate whether the task fails if the process exit code is different from the value specified in **SuccessValue**.</span></span>  
  
 <span data-ttu-id="dce1f-124">**SuccessValue**</span><span class="sxs-lookup"><span data-stu-id="dce1f-124">**SuccessValue**</span></span>  
 <span data-ttu-id="dce1f-125">Consente di specificare il valore restituito dal file eseguibile per segnalare l'esito positivo.</span><span class="sxs-lookup"><span data-stu-id="dce1f-125">Specify the value returned by the executable to indicate success.</span></span> <span data-ttu-id="dce1f-126">Per impostazione predefinita, questo valore è impostato su **0**.</span><span class="sxs-lookup"><span data-stu-id="dce1f-126">By default this value is set to **0**.</span></span>  
  
 <span data-ttu-id="dce1f-127">**TimeOut**</span><span class="sxs-lookup"><span data-stu-id="dce1f-127">**TimeOut**</span></span>  
 <span data-ttu-id="dce1f-128">Consente di specificare il numero di secondi di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="dce1f-128">Specify the number of seconds that the process can run.</span></span> <span data-ttu-id="dce1f-129">Il valore **0** indica che non è previsto alcun timeout e il processo viene eseguito fino al completamento o finché non si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="dce1f-129">A value of **0** indicates that no time-out value is used, and the process runs until it is completed or until an error occurs.</span></span>  
  
 <span data-ttu-id="dce1f-130">**TerminateProcessAfterTimeOut**</span><span class="sxs-lookup"><span data-stu-id="dce1f-130">**TerminateProcessAfterTimeOut**</span></span>  
 <span data-ttu-id="dce1f-131">Consente di indicare se il processo deve essere terminato allo scadere del periodo di timeout specificato nell'opzione **TimeOut** .</span><span class="sxs-lookup"><span data-stu-id="dce1f-131">Indicate whether the process is forced to end after the time-out period specified by the **TimeOut** option.</span></span> <span data-ttu-id="dce1f-132">Questa opzione è disponibile solo se **TimeOut** non è impostata su **0**.</span><span class="sxs-lookup"><span data-stu-id="dce1f-132">This option is available only if **TimeOut** is not **0**.</span></span>  
  
 <span data-ttu-id="dce1f-133">**WindowStyle**</span><span class="sxs-lookup"><span data-stu-id="dce1f-133">**WindowStyle**</span></span>  
 <span data-ttu-id="dce1f-134">Consente di specificare lo stile della finestra in cui viene eseguito il processo.</span><span class="sxs-lookup"><span data-stu-id="dce1f-134">Specify the window style in which to run the process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce1f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dce1f-135">See Also</span></span>  
 <span data-ttu-id="dce1f-136">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dce1f-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="dce1f-137">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="dce1f-137">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
