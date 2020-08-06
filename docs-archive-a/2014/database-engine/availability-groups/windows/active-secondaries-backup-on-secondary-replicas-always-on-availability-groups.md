---
title: 'Repliche secondarie attive: backup in repliche secondarie (gruppi di disponibilità Always On) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- backup priority
- backup on secondary replicas
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], backup on secondary replicas
- active secondary replicas [SQL Server], backup on
- automated backup preference
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 82afe51b-71d1-4d5b-b20a-b57afc002405
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0cf899cdbeb1ae4ede6c9196b8eb93a9d9e54f05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716848"
---
# <a name="active-secondaries-backup-on-secondary-replicas-always-on-availability-groups"></a><span data-ttu-id="9b332-102">Repliche secondarie attive: Backup in repliche secondarie (gruppi di disponibilità Always On)</span><span class="sxs-lookup"><span data-stu-id="9b332-102">Active Secondaries: Backup on Secondary Replicas (Always On Availability Groups)</span></span>
  <span data-ttu-id="9b332-103">Nelle funzionalità secondarie attive di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] è incluso il supporto per l'esecuzione di operazioni di backup nelle repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="9b332-103">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] active secondary capabilities include support for performing backup operations on secondary replicas.</span></span> <span data-ttu-id="9b332-104">Le operazioni di backup possono richiedere considerevoli risorse a livello di I/O e di CPU (con compressione dei backup).</span><span class="sxs-lookup"><span data-stu-id="9b332-104">Backup operations can put significant strain on I/O and CPU (with backup compression).</span></span> <span data-ttu-id="9b332-105">La ripartizione dei backup su una replica secondaria sincronizzata o in sincronizzazione consente di utilizzare le risorse sull'istanza del server che ospita la replica primaria per i carichi di lavoro di livello 1.</span><span class="sxs-lookup"><span data-stu-id="9b332-105">Offloading backups to a synchronized or synchronizing secondary replica allows you to use the resources on server instance that hosts the primary replica for your tier-1 workloads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b332-106">Le istruzioni RESTORE non sono consentite nei database primari o secondari di un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="9b332-106">RESTORE statements are not allowed on either the primary or secondary databases of an availability group.</span></span>  
  
  
  
##  <a name="backup-types-supported-on-secondary-replicas"></a><a name="SupportedBuTypes"></a> <span data-ttu-id="9b332-107">Tipi di backup supportati nelle repliche secondarie</span><span class="sxs-lookup"><span data-stu-id="9b332-107">Backup Types Supported on Secondary Replicas</span></span>  
  
-   <span data-ttu-id="9b332-108">`BACKUP DATABASE` supporta solo i backup completi di sola copia di database, file o filegroup in caso di esecuzione nelle repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="9b332-108">`BACKUP DATABASE` supports only copy-only full backups of databases, files, or filegroups when it is executed on secondary replicas.</span></span> <span data-ttu-id="9b332-109">Si noti che tramite i backup di sola copia non viene influenzata la catena di log e non viene cancellata la mappa di bit differenziale.</span><span class="sxs-lookup"><span data-stu-id="9b332-109">Note that copy-only backups do not impact the log chain or clear the differential bitmap.</span></span>  
  
-   <span data-ttu-id="9b332-110">I backup differenziali non sono supportati nelle repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="9b332-110">Differential backups are not supported on secondary replicas.</span></span>  
  
