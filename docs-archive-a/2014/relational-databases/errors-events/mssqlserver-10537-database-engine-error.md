---
title: MSSQLSERVER_10537 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10537 (Database Engine error)
ms.assetid: 728469a4-6523-4a37-925f-a950d75420fa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b1baccad5236bd8c1a71024b7dd542cc9d11cbd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718228"
---
# <a name="mssqlserver_10537"></a><span data-ttu-id="b94b7-102">MSSQLSERVER_10537</span><span class="sxs-lookup"><span data-stu-id="b94b7-102">MSSQLSERVER_10537</span></span>
    
## <a name="details"></a><span data-ttu-id="b94b7-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b94b7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b94b7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b94b7-104">Product Name</span></span>|<span data-ttu-id="b94b7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b94b7-105">SQL Server</span></span>|  
|<span data-ttu-id="b94b7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b94b7-106">Event ID</span></span>|<span data-ttu-id="b94b7-107">10537</span><span class="sxs-lookup"><span data-stu-id="b94b7-107">10537</span></span>|  
|<span data-ttu-id="b94b7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b94b7-108">Event Source</span></span>|<span data-ttu-id="b94b7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b94b7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b94b7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b94b7-110">Component</span></span>|<span data-ttu-id="b94b7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b94b7-111">SQLEngine</span></span>|  
|<span data-ttu-id="b94b7-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b94b7-112">Symbolic Name</span></span>|<span data-ttu-id="b94b7-113">PG_DUP_ENABLED</span><span class="sxs-lookup"><span data-stu-id="b94b7-113">PG_DUP_ENABLED</span></span>|  
|<span data-ttu-id="b94b7-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b94b7-114">Message Text</span></span>|<span data-ttu-id="b94b7-115">Impossibile abilitare la guida di pano '%.\*ls' perché la guida di piano '%.\*ls' abilitata contiene lo stesso ambito e lo stesso valore di offset iniziale dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b94b7-115">Cannot enable plan guide '%.\*ls' because the enabled plan guide '%.\*ls' contains the same scope and starting offset value as the statement.</span></span> <span data-ttu-id="b94b7-116">Disabilitare la guida di piano esistente prima di abilitare la guida di piano specificata.</span><span class="sxs-lookup"><span data-stu-id="b94b7-116">Disable the existing plan guide before enabling the specified plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b94b7-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b94b7-117">Explanation</span></span>  
 <span data-ttu-id="b94b7-118">Una guida di piano esistente abilitata contiene lo stesso ambito e lo stesso valore di offset iniziale dell'istruzione presente nella guida di piano specificata.</span><span class="sxs-lookup"><span data-stu-id="b94b7-118">An existing plan guide contains the same scope and starting offset value as the statement in the specified plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b94b7-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b94b7-119">User Action</span></span>  
 <span data-ttu-id="b94b7-120">Disabilitare la guida di piano esistente prima di abilitare la guida di piano specificata.</span><span class="sxs-lookup"><span data-stu-id="b94b7-120">Disable the existing plan guide before enabling the specified plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b94b7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b94b7-121">See Also</span></span>  
 <span data-ttu-id="b94b7-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b94b7-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="b94b7-123">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="b94b7-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="b94b7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b94b7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
