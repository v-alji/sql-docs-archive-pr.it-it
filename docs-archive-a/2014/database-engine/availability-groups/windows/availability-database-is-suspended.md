---
title: Il database di disponibilità è sospeso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp1notsuspended.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6baee70f-848c-4e86-b20d-78875c0f82cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07a547f217367f13df739348325461c862d831f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624383"
---
# <a name="availability-database-is-suspended"></a><span data-ttu-id="e3b89-102">Il database di disponibilità è sospeso</span><span class="sxs-lookup"><span data-stu-id="e3b89-102">Availability database is suspended</span></span>
    
## <a name="introduction"></a><span data-ttu-id="e3b89-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="e3b89-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3b89-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="e3b89-104">**Policy Name**</span></span>|<span data-ttu-id="e3b89-105">Stato di sospensione del database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="e3b89-105">Availability Database Suspension State</span></span>|  
|<span data-ttu-id="e3b89-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="e3b89-106">**Issue**</span></span>|<span data-ttu-id="e3b89-107">Database di disponibilità sospeso.</span><span class="sxs-lookup"><span data-stu-id="e3b89-107">Availability database is suspended.</span></span>|  
|<span data-ttu-id="e3b89-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="e3b89-108">**Category**</span></span>|<span data-ttu-id="e3b89-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="e3b89-109">**Warning**</span></span>|  
|<span data-ttu-id="e3b89-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="e3b89-110">**Facet**</span></span>|<span data-ttu-id="e3b89-111">Database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="e3b89-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e3b89-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3b89-112">Description</span></span>  
 <span data-ttu-id="e3b89-113">Questi criteri consentono di controllare lo stato di spostamento dei dati del database secondario, anche noto come "replica di database secondaria".</span><span class="sxs-lookup"><span data-stu-id="e3b89-113">This policy checks the state of data movement of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="e3b89-114">I criteri sono in uno stato non integro se questo spostamento è sospeso.</span><span class="sxs-lookup"><span data-stu-id="e3b89-114">The policy is in an unhealthy state when the data movement is suspended.</span></span> <span data-ttu-id="e3b89-115">Altrimenti, sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="e3b89-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3b89-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili in [Il database di disponibilità è sospeso](https://go.microsoft.com/fwlink/p/?LinkId=220860) in TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="e3b89-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability database is suspended](https://go.microsoft.com/fwlink/p/?LinkId=220860) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="e3b89-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="e3b89-117">Possible Causes</span></span>  
 <span data-ttu-id="e3b89-118">È probabile che la sincronizzazione dei dati in questo database di disponibilità sia stata sospesa per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3b89-118">Data synchronization on this availability database might have been suspended because of the following:</span></span>  
  
-   <span data-ttu-id="e3b89-119">È probabile che la sincronizzazione dei dati sia sospesa a causa di un errore.</span><span class="sxs-lookup"><span data-stu-id="e3b89-119">Due to an error, the system might have suspended data synchronization.</span></span>  
  
-   <span data-ttu-id="e3b89-120">È probabile che l'amministratore del database abbia sospeso la sincronizzazione dei dati per scopi di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e3b89-120">The database administrator might have suspended data synchronization for maintenance purposes.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="e3b89-121">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="e3b89-121">Possible Solution</span></span>  
 <span data-ttu-id="e3b89-122">Riprendere la sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e3b89-122">Resume data synchronization.</span></span> <span data-ttu-id="e3b89-123">Se il problema persistente, controllare il gruppo di disponibilità nel Registro eventi, quindi diagnosticare il motivo per il quale lo spostamento dei dati è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="e3b89-123">If the issue persists, check the availability group in the Event log, and then diagnose why the system suspended data movement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b89-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3b89-124">See Also</span></span>  
 <span data-ttu-id="e3b89-125">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e3b89-125">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="e3b89-126">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e3b89-126">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
