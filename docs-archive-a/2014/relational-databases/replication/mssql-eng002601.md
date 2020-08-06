---
title: MSSQL_ENG002601 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG002601 error
ms.assetid: 657c3ae6-9e4b-4c60-becc-4caf7435c1dc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2e8340fef83749fd6d041af42566b10ed3542c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724512"
---
# <a name="mssql_eng002601"></a><span data-ttu-id="0f0ad-102">MSSQL_ENG002601</span><span class="sxs-lookup"><span data-stu-id="0f0ad-102">MSSQL_ENG002601</span></span>
    
## <a name="message-details"></a><span data-ttu-id="0f0ad-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="0f0ad-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f0ad-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0f0ad-104">Product Name</span></span>|<span data-ttu-id="0f0ad-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f0ad-105">SQL Server</span></span>|  
|<span data-ttu-id="0f0ad-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0f0ad-106">Event ID</span></span>|<span data-ttu-id="0f0ad-107">2601</span><span class="sxs-lookup"><span data-stu-id="0f0ad-107">2601</span></span>|  
|<span data-ttu-id="0f0ad-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0f0ad-108">Event Source</span></span>|<span data-ttu-id="0f0ad-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0f0ad-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0f0ad-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0f0ad-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="0f0ad-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0f0ad-111">Symbolic Name</span></span>|<span data-ttu-id="0f0ad-112">N/D</span><span class="sxs-lookup"><span data-stu-id="0f0ad-112">N/A</span></span>|  
|<span data-ttu-id="0f0ad-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0f0ad-113">Message Text</span></span>|<span data-ttu-id="0f0ad-114">Non è possibile inserire la riga di chiave duplicata nell'oggetto '%.\*ls!' con indice univoco '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-114">Cannot insert duplicate key row in object '%.\*ls' with unique index '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0f0ad-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0f0ad-115">Explanation</span></span>  
 <span data-ttu-id="0f0ad-116">Questo errore generale può essere generato indipendentemente dal fatto che un database venga o meno replicato.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-116">This is a general error that can be raised regardless of whether a database is replicated.</span></span> <span data-ttu-id="0f0ad-117">Nei database replicati l'errore viene di solito generato in quanto le chiavi primarie non sono state gestite correttamente nella topologia.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-117">In replicated databases, the error is typically raised because primary keys have not been managed appropriately across the topology.</span></span> <span data-ttu-id="0f0ad-118">In un ambiente distribuito è fondamentale garantire che lo stesso valore non venga inserito in una colonna chiave primaria o in qualsiasi altra colonna univoca in più di un nodo.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-118">In a distributed environment it is essential to ensure that the same value is not inserted into a primary key column or any other unique column at more than one node.</span></span> <span data-ttu-id="0f0ad-119">Le cause possibile includono:</span><span class="sxs-lookup"><span data-stu-id="0f0ad-119">Possible causes include the following:</span></span>  
  
-   <span data-ttu-id="0f0ad-120">Le operazioni di inserimento e aggiornamento su una riga vengono eseguite in più di un nodo.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-120">Inserts and updates to a row are occurring at more than one node.</span></span> <span data-ttu-id="0f0ad-121">Sebbene la replica di tipo merge e le sottoscrizioni aggiornabili per la replica transazionale consentano il rilevamento e la risoluzione dei conflitti, è preferibile inserire o aggiornare una determinata riga in un unico nodo.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-121">Merge replication and updatable subscriptions for transactional replication both provide conflict detection and resolution, but it is still preferable to insert or update a given row at only one node.</span></span> <span data-ttu-id="0f0ad-122">La replica transazionale di tipo peer-to-peer non fornisce funzioni di rilevamento e risoluzione dei conflitti e richiede il partizionamento degli inserimenti e degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-122">Peer-to-peer transactional does not provide conflict detection and resolution; it requires that inserts and updates be partitioned.</span></span>  
  
-   <span data-ttu-id="0f0ad-123">È stata inserita una riga in un Sottoscrittore che dovrebbe essere di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-123">A row was inserted at a Subscriber that should be read-only.</span></span> <span data-ttu-id="0f0ad-124">I Sottoscrittori delle pubblicazioni snapshot devono essere considerati come di sola lettura, analogamente ai Sottoscrittori delle pubblicazioni transazionali a meno che non vengano utilizzate sottoscrizioni aggiornabili o una replica transazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-124">Subscribers to snapshot publications should be treated as read-only, as should Subscribers to transactional publications unless updatable subscriptions or peer-to-peer transactional replication is used.</span></span>  
  
