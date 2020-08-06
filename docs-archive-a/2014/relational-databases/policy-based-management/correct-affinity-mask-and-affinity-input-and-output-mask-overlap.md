---
title: Correggi la maschera di affinità e la maschera di output di input affinità | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1a0da6df-57ff-4f3f-aae9-2fbc4897508c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486b4441a20db7630082344fb1f277bba053f3ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726903"
---
# <a name="correct-affinity-mask-and-affinity-input-output-mask-overlap"></a><span data-ttu-id="62678-102">Correzione della sovrapposizione della maschera di affinità e della maschera di output di input affinità</span><span class="sxs-lookup"><span data-stu-id="62678-102">Correct Affinity Mask and Affinity Input Output Mask Overlap</span></span>
  <span data-ttu-id="62678-103">Questa regola consente di controllare se l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dispone di uno o più processori a cui sono assegnate sia l'opzione affinity mask sia l'opzione affinity I/O mask.</span><span class="sxs-lookup"><span data-stu-id="62678-103">This rule checks whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one or more processors that are assigned to be used with both the affinity mask and the affinity I/O mask options.</span></span> <span data-ttu-id="62678-104">In un computer con più di un processore, le opzioni affinity mask e affinity I/O mask vengono utilizzate per designare le CPU utilizzate da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62678-104">On a computer that has more than one processor, the affinity mask and the affinity I/O mask options are used to designate which CPUs are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="62678-105">L'abilitazione di una CPU con entrambe le opzioni può ridurre le prestazioni forzando un utilizzo eccessivo del processore.</span><span class="sxs-lookup"><span data-stu-id="62678-105">Enabling a CPU with both the affinity mask and the affinity I/O mask can slow performance by forcing the processor to be overused.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="62678-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="62678-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="62678-107">È consigliabile specificare entrambe le opzioni, affinity mask e affinity I/O mask, ma abilitarne una sola per volta per ciascuna CPU.</span><span class="sxs-lookup"><span data-stu-id="62678-107">When you specify either the affinity mask or the affinity I/O mask options, you should specify both, but only enable each CPU no more than once.</span></span>  
  
 <span data-ttu-id="62678-108">Non abilitare entrambe le opzioni per la stessa CPU.</span><span class="sxs-lookup"><span data-stu-id="62678-108">Do not enable the same CPU in both the affinity mask option and the affinity I/O mask option.</span></span> <span data-ttu-id="62678-109">I bit corrispondenti a ogni CPU devono essere associati a uno dei tre stati seguenti:</span><span class="sxs-lookup"><span data-stu-id="62678-109">The bits that correspond to each CPU should be in one of the following states:</span></span>  
  
-   <span data-ttu-id="62678-110">0 sia nell'opzione affinity mask sia nell'opzione affinity I/O mask</span><span class="sxs-lookup"><span data-stu-id="62678-110">0 in both the affinity mask option and the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="62678-111">0 nell'opzione affinity mask e 1 nell'opzione affinity I/O mask</span><span class="sxs-lookup"><span data-stu-id="62678-111">0 in the affinity mask option and 1 in the affinity I/O mask option</span></span>  
  
-   <span data-ttu-id="62678-112">1 nell'opzione affinity mask e 0 nell'opzione affinity I/O mask</span><span class="sxs-lookup"><span data-stu-id="62678-112">1 in the affinity mask option and 0 in the affinity I/O mask option</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="62678-113">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="62678-113">For More Information</span></span>  
 [<span data-ttu-id="62678-114">Opzione di configurazione del server affinity mask</span><span class="sxs-lookup"><span data-stu-id="62678-114">affinity mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="62678-115">Opzione di configurazione del server Affinity Mask I/O</span><span class="sxs-lookup"><span data-stu-id="62678-115">affinity Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity-input-output-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="62678-116">Opzione di configurazione affinity64 mask</span><span class="sxs-lookup"><span data-stu-id="62678-116">affinity64 mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-mask-server-configuration-option.md)  
  
 [<span data-ttu-id="62678-117">Opzione di configurazione del server Affinity64 I/O</span><span class="sxs-lookup"><span data-stu-id="62678-117">affinity64 Input-Output mask Server Configuration Option</span></span>](../../database-engine/configure-windows/affinity64-input-output-mask-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="62678-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62678-118">See Also</span></span>  
 [<span data-ttu-id="62678-119">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="62678-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
