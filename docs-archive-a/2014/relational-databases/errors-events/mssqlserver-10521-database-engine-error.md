---
title: MSSQLSERVER_10521 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10521 (Database Engine error)
ms.assetid: ba2d7e44-207c-4428-b5f0-c975ac122c0d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c034bd13e212b9b39bfd348353d59e23fc748079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715387"
---
# <a name="mssqlserver_10521"></a><span data-ttu-id="2b61d-102">MSSQLSERVER_10521</span><span class="sxs-lookup"><span data-stu-id="2b61d-102">MSSQLSERVER_10521</span></span>
    
## <a name="details"></a><span data-ttu-id="2b61d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2b61d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b61d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="2b61d-104">Product Name</span></span>|<span data-ttu-id="2b61d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b61d-105">SQL Server</span></span>|  
|<span data-ttu-id="2b61d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="2b61d-106">Event ID</span></span>|<span data-ttu-id="2b61d-107">10521</span><span class="sxs-lookup"><span data-stu-id="2b61d-107">10521</span></span>|  
|<span data-ttu-id="2b61d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="2b61d-108">Event Source</span></span>|<span data-ttu-id="2b61d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2b61d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2b61d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2b61d-110">Component</span></span>|<span data-ttu-id="2b61d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2b61d-111">SQLEngine</span></span>|  
|<span data-ttu-id="2b61d-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="2b61d-112">Symbolic Name</span></span>|<span data-ttu-id="2b61d-113">PG_PARAM_NEEDED</span><span class="sxs-lookup"><span data-stu-id="2b61d-113">PG_PARAM_NEEDED</span></span>|  
|<span data-ttu-id="2b61d-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2b61d-114">Message Text</span></span>|<span data-ttu-id="2b61d-115">Impossibile creare la guida di piano '%.\*ls' perché `@type` è stato specificato come '%ls' e il parametro '%ls' è NULL.</span><span class="sxs-lookup"><span data-stu-id="2b61d-115">Cannot create plan guide '%.\*ls' because `@type` was specified as '%ls' and the parameter '%ls' is NULL.</span></span> <span data-ttu-id="2b61d-116">Questo tipo richiede un valore non NULL per il parametro.</span><span class="sxs-lookup"><span data-stu-id="2b61d-116">This type requires a non-NULL value for the parameter.</span></span> <span data-ttu-id="2b61d-117">Specificare un valore non NULL per il parametro oppure impostare un tipo che consenta un valore NULL per il parametro.</span><span class="sxs-lookup"><span data-stu-id="2b61d-117">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2b61d-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="2b61d-118">Explanation</span></span>  
 <span data-ttu-id="2b61d-119">Il tipo indicato in `@type` richiede un valore non Null per il parametro specificato, ma è stato fornito un valore Null.</span><span class="sxs-lookup"><span data-stu-id="2b61d-119">The type specified in `@type` requires a non-NULL value for the specified parameter; however a NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2b61d-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2b61d-120">User Action</span></span>  
 <span data-ttu-id="2b61d-121">Specificare un valore non NULL per il parametro oppure impostare un tipo che consenta un valore NULL per il parametro.</span><span class="sxs-lookup"><span data-stu-id="2b61d-121">Specify a non-NULL value for the parameter, or change the type to one that allows a NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b61d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b61d-122">See Also</span></span>  
 <span data-ttu-id="2b61d-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b61d-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="2b61d-124">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="2b61d-124">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="2b61d-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b61d-125">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
