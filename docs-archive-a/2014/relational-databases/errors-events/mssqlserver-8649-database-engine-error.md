---
title: MSSQLSERVER_8649 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8649 (Database Engine error)
ms.assetid: 992dbc74-7c3a-498b-9f1b-b28387640677
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b39ed0d8ffe5f7f601b6cb1393596d0d6546e557
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635064"
---
# <a name="mssqlserver_8649"></a><span data-ttu-id="9f8a2-102">MSSQLSERVER_8649</span><span class="sxs-lookup"><span data-stu-id="9f8a2-102">MSSQLSERVER_8649</span></span>
    
## <a name="details"></a><span data-ttu-id="9f8a2-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9f8a2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f8a2-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="9f8a2-104">Product Name</span></span>|<span data-ttu-id="9f8a2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f8a2-105">SQL Server</span></span>|  
|<span data-ttu-id="9f8a2-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="9f8a2-106">Event ID</span></span>|<span data-ttu-id="9f8a2-107">8649</span><span class="sxs-lookup"><span data-stu-id="9f8a2-107">8649</span></span>|  
|<span data-ttu-id="9f8a2-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="9f8a2-108">Event Source</span></span>|<span data-ttu-id="9f8a2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9f8a2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9f8a2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9f8a2-110">Component</span></span>|<span data-ttu-id="9f8a2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9f8a2-111">SQLEngine</span></span>|  
|<span data-ttu-id="9f8a2-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="9f8a2-112">Symbolic Name</span></span>|<span data-ttu-id="9f8a2-113">COST_TOO_HIGH</span><span class="sxs-lookup"><span data-stu-id="9f8a2-113">COST_TOO_HIGH</span></span>|  
|<span data-ttu-id="9f8a2-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="9f8a2-114">Message Text</span></span>|<span data-ttu-id="9f8a2-115">La query è stata annullata perché il suo costo stimato (%d) è maggiore della soglia configurata, pari a %d.</span><span class="sxs-lookup"><span data-stu-id="9f8a2-115">The query has been canceled because the estimated cost of this query (%d) exceeds the configured threshold of %d.</span></span> <span data-ttu-id="9f8a2-116">Contattare l'amministratore del sistema.</span><span class="sxs-lookup"><span data-stu-id="9f8a2-116">Contact the system administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f8a2-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9f8a2-117">Explanation</span></span>  
 <span data-ttu-id="9f8a2-118">La query è stata annullata perché il suo costo stimato supera la soglia configurata impostata per QUERY_GOVERNOR_COST_LIMIT.</span><span class="sxs-lookup"><span data-stu-id="9f8a2-118">The query was canceled because the estimated cost of this query exceeds the configured threshold set for the QUERY_GOVERNOR_COST_LIMIT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f8a2-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="9f8a2-119">User Action</span></span>  
 <span data-ttu-id="9f8a2-120">Impostare l'opzione QUERY_GOVERNOR_COST_LIMIT su un valore più elevato.</span><span class="sxs-lookup"><span data-stu-id="9f8a2-120">Set the QUERY_GOVERNOR_COST_LIMIT option to a higher value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8a2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f8a2-121">See Also</span></span>  
 [<span data-ttu-id="9f8a2-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9f8a2-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql)  
  
  
