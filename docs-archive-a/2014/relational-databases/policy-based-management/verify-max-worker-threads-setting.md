---
title: Verificare l'impostazione relativa al numero massimo di thread di lavoro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 2d94adfd-3ba1-493a-b29a-b436f9d583df
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dbffb87f58d2beb633f43ff18680222ea62cf5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626690"
---
# <a name="verify-max-worker-threads-setting"></a><span data-ttu-id="ff19b-102">Verifica dell'impostazione relativa al numero massimo di thread di lavoro</span><span class="sxs-lookup"><span data-stu-id="ff19b-102">Verify Max Worker Threads Setting</span></span>
  <span data-ttu-id="ff19b-103">Questa regola consente di controllare l'opzione server relativa al numero massimo di thread di lavoro per individuare l'eventuale presenza di impostazioni non corrette.</span><span class="sxs-lookup"><span data-stu-id="ff19b-103">This rule checks the max worker threads server option for potentially incorrect settings.</span></span> <span data-ttu-id="ff19b-104">L'impostazione dell'opzione relativa al numero massimo di thread di lavoro su un valore troppo basso può comportare la presenza di un numero insufficiente di thread per l'elaborazione tempestiva delle richieste client in ingresso e provocare una mancanza di thread.</span><span class="sxs-lookup"><span data-stu-id="ff19b-104">Setting the max worker threads option to a small value may prevent enough threads from servicing incoming client requests in a timely manner and could lead to "thread starvation".</span></span> <span data-ttu-id="ff19b-105">L'impostazione di questa opzione su un valore elevato, tuttavia, può provocare uno spreco di spazio, in quanto ogni thread attivo utilizza 512 KB nei server a 32 bit e fino a 4 MB nei server a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ff19b-105">However, setting the option to a large value can waste address space, because each active thread consumes 512 KB on 32-bit servers and up to 4 MB on 64-bit servers.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ff19b-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="ff19b-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ff19b-107">Impostare l'opzione max worker threads su 0.</span><span class="sxs-lookup"><span data-stu-id="ff19b-107">Set the max worker threads option to 0.</span></span> <span data-ttu-id="ff19b-108">In questo modo, il numero corretto di thread di lavoro attivi verrà determinato automaticamente in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in base alle richieste dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ff19b-108">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically determine the correct number of active worker threads based on user requests.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ff19b-109">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ff19b-109">For More Information</span></span>  
 [<span data-ttu-id="ff19b-110">Configurare l'opzione di configurazione del server max worker threads</span><span class="sxs-lookup"><span data-stu-id="ff19b-110">Configure the max worker threads Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff19b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff19b-111">See Also</span></span>  
 [<span data-ttu-id="ff19b-112">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="ff19b-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
