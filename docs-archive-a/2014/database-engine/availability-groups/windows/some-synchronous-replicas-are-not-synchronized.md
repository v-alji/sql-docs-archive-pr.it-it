---
title: Alcune repliche sincrone non sono sincronizzate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp5synchronized.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: e58ed56e-4c30-42e6-a9fc-a8c401620e02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecef2d16e80e128834a71e1f1f112096f8ccc9cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628983"
---
# <a name="some-synchronous-replicas-are-not-synchronized"></a><span data-ttu-id="bbe2e-102">Alcune repliche sincrone non sono sincronizzate</span><span class="sxs-lookup"><span data-stu-id="bbe2e-102">Some synchronous replicas are not synchronized</span></span>
    
## <a name="introduction"></a><span data-ttu-id="bbe2e-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="bbe2e-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbe2e-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="bbe2e-104">**Policy Name**</span></span>|<span data-ttu-id="bbe2e-105">Stato di sincronizzazione dei dati delle repliche sincrone</span><span class="sxs-lookup"><span data-stu-id="bbe2e-105">Synchronous Replicas Data Synchronization State</span></span>|  
|<span data-ttu-id="bbe2e-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="bbe2e-106">**Issue**</span></span>|<span data-ttu-id="bbe2e-107">Alcune repliche sincrone non sono sincronizzate.</span><span class="sxs-lookup"><span data-stu-id="bbe2e-107">Some synchronous replicas are not synchronized.</span></span>|  
|<span data-ttu-id="bbe2e-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="bbe2e-108">**Category**</span></span>|<span data-ttu-id="bbe2e-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="bbe2e-109">**Warning**</span></span>|  
|<span data-ttu-id="bbe2e-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="bbe2e-110">**Facet**</span></span>|<span data-ttu-id="bbe2e-111">gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="bbe2e-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bbe2e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbe2e-112">Description</span></span>  
 <span data-ttu-id="bbe2e-113">Questi criteri consentono di eseguire il rollup dello stato di sincronizzazione dei dati di tutte le repliche di disponibilità e di verificare tutte le repliche di disponibilità che non sono nello stato di sincronizzazione previsto.</span><span class="sxs-lookup"><span data-stu-id="bbe2e-113">This policy rolls up the data synchronization state of all availability replicas and checks for any availability replicas that are not in the expected synchronization state.</span></span> <span data-ttu-id="bbe2e-114">I criteri sono in uno stato non integro se una replica asincrona è in uno stato NON IN SINCRONIZZAZIONE e una replica sincrona è in uno stato NON SINCRONIZZATO.</span><span class="sxs-lookup"><span data-stu-id="bbe2e-114">The policy is in an unhealthy state when any asynchronous replica is not in a SYNCHRONIZING state and any synchronous replica is not in a SYNCHRONIZED state.</span></span> <span data-ttu-id="bbe2e-115">Altrimenti, i criteri sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="bbe2e-115">The policy state is otherwise healthy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbe2e-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa ad [alcune repliche sincrone non sono sincronizzate](https://go.microsoft.com/fwlink/p/?LinkId=220853) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="bbe2e-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Some synchronous replicas are not synchronized](https://go.microsoft.com/fwlink/p/?LinkId=220853) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="bbe2e-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="bbe2e-117">Possible Causes</span></span>  
 <span data-ttu-id="bbe2e-118">In questo gruppo di disponibilità, almeno una replica sincrona non è attualmente sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="bbe2e-118">In this availability group, at least one synchronous replica is not currently synchronized.</span></span> <span data-ttu-id="bbe2e-119">Lo stato di sincronizzazione della replica potrebbe essere SINCRONIZZAZIONE IN CORSO o NON IN SINCRONIZZAZIONE.</span><span class="sxs-lookup"><span data-stu-id="bbe2e-119">The replica synchronization state could be either SYNCHONIZING or NOT SYNCHRONIZING.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="bbe2e-120">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="bbe2e-120">Possible Solution</span></span>  
 <span data-ttu-id="bbe2e-121">Utilizzare lo stato dei criteri della replica di disponibilità per trovare quella con lo stato di sincronizzazione non corretto e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="bbe2e-121">Use the availability replica policy state to find the availability replica with the incorrect synchronization state, and then resolve the issue at the availability replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe2e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbe2e-122">See Also</span></span>  
 <span data-ttu-id="bbe2e-123">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bbe2e-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="bbe2e-124">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="bbe2e-124">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
