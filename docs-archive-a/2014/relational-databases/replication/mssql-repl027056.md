---
title: MSSQL_REPL027056 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027056 error
ms.assetid: 92d62f3c-b8ae-482e-a348-2e9a8ee9786e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fb130321ec54c39559d52e493cc8f3424172fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721347"
---
# <a name="mssql_repl027056"></a><span data-ttu-id="e6700-102">MSSQL_REPL027056</span><span class="sxs-lookup"><span data-stu-id="e6700-102">MSSQL_REPL027056</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e6700-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="e6700-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6700-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e6700-104">Product Name</span></span>|<span data-ttu-id="e6700-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6700-105">SQL Server</span></span>|  
|<span data-ttu-id="e6700-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e6700-106">Event ID</span></span>|<span data-ttu-id="e6700-107">27056</span><span class="sxs-lookup"><span data-stu-id="e6700-107">27056</span></span>|  
|<span data-ttu-id="e6700-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e6700-108">Event Source</span></span>|<span data-ttu-id="e6700-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e6700-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e6700-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e6700-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e6700-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e6700-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e6700-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e6700-112">Message Text</span></span>|<span data-ttu-id="e6700-113">Impossibile modificare la cronologia di generazione in '%1'.</span><span class="sxs-lookup"><span data-stu-id="e6700-113">The merge process was unable to change generation history at the '%1'.</span></span> <span data-ttu-id="e6700-114">Per risolvere il problema, riavviare la sincronizzazione con la registrazione dettagliata della cronologia e specificare un file di output in cui registrare i dati.</span><span class="sxs-lookup"><span data-stu-id="e6700-114">When troubleshooting, restart the synchronization with verbose history logging and specify an output file to which to write.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e6700-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e6700-115">Explanation</span></span>  
 <span data-ttu-id="e6700-116">Questo errore viene solitamente generato come risultato della contesa in tabelle di sistema della replica di tipo merge che hanno raggiunto una dimensione eccessiva.</span><span class="sxs-lookup"><span data-stu-id="e6700-116">This error is typically raised as a result of contention in merge replication system tables that have grown excessively large.</span></span> <span data-ttu-id="e6700-117">L'eccessivo aumento delle dimensioni delle tabelle di sistema è in genere dovuto a un lungo periodo di memorizzazione della pubblicazione, in quanto i metadati devono essere archiviati in queste tabelle fino al raggiungimento del periodo di memorizzazione.</span><span class="sxs-lookup"><span data-stu-id="e6700-117">Large system tables are typically caused by a long publication retention period, because metadata must be stored in these tables until the retention period is reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6700-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e6700-118">User Action</span></span>  
 <span data-ttu-id="e6700-119">**Per risolvere il problema:**</span><span class="sxs-lookup"><span data-stu-id="e6700-119">**To resolve the issue:**</span></span>  
  
1.  <span data-ttu-id="e6700-120">Ridurre il valore dei parametri**DownloadGenerationsPerBatch** e **-UploadGenerationsPerBatch** per l'agente di merge in modo da consentire la continuazione dell'elaborazione mentre si risolve il problema sottostante che causa l'errore.</span><span class="sxs-lookup"><span data-stu-id="e6700-120">Decrease the value of the -**DownloadGenerationsPerBatch** and **-UploadGenerationsPerBatch** parameters for the Merge Agent to allow processing to continue while you address the underlying issue causing the error.</span></span> <span data-ttu-id="e6700-121">I parametri degli agenti possono essere specificati nei profili agente e dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e6700-121">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="e6700-122">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="e6700-122">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="e6700-123">Usare i profili agenti di replica</span><span class="sxs-lookup"><span data-stu-id="e6700-123">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="e6700-124">Visualizzare e modificare i parametri del prompt dei comandi dell'agente di replica &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e6700-124">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="e6700-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e6700-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
2.  <span data-ttu-id="e6700-126">Specificare l'impostazione più bassa possibile per il periodo di memorizzazione della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="e6700-126">Specify the lowest setting possible for the publication retention period.</span></span> <span data-ttu-id="e6700-127">Per altre informazioni, vedere [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="e6700-127">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
3.  <span data-ttu-id="e6700-128">Come parte della manutenzione per la replica di tipo merge, controllare occasionalmente l'aumento delle dimensioni delle tabelle di sistema associate alla replica di tipo merge: **MSmerge_contents**, **MSmerge_genhistory**e **MSmerge_tombstone**, **MSmerge_current_partition_mappings**e **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="e6700-128">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="e6700-129">Reindicizzare periodicamente queste tabelle.</span><span class="sxs-lookup"><span data-stu-id="e6700-129">Periodically re-index these tables.</span></span> <span data-ttu-id="e6700-130">Per altre informazioni, vedere [Riorganizzare e ricompilare gli indici](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e6700-130">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6700-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6700-131">See Also</span></span>  
 [<span data-ttu-id="e6700-132">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="e6700-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
