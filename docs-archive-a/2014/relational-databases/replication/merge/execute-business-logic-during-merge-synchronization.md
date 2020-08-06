---
title: Eseguire logiche di business durante la sincronizzazione di tipo merge | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- custom error resolution [SQL Server replication]
- custom change handling [SQL Server replication]
- errors [SQL Server replication], business logic handlers
- merge replication business logic handlers [SQL Server replication]
- conflict resolution [SQL Server replication], merge replication
- business logic handlers [SQL Server replication]
ms.assetid: 9d4da2ef-c17f-4a31-a1f6-5c3b7ca85f71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1e082cbbb46ceae712cd39925c28fe89988a3793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623210"
---
# <a name="execute-business-logic-during-merge-synchronization"></a><span data-ttu-id="0043b-102">Esecuzione di logiche di business durante la sincronizzazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="0043b-102">Execute Business Logic During Merge Synchronization</span></span>
  <span data-ttu-id="0043b-103">Il framework di gestione della logica di business consente di scrivere un assembly di codice gestito che viene chiamato durante il processo di sincronizzazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="0043b-103">The business logic handler framework allows you to write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="0043b-104">L'assembly include la logica di business che consente di rispondere a diverse situazioni durante la sincronizzazione, ad esempio modifiche ai dati, conflitti ed errori.</span><span class="sxs-lookup"><span data-stu-id="0043b-104">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="0043b-105">Il framework di gestione della logica di business offre un semplice modello di programmazione e i dati forniti all'assembly dal processo di merge sono sotto forma di set di dati ADO.NET. In questo modo, è possibile approfondire la propria conoscenza di ADO.NET anziché apprendere un'interfaccia specifica.</span><span class="sxs-lookup"><span data-stu-id="0043b-105">The business logic handler framework provides a simple programming model, and the data that the merge process provides to your assembly is in the form of an ADO.NET data set, so you can leverage knowledge of ADO.NET rather than learning a proprietary interface.</span></span> <span data-ttu-id="0043b-106">Per ulteriori informazioni sulla programmazione dei gestori della logica di business, vedere:</span><span class="sxs-lookup"><span data-stu-id="0043b-106">For more information on programming business logic handlers, see:</span></span>  
  
-   <span data-ttu-id="0043b-107">Riferimento all'API: <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span><span class="sxs-lookup"><span data-stu-id="0043b-107">The application programming interface (API) reference: <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span></span>  
  
-   <span data-ttu-id="0043b-108">Le istruzioni per implementare un gestore della logica di business: [Implementare un gestore della logica di business per un articolo di merge](../implement-a-business-logic-handler-for-a-merge-article.md)</span><span class="sxs-lookup"><span data-stu-id="0043b-108">Instructions on how to implement a business logic handler: [Implement a Business Logic Handler for a Merge Article](../implement-a-business-logic-handler-for-a-merge-article.md)</span></span>  
  
## <a name="uses-for-business-logic-handlers"></a><span data-ttu-id="0043b-109">Utilizzi dei gestori della logica di business</span><span class="sxs-lookup"><span data-stu-id="0043b-109">Uses for Business Logic Handlers</span></span>  
 <span data-ttu-id="0043b-110">Il processo di sincronizzazione di tipo merge consente di richiamare i gestori della logica di business per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0043b-110">The merge synchronization process can invoke business logic handlers to perform:</span></span>  
  
-   <span data-ttu-id="0043b-111">Gestione personalizzata delle modifiche</span><span class="sxs-lookup"><span data-stu-id="0043b-111">Custom change handling</span></span>  
  
-   <span data-ttu-id="0043b-112">Risoluzione personalizzata dei conflitti</span><span class="sxs-lookup"><span data-stu-id="0043b-112">Custom conflict resolution</span></span>  
  
