---
title: Funzione di classificazione di Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function
- user-defined functions [SQL Server], classifier function
- classifier function [SQL Server]
- classifier function [SQL Server], overview
ms.assetid: 64c25012-7068-476f-afa2-0b4f3adde9a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69b6fd10ac0adc6f76925e0d41f110b917111466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715147"
---
# <a name="resource-governor-classifier-function"></a><span data-ttu-id="ed7a7-102">Funzione di classificazione di Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ed7a7-102">Resource Governor Classifier Function</span></span>
  <span data-ttu-id="ed7a7-103">Il processo di classificazione di Resource Governor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consente di assegnare sessioni in ingresso a un gruppo di carico di lavoro in base alle caratteristiche della sessione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource governor classification process assigns incoming sessions to a workload group based on the characteristics of the session.</span></span> <span data-ttu-id="ed7a7-104">È possibile personalizzare la logica di classificazione scrivendo una funzione definita dall'utente, chiamata funzione di classificazione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-104">You can tailor the classification logic by writing a user-defined function, called a classifier function.</span></span>  
  
## <a name="classification"></a><span data-ttu-id="ed7a7-105">Classificazione</span><span class="sxs-lookup"><span data-stu-id="ed7a7-105">Classification</span></span>  
 <span data-ttu-id="ed7a7-106">Resource Governor supporta la classificazione delle sessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-106">Resource Governor supports the classification of incoming sessions.</span></span> <span data-ttu-id="ed7a7-107">La classificazione è basata su un set di criteri definiti dall'utente contenuti in una funzione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-107">Classification is based on a set of user-written criteria contained in a function.</span></span> <span data-ttu-id="ed7a7-108">I risultati della logica della funzione consentono a Resource Governor di classificare sessioni in gruppi del carico di lavoro esistenti.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-108">The results of the function logic enable Resource Governor to classify sessions into existing workload groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed7a7-109">Il gruppo del carico di lavoro interno è popolato con richieste per solo uso interno.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-109">The internal workload group is populated with requests that are for internal use only.</span></span> <span data-ttu-id="ed7a7-110">Non è possibile modificare i criteri utilizzati per indirizzare tali richieste né è possibile classificare richieste nel gruppo del carico di lavoro interno.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-110">You cannot change the criteria used for routing these requests and you cannot classify requests into the internal workload group.</span></span>  
  
 <span data-ttu-id="ed7a7-111">È possibile scrivere una funzione scalare che contiene la logica utilizzata per assegnare sessioni in ingresso a un gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-111">You can write a scalar function that contains the logic that is used to assign incoming sessions to a workload group.</span></span> <span data-ttu-id="ed7a7-112">Prima che sia possibile utilizzare tale funzione, è necessario completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed7a7-112">Before you can use this function, you must complete the following actions:</span></span>  
  
-   <span data-ttu-id="ed7a7-113">Creare e registrare la funzione utilizzando l'istruzione ALTER RESOURCE GOVERNOR.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-113">Create and register the function using the ALTER RESOURCE GOVERNOR statement.</span></span> <span data-ttu-id="ed7a7-114">Per altre informazioni, vedere [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ed7a7-114">For more information, see [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql).</span></span>  
  
-   <span data-ttu-id="ed7a7-115">Aggiornare la configurazione di Resource Governor utilizzando l'istruzione ALTER RESOURCE GOVERNOR con il parametro RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-115">Update the Resource Governor configuration using the ALTER RESOURCE GOVERNOR statement with the RECONFIGURE parameter.</span></span>  
  
 <span data-ttu-id="ed7a7-116">Dopo avere creato la funzione e applicato le modifiche di configurazione, la funzione di classificazione di Resource Governor utilizzerà il nome del gruppo del carico di lavoro restituito dalla funzione per inviare una nuova richiesta al gruppo del carico di lavoro appropriato.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-116">After you create the function and apply the configuration changes, the Resource Governor classifier will use the workload group name returned by the function to send a new request to the appropriate workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed7a7-117">Potrebbe verificarsi il timeout della sessione client se la funzione di classificazione non viene completata entro il timeout specificato per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-117">The client session may time out if the classification function does not complete within the specified time-out for the login.</span></span> <span data-ttu-id="ed7a7-118">Il timeout di accesso è una proprietà client e, in quanto tale, il server non è a conoscenza di un timeout. Una funzione di classificazione con esecuzione prolungata può lasciare il server con connessioni orfane per periodi prolungati.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-118">Login time-out is a client property and as such, the server is unaware of a time-out. A long-running classifier function can leave the server with orphaned connections for long periods.</span></span> <span data-ttu-id="ed7a7-119">È importante che vengano create funzioni di classificazione che terminano l'esecuzione prima del timeout della connessione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-119">It is important that you create classifier functions that finish executing before a connection time-out.</span></span>  
  
 <span data-ttu-id="ed7a7-120">La funzione definita dall'utente ha le seguenti caratteristiche e comportamenti:</span><span class="sxs-lookup"><span data-stu-id="ed7a7-120">The user-defined function has the following characteristics and behaviors:</span></span>  
  
