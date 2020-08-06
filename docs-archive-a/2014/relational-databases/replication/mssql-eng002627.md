---
title: MSSQL_ENG002627 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002627 error
ms.assetid: 7f4136ac-3784-4a41-a98c-8a02308e4883
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cf481635d6a24570792c9da04fe71ebea885ce5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725483"
---
# <a name="mssql_eng002627"></a><span data-ttu-id="1b8a6-102">MSSQL_ENG002627</span><span class="sxs-lookup"><span data-stu-id="1b8a6-102">MSSQL_ENG002627</span></span>
    
## <a name="message-details"></a><span data-ttu-id="1b8a6-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="1b8a6-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1b8a6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="1b8a6-104">Product Name</span></span>|<span data-ttu-id="1b8a6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b8a6-105">SQL Server</span></span>|  
|<span data-ttu-id="1b8a6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="1b8a6-106">Event ID</span></span>|<span data-ttu-id="1b8a6-107">2627</span><span class="sxs-lookup"><span data-stu-id="1b8a6-107">2627</span></span>|  
|<span data-ttu-id="1b8a6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="1b8a6-108">Event Source</span></span>|<span data-ttu-id="1b8a6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1b8a6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1b8a6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1b8a6-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="1b8a6-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="1b8a6-111">Symbolic Name</span></span>|<span data-ttu-id="1b8a6-112">N/D</span><span class="sxs-lookup"><span data-stu-id="1b8a6-112">N/A</span></span>|  
|<span data-ttu-id="1b8a6-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="1b8a6-113">Message Text</span></span>|<span data-ttu-id="1b8a6-114">Violazione del vincolo %ls '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-114">Violation of %ls constraint '%.\*ls'.</span></span> <span data-ttu-id="1b8a6-115">Non è possibile inserire la chiave duplicata nell'oggetto '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-115">Cannot insert duplicate key in object '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1b8a6-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1b8a6-116">Explanation</span></span>  
 <span data-ttu-id="1b8a6-117">Questo errore generale può essere generato indipendentemente dal fatto che un database venga o meno replicato.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-117">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="1b8a6-118">Nei database replicati l'errore viene di solito generato in quanto le chiavi primarie non sono state gestite correttamente nella topologia.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-118">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="1b8a6-119">In un ambiente distribuito è fondamentale garantire che lo stesso valore non venga inserito in una colonna chiave primaria o in qualsiasi altra colonna univoca in più di un nodo.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-119">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="1b8a6-120">Le cause possibile includono:</span><span class="sxs-lookup"><span data-stu-id="1b8a6-120">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="1b8a6-121">Le operazioni di inserimento e aggiornamento su una riga vengono eseguite in più di un nodo.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-121">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="1b8a6-122">Sebbene la replica di tipo merge e le sottoscrizioni aggiornabili per la replica transazionale consentano il rilevamento e la risoluzione dei conflitti, è preferibile inserire o aggiornare una determinata riga in un unico nodo.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-122">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="1b8a6-123">La replica transazionale di tipo peer-to-peer non fornisce funzioni di rilevamento e risoluzione dei conflitti e richiede il partizionamento degli inserimenti e degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-123">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="1b8a6-124">È stata inserita una riga in un Sottoscrittore che dovrebbe essere di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-124">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="1b8a6-125">I Sottoscrittori delle pubblicazioni snapshot devono essere considerati come di sola lettura, analogamente ai Sottoscrittori delle pubblicazioni transazionali a meno che non vengano utilizzate sottoscrizioni aggiornabili o una replica transazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-125">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="1b8a6-126">Viene utilizzata una tabella con una colonna Identity, ma la colonna non è gestita in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-126">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1b8a6-127">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="1b8a6-127">User Action</span></span>  
 <span data-ttu-id="1b8a6-128">L'azione richiesta dipende dal motivo per il quale è stato generato l'errore:</span><span class="sxs-lookup"><span data-stu-id="1b8a6-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="1b8a6-129">Le operazioni di inserimento e aggiornamento su una riga vengono eseguite in più di un nodo.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="1b8a6-130">Indipendentemente dal tipo di replica utilizzato, è consigliabile partizionare inserimenti e aggiornamenti quando possibile, in modo da ridurre l'elaborazione richiesta per il rilevamento e la risoluzione dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="1b8a6-131">Per la replica transazionale peer-to-peer, è richiesto il partizionamento di inserimenti e aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="1b8a6-132">Per altre informazioni, vedere [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="1b8a6-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="1b8a6-133">È stata inserita una riga in un Sottoscrittore che dovrebbe essere di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="1b8a6-134">Non inserire o aggiornare righe nel Sottoscrittore a meno che non si stia utilizzando la replica di tipo merge, la replica transazionale con sottoscrizioni aggiornabili o la replica transazionale peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="1b8a6-135">Viene utilizzata una tabella con una colonna Identity, ma la colonna non è gestita in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="1b8a6-136">Per la replica di tipo merge e la replica transazionale con sottoscrizioni aggiornabili, le colonne Identity devono essere gestite automaticamente dalla replica.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="1b8a6-137">Per la replica transazionale peer-to-peer, devono invece essere gestite manualmente.</span><span class="sxs-lookup"><span data-stu-id="1b8a6-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="1b8a6-138">Per altre informazioni, vedere [Replicare colonne Identity](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="1b8a6-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8a6-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b8a6-139">See Also</span></span>  
 <span data-ttu-id="1b8a6-140">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="1b8a6-140">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="1b8a6-141">[Replica di tipo merge](merge/merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="1b8a6-141">[Merge Replication](merge/merge-replication.md) </span></span>  
 <span data-ttu-id="1b8a6-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="1b8a6-142">[Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md) </span></span>  
 [<span data-ttu-id="1b8a6-143">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="1b8a6-143">Updatable Subscriptions for Transactional Replication</span></span>](transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