-   <span data-ttu-id="0f0ad-125">Viene utilizzata una tabella con una colonna Identity, ma la colonna non è gestita in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-125">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
-   <span data-ttu-id="0f0ad-126">Nella replica di tipo merge questo errore può verificarsi anche durante un inserimento nella tabella di sistema **MSmerge_contents**. L'errore generato è simile all'errore "Impossibile inserire la riga di chiave duplicata nell'oggetto 'MSmerge_contents' con indice univoco 'ucl1SycContents'".</span><span class="sxs-lookup"><span data-stu-id="0f0ad-126">In merge replication, this error can also occur during an insert into the system table **MSmerge_contents**; the error raised is similar to: Cannot insert duplicate key row in object 'MSmerge_contents' with unique index 'ucl1SycContents.'</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f0ad-127">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0f0ad-127">User Action</span></span>  
 <span data-ttu-id="0f0ad-128">L'azione richiesta dipende dal motivo per il quale è stato generato l'errore:</span><span class="sxs-lookup"><span data-stu-id="0f0ad-128">The action required depends on the reason the error was raised:</span></span>  
  
-   <span data-ttu-id="0f0ad-129">Le operazioni di inserimento e aggiornamento su una riga vengono eseguite in più di un nodo.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-129">Inserts and updates to a row are occurring at more than one node.</span></span>  
  
     <span data-ttu-id="0f0ad-130">Indipendentemente dal tipo di replica utilizzato, è consigliabile partizionare inserimenti e aggiornamenti quando possibile, in modo da ridurre l'elaborazione richiesta per il rilevamento e la risoluzione dei conflitti.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-130">Regardless of the type of replication used, we recommend that you partition inserts and updates whenever possible, because this reduces the processing required for conflict detection and resolution.</span></span> <span data-ttu-id="0f0ad-131">Per la replica transazionale peer-to-peer, è richiesto il partizionamento di inserimenti e aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-131">For peer-to-peer transactional replication, partitioning inserts and updates is required.</span></span> <span data-ttu-id="0f0ad-132">Per altre informazioni, vedere [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0f0ad-132">For more information, see [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="0f0ad-133">È stata inserita una riga in un Sottoscrittore che dovrebbe essere di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-133">A row was inserted at a Subscriber that should be read-only.</span></span>  
  
     <span data-ttu-id="0f0ad-134">Non inserire o aggiornare righe nel Sottoscrittore a meno che non si stia utilizzando la replica di tipo merge, la replica transazionale con sottoscrizioni aggiornabili o la replica transazionale peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-134">Do not insert or update rows at the Subscriber unless you are using merge replication, transactional replication with updatable subscriptions, or peer-to-peer transactional replication.</span></span>  
  
-   <span data-ttu-id="0f0ad-135">Viene utilizzata una tabella con una colonna Identity, ma la colonna non è gestita in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-135">A table with an identity column is being used, but the column is not managed appropriately.</span></span>  
  
     <span data-ttu-id="0f0ad-136">Per la replica di tipo merge e la replica transazionale con sottoscrizioni aggiornabili, le colonne Identity devono essere gestite automaticamente dalla replica.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-136">For merge replication and transactional replication with updatable subscriptions, identity columns should be managed automatically by replication.</span></span> <span data-ttu-id="0f0ad-137">Per la replica transazionale peer-to-peer, devono invece essere gestite manualmente.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-137">For peer-to-peer transactional replication, they must be managed manually.</span></span> <span data-ttu-id="0f0ad-138">Per altre informazioni, vedere [Replicare colonne Identity](publish/replicate-identity-columns.md).</span><span class="sxs-lookup"><span data-stu-id="0f0ad-138">For more information, see [Replicate Identity Columns](publish/replicate-identity-columns.md).</span></span>  
  
-   <span data-ttu-id="0f0ad-139">L'errore si verifica durante un inserimento nella tabella di sistema **MSmerge_contents**.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-139">The error occurs during an insert into the system table **MSmerge_contents**.</span></span>  
  
     <span data-ttu-id="0f0ad-140">Tale errore può verificarsi a causa di un valore non corretto per la proprietà del filtro join **join_unique_key**.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-140">This error can occur because of an incorrect value for the join filter property **join_unique_key**.</span></span> <span data-ttu-id="0f0ad-141">Tale proprietà deve essere impostata su TRUE solo se la colonna unita in join nella tabella padre è univoca.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-141">This property should be set to TRUE only if the joined column in the parent table is unique.</span></span> <span data-ttu-id="0f0ad-142">Se la proprietà è impostata su TRUE ma la colonna non è univoca, viene generato l'errore.</span><span class="sxs-lookup"><span data-stu-id="0f0ad-142">If the property is set to TRUE, but the column is not unique, this error is raised.</span></span> <span data-ttu-id="0f0ad-143">Per ulteriori informazioni sull'impostazione di questa proprietà, vedere [Definizione e modifica di un filtro di join tra articoli di merge](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="0f0ad-143">For more information on setting this property, see [Define and Modify a Join Filter Between Merge Articles](publish/define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f0ad-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f0ad-144">See Also</span></span>  
 [<span data-ttu-id="0f0ad-145">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="0f0ad-145">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
