---
title: MSSQLSERVER_30089 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9992 (Database Engine error)
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d0b9c71ea620174f993ae87befed8a21bb3d0bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628737"
---
# <a name="mssqlserver_30089"></a><span data-ttu-id="73793-102">MSSQLSERVER_30089</span><span class="sxs-lookup"><span data-stu-id="73793-102">MSSQLSERVER_30089</span></span>
    
## <a name="details"></a><span data-ttu-id="73793-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="73793-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73793-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="73793-104">Product Name</span></span>|<span data-ttu-id="73793-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="73793-105">SQL Server</span></span>|  
|<span data-ttu-id="73793-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="73793-106">Event ID</span></span>|<span data-ttu-id="73793-107">30089</span><span class="sxs-lookup"><span data-stu-id="73793-107">30089</span></span>|  
|<span data-ttu-id="73793-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="73793-108">Event Source</span></span>|<span data-ttu-id="73793-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="73793-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="73793-110">Componente</span><span class="sxs-lookup"><span data-stu-id="73793-110">Component</span></span>|<span data-ttu-id="73793-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="73793-111">SQLEngine</span></span>|  
|<span data-ttu-id="73793-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="73793-112">Symbolic Name</span></span>|<span data-ttu-id="73793-113">IFTS_FDHOST_TERMINATEDABNORMAL</span><span class="sxs-lookup"><span data-stu-id="73793-113">IFTS_FDHOST_TERMINATEDABNORMAL</span></span>|  
|<span data-ttu-id="73793-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="73793-114">Message Text</span></span>|<span data-ttu-id="73793-115">Il processo host del daemon di filtri full-text (FDHost) si è arrestato in modo anomalo.</span><span class="sxs-lookup"><span data-stu-id="73793-115">The fulltext filter daemon host (FDHost) process has stopped abnormally.</span></span> <span data-ttu-id="73793-116">Il problema può essere dovuto a un componente linguistico configurato in modo errato o non funzionante, ad esempio un word breaker, uno stemmer o un filtro, che ha causato un errore irreversibile durante l'indicizzazione full-text o l'elaborazione di query.</span><span class="sxs-lookup"><span data-stu-id="73793-116">This can occur if an incorrectly configured or malfunctioning linguistic component, such as a wordbreaker, stemmer or filter has caused an irrecoverable error during full-text indexing or query processing.</span></span> <span data-ttu-id="73793-117">Il processo verrà riavviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="73793-117">The process will be restarted automatically.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="73793-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="73793-118">Explanation</span></span>  
 <span data-ttu-id="73793-119">Nell'host del daemon di filtri full-text si è verificato un problema che ha forzato l'arresto anomalo.</span><span class="sxs-lookup"><span data-stu-id="73793-119">The full-text filter daemon host has encountered some problem that has forced it to stop abnormally.</span></span> <span data-ttu-id="73793-120">La causa del problema può essere un documento formattato in modo non corretto, un bug nel filtro o nel word breaker oppure un errore nel daemon di filtri.</span><span class="sxs-lookup"><span data-stu-id="73793-120">The cause of the problem could be a badly formatted document, a bug in the filter or word-breaker, or a problem in filter daemon.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73793-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="73793-121">User Action</span></span>  
 <span data-ttu-id="73793-122">In genere il daemon eseguirà il recupero dall'errore.</span><span class="sxs-lookup"><span data-stu-id="73793-122">Typically, the daemon will recover from the error.</span></span> <span data-ttu-id="73793-123">Se il problema si ripete, è necessario risolverlo.</span><span class="sxs-lookup"><span data-stu-id="73793-123">If it is consistently failing, troubleshooting is necessary.</span></span> <span data-ttu-id="73793-124">Per isolare il problema, provare le soluzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="73793-124">Try the following to isolate the issue:</span></span>  
  
1.  <span data-ttu-id="73793-125">Se è stato installato recentemente un nuovo componente linguistico, rimuoverlo dal sistema.</span><span class="sxs-lookup"><span data-stu-id="73793-125">If a new linguistic component has been installed recently, remove it from the system.</span></span>  
  
2.  <span data-ttu-id="73793-126">Analizzare il log di tipo ricerca per identificare qualsiasi nuovo documento per cui non è stato possibile eseguire l'indicizzazione full-text, quindi rimuovere il documento.</span><span class="sxs-lookup"><span data-stu-id="73793-126">Look at the crawl log to identify any new document that failed to be full-text indexed, and remove it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73793-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73793-127">See Also</span></span>  
 <span data-ttu-id="73793-128">[sp_help_fulltext_system_components &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73793-128">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="73793-129">[Configurare e gestire Word breaker e stemmer per la ricerca](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="73793-129">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="73793-130">Configurare e gestire filtri per la ricerca</span><span class="sxs-lookup"><span data-stu-id="73793-130">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
