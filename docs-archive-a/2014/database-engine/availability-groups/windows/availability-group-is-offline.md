---
title: Il gruppo di disponibilità è offline | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp2online.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 093c5208-bf7a-49f4-a546-72b48197cadf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b25e5b22a09783c8dfcad862500b5c0dfcb2c319
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624376"
---
# <a name="availability-group-is-offline"></a><span data-ttu-id="efa76-102">Il gruppo di disponibilità è offline</span><span class="sxs-lookup"><span data-stu-id="efa76-102">Availability group is offline</span></span>
    
## <a name="introduction"></a><span data-ttu-id="efa76-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="efa76-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efa76-104">**Nome criteri**</span><span class="sxs-lookup"><span data-stu-id="efa76-104">**Policy Name**</span></span>|<span data-ttu-id="efa76-105">Stato online del gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="efa76-105">Availability Group Online State</span></span>|  
|<span data-ttu-id="efa76-106">**Problema**</span><span class="sxs-lookup"><span data-stu-id="efa76-106">**Issue**</span></span>|<span data-ttu-id="efa76-107">Il gruppo di disponibilità è offline.</span><span class="sxs-lookup"><span data-stu-id="efa76-107">Availability group is offline.</span></span>|  
|<span data-ttu-id="efa76-108">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="efa76-108">**Category**</span></span>|<span data-ttu-id="efa76-109">**Critico**</span><span class="sxs-lookup"><span data-stu-id="efa76-109">**Critical**</span></span>|  
|<span data-ttu-id="efa76-110">**Facet**</span><span class="sxs-lookup"><span data-stu-id="efa76-110">**Facet**</span></span>|<span data-ttu-id="efa76-111">gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="efa76-111">Availability group</span></span>|  
  
## <a name="description"></a><span data-ttu-id="efa76-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efa76-112">Description</span></span>  
 <span data-ttu-id="efa76-113">Questi criteri consentono di controllare lo stato online o offline del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="efa76-113">This policy checks the online or offline state of the availability group.</span></span> <span data-ttu-id="efa76-114">I criteri si trovano in uno stato non integro e viene generato un avviso quando la risorsa cluster del gruppo di disponibilità è offline o nel gruppo di disponibilità non è disponibile una replica primaria.</span><span class="sxs-lookup"><span data-stu-id="efa76-114">The policy is in an unhealthy state and an alert is raised when the cluster resource of the availability group is offline or the availability group does not have a primary replica.</span></span>  
  
 <span data-ttu-id="efa76-115">I criteri si trovano in uno stato integro quando la risorsa cluster del gruppo di disponibilità è online e nel gruppo di disponibilità è disponibile una replica primaria.</span><span class="sxs-lookup"><span data-stu-id="efa76-115">The policy state is healthy when the cluster resource of the availability group is online and the availability group has a primary replica.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="efa76-116"> Per questa versione di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], le informazioni sulle possibili cause e le soluzioni sono disponibili nella pagina relativa alla situazione in cui il [gruppo di disponibilità è offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) su Wiki di TechNet.</span><span class="sxs-lookup"><span data-stu-id="efa76-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Availability group is offline](https://go.microsoft.com/fwlink/p/?LinkId=220850) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="efa76-117">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="efa76-117">Possible Causes</span></span>  
 <span data-ttu-id="efa76-118">Questo problema può essere causato da un errore nell'istanza del server in cui è ospitata la replica primaria o dal passaggio alla modalità offline della risorsa del gruppo di disponibilità WSCF (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="efa76-118">This issue can be caused by a failure in the server instance that hosts the primary replica or by the Windows Server Failover Cluster (WSFC) availability group resource going offline.</span></span> <span data-ttu-id="efa76-119">Di seguito sono riportate le possibili cause del passaggio alla modalità offline del gruppo di disponibilità:</span><span class="sxs-lookup"><span data-stu-id="efa76-119">Following are possible causes for the availability group to be offline:</span></span>  
  
-   <span data-ttu-id="efa76-120">Il gruppo di disponibilità non è configurato con la modalità di failover automatico.</span><span class="sxs-lookup"><span data-stu-id="efa76-120">The availability group is not configured with automatic failover mode.</span></span> <span data-ttu-id="efa76-121">La replica primaria non è più disponibile e il ruolo di tutte le repliche nel gruppo di disponibilità diventa RISOLUZIONE.</span><span class="sxs-lookup"><span data-stu-id="efa76-121">The primary replica becomes unavailable and the role of all replicas in the availability group become RESOLVING.</span></span>  
  
    -   <span data-ttu-id="efa76-122">Il servizio dell'istanza della replica primaria non funziona o non risponde.</span><span class="sxs-lookup"><span data-stu-id="efa76-122">The primary replica instance service is down or unresponsive.</span></span>  
  
    -   <span data-ttu-id="efa76-123">Si è verificato un problema di connettività tra il gruppo di disponibilità e il cluster.</span><span class="sxs-lookup"><span data-stu-id="efa76-123">The availability group has a connectivity issue with the cluster.</span></span>  
  
