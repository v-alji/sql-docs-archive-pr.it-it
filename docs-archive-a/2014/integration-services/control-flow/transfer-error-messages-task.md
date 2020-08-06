---
title: Attività Trasferisci messaggi di errore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.f1
helpviewer_keywords:
- Transfer Error Messages task [Integration Services]
ms.assetid: da702289-035a-4d14-bd74-04461fbfee1b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952acc28a79fef7e7351c97400e05bc7ba5b9243
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623425"
---
# <a name="transfer-error-messages-task"></a><span data-ttu-id="1c9c4-102">Attività Trasferisci messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="1c9c4-102">Transfer Error Messages Task</span></span>
  <span data-ttu-id="1c9c4-103">L'attività Trasferisci messaggi di errore trasferisce uno o più messaggi di errore definiti dall'utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tra istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c9c4-103">The Transfer Error Messages task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined error messages between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1c9c4-104">I messaggi definiti dall'utente sono messaggi con un identificatore che è uguale o maggiore di 50000.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-104">User-defined messages are messages with an identifier that is equal to or greater than 50000.</span></span> <span data-ttu-id="1c9c4-105">I messaggi con identificatore minore di 50000 sono messaggi di errore di sistema e non possono essere trasferiti utilizzando l'attività Trasferisci messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-105">Messages with an identifier less than 50000 are system error messages, and cannot be transferred by using the Transfer Error Messages task.</span></span>  
  
 <span data-ttu-id="1c9c4-106">È possibile configurare l'attività Trasferisci messaggi di errore per il trasferimento di tutti i messaggi di errore o dei soli messaggi di errore specificati.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-106">The Transfer Error Messages task can be configured to transfer all error messages, or only the specified error messages.</span></span> <span data-ttu-id="1c9c4-107">I messaggi di errore definiti dall'utente possono essere disponibili in lingue diverse. È possibile configurare l'attività per il trasferimento dei soli messaggi nelle lingue selezionate.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-107">User-defined error messages may be available in a number of different languages and the task can be configured to transfer only messages in selected languages.</span></span> <span data-ttu-id="1c9c4-108">È necessario che nel server di destinazione sia inclusa la versione del messaggio che utilizza la tabella codici 1033, corrispondente all'inglese americano, per poter trasferire su tale server versioni del messaggio in altre lingue.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-108">A us_english version of the message that uses code page 1033 must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
 <span data-ttu-id="1c9c4-109">La tabella sysmessages del database master contiene tutti i messaggi di errore, sia di sistema che definiti dall'utente, usati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c9c4-109">The sysmessages table in the master database contains all the error messages-both system and user-defined-that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses.</span></span>  
  
 <span data-ttu-id="1c9c4-110">I messaggi definiti dall'utente da trasferire potrebbero essere già presenti nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-110">The user-defined messages to be transferred may already exist on the destination.</span></span> <span data-ttu-id="1c9c4-111">Un messaggio di errore è considerato duplicato se l'identificatore e la lingua corrispondono a quelli di un messaggio di errore esistente.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-111">An error message is defined as a duplicate error message if the identifier and the language are the same.</span></span> <span data-ttu-id="1c9c4-112">È possibile configurare l'attività Trasferisci messaggi di errore per la gestione dei messaggi di errore duplicati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c9c4-112">The Transfer Error Messages task can be configured to handle existing error messages in the following ways:</span></span>  
  
-   <span data-ttu-id="1c9c4-113">I messaggi di errore duplicati vengono sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-113">Overwrite existing error messages.</span></span>  
  
-   <span data-ttu-id="1c9c4-114">In presenza di messaggi di errore duplicati l'attività ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-114">Fail the task when duplicate messages exist.</span></span>  
  
