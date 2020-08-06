---
title: Un database secondario non è associato | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp2joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 10817e5e-75fa-42dd-baa2-359bea3ad051
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81275e85fd865924778f6d6f985e170a5bda9f9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724211"
---
# <a name="secondary-database-is-not-joined"></a><span data-ttu-id="e7880-102">Un database secondario non è associato</span><span class="sxs-lookup"><span data-stu-id="e7880-102">Secondary database is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="e7880-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="e7880-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7880-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="e7880-104">**Policy Name**</span></span>|<span data-ttu-id="e7880-105">Stato di join del database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="e7880-105">Availability Database Join State</span></span>|  
|<span data-ttu-id="e7880-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="e7880-106">**Issue**</span></span>|<span data-ttu-id="e7880-107">Il database secondario non è unito in join.</span><span class="sxs-lookup"><span data-stu-id="e7880-107">Secondary database is not joined.</span></span>|  
|<span data-ttu-id="e7880-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="e7880-108">**Category**</span></span>|<span data-ttu-id="e7880-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="e7880-109">**Warning**</span></span>|  
|<span data-ttu-id="e7880-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="e7880-110">**Facet**</span></span>|<span data-ttu-id="e7880-111">Database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="e7880-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e7880-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7880-112">Description</span></span>  
 <span data-ttu-id="e7880-113">Questi criteri consentono di controllare lo stato di join del database secondario, anche noto come "replica di database secondaria".</span><span class="sxs-lookup"><span data-stu-id="e7880-113">This policy checks the join state of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="e7880-114">I criteri sono in uno stato non integro quando la replica del set di dati non è unita in join.</span><span class="sxs-lookup"><span data-stu-id="e7880-114">The policy is in an unhealthy state when the dataset replica is not joined.</span></span> <span data-ttu-id="e7880-115">Altrimenti, sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="e7880-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7880-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]le informazioni sulle cause e sulle soluzioni possibili sono disponibili in [Secondary database is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220862) (Database secondario non unito in join) in TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="e7880-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Secondary database is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220862) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="e7880-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="e7880-117">Possible Causes</span></span>  
 <span data-ttu-id="e7880-118">Questo database secondario non è unito in join al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="e7880-118">This secondary database is not joined to the availability group.</span></span> <span data-ttu-id="e7880-119">La configurazione di questo database secondario è incompleta.</span><span class="sxs-lookup"><span data-stu-id="e7880-119">The configuration of this secondary database is incomplete.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="e7880-120">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="e7880-120">Possible Solution</span></span>  
 <span data-ttu-id="e7880-121">Utilizzare Transact-SQL, PowerShell o SQL Server Management Studio per creare un join della replica secondaria al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="e7880-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="e7880-122">Per altre informazioni sul join delle repliche secondarie ai gruppi di disponibilità, vedere [Creare un join di una replica secondaria a un gruppo di disponibilità (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="e7880-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7880-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7880-123">See Also</span></span>  
 <span data-ttu-id="e7880-124">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e7880-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="e7880-125">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e7880-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
