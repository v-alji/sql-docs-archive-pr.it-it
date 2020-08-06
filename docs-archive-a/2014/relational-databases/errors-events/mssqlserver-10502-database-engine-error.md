---
title: MSSQLSERVER_10502 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10502 (Database Engine error)
ms.assetid: 26d9b64d-4299-4b55-92d0-0a32a3688c0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eeec3a3adf318cadc96501938f8a5565f1c07670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624248"
---
# <a name="mssqlserver_10502"></a><span data-ttu-id="f5f82-102">MSSQLSERVER_10502</span><span class="sxs-lookup"><span data-stu-id="f5f82-102">MSSQLSERVER_10502</span></span>
    
## <a name="details"></a><span data-ttu-id="f5f82-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f5f82-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5f82-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f5f82-104">Product Name</span></span>|<span data-ttu-id="f5f82-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5f82-105">SQL Server</span></span>|  
|<span data-ttu-id="f5f82-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f5f82-106">Event ID</span></span>|<span data-ttu-id="f5f82-107">10502</span><span class="sxs-lookup"><span data-stu-id="f5f82-107">10502</span></span>|  
|<span data-ttu-id="f5f82-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f5f82-108">Event Source</span></span>|<span data-ttu-id="f5f82-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f5f82-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f5f82-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f5f82-110">Component</span></span>|<span data-ttu-id="f5f82-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f5f82-111">SQLEngine</span></span>|  
|<span data-ttu-id="f5f82-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f5f82-112">Symbolic Name</span></span>|<span data-ttu-id="f5f82-113">PG_DUP_FOUND</span><span class="sxs-lookup"><span data-stu-id="f5f82-113">PG_DUP_FOUND</span></span>|  
|<span data-ttu-id="f5f82-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f5f82-114">Message Text</span></span>|<span data-ttu-id="f5f82-115">Impossibile creare la guida di piano '%.\*ls' perché l'istruzione specificata da @stmt e @module_or_batch o da @plan_handle e @statement_start_offset corrisponde alla guida di piano '%.\*ls' esistente nel database.</span><span class="sxs-lookup"><span data-stu-id="f5f82-115">Cannot create plan guide '%.\*ls' because the statement specified by @stmt and @module_or_batch, or by @plan_handle and @statement_start_offset, matches the existing plan guide '%.\*ls' in the database.</span></span> <span data-ttu-id="f5f82-116">Eliminare la guida di piano esistente prima di creare quella nuova.</span><span class="sxs-lookup"><span data-stu-id="f5f82-116">Drop the existing plan guide before creating the new plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f5f82-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f5f82-117">Explanation</span></span>  
 <span data-ttu-id="f5f82-118">Per l'istruzione specificata esiste già una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="f5f82-118">A plan guide exists for the specified statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5f82-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f5f82-119">User Action</span></span>  
 <span data-ttu-id="f5f82-120">Eliminare la guida di piano esistente prima di creare quella nuova.</span><span class="sxs-lookup"><span data-stu-id="f5f82-120">Drop the existing plan guide before creating the new plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f82-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5f82-121">See Also</span></span>  
 <span data-ttu-id="f5f82-122">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="f5f82-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="f5f82-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5f82-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="f5f82-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f5f82-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
