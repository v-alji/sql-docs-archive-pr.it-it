---
title: MSSQLSERVER_10536 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10536 (Database Engine error)
ms.assetid: 9f97b41f-0ef8-4ad2-aec0-906a5d7522ba
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 00d08f4555f38b61661a917ba94c023f9dd6c4a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718227"
---
# <a name="mssqlserver_10536"></a><span data-ttu-id="ab1f3-102">MSSQLSERVER_10536</span><span class="sxs-lookup"><span data-stu-id="ab1f3-102">MSSQLSERVER_10536</span></span>
    
## <a name="details"></a><span data-ttu-id="ab1f3-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ab1f3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab1f3-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ab1f3-104">Product Name</span></span>|<span data-ttu-id="ab1f3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ab1f3-105">SQL Server</span></span>|  
|<span data-ttu-id="ab1f3-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="ab1f3-106">Event ID</span></span>|<span data-ttu-id="ab1f3-107">10536</span><span class="sxs-lookup"><span data-stu-id="ab1f3-107">10536</span></span>|  
|<span data-ttu-id="ab1f3-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ab1f3-108">Event Source</span></span>|<span data-ttu-id="ab1f3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ab1f3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ab1f3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ab1f3-110">Component</span></span>|<span data-ttu-id="ab1f3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ab1f3-111">SQLEngine</span></span>|  
|<span data-ttu-id="ab1f3-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="ab1f3-112">Symbolic Name</span></span>|<span data-ttu-id="ab1f3-113">PG_TOO_MANY_STMTS</span><span class="sxs-lookup"><span data-stu-id="ab1f3-113">PG_TOO_MANY_STMTS</span></span>|  
|<span data-ttu-id="ab1f3-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ab1f3-114">Message Text</span></span>|<span data-ttu-id="ab1f3-115">Impossibile creare la guida di piano '%.\*ls' perché il batch o il modulo corrispondente al valore `@plan_handle` specificato contiene più di 1000 istruzioni idonee.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-115">Cannot create plan guide '%.\*ls' because the batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span> <span data-ttu-id="ab1f3-116">Creare una guida di piano per ciascuna istruzione nel batch o nel modulo specificando un valore `statement_start_offset` per ciascuna istruzione.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-116">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ab1f3-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ab1f3-117">Explanation</span></span>  
 <span data-ttu-id="ab1f3-118">Il batch o il modulo corrispondente al valore `@plan_handle` contiene più di 1000 istruzioni idonee.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-118">The batch or module corresponding to the specified `@plan_handle` contains more than 1000 eligible statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab1f3-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ab1f3-119">User Action</span></span>  
 <span data-ttu-id="ab1f3-120">Creare una guida di piano per ciascuna istruzione nel batch o nel modulo specificando un valore `statement_start_offset` per ciascuna istruzione.</span><span class="sxs-lookup"><span data-stu-id="ab1f3-120">Create a plan guide for each statement in the batch or module by specifying a `statement_start_offset` value for each statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1f3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab1f3-121">See Also</span></span>  
 <span data-ttu-id="ab1f3-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ab1f3-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="ab1f3-123">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="ab1f3-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="ab1f3-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ab1f3-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
