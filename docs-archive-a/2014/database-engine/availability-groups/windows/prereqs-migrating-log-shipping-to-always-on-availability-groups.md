---
title: Prerequisiti per la migrazione dal log shipping al Gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 2738ce65-205e-4682-92d8-dc7e37c58b2b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 76b50d5af8eb520b3764ff56397c040f2d0d0141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718726"
---
# <a name="prerequisites-for-migrating-from-log-shipping-to-alwayson-availability-groups-sql-server"></a><span data-ttu-id="cb8ba-102">Prerequisiti per la migrazione dal log shipping ai gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cb8ba-102">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="cb8ba-103">In questo argomento vengono descritti i prerequisiti per convertire un database primario per il log shipping insieme a uno o più dei relativi database secondari in un database primario AlwaysOn e nei relativi database secondari.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-103">This topic describes the prerequisites for converting a log shipping primary database along with one or more of its secondary databases to an AlwaysOn primary database and secondary database(s).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb8ba-104">In un gruppo di disponibilità è possibile configurare qualsiasi database primario o secondario (possibilmente leggibile) come un database primario per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-104">You can configure any primary or secondary database (possibly readable) in an availability group as a log shipping primary database.</span></span>  
  
 <span data-ttu-id="cb8ba-105">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="cb8ba-105">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="cb8ba-106">Prerequisiti dei gruppi di disponibilità</span><span class="sxs-lookup"><span data-stu-id="cb8ba-106">Availability Group Prerequisites</span></span>](#AGPrereqsRealAddress)  
  
-   [<span data-ttu-id="cb8ba-107">Prerequisiti per il log shipping</span><span class="sxs-lookup"><span data-stu-id="cb8ba-107">Log Shipping Prerequisites</span></span>](#LogShipPrereqs)  
  
-   [<span data-ttu-id="cb8ba-108">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="cb8ba-108">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="cb8ba-109">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="cb8ba-109">Related Content</span></span>](#RelatedContent)  
  
##  <a name="availability-group-prerequisites"></a><a name="AGPrereqsRealAddress"></a><span data-ttu-id="cb8ba-110">Prerequisiti del gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="cb8ba-110">Availability Group Prerequisites</span></span>  
 <span data-ttu-id="cb8ba-111">Per consentire l'esecuzione dei processi di backup sulla replica primaria del gruppo di disponibilità, utilizzare le seguenti impostazioni per i gruppi di disponibilità AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="cb8ba-111">To allow backup jobs to run on the primary replica of the availability group, use the following AlwaysOn Availability Groups backup settings:</span></span>  
  
|<span data-ttu-id="cb8ba-112">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cb8ba-112">Property</span></span>|<span data-ttu-id="cb8ba-113">Impostazione</span><span class="sxs-lookup"><span data-stu-id="cb8ba-113">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="cb8ba-114">Preferenza di backup automatico del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-114">Automated backup preference of availability group</span></span>|<span data-ttu-id="cb8ba-115">Solo nella replica primaria</span><span class="sxs-lookup"><span data-stu-id="cb8ba-115">Only on the primary replica</span></span>|  
|<span data-ttu-id="cb8ba-116">Priorità di backup della replica primaria.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-116">Backup priority of the primary replica.</span></span>|<span data-ttu-id="cb8ba-117">>0</span><span class="sxs-lookup"><span data-stu-id="cb8ba-117">>0</span></span>|  
  
 <span data-ttu-id="cb8ba-118">**Per ulteriori informazioni:**</span><span class="sxs-lookup"><span data-stu-id="cb8ba-118">**For more information:**</span></span>  
  
 [<span data-ttu-id="cb8ba-119">Visualizzazione delle Proprietà dei gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-119">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
 [<span data-ttu-id="cb8ba-120">Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-120">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="log-shipping-prerequisites"></a><a name="LogShipPrereqs"></a> <span data-ttu-id="cb8ba-121">Prerequisiti per il log shipping</span><span class="sxs-lookup"><span data-stu-id="cb8ba-121">Log Shipping Prerequisites</span></span>  
  
-   <span data-ttu-id="cb8ba-122">È necessario che il database primario per il log shipping risieda nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che ospita la replica primaria iniziale/corrente del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-122">The log shipping primary database must reside on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the initial/current primary replica of the availability group.</span></span>  
  
-   <span data-ttu-id="cb8ba-123">Per fare in modo che un determinato database secondario per il log shipping venga convertito in un database secondario AlwaysOn, tale database dovrà:</span><span class="sxs-lookup"><span data-stu-id="cb8ba-123">For a given log shipping secondary database to be converted to an AlwaysOn secondary database, it must:</span></span>  
  
    -   <span data-ttu-id="cb8ba-124">Utilizzare lo stesso nome del database primario.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-124">Use the same name as the primary database.</span></span>  
  
    -   <span data-ttu-id="cb8ba-125">Risiedere su un'istanza del server in cui viene ospitata una replica secondaria del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-125">Reside on a server instance that hosts a secondary replica for the availability group.</span></span>  
  
 <span data-ttu-id="cb8ba-126">Dopo l'esecuzione del processo di backup sul database primario, disabilitare il processo di backup e al termine dell'esecuzione del processo di ripristino su un determinato database secondario, disabilitare il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-126">Once the backup job has run on the primary database, disable the backup job, and once the restore job has run on a given secondary database, disable the restore job.</span></span>  
  
 <span data-ttu-id="cb8ba-127">Dopo avere creato tutti i database secondari per il gruppo di disponibilità, se si desidera eseguire backup sulle repliche secondarie, è necessario configurare nuovamente la preferenza di backup automatico del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="cb8ba-127">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you need to re-configure the automated backup preference of the availability group.</span></span>  
  
 <span data-ttu-id="cb8ba-128">**Per ulteriori informazioni:**</span><span class="sxs-lookup"><span data-stu-id="cb8ba-128">**For more information:**</span></span>  
  
 <span data-ttu-id="cb8ba-129">[Converting a logshipping configuration to Availability Group](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (Conversione di una configurazione per il log shipping in un gruppo di disponibilità) (blog su SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cb8ba-129">[Converting a logshipping configuration to Availability Group](https://blogs.msdn.com/b/sqlalwayson/archive/2012/01/09/converting-a-logshipping-configuration-to-availability-group.aspx) (a SQL Server blog)</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cb8ba-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="cb8ba-130">Related Tasks</span></span>  
 <span data-ttu-id="cb8ba-131">**Log shipping**</span><span class="sxs-lookup"><span data-stu-id="cb8ba-131">**Log shipping**</span></span>  
  
-   [<span data-ttu-id="cb8ba-132">Aggiornare il log shipping a SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-132">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](../../log-shipping/upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="cb8ba-133">Rimuovere il log shipping &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-133">Remove Log Shipping &#40;SQL Server&#41;</span></span>](../../log-shipping/remove-log-shipping-sql-server.md)  
  
 <span data-ttu-id="cb8ba-134">**Gruppi di disponibilità AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="cb8ba-134">**AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="cb8ba-135">Usare la Creazione guidata Gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-135">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="cb8ba-136">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-136">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="cb8ba-137">Creare un gruppo di disponibilità &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-137">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="cb8ba-138">Creare un gruppo di disponibilità &#40;PowerShell SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-138">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="cb8ba-139">Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-139">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="cb8ba-140">Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-140">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="cb8ba-141">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="cb8ba-141">Related Content</span></span>  
  
-   <span data-ttu-id="cb8ba-142">**Blog:**</span><span class="sxs-lookup"><span data-stu-id="cb8ba-142">**Blogs:**</span></span>  
  
     [<span data-ttu-id="cb8ba-143">Conversione di una configurazione per il log shipping in un gruppo di disponibilità</span><span class="sxs-lookup"><span data-stu-id="cb8ba-143">Converting a logshipping configuration to Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/converting-a-logshipping-configuration-to-availability-group)  
  
     [<span data-ttu-id="cb8ba-144">Pagina relativa all'aggiunta di un database primario e di database secondari per il log shipping in un gruppo di disponibilità esistente</span><span class="sxs-lookup"><span data-stu-id="cb8ba-144">Add a Log Shipping Primary Database and Secondary Database(s) to an Existing Availability Group</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/add-a-log-shipping-primary-database-and-secondary-databases-to-an-existing-availability-group)  
  
     [<span data-ttu-id="cb8ba-145">Blog del team di SQL Server AlwaysOn: Blog ufficiale del team di SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="cb8ba-145">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/)  
  
     [<span data-ttu-id="cb8ba-146">Pagina relativa ai blog del Servizio Supporto Tecnico Clienti per gli ingegneri di SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb8ba-146">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="cb8ba-147">**White paper:**</span><span class="sxs-lookup"><span data-stu-id="cb8ba-147">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="cb8ba-148">Pagina relativa alla guida alla migrazione in cui viene illustrata la migrazione in gruppi di disponibilità AlwaysOn da distribuzioni precedenti in cui vengono combinati il mirroring del database e il log shipping</span><span class="sxs-lookup"><span data-stu-id="cb8ba-148">Migration Guide: Migrating to AlwaysOn Availability Groups from Prior Deployments Combining Database Mirroring and Log Shipping</span></span>](https://msdn.microsoft.com/library/jj635217)  
  
     [<span data-ttu-id="cb8ba-149">Pagina relativa ai white paper Microsoft per SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="cb8ba-149">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="cb8ba-150">Pagina relativa ai white paper del team di consulenza clienti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb8ba-150">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="cb8ba-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb8ba-151">See Also</span></span>  
 <span data-ttu-id="cb8ba-152">[Informazioni sul log shipping &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cb8ba-152">[About Log Shipping &#40;SQL Server&#41;](../../log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="cb8ba-153">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cb8ba-153">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="cb8ba-154">Monitoraggio di Gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb8ba-154">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
