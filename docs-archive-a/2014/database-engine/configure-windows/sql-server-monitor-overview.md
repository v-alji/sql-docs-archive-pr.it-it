---
title: Panoramica di Monitoraggio SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlservermonitor.main.f1
helpviewer_keywords:
- SQL Server Monitor [SQL Server]
ms.assetid: 048ae16d-31c3-489a-9f1e-1400a3bacd39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab90186ed493e616e672cfacf881fd61be166f88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624339"
---
# <a name="sql-server-monitor-overview"></a><span data-ttu-id="89ffd-102">Panoramica di Monitoraggio SQL Server</span><span class="sxs-lookup"><span data-stu-id="89ffd-102">SQL Server Monitor Overview</span></span>
  <span data-ttu-id="89ffd-103">In Monitoraggio SQL Server non sono disponibili funzioni di monitoraggio, ma moduli che consentono di effettuare tale operazione.</span><span class="sxs-lookup"><span data-stu-id="89ffd-103">SQL Server Monitor does not perform monitoring functions, but it hosts modules that do.</span></span> <span data-ttu-id="89ffd-104">Nei moduli di Monitoraggio SQL Server sono inclusi Monitoraggio replica e Monitoraggio mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="89ffd-104">The SQL Server Monitor modules include Replication Monitor and Database Mirroring Monitor.</span></span>  
  
 <span data-ttu-id="89ffd-105">Per usare uno di questi moduli, selezionarlo dal menu **Go** .</span><span class="sxs-lookup"><span data-stu-id="89ffd-105">To use one of these modules, select that module on the **Go** menu.</span></span> <span data-ttu-id="89ffd-106">Il modulo attualmente selezionato controlla il contenuto dei riquadri di navigazione e dei dettagli, l'interazione dell'utente nei riquadri dei dettagli e le query relative a contenuto e stato.</span><span class="sxs-lookup"><span data-stu-id="89ffd-106">The currently selected module owns the content of the navigation and detail panes, user interaction in the detail panes, and the queries for content and status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89ffd-107">Per altre informazioni su questi monitoraggi, vedere [Monitoraggio della replica](../../relational-databases/replication/monitoring-replication.md) e [Monitoraggio del mirroring del database &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="89ffd-107">For more information about these monitors, see [Monitoring Replication](../../relational-databases/replication/monitoring-replication.md) and [Monitoring Database Mirroring &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="89ffd-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="89ffd-108">Permissions</span></span>  
  
-   <span data-ttu-id="89ffd-109">Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="89ffd-109">Replication Monitor</span></span>  
  
     <span data-ttu-id="89ffd-110">Per monitorare la replica, è necessaria l'assegnazione al ruolo predefinito del server **sysadmin** per il server di distribuzione o l'assegnazione al ruolo predefinito del database **replmonitor** nel database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="89ffd-110">To monitor replication, you must be a member of the **sysadmin** fixed server role at the Distributor or a member of the **replmonitor** fixed database role in the distribution database.</span></span> <span data-ttu-id="89ffd-111">Un amministratore di sistema può aggiungere qualsiasi utente al ruolo **replmonitor** , consentendo a tale utente di visualizzare l'attività di replica in Monitoraggio replica, ma non di amministrare la replica.</span><span class="sxs-lookup"><span data-stu-id="89ffd-111">A system administrator can add any user to the **replmonitor** role, which allows that user to view replication activity in Replication Monitor; however, the user cannot administer replication.</span></span>  
  
-   <span data-ttu-id="89ffd-112">Monitoraggio mirroring del database</span><span class="sxs-lookup"><span data-stu-id="89ffd-112">Database Mirroring Monitor</span></span>  
  
     <span data-ttu-id="89ffd-113">Per monitorare il mirroring del database, è necessaria l'assegnazione al ruolo predefinito del server **sysadmin** o l'assegnazione al ruolo predefinito del database **dbm_monitor** nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="89ffd-113">To monitor database mirroring, you must be a member of either the **sysadmin** fixed server role or the **dbm_monitor** fixed database role on the server instance.</span></span> <span data-ttu-id="89ffd-114">Se l'utente è membro di **sysadmin** o di **dbm_monitor** in una sola delle istanze del server partner, il monitoraggio può connettersi solo a tale partner e non è in grado di recuperare informazioni dall'altro partner.</span><span class="sxs-lookup"><span data-stu-id="89ffd-114">If you are a member of **sysadmin** or **dbm_monitor** on only one of the partner server instances, the monitor can connect only to that partner; the monitor cannot retrieve information from the other partner.</span></span> <span data-ttu-id="89ffd-115">Per altre informazioni, vedere [Panoramica di Monitoraggio mirroring del database](../database-mirroring/database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="89ffd-115">For more information, see [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="menu-options"></a><span data-ttu-id="89ffd-116">Opzioni di menu</span><span class="sxs-lookup"><span data-stu-id="89ffd-116">Menu Options</span></span>  
 <span data-ttu-id="89ffd-117">Monitoraggio SQL Server ha un menu che include comandi relativi a Monitoraggio SQL Server stesso.</span><span class="sxs-lookup"><span data-stu-id="89ffd-117">SQL Server Monitor has a menu that contains commands that pertain to SQL Server Monitor.</span></span> <span data-ttu-id="89ffd-118">Il menu può inoltre includere comandi relativi al modulo selezionato.</span><span class="sxs-lookup"><span data-stu-id="89ffd-118">This menu may also contain commands from the selected module.</span></span>  
  
 <span data-ttu-id="89ffd-119">Le opzioni di menu seguenti sono relative a Monitoraggio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89ffd-119">The following menu options pertain to SQL Server Monitor.</span></span>  
  
 <span data-ttu-id="89ffd-120">**File**</span><span class="sxs-lookup"><span data-stu-id="89ffd-120">**File**</span></span>  
 <span data-ttu-id="89ffd-121">Questo menu include il comando **Esci** .</span><span class="sxs-lookup"><span data-stu-id="89ffd-121">This menu contains the **Exit** command.</span></span>  
  
 <span data-ttu-id="89ffd-122">**Azione**</span><span class="sxs-lookup"><span data-stu-id="89ffd-122">**Action**</span></span>  
 <span data-ttu-id="89ffd-123">Include il menu di scelta rapida del nodo selezionato nell'albero di navigazione.</span><span class="sxs-lookup"><span data-stu-id="89ffd-123">Contains the context menu of the node selected in the navigation tree.</span></span>  
  
 <span data-ttu-id="89ffd-124">**Go**</span><span class="sxs-lookup"><span data-stu-id="89ffd-124">**Go**</span></span>  
 <span data-ttu-id="89ffd-125">Include un elenco dei componenti di monitoraggio:</span><span class="sxs-lookup"><span data-stu-id="89ffd-125">Contains a list of monitoring components:</span></span>  
  
-   <span data-ttu-id="89ffd-126">Mirroring del database</span><span class="sxs-lookup"><span data-stu-id="89ffd-126">Database Mirroring</span></span>  
  
-   <span data-ttu-id="89ffd-127">Replica</span><span class="sxs-lookup"><span data-stu-id="89ffd-127">Replication</span></span>  
  
 <span data-ttu-id="89ffd-128">**Per utilizzare SQL Server Management Studio per il monitoraggio del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="89ffd-128">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="89ffd-129">Avviare il monitoraggio mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="89ffd-129">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="89ffd-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89ffd-130">See Also</span></span>  
 [<span data-ttu-id="89ffd-131">Monitoraggio del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89ffd-131">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-sql-server.md)  
  
  
