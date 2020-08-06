---
title: Attività Trasferisci stored procedure master | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfermasterspstask.f1
helpviewer_keywords:
- Transfer Master Stored Procedures task [Integration Services]
ms.assetid: 81702560-48a3-46d1-a469-e41304c7af8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1915a3129eeb6e14c4315c37f2c6c2bf5b0d5412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724840"
---
# <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="8c977-102">Attività Trasferisci stored procedure master</span><span class="sxs-lookup"><span data-stu-id="8c977-102">Transfer Master Stored Procedures Task</span></span>
  <span data-ttu-id="8c977-103">L'attività Trasferisci stored procedure master trasferisce una o più stored procedure definite dall'utente tra i database **master** di istanze diverse di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c977-103">The Transfer Master Stored Procedures task transfers one or more user-defined stored procedures between **master** databases on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8c977-104">Per trasferire una stored procedure dal database **master** , è necessario che il proprietario stored della procedure sia un dbo.</span><span class="sxs-lookup"><span data-stu-id="8c977-104">To transfer a stored procedure from the **master** database, the owner of the procedure must be dbo.</span></span>  
  
 <span data-ttu-id="8c977-105">È possibile configurare l'attività Trasferisci stored procedure master per il trasferimento di tutte le stored procedure o delle stored procedure specificate.</span><span class="sxs-lookup"><span data-stu-id="8c977-105">The Transfer Master Stored Procedures task can be configured to transfer all stored procedures or only specified stored procedures.</span></span> <span data-ttu-id="8c977-106">Questa attività non esegue la copia delle stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="8c977-106">This task does not copy system stored procedures.</span></span>  
  
 <span data-ttu-id="8c977-107">È possibile che le stored procedure master da trasferire siano già presenti nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="8c977-107">The master stored procedures to be transferred may already exist on the destination.</span></span> <span data-ttu-id="8c977-108">È tuttavia possibile configurare l'attività Trasferisci stored procedure master per la gestione di eventuali stored procedure esistenti nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c977-108">The Transfer Master Stored Procedures task can be configured to handle existing stored procedures in the following ways:</span></span>  
  
-   <span data-ttu-id="8c977-109">Le stored procedure esistenti vengono sovrascritte.</span><span class="sxs-lookup"><span data-stu-id="8c977-109">Overwrite existing stored procedures.</span></span>  
  
-   <span data-ttu-id="8c977-110">In presenza di stored procedure duplicate l'attività ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8c977-110">Fail the task when duplicate stored procedures exist.</span></span>  
  
