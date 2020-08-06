---
title: Alcune repliche di disponibilità sono disconnesse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp7allconnected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: aea808be-6f0f-40c2-9aa2-a2a435ec6443
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1bb6535b513770b9b4718a0e8372c0a5bc3cba84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628992"
---
# <a name="some-availability-replicas-are-disconnected"></a><span data-ttu-id="b4723-102">Alcune repliche di disponibilità sono disconnesse</span><span class="sxs-lookup"><span data-stu-id="b4723-102">Some availability replicas are disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="b4723-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="b4723-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4723-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="b4723-104">**Policy Name**</span></span>|<span data-ttu-id="b4723-105">Stato di connessione delle repliche di disponibilità</span><span class="sxs-lookup"><span data-stu-id="b4723-105">Availability Replicas Connection State</span></span>|  
|<span data-ttu-id="b4723-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="b4723-106">**Issue**</span></span>|<span data-ttu-id="b4723-107">Alcune repliche di disponibilità sono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="b4723-107">Some availability replicas are disconnected.</span></span>|  
|<span data-ttu-id="b4723-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="b4723-108">**Category**</span></span>|<span data-ttu-id="b4723-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="b4723-109">**Warning**</span></span>|  
|<span data-ttu-id="b4723-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="b4723-110">**Facet**</span></span>|<span data-ttu-id="b4723-111">gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="b4723-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b4723-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4723-112">Description</span></span>  
 <span data-ttu-id="b4723-113">Questi criteri consentono di eseguire il rollup dello stato di connessione di tutte le repliche di disponibilità e di verificare tutte le repliche di disponibilità che sono disconnesse.</span><span class="sxs-lookup"><span data-stu-id="b4723-113">This policy rolls up the connection state of all availability replicas and checks for any availability replicas that are DISCONENCTED.</span></span> <span data-ttu-id="b4723-114">I criteri sono in uno stato non integro quando una replica di disponibilità è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="b4723-114">The policy is in an unhealthy state when any availability replica is DISCONNECTED.</span></span> <span data-ttu-id="b4723-115">Altrimenti, sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="b4723-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4723-116"> Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa alla situazione in cui [alcune repliche di disponibilità sono disconnesse](https://go.microsoft.com/fwlink/p/?LinkId=220855) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="b4723-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220855) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="b4723-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="b4723-117">Possible Causes</span></span>  
 <span data-ttu-id="b4723-118">In questo gruppo di disponibilità, almeno una replica secondaria non è connessa alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="b4723-118">In this availability group, at least one secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="b4723-119">Lo stato è DISCONNESSO.</span><span class="sxs-lookup"><span data-stu-id="b4723-119">The connected state is DISCONNECTED.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="b4723-120">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="b4723-120">Possible Solution</span></span>  
 <span data-ttu-id="b4723-121">Utilizzare lo stato dei criteri della replica di disponibilità per trovare quella disconnessa e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="b4723-121">Use the availability replica policy state to find the availability replica that is DISCONNECTED, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4723-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4723-122">See Also</span></span>  
 <span data-ttu-id="b4723-123">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b4723-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="b4723-124">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b4723-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
