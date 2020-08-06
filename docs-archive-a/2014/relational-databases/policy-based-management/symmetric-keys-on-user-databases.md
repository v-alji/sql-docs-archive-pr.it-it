---
title: Chiavi simmetriche nei database utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3333ab5b-2518-4753-a0a8-57df5e5af74f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ca0fb62ccb32ce244e1087281997dcd9929df89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626705"
---
# <a name="symmetric-keys-on-user-databases"></a><span data-ttu-id="da3d7-102">Chiavi simmetriche nei database utente</span><span class="sxs-lookup"><span data-stu-id="da3d7-102">Symmetric Keys on User Databases</span></span>
  <span data-ttu-id="da3d7-103">Questa regola consente di controllare se le chiavi con lunghezza minore di 128 byte utilizzano l'algoritmo di crittografia RC2 o RC4.</span><span class="sxs-lookup"><span data-stu-id="da3d7-103">This rule checks whether keys that have a length of less than 128 bytes do not use the RC2 or RC4 encryption algorithm.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="da3d7-104">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="da3d7-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="da3d7-105">Utilizzare la crittografia AES a 128 bit o maggiore per creare chiavi simmetriche per la crittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="da3d7-105">Use AES 128 bit or larger to create symmetric keys for data encryption.</span></span> <span data-ttu-id="da3d7-106">Se la crittografia AES non è supportata dal sistema operativo in uso, utilizzare 3DES.</span><span class="sxs-lookup"><span data-stu-id="da3d7-106">If AES is not supported by your operating system, use 3DES.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="da3d7-107">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="da3d7-107">For More Information</span></span>  
 [<span data-ttu-id="da3d7-108">Scelta di un algoritmo di crittografia</span><span class="sxs-lookup"><span data-stu-id="da3d7-108">Choose an Encryption Algorithm</span></span>](../security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a><span data-ttu-id="da3d7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da3d7-109">See Also</span></span>  
 [<span data-ttu-id="da3d7-110">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="da3d7-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
