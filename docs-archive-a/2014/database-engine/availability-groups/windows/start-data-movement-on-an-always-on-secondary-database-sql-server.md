---
title: Avviare lo spostamento dati su un database secondario AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], databases
ms.assetid: 498eb3fb-6a43-434d-ad95-68a754232c45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ce4f80b456244cd6e024377383abe75e002057a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724971"
---
# <a name="start-data-movement-on-an-alwayson-secondary-database-sql-server"></a><span data-ttu-id="0e70b-102">Avviare lo spostamento dati su un database secondario AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0e70b-102">Start Data Movement on an AlwaysOn Secondary Database (SQL Server)</span></span>
  <span data-ttu-id="0e70b-103">In questo argomento vengono fornite informazioni relative all'avvio della sincronizzazione dati dopo l'aggiunta di un database a un gruppo di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="0e70b-103">This topic contains information about how to start data synchronization after you add a database to an AlwaysOn availability group.</span></span> <span data-ttu-id="0e70b-104">Per ogni nuova replica primaria, è necessario preparare i database secondari nelle istanze del server che ospitano le repliche secondarie.</span><span class="sxs-lookup"><span data-stu-id="0e70b-104">For each new primary replica, secondary databases must be prepared on the server instances that host the secondary replicas.</span></span> <span data-ttu-id="0e70b-105">È quindi necessario eseguire manualmente il join di ciascuno di questi database secondari al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0e70b-105">Then each of these secondary databases must be manually joined to the availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e70b-106">Se i percorsi dei file sono identici in ogni istanza del server che ospita una replica di disponibilità per un gruppo di disponibilità, è possibile che la sincronizzazione dati venga avviata automaticamente dalla [Creazione guidata Gruppo di disponibilità](use-the-availability-group-wizard-sql-server-management-studio.md), dalla procedura guidata [Aggiungi database a gruppo di disponibilità](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)o dalla procedura guidata [Aggiungi database a gruppo di disponibilità](availability-group-add-database-to-group-wizard.md) .</span><span class="sxs-lookup"><span data-stu-id="0e70b-106">If the file paths are identical on every server instance that hosts an availability replica for an availability group, the [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md) might be able to automatically start data synchronization for you.</span></span>  
  
 <span data-ttu-id="0e70b-107">Per avviare manualmente la sincronizzazione dati, è necessario connettersi a ogni istanza del server in cui è ospitata una replica secondaria per il gruppo di disponibilità e completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e70b-107">To start data synchronization manually, you need to connect, in turn, to each server instance that is hosting a secondary replica for the availability group and complete the following steps:</span></span>  
  
1.  <span data-ttu-id="0e70b-108">Ripristinare i backup correnti di ogni database primario e il relativo log delle transazioni tramite RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="0e70b-108">Restore current backups of each primary database and its transaction log (using RESTORE WITH NORECOVERY).</span></span> <span data-ttu-id="0e70b-109">È possibile utilizzare uno dei metodi alternativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e70b-109">You can use either of the following alternative approaches:</span></span>  
  
    -   <span data-ttu-id="0e70b-110">Ripristinare manualmente un backup recente del database primario utilizzando RESTORE WITH NORECOVERY, quindi ripristinare ogni successivo backup del log utilizzando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="0e70b-110">Manually restore a recent database backup of the primary database using RESTORE WITH NORECOVERY, and then restore each subsequent log backup using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="0e70b-111">Eseguire questa sequenza di ripristino in ogni istanza del server che ospita una replica secondaria per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0e70b-111">Perform this restore sequence on every server instance that hosts a secondary replica for the availability group.</span></span>  
  
         <span data-ttu-id="0e70b-112">**Per ulteriori informazioni:**</span><span class="sxs-lookup"><span data-stu-id="0e70b-112">**For more information:**</span></span>  
  
         [<span data-ttu-id="0e70b-113">Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e70b-113">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
    -   <span data-ttu-id="0e70b-114">Se vengono aggiunti uno o più database primari per il log shipping a un gruppo di disponibilità, è possibile eseguire la migrazione di uno o più database secondari corrispondenti da log shipping a gruppi di disponibilità AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="0e70b-114">If you are adding one or more log shipping primary databases to an availability group, you might be able to migrate one or more of the corresponding secondary databases from log shipping to AlwaysOn Availability Groups.</span></span> <span data-ttu-id="0e70b-115">Per la migrazione di un database secondario per il log shipping è necessario che venga utilizzato lo stesso nome di database del database primario e che il database risieda in un'istanza del server in cui è ospitata una replica secondaria per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0e70b-115">Migrating a log shipping secondary database requires that it use the same database name as the primary database and that it reside on a server instance that is hosting a secondary replica for the availability group.</span></span> <span data-ttu-id="0e70b-116">Il gruppo di disponibilità deve inoltre essere configurato in modo che la replica primaria sia quella preferita per i backup e sia un candidato per l'esecuzione di backup, ovvero che la relativa priorità di backup sia >0.</span><span class="sxs-lookup"><span data-stu-id="0e70b-116">Furthermore, the availability group must be configured so that the primary replica is preferred for backups and is a candidate for performing backups (that is, that has a backup priority that is >0).</span></span> <span data-ttu-id="0e70b-117">Dopo l'esecuzione del processo di backup sul database primario, sarà necessario disabilitare il processo di backup e al termine dell'esecuzione del processo di ripristino su un determinato database secondario, disabilitare il processo di ripristino.</span><span class="sxs-lookup"><span data-stu-id="0e70b-117">Once the backup job has run on the primary database, you will need to disable the backup job, and once the restore job has run on a given secondary database, you will need to disable the restore job.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0e70b-118">Dopo aver creato tutti i database secondari per il gruppo di disponibilità, se si desidera eseguire backup nelle repliche secondarie, sarà necessario configurare nuovamente le preferenze di backup automatico del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0e70b-118">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you will need to re-configure the automated backup preference of the availability group.</span></span>  
  
         <span data-ttu-id="0e70b-119">**Per ulteriori informazioni:**</span><span class="sxs-lookup"><span data-stu-id="0e70b-119">**For more information:**</span></span>  
  
         [<span data-ttu-id="0e70b-120">Prerequisiti per la migrazione dal log shipping a Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e70b-120">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
         [<span data-ttu-id="0e70b-121">Configurare il backup su repliche di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e70b-121">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
2.  <span data-ttu-id="0e70b-122">Creare al più presto un join di ogni database secondario appena preparato al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0e70b-122">As soon as possible, join each newly prepared secondary database to the availability group.</span></span>  
  
     <span data-ttu-id="0e70b-123">**Per ulteriori informazioni:**</span><span class="sxs-lookup"><span data-stu-id="0e70b-123">**For more information:**</span></span>  
  
     [<span data-ttu-id="0e70b-124">Creare un join di un database secondario a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e70b-124">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="LaunchWiz"></a> <span data-ttu-id="0e70b-125">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0e70b-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="0e70b-126">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0e70b-126">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0e70b-127">Usare la procedura guidata Aggiungi replica a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0e70b-127">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0e70b-128">Usare la procedura guidata Aggiungi database a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0e70b-128">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e70b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e70b-129">See Also</span></span>  
 [<span data-ttu-id="0e70b-130">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e70b-130">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
