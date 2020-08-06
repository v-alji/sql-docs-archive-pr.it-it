---
title: Il gruppo di disponibilità non è pronto per il failover automatico | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp3autofailover.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 28261014-342c-442a-bd89-6d04b8d4e8b7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2995ddec51cd70d8a3f209229d0ecb9b0132c79e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624379"
---
# <a name="availability-group-is-not-ready-for-automatic-failover"></a><span data-ttu-id="79353-102">Il gruppo di disponibilità non è pronto per il failover automatico</span><span class="sxs-lookup"><span data-stu-id="79353-102">Availability group is not ready for automatic failover</span></span>
    
## <a name="introduction"></a><span data-ttu-id="79353-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="79353-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79353-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="79353-104">**Policy Name**</span></span>|<span data-ttu-id="79353-105">Conformità del gruppo di disponibilità al failover automatico</span><span class="sxs-lookup"><span data-stu-id="79353-105">Availability Group Automatic Failover Readiness</span></span>|  
|<span data-ttu-id="79353-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="79353-106">**Issue**</span></span>|<span data-ttu-id="79353-107">Il gruppo di disponibilità non è pronto per il failover automatico.</span><span class="sxs-lookup"><span data-stu-id="79353-107">Availability group is not ready for automatic failover.</span></span>|  
|<span data-ttu-id="79353-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="79353-108">**Category**</span></span>|<span data-ttu-id="79353-109">**Critico**</span><span class="sxs-lookup"><span data-stu-id="79353-109">**Critical**</span></span>|  
|<span data-ttu-id="79353-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="79353-110">**Facet**</span></span>|<span data-ttu-id="79353-111">gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="79353-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="79353-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79353-112">Description</span></span>  
 <span data-ttu-id="79353-113">Con questi criteri è possibile verificare che nel gruppo di disponibilità sia disponibile almeno una replica secondaria pronta per il failover.</span><span class="sxs-lookup"><span data-stu-id="79353-113">This policy checks to verify that the availability group has at least one secondary replica that is failover ready.</span></span> <span data-ttu-id="79353-114">I criteri si trovano in uno stato non integro e viene generato un avviso quando il failover della replica primaria è automatico, ma nessuna delle repliche secondarie nel gruppo di disponibilità è pronta per il failover.</span><span class="sxs-lookup"><span data-stu-id="79353-114">The policy is in an unhealthy state and an alert is raised when the failover mode of the primary replica is automatic, however none of the secondary replicas in the availability group are failover ready.</span></span>  
  
 <span data-ttu-id="79353-115">I criteri sono in uno stato integro quando almeno una replica secondaria è pronta per il failover automatico.</span><span class="sxs-lookup"><span data-stu-id="79353-115">The policy is in a healthy state when at least one secondary replica is automatic failover ready.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79353-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa alla situazione in cui il [gruppo di disponibilità non è pronto per il failover automatico](https://go.microsoft.com/fwlink/p/?LinkId=220851) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="79353-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is not ready for automatic failover](https://go.microsoft.com/fwlink/p/?LinkId=220851) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="79353-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="79353-117">Possible Causes</span></span>  
 <span data-ttu-id="79353-118">Il gruppo di disponibilità non è pronto per il failover automatico.</span><span class="sxs-lookup"><span data-stu-id="79353-118">The availability group is not ready for automatic failover.</span></span> <span data-ttu-id="79353-119">La replica primaria viene configurata per il failover automatico; tuttavia, la replica secondaria non è pronta per il failover automatico.</span><span class="sxs-lookup"><span data-stu-id="79353-119">The primary replica is configured for automatic failover; however, the secondary replica is not ready for automatic failover.</span></span> <span data-ttu-id="79353-120">La replica secondaria configurata per il failover automatico potrebbe non essere disponibile o il relativo stato della sincronizzazione dei dati è attualmente NON SINCRONIZZATO.</span><span class="sxs-lookup"><span data-stu-id="79353-120">The secondary replica that is configured for automatic failover might be unavailable or its data synchronization state is currently not SYNCHRONIZED.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="79353-121">Possibili soluzioni</span><span class="sxs-lookup"><span data-stu-id="79353-121">Possible Solutions</span></span>  
 <span data-ttu-id="79353-122">Di seguito sono riportate le possibili soluzioni a questo problema:</span><span class="sxs-lookup"><span data-stu-id="79353-122">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="79353-123">Verificare che almeno una replica secondaria venga configurata come failover automatico.</span><span class="sxs-lookup"><span data-stu-id="79353-123">Verify that at least one secondary replica is configured as automatic failover.</span></span> <span data-ttu-id="79353-124">Se non è disponibile alcuna replica secondaria configurata come failover automatico, aggiornare la configurazione di una replica secondaria affinché rappresenti la destinazione del failover automatico con commit sincrono.</span><span class="sxs-lookup"><span data-stu-id="79353-124">If there is not a secondary replica configured as automatic failover, update the configuration of a secondary replica to be the automatic failover target with synchronous commit.</span></span>  
  
-   <span data-ttu-id="79353-125">Utilizzare i criteri per verificare che i dati siano in uno stato di sincronizzazione e che la destinazione del failover automatico sia SINCRONIZZATO, quindi risolvere il problema della replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="79353-125">Use the policy to verify that the data is in a synchronization state and the automatic failover target is SYNCHRONIZED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79353-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79353-126">See Also</span></span>  
 <span data-ttu-id="79353-127">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="79353-127">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="79353-128">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="79353-128">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
