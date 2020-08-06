---
title: MSSQLSERVER_10534 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10534 (Database Engine error)
ms.assetid: e65bb118-99d5-4fdb-b1d5-0ec70f0a677b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 793bb0bf5048e30624d9566f65e7c6752bd14386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715380"
---
# <a name="mssqlserver_10534"></a><span data-ttu-id="7323e-102">MSSQLSERVER_10534</span><span class="sxs-lookup"><span data-stu-id="7323e-102">MSSQLSERVER_10534</span></span>
    
## <a name="details"></a><span data-ttu-id="7323e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7323e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7323e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="7323e-104">Product Name</span></span>|<span data-ttu-id="7323e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7323e-105">SQL Server</span></span>|  
|<span data-ttu-id="7323e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="7323e-106">Event ID</span></span>|<span data-ttu-id="7323e-107">10534</span><span class="sxs-lookup"><span data-stu-id="7323e-107">10534</span></span>|  
|<span data-ttu-id="7323e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="7323e-108">Event Source</span></span>|<span data-ttu-id="7323e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7323e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7323e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7323e-110">Component</span></span>|<span data-ttu-id="7323e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7323e-111">SQLEngine</span></span>|  
|<span data-ttu-id="7323e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="7323e-112">Symbolic Name</span></span>|<span data-ttu-id="7323e-113">PG_INVALID_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7323e-113">PG_INVALID_PARAMS</span></span>|  
|<span data-ttu-id="7323e-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7323e-114">Message Text</span></span>|<span data-ttu-id="7323e-115">Impossibile creare la guida di piano '%.\*ls' perché il valore specificato per `@params` non è valido.</span><span class="sxs-lookup"><span data-stu-id="7323e-115">Cannot create plan guide '%.\*ls' because the value specified for `@params` is invalid.</span></span> <span data-ttu-id="7323e-116">Specificare il valore nel formato *nome_parametro tipo_parametro* o specificare NULL.</span><span class="sxs-lookup"><span data-stu-id="7323e-116">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7323e-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7323e-117">Explanation</span></span>  
 <span data-ttu-id="7323e-118">Il valore specificato per `@params` non è valido.</span><span class="sxs-lookup"><span data-stu-id="7323e-118">The value specified for `@params` is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7323e-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7323e-119">User Action</span></span>  
 <span data-ttu-id="7323e-120">Specificare il valore nel formato *nome_parametro tipo_parametro* o specificare NULL.</span><span class="sxs-lookup"><span data-stu-id="7323e-120">Specify the value in the form *parameter_name parameter_type*, or specify NULL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7323e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7323e-121">See Also</span></span>  
 <span data-ttu-id="7323e-122">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="7323e-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="7323e-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7323e-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="7323e-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7323e-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
