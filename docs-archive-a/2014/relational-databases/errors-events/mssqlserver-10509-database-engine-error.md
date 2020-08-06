---
title: MSSQLSERVER_10509 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10509 (Database Engine error)
ms.assetid: e9dd5357-ee3d-420a-9a89-d12ab5404e73
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73194c7da553bf27acb78d8c4e7d71bc93f457d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724740"
---
# <a name="mssqlserver_10509"></a><span data-ttu-id="74665-102">MSSQLSERVER_10509</span><span class="sxs-lookup"><span data-stu-id="74665-102">MSSQLSERVER_10509</span></span>
    
## <a name="details"></a><span data-ttu-id="74665-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="74665-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74665-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="74665-104">Product Name</span></span>|<span data-ttu-id="74665-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="74665-105">SQL Server</span></span>|  
|<span data-ttu-id="74665-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="74665-106">Event ID</span></span>|<span data-ttu-id="74665-107">10509</span><span class="sxs-lookup"><span data-stu-id="74665-107">10509</span></span>|  
|<span data-ttu-id="74665-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="74665-108">Event Source</span></span>|<span data-ttu-id="74665-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="74665-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="74665-110">Componente</span><span class="sxs-lookup"><span data-stu-id="74665-110">Component</span></span>|<span data-ttu-id="74665-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="74665-111">SQLEngine</span></span>|  
|<span data-ttu-id="74665-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="74665-112">Symbolic Name</span></span>|<span data-ttu-id="74665-113">PG_INVALID_STMT</span><span class="sxs-lookup"><span data-stu-id="74665-113">PG_INVALID_STMT</span></span>|  
|<span data-ttu-id="74665-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="74665-114">Message Text</span></span>|<span data-ttu-id="74665-115">Impossibile creare la guida di piano '%.\*ls' perché l'istruzione specificata da `@stmt` o `@statement_start_offset` contiene un errore di sintassi o non può essere usata in una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="74665-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span> <span data-ttu-id="74665-116">Specificare una singola istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] valida o una posizione di inizio valida dell'istruzione nel batch.</span><span class="sxs-lookup"><span data-stu-id="74665-116">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="74665-117">Per ottenere una posizione di inizio valida, eseguire una query sulla colonna statement_start_offset nella funzione a gestione dinamica sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="74665-117">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="74665-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="74665-118">Explanation</span></span>  
 <span data-ttu-id="74665-119">L'istruzione specificata da `@stmt` o `@statement_start_offset` contiene un errore di sintassi o non può essere utilizzata in una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="74665-119">The statement specified by `@stmt` or `@statement_start_offset` either contains a syntax error or is ineligible for use in a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74665-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="74665-120">User Action</span></span>  
 <span data-ttu-id="74665-121">Specificare una singola istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] valida o una posizione di inizio valida dell'istruzione nel batch.</span><span class="sxs-lookup"><span data-stu-id="74665-121">Provide a single valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a valid starting position of the statement within the batch.</span></span> <span data-ttu-id="74665-122">Per ottenere una posizione di inizio valida, eseguire una query sulla colonna statement_start_offset nella funzione a gestione dinamica sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="74665-122">To obtain a valid starting position, query the statement_start_offset column in the sys.dm_exec_query_stats dynamic management function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74665-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74665-123">See Also</span></span>  
 <span data-ttu-id="74665-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="74665-124">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="74665-125">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="74665-125">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="74665-126">[sys. dm_exec_query_stats &#40;&#41;Transact-SQL](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="74665-126">[sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) </span></span>  
 [<span data-ttu-id="74665-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="74665-127">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
