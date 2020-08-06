---
title: MSSQL_ENG014151 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014151 error
ms.assetid: 54b45e70-46b3-4c7a-a5bf-06f6dd028ceb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2796451f6f681cfb0ce529ed44a946c34135649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624062"
---
# <a name="mssql_eng014151"></a><span data-ttu-id="b7c75-102">MSSQL_ENG014151</span><span class="sxs-lookup"><span data-stu-id="b7c75-102">MSSQL_ENG014151</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b7c75-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="b7c75-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7c75-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b7c75-104">Product Name</span></span>|<span data-ttu-id="b7c75-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7c75-105">SQL Server</span></span>|  
|<span data-ttu-id="b7c75-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b7c75-106">Event ID</span></span>|<span data-ttu-id="b7c75-107">14151</span><span class="sxs-lookup"><span data-stu-id="b7c75-107">14151</span></span>|  
|<span data-ttu-id="b7c75-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b7c75-108">Event Source</span></span>|<span data-ttu-id="b7c75-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b7c75-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b7c75-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b7c75-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b7c75-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b7c75-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b7c75-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b7c75-112">Message Text</span></span>|<span data-ttu-id="b7c75-113">Replica-%s: l'esecuzione dell'agente %s non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b7c75-113">Replication-%s: agent %s failed.</span></span> <span data-ttu-id="b7c75-114">%s</span><span class="sxs-lookup"><span data-stu-id="b7c75-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b7c75-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b7c75-115">Explanation</span></span>  
 <span data-ttu-id="b7c75-116">Questo errore viene generato per qualunque errore dell'agente di replica.</span><span class="sxs-lookup"><span data-stu-id="b7c75-116">This error is raised for any replication agent failure.</span></span> <span data-ttu-id="b7c75-117">Il testo alla fine del messaggio dipende dal contesto dell'errore.</span><span class="sxs-lookup"><span data-stu-id="b7c75-117">The text at the end of the message depends on the context of the failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b7c75-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b7c75-118">User Action</span></span>  
 <span data-ttu-id="b7c75-119">Questo errore può verificarsi in numerose situazioni. Utilizzare gli approcci seguenti in base alla necessità:</span><span class="sxs-lookup"><span data-stu-id="b7c75-119">This error can occur in a number of situations; use the following approaches as necessary:</span></span>  
  
-   <span data-ttu-id="b7c75-120">Riavviare l'agente che ha presentato l'errore per vedere se viene eseguito senza errori.</span><span class="sxs-lookup"><span data-stu-id="b7c75-120">Restart the failed agent to see if it will now run without failures.</span></span> <span data-ttu-id="b7c75-121">Per altre informazioni, vedere [Avviare e arrestare un agente di replica &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) e [Concetti di base relativi ai file eseguibili dell'agente di replica](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="b7c75-121">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="b7c75-122">Verificare nella cronologia dell'agente e nella cronologia processo la presenza di eventuali altri errori verificatisi nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="b7c75-122">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="b7c75-123">Per informazioni sui dettagli di stato e di errore dell'agente di visualizzazione in Monitoraggio replica, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b7c75-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="b7c75-124">Verificare il funzionamento della connettività di base tra i computer a cui l'agente accede, quindi connettersi a ogni computer con un'utilità come [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b7c75-124">Verify that basic connectivity is working between the computers accessed by the agent, and then connect to each computer with a utility like the [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="b7c75-125">Quando ci si connette, utilizzare lo stesso account con cui l'agente effettua le connessioni.</span><span class="sxs-lookup"><span data-stu-id="b7c75-125">When connecting, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="b7c75-126">Per ulteriori informazioni sulle autorizzazioni richieste da ogni account di agente, vedere [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="b7c75-126">For more information about the permissions required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="b7c75-127">Se l'errore si verifica durante la creazione o l'applicazione di uno snapshot, verificare l'eventuale presenza di errori nei file della directory snapshot.</span><span class="sxs-lookup"><span data-stu-id="b7c75-127">If the error occurs while creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="b7c75-128">Se l'errore continua a verificarsi, aumentare il livello di dettaglio per la registrazione delle operazioni dell'agente e specificare un file di output per il log.</span><span class="sxs-lookup"><span data-stu-id="b7c75-128">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="b7c75-129">A seconda del contesto dell'errore, in questo modo si potrebbero ottenere ulteriori informazioni sui passaggi che conducono all'errore e/o messaggi di errore aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b7c75-129">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c75-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7c75-130">See Also</span></span>  
 <span data-ttu-id="b7c75-131">[Amministrazione dell'agente di replica](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="b7c75-131">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="b7c75-132">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="b7c75-132">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="b7c75-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="b7c75-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="b7c75-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="b7c75-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="b7c75-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="b7c75-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="b7c75-136">[Agente di lettura coda repliche](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="b7c75-136">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="b7c75-137">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="b7c75-137">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
