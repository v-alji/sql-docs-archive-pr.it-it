---
title: MSSQLSERVER_10519 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10519 (Database Engine error)
ms.assetid: 3be393a1-b186-41ae-afb9-a3d07ff354bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0ec584649842f787b1de9d2ea6d161aea6970250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721472"
---
# <a name="mssqlserver_10519"></a><span data-ttu-id="987f7-102">MSSQLSERVER_10519</span><span class="sxs-lookup"><span data-stu-id="987f7-102">MSSQLSERVER_10519</span></span>
    
## <a name="details"></a><span data-ttu-id="987f7-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="987f7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="987f7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="987f7-104">Product Name</span></span>|<span data-ttu-id="987f7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="987f7-105">SQL Server</span></span>|  
|<span data-ttu-id="987f7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="987f7-106">Event ID</span></span>|<span data-ttu-id="987f7-107">10519</span><span class="sxs-lookup"><span data-stu-id="987f7-107">10519</span></span>|  
|<span data-ttu-id="987f7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="987f7-108">Event Source</span></span>|<span data-ttu-id="987f7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="987f7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="987f7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="987f7-110">Component</span></span>|<span data-ttu-id="987f7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="987f7-111">SQLEngine</span></span>|  
|<span data-ttu-id="987f7-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="987f7-112">Symbolic Name</span></span>|<span data-ttu-id="987f7-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span><span class="sxs-lookup"><span data-stu-id="987f7-113">PG_INCOMPATIBLE_STMT_AND_HINTS</span></span>|  
|<span data-ttu-id="987f7-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="987f7-114">Message Text</span></span>|<span data-ttu-id="987f7-115">Impossibile creare la guida di piano '%.\*ls' perché gli hint specificati in `@hints` non possono essere applicati all'istruzione specificata da `@stmt` o `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="987f7-115">Cannot create plan guide '%.\*ls' because the hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span> <span data-ttu-id="987f7-116">Verificare che gli hint possano essere applicati all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="987f7-116">Verify that the hints can be applied to the statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="987f7-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="987f7-117">Explanation</span></span>  
 <span data-ttu-id="987f7-118">Gli hint specificati in `@hints` non possono essere applicati all'istruzione specificata da `@stmt` o `@statement_start_offset`.</span><span class="sxs-lookup"><span data-stu-id="987f7-118">The hints specified in `@hints` cannot be applied to the statement specified by either `@stmt` or `@statement_start_offset`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="987f7-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="987f7-119">User Action</span></span>  
 <span data-ttu-id="987f7-120">Specificare hint che possono essere applicati all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="987f7-120">Specify hints that can be applied to the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987f7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="987f7-121">See Also</span></span>  
 <span data-ttu-id="987f7-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="987f7-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="987f7-123">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="987f7-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="987f7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="987f7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
