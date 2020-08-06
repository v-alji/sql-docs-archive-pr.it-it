---
title: La replica di disponibilità non presenta un ruolo integro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp1rolehealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: ebb2c9f4-2097-4688-b4fb-8f0571047317
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7be26945903a5e3b602ef4a99c269de6a58b04a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716840"
---
# <a name="availability-replica-does-not-have-a-healthy-role"></a><span data-ttu-id="2b9ea-102">La replica di disponibilità non dispone di un ruolo integro</span><span class="sxs-lookup"><span data-stu-id="2b9ea-102">Availability replica does not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="2b9ea-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="2b9ea-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b9ea-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="2b9ea-104">**Policy Name**</span></span>|<span data-ttu-id="2b9ea-105">Stato del ruolo della replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="2b9ea-105">Availability Replica Role State</span></span>|  
|<span data-ttu-id="2b9ea-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="2b9ea-106">**Issue**</span></span>|<span data-ttu-id="2b9ea-107">La replica di disponibilità non presenta un ruolo integro.</span><span class="sxs-lookup"><span data-stu-id="2b9ea-107">Availability replica does not have a healthy role.</span></span>|  
|<span data-ttu-id="2b9ea-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="2b9ea-108">**Category**</span></span>|<span data-ttu-id="2b9ea-109">**Critico**</span><span class="sxs-lookup"><span data-stu-id="2b9ea-109">**Critical**</span></span>|  
|<span data-ttu-id="2b9ea-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="2b9ea-110">**Facet**</span></span>|<span data-ttu-id="2b9ea-111">replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="2b9ea-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b9ea-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b9ea-112">Description</span></span>  
 <span data-ttu-id="2b9ea-113">Tramite questi criteri viene controllato lo stato del ruolo della replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2b9ea-113">This policy checks the state of the role of the availability replica.</span></span> <span data-ttu-id="2b9ea-114">I criteri sono in uno stato non integro quando il ruolo della replica di disponibilità non è né primario né secondario.</span><span class="sxs-lookup"><span data-stu-id="2b9ea-114">The policy is in an unhealthy state when the role of the availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="2b9ea-115">Altrimenti, sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="2b9ea-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b9ea-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa alla [replica di disponibilità che non presenta un ruolo integro](https://go.microsoft.com/fwlink/p/?LinkId=220856) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="2b9ea-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica does not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220856) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="2b9ea-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="2b9ea-117">Possible Causes</span></span>  
 <span data-ttu-id="2b9ea-118">Il ruolo di questa replica di disponibilità non è integro.</span><span class="sxs-lookup"><span data-stu-id="2b9ea-118">The role of this availability replica is unhealthy.</span></span> <span data-ttu-id="2b9ea-119">La replica non presenta il ruolo primario o quello secondario.</span><span class="sxs-lookup"><span data-stu-id="2b9ea-119">The replica does not have either the primary or secondary role.</span></span>  
  
## <a name="possible-solution-information_still_to_come"></a><span data-ttu-id="2b9ea-120">Possibile soluzione: Information_still_to_come</span><span class="sxs-lookup"><span data-stu-id="2b9ea-120">Possible Solution: Information_still_to_come</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b9ea-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b9ea-121">See Also</span></span>  
 <span data-ttu-id="2b9ea-122">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2b9ea-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="2b9ea-123">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2b9ea-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
