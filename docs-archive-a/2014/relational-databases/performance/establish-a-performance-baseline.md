---
title: Definire una base di riferimento delle prestazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], baselines
- monitoring performance [SQL Server], baselines
- tuning databases [SQL Server], baselines
- server performance [SQL Server], baselines
- performance [SQL Server], baselines
- baseline performance [SQL Server]
- measurements for baseline statistics [SQL Server]
- monitoring server performance [SQL Server], establishing baseline
- database monitoring [SQL Server], baselines
ms.assetid: dc5aa8d6-2507-448f-ad86-4196443915fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0cb85ae8ad370b816c6240b58aabd247c7593c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713060"
---
# <a name="establish-a-performance-baseline"></a><span data-ttu-id="b7327-102">Definire una base di riferimento delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="b7327-102">Establish a Performance Baseline</span></span>
  <span data-ttu-id="b7327-103">Per stabilire se le prestazioni del sistema [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono ottimali, misurare le prestazioni a intervalli di tempo regolari, anche quando non si è verificato alcun problema, in modo da definire una base di riferimento per le prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="b7327-103">To determine whether your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system is performing optimally, take performance measurements at regular intervals over time, even when no problems occur, to establish a server performance baseline.</span></span> <span data-ttu-id="b7327-104">Confrontare ogni set di misurazioni con i set precedenti.</span><span class="sxs-lookup"><span data-stu-id="b7327-104">Compare each new set of measurements with those taken earlier.</span></span>  
  
 <span data-ttu-id="b7327-105">Le aree seguenti influiscono sulle prestazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b7327-105">The following areas affect the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="b7327-106">Risorse di sistema (hardware)</span><span class="sxs-lookup"><span data-stu-id="b7327-106">System resources (hardware)</span></span>  
  
-   <span data-ttu-id="b7327-107">Architettura di rete</span><span class="sxs-lookup"><span data-stu-id="b7327-107">Network architecture</span></span>  
  
-   <span data-ttu-id="b7327-108">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="b7327-108">The operating system</span></span>  
  
-   <span data-ttu-id="b7327-109">Applicazioni di database</span><span class="sxs-lookup"><span data-stu-id="b7327-109">Database applications</span></span>  
  
-   <span data-ttu-id="b7327-110">Applicazioni client</span><span class="sxs-lookup"><span data-stu-id="b7327-110">Client applications</span></span>  
  
 <span data-ttu-id="b7327-111">Le misurazioni di riferimento devono essere utilizzate almeno per determinare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7327-111">At a minimum, use baseline measurements to determine:</span></span>  
  
-   <span data-ttu-id="b7327-112">Orari di punta e di minore attività.</span><span class="sxs-lookup"><span data-stu-id="b7327-112">Peak and off-peak hours of operation.</span></span>  
  
-   <span data-ttu-id="b7327-113">Tempi di risposta di query o batch di comandi.</span><span class="sxs-lookup"><span data-stu-id="b7327-113">Production-query or batch-command response times.</span></span>  
  
-   <span data-ttu-id="b7327-114">Tempi necessari per il completamento di operazioni di backup e ripristino dei database.</span><span class="sxs-lookup"><span data-stu-id="b7327-114">Database backup and restore completion times.</span></span>  
  
 <span data-ttu-id="b7327-115">Dopo aver definito una base di riferimento attendibile, confrontare i dati statistici di riferimento con le prestazioni correnti del server.</span><span class="sxs-lookup"><span data-stu-id="b7327-115">After you establish a server performance baseline, compare the baseline statistics to current server performance.</span></span> <span data-ttu-id="b7327-116">I valori notevolmente superiori o inferiori a quelli di riferimento sono possibili candidati per analisi più approfondite.</span><span class="sxs-lookup"><span data-stu-id="b7327-116">Numbers far above or far below your baseline are candidates for further investigation.</span></span> <span data-ttu-id="b7327-117">Tali scostamenti possono indicare aree per cui sono necessari interventi di ottimizzazione o riconfigurazione.</span><span class="sxs-lookup"><span data-stu-id="b7327-117">They may indicate areas in need of tuning or reconfiguration.</span></span> <span data-ttu-id="b7327-118">In presenza di un aumento dei tempi di esecuzione di un set di query, ad esempio, esaminare le query per verificare se è possibile riscriverle oppure se è necessario aggiungere statistiche di colonna o nuovi indici.</span><span class="sxs-lookup"><span data-stu-id="b7327-118">For example, if the amount of time to execute a set of queries increases, examine the queries to determine if they can be rewritten, or if column statistics or new indexes must be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7327-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7327-119">See Also</span></span>  
 [<span data-ttu-id="b7327-120">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b7327-120">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
