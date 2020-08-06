---
title: MSSQLSERVER_10535 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10535 (Database Engine error)
ms.assetid: 478fd978-11d9-4155-8329-f599fdbec14b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 439d282f18490a4353d6528276eaf7e4231c503b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715375"
---
# <a name="mssqlserver_10535"></a><span data-ttu-id="3abea-102">MSSQLSERVER_10535</span><span class="sxs-lookup"><span data-stu-id="3abea-102">MSSQLSERVER_10535</span></span>
    
## <a name="details"></a><span data-ttu-id="3abea-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3abea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3abea-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3abea-104">Product Name</span></span>|<span data-ttu-id="3abea-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3abea-105">SQL Server</span></span>|  
|<span data-ttu-id="3abea-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="3abea-106">Event ID</span></span>|<span data-ttu-id="3abea-107">10535</span><span class="sxs-lookup"><span data-stu-id="3abea-107">10535</span></span>|  
|<span data-ttu-id="3abea-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3abea-108">Event Source</span></span>|<span data-ttu-id="3abea-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3abea-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3abea-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3abea-110">Component</span></span>|<span data-ttu-id="3abea-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3abea-111">SQLEngine</span></span>|  
|<span data-ttu-id="3abea-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3abea-112">Symbolic Name</span></span>|<span data-ttu-id="3abea-113">PG_NO_PLAN</span><span class="sxs-lookup"><span data-stu-id="3abea-113">PG_NO_PLAN</span></span>|  
|<span data-ttu-id="3abea-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3abea-114">Message Text</span></span>|<span data-ttu-id="3abea-115">Impossibile cerare la guida di piano '%.\*ls' perché non è stato trovato alcun piano nella cache dei piani corrispondente all'handle di piani specificato.</span><span class="sxs-lookup"><span data-stu-id="3abea-115">Cannot create plan guide '%.\*ls' because a plan was not found in the plan cache that corresponds to the specified plan handle.</span></span> <span data-ttu-id="3abea-116">Specificare un handle di piani memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="3abea-116">Specify a cached plan handle.</span></span> <span data-ttu-id="3abea-117">Per un elenco degli handle di piani memorizzati nella cache, eseguire una query sulla vista a gestione dinamica sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="3abea-117">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3abea-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3abea-118">Explanation</span></span>  
 <span data-ttu-id="3abea-119">Non è stato trovato alcun piano nella cache dei piani corrispondente all'handle di piani specificato.</span><span class="sxs-lookup"><span data-stu-id="3abea-119">A plan was not found in the plan cache that corresponds to the specified plan handle.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3abea-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3abea-120">User Action</span></span>  
 <span data-ttu-id="3abea-121">Specificare un handle di piani memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="3abea-121">Specify a cached plan handle.</span></span> <span data-ttu-id="3abea-122">Per un elenco degli handle di piani memorizzati nella cache, eseguire una query sulla vista a gestione dinamica sys.dm_exec_query_stats.</span><span class="sxs-lookup"><span data-stu-id="3abea-122">For a list of cached plan handles, query the sys.dm_exec_query_stats dynamic management view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abea-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3abea-123">See Also</span></span>  
 <span data-ttu-id="3abea-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3abea-124">[sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) </span></span>  
 [<span data-ttu-id="3abea-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3abea-125">sys.dm_exec_query_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql)  
  
  
