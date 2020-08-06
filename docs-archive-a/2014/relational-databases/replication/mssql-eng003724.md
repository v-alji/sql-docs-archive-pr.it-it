---
title: MSSQL_ENG003724 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003724 error
ms.assetid: 10cb119d-92df-4124-b85d-cd2f2666c99c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dbfb68575c5ffa73276b3bbe1643381c3f0cc412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725479"
---
# <a name="mssql_eng003724"></a><span data-ttu-id="11fdb-102">MSSQL_ENG003724</span><span class="sxs-lookup"><span data-stu-id="11fdb-102">MSSQL_ENG003724</span></span>
    
## <a name="message-details"></a><span data-ttu-id="11fdb-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="11fdb-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11fdb-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="11fdb-104">Product Name</span></span>|<span data-ttu-id="11fdb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="11fdb-105">SQL Server</span></span>|  
|<span data-ttu-id="11fdb-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="11fdb-106">Event ID</span></span>|<span data-ttu-id="11fdb-107">3724</span><span class="sxs-lookup"><span data-stu-id="11fdb-107">3724</span></span>|  
|<span data-ttu-id="11fdb-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="11fdb-108">Event Source</span></span>|<span data-ttu-id="11fdb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="11fdb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="11fdb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="11fdb-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="11fdb-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="11fdb-111">Symbolic Name</span></span>||  
|<span data-ttu-id="11fdb-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="11fdb-112">Message Text</span></span>|<span data-ttu-id="11fdb-113">Impossibile %S_MSG la %S_MSG '%.\*ls' perché è in uso per la replica.</span><span class="sxs-lookup"><span data-stu-id="11fdb-113">Cannot %S_MSG the %S_MSG '%.\*ls' because it is being used for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="11fdb-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="11fdb-114">Explanation</span></span>  
 <span data-ttu-id="11fdb-115">Quando gli oggetti di un database vengono replicati, vengono contrassegnati come replicati nella tabella di sistema **sysarticles** (per le pubblicazioni snapshot e transazionali) o **sysmergearticles** (per le pubblicazioni di tipo merge).</span><span class="sxs-lookup"><span data-stu-id="11fdb-115">When objects in a database are replicated, they are marked as replicated in the system table **sysarticles** (for snapshot and transactional publications) or **sysmergearticles** (for merge publications).</span></span> <span data-ttu-id="11fdb-116">Se si tenta di eliminare un oggetto replicato, viene generato questo errore.</span><span class="sxs-lookup"><span data-stu-id="11fdb-116">If you attempt drop a replicated object, this error is raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11fdb-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="11fdb-117">User Action</span></span>  
 <span data-ttu-id="11fdb-118">Verificare che l'oggetto di database non sia replicato prima di tentare di eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="11fdb-118">Ensure the database object is not replicated before attempting to drop it.</span></span> <span data-ttu-id="11fdb-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="11fdb-119">For example:</span></span>  
  
-   <span data-ttu-id="11fdb-120">Se l'errore si verifica nel database di pubblicazione, eliminare l'articolo dalla pubblicazione prima di eliminare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="11fdb-120">If the error occurs in the publication database, drop the article from the publication before dropping the object.</span></span> <span data-ttu-id="11fdb-121">Per altre informazioni, vedere [Aggiungere ed eliminare articoli in pubblicazioni esistenti](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="11fdb-121">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
-   <span data-ttu-id="11fdb-122">Se l'errore si verifica nel database di sottoscrizione, eliminare la sottoscrizione prima di eliminare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="11fdb-122">If the error occurs in the subscription database, drop the subscription before dropping the object.</span></span> <span data-ttu-id="11fdb-123">Per altre informazioni, vedere [Sottoscrivere le pubblicazioni](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="11fdb-123">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="11fdb-124">Nelle sottoscrizioni a pubblicazioni transazionali è possibile eliminare la sottoscrizione a un singolo articolo anziché all'intera pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="11fdb-124">For subscriptions to transactional publications, it is possible to drop the subscription to an individual article rather than the entire publication.</span></span> <span data-ttu-id="11fdb-125">Per altre informazioni, vedere [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="11fdb-125">For more information, see [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span>  
  
 <span data-ttu-id="11fdb-126">Se questo errore si verifica in un database non replicato, eseguire [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) per verificare che gli oggetti nel database non siano contrassegnati come replicati.</span><span class="sxs-lookup"><span data-stu-id="11fdb-126">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11fdb-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11fdb-127">See Also</span></span>  
 [<span data-ttu-id="11fdb-128">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="11fdb-128">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
