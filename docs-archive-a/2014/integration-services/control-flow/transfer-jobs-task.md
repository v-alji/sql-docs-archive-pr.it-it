---
title: Attività Trasferisci processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.f1
helpviewer_keywords:
- Transfer Jobs task [Integration Services]
ms.assetid: 1bf33885-9c5b-47e4-a549-f5920b66a1de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d692934d5f7c8c1449b123ee8b9caf1d8bb34744
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623424"
---
# <a name="transfer-jobs-task"></a><span data-ttu-id="c8da4-102">Attività Trasferisci processi</span><span class="sxs-lookup"><span data-stu-id="c8da4-102">Transfer Jobs Task</span></span>
  <span data-ttu-id="c8da4-103">L'attività Trasferisci processi trasferisce uno o più processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tra istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8da4-103">The Transfer Jobs task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c8da4-104">È possibile configurare l'attività per il trasferimento di tutti i processi o dei processi specificati.</span><span class="sxs-lookup"><span data-stu-id="c8da4-104">The Transfer Jobs task can be configured to transfer all jobs, or only specified jobs.</span></span> <span data-ttu-id="c8da4-105">È inoltre possibile indicare se i processi trasferiti devono essere attivati o meno nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="c8da4-105">You can also indicate whether the transferred jobs are enabled at the destination.</span></span>  
  
 <span data-ttu-id="c8da4-106">I processi da trasferire potrebbero essere già presenti nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="c8da4-106">The jobs to be transferred may already exist on the destination.</span></span> <span data-ttu-id="c8da4-107">È possibile configurare l'attività Trasferisci processi per la gestione dei processi duplicati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8da4-107">The Transfer Jobs task can be configured to handle existing jobs in the following ways:</span></span>  
  
-   <span data-ttu-id="c8da4-108">I processi duplicati vengono sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="c8da4-108">Overwrite existing jobs.</span></span>  
  
-   <span data-ttu-id="c8da4-109">In presenza di processi duplicati l'attività ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c8da4-109">Fail the task when duplicate jobs exist.</span></span>  
  
