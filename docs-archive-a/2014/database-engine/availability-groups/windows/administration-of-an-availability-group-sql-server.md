---
title: Amministrazione di un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], managing
ms.assetid: 0b7542fa-235e-413d-81bf-3eff9ee07480
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2cac9a34fe71c11f71ec47bbb6d690199869fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624961"
---
# <a name="administration-of-an-availability-group-sql-server"></a><span data-ttu-id="19590-102">Amministrazione di un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="19590-102">Administration of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="19590-103">La gestione di un gruppo di disponibilità AlwaysOn esistente in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] prevede una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="19590-103">Managing an existing AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] involves one or more of the following tasks:</span></span>  
  
-   <span data-ttu-id="19590-104">Modifica delle proprietà di una replica di disponibilità esistente, ad esempio per modificare l'accesso della connessione client (per la configurazione di repliche secondarie leggibili), attraverso la modifica della modalità di failover, della modalità di disponibilità o dell'impostazione del timeout di sessione.</span><span class="sxs-lookup"><span data-stu-id="19590-104">Altering the properties of an existing availability replica, for example to change client connection access (for configuring readable secondary replicas), changing its failover mode, availability mode, or session timeout setting.</span></span>  
  
-   <span data-ttu-id="19590-105">Aggiunta o rimozione di repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="19590-105">Adding or removing secondary replicas.</span></span>  
  
-   <span data-ttu-id="19590-106">Aggiunta o rimozione di un database.</span><span class="sxs-lookup"><span data-stu-id="19590-106">Adding or removing a database.</span></span>  
  
-   <span data-ttu-id="19590-107">Sospensione o ripresa di un database.</span><span class="sxs-lookup"><span data-stu-id="19590-107">Suspending or resuming a database.</span></span>  
  
-   <span data-ttu-id="19590-108">Esecuzione di un failover manuale pianificato ( *failover manuale*) o di un failover manuale forzato ( *failover forzato*).</span><span class="sxs-lookup"><span data-stu-id="19590-108">Performing a planned manual failover (a *manual failover*) or a forced manual failover (a *forced failover*).</span></span>  
  
-   <span data-ttu-id="19590-109">Creazione o configurazione di un listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="19590-109">Creating or configuring an availability group listener.</span></span>  
  