-   <span data-ttu-id="9b332-111">**BACKUP LOG** supporta solo i backup di log regolari (l'opzione COPY_ONLY non è supportata per i backup di log in repliche secondarie).</span><span class="sxs-lookup"><span data-stu-id="9b332-111">**BACKUP LOG** supports only regular log backups (the COPY_ONLY option is not supported for log backups on secondary replicas).</span></span>  
  
     <span data-ttu-id="9b332-112">È garantita una catena di log coerente tra i backup di log eseguiti nelle repliche (primarie e secondarie), indipendentemente dalla relativa modalità di disponibilità (commit sincrono o asincrono).</span><span class="sxs-lookup"><span data-stu-id="9b332-112">A consistent log chain is ensured across log backups taken on any of the replicas (primary or secondary), irrespective of their availability mode (synchronous-commit or asynchronous-commit).</span></span>  
  
-   <span data-ttu-id="9b332-113">Per eseguire il backup di un database secondario, è necessario che una replica secondaria sia in grado di comunicare con la replica primaria e sia nello stato `SYNCHRONIZED` o `SYNCHRONIZING`.</span><span class="sxs-lookup"><span data-stu-id="9b332-113">To back up a secondary database, a secondary replica must be able to communicate with the primary replica and must be `SYNCHRONIZED` or `SYNCHRONIZING`.</span></span>  
  
##  <a name="configuring-where-backup-jobs-run"></a><a name="WhereBuJobsRun"></a><span data-ttu-id="9b332-114">Configurazione del percorso di esecuzione dei processi di backup</span><span class="sxs-lookup"><span data-stu-id="9b332-114">Configuring Where Backup Jobs Run</span></span>  
 <span data-ttu-id="9b332-115">L'esecuzione di backup su una replica secondaria per ripartire il carico di lavoro di backup dal server di produzione primario comporta notevoli vantaggi,</span><span class="sxs-lookup"><span data-stu-id="9b332-115">Performing backups on a secondary replica to offload the backup workload from the primary production server is a great benefit.</span></span> <span data-ttu-id="9b332-116">tuttavia rende più complessa la selezione dei percorsi di esecuzione dei processi di backup.</span><span class="sxs-lookup"><span data-stu-id="9b332-116">However, performing backups on secondary replicas introduce significant complexity to the process of determining where backup jobs should run.</span></span> <span data-ttu-id="9b332-117">Per risolvere questo problema, configurare dove eseguire i processi di backup come segue:</span><span class="sxs-lookup"><span data-stu-id="9b332-117">To address this, configure where backup jobs run as follows:</span></span>  
  
1.  <span data-ttu-id="9b332-118">Configurare il gruppo di disponibilità per specificare le repliche di disponibilità per cui si desidera venga eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="9b332-118">Configure the availability group to specify which availability replicas where you would prefer backups to be performed.</span></span> <span data-ttu-id="9b332-119">Per altre informazioni, vedere i parametri *AUTOMATED_BACKUP_PREFERENCE* e *BACKUP_PRIORITY* in [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) o [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b332-119">For more information, see *AUTOMATED_BACKUP_PREFERENCE* and *BACKUP_PRIORITY* parameters in [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) or [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
2.  <span data-ttu-id="9b332-120">Creare processi di backup controllati da script per ogni database di disponibilità in ogni istanza del server che ospita una replica di disponibilità che è un candidato per l'esecuzione del backup.</span><span class="sxs-lookup"><span data-stu-id="9b332-120">Create scripted backup jobs for every availability database on every server instance that hosts an availability replica that is a candidate for performing backups.</span></span> <span data-ttu-id="9b332-121">Per altre informazioni, vedere la sezione "Completamento: Dopo avere configurato il backup su repliche secondarie" di [Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b332-121">For more information, see the "Follow Up: After Configuring Backup on Secondary Replicas" section of [Configure Backup on Availability Replicas &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9b332-122">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="9b332-122">Related Tasks</span></span>  
 <span data-ttu-id="9b332-123">**Per configurare il backup delle repliche secondarie**</span><span class="sxs-lookup"><span data-stu-id="9b332-123">**To configure backup on secondary replicas**</span></span>  
  
-   [<span data-ttu-id="9b332-124">Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9b332-124">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
 <span data-ttu-id="9b332-125">**Per determinare se la replica corrente è la replica di backup preferita**</span><span class="sxs-lookup"><span data-stu-id="9b332-125">**To determine whether the current replica is the preferred backup replica**</span></span>  
  
-   [<span data-ttu-id="9b332-126">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="9b332-126">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
  
 <span data-ttu-id="9b332-127">**Per creare un processo di backup**</span><span class="sxs-lookup"><span data-stu-id="9b332-127">**To create a backup job**</span></span>  
  
-   [<span data-ttu-id="9b332-128">Utilizzare la Creazione guidata piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="9b332-128">Use the Maintenance Plan Wizard</span></span>](../../../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
-   [<span data-ttu-id="9b332-129">Implementazione di processi</span><span class="sxs-lookup"><span data-stu-id="9b332-129">Implement Jobs</span></span>](../../../ssms/agent/implement-jobs.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="9b332-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b332-130">See Also</span></span>  
 <span data-ttu-id="9b332-131">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b332-131">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="9b332-132">[Backup di sola copia &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b332-132">[Copy-Only Backups &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span></span>  
 <span data-ttu-id="9b332-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b332-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span></span>  
 [<span data-ttu-id="9b332-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9b332-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