-   <span data-ttu-id="c8da4-110">I processi duplicati vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="c8da4-110">Skip duplicate jobs.</span></span>  
  
 <span data-ttu-id="c8da4-111">In fase di esecuzione l'attività Trasferisci processi si connette al server di origine e al server di destinazione utilizzando una o più gestioni connessioni SMO.</span><span class="sxs-lookup"><span data-stu-id="c8da4-111">At run time, the Transfer Jobs task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="c8da4-112">Le gestioni connessioni SMO vengono configurate separatamente dall'attività Trasferisci processi, che tuttavia vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c8da4-112">The SMO connection manager is configured separately from the Transfer Jobs task, and then is referenced in the Transfer Jobs task.</span></span> <span data-ttu-id="c8da4-113">Le gestioni connessioni SMO specificano il server e la modalità di autenticazione da adottare per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="c8da4-113">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="c8da4-114">Per altre informazioni, vedere [Gestione connessione file](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c8da4-114">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-jobs-between-instances-of-sql-server"></a><span data-ttu-id="c8da4-115">Trasferimento di processi tra istanze di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c8da4-115">Transferring Jobs Between Instances of SQL Server</span></span>  
 <span data-ttu-id="c8da4-116">L'attività Trasferisci processi supporta un'origine e una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c8da4-116">The Transfer Jobs task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="c8da4-117">Non esiste alcuna limitazione relativamente alla versione da utilizzare come origine o destinazione.</span><span class="sxs-lookup"><span data-stu-id="c8da4-117">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="c8da4-118">Eventi</span><span class="sxs-lookup"><span data-stu-id="c8da4-118">Events</span></span>  
 <span data-ttu-id="c8da4-119">L'attività Trasferisci processi genera un evento informativo in cui è indicato il numero di processi trasferiti. Genera inoltre un evento di avviso quando un processo viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="c8da4-119">The Transfer Jobs task raises an information event that reports the number of jobs transferred and a warning event when a job is overwritten.</span></span> <span data-ttu-id="c8da4-120">Non viene riportato lo stato incrementale del trasferimento, ma solo il completamento 0% e 100%.</span><span class="sxs-lookup"><span data-stu-id="c8da4-120">The task does not report incremental progress of the job transfer; it reports only 0% and 100% completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="c8da4-121">Valore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c8da4-121">Execution Value</span></span>  
 <span data-ttu-id="c8da4-122">Il valore di esecuzione, definito nella proprietà `ExecutionValue` dell'attività, restituisce il numero di processi trasferiti.</span><span class="sxs-lookup"><span data-stu-id="c8da4-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of jobs that are transferred.</span></span> <span data-ttu-id="c8da4-123">Tramite l'assegnazione di una variabile definita dall'utente alla proprietà `ExecValueVariable` dell'attività, le informazioni sul trasferimento dei processi possono essere rese disponibili ad altri oggetti del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c8da4-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Jobs task, information about the job transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="c8da4-124">Per altre informazioni, vedere [Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Utilizzo di variabili nei pacchetti](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="c8da4-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="c8da4-125">Voci di log</span><span class="sxs-lookup"><span data-stu-id="c8da4-125">Log Entries</span></span>  
 <span data-ttu-id="c8da4-126">L'attività Trasferisci processi include le voci di log personalizzate seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8da4-126">The Transfer Jobs task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="c8da4-127">TransferJobsTaskStarTransferringObjects   Indica che il trasferimento è iniziato.</span><span class="sxs-lookup"><span data-stu-id="c8da4-127">TransferJobsTaskStarTransferringObjects   This log entry reports that the transfer has started.</span></span> <span data-ttu-id="c8da4-128">La voce di log include l'ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="c8da4-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="c8da4-129">TransferJobsTaskFinishedTransferringObjects    Indica che il trasferimento è stato completato.</span><span class="sxs-lookup"><span data-stu-id="c8da4-129">TransferJobsTaskFinishedTransferringObjects    This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="c8da4-130">La voce di log include l'ora di fine.</span><span class="sxs-lookup"><span data-stu-id="c8da4-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="c8da4-131">Inoltre, una voce di log per l'evento `OnInformation` indica il numero di processi che sono stati trasferiti e viene scritta una voce di log per l'evento `OnWarning` per ogni processo sovrascritto nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="c8da4-131">In addition, a log entry for the `OnInformation` event reports the number of jobs that were transferred and a log entry for the `OnWarning` event is written for each job on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="c8da4-132">Sicurezza e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c8da4-132">Security and Permissions</span></span>  
 <span data-ttu-id="c8da4-133">Per poter trasferire processi, l'utente deve essere un membro del ruolo predefinito del server sysadmin o di uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent nel database msdb, sia nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]di origine che in quella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c8da4-133">To transfer jobs, the user must be a member of the sysadmin fixed server role or one of the fixed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles on the msdb database on the both the source and destination instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="configuration-of-the-transfer-jobs-task"></a><span data-ttu-id="c8da4-134">Configurazione dell'attività Trasferisci processi</span><span class="sxs-lookup"><span data-stu-id="c8da4-134">Configuration of the Transfer Jobs Task</span></span>  
 <span data-ttu-id="c8da4-135">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="c8da4-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c8da4-136">Per informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8da4-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c8da4-137">Editor attività Trasferisci processi &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="c8da4-137">Transfer Jobs Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="c8da4-138">Editor attività Trasferisci processi &#40;pagina Processi&#41;</span><span class="sxs-lookup"><span data-stu-id="c8da4-138">Transfer Jobs Task Editor &#40;Jobs Page&#41;</span></span>](../transfer-jobs-task-editor-jobs-page.md)  
  
-   [<span data-ttu-id="c8da4-139">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="c8da4-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="c8da4-140">Per informazioni sull'impostazione di queste proprietà a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8da4-140">For information about programmatically setting these properties, click the of the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferJobsTask.TransferJobsTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="c8da4-141">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="c8da4-141">Related Tasks</span></span>  
 <span data-ttu-id="c8da4-142">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="c8da4-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="c8da4-143">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="c8da4-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="c8da4-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8da4-144">See Also</span></span>  
 <span data-ttu-id="c8da4-145">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="c8da4-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="c8da4-146">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="c8da4-146">Control Flow</span></span>](control-flow.md)  
  
  