-   <span data-ttu-id="efa76-124">Il gruppo di disponibilità è configurato con la modalità di failover automatico, ma non viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="efa76-124">The availability group is configured with automatic failover mode and does not complete successfully.</span></span>  
  
    -   <span data-ttu-id="efa76-125">Durante il failover automatico, il controllo di conformità della replica primaria nella replica di destinazione non viene eseguito correttamente e nessuna replica è disponibile a diventare la nuova primaria.</span><span class="sxs-lookup"><span data-stu-id="efa76-125">During the automatic failover, the primary readiness check on the target replica fails, and there is no replica available to become the new primary.</span></span>  
  
-   <span data-ttu-id="efa76-126">La risorsa del gruppo di disponibilità nel cluster passa alla modalità offline.</span><span class="sxs-lookup"><span data-stu-id="efa76-126">The availability group resource in the cluster becomes offline.</span></span>  
  
    -   <span data-ttu-id="efa76-127">Si verifica un problema grave in qualsiasi risorsa cluster dipendente che ne determina il passaggio alla modalità offline.</span><span class="sxs-lookup"><span data-stu-id="efa76-127">Any dependent cluster resource encounters a critical issue and becomes offline.</span></span> <span data-ttu-id="efa76-128">La risorsa del gruppo di disponibilità è offline finché la risorsa dipendente non passa alla modalità online.</span><span class="sxs-lookup"><span data-stu-id="efa76-128">The availability group resource is also offline until the dependent resource becomes online.</span></span>  
  
    -   <span data-ttu-id="efa76-129">Un problema grave nel cluster determina la disabilitazione della risorsa del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="efa76-129">A critical issue in the cluster turns off the availability group resource.</span></span>  
  
-   <span data-ttu-id="efa76-130">È in corso un failover automatico, manuale o forzato per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="efa76-130">There is an automatic, manual, or forced failover in progress for the availability group.</span></span>  
  
## <a name="possible-solutions"></a><span data-ttu-id="efa76-131">Possibili soluzioni</span><span class="sxs-lookup"><span data-stu-id="efa76-131">Possible Solutions</span></span>  
 <span data-ttu-id="efa76-132">Di seguito sono riportate le possibili soluzioni a questo problema:</span><span class="sxs-lookup"><span data-stu-id="efa76-132">Following are possible solutions for this issue:</span></span>  
  
-   <span data-ttu-id="efa76-133">Se l'istanza di SQL Server della replica primaria non è attiva, riavviare il server, quindi verificare che venga recuperato uno stato integro per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="efa76-133">If the SQL Server instance of the primary replica is down, restart the server and then verify that the availability group recovers to a healthy state.</span></span>  
  
-   <span data-ttu-id="efa76-134">Se sembra che il failover automatico non sia stato completato correttamente, verificare che i database della replica siano sincronizzati con la replica primaria nota in precedenza, quindi eseguire il failover alla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="efa76-134">If the automatic failover appears to have failed, verify that the databases on the replica are synchronized with the previously known primary replica, and then failover to the primary replica.</span></span> <span data-ttu-id="efa76-135">Se i database non sono sincronizzati, selezionare una replica con una perdita minima di dati, quindi recuperare alla modalità failover.</span><span class="sxs-lookup"><span data-stu-id="efa76-135">If the databases are not synchronized, select a replica with a minimum loss of data, and then recover to failover mode.</span></span>  
  
-   <span data-ttu-id="efa76-136">Se la risorsa nel cluster è offline mentre le istanze di SQL Server sembrano essere integre, utilizzare Gestione cluster di failover per controllare l'integrità del cluster o altri problemi del cluster nel server.</span><span class="sxs-lookup"><span data-stu-id="efa76-136">If the resource in the cluster is offline while the instances of SQL Server appear to be healthy, use Failover Cluster Manager to check the cluster health or other cluster issues on the server.</span></span> <span data-ttu-id="efa76-137">Gestione cluster di failover può essere utilizzato anche per tentare di portare online la risorsa del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="efa76-137">You can also use the Failover Cluster Manager to attempt to turn the availability group resource online.</span></span>  
  
-   <span data-ttu-id="efa76-138">Se è in corso un failover, attenderne il completamento.</span><span class="sxs-lookup"><span data-stu-id="efa76-138">If there is a failover in progress, wait for the failover to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa76-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efa76-139">See Also</span></span>  
 <span data-ttu-id="efa76-140">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="efa76-140">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="efa76-141">Usare il Dashboard Always On &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="efa76-141">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