-   <span data-ttu-id="19590-110">Gestione di [repliche secondarie leggibili](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) per un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="19590-110">Managing [readable secondary replicas](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="19590-111">Tale attività implica la configurazione di una o più repliche per l'accesso in sola lettura quando vengono eseguite nel ruolo secondario e la configurazione del routing di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="19590-111">This involves configuring one or more replicas to read-only access when running under the secondary role, and configuring read-only routing.</span></span>  
  
-   <span data-ttu-id="19590-112">Gestione di [backup in repliche secondarie](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) per un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="19590-112">Managing [backups on secondary replicas](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md) for a given availability group.</span></span> <span data-ttu-id="19590-113">Tale attività implica la configurazione del percorso di esecuzione dei processi di backup e quindi la creazione di script dei processi di backup per implementare le preferenze di backup.</span><span class="sxs-lookup"><span data-stu-id="19590-113">This involves configuring where you prefer that backup jobs run and then scripting backup jobs to implement your backup preference.</span></span> <span data-ttu-id="19590-114">È necessario creare script dei processi di backup per ogni database nel gruppo di disponibilità in ogni istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in cui è ospitata una replica di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="19590-114">you need to script backup jobs for every database in the availability group on every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts an availability replica.</span></span>  
  
-   <span data-ttu-id="19590-115">Eliminazione di un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="19590-115">Deleting an availability group.</span></span>  
  
-   <span data-ttu-id="19590-116">Migrazione tra cluster di gruppi di disponibilità AlwaysOn per l'aggiornamento del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="19590-116">Cross-cluster migration of AlwaysOn Availability Groups for OS upgrade</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="19590-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="19590-117">Related Tasks</span></span>  
 <span data-ttu-id="19590-118">**Per configurare un gruppo di disponibilità esistente**</span><span class="sxs-lookup"><span data-stu-id="19590-118">**To configure an existing availability group**</span></span>  
  
-   [<span data-ttu-id="19590-119">Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-119">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-120">Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-120">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-121">Aggiungere un database a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-121">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="19590-122">Rimuovere un database secondario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-122">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-123">Rimuovere un database primario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-123">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-124">Configurare i criteri di failover flessibili per controllare le condizioni per il failover automatico &#40;Gruppi di disponibilità AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-124">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover &#40;AlwaysOn Availability Groups&#41;</span></span>](configure-flexible-automatic-failover-policy.md)  
  
 <span data-ttu-id="19590-125">**Per gestire un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="19590-125">**To manage an availability group**</span></span>  
  
-   [<span data-ttu-id="19590-126">Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-126">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="19590-127">Eseguire un failover manuale pianificato di un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-127">Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-128">Eseguire un failover manuale forzato di un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-128">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-129">Rimuovere un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-129">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
  
 <span data-ttu-id="19590-130">**Per gestire una replica di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="19590-130">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="19590-131">Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-131">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-132">Creare un join di una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-132">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-133">Rimuovere una replica secondaria da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-133">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-134">Modificare la modalità di disponibilità di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-134">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="19590-135">Modificare la modalità di failover di una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-135">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="19590-136">Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-136">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="19590-137">Configurare l'accesso in sola lettura in una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-137">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="19590-138">Configurare il routing di sola lettura per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-138">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-139">Modificare il periodo di timeout della sessione per una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-139">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="19590-140">**Per gestire un database di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="19590-140">**To manage an availability database**</span></span>  
  
-   [<span data-ttu-id="19590-141">Aggiungere un database a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-141">Add a Database to an Availability Group &#40;SQL Server&#41;</span></span>](availability-group-add-a-database.md)  
  
-   [<span data-ttu-id="19590-142">Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-142">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-143">Rimuovere un database primario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-143">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-144">Rimuovere un database secondario da un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-144">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="19590-145">Sospendere un database di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-145">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
-   [<span data-ttu-id="19590-146">Riprendere un database di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-146">Resume an Availability Database &#40;SQL Server&#41;</span></span>](resume-an-availability-database-sql-server.md)  
  
 <span data-ttu-id="19590-147">**Per monitorare un gruppo di disponibilità**</span><span class="sxs-lookup"><span data-stu-id="19590-147">**To monitor an availability group**</span></span>  
  
-   [<span data-ttu-id="19590-148">Monitoraggio di Gruppi di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-148">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
 <span data-ttu-id="19590-149">**Per supportare la migrazione di gruppi di disponibilità in un nuovo cluster WSFC (migrazione tra cluster)**</span><span class="sxs-lookup"><span data-stu-id="19590-149">**To support migrating availability groups to a new WSFC cluster (cross-cluster migration)**</span></span>  
  
-   [<span data-ttu-id="19590-150">Modificare il contesto del cluster HADR dell'istanza del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-150">Change the HADR Cluster Context of Server Instance &#40;SQL Server&#41;</span></span>](change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
  
-   [<span data-ttu-id="19590-151">Portare un gruppo di disponibilità offline &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-151">Take an Availability Group Offline &#40;SQL Server&#41;</span></span>](../../take-an-availability-group-offline-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="19590-152">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="19590-152">Related Content</span></span>  
  
-   <span data-ttu-id="19590-153">**Blog:**</span><span class="sxs-lookup"><span data-stu-id="19590-153">**Blogs:**</span></span>  
  
     [<span data-ttu-id="19590-154">Blog del team di SQL Server AlwaysOn: Blog ufficiale del team di SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="19590-154">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="19590-155">Pagina relativa ai blog del Servizio Supporto Tecnico Clienti per gli ingegneri di SQL Server</span><span class="sxs-lookup"><span data-stu-id="19590-155">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="19590-156">**Video:**</span><span class="sxs-lookup"><span data-stu-id="19590-156">**Videos:**</span></span>  
  
     [<span data-ttu-id="19590-157">Pagina relativa alla prima parte riguardante l'introduzione della soluzione a disponibilità elevata di prossima generazione della serie AlwaysOn di Microsoft SQL Server nome in codice "Denali"</span><span class="sxs-lookup"><span data-stu-id="19590-157">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="19590-158">Pagina relativa alla seconda parte riguardante la compilazione di una soluzione a disponibilità elevata critica tramite AlwasyOn della serie AlwaysOn di Microsoft SQL Server nome in codice "Denali"</span><span class="sxs-lookup"><span data-stu-id="19590-158">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="19590-159">**White paper:**</span><span class="sxs-lookup"><span data-stu-id="19590-159">**White papers:**</span></span>  
  
     [<span data-ttu-id="19590-160">Pagina relativa ai white paper Microsoft per SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="19590-160">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="19590-161">Pagina relativa ai white paper del team di consulenza clienti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="19590-161">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
  
## <a name="see-also"></a><span data-ttu-id="19590-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19590-162">See Also</span></span>  
 <span data-ttu-id="19590-163">[Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="19590-163">[AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="19590-164">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="19590-164">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="19590-165">Configurazione di un'istanza del server per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-165">Configuration of a Server Instance for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](configuration-of-a-server-instance-for-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="19590-166">[Creazione e configurazione di gruppi di disponibilità &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="19590-166">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="19590-167">[Repliche secondarie attive: repliche secondarie leggibili &#40;Gruppi di disponibilità AlwaysOn&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="19590-167">[Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="19590-168">Repliche secondarie attive: backup in repliche secondarie &#40;Gruppi di disponibilità AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-168">Active Secondaries: Backup on Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md)  
 <span data-ttu-id="19590-169">[Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="19590-169">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 <span data-ttu-id="19590-170">[Criteri AlwaysOn per problemi operativi con Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="19590-170">[AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups &#40;SQL Server&#41;](always-on-policies-for-operational-issues-always-on-availability.md) </span></span>  
 <span data-ttu-id="19590-171">[Monitoraggio di Gruppi di disponibilità &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="19590-171">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="19590-172">[Gruppi di disponibilità AlwaysOn: interoperabilità &#40;SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="19590-172">[AlwaysOn Availability Groups: Interoperability &#40;SQL Server&#41;](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 <span data-ttu-id="19590-173">[Panoramica delle istruzioni Transact-SQL per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="19590-173">[Overview of Transact-SQL Statements for AlwaysOn Availability Groups &#40;SQL Server&#41;](transact-sql-statements-for-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="19590-174">Panoramica dei cmdlet di PowerShell per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19590-174">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
