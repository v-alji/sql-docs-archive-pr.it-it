---
title: Editor attività Message Queue (pagina ricezione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.receive.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 7028756d-1dcc-480c-bbcd-e9654f0772a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f45aa579d37d1fdd3a3124eea972014ce839fdc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727036"
---
# <a name="message-queue-task-editor-receive-page"></a><span data-ttu-id="4b61e-102">Editor attività Message Queue (pagina Ricezione)</span><span class="sxs-lookup"><span data-stu-id="4b61e-102">Message Queue Task Editor (Receive Page)</span></span>
  <span data-ttu-id="4b61e-103">Usare la pagina **Ricezione** della finestra di dialogo **Editor attività Message Queue** per configurare un'attività Message Queue che consenta di ricevere messaggi di [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="4b61e-103">Use the **Receive** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to receive [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ) messages.</span></span>  
  
 <span data-ttu-id="4b61e-104">Per ulteriori informazioni su questa attività, vedere [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="4b61e-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4b61e-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4b61e-105">Options</span></span>  
 <span data-ttu-id="4b61e-106">**RemoveFromMessageQueue**</span><span class="sxs-lookup"><span data-stu-id="4b61e-106">**RemoveFromMessageQueue**</span></span>  
 <span data-ttu-id="4b61e-107">Consente di indicare se rimuovere il messaggio dalla coda dopo averlo ricevuto.</span><span class="sxs-lookup"><span data-stu-id="4b61e-107">Indicate whether to remove the message from the queue after it is received.</span></span> <span data-ttu-id="4b61e-108">Per impostazione predefinita, questo valore è impostato su `False`.</span><span class="sxs-lookup"><span data-stu-id="4b61e-108">By default, this value is set to `False`.</span></span>  
  
 <span data-ttu-id="4b61e-109">**ErrorIfMessageTimeOut**</span><span class="sxs-lookup"><span data-stu-id="4b61e-109">**ErrorIfMessageTimeOut**</span></span>  
 <span data-ttu-id="4b61e-110">Consente di indicare se l'attività viene interrotta quando si verifica il timeout del messaggio, visualizzando un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="4b61e-110">Indicate whether the task fails when the message times out, displaying an error message.</span></span> <span data-ttu-id="4b61e-111">Il valore predefinito è `False`.</span><span class="sxs-lookup"><span data-stu-id="4b61e-111">The default is `False`.</span></span>  
  
 <span data-ttu-id="4b61e-112">**TimeoutAfter**</span><span class="sxs-lookup"><span data-stu-id="4b61e-112">**TimeoutAfter**</span></span>  
 <span data-ttu-id="4b61e-113">Se si sceglie di visualizzare un messaggio di errore in caso di errore dell'attività, specificare il numero di secondi di attesa prima della visualizzazione del messaggio di timeout.</span><span class="sxs-lookup"><span data-stu-id="4b61e-113">If you choose to display an error message on task failure, specify the number of seconds to wait before displaying the time-out message.</span></span>  
  
 <span data-ttu-id="4b61e-114">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="4b61e-114">**MessageType**</span></span>  
 <span data-ttu-id="4b61e-115">Consente di selezionare il tipo di messaggio.</span><span class="sxs-lookup"><span data-stu-id="4b61e-115">Select the message type.</span></span> <span data-ttu-id="4b61e-116">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4b61e-116">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="4b61e-117">valore</span><span class="sxs-lookup"><span data-stu-id="4b61e-117">Value</span></span>|<span data-ttu-id="4b61e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b61e-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b61e-119">**Messaggio file di dati**</span><span class="sxs-lookup"><span data-stu-id="4b61e-119">**Data file message**</span></span>|<span data-ttu-id="4b61e-120">Il messaggio viene archiviato in un file.</span><span class="sxs-lookup"><span data-stu-id="4b61e-120">The message is stored in a file.</span></span> <span data-ttu-id="4b61e-121">La selezione del valore determina la visualizzazione dell'opzione dinamica **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-121">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="4b61e-122">**Messaggio variabili**</span><span class="sxs-lookup"><span data-stu-id="4b61e-122">**Variable message**</span></span>|<span data-ttu-id="4b61e-123">Il messaggio viene archiviato in una variabile.</span><span class="sxs-lookup"><span data-stu-id="4b61e-123">The message is stored in a variable.</span></span> <span data-ttu-id="4b61e-124">La selezione del valore determina la visualizzazione dell'opzione dinamica **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-124">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="4b61e-125">**Messaggio stringa**</span><span class="sxs-lookup"><span data-stu-id="4b61e-125">**String message**</span></span>|<span data-ttu-id="4b61e-126">Il messaggio viene archiviato nell'attività Message Queue.</span><span class="sxs-lookup"><span data-stu-id="4b61e-126">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="4b61e-127">La selezione del valore determina la visualizzazione dell'opzione dinamica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-127">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
|<span data-ttu-id="4b61e-128">**Messaggio stringa in variabile**</span><span class="sxs-lookup"><span data-stu-id="4b61e-128">**String message to variable**</span></span>|<span data-ttu-id="4b61e-129">Il messaggio viene archiviato in una variabile.</span><span class="sxs-lookup"><span data-stu-id="4b61e-129">The message</span></span><br /><br /> <span data-ttu-id="4b61e-130">La selezione del valore determina la visualizzazione dell'opzione dinamica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-130">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="4b61e-131">Opzioni dinamiche di MessageType</span><span class="sxs-lookup"><span data-stu-id="4b61e-131">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="4b61e-132">MessageType = Messaggio file di dati</span><span class="sxs-lookup"><span data-stu-id="4b61e-132">MessageType = Data file message</span></span>  
 <span data-ttu-id="4b61e-133">**SaveFileAs**</span><span class="sxs-lookup"><span data-stu-id="4b61e-133">**SaveFileAs**</span></span>  
 <span data-ttu-id="4b61e-134">Digitare il percorso del file da usare o fare clic sul pulsante con i puntini di sospensione **(...)** e quindi individuare il file.</span><span class="sxs-lookup"><span data-stu-id="4b61e-134">Type the path of the file to use, or click the ellipsis button **(...)** and then locate the file.</span></span>  
  
 <span data-ttu-id="4b61e-135">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="4b61e-135">**Overwrite**</span></span>  
 <span data-ttu-id="4b61e-136">Consente di indicare se sovrascrivere i dati in un file esistente durante il salvataggio del contenuto di un messaggio con file di dati.</span><span class="sxs-lookup"><span data-stu-id="4b61e-136">Indicate whether to overwrite the data in an existing file when saving the contents of a data file message.</span></span> <span data-ttu-id="4b61e-137">Il valore predefinito è `False`.</span><span class="sxs-lookup"><span data-stu-id="4b61e-137">The default is `False`.</span></span>  
  
 <span data-ttu-id="4b61e-138">**Filter**</span><span class="sxs-lookup"><span data-stu-id="4b61e-138">**Filter**</span></span>  
 <span data-ttu-id="4b61e-139">Consente di specificare se applicare un filtro al messaggio.</span><span class="sxs-lookup"><span data-stu-id="4b61e-139">Specify whether to apply a filter to the message.</span></span> <span data-ttu-id="4b61e-140">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4b61e-140">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="4b61e-141">valore</span><span class="sxs-lookup"><span data-stu-id="4b61e-141">Value</span></span>|<span data-ttu-id="4b61e-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b61e-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b61e-143">**Nessun filtro**</span><span class="sxs-lookup"><span data-stu-id="4b61e-143">**No filter**</span></span>|<span data-ttu-id="4b61e-144">L'attività non filtra i messaggi.</span><span class="sxs-lookup"><span data-stu-id="4b61e-144">The task does not filter messages.</span></span> <span data-ttu-id="4b61e-145">La selezione del valore determina la visualizzazione dell'opzione dinamica **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-145">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="4b61e-146">**Dal pacchetto**</span><span class="sxs-lookup"><span data-stu-id="4b61e-146">**From package**</span></span>|<span data-ttu-id="4b61e-147">Il messaggio riceve solo messaggi dal pacchetto specificato.</span><span class="sxs-lookup"><span data-stu-id="4b61e-147">The message receives only messages from the specified package.</span></span> <span data-ttu-id="4b61e-148">La selezione del valore determina la visualizzazione dell'opzione dinamica **Identifier**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-148">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="4b61e-149">Opzioni dinamiche di filtro</span><span class="sxs-lookup"><span data-stu-id="4b61e-149">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="4b61e-150">Filter = Nessun filtro</span><span class="sxs-lookup"><span data-stu-id="4b61e-150">Filter = No filter</span></span>  
 <span data-ttu-id="4b61e-151">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="4b61e-151">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="4b61e-152">Questa opzione è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4b61e-152">This option is read-only.</span></span> <span data-ttu-id="4b61e-153">Può essere vuota o contenere il GUID di un pacchetto se la proprietà Filter è stata impostata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4b61e-153">It may be blank or contain the GUID of a package when the Filter property was previously set.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="4b61e-154">Filter = Dal pacchetto</span><span class="sxs-lookup"><span data-stu-id="4b61e-154">Filter = From package</span></span>  
 <span data-ttu-id="4b61e-155">**Identificatore**</span><span class="sxs-lookup"><span data-stu-id="4b61e-155">**Identifier**</span></span>  
 <span data-ttu-id="4b61e-156">Se si sceglie di applicare un filtro, digitare l'identificatore univoco del pacchetto da cui si possono ricevere i messaggi oppure fare clic sul pulsante con i puntini di sospensione **(...)** e specificare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4b61e-156">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="4b61e-157">**Argomenti correlati:** [Seleziona pacchetto](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="4b61e-157">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="4b61e-158">MessageType = Messaggio variabili</span><span class="sxs-lookup"><span data-stu-id="4b61e-158">MessageType = Variable message</span></span>  
 <span data-ttu-id="4b61e-159">**Filter**</span><span class="sxs-lookup"><span data-stu-id="4b61e-159">**Filter**</span></span>  
 <span data-ttu-id="4b61e-160">Consente di specificare se applicare un filtro ai messaggi.</span><span class="sxs-lookup"><span data-stu-id="4b61e-160">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="4b61e-161">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4b61e-161">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="4b61e-162">valore</span><span class="sxs-lookup"><span data-stu-id="4b61e-162">Value</span></span>|<span data-ttu-id="4b61e-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b61e-163">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b61e-164">**Nessun filtro**</span><span class="sxs-lookup"><span data-stu-id="4b61e-164">**No filter**</span></span>|<span data-ttu-id="4b61e-165">L'attività non filtra i messaggi.</span><span class="sxs-lookup"><span data-stu-id="4b61e-165">The task does not filter messages.</span></span> <span data-ttu-id="4b61e-166">La selezione del valore determina la visualizzazione dell'opzione dinamica **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-166">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="4b61e-167">**Dal pacchetto**</span><span class="sxs-lookup"><span data-stu-id="4b61e-167">**From package**</span></span>|<span data-ttu-id="4b61e-168">Il messaggio riceve solo messaggi dal pacchetto specificato.</span><span class="sxs-lookup"><span data-stu-id="4b61e-168">The message receives only messages from the specified package.</span></span> <span data-ttu-id="4b61e-169">La selezione del valore determina la visualizzazione dell'opzione dinamica **Identifier**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-169">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
 <span data-ttu-id="4b61e-170">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="4b61e-170">**Variable**</span></span>  
 <span data-ttu-id="4b61e-171">Digitare il nome della variabile oppure fare clic su \<**New variable...**> per configurare una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="4b61e-171">Type the variable name, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="4b61e-172">**Argomenti correlati:** [Aggiungi variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="4b61e-172">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="4b61e-173">Opzioni dinamiche di filtro</span><span class="sxs-lookup"><span data-stu-id="4b61e-173">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="4b61e-174">Filter = Nessun filtro</span><span class="sxs-lookup"><span data-stu-id="4b61e-174">Filter = No filter</span></span>  
 <span data-ttu-id="4b61e-175">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="4b61e-175">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="4b61e-176">Questa opzione è vuota.</span><span class="sxs-lookup"><span data-stu-id="4b61e-176">This option is blank.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="4b61e-177">Filter = Dal pacchetto</span><span class="sxs-lookup"><span data-stu-id="4b61e-177">Filter = From package</span></span>  
 <span data-ttu-id="4b61e-178">**Identificatore**</span><span class="sxs-lookup"><span data-stu-id="4b61e-178">**Identifier**</span></span>  
 <span data-ttu-id="4b61e-179">Se si sceglie di applicare un filtro, digitare l'identificatore univoco del pacchetto da cui si possono ricevere i messaggi oppure fare clic sul pulsante con i puntini di sospensione **(...)** e specificare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4b61e-179">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="4b61e-180">**Argomenti correlati:** [Seleziona pacchetto](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="4b61e-180">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="4b61e-181">MessageType = Messaggio stringa</span><span class="sxs-lookup"><span data-stu-id="4b61e-181">MessageType = String message</span></span>  
 <span data-ttu-id="4b61e-182">**Confronta**</span><span class="sxs-lookup"><span data-stu-id="4b61e-182">**Compare**</span></span>  
 <span data-ttu-id="4b61e-183">Consente di specificare se applicare un filtro ai messaggi.</span><span class="sxs-lookup"><span data-stu-id="4b61e-183">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="4b61e-184">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4b61e-184">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="4b61e-185">valore</span><span class="sxs-lookup"><span data-stu-id="4b61e-185">Value</span></span>|<span data-ttu-id="4b61e-186">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b61e-186">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b61e-187">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="4b61e-187">**None**</span></span>|<span data-ttu-id="4b61e-188">I messaggi non vengono confrontati.</span><span class="sxs-lookup"><span data-stu-id="4b61e-188">Messages are not compared.</span></span>|  
|<span data-ttu-id="4b61e-189">**Corrispondenza esatta**</span><span class="sxs-lookup"><span data-stu-id="4b61e-189">**Exact match**</span></span>|<span data-ttu-id="4b61e-190">I messaggi devono corrispondere esattamente alla stringa nell'opzione indicata **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="4b61e-190">Messages must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="4b61e-191">**Ignora maiuscole/minuscole**</span><span class="sxs-lookup"><span data-stu-id="4b61e-191">**Ignore case**</span></span>|<span data-ttu-id="4b61e-192">I messaggi devono corrispondere alla stringa indicata nell'opzione **CompareString** , ma nel confronto non viene rilevata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4b61e-192">Message must match the string in the **CompareString** option, but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="4b61e-193">**Stringa contenente**</span><span class="sxs-lookup"><span data-stu-id="4b61e-193">**Containing**</span></span>|<span data-ttu-id="4b61e-194">Il messaggio deve contenere la stringa indicata nell'opzione **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="4b61e-194">Message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="4b61e-195">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="4b61e-195">**CompareString**</span></span>  
 <span data-ttu-id="4b61e-196">Specificare la stringa con cui confrontare il messaggio, a meno che l'opzione **Compare** sia impostata su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-196">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
### <a name="messagetype--string-message-to-variable"></a><span data-ttu-id="4b61e-197">MessageType = Messaggio stringa in variabile</span><span class="sxs-lookup"><span data-stu-id="4b61e-197">MessageType = String message to variable</span></span>  
 <span data-ttu-id="4b61e-198">**Confronta**</span><span class="sxs-lookup"><span data-stu-id="4b61e-198">**Compare**</span></span>  
 <span data-ttu-id="4b61e-199">Consente di specificare se applicare un filtro ai messaggi.</span><span class="sxs-lookup"><span data-stu-id="4b61e-199">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="4b61e-200">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4b61e-200">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="4b61e-201">valore</span><span class="sxs-lookup"><span data-stu-id="4b61e-201">Value</span></span>|<span data-ttu-id="4b61e-202">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b61e-202">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b61e-203">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="4b61e-203">**None**</span></span>|<span data-ttu-id="4b61e-204">I messaggi non vengono confrontati.</span><span class="sxs-lookup"><span data-stu-id="4b61e-204">Messages are not compared.</span></span>|  
|<span data-ttu-id="4b61e-205">**Corrispondenza esatta**</span><span class="sxs-lookup"><span data-stu-id="4b61e-205">**Exact match**</span></span>|<span data-ttu-id="4b61e-206">I messaggi devono corrispondere esattamente alla stringa indicata nell'opzione **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="4b61e-206">The message must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="4b61e-207">**Ignora maiuscole/minuscole**</span><span class="sxs-lookup"><span data-stu-id="4b61e-207">**Ignore case**</span></span>|<span data-ttu-id="4b61e-208">I messaggi devono corrispondere alla stringa indicata nell'opzione **CompareString** , ma nel confronto non viene rilevata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4b61e-208">The message must match the string in the **CompareString** option but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="4b61e-209">**Stringa contenente**</span><span class="sxs-lookup"><span data-stu-id="4b61e-209">**Containing**</span></span>|<span data-ttu-id="4b61e-210">Il messaggio deve contenere la stringa indicata nell'opzione **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="4b61e-210">The message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="4b61e-211">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="4b61e-211">**CompareString**</span></span>  
 <span data-ttu-id="4b61e-212">Specificare la stringa con cui confrontare il messaggio, a meno che l'opzione **Compare** sia impostata su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="4b61e-212">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
 <span data-ttu-id="4b61e-213">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="4b61e-213">**Variable**</span></span>  
 <span data-ttu-id="4b61e-214">Digitare il nome della variabile per la memorizzazione del messaggio ricevuto oppure fare clic su \<**New variable...**> per configurare una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="4b61e-214">Type the name of the variable to hold the received message, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="4b61e-215">**Argomenti correlati:** [Aggiungi variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="4b61e-215">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b61e-216">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b61e-216">See Also</span></span>  
 <span data-ttu-id="4b61e-217">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4b61e-217">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4b61e-218">[Editor attività Message Queue &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="4b61e-218">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="4b61e-219">[Editor attività Message Queue &#40;Invia pagina&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="4b61e-219">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 <span data-ttu-id="4b61e-220">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="4b61e-220">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="4b61e-221">Attività Message Queue</span><span class="sxs-lookup"><span data-stu-id="4b61e-221">Message Queue Task</span></span>](control-flow/message-queue-task.md)  
  
  
