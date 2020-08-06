---
title: Alcune repliche di disponibilità non stanno sincronizzando i dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp4synchronizing.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 3db6a569-e942-4321-a0dd-c4ab002087c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 762b7da1f7b8a07257c2a900307eb1bb10408653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628989"
---
# <a name="some-availability-replicas-are-not-synchronizing-data"></a><span data-ttu-id="4a20c-102">Alcune repliche di disponibilità non stanno sincronizzando i dati.</span><span class="sxs-lookup"><span data-stu-id="4a20c-102">Some availability replicas are not synchronizing data</span></span>
    
## <a name="introduction"></a><span data-ttu-id="4a20c-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="4a20c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a20c-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="4a20c-104">**Policy Name**</span></span>|<span data-ttu-id="4a20c-105">Stato di sincronizzazione dei dati delle repliche di disponibilità</span><span class="sxs-lookup"><span data-stu-id="4a20c-105">Availability Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="4a20c-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="4a20c-106">**Issue**</span></span>|<span data-ttu-id="4a20c-107">Alcune repliche di disponibilità non prevedono la sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="4a20c-107">Some availability replicas are not synchronizing data.</span></span>|  
|<span data-ttu-id="4a20c-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="4a20c-108">**Category**</span></span>|<span data-ttu-id="4a20c-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="4a20c-109">**Warning**</span></span>|  
|<span data-ttu-id="4a20c-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="4a20c-110">**Facet**</span></span>|<span data-ttu-id="4a20c-111">gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="4a20c-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4a20c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a20c-112">Description</span></span>  
 <span data-ttu-id="4a20c-113">Questi criteri consentono di eseguire il rollup dello stato di sincronizzazione dei dati di tutte le repliche di disponibilità nel gruppo di disponibilità e di verificare se la sincronizzazione di una qualsiasi replica di disponibilità non funzioni.</span><span class="sxs-lookup"><span data-stu-id="4a20c-113">This policy rolls up the data synchronization state of all availability replicas in the availability group and checks if the synchronization of any availability replica is not operational.</span></span> <span data-ttu-id="4a20c-114">I criteri si trovano in uno stato non integro se uno degli stati di sincronizzazione dei dati della replica di disponibilità è NON IN SINCRONIZZAZIONE.</span><span class="sxs-lookup"><span data-stu-id="4a20c-114">The policy is in an unhealthy state if any of the data synchronization states of the availability replica is NOT SYNCRONIZING.</span></span>  
  
 <span data-ttu-id="4a20c-115">Questi criteri sono in uno stato integro se nessuno degli stati di sincronizzazione dei dati della replica di disponibilità è NON IN SINCRONIZZAZIONE.</span><span class="sxs-lookup"><span data-stu-id="4a20c-115">This policy is in a healthy state if none of the data synchronization states of the availability replica is NOT SYNCHRONIZING.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a20c-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili in [Alcune repliche di disponibilità non stanno sincronizzando i dati](https://go.microsoft.com/fwlink/p/?LinkId=220852) nella Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="4a20c-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some availability replicas are not synchronizing data](https://go.microsoft.com/fwlink/p/?LinkId=220852) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="4a20c-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="4a20c-117">Possible Causes</span></span>  
 <span data-ttu-id="4a20c-118">In questo gruppo di disponibilità, almeno una replica secondaria non si trova nello stato di sincronizzazione NON IN SINCRONIZZAZIONE e non riceve dati dalla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="4a20c-118">In this availability group, at least one secondary replica has a NOT SYNCHRONIZING synchronization state and is not receiving data from the primary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="4a20c-119">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="4a20c-119">Possible Solution</span></span>  
 <span data-ttu-id="4a20c-120">Utilizzare lo stato dei criteri della replica di disponibilità per trovare la replica di disponibilità con uno stato NON IN SINCRONIZZAZIONE e risolvere il relativo problema.</span><span class="sxs-lookup"><span data-stu-id="4a20c-120">Use the availability replica policy state to find the availability replica with a NOT SYNCHROINIZING state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a20c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a20c-121">See Also</span></span>  
 <span data-ttu-id="4a20c-122">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4a20c-122">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="4a20c-123">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4a20c-123">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
