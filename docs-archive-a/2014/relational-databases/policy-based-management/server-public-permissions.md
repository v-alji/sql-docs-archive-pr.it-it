---
title: Autorizzazioni server per il ruolo public | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 9a276caa-ea38-473d-92bc-26302bfcf660
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7913c4715f47b8105b72b1c817dbe77e52d40539
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724536"
---
# <a name="server-public-permissions"></a><span data-ttu-id="e8012-102">Autorizzazioni server per il ruolo public</span><span class="sxs-lookup"><span data-stu-id="e8012-102">Server public Permissions</span></span>
  <span data-ttu-id="e8012-103">Questa regola consente di determinare se il ruolo del server public dispone di autorizzazioni server.</span><span class="sxs-lookup"><span data-stu-id="e8012-103">This rule determines whether the public server role has server permissions.</span></span> <span data-ttu-id="e8012-104">Ogni account di accesso creato nel server è un membro del ruolo del server public.</span><span class="sxs-lookup"><span data-stu-id="e8012-104">Every login that is created on the server is a member of the public server role.</span></span> <span data-ttu-id="e8012-105">Se questa condizione viene soddisfatta, ogni account di accesso nel server disporrà di autorizzazioni server.</span><span class="sxs-lookup"><span data-stu-id="e8012-105">If this condition is met, every login on the server will have server permissions.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e8012-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="e8012-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e8012-107">Non concedere autorizzazioni server al ruolo del server public.</span><span class="sxs-lookup"><span data-stu-id="e8012-107">Do not grant server permissions to the server public role.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8012-108">Al termine dell'installazione, il ruolo **public** dispone dell' `CONNECT` autorizzazione per tutti gli endpoint ad eccezione della **connessione amministrativa dedicata**.</span><span class="sxs-lookup"><span data-stu-id="e8012-108">After setup completes the **PUBLIC** role has `CONNECT` permission on all the endpoints except the **Dedicated Admin Connection**.</span></span> <span data-ttu-id="e8012-109">Questa situazione è normale e, generalmente, non deve essere modificata</span><span class="sxs-lookup"><span data-stu-id="e8012-109">This is normal and should not be normally changed.</span></span> <span data-ttu-id="e8012-110">(l'accesso viene controllato tramite l'autorizzazione `CONNECT SQL` che viene concessa automaticamente in caso di creazione di nuovi account di accesso).</span><span class="sxs-lookup"><span data-stu-id="e8012-110">(Access is controlled by using the `CONNECT SQL` permission which is automatically granted when new logins are created.)</span></span>  
  
### <a name="for-more-information"></a><span data-ttu-id="e8012-111">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e8012-111">For more information</span></span>  
 [<span data-ttu-id="e8012-112">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8012-112">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
  
