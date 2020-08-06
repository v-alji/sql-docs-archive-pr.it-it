---
title: Valore massimo per le dimensioni del pacchetto di rete impostato su 8060 byte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 86db5da1-afe4-4fbb-8bf8-33cedc7e4361
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 01b500cbe65107767d73bc2901b6d5e028b94ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626706"
---
# <a name="network-packet-size-should-not-exceed-8060-bytes"></a><span data-ttu-id="459b2-102">Valore massimo per le dimensioni del pacchetto di rete impostato su 8060 byte</span><span class="sxs-lookup"><span data-stu-id="459b2-102">Network Packet Size Should Not Exceed 8060 Bytes</span></span>
  <span data-ttu-id="459b2-103">Se il valore specificato per sp_configure ''network packet size' o se le dimensioni del pacchetto di rete di qualsiasi utente connesso sono maggiori di 8060 byte, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue operazioni di allocazione della memoria diverse.</span><span class="sxs-lookup"><span data-stu-id="459b2-103">If the value specified for sp_configure 'network packet size' or if the network packet size of any logged-in user is more than 8060 bytes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs different memory allocation operations.</span></span> <span data-ttu-id="459b2-104">In questo caso, può verificarsi un aumento dello spazio degli indirizzi virtuali dei processi non riservato per il pool di buffer.</span><span class="sxs-lookup"><span data-stu-id="459b2-104">This can cause an increase in the process virtual address space that is not reserved for the buffer pool.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="459b2-105">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="459b2-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="459b2-106">Le dimensioni del pacchetto di rete non devono superare 8060 byte.</span><span class="sxs-lookup"><span data-stu-id="459b2-106">The network packet size should not exceed 8060 bytes.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="459b2-107">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="459b2-107">For More Information</span></span>  
 [<span data-ttu-id="459b2-108">Articolo 903002 della Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="459b2-108">Microsoft Knowledge Base article 903002</span></span>](https://go.microsoft.com/fwlink/?linkid=117749)  
  
## <a name="see-also"></a><span data-ttu-id="459b2-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="459b2-109">See Also</span></span>  
 [<span data-ttu-id="459b2-110">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="459b2-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
