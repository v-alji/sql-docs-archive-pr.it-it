---
title: MSSQLSERVER_10520 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10520 (Database Engine error)
ms.assetid: cc8799f1-5b90-4248-b209-e1d5087f9529
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b8bdf080703fa6bd02fc34b8c31f59407814b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715391"
---
# <a name="mssqlserver_10520"></a><span data-ttu-id="673e1-102">MSSQLSERVER_10520</span><span class="sxs-lookup"><span data-stu-id="673e1-102">MSSQLSERVER_10520</span></span>
    
## <a name="details"></a><span data-ttu-id="673e1-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="673e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="673e1-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="673e1-104">Product Name</span></span>|<span data-ttu-id="673e1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="673e1-105">SQL Server</span></span>|  
|<span data-ttu-id="673e1-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="673e1-106">Event ID</span></span>|<span data-ttu-id="673e1-107">10520</span><span class="sxs-lookup"><span data-stu-id="673e1-107">10520</span></span>|  
|<span data-ttu-id="673e1-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="673e1-108">Event Source</span></span>|<span data-ttu-id="673e1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="673e1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="673e1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="673e1-110">Component</span></span>|<span data-ttu-id="673e1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="673e1-111">SQLEngine</span></span>|  
|<span data-ttu-id="673e1-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="673e1-112">Symbolic Name</span></span>|<span data-ttu-id="673e1-113">PG_PARAM_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="673e1-113">PG_PARAM_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="673e1-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="673e1-114">Message Text</span></span>|<span data-ttu-id="673e1-115">Impossibile creare la guida di piano '%.\*ls' perché @type è stato specificato come '%ls' ed è stato specificato un valore non NULL per il parametro '%ls'.</span><span class="sxs-lookup"><span data-stu-id="673e1-115">Cannot create plan guide '%.\*ls' because @type was specified as '%ls' and a non-NULL value is specified for the parameter '%ls'.</span></span> <span data-ttu-id="673e1-116">Questo tipo richiede un valore NULL per il parametro.</span><span class="sxs-lookup"><span data-stu-id="673e1-116">This type requires a NULL value for the parameter.</span></span> <span data-ttu-id="673e1-117">Specificare NULL per il parametro oppure impostare un tipo che consenta un valore non NULL per il parametro.</span><span class="sxs-lookup"><span data-stu-id="673e1-117">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="673e1-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="673e1-118">Explanation</span></span>  
 <span data-ttu-id="673e1-119">Il tipo indicato in @type richiede un valore NULL per il parametro specificato, ma è stato fornito un valore non NULL.</span><span class="sxs-lookup"><span data-stu-id="673e1-119">The type specified in @type requires a NULL value for the specified parameter, however a non-NULL value was supplied.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="673e1-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="673e1-120">User Action</span></span>  
 <span data-ttu-id="673e1-121">Specificare NULL per il parametro oppure impostare un tipo che consenta un valore non NULL per il parametro.</span><span class="sxs-lookup"><span data-stu-id="673e1-121">Specify NULL for the parameter, or change the type to one that allows a non-NULL value for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673e1-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="673e1-122">See Also</span></span>  
 <span data-ttu-id="673e1-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="673e1-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="673e1-124">Guide di piano</span><span class="sxs-lookup"><span data-stu-id="673e1-124">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
