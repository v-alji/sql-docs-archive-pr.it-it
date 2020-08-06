---
title: MSSQLSERVER_10507 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10507 (Database Engine error)
ms.assetid: cd83fa81-ac37-4eda-a3c3-17610b051de2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a80e48948c03b370c07742fabbb3cf8eb3e74315
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722863"
---
# <a name="mssqlserver_10507"></a><span data-ttu-id="319d7-102">MSSQLSERVER_10507</span><span class="sxs-lookup"><span data-stu-id="319d7-102">MSSQLSERVER_10507</span></span>
    
## <a name="details"></a><span data-ttu-id="319d7-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="319d7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="319d7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="319d7-104">Product Name</span></span>|<span data-ttu-id="319d7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="319d7-105">SQL Server</span></span>|  
|<span data-ttu-id="319d7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="319d7-106">Event ID</span></span>|<span data-ttu-id="319d7-107">10507</span><span class="sxs-lookup"><span data-stu-id="319d7-107">10507</span></span>|  
|<span data-ttu-id="319d7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="319d7-108">Event Source</span></span>|<span data-ttu-id="319d7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="319d7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="319d7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="319d7-110">Component</span></span>|<span data-ttu-id="319d7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="319d7-111">SQLEngine</span></span>|  
|<span data-ttu-id="319d7-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="319d7-112">Symbolic Name</span></span>|<span data-ttu-id="319d7-113">PG_STMT_DOES_NOT_MATCH</span><span class="sxs-lookup"><span data-stu-id="319d7-113">PG_STMT_DOES_NOT_MATCH</span></span>|  
|<span data-ttu-id="319d7-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="319d7-114">Message Text</span></span>|<span data-ttu-id="319d7-115">Impossibile creare la guida di piano '%.\*ls' perché l'istruzione specificata da `@stmt` e `@module_or_batch` o da `@plan_handle` e `@statement_start_offset` non corrisponde ad alcuna istruzione nel modulo o nel batch specificato.</span><span class="sxs-lookup"><span data-stu-id="319d7-115">Cannot create plan guide '%.\*ls' because the statement specified by `@stmt` and `@module_or_batch`, or by `@plan_handle` and `@statement_start_offset`, does not match any statement in the specified module or batch.</span></span> <span data-ttu-id="319d7-116">Modificare i valori in modo da corrispondere a un'istruzione nel modulo o nel batch.</span><span class="sxs-lookup"><span data-stu-id="319d7-116">Modify the values to match a statement in the module or batch.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="319d7-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="319d7-117">Explanation</span></span>  
 <span data-ttu-id="319d7-118">Un'istruzione nel modulo o nel batch non corrisponde a quella specificata o al valore dell'offset dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="319d7-118">A statement in the specified module or batch could not be matched to the specified statement or statement offset value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="319d7-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="319d7-119">User Action</span></span>  
 <span data-ttu-id="319d7-120">Modificare i valori del parametro specificato in modo da corrispondere a un'istruzione nel modulo o nel batch.</span><span class="sxs-lookup"><span data-stu-id="319d7-120">Modify the specified parameter values to match a statement in the module or batch.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="319d7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="319d7-121">See Also</span></span>  
 <span data-ttu-id="319d7-122">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="319d7-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="319d7-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="319d7-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="319d7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="319d7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