-   <span data-ttu-id="ed7a7-121">La funzione definita dall'utente viene valutata per ogni nuova sessione, anche quando il pool di connessioni è abilitato.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-121">The user-defined function is evaluated for every new session, even when connection pooling is enabled.</span></span>  
  
-   <span data-ttu-id="ed7a7-122">La funzione definita dall'utente fornisce il contesto del gruppo del carico di lavoro per la sessione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-122">The user-defined function gives workload group context for the session.</span></span> <span data-ttu-id="ed7a7-123">Dopo che l'appartenenza a un gruppo è stata determinata, la sessione viene associata al gruppo del carico di lavoro per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-123">After group membership is determined, the session is bound to the workload group for the lifetime of the session.</span></span>  
  
-   <span data-ttu-id="ed7a7-124">Se la funzione definita dall'utente restituisce NULL, il valore predefinito o il nome di un gruppo non esistente, alla sessione viene fornito il contesto predefinito del gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-124">If the user-defined function returns NULL, default, or the name of non-existent group the session is given the default workload group context.</span></span> <span data-ttu-id="ed7a7-125">Alla sessione viene inoltre fornito il contesto predefinito se per qualsiasi motivo la funzione non riesce.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-125">The session is also given the default context if the function fails for any reason.</span></span>  
  
-   <span data-ttu-id="ed7a7-126">La funzione deve essere definita con l'ambito del server (database master).</span><span class="sxs-lookup"><span data-stu-id="ed7a7-126">The function should be defined with server scope (master database).</span></span>  
  
-   <span data-ttu-id="ed7a7-127">La designazione della funzione di classificazione definita dall'utente viene applicata solo dopo l'esecuzione di ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-127">The classifier user-defined function designation only takes effect after ALTER RESOURCE GOVERNOR RECONFIGURE is executed.</span></span>  
  
-   <span data-ttu-id="ed7a7-128">È possibile definire come classificatore solo una funzione definita dall'utente alla volta.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-128">Only one user-defined function can be designated as a classifier at a time.</span></span>  
  
-   <span data-ttu-id="ed7a7-129">La funzione di classificazione definita dall'utente non può essere eliminata o modificata a meno che non venga rimosso lo stato di classificazione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-129">The classifier user-defined function cannot be dropped or altered unless its classifier status is removed.</span></span>  
  
-   <span data-ttu-id="ed7a7-130">In assenza di una funzione di classificazione definita dall'utente, tutte le sessioni vengono classificate nel gruppo predefinito.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-130">In the absence of a classifier user-defined function, all sessions are classified into the default group.</span></span>  
  
