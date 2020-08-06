---
title: Impostare l'opzione di database AUTO_SHRINK su OFF | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 16403850-d745-4754-b84f-5f01aaecd24e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 42d79ed13a691c3d39a28e7ab35a740a9f613fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724524"
---
# <a name="set-the-auto_shrink-database-option-to-off"></a><span data-ttu-id="7d996-102">Impostazione dell'opzione di database AUTO_SHRINK su OFF</span><span class="sxs-lookup"><span data-stu-id="7d996-102">Set the AUTO_SHRINK Database Option to OFF</span></span>
  <span data-ttu-id="7d996-103">Questa regola consente di controllare se l'opzione di database AUTO_SHRINK è impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="7d996-103">This rule checks whether the AUTO_SHRINK database option is set to OFF.</span></span> <span data-ttu-id="7d996-104">La compattazione e l'espansione di un database comportano spesso la frammentazione fisica.</span><span class="sxs-lookup"><span data-stu-id="7d996-104">Frequently shrinking and expanding a database can lead to physical fragmentation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="7d996-105">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="7d996-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="7d996-106">Impostare l'opzione di database AUTO_SHRINK su OFF.</span><span class="sxs-lookup"><span data-stu-id="7d996-106">Set the AUTO_SHRINK database option to OFF.</span></span> <span data-ttu-id="7d996-107">Se si prevede che lo spazio recuperato non sarà necessario in futuro, è possibile liberare spazio compattando manualmente il database.</span><span class="sxs-lookup"><span data-stu-id="7d996-107">If you know that the space that you are reclaiming will not be needed in the future, you can reclaim the space by manually shrinking the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="7d996-108">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="7d996-108">For More Information</span></span>  
 <span data-ttu-id="7d996-109">Articolo [315512](https://go.microsoft.com/fwlink/?linkid=117750)della Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="7d996-109">Microsoft Knowledge Base article [315512](https://go.microsoft.com/fwlink/?linkid=117750)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d996-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d996-110">See Also</span></span>  
 [<span data-ttu-id="7d996-111">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="7d996-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
