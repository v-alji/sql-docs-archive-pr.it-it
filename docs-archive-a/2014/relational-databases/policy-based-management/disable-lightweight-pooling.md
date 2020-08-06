---
title: Disabilitare l'opzione lightweight pooling | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 481bb43d-6fe5-497c-9096-971fb6bf733b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13b9ccba0a3a5805dab2eec1d04cc161e6dbd6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725591"
---
# <a name="disable-lightweight-pooling"></a><span data-ttu-id="518dd-102">Disabilitazione di lightweight pooling</span><span class="sxs-lookup"><span data-stu-id="518dd-102">Disable Lightweight Pooling</span></span>
  <span data-ttu-id="518dd-103">Questa regola consente di controllare che l'opzione lightweight pooling sia disabilitata nel server.</span><span class="sxs-lookup"><span data-stu-id="518dd-103">This rule checks that lightweight pooling is disabled on the server.</span></span> <span data-ttu-id="518dd-104">Se si imposta lightweight pooling su 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passerà alla pianificazione in modalità fiber.</span><span class="sxs-lookup"><span data-stu-id="518dd-104">Setting lightweightpooling to 1 causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to switch to fiber mode scheduling.</span></span> <span data-ttu-id="518dd-105">La modalità fiber deve essere utilizzata in situazioni specifiche in cui il cambio di contesto dei thread di lavoro UMS costituisce un importante collo di bottiglia per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="518dd-105">Fiber mode is intended for certain situations in which the context switching of the UMS workers is the important bottleneck in performance.</span></span> <span data-ttu-id="518dd-106">Poiché questa situazione è poco frequente, la modalità fiber consente raramente di ottimizzare le prestazioni o la scalabilità in un sistema tipico.</span><span class="sxs-lookup"><span data-stu-id="518dd-106">Because this is rare, fiber mode seldom improves performance or scalability on the typical system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="518dd-107">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="518dd-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="518dd-108">L'opzione lightweightpooling deve essere abilitata solo in seguito a test approfonditi, dopo avere valutato tutte le altre possibilità di ottimizzazione delle prestazioni, e quando il cambio del contesto è un problema noto nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="518dd-108">The lightweightpooling option should only be enabled after thorough testing, after all other performance tuning opportunities are evaluated, and when context switching is a known issue in your environment.</span></span>  
  
 <span data-ttu-id="518dd-109">È consigliabile evitare di utilizzare la pianificazione in modalità fiber per operazioni di routine, in quanto può ridurre le prestazioni impedendo i normali vantaggi derivati dal cambio del contesto e perché alcuni componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che utilizzano TLS (Thread Local Storage) o oggetti di proprietà del thread, ad esempio i mutex (un tipo di oggetto kernel Win32), non possono funzionare correttamente in modalità fiber.</span><span class="sxs-lookup"><span data-stu-id="518dd-109">We recommend that you do not use fiber mode scheduling for routine operation because it can decrease performance by preventing the regular benefits of context switching, and because some components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that use Thread Local Storage (TLS) or thread-owned objects, such as mutexes (a kind of Win32 kernel object), cannot function correctly in fiber mode</span></span>  
  
 <span data-ttu-id="518dd-110">Per rimuovere l'opzione lightweight pooling, eseguire l'istruzione seguente, quindi riavviare il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="518dd-110">To remove lightweight pooling, execute the following statement, and then restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
sp_configure 'lightweightpooling', 0;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="518dd-111">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="518dd-111">For More Information</span></span>  
 [<span data-ttu-id="518dd-112">Opzione di configurazione del server lightweight pooling</span><span class="sxs-lookup"><span data-stu-id="518dd-112">lightweight pooling Server Configuration Option</span></span>](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="518dd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="518dd-113">See Also</span></span>  
 [<span data-ttu-id="518dd-114">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="518dd-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