-   <span data-ttu-id="0043b-113">Risoluzione personalizzata degli errori</span><span class="sxs-lookup"><span data-stu-id="0043b-113">Custom error resolution</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0043b-114">Il gestore della logica di business specificato viene eseguito per ogni riga sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="0043b-114">The business logic handler you specify is executed for every row that is synchronized.</span></span> <span data-ttu-id="0043b-115">La complessità della logica e le chiamate ad altre applicazioni o servizi di rete possono ridurre le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0043b-115">Complex logic and calls to other applications or network services can impact performance.</span></span>  
  
### <a name="custom-change-handling"></a><span data-ttu-id="0043b-116">Gestione personalizzata delle modifiche</span><span class="sxs-lookup"><span data-stu-id="0043b-116">Custom Change Handling</span></span>  
 <span data-ttu-id="0043b-117">Il gestore della logica di business può essere richiamato durante l'elaborazione di modifiche ai dati non in conflitto e consente di eseguire una delle tre azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0043b-117">The business logic handler can be invoked during the processing of non-conflicting data changes and can perform one of three actions:</span></span>  
  
-   <span data-ttu-id="0043b-118">Rifiutare i dati</span><span class="sxs-lookup"><span data-stu-id="0043b-118">Reject the data</span></span>  
  
     <span data-ttu-id="0043b-119">Operazione utile per le applicazioni di cui non si desidera propagare le modifiche a o da un Sottoscrittore specifico.</span><span class="sxs-lookup"><span data-stu-id="0043b-119">This is useful for applications that do not want changes propagated to or from a given Subscriber.</span></span> <span data-ttu-id="0043b-120">Un amministratore, ad esempio, potrebbe escludere tramite un filtro gli inserimenti che non appartengono alla partizione del Sottoscrittore oppure eventualmente rifiutare le eliminazioni eseguite in un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="0043b-120">For example, an administrator could filter out inserts that do not belong in the Subscriber's partition, or possibly reject deletes performed at a Subscriber.</span></span> <span data-ttu-id="0043b-121">Un'applicazione potrebbe inoltre rifiutare un ordine immesso in un Sottoscrittore perché le scorte non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="0043b-121">As another example, an application could reject an order entered at a Subscriber because the inventory is no longer available.</span></span>  
  
-   <span data-ttu-id="0043b-122">Accettare i dati</span><span class="sxs-lookup"><span data-stu-id="0043b-122">Accept the data</span></span>  
  
     <span data-ttu-id="0043b-123">Operazione utile per le applicazioni in cui è necessario esaminare le modifiche ai dati apportate nel server di pubblicazione o nel Sottoscrittore prima di consentirne la propagazione.</span><span class="sxs-lookup"><span data-stu-id="0043b-123">This is useful for applications in which it is necessary to review data changes made at either the Publisher or Subscriber before allowing them to be propagated.</span></span> <span data-ttu-id="0043b-124">Un'applicazione di livello intermedio, ad esempio, consentirebbe di esaminare i nuovi ordini provenienti dal campo e di integrarli con un processo del flusso di lavoro relativo all'approvvigionamento nel livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="0043b-124">For example, a mid-tier application could examine new orders coming in from the field and integrate with a procurement workflow process in the mid-tier.</span></span>  
  
-   <span data-ttu-id="0043b-125">Applicare dati personalizzati</span><span class="sxs-lookup"><span data-stu-id="0043b-125">Apply custom data</span></span>  
  
     <span data-ttu-id="0043b-126">Operazione utile per le applicazioni in cui è necessario sostituire operazioni o valori di dati specifici.</span><span class="sxs-lookup"><span data-stu-id="0043b-126">This is useful for applications that need to override specific data values or operations.</span></span> <span data-ttu-id="0043b-127">In un'applicazione, ad esempio, un'eliminazione di riga potrebbe essere trasformata in un aggiornamento speciale che imposta una colonna **status** della riga sul valore "deleted" e quindi rileva l'identità del client che ha eseguito l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="0043b-127">For example, an application could transform a row delete into a special update that sets a **status** column in the row to a value of "deleted" and then tracks the identity of the client performing the delete.</span></span> <span data-ttu-id="0043b-128">Questa operazione potrebbe risultare utile per effettuare controlli e monitorare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0043b-128">This might be useful for auditing or workflow purposes.</span></span>  
  
