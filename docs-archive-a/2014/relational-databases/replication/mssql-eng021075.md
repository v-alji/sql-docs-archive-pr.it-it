---
title: MSSQL_ENG021075 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021075 error
ms.assetid: c8c29543-d1f6-49d5-b6c8-e8c3aa373090
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 20f2428038326681f5f8eb877e5c3017ced30f00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635499"
---
# <a name="mssql_eng021075"></a><span data-ttu-id="82202-102">MSSQL_ENG021075</span><span class="sxs-lookup"><span data-stu-id="82202-102">MSSQL_ENG021075</span></span>
    
## <a name="message-details"></a><span data-ttu-id="82202-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="82202-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82202-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="82202-104">Product Name</span></span>|<span data-ttu-id="82202-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="82202-105">SQL Server</span></span>|  
|<span data-ttu-id="82202-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="82202-106">Event ID</span></span>|<span data-ttu-id="82202-107">21075</span><span class="sxs-lookup"><span data-stu-id="82202-107">21075</span></span>|  
|<span data-ttu-id="82202-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="82202-108">Event Source</span></span>|<span data-ttu-id="82202-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="82202-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="82202-110">Componente</span><span class="sxs-lookup"><span data-stu-id="82202-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="82202-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="82202-111">Symbolic Name</span></span>||  
|<span data-ttu-id="82202-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="82202-112">Message Text</span></span>|<span data-ttu-id="82202-113">Lo snapshot iniziale per la pubblicazione '%s' non è ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="82202-113">The initial snapshot for publication '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82202-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="82202-114">Explanation</span></span>  
 <span data-ttu-id="82202-115">L'errore MSSQL_ENG021075 viene generato in caso di avvio dell'agente di distribuzione o di merge prima che l'agente snapshot abbia completato la generazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="82202-115">Error MSSQL_ENG021075 is raised if the Distribution Agent or Merge Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82202-116">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="82202-116">User Action</span></span>  
 <span data-ttu-id="82202-117">Se l'agente snapshot per la pubblicazione non è stato avviato dopo la creazione della sottoscrizione oppure dall'ultima reinizializzazione della sottoscrizione, avviare l'agente snapshot e attenderne il completamento prima di avviare l'agente di distribuzione o di merge.</span><span class="sxs-lookup"><span data-stu-id="82202-117">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent or Merge Agent.</span></span> <span data-ttu-id="82202-118">Per altre informazioni, vedere [Creare e applicare lo snapshot](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="82202-118">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="82202-119">Se l'agente snapshot non viene completato, controllarne la cronologia per individuare eventuali errori e risolverli.</span><span class="sxs-lookup"><span data-stu-id="82202-119">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="82202-120">Per informazioni sui dettagli di stato e di errore dell'agente di visualizzazione in Monitoraggio replica, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="82202-120">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="82202-121">Se l'errore continua a verificarsi, aumentare il livello di dettaglio per la registrazione delle operazioni dell'agente e specificare un file di output per il log.</span><span class="sxs-lookup"><span data-stu-id="82202-121">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="82202-122">A seconda del contesto dell'errore, in questo modo si potrebbero ottenere ulteriori informazioni sui passaggi che conducono all'errore e/o messaggi di errore aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="82202-122">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82202-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82202-123">See Also</span></span>  
 [<span data-ttu-id="82202-124">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="82202-124">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
