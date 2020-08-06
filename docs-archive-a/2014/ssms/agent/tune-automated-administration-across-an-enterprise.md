---
title: Ottimizzare l'amministrazione automatizzata in un'organizzazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- performance [SQL Server], automated administration
- tuning automated administration [SQL Server]
- monitoring performance [SQL Server], automated administration
ms.assetid: 671fed35-3859-4b0d-8f38-4dd07436857e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52fef95cd13beafef89701196a445a90e6fc1eb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630237"
---
# <a name="tune-automated-administration-across-an-enterprise"></a><span data-ttu-id="c0d21-102">Ottimizzazione dell'amministrazione automatizzata in un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c0d21-102">Tune Automated Administration Across an Enterprise</span></span>
  <span data-ttu-id="c0d21-103">L'amministrazione multiserver implementata da Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sfrutta le caratteristiche di ottimizzazione automatica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0d21-103">Multiserver administration with Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent takes advantage of the self-tuning features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c0d21-104">In condizioni normali, non è pertanto necessario eseguire ottimizzazioni dei processi aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c0d21-104">Therefore, under normal conditions, additional job tuning is not necessary.</span></span> <span data-ttu-id="c0d21-105">L'esecuzione di processi, la generazione di avvisi e le notifiche agli operatori possono tuttavia determinare un aumento dei carichi di rete</span><span class="sxs-lookup"><span data-stu-id="c0d21-105">However, network loads increase when you run jobs, generate alerts, and notify operators.</span></span> <span data-ttu-id="c0d21-106">e in questi casi è possibile ottimizzare l'amministrazione automatizzata all'interno di un'organizzazione in modo da ridurre al minimo il traffico di rete provocato da queste attività.</span><span class="sxs-lookup"><span data-stu-id="c0d21-106">You can tune automated administration across an enterprise to minimize the network traffic these activities cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d21-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0d21-107">See Also</span></span>  
 [<span data-ttu-id="c0d21-108">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="c0d21-108">Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
