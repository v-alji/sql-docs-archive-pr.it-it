---
title: Lo stato di sincronizzazione dei dati del database di disponibilità non è integro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.arp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 4fd003e7-808e-4b0e-b28a-47d9f2616f06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a179008c20b108a2f6aaefd5dd80b22708e94a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727127"
---
# <a name="data-synchronization-state-of-availability-database-is-not-healthy"></a><span data-ttu-id="e9c0c-102">Lo stato della sincronizzazione dei dati del database di disponibilità non è integro</span><span class="sxs-lookup"><span data-stu-id="e9c0c-102">Data synchronization state of availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="e9c0c-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="e9c0c-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9c0c-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="e9c0c-104">**Policy Name**</span></span>|<span data-ttu-id="e9c0c-105">Stato di sincronizzazione dei dati del database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="e9c0c-105">Availability Database Data Synchronization State</span></span>|  
|<span data-ttu-id="e9c0c-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="e9c0c-106">**Issue**</span></span>|<span data-ttu-id="e9c0c-107">Lo stato di sincronizzazione dei dati del database di disponibilità non è integro.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-107">Data synchronization state of availability database is not healthy.</span></span>|  
|<span data-ttu-id="e9c0c-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="e9c0c-108">**Category**</span></span>|<span data-ttu-id="e9c0c-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="e9c0c-109">**Warning**</span></span>|  
|<span data-ttu-id="e9c0c-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="e9c0c-110">**Facet**</span></span>|<span data-ttu-id="e9c0c-111">Database di disponibilità</span><span class="sxs-lookup"><span data-stu-id="e9c0c-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e9c0c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9c0c-112">Description</span></span>  
 <span data-ttu-id="e9c0c-113">Questi criteri consentono di eseguire il rollup dello stato di sincronizzazione dei dati di tutti i database di disponibilità, anche noti come "repliche di disponibilità", nella replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-113">This policy rolls up the data synchronization state of all availability databases (also known as "database replicas") in the availability replica.</span></span> <span data-ttu-id="e9c0c-114">I criteri sono in uno stato non integro se una qualsiasi replica del database non è nello stato di sincronizzazione dei dati previsto.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-114">The policy is in an unhealthy sate when any database replica is not in the expected data synchronization state.</span></span> <span data-ttu-id="e9c0c-115">Altrimenti, sono in uno stato integro.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9c0c-116">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa allo [stato di sincronizzazione non integro dei dati di alcuni database di disponibilità](https://go.microsoft.com/fwlink/p/?LinkId=220858) su TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of some availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220858) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="e9c0c-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="e9c0c-117">Possible Causes</span></span>  
 <span data-ttu-id="e9c0c-118">Lo stato di sincronizzazione dei dati di questo database di disponibilità non è integro.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-118">The data synchronization state of this availability database is unhealthy.</span></span> <span data-ttu-id="e9c0c-119">In una replica di disponibilità con commit asincrono, ogni database di disponibilità deve trovarsi nello stato SINCRONIZZAZIONE IN CORSO.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-119">On an asynchronous-commit availability replica, every availability database should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="e9c0c-120">In una replica con commit sincrono, ogni database di disponibilità deve trovarsi nello stato SINCRONIZZATO.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-120">On a synchronous-commit replica, every availability database must be in the SYNCHRONIZED state.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="e9c0c-121">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="e9c0c-121">Possible Solution</span></span>  
 <span data-ttu-id="e9c0c-122">Utilizzare i criteri della replica del database per trovare la replica del database con uno stato di sincronizzazione dei dati non integro e risolvere il relativo problema.</span><span class="sxs-lookup"><span data-stu-id="e9c0c-122">Use the database replica policy to find the database replica with an unhealthy data synchronization state, and then resolve the issue at the database replica.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c0c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9c0c-123">See Also</span></span>  
 <span data-ttu-id="e9c0c-124">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e9c0c-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="e9c0c-125">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e9c0c-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
