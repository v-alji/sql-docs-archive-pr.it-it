---
title: Replica transazionale bidirezionale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- bidirectional replication
- transactional replication, bidirectional replication
- bidirectional transactional replication
ms.assetid: 98772e95-67ed-4010-8108-5113dbe709ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57b18dde2e7134e0ba9eb6a9b2e8f5357d171a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629341"
---
# <a name="bidirectional-transactional-replication"></a><span data-ttu-id="db84b-102">replica transazionale bidirezionale</span><span class="sxs-lookup"><span data-stu-id="db84b-102">Bidirectional Transactional Replication</span></span>
  <span data-ttu-id="db84b-103">La replica transazionale bidirezionale è una topologia di replica transazionale specifica che consente lo scambio reciproco di modifiche tra due server: ogni server pubblica i dati e successivamente esegue la sottoscrizione di una pubblicazione con gli stessi dati dell'altro server.</span><span class="sxs-lookup"><span data-stu-id="db84b-103">Bidirectional transactional replication is a specific transactional replication topology that allows two servers to exchange changes with each other: each server publishes data and then subscribes to a publication with the same data from the other server.</span></span> <span data-ttu-id="db84b-104">Il **@loopback_detection** parametro di [sp_addsubscription &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) è impostato su true per garantire che le modifiche vengano inviate solo al Sottoscrittore e che non comportino l'invio della modifica al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="db84b-104">The **@loopback_detection** parameter of [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) is set to TRUE to ensure that changes are only sent to the Subscriber and do not result in the change being sent back to the Publisher.</span></span>  
  
 <span data-ttu-id="db84b-105">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] e versioni successive questa topologia è supportata inoltre dalla replica transazionale peer-to-peer, ma la replica bidirezionale consente di migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="db84b-105">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later versions, this topology is also supported by peer-to-peer transactional replication, but bidirectional replication can provide improved performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db84b-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db84b-106">See Also</span></span>  
 [<span data-ttu-id="db84b-107">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="db84b-107">Peer-to-Peer Transactional Replication</span></span>](peer-to-peer-transactional-replication.md)  
  
  
