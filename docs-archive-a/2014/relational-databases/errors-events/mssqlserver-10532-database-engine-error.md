---
title: MSSQLSERVER_10532 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10532 (Database Engine error)
ms.assetid: 01da29ee-bf67-433f-8148-587a7e8d1d76
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26ab34c319eff62737eae337828247fdfd7e901b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723903"
---
# <a name="mssqlserver_10532"></a><span data-ttu-id="fec38-102">MSSQLSERVER_10532</span><span class="sxs-lookup"><span data-stu-id="fec38-102">MSSQLSERVER_10532</span></span>
    
## <a name="details"></a><span data-ttu-id="fec38-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fec38-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fec38-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="fec38-104">Product Name</span></span>|<span data-ttu-id="fec38-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fec38-105">SQL Server</span></span>|  
|<span data-ttu-id="fec38-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="fec38-106">Event ID</span></span>|<span data-ttu-id="fec38-107">10532</span><span class="sxs-lookup"><span data-stu-id="fec38-107">10532</span></span>|  
|<span data-ttu-id="fec38-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="fec38-108">Event Source</span></span>|<span data-ttu-id="fec38-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fec38-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fec38-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fec38-110">Component</span></span>|<span data-ttu-id="fec38-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fec38-111">SQLEngine</span></span>|  
|<span data-ttu-id="fec38-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="fec38-112">Symbolic Name</span></span>|<span data-ttu-id="fec38-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="fec38-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="fec38-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="fec38-114">Message Text</span></span>|<span data-ttu-id="fec38-115">Impossibile creare la guida di piano '%.\*ls' perché il batch o il modulo specificato da `@plan_handle` non contiene un'istruzione idonea per una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="fec38-115">Cannot create plan guide '%.\*ls' because the batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span> <span data-ttu-id="fec38-116">Specificare un valore diverso per `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="fec38-116">Specify a different value for `@plan_handle`.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fec38-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="fec38-117">Explanation</span></span>  
 <span data-ttu-id="fec38-118">Il batch o il modulo specificato da `@plan_handle` non contiene un'istruzione idonea per una guida di piano.</span><span class="sxs-lookup"><span data-stu-id="fec38-118">The batch or module specified by `@plan_handle` does not contain a statement that is eligible for a plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fec38-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="fec38-119">User Action</span></span>  
 <span data-ttu-id="fec38-120">Specificare un valore diverso per `@plan_handle`.</span><span class="sxs-lookup"><span data-stu-id="fec38-120">Specify a different value for `@plan_handle`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec38-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fec38-121">See Also</span></span>  
 <span data-ttu-id="fec38-122">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="fec38-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="fec38-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fec38-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="fec38-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fec38-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
