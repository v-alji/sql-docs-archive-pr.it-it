---
title: Lo stato di sincronizzazione dei dati di alcuni database di disponibilità non è integro | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp3datasynchealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 89f95d15-33c6-4768-bccd-9dbf8c4f49a9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 221f25a1ee7e4a8719acc133372c742ca4a79303
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727116"
---
# <a name="data-synchronization-state-of-some-availability-database-is-not-healthy"></a><span data-ttu-id="658dd-102">Lo stato della sincronizzazione dei dati di alcuni database disponibili non è integro</span><span class="sxs-lookup"><span data-stu-id="658dd-102">Data synchronization state of some availability database is not healthy</span></span>
    
## <a name="introduction"></a><span data-ttu-id="658dd-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="658dd-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="658dd-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="658dd-104">**Policy Name**</span></span>|<span data-ttu-id="658dd-105">Stato di sincronizzazione dei dati delle repliche di disponibilità</span><span class="sxs-lookup"><span data-stu-id="658dd-105">Availability Replica Data Synchronization State</span></span>|  
|<span data-ttu-id="658dd-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="658dd-106">**Issue**</span></span>|<span data-ttu-id="658dd-107">Lo stato di sincronizzazione dei dati di alcuni database di disponibilità non è integro.</span><span class="sxs-lookup"><span data-stu-id="658dd-107">Data synchronization state of some availability database is not healthy.</span></span>|  
|<span data-ttu-id="658dd-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="658dd-108">**Category**</span></span>|<span data-ttu-id="658dd-109">**Warning**</span><span class="sxs-lookup"><span data-stu-id="658dd-109">**Warning**</span></span>|  
|<span data-ttu-id="658dd-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="658dd-110">**Facet**</span></span>|<span data-ttu-id="658dd-111">replica di disponibilità</span><span class="sxs-lookup"><span data-stu-id="658dd-111">Availability replica</span></span>|  
  
## <a name="description"></a><span data-ttu-id="658dd-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="658dd-112">Description</span></span>  
 <span data-ttu-id="658dd-113">Questi criteri consentono di controllare lo stato di sincronizzazione dei dati del database di disponibilità, anche noto come "replica di database".</span><span class="sxs-lookup"><span data-stu-id="658dd-113">This policy checks the data synchronization state of the availability database (also known as a "database replica").</span></span> <span data-ttu-id="658dd-114">I criteri sono in uno stato non integro se lo stato di sincronizzazione dei dati è NON IN SINCRONIZZAZIONE o lo stato per la replica del database con commit sincrono è NON SINCRONIZZATO.</span><span class="sxs-lookup"><span data-stu-id="658dd-114">The policy is in an unhealthy state when the data synchronization state is NOT SYNCHRONIZING or the state is not SYNCHRONIZED for the synchronous-commit database replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="658dd-115">Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili in [Lo stato della sincronizzazione dei dati del database di disponibilità non è integro](https://go.microsoft.com/fwlink/p/?LinkId=220863) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="658dd-115">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Data synchronization state of availability database is not healthy](https://go.microsoft.com/fwlink/p/?LinkId=220863) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="658dd-116">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="658dd-116">Possible Causes</span></span>  
 <span data-ttu-id="658dd-117">Almeno un database di disponibilità in questa replica di disponibilità si trova in uno stato di sincronizzazione dei dati non integro.</span><span class="sxs-lookup"><span data-stu-id="658dd-117">At least one availability database on the replica has an unhealthy data synchronization state.</span></span> <span data-ttu-id="658dd-118">Se si tratta di una replica di disponibilità con commit asincrono, tutti i database di disponibilità devono trovarsi nello stato SINCRONIZZAZIONE IN CORSO.</span><span class="sxs-lookup"><span data-stu-id="658dd-118">If this is an asynchronous-commit availability replica, all availability databases should be in the SYNCHRONIZING state.</span></span> <span data-ttu-id="658dd-119">Se invece si tratta di una replica di disponibilità con commit sincrono, tutti i database di disponibilità devono trovarsi nello stato SINCRONIZZATO.</span><span class="sxs-lookup"><span data-stu-id="658dd-119">If this is a synchronous-commit availability replica, all availability databases should be in the SYNCHRONIZED state.</span></span> <span data-ttu-id="658dd-120">Il problema può essere causato da uno dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="658dd-120">This issue can be caused by the following:</span></span>  
  
-   <span data-ttu-id="658dd-121">La replica di disponibilità potrebbe essere disconnessa.</span><span class="sxs-lookup"><span data-stu-id="658dd-121">The availability replica might be disconnected.</span></span>  
  
-   <span data-ttu-id="658dd-122">Lo spostamento di dati potrebbe essere sospeso.</span><span class="sxs-lookup"><span data-stu-id="658dd-122">The data movement might be suspended.</span></span>  
  
-   <span data-ttu-id="658dd-123">Il database potrebbe non essere accessibile.</span><span class="sxs-lookup"><span data-stu-id="658dd-123">The database might not be accessible.</span></span>  
  
-   <span data-ttu-id="658dd-124">Potrebbe verificarsi un problema di ritardo temporaneo dovuto alla latenza di rete o al carico nella replica primaria o secondaria.</span><span class="sxs-lookup"><span data-stu-id="658dd-124">There might be a temporary delay issue due to network latency or the load on the primary or secondary replica.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="658dd-125">Possibile soluzione</span><span class="sxs-lookup"><span data-stu-id="658dd-125">Possible Solution</span></span>  
 <span data-ttu-id="658dd-126">Risolvere tutti i problemi di connessione o di spostamento di dati sospesi.</span><span class="sxs-lookup"><span data-stu-id="658dd-126">Resolve any connection or data movement suspend issues.</span></span> <span data-ttu-id="658dd-127">Verificare gli eventi relativi a questo problema utilizzando SQL Server Management Studio e trovare l'errore di database.</span><span class="sxs-lookup"><span data-stu-id="658dd-127">Check the events for this issue using SQL Server Management Studio, and find the database error.</span></span> <span data-ttu-id="658dd-128">Seguire le procedure per la risoluzione dei problemi per l'errore specifico.</span><span class="sxs-lookup"><span data-stu-id="658dd-128">Follow the troubleshooting steps for the specific error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658dd-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="658dd-129">See Also</span></span>  
 <span data-ttu-id="658dd-130">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="658dd-130">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="658dd-131">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="658dd-131">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