-   <span data-ttu-id="8c977-111">Le stored procedure duplicate vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="8c977-111">Skip duplicate stored procedures.</span></span>  
  
 <span data-ttu-id="8c977-112">In fase di esecuzione l'attività Trasferisci stored procedure master si connette al server di origine e al server di destinazione utilizzando due gestioni connessioni SMO.</span><span class="sxs-lookup"><span data-stu-id="8c977-112">At run time, the Transfer Master Stored Procedures task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="8c977-113">Le gestioni connessioni SMO vengono configurate separatamente dall'attività Trasferisci stored procedure master, che tuttavia vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="8c977-113">The SMO connection managers are configured separately from the Transfer Master Stored Procedures task, and then referenced in the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="8c977-114">Le gestioni connessioni SMO specificano il server e la modalità di autenticazione da utilizzare per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="8c977-114">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="8c977-115">Per altre informazioni, vedere [Gestione connessione file](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8c977-115">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-stored-procedures-between-instances-of-sql-server"></a><span data-ttu-id="8c977-116">Trasferimento di stored procedure tra istanze di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c977-116">Transferring Stored Procedures Between Instances of SQL Server</span></span>  
 <span data-ttu-id="8c977-117">L'attività Trasferisci stored procedure master supporta un'origine e una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c977-117">The Transfer Master Stored Procedures task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="8c977-118">Eventi</span><span class="sxs-lookup"><span data-stu-id="8c977-118">Events</span></span>  
 <span data-ttu-id="8c977-119">L'attività genera un evento informativo in cui è indicato il numero di stored procedure trasferite. Genera inoltre un evento di avviso quando una stored procedure viene sovrascritta.</span><span class="sxs-lookup"><span data-stu-id="8c977-119">The task raises an information event that reports the number of stored procedures transferred and a warning event when a stored procedure is overwritten.</span></span>  
  
 <span data-ttu-id="8c977-120">Non viene riportato lo stato incrementale del trasferimento, ma solo il completamento 0% e 100%.</span><span class="sxs-lookup"><span data-stu-id="8c977-120">The Transfer Master Stored Procedures task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="8c977-121">Valore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8c977-121">Execution Value</span></span>  
 <span data-ttu-id="8c977-122">Il valore di esecuzione, definito nella proprietà `ExecutionValue` dell'attività, restituisce il numero di stored procedure trasferite.</span><span class="sxs-lookup"><span data-stu-id="8c977-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of stored procedures transferred.</span></span> <span data-ttu-id="8c977-123">Tramite l'assegnazione di una variabile definita dall'utente alla proprietà `ExecValueVariable` dell'attività, le informazioni sul trasferimento di stored procedure master possono essere rese disponibili ad altri oggetti del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8c977-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Master Stored Procedures task, information about the stored procedure transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="8c977-124">Per altre informazioni, vedere [Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Utilizzo di variabili nei pacchetti](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="8c977-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="8c977-125">Voci di log</span><span class="sxs-lookup"><span data-stu-id="8c977-125">Log Entries</span></span>  
 <span data-ttu-id="8c977-126">L'attività Trasferisci stored procedure master include le voci di log personalizzate seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c977-126">The Transfer Master Stored Procedures task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="8c977-127">TransferStoredProceduresTaskStartTransferringObjects  Indica che il trasferimento è iniziato.</span><span class="sxs-lookup"><span data-stu-id="8c977-127">TransferStoredProceduresTaskStartTransferringObjects  This log entry reports that the transfer has started.</span></span> <span data-ttu-id="8c977-128">La voce di log include l'ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="8c977-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="8c977-129">TransferSStoredProceduresTaskFinishedTransferringObjects  Indica che il trasferimento è stato completato.</span><span class="sxs-lookup"><span data-stu-id="8c977-129">TransferSStoredProceduresTaskFinishedTransferringObjects  This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="8c977-130">La voce di log include l'ora di fine.</span><span class="sxs-lookup"><span data-stu-id="8c977-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="8c977-131">Inoltre, una voce di log per l'evento `OnInformation` indica il numero di stored procedure che sono state trasferite e viene scritta una voce di log per l'evento `OnWarning` per ogni stored procedure sovrascritta nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="8c977-131">In addition, a log entry for the `OnInformation` event reports the number of stored procedures that were transferred, and a log entry for the `OnWarning` event is written for each stored procedure on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="8c977-132">Sicurezza e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8c977-132">Security and Permissions</span></span>  
 <span data-ttu-id="8c977-133">L'utente deve disporre dell'autorizzazione per la visualizzazione dell'elenco di stored procedure nel database **master** dell'origine ed essere un membro del ruolo del server amministratore di sistema o disporre dell'autorizzazione per la creazione di stored procedure nel database **master** del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8c977-133">The user must have permission to view the list of stored procedure in the **master** database on the source, and must be a member of the sysadmin server role or have permission to created stored procedures in the **master** database on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-master-stored-procedures-task"></a><span data-ttu-id="8c977-134">Configurazione dell'attività Trasferisci stored procedure master</span><span class="sxs-lookup"><span data-stu-id="8c977-134">Configuration of the Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="8c977-135">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="8c977-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8c977-136">Per informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c977-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8c977-137">Editor attività Trasferisci stored procedure master &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="8c977-137">Transfer Master Stored Procedures Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="8c977-138">Editor attività Trasferisci stored procedure master &#40;pagina Stored procedure&#41;</span><span class="sxs-lookup"><span data-stu-id="8c977-138">Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;</span></span>](../transfer-master-stored-procedures-task-editor-stored-procedures-page.md)  
  
-   [<span data-ttu-id="8c977-139">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="8c977-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="8c977-140">Per informazioni sull'impostazione di queste proprietà a livello di codice, fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="8c977-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferStoredProceduresTask.TransferStoredProceduresTask>  
  
### <a name="configuring-the-transfer-master-stored-procedures-task-programmatically"></a><span data-ttu-id="8c977-141">Configurazione dell'attività Trasferisci stored procedure master a livello di codice</span><span class="sxs-lookup"><span data-stu-id="8c977-141">Configuring the Transfer Master Stored Procedures Task Programmatically</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8c977-142">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="8c977-142">Related Tasks</span></span>  
 <span data-ttu-id="8c977-143">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="8c977-143">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="8c977-144">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="8c977-144">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c977-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c977-145">See Also</span></span>  
 <span data-ttu-id="8c977-146">[Attività Trasferisci oggetti di SQL Server](transfer-sql-server-objects-task.md) </span><span class="sxs-lookup"><span data-stu-id="8c977-146">[Transfer SQL Server Objects Task](transfer-sql-server-objects-task.md) </span></span>  
 <span data-ttu-id="8c977-147">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="8c977-147">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="8c977-148">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="8c977-148">Control Flow</span></span>](control-flow.md)  
  
  
