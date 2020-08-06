---
title: Attività Trasferisci account di accesso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.f1
helpviewer_keywords:
- Transfer Logins task [Integration Services]
ms.assetid: 1df60fd6-c019-405d-8155-c330dbac2cc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d42d39b6cc7c2f350e3e3adc774be23934981369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623422"
---
# <a name="transfer-logins-task"></a><span data-ttu-id="27b6b-102">Attività Trasferisci account di accesso</span><span class="sxs-lookup"><span data-stu-id="27b6b-102">Transfer Logins Task</span></span>
  <span data-ttu-id="27b6b-103">L'attività Trasferisci account di accesso trasferisce uno o più account di accesso tra istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27b6b-103">The Transfer Logins task transfers one or more logins between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="transfer-logins-between-instances-of-sql-server"></a><span data-ttu-id="27b6b-104">Trasferimento di account di accesso tra istanze di SQL Server</span><span class="sxs-lookup"><span data-stu-id="27b6b-104">Transfer Logins Between Instances of SQL Server</span></span>  
 <span data-ttu-id="27b6b-105">L'attività Trasferisci account di accesso supporta un'origine e una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27b6b-105">The Transfer Logins task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="27b6b-106">Eventi</span><span class="sxs-lookup"><span data-stu-id="27b6b-106">Events</span></span>  
 <span data-ttu-id="27b6b-107">L'attività Trasferisci account di accesso genera un evento informativo in cui è indicato il numero di account di accesso trasferiti. Genera inoltre un evento di avviso quando un account di accesso viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="27b6b-107">The task raises an information event that reports the number of logins transferred and a warning event when a login is overwritten.</span></span>  
  
 <span data-ttu-id="27b6b-108">Non viene riportato lo stato incrementale del trasferimento, ma solo il completamento 0% e 100%.</span><span class="sxs-lookup"><span data-stu-id="27b6b-108">The Transfer Logins task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="27b6b-109">Valore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="27b6b-109">Execution Value</span></span>  
 <span data-ttu-id="27b6b-110">Il valore di esecuzione, definito nella proprietà `ExecutionValue` dell'attività, restituisce il numero di account di accesso trasferiti.</span><span class="sxs-lookup"><span data-stu-id="27b6b-110">The execution value, defined in the `ExecutionValue` property of the task, returns the number of logins transferred.</span></span> <span data-ttu-id="27b6b-111">Tramite l'assegnazione di una variabile definita dall'utente alla proprietà `ExecValueVariable` dell'attività, le informazioni sul trasferimento degli account di accesso possono essere rese disponibili ad altri oggetti del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="27b6b-111">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Logins task, information about the login transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="27b6b-112">Per altre informazioni, vedere [Variabili di Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) e [Utilizzo di variabili nei pacchetti](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="27b6b-112">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="27b6b-113">Voci di log</span><span class="sxs-lookup"><span data-stu-id="27b6b-113">Log Entries</span></span>  
 <span data-ttu-id="27b6b-114">L'attività Trasferisci account di accesso include le voci di log personalizzate seguenti:</span><span class="sxs-lookup"><span data-stu-id="27b6b-114">The Transfer Logins task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="27b6b-115">TransferLoginsTaskStarTransferringObjects    Indica che il trasferimento è iniziato.</span><span class="sxs-lookup"><span data-stu-id="27b6b-115">TransferLoginsTaskStarTransferringObjects    This log entry reports the transfer has started.</span></span> <span data-ttu-id="27b6b-116">La voce di log include l'ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="27b6b-116">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="27b6b-117">TransferLoginsTaskFinishedTransferringObjects   Indica che il trasferimento è stato completato.</span><span class="sxs-lookup"><span data-stu-id="27b6b-117">TransferLoginsTaskFinishedTransferringObjects   This log entry reports the transfer has completed.</span></span> <span data-ttu-id="27b6b-118">La voce di log include l'ora di fine.</span><span class="sxs-lookup"><span data-stu-id="27b6b-118">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="27b6b-119">Inoltre, una voce di log per l'evento `OnInformation` indica il numero di account di accesso che sono stati trasferiti e viene scritta una voce di log per l'evento `OnWarning` per ogni account di accesso sovrascritto nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="27b6b-119">In addition, a log entry for the `OnInformation` event reports the number of logins that were transferred, and a log entry for the `OnWarning` event is written for each login on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="27b6b-120">Sicurezza e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="27b6b-120">Security and Permissions</span></span>  
 <span data-ttu-id="27b6b-121">Per poter esplorare gli account di accesso nel server di origine e creare account di accesso nel server di destinazione, è necessario che l'utente sia un membro del ruolo del server sysadmin in entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="27b6b-121">To browse logins on the source server and to create logins on the destination server, the user must be a member of the sysadmin server role on both servers.</span></span>  
  
## <a name="configuration-of-the-transfer-logins-task"></a><span data-ttu-id="27b6b-122">Configurazione dell'attività Trasferisci account di accesso</span><span class="sxs-lookup"><span data-stu-id="27b6b-122">Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="27b6b-123">È possibile configurare l'attività per il trasferimento di tutti gli account di accesso, degli account di accesso specificati o di tutti gli account di accesso che accedono ai database specificati.</span><span class="sxs-lookup"><span data-stu-id="27b6b-123">The Transfer Logins task can be configured to transfer all logins, only specified logins, or all logins that have access to specified databases only.</span></span> <span data-ttu-id="27b6b-124">L'account di accesso sa non può essere trasferito.</span><span class="sxs-lookup"><span data-stu-id="27b6b-124">The sa login cannot be transferred.</span></span> <span data-ttu-id="27b6b-125">È possibile rinominare l'account di accesso sa. Dopo essere stato rinominato, tuttavia, l'account di accesso sa non può essere trasferito.</span><span class="sxs-lookup"><span data-stu-id="27b6b-125">The sa login may be renamed; however, the renamed sa login cannot be transferred either.</span></span>  
  
 <span data-ttu-id="27b6b-126">È inoltre possibile specificare se l'attività deve copiare gli identificatori di sicurezza (SID) associati agli account di accesso.</span><span class="sxs-lookup"><span data-stu-id="27b6b-126">You can also indicate whether the task copies the security identifiers (SIDs) associated with the logins.</span></span> <span data-ttu-id="27b6b-127">Se l'attività Trasferisci account di accesso viene utilizzata insieme all'attività Trasferisci database, i SID devono essere copiati nella destinazione. Se non si esegue questa operazione, gli account di accesso trasferiti non vengono riconosciuti dal database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="27b6b-127">If the Transfer Logins task is used in conjunction with the Transfer Database task the SIDs must be copied to the destination; otherwise, the transferred logins are not recognized by the destination database.</span></span>  
  
 <span data-ttu-id="27b6b-128">Nella destinazione gli account di accesso trasferiti vengono disabilitati e vi vengono assegnate password casuali.</span><span class="sxs-lookup"><span data-stu-id="27b6b-128">At the destination, the transferred logins are disabled and assigned random passwords.</span></span> <span data-ttu-id="27b6b-129">Un membro del ruolo sysadmin nel server di destinazione deve modificare le password e attivare gli account di accesso in modo che possano essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="27b6b-129">A member of the sysadmin role on the destination server must change the passwords and enable the logins before the logins can be used.</span></span>  
  
 <span data-ttu-id="27b6b-130">Gli account di accesso da trasferire potrebbero essere già presenti nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="27b6b-130">The logins to be transferred may already exist on the destination.</span></span> <span data-ttu-id="27b6b-131">È possibile configurare l'attività Trasferisci account di accesso per la gestione degli account di accesso duplicati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="27b6b-131">The Transfer Logins task can be configured to handle existing logins in the following ways:</span></span>  
  
-   <span data-ttu-id="27b6b-132">Gli account di accesso duplicati vengono sovrascritti.</span><span class="sxs-lookup"><span data-stu-id="27b6b-132">Overwrite existing logins.</span></span>  
  
-   <span data-ttu-id="27b6b-133">In presenza di account di accesso duplicati l'attività ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="27b6b-133">Fail the task when duplicate logins exist.</span></span>  
  
-   <span data-ttu-id="27b6b-134">Gli account di accesso duplicati vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="27b6b-134">Skip duplicate logins.</span></span>  
  
 <span data-ttu-id="27b6b-135">In fase di esecuzione l'attività Trasferisci account di accesso si connette al server di origine e al server di destinazione utilizzando due gestioni di connessione SMO.</span><span class="sxs-lookup"><span data-stu-id="27b6b-135">At run time, the Transfer Logins task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="27b6b-136">Le due gestioni vengono configurate separatamente dall'attività Trasferisci account di accesso, che tuttavia vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="27b6b-136">The SMO connection managers are configured separately from the Transfer Logins task, and then referenced in the Transfer Logins task.</span></span> <span data-ttu-id="27b6b-137">Le gestioni connessioni SMO specificano il server e la modalità di autenticazione da utilizzare per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="27b6b-137">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="27b6b-138">Per altre informazioni, vedere [Gestione connessione file](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="27b6b-138">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="27b6b-139">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="27b6b-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="27b6b-140">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27b6b-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="27b6b-141">Editor attività Trasferisci account di accesso &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="27b6b-141">Transfer Logins Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="27b6b-142">Editor attività Trasferisci account di accesso &#40;pagina Account di accesso&#41;</span><span class="sxs-lookup"><span data-stu-id="27b6b-142">Transfer Logins Task Editor &#40;Logins Page&#41;</span></span>](../transfer-logins-task-editor-logins-page.md)  
  
-   [<span data-ttu-id="27b6b-143">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="27b6b-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="27b6b-144">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="27b6b-144">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="27b6b-145">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="27b6b-145">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-transfer-logins-task"></a><span data-ttu-id="27b6b-146">Configurazione a livello di codice dell'attività Trasferisci account di accesso</span><span class="sxs-lookup"><span data-stu-id="27b6b-146">Programmatic Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="27b6b-147">Per ulteriori informazioni sull'impostazione di queste proprietà a livello di codice, fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="27b6b-147">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferLoginsTask.TransferLoginsTask>  
  
  
