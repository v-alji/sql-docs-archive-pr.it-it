---
title: Alcune repliche di disponibilità non presentano un ruolo integro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp6allroleshealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 7ec5b337-7201-4a66-a541-7560f8b18784
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 801fe20edf6f2dbe09bc800722cf4210988ebc69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628988"
---
# <a name="some-availability-replicas-do-not-have-a-healthy-role"></a><span data-ttu-id="9b2d1-102">Alcune repliche di disponibilità non dispongono di un ruolo integro</span><span class="sxs-lookup"><span data-stu-id="9b2d1-102">Some availability replicas do not have a healthy role</span></span>
    
## <a name="introduction"></a><span data-ttu-id="9b2d1-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="9b2d1-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b2d1-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="9b2d1-104">**Policy Name**</span></span>|<span data-ttu-id="9b2d1-105">Stato del ruolo delle repliche di disponibilità</span><span class="sxs-lookup"><span data-stu-id="9b2d1-105">Availability Replicas Role State</span></span>|  
|<span data-ttu-id="9b2d1-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="9b2d1-106">**Issue**</span></span>|<span data-ttu-id="9b2d1-107">Alcune repliche di disponibilità non presentano un ruolo integro.</span><span class="sxs-lookup"><span data-stu-id="9b2d1-107">Some availability replicas do not have a healthy role.</span></span>|  
|<span data-ttu-id="9b2d1-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="9b2d1-108">**Category**</span></span>|<span data-ttu-id="9b2d1-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="9b2d1-109">**Warning**</span></span>|  
|<span data-ttu-id="9b2d1-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="9b2d1-110">**Facet**</span></span>|<span data-ttu-id="9b2d1-111">gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="9b2d1-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9b2d1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b2d1-112">Description</span></span>  
 <span data-ttu-id="9b2d1-113">Questi criteri consentono di eseguire il rollup dello stato di connessione di tutte le repliche di disponibilità e di verificare l'eventuale esistenza di repliche di disponibilità che non presentano un ruolo integro.</span><span class="sxs-lookup"><span data-stu-id="9b2d1-113">This policy rolls up the connection state of all availability replicas and checks if there are any availability replicas that are not in a healthy role.</span></span> <span data-ttu-id="9b2d1-114">I criteri sono in uno stato non integro quando una replica di disponibilità non è né primaria né secondaria.</span><span class="sxs-lookup"><span data-stu-id="9b2d1-114">The policy is in an unhealthy state when any availability replica is neither primary nor secondary.</span></span> <span data-ttu-id="9b2d1-115">Altrimenti, sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="9b2d1-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b2d1-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa ad [alcune repliche di disponibilità che non presentano un ruolo integro](https://go.microsoft.com/fwlink/p/?LinkId=220854) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="9b2d1-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas do not have a healthy role](https://go.microsoft.com/fwlink/p/?LinkId=220854) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="9b2d1-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="9b2d1-117">Possible Causes</span></span>  
 <span data-ttu-id="9b2d1-118">Nel gruppo di disponibilità è presente almeno una replica di disponibilità il cui ruolo attuale non è primario né secondario.</span><span class="sxs-lookup"><span data-stu-id="9b2d1-118">In this availability group, at least one availability replica does not currently have the primary or secondary role.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="9b2d1-119">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="9b2d1-119">Possible Solution</span></span>  
 <span data-ttu-id="9b2d1-120">Utilizzare lo stato dei criteri della replica di disponibilità per trovare quella il cui ruolo non è primario o secondario e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="9b2d1-120">Use the availability replica policy state to find the availability replica whose role is not primary or secondary, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2d1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b2d1-121">See Also</span></span>  
 <span data-ttu-id="9b2d1-122">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b2d1-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="9b2d1-123">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9b2d1-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
