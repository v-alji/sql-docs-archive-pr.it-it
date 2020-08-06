---
title: Impostare l'opzione di database AUTO_CLOSE su OFF | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: e6b03364-263a-4ec4-9794-de9869d396ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: db6cf5a3f82c3493a8732958594743104fccc968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724527"
---
# <a name="set-the-auto_close-database-option-to-off"></a><span data-ttu-id="b428a-102">Impostazione dell'opzione di database AUTO_CLOSE su OFF</span><span class="sxs-lookup"><span data-stu-id="b428a-102">Set the AUTO_CLOSE Database Option to OFF</span></span>
  <span data-ttu-id="b428a-103">Questa regola consente di controllare se l'opzione di database AUTO_ CLOSE è impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="b428a-103">This rule checks whether the AUTO_ CLOSE option is set OFF.</span></span> <span data-ttu-id="b428a-104">Se impostata su ON, l'opzione AUTO_CLOSE può provocare una riduzione delle prestazione nei database cui si accede di frequente a causa dell'aumento di overhead dovuto all'apertura e alla chiusura del database dopo ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="b428a-104">When AUTO_CLOSE is set ON, this option can cause performance degradation on frequently accessed databases because of the increased overhead of opening and closing the database after each connection.</span></span> <span data-ttu-id="b428a-105">L'opzione AUTO_CLOSE comporta anche lo scaricamento della cache delle procedure dopo ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="b428a-105">AUTO_CLOSE also flushes the procedure cache after each connection.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b428a-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="b428a-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b428a-107">Impostare l'opzione AUTO_CLOSE su OFF per i database cui si accede di frequente.</span><span class="sxs-lookup"><span data-stu-id="b428a-107">If a database is accessed frequently, set the AUTO_CLOSE option to OFF for the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b428a-108">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="b428a-108">For More Information</span></span>  
 [<span data-ttu-id="b428a-109">Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b428a-109">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="b428a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b428a-110">See Also</span></span>  
 [<span data-ttu-id="b428a-111">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="b428a-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