### <a name="custom-conflict-resolution"></a><span data-ttu-id="0043b-129">Risoluzione personalizzata dei conflitti</span><span class="sxs-lookup"><span data-stu-id="0043b-129">Custom Conflict Resolution</span></span>  
 <span data-ttu-id="0043b-130">La replica di tipo merge consente di rilevare e risolvere i conflitti, permettendo di accettare una strategia di risoluzione predefinita o di scegliere la risoluzione personalizzata per i conflitti.</span><span class="sxs-lookup"><span data-stu-id="0043b-130">Merge replication provides conflict detection and resolution, allowing you to accept a default resolution strategy or choose custom resolution for conflicts.</span></span> <span data-ttu-id="0043b-131">Per altre informazioni, vedere [Rilevamento e risoluzione avanzati dei conflitti nella replica di tipo merge](advanced-merge-replication-conflict-detection-and-resolution.md).</span><span class="sxs-lookup"><span data-stu-id="0043b-131">For more information, see [Advanced Merge Replication Conflict Detection and Resolution](advanced-merge-replication-conflict-detection-and-resolution.md).</span></span> <span data-ttu-id="0043b-132">Il gestore della logica di business può essere richiamato durante l'elaborazione di modifiche ai dati in conflitto e consente di eseguire una delle due azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0043b-132">The business logic handler can be invoked during the processing of conflicting data changes and can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="0043b-133">Accettare la risoluzione predefinita</span><span class="sxs-lookup"><span data-stu-id="0043b-133">Accept default resolution</span></span>  
  
     <span data-ttu-id="0043b-134">Operazione utile per le applicazioni per cui può essere necessario esaminare il conflitto, eseguire altre azioni ed eventualmente registrare un messaggio personalizzato del log dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="0043b-134">This is useful for applications that might need to review the conflict, perform additional actions, and possibly log a custom conflict log message.</span></span>  
  
-   <span data-ttu-id="0043b-135">Eseguire la risoluzione personalizzata</span><span class="sxs-lookup"><span data-stu-id="0043b-135">Perform custom resolution</span></span>  
  
     <span data-ttu-id="0043b-136">Operazione utile per le applicazioni per cui può essere necessario selezionare valori di dati specifici della logica di business e fornire al processo di sincronizzazione questo set di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0043b-136">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="0043b-137">Un'applicazione, ad esempio, potrebbe rendere disponibile una nuova versione della riga confermata combinando i valori dei set di dati del server di pubblicazione e del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="0043b-137">For example, an application could provide a new version of the winning row by combining values from the Publisher and Subscriber data sets.</span></span>  
  
### <a name="custom-error-resolution"></a><span data-ttu-id="0043b-138">Risoluzione personalizzata degli errori</span><span class="sxs-lookup"><span data-stu-id="0043b-138">Custom Error Resolution</span></span>  
 <span data-ttu-id="0043b-139">È possibile richiamare la logica personalizzata durante la propagazione delle modifiche che restituiscono errori.</span><span class="sxs-lookup"><span data-stu-id="0043b-139">Custom logic can be invoked during the propagation of changes that result in errors.</span></span> <span data-ttu-id="0043b-140">La logica consente di eseguire una delle due azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0043b-140">The logic can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="0043b-141">Accettare la risoluzione predefinita degli errori</span><span class="sxs-lookup"><span data-stu-id="0043b-141">Accept default error resolution</span></span>  
  
     <span data-ttu-id="0043b-142">Operazione utile per le applicazioni per cui può essere necessario esaminare l'errore ed eseguire l'altra azione ed eventualmente registrare un messaggio personalizzato del log degli errori.</span><span class="sxs-lookup"><span data-stu-id="0043b-142">This is useful for applications that might need to review the error and perform additional action and possibly log a custom error log message.</span></span>  
  
