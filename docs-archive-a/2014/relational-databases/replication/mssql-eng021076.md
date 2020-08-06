---
title: MSSQL_ENG021076 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021076 error
ms.assetid: 612e5c59-ba3e-49c3-a3df-56bac3d850a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4161428767ce78726436c0cf794f5250140d35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714184"
---
# <a name="mssql_eng021076"></a><span data-ttu-id="b863d-102">MSSQL_ENG021076</span><span class="sxs-lookup"><span data-stu-id="b863d-102">MSSQL_ENG021076</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b863d-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="b863d-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b863d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b863d-104">Product Name</span></span>|<span data-ttu-id="b863d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b863d-105">SQL Server</span></span>|  
|<span data-ttu-id="b863d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b863d-106">Event ID</span></span>|<span data-ttu-id="b863d-107">21076</span><span class="sxs-lookup"><span data-stu-id="b863d-107">21076</span></span>|  
|<span data-ttu-id="b863d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b863d-108">Event Source</span></span>|<span data-ttu-id="b863d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b863d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b863d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b863d-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b863d-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b863d-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b863d-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b863d-112">Message Text</span></span>|<span data-ttu-id="b863d-113">Lo snapshot iniziale per l'articolo '%s' non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="b863d-113">The initial snapshot for article '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b863d-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b863d-114">Explanation</span></span>  
 <span data-ttu-id="b863d-115">L'errore MSSQL_ENG021076 può essere generato se l'agente di distribuzione viene avviato prima che l'agente snapshot abbia terminato la generazione dello snapshot</span><span class="sxs-lookup"><span data-stu-id="b863d-115">Error MSSQL_ENG021076 can be raised if the Distribution Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span> <span data-ttu-id="b863d-116">e solo se la pubblicazione contiene un unico articolo.</span><span class="sxs-lookup"><span data-stu-id="b863d-116">This error is raised only if the publication contains a single article.</span></span> <span data-ttu-id="b863d-117">Se la pubblicazione contiene più articoli, viene generato invece l'errore MSSQL_ENG021075.</span><span class="sxs-lookup"><span data-stu-id="b863d-117">If the publication contains more than one article, MSSQL_ENG021075 is raised instead.</span></span> <span data-ttu-id="b863d-118">Per altre informazioni, vedere [MSSQL_ENG021075](mssql-eng021075.md).</span><span class="sxs-lookup"><span data-stu-id="b863d-118">For more information, see [MSSQL_ENG021075](mssql-eng021075.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b863d-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b863d-119">User Action</span></span>  
 <span data-ttu-id="b863d-120">Se l'agente snapshot per la pubblicazione non è stato avviato in seguito alla creazione della sottoscrizione o se non è stato avviato dall'ultima volta in cui si è scelto di reinizializzare la sottoscrizione, avviare l'agente snapshot e consentire il completamento delle operazioni prima di avviare l'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b863d-120">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent.</span></span> <span data-ttu-id="b863d-121">Per altre informazioni, vedere [Creare e applicare lo snapshot](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="b863d-121">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="b863d-122">Se l'agente snapshot non viene completato, controllarne la cronologia per individuare eventuali errori e risolverli.</span><span class="sxs-lookup"><span data-stu-id="b863d-122">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="b863d-123">Per informazioni sui dettagli di stato e di errore dell'agente di visualizzazione in Monitoraggio replica, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b863d-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="b863d-124">Se l'errore continua a verificarsi, aumentare il livello di dettaglio per la registrazione delle operazioni dell'agente e specificare un file di output per il log.</span><span class="sxs-lookup"><span data-stu-id="b863d-124">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="b863d-125">A seconda del contesto dell'errore, in questo modo si potrebbero ottenere ulteriori informazioni sui passaggi che conducono all'errore e/o messaggi di errore aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b863d-125">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b863d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b863d-126">See Also</span></span>  
 [<span data-ttu-id="b863d-127">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="b863d-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
