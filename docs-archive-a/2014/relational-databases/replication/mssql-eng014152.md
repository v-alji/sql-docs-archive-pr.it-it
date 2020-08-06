---
title: MSSQL_ENG014152 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014152 error
ms.assetid: 4215e2b1-cd30-441f-9671-9afc742adf6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 615b9cf2996653d86c44d6e43a83e01e8287b110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627205"
---
# <a name="mssql_eng014152"></a><span data-ttu-id="2797a-102">MSSQL_ENG014152</span><span class="sxs-lookup"><span data-stu-id="2797a-102">MSSQL_ENG014152</span></span>
    
## <a name="message-details"></a><span data-ttu-id="2797a-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="2797a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2797a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="2797a-104">Product Name</span></span>|<span data-ttu-id="2797a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2797a-105">SQL Server</span></span>|  
|<span data-ttu-id="2797a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="2797a-106">Event ID</span></span>|<span data-ttu-id="2797a-107">14152</span><span class="sxs-lookup"><span data-stu-id="2797a-107">14152</span></span>|  
|<span data-ttu-id="2797a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="2797a-108">Event Source</span></span>|<span data-ttu-id="2797a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2797a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2797a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2797a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="2797a-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="2797a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="2797a-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2797a-112">Message Text</span></span>|<span data-ttu-id="2797a-113">Replica-%s: ripetizione dell'esecuzione dell'agente %s pianificata.</span><span class="sxs-lookup"><span data-stu-id="2797a-113">Replication-%s: agent %s scheduled for retry.</span></span> <span data-ttu-id="2797a-114">%s</span><span class="sxs-lookup"><span data-stu-id="2797a-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2797a-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="2797a-115">Explanation</span></span>  
 <span data-ttu-id="2797a-116">L'agente di replica specificato è stato pianificato in modo da tentare nuovamente l'esecuzione dell'operazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="2797a-116">The specified replication agent has been scheduled to retry the requested operation.</span></span> <span data-ttu-id="2797a-117">Verranno eseguiti nuovi tentativi finché non verrà raggiunto il numero massimo di tentativi configurato per il passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="2797a-117">The process continues to retry until it reaches the configured maximum number of retry attempts for the job step.</span></span>  
  
 <span data-ttu-id="2797a-118">Viene in genere eseguito un nuovo tentativo per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2797a-118">A retry typically occurs because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="2797a-119">È stato superato il valore di **QueryTimeout** .</span><span class="sxs-lookup"><span data-stu-id="2797a-119">The **QueryTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="2797a-120">È stato superato il valore di **LoginTimeout** .</span><span class="sxs-lookup"><span data-stu-id="2797a-120">The **LoginTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="2797a-121">Il processo di replica è stato scelto come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="2797a-121">The replication process was chosen as a deadlock victim.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2797a-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2797a-122">User Action</span></span>  
 <span data-ttu-id="2797a-123">Se il messaggio relativo a nuovi tentativi non viene visualizzato di frequente, non è richiesto nessun intervento da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2797a-123">If the retry message is infrequent, no user action is required.</span></span>  
  
 <span data-ttu-id="2797a-124">Utilizzare [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) per visualizzare l'impostazione corrente relativa al numero massimo di tentativi di esecuzione del passaggio **Run agent** per l'agente di replica specificato.</span><span class="sxs-lookup"><span data-stu-id="2797a-124">Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) to view the current setting for the maximum number of times the **Run agent** step for the specified replication agent will retry.</span></span> <span data-ttu-id="2797a-125">È possibile utilizzare il **@retry_attempts** parametro della stored procedure [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) per modificare il numero di tentativi di ripetizione di un passaggio di processo.</span><span class="sxs-lookup"><span data-stu-id="2797a-125">You can use the **@retry_attempts** parameter of the [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) stored procedure to adjust the number of times a job step retries.</span></span>  
  
 <span data-ttu-id="2797a-126">Se il messaggio relativo a nuovi tentativi viene visualizzato di frequente, risolvere il problema in base al messaggio che causa l'esecuzione di nuovi tentativi.</span><span class="sxs-lookup"><span data-stu-id="2797a-126">If the retry message recurs frequently, troubleshoot the issue based on the message that is causing the retry.</span></span> <span data-ttu-id="2797a-127">Verificare nella cronologia dell'agente la presenza di messaggi che indicano il motivo per cui è stato necessario pianificare il nuovo tentativo.</span><span class="sxs-lookup"><span data-stu-id="2797a-127">Check the agent's history for messages that indicate why the retry had to be scheduled.</span></span> <span data-ttu-id="2797a-128">In alcuni casi potrebbe essere necessario attivare un livello di registrazione più dettagliato per l'agente di replica.</span><span class="sxs-lookup"><span data-stu-id="2797a-128">In some cases you may have to enable more detailed logging for your replication agent.</span></span> <span data-ttu-id="2797a-129">Per ulteriori informazioni sulla configurazione della registrazione per la replica, vedere l'articolo [312292](https://support.microsoft.com/kb/312292)della Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="2797a-129">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2797a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2797a-130">See Also</span></span>  
 [<span data-ttu-id="2797a-131">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="2797a-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
