---
title: Replica di disponibilità non unita in join | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp4joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 9c0d10b1-9e12-430c-83b9-ca2bd0a3afc4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7c4f76e98d373e50124f5ca2b135a9fad8f34226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716832"
---
# <a name="availability-replica-is-not-joined"></a><span data-ttu-id="2f72b-102">Replica di disponibilità non unita in join</span><span class="sxs-lookup"><span data-stu-id="2f72b-102">Availability replica is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="2f72b-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="2f72b-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f72b-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="2f72b-104">**Policy Name**</span></span>|<span data-ttu-id="2f72b-105">Stato di join della replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="2f72b-105">Availability Replica Join State</span></span>|  
|<span data-ttu-id="2f72b-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="2f72b-106">**Issue**</span></span>|<span data-ttu-id="2f72b-107">La replica di disponibilità non è unita in join.</span><span class="sxs-lookup"><span data-stu-id="2f72b-107">Availability Replica is not joined.</span></span>|  
|<span data-ttu-id="2f72b-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="2f72b-108">**Category**</span></span>|<span data-ttu-id="2f72b-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="2f72b-109">**Warning**</span></span>|  
|<span data-ttu-id="2f72b-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="2f72b-110">**Facet**</span></span>|<span data-ttu-id="2f72b-111">replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="2f72b-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f72b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f72b-112">Description</span></span>  
 <span data-ttu-id="2f72b-113">Tramite questi criteri viene controllato lo stato del join della replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2f72b-113">This policy checks the join state of the availability replica.</span></span> <span data-ttu-id="2f72b-114">Lo stato dei criteri non è integro quando la replica di disponibilità viene aggiunta al gruppo di disponibilità, ma non ne viene creato il join correttamente.</span><span class="sxs-lookup"><span data-stu-id="2f72b-114">The policy is in an unhealthy state when the availability replica is added to the availability group, but is not joined properly.</span></span> <span data-ttu-id="2f72b-115">Altrimenti, sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="2f72b-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f72b-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa alla situazione in cui [la replica di disponibilità non è unita in join](https://go.microsoft.com/fwlink/p/?LinkId=220859) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="2f72b-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220859) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="2f72b-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="2f72b-117">Possible Causes</span></span>  
 <span data-ttu-id="2f72b-118">La replica secondaria non è unita in join al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2f72b-118">The secondary replica is not joined to the availability group.</span></span> <span data-ttu-id="2f72b-119">Affinché una replica di disponibilità venga correttamente unita in join al gruppo di disponibilità, lo stato del join deve essere Istanza autonoma unita in join (1) o Cluster di failover unito in join (2).</span><span class="sxs-lookup"><span data-stu-id="2f72b-119">For an availability replica to be successfully joined to the availability group, the join state must be Joined Standalone Instance (1) or Joined Failover Cluster (2).</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="2f72b-120">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="2f72b-120">Possible Solution</span></span>  
 <span data-ttu-id="2f72b-121">Utilizzare Transact-SQL, PowerShell o SQL Server Management Studio per creare un join della replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2f72b-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="2f72b-122">Per altre informazioni sul join delle repliche secondarie ai gruppi di disponibilità, vedere [Creare un join di una replica secondaria a un gruppo di disponibilità (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="2f72b-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f72b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f72b-123">See Also</span></span>  
 <span data-ttu-id="2f72b-124">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2f72b-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="2f72b-125">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2f72b-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
