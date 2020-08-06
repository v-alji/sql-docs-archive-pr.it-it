---
title: MSSQLSERVER_10539 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10539 (Database Engine error)
ms.assetid: 49c26ff7-18b8-4f07-a087-f45f63463b3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd1f190b8f5d3ab9755409bdd034fa374ea5314
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715363"
---
# <a name="mssqlserver_10539"></a><span data-ttu-id="26eb6-102">MSSQLSERVER_10539</span><span class="sxs-lookup"><span data-stu-id="26eb6-102">MSSQLSERVER_10539</span></span>
    
## <a name="details"></a><span data-ttu-id="26eb6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="26eb6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26eb6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="26eb6-104">Product Name</span></span>|<span data-ttu-id="26eb6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="26eb6-105">SQL Server</span></span>|  
|<span data-ttu-id="26eb6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="26eb6-106">Event ID</span></span>|<span data-ttu-id="26eb6-107">10539</span><span class="sxs-lookup"><span data-stu-id="26eb6-107">10539</span></span>|  
|<span data-ttu-id="26eb6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="26eb6-108">Event Source</span></span>|<span data-ttu-id="26eb6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="26eb6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="26eb6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="26eb6-110">Component</span></span>|<span data-ttu-id="26eb6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="26eb6-111">SQLEngine</span></span>|  
|<span data-ttu-id="26eb6-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="26eb6-112">Symbolic Name</span></span>|<span data-ttu-id="26eb6-113">PG_NO_PLAN_FOR_STMT</span><span class="sxs-lookup"><span data-stu-id="26eb6-113">PG_NO_PLAN_FOR_STMT</span></span>|  
|<span data-ttu-id="26eb6-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="26eb6-114">Message Text</span></span>|<span data-ttu-id="26eb6-115">Impossibile creare la guida di piano '%.\*ls' dalla cache perché non è disponibile un piano di query per l'istruzione con offset iniziale %d.</span><span class="sxs-lookup"><span data-stu-id="26eb6-115">Cannot create plan guide '%.\*ls' from cache because a query plan is not available for the statement with start offset %d.</span></span> <span data-ttu-id="26eb6-116">Questo problema può verificarsi se l'istruzione dipende da oggetti di database non ancora creati.</span><span class="sxs-lookup"><span data-stu-id="26eb6-116">This problem can occur if the statement depends on database objects that have not yet been created.</span></span> <span data-ttu-id="26eb6-117">Verificare che esistano tutti gli oggetti di database necessari ed eseguire l'istruzione prima di creare la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="26eb6-117">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="26eb6-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="26eb6-118">Explanation</span></span>  
 <span data-ttu-id="26eb6-119">Un piano di query non è disponibile nella cache dei piani per l'istruzione con l'offset iniziale specificato.</span><span class="sxs-lookup"><span data-stu-id="26eb6-119">A query plan is not available in the plan cache for the statement with the specified starting offset.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="26eb6-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="26eb6-120">User Action</span></span>  
 <span data-ttu-id="26eb6-121">Verificare che esistano tutti gli oggetti di database necessari ed eseguire l'istruzione prima di creare la guida di piano.</span><span class="sxs-lookup"><span data-stu-id="26eb6-121">Make sure that all necessary database objects exist, and execute the statement before creating the plan guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26eb6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26eb6-122">See Also</span></span>  
 [<span data-ttu-id="26eb6-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="26eb6-123">sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
