---
title: MSSQLSERVER_10538 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10538 (Database Engine error)
ms.assetid: 284d19b4-4979-4cbe-a9be-ac1104433c69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: edc6abf192a3341f9b84c99e99071343cc882c3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715368"
---
# <a name="mssqlserver_10538"></a><span data-ttu-id="cdcb7-102">MSSQLSERVER_10538</span><span class="sxs-lookup"><span data-stu-id="cdcb7-102">MSSQLSERVER_10538</span></span>
    
## <a name="details"></a><span data-ttu-id="cdcb7-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cdcb7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cdcb7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="cdcb7-104">Product Name</span></span>|<span data-ttu-id="cdcb7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cdcb7-105">SQL Server</span></span>|  
|<span data-ttu-id="cdcb7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="cdcb7-106">Event ID</span></span>|<span data-ttu-id="cdcb7-107">10538</span><span class="sxs-lookup"><span data-stu-id="cdcb7-107">10538</span></span>|  
|<span data-ttu-id="cdcb7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="cdcb7-108">Event Source</span></span>|<span data-ttu-id="cdcb7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cdcb7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cdcb7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="cdcb7-110">Component</span></span>|<span data-ttu-id="cdcb7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cdcb7-111">SQLEngine</span></span>|  
|<span data-ttu-id="cdcb7-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="cdcb7-112">Symbolic Name</span></span>|<span data-ttu-id="cdcb7-113">PG_INVALID_PLANGUIDE_HANDLE</span><span class="sxs-lookup"><span data-stu-id="cdcb7-113">PG_INVALID_PLANGUIDE_HANDLE</span></span>|  
|<span data-ttu-id="cdcb7-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="cdcb7-114">Message Text</span></span>|<span data-ttu-id="cdcb7-115">Impossibile trovare la guida di piano. L'ID della guida di piano specificato è NULL o non valido oppure l'utente non dispone dell'autorizzazione per l'oggetto a cui fa riferimento la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-115">Cannot find the plan guide either because the specified plan guide ID is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span> <span data-ttu-id="cdcb7-116">Verificare che l'ID della guida di piano sia valido, che la sessione corrente sia impostata sul contesto di database corretto e di disporre dell'autorizzazione ALTER per l'oggetto a cui fa riferimento la guida di piano o dell'autorizzazione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-116">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have either ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cdcb7-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="cdcb7-117">Explanation</span></span>  
 <span data-ttu-id="cdcb7-118">L'ID della guida di piano specificato è NULL o non valido oppure l'utente non dispone dell'autorizzazione per l'oggetto a cui fa riferimento la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-118">The ID of the specified plan guide is NULL or invalid, or you do not have permission on the object referenced by the plan guide.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cdcb7-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="cdcb7-119">User Action</span></span>  
 <span data-ttu-id="cdcb7-120">Verificare che l'ID della guida di piano sia valido, che la sessione corrente sia impostata sul contesto di database corretto e di disporre dell'autorizzazione ALTER per l'oggetto a cui fa riferimento la guida di piano o dell'autorizzazione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cdcb7-120">Verify that the plan guide ID is valid, the current session is set to the correct database context, and you have ALTER DATABASE permission or ALTER permission on the object referenced by the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdcb7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdcb7-121">See Also</span></span>  
 <span data-ttu-id="cdcb7-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cdcb7-122">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 <span data-ttu-id="cdcb7-123">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="cdcb7-123">[Plan Guides](../performance/plan-guides.md) </span></span>  
 [<span data-ttu-id="cdcb7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cdcb7-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