-   <span data-ttu-id="ed7a7-131">Il gruppo del carico di lavoro restituito dalla funzione di classificazione è esterno all'ambito della restrizione relativa all'associazione allo schema.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-131">The workload group returned by the classifier function is outside the scope of the schema-binding restriction.</span></span> <span data-ttu-id="ed7a7-132">Non è possibile ad esempio eliminare una tabella, ma è possibile eliminare un gruppo del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-132">For example, you cannot drop a table, but you can drop a workload group.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed7a7-133">Si consiglia di abilitare la connessione amministrativa dedicata nel server.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-133">We recommend enabling the Dedicated Administrator Connection (DAC) on the server.</span></span> <span data-ttu-id="ed7a7-134">Tale connessione non è soggetta alla classificazione di Resource Governor e può essere utilizzata per monitorare e risolvere i problemi relativi a una funzione di classificazione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-134">The DAC is not subject to Resource Governor classification and can be used to monitor and troubleshoot a classifier function.</span></span> <span data-ttu-id="ed7a7-135">Per altre informazioni, vedere [Connessione di diagnostica per gli amministratori di database](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="ed7a7-135">For more information, see [Diagnostic Connection for Database Administrators](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md).</span></span> <span data-ttu-id="ed7a7-136">Se per la risoluzione dei problemi non è disponibile alcuna connessione DAC, è possibile riavviare il sistema in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-136">If a DAC is not available for troubleshooting, the other option is to restart the system in single user mode.</span></span> <span data-ttu-id="ed7a7-137">Sebbene tale modalità non sia soggetta alla classificazione, non consente di eseguire la diagnosi della classificazione di Resource Governor mentre quest'ultimo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-137">Although single user mode is not subject to classification, it does not give you the ability to diagnose Resource Governor classification while it is running.</span></span>  
  
### <a name="classification-process"></a><span data-ttu-id="ed7a7-138">Processo di classificazione</span><span class="sxs-lookup"><span data-stu-id="ed7a7-138">Classification Process</span></span>  
 <span data-ttu-id="ed7a7-139">Nel contesto di Resource Governor il processo di accesso per una sessione è costituito dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed7a7-139">In the context of Resource Governor, the login process for a session consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="ed7a7-140">Autenticazione dell'account di accesso</span><span class="sxs-lookup"><span data-stu-id="ed7a7-140">Login authentication</span></span>  
  
2.  <span data-ttu-id="ed7a7-141">Esecuzione del trigger LOGON</span><span class="sxs-lookup"><span data-stu-id="ed7a7-141">LOGON trigger execution</span></span>  
  
3.  <span data-ttu-id="ed7a7-142">Classificazione</span><span class="sxs-lookup"><span data-stu-id="ed7a7-142">Classification</span></span>  
  
 <span data-ttu-id="ed7a7-143">Quando la classificazione viene avviata, in Resource Governor viene eseguita la funzione di classificazione e il valore restituito dalla funzione viene utilizzato per inviare richieste al gruppo del carico di lavoro appropriato.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-143">When classification starts, Resource Governor executes the classifier function and uses the value returned by the function to send requests to the appropriate workload group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed7a7-144">Informazioni sull'esecuzione della funzione di classificazione e sui trigger LOGON sono disponibili in [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) e [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ed7a7-144">Information about the execution of the classifier function and LOGON triggers is exposed in [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_exec_requests](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql).</span></span>  
  
## <a name="classification-function-tasks"></a><span data-ttu-id="ed7a7-145">Attività della funzione di classificazione</span><span class="sxs-lookup"><span data-stu-id="ed7a7-145">Classification Function Tasks</span></span>  
  
|<span data-ttu-id="ed7a7-146">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="ed7a7-146">Task Description</span></span>|<span data-ttu-id="ed7a7-147">Argomento</span><span class="sxs-lookup"><span data-stu-id="ed7a7-147">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="ed7a7-148">Viene descritto come creare e verificare una funzione di classificazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ed7a7-148">Describes how to create and test a classifier user-defined function.</span></span>|[<span data-ttu-id="ed7a7-149">Creare e testare una funzione di classificazione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="ed7a7-149">Create and Test a Classifier User-Defined Function</span></span>](create-and-test-a-classifier-user-defined-function.md)|  
  
## <a name="see-also"></a><span data-ttu-id="ed7a7-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed7a7-150">See Also</span></span>  
 <span data-ttu-id="ed7a7-151">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ed7a7-151">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="ed7a7-152">[Abilitare Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ed7a7-152">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="ed7a7-153">[Pool di risorse di Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="ed7a7-153">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="ed7a7-154">[Gruppo di carico di lavoro di Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="ed7a7-154">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="ed7a7-155">[Configurare Resource Governor utilizzando un modello](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="ed7a7-155">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="ed7a7-156">Visualizzare proprietà di Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ed7a7-156">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
