---
title: Bit relativo alla proprietà trustworthy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3198188a-2b59-4865-9560-10f760934b8e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 062a63dd52f4641a0ddfcbc20cb9bad3cce6dc61
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626703"
---
# <a name="trustworthy-bit"></a><span data-ttu-id="9331b-102">Bit relativo alla proprietà trustworthy</span><span class="sxs-lookup"><span data-stu-id="9331b-102">Trustworthy Bit</span></span>
  <span data-ttu-id="9331b-103">Questa regola consente di determinare se il ruolo dbo per un database è assegnato al ruolo predefinito del server sysadmin e se per il database il bit relativo alla proprietà trustworthy è impostato su ON.</span><span class="sxs-lookup"><span data-stu-id="9331b-103">This rule determines whether the dbo role for a database is assigned to the sysadmin fixed server role and the database has its trustworthy bit set to ON.</span></span>  
  
 <span data-ttu-id="9331b-104">Se queste condizioni vengono soddisfatte, un utente di database con privilegi potrà elevare il livello di privilegi al ruolo sysadmin.</span><span class="sxs-lookup"><span data-stu-id="9331b-104">If these conditions are met, a privileged database user can elevate privileges to the sysadmin role.</span></span> <span data-ttu-id="9331b-105">In questo ruolo l'utente può creare ed eseguire assembly non protetti che potrebbero danneggiare il sistema.</span><span class="sxs-lookup"><span data-stu-id="9331b-105">In this role, the user can create and run unsafe assemblies that compromise the system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="9331b-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="9331b-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="9331b-107">Disattivare il bit relativo alla proprietà trustworthy o revocare le autorizzazioni sysadmin al ruolo del database dbo.</span><span class="sxs-lookup"><span data-stu-id="9331b-107">Turn off the trustworthy bit or revoke sysadmin permissions from the dbo database role.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="9331b-108">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9331b-108">For More Information</span></span>  
 [<span data-ttu-id="9331b-109">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9331b-109">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="9331b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9331b-110">See Also</span></span>  
 [<span data-ttu-id="9331b-111">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="9331b-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
