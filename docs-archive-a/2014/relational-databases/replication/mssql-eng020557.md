---
title: MSSQL_ENG020557 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020557 error
ms.assetid: c43c6952-5b60-4347-b881-11a0004dce24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45c24d453eb95abaa967ae65ceb5934b7dee969e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637803"
---
# <a name="mssql_eng020557"></a><span data-ttu-id="88b95-102">MSSQL_ENG020557</span><span class="sxs-lookup"><span data-stu-id="88b95-102">MSSQL_ENG020557</span></span>
    
## <a name="message-details"></a><span data-ttu-id="88b95-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="88b95-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88b95-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="88b95-104">Product Name</span></span>|<span data-ttu-id="88b95-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="88b95-105">SQL Server</span></span>|  
|<span data-ttu-id="88b95-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="88b95-106">Event ID</span></span>|<span data-ttu-id="88b95-107">20557</span><span class="sxs-lookup"><span data-stu-id="88b95-107">20557</span></span>|  
|<span data-ttu-id="88b95-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="88b95-108">Event Source</span></span>|<span data-ttu-id="88b95-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="88b95-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="88b95-110">Componente</span><span class="sxs-lookup"><span data-stu-id="88b95-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="88b95-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="88b95-111">Symbolic Name</span></span>||  
|<span data-ttu-id="88b95-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="88b95-112">Message Text</span></span>|<span data-ttu-id="88b95-113">Arresto dell'agente.</span><span class="sxs-lookup"><span data-stu-id="88b95-113">Agent shutdown.</span></span> <span data-ttu-id="88b95-114">Per ulteriori informazioni, cercare nella cronologia dei processi di SQL Server Agent il processo '%s'.</span><span class="sxs-lookup"><span data-stu-id="88b95-114">For more information, see the SQL Server Agent job history for job '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="88b95-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="88b95-115">Explanation</span></span>  
 <span data-ttu-id="88b95-116">Un agente di replica è stato arrestato ma nella tabella di cronologia appropriata non è stato scritto nessun motivo oppure l'agente è stato arrestato durante l'esecuzione di un processo.</span><span class="sxs-lookup"><span data-stu-id="88b95-116">A replication agent has shut down without writing a reason to the appropriate history table, or the agent was shut down while in the middle of a process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="88b95-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="88b95-117">User Action</span></span>  
  
-   <span data-ttu-id="88b95-118">Riavviare l'agente per verificare se viene eseguito senza errori.</span><span class="sxs-lookup"><span data-stu-id="88b95-118">Restart the agent to see whether it will now run without failures.</span></span> <span data-ttu-id="88b95-119">Per altre informazioni, vedere [Avviare e arrestare un agente di replica &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) e [Concetti di base relativi ai file eseguibili dell'agente di replica](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="88b95-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="88b95-120">Verificare nella cronologia dell'agente e nella cronologia processo la presenza di eventuali altri errori verificatisi nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="88b95-120">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="88b95-121">Per informazioni sui dettagli di stato e di errore dell'agente di visualizzazione in Monitoraggio replica, vedere [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="88b95-121">For information about how to view agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>
-   <span data-ttu-id="88b95-122">Verificare il funzionamento della connettività di base tra i computer a cui l'agente accede e quindi connettersi a ogni computer usando un'utilità, ad esempio **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="88b95-122">Verify that basic connectivity is working between the computers that are accessed by the agent, and then connect to each computer by using a utility, such as the **sqlcmd** utility.</span></span> <span data-ttu-id="88b95-123">Per la connessione utilizzare lo stesso account con cui l'agente effettua le connessioni.</span><span class="sxs-lookup"><span data-stu-id="88b95-123">When you connect, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="88b95-124">Per ulteriori informazioni sulle autorizzazioni necessarie per ogni account di agente, vedere [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="88b95-124">For more information about the permissions that are required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="88b95-125">Se l'errore si verifica durante la creazione o l'applicazione di uno snapshot, verificare l'eventuale presenza di errori nei file della directory snapshot.</span><span class="sxs-lookup"><span data-stu-id="88b95-125">If the error occurs while you are creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="88b95-126">Se l'errore continua a verificarsi, aumentare il livello di dettaglio per la registrazione delle operazioni dell'agente e specificare un file di output per il log.</span><span class="sxs-lookup"><span data-stu-id="88b95-126">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="88b95-127">A seconda del contesto dell'errore, in questo modo è possibile ottenere ulteriori informazioni sui passaggi che conducono all'errore e messaggi di errore aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="88b95-127">Depending on the context of the error, this could provide the steps leading up to the error and additional error messages.</span></span> <span data-ttu-id="88b95-128">Per ulteriori informazioni sulla configurazione della registrazione per la replica, vedere l'articolo [312292](https://support.microsoft.com/kb/312292)della Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="88b95-128">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b95-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88b95-129">See Also</span></span>  
 [<span data-ttu-id="88b95-130">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="88b95-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
