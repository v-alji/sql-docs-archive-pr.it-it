---
title: MSSQLSERVER_10533 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10533 (Database Engine error)
ms.assetid: cc2fbdab-7b90-415f-a1f9-066824344283
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccef25bc8f594cb6ea0b60aefab838ef27cda6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628763"
---
# <a name="mssqlserver_10533"></a><span data-ttu-id="cf814-102">MSSQLSERVER_10533</span><span class="sxs-lookup"><span data-stu-id="cf814-102">MSSQLSERVER_10533</span></span>
    
## <a name="details"></a><span data-ttu-id="cf814-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cf814-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf814-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="cf814-104">Product Name</span></span>|<span data-ttu-id="cf814-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cf814-105">SQL Server</span></span>|  
|<span data-ttu-id="cf814-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="cf814-106">Event ID</span></span>|<span data-ttu-id="cf814-107">10533</span><span class="sxs-lookup"><span data-stu-id="cf814-107">10533</span></span>|  
|<span data-ttu-id="cf814-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="cf814-108">Event Source</span></span>|<span data-ttu-id="cf814-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cf814-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cf814-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cf814-110">Component</span></span>|<span data-ttu-id="cf814-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cf814-111">SQLEngine</span></span>|  
|<span data-ttu-id="cf814-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="cf814-112">Symbolic Name</span></span>|<span data-ttu-id="cf814-113">PG_NAME_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="cf814-113">PG_NAME_TOO_BIG</span></span>|  
|<span data-ttu-id="cf814-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="cf814-114">Message Text</span></span>|<span data-ttu-id="cf814-115">Impossibile creare la guida di piano '%.\*ls' perché il nome della guida di piano supera la lunghezza massima consentita di 124 caratteri.</span><span class="sxs-lookup"><span data-stu-id="cf814-115">Cannot create plan guide '%.\*ls' because the plan guide name exceeds 124 characters, the maximum number allowed.</span></span> <span data-ttu-id="cf814-116">Specificare un nome che contiene meno di 125 caratteri.</span><span class="sxs-lookup"><span data-stu-id="cf814-116">Specify a name that contains fewer than 125 characters.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cf814-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="cf814-117">Explanation</span></span>  
 <span data-ttu-id="cf814-118">Il nome della guida di piano supera la lunghezza massima consentita di 124 caratteri.</span><span class="sxs-lookup"><span data-stu-id="cf814-118">The plan guide name exceeds 124 characters, the maximum number allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cf814-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="cf814-119">User Action</span></span>  
 <span data-ttu-id="cf814-120">Specificare un nome che contiene meno di 125 caratteri.</span><span class="sxs-lookup"><span data-stu-id="cf814-120">Specify a name that contains fewer than 125 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf814-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf814-121">See Also</span></span>  
 <span data-ttu-id="cf814-122">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="cf814-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="cf814-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cf814-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="cf814-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cf814-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