-   <span data-ttu-id="1c9c4-115">I messaggi di errore duplicati vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-115">Skip duplicate error messages.</span></span>  
  
 <span data-ttu-id="1c9c4-116">In fase di esecuzione l'attività Trasferisci messaggi di errore si connette al server di origine e al server di destinazione utilizzando una o più gestioni connessioni SMO.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-116">At run time, the Transfer Error Messages task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="1c9c4-117">Le gestioni connessioni SMO vengono configurate separatamente dall'attività Trasferisci messaggi di errore, che tuttavia vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-117">The SMO connection manager is configured separately from the Transfer Error Messages task, and then is referenced in the Transfer Error Messages task.</span></span> <span data-ttu-id="1c9c4-118">Le gestioni connessioni SMO specificano il server e la modalità di autenticazione da adottare per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-118">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="1c9c4-119">Per altre informazioni, vedere [Gestione connessione file](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1c9c4-119">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="1c9c4-120">L'attività Trasferisci messaggi di errore supporta un'origine e una destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c9c4-120">The Transfer Error Messages task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="1c9c4-121">Non esiste alcuna limitazione relativamente alla versione da utilizzare come origine o destinazione.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-121">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="1c9c4-122">Eventi</span><span class="sxs-lookup"><span data-stu-id="1c9c4-122">Events</span></span>  
 <span data-ttu-id="1c9c4-123">L'attività Trasferisci messaggi di errore genera un evento informativo in cui è indicato il numero di messaggi di errore trasferiti.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-123">The task raises an information event that reports the number of error messages that have been transferred.</span></span>  
  
 <span data-ttu-id="1c9c4-124">Non viene riportato lo stato incrementale del trasferimento, ma solo il completamento 0% e 100%.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-124">The Transfer Error Messages task does not report incremental progress of the error message transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="1c9c4-125">Valore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="1c9c4-125">Execution Value</span></span>  
 <span data-ttu-id="1c9c4-126">Il valore di esecuzione, definito nella proprietà `ExecutionValue` dell'attività, restituisce il numero di messaggi di errore trasferiti.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-126">The execution value, defined in the `ExecutionValue` property of the task, returns the number of error messages that have been transferred.</span></span> <span data-ttu-id="1c9c4-127">Tramite l'assegnazione di una variabile definita dall'utente alla proprietà `ExecValueVariable` dell'attività, le informazioni sul trasferimento dei messaggi di errore possono essere rese disponibili ad altri oggetti del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-127">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Error Message task, information about the error message transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="1c9c4-128">Per altre informazioni, vedere [Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Utilizzo di variabili nei pacchetti](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1c9c4-128">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="1c9c4-129">Voci di log</span><span class="sxs-lookup"><span data-stu-id="1c9c4-129">Log Entries</span></span>  
 <span data-ttu-id="1c9c4-130">L'attività Trasferisci messaggi di errore include le voci di log personalizzate seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c9c4-130">The Transfer Error Messages task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="1c9c4-131">TransferErrorMessagesTaskStartTransferringObjects    Indica che il trasferimento è iniziato.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-131">TransferErrorMessagesTaskStartTransferringObjects    This log entry reports that the transfer has started.</span></span> <span data-ttu-id="1c9c4-132">La voce di log include l'ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-132">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="1c9c4-133">TransferErrorMessagesTaskFinishedTransferringObjects    Indica che il trasferimento è stato completato.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-133">TransferErrorMessagesTaskFinishedTransferringObjects   This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="1c9c4-134">La voce di log include l'ora di fine.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-134">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="1c9c4-135">Una voce di log per l'evento `OnInformation` indica inoltre il numero di messaggi di errore che sono stati trasferiti e viene scritta una voce di log per l'evento `OnWarning event` per ogni messaggio di errore sovrascritto nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-135">In addition, a log entry for the `OnInformation` event reports the number of error messages that were transferred, and a log entry for the `OnWarning event` is written for each error message on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="1c9c4-136">Sicurezza e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1c9c4-136">Security and Permissions</span></span>  
 <span data-ttu-id="1c9c4-137">Per poter creare messaggi di errore, l'utente che esegue il pacchetto deve essere un membro del ruolo del server sysadmin o serveradmin nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-137">To create new error messages, the user that runs the package must be a member of the sysadmin or serveradmin server role on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-error-messages-task"></a><span data-ttu-id="1c9c4-138">Configurazione dell'attività Trasferisci messaggi di errore</span><span class="sxs-lookup"><span data-stu-id="1c9c4-138">Configuration of the Transfer Error Messages Task</span></span>  
 <span data-ttu-id="1c9c4-139">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="1c9c4-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1c9c4-140">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c9c4-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="1c9c4-141">Editor attività Trasferisci messaggi di errore &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="1c9c4-141">Transfer Error Messages Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="1c9c4-142">Editor attività Trasferisci messaggi di errore &#40;pagina Messaggi&#41;</span><span class="sxs-lookup"><span data-stu-id="1c9c4-142">Transfer Error Messages Task Editor &#40;Messages Page&#41;</span></span>](../transfer-error-messages-task-editor-messages-page.md)  
  
-   [<span data-ttu-id="1c9c4-143">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="1c9c4-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="1c9c4-144">Per informazioni sull'impostazione di queste proprietà a livello di codice, fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="1c9c4-144">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferErrorMessagesTask.TransferErrorMessagesTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="1c9c4-145">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="1c9c4-145">Related Tasks</span></span>  
 <span data-ttu-id="1c9c4-146">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="1c9c4-146">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="1c9c4-147">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="1c9c4-147">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="1c9c4-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c9c4-148">See Also</span></span>  
 <span data-ttu-id="1c9c4-149">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="1c9c4-149">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="1c9c4-150">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="1c9c4-150">Control Flow</span></span>](control-flow.md)  
  
  
