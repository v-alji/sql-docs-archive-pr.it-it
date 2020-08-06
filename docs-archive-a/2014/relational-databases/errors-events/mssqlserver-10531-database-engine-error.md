---
title: MSSQLSERVER_10531 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10531 (Database Engine error)
ms.assetid: bb40e994-231c-44ce-933f-8d767fb2f450
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6230c046a9eb7b900377888c59a3a492f2b89f73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715384"
---
# <a name="mssqlserver_10531"></a><span data-ttu-id="0c4cd-102">MSSQLSERVER_10531</span><span class="sxs-lookup"><span data-stu-id="0c4cd-102">MSSQLSERVER_10531</span></span>
    
## <a name="details"></a><span data-ttu-id="0c4cd-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0c4cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c4cd-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0c4cd-104">Product Name</span></span>|<span data-ttu-id="0c4cd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0c4cd-105">SQL Server</span></span>|  
|<span data-ttu-id="0c4cd-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0c4cd-106">Event ID</span></span>|<span data-ttu-id="0c4cd-107">10531</span><span class="sxs-lookup"><span data-stu-id="0c4cd-107">10531</span></span>|  
|<span data-ttu-id="0c4cd-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0c4cd-108">Event Source</span></span>|<span data-ttu-id="0c4cd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0c4cd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0c4cd-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0c4cd-110">Component</span></span>|<span data-ttu-id="0c4cd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0c4cd-111">SQLEngine</span></span>|  
|<span data-ttu-id="0c4cd-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0c4cd-112">Symbolic Name</span></span>|<span data-ttu-id="0c4cd-113">PG_NO_ELIGIBLE_STMT</span><span class="sxs-lookup"><span data-stu-id="0c4cd-113">PG_NO_ELIGIBLE_STMT</span></span>|  
|<span data-ttu-id="0c4cd-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0c4cd-114">Message Text</span></span>|<span data-ttu-id="0c4cd-115">Impossibile creare la guida di piano '%.\*ls' dalla cache perché l'utente non dispone delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="0c4cd-115">Cannot create plan guide '%.\*ls' from cache because the user does not have adequate permissions.</span></span> <span data-ttu-id="0c4cd-116">Per creare la guida di piano, concedere all'utente l'autorizzazione VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="0c4cd-116">Grant the VIEW SERVER STATE permission to the user creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0c4cd-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0c4cd-117">Explanation</span></span>  
 <span data-ttu-id="0c4cd-118">L'utente non dispone delle autorizzazioni necessarie per creare la guida di piano dalla cache dei piani.</span><span class="sxs-lookup"><span data-stu-id="0c4cd-118">The user does not have adequate permissions to create the specified plan guide from the plan cache.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c4cd-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0c4cd-119">User Action</span></span>  
 <span data-ttu-id="0c4cd-120">Concedere l'autorizzazione VIEW SERVER STATE all'utente che crea la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="0c4cd-120">Grant VIEW SERVER STATE permission to the user creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4cd-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c4cd-121">See Also</span></span>  
 <span data-ttu-id="0c4cd-122">[Guide di piano](../performance/plan-guides.md) </span><span class="sxs-lookup"><span data-stu-id="0c4cd-122">[Plan Guides](../performance/plan-guides.md) </span></span>  
 <span data-ttu-id="0c4cd-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c4cd-123">[sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) </span></span>  
 [<span data-ttu-id="0c4cd-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0c4cd-124">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
