---
title: La replica di disponibilità è disconnessa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp2connected.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 1a2162d3-54fb-4356-b349-effbdc15a5a4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1db92b8e73b6daaee7edf5042b1d73cfeb471d1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716835"
---
# <a name="availability-replica-is-disconnected"></a><span data-ttu-id="31c1c-102">La replica di disponibilità è disconnessa</span><span class="sxs-lookup"><span data-stu-id="31c1c-102">Availability replica is disconnected</span></span>
    
## <a name="introduction"></a><span data-ttu-id="31c1c-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="31c1c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31c1c-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="31c1c-104">**Policy Name**</span></span>|<span data-ttu-id="31c1c-105">Stato di connessione della replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="31c1c-105">Availability Replica Connection State</span></span>|  
|<span data-ttu-id="31c1c-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="31c1c-106">**Issue**</span></span>|<span data-ttu-id="31c1c-107">La replica di disponibilità è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="31c1c-107">Availability replica is disconnected.</span></span>|  
|<span data-ttu-id="31c1c-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="31c1c-108">**Category**</span></span>|<span data-ttu-id="31c1c-109">**Critico**</span><span class="sxs-lookup"><span data-stu-id="31c1c-109">**Critical**</span></span>|  
|<span data-ttu-id="31c1c-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="31c1c-110">**Facet**</span></span>|<span data-ttu-id="31c1c-111">replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="31c1c-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="31c1c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31c1c-112">Description</span></span>  
 <span data-ttu-id="31c1c-113">Tramite questi criteri è possibile controllare lo stato di connessione tra le repliche di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="31c1c-113">This policy checks the connection state between availability replicas.</span></span> <span data-ttu-id="31c1c-114">I criteri sono in uno stato non integro quando lo stato di connessione della replica di disponibilità è DISCONNESSO.</span><span class="sxs-lookup"><span data-stu-id="31c1c-114">The policy is in an unhealthy state when the connection state of the availability replica is DISCONNECTED.</span></span> <span data-ttu-id="31c1c-115">Altrimenti, sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="31c1c-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31c1c-116"> Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa alla situazione in cui la [replica di disponibilità è disconnessa](https://go.microsoft.com/fwlink/p/?LinkId=220857) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="31c1c-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability replica is disconnected](https://go.microsoft.com/fwlink/p/?LinkId=220857) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="31c1c-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="31c1c-117">Possible Causes</span></span>  
 <span data-ttu-id="31c1c-118">La replica secondaria non è connessa alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="31c1c-118">The secondary replica is not connected to the primary replica.</span></span> <span data-ttu-id="31c1c-119">Lo stato è DISCONNESSO.</span><span class="sxs-lookup"><span data-stu-id="31c1c-119">The connected state is DISCONNECTED.</span></span> <span data-ttu-id="31c1c-120">Il problema può essere causato da uno dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="31c1c-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="31c1c-121">La porta di connessione potrebbe essere in conflitto con un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="31c1c-121">The connection port might be in conflict with another application.</span></span>  
  
-   <span data-ttu-id="31c1c-122">Il tipo o l'algoritmo di crittografia non è corrispondente.</span><span class="sxs-lookup"><span data-stu-id="31c1c-122">The encryption type or algorithm is mismatched.</span></span>  
  
-   <span data-ttu-id="31c1c-123">L'endpoint di connessione è stato eliminato o non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="31c1c-123">The connection endpoint has been deleted or has not been started.</span></span>  
  
-   <span data-ttu-id="31c1c-124">Il trasporto è disconnesso.</span><span class="sxs-lookup"><span data-stu-id="31c1c-124">The transport is disconnected.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="31c1c-125">Possibili soluzioni</span><span class="sxs-lookup"><span data-stu-id="31c1c-125">Possible Solutions</span></span>  
 <span data-ttu-id="31c1c-126">Di seguito sono riportate le possibili soluzioni a questo problema:</span><span class="sxs-lookup"><span data-stu-id="31c1c-126">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="31c1c-127">Verificare la configurazione dell'endpoint del mirroring di database per le istanze della replica primaria e secondaria e aggiornare la configurazione non corrispondente.</span><span class="sxs-lookup"><span data-stu-id="31c1c-127">Check the database mirroring endpoint configuration for the instances of the primary and secondary replica and update the mismatched configuration.</span></span>  
  
-   <span data-ttu-id="31c1c-128">Controllare se la porta è in conflitto, e in questo caso, modificare il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="31c1c-128">Check if the port is conflicting, and if so, change the port number.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c1c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31c1c-129">See Also</span></span>  
 <span data-ttu-id="31c1c-130">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="31c1c-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="31c1c-131">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="31c1c-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
