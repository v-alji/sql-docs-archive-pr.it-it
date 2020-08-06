---
title: Autorizzazioni Guest nei database utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 540f1c6d-df51-497e-958a-3a0f429d2920
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 344c5fd0639876998f1585c32fac5f7599f664e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624690"
---
# <a name="guest-permissions-on-user-databases"></a><span data-ttu-id="5f85f-102">Autorizzazioni Guest nei database utente</span><span class="sxs-lookup"><span data-stu-id="5f85f-102">Guest Permissions on User Databases</span></span>
  <span data-ttu-id="5f85f-103">Questa regola consente di determinare se l'utente guest dispone dell'autorizzazione necessaria per accedere al database.</span><span class="sxs-lookup"><span data-stu-id="5f85f-103">This rule determines whether the guest user has permission to access the database.</span></span> <span data-ttu-id="5f85f-104">Questa regola si applica solo ai database utente.</span><span class="sxs-lookup"><span data-stu-id="5f85f-104">This rule applies to user databases only.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="5f85f-105">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="5f85f-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="5f85f-106">Se non è necessaria, revocare l'autorizzazione di accesso al database dell'utente guest.</span><span class="sxs-lookup"><span data-stu-id="5f85f-106">Revoke the guest user permission to access the database if it is not required.</span></span>  
  
 <span data-ttu-id="5f85f-107">L'utente guest non può essere rimosso. È tuttavia possibile disabilitarlo revocandone l'autorizzazione CONNECT tramite l'esecuzione di REVOKE CONNECT FROM GUEST all'interno di un database diverso da master, tempdb o msdb.</span><span class="sxs-lookup"><span data-stu-id="5f85f-107">The guest user cannot be dropped, but guest user can be disabled by revoking its CONNECT permission by executing REVOKE CONNECT FROM GUEST within any database other than master, tempdb, or msdb.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="5f85f-108">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="5f85f-108">For More Information</span></span>  
 [<span data-ttu-id="5f85f-109">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="5f85f-109">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f85f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f85f-110">See Also</span></span>  
 [<span data-ttu-id="5f85f-111">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="5f85f-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