-   <span data-ttu-id="0043b-143">Accettare la risoluzione personalizzata degli errori</span><span class="sxs-lookup"><span data-stu-id="0043b-143">Accept custom error resolution</span></span>  
  
     <span data-ttu-id="0043b-144">Operazione utile per le applicazioni per cui può essere necessario selezionare valori di dati specifici della logica di business e fornire al processo di sincronizzazione questo set di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0043b-144">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="0043b-145">Se, ad esempio, durante il processo di replica viene rilevata una violazione di chiave duplicata, il gestore della logica di business potrebbe specificare una nuova versione della modifica ai dati in cui la chiave non risulta più in conflitto.</span><span class="sxs-lookup"><span data-stu-id="0043b-145">For example, if the replication process encounters a duplicate key violation, the business logic handler could provide a new version of the data change in which the key will no longer conflict.</span></span> <span data-ttu-id="0043b-146">Le modifiche apportate nel server di pubblicazione e nel Sottoscrittore possono essere mantenute nel database e il processo di replica non deve compensare l'inserimento non riuscito con un'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="0043b-146">Changes made at the Publisher and Subscriber can then persist in the database, and the replication process doesn't have to compensate for the failed insert with a delete.</span></span>  
  
## <a name="deployment-scenarios-for-business-logic-handlers"></a><span data-ttu-id="0043b-147">Scenari di distribuzione per gestori della logica di business</span><span class="sxs-lookup"><span data-stu-id="0043b-147">Deployment Scenarios for Business Logic Handlers</span></span>  
 <span data-ttu-id="0043b-148">È possibile distribuire gestori della logica di business nei sistemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0043b-148">Business logic handlers can be deployed at:</span></span>  
  
-   <span data-ttu-id="0043b-149">Server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0043b-149">The Distributor.</span></span> <span data-ttu-id="0043b-150">Utilizzare una sottoscrizione push per eseguire la logica di business nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0043b-150">Use a push subscription so that business logic is executed at the Distributor.</span></span>  
  
-   <span data-ttu-id="0043b-151">Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="0043b-151">The Subscriber.</span></span> <span data-ttu-id="0043b-152">Utilizzare una sottoscrizione pull per eseguire la logica di business nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="0043b-152">Use a pull subscription so that business logic is executed at the Subscriber.</span></span>  
  
-   <span data-ttu-id="0043b-153">Server IIS (Internet Information Services), se si utilizza la sincronizzazione tramite il Web.</span><span class="sxs-lookup"><span data-stu-id="0043b-153">An Internet Information Services (IIS) server if Web synchronization is used.</span></span> <span data-ttu-id="0043b-154">Utilizzare una sottoscrizione pull sincronizzata tramite il Web per eseguire il gestore della logica di business nel server IIS.</span><span class="sxs-lookup"><span data-stu-id="0043b-154">Use a pull subscription synchronized with Web synchronization, and the business logic handler will execute at the IIS Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0043b-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0043b-155">See Also</span></span>  
 <span data-ttu-id="0043b-156">[Replica di tipo merge](merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="0043b-156">[Merge Replication](merge-replication.md) </span></span>  
 <span data-ttu-id="0043b-157">[Subscribe to Publications](../subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="0043b-157">[Subscribe to Publications](../subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="0043b-158">[Sincronizzare i dati](../synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="0043b-158">[Synchronize Data](../synchronize-data.md) </span></span>  
 [<span data-ttu-id="0043b-159">Sincronizzazione Web per la replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="0043b-159">Web Synchronization for Merge Replication</span></span>](../web-synchronization-for-merge-replication.md)  
  
  
