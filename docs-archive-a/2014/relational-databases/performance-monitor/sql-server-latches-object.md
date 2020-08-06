---
title: Oggetto Latches di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Latches object
- SQLServer:Latches
ms.assetid: 2393ea1c-2bf3-41c3-9f37-b9761144eeca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f49ac00114065e971c0893f9217ab883eb2d7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625338"
---
# <a name="sql-server-latches-object"></a><span data-ttu-id="e2e51-102">Oggetto Latch di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2e51-102">SQL Server, Latches Object</span></span>
  <span data-ttu-id="e2e51-103">L'oggetto **SQLServer:Latch** in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornisce contatori per monitorare i blocchi di risorsa interni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , definiti latch.</span><span class="sxs-lookup"><span data-stu-id="e2e51-103">The **SQLServer:Latches** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor internal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource locks called latches.</span></span> <span data-ttu-id="e2e51-104">Il monitoraggio dei latch per determinare l'attività degli utenti e l'utilizzo delle risorse può essere utile per identificare eventuali colli di bottiglia.</span><span class="sxs-lookup"><span data-stu-id="e2e51-104">Monitoring the latches to determine user activity and resource usage can help you to identify performance bottlenecks.</span></span>  
  
 <span data-ttu-id="e2e51-105">Nella tabella seguente vengono descritti i contatori dell'oggetto **Latches** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2e51-105">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Latches** counters.</span></span>  
  
|<span data-ttu-id="e2e51-106">Contatori di SQLServer:Latch</span><span class="sxs-lookup"><span data-stu-id="e2e51-106">SQL Server Latches counters</span></span>|<span data-ttu-id="e2e51-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2e51-107">Description</span></span>|  
|---------------------------------|-----------------|  
|<span data-ttu-id="e2e51-108">**Tempo medio di attesa latch (ms)**</span><span class="sxs-lookup"><span data-stu-id="e2e51-108">**Average Latch Wait Time (ms)**</span></span>|<span data-ttu-id="e2e51-109">Tempo medio di attesa di latch da parte delle richieste di latch (in millisecondi).</span><span class="sxs-lookup"><span data-stu-id="e2e51-109">Average latch wait time (in milliseconds) for latch requests that had to wait.</span></span>|  
|<span data-ttu-id="e2e51-110">**Attese latch/sec**</span><span class="sxs-lookup"><span data-stu-id="e2e51-110">**Latch Waits/sec**</span></span>|<span data-ttu-id="e2e51-111">Numero di richieste di latch non soddisfatte immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e2e51-111">Number of latch requests that could not be granted immediately.</span></span>|  
|<span data-ttu-id="e2e51-112">**Numero di SuperLatch**</span><span class="sxs-lookup"><span data-stu-id="e2e51-112">**Number of SuperLatches**</span></span>|<span data-ttu-id="e2e51-113">Numero di latch utilizzati attualmente come SuperLatch.</span><span class="sxs-lookup"><span data-stu-id="e2e51-113">Number of latches that are currently SuperLatches.</span></span>|  
|<span data-ttu-id="e2e51-114">**Abbassamenti di livello SuperLatch/sec**</span><span class="sxs-lookup"><span data-stu-id="e2e51-114">**SuperLatch Demotions/sec**</span></span>|<span data-ttu-id="e2e51-115">Numero di SuperLatch abbassati al livello di latch normali nell'ultimo secondo.</span><span class="sxs-lookup"><span data-stu-id="e2e51-115">Number of SuperLatches that have been demoted to regular latches in the last second.</span></span>|  
|<span data-ttu-id="e2e51-116">**Promozioni a SuperLatch/sec**</span><span class="sxs-lookup"><span data-stu-id="e2e51-116">**SuperLatch Promotions/sec**</span></span>|<span data-ttu-id="e2e51-117">Numero di latch promossi a SuperLatch nell'ultimo secondo.</span><span class="sxs-lookup"><span data-stu-id="e2e51-117">Number of latches that have been promoted to SuperLatches in the last second.</span></span>|  
|<span data-ttu-id="e2e51-118">**Tempo totale di attesa latch (ms)**</span><span class="sxs-lookup"><span data-stu-id="e2e51-118">**Total Latch Wait Time (ms)**</span></span>|<span data-ttu-id="e2e51-119">Tempo totale di attesa di latch da parte delle richieste di latch nell'ultimo secondo (in millisecondi).</span><span class="sxs-lookup"><span data-stu-id="e2e51-119">Total latch wait time (in milliseconds) for latch requests in the last second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2e51-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2e51-120">See Also</span></span>  
 [<span data-ttu-id="e2e51-121">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="e2e51-121">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
