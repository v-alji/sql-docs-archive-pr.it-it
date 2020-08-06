---
title: Eseguire il backup e ripristino di database replicati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- backups [SQL Server replication]
- administering replication, restoring
- backing up replicated databases
- backups [SQL Server replication], about backups
- restoring replicated databases [SQL Server replication]
- recovery [SQL Server replication], about recovery
- restoring databases [SQL Server], replicated databases
- backing up databases [SQL Server], replicated databases
- restoring [SQL Server replication], about restoring
- recovery [SQL Server replication]
- replication [SQL Server], administering
- distribution databases [SQL Server replication], backing up
- restoring [SQL Server replication]
- administering replication, backing up
ms.assetid: 04588807-21e7-4bbe-9727-b72f692cffa7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e91505bacf67f7f4628bd1b3f6b2cc78a6bc4c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629366"
---
# <a name="back-up-and-restore-replicated-databases"></a><span data-ttu-id="7ff1b-102">Backup e ripristino di database replicati</span><span class="sxs-lookup"><span data-stu-id="7ff1b-102">Back Up and Restore Replicated Databases</span></span>
  <span data-ttu-id="7ff1b-103">Il backup e il ripristino dei dati dei database replicati richiedono un'attenzione particolare.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-103">Replicated databases require special attention with regards to backing up and restoring data.</span></span> <span data-ttu-id="7ff1b-104">In questo argomento sono fornite informazioni introduttive e collegamenti ad informazioni più approfondite sulle strategie di backup e ripristino per ogni tipo di replica.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-104">This topic provides introductory information and links to further information on backup and restore strategies for each type of replication.</span></span>  
  
 <span data-ttu-id="7ff1b-105">La replica supporta il ripristino dei database replicati nello stesso server e nello stesso database da cui è stato creato il backup.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-105">Replication supports restoring replicated databases to the same server and database from which the backup was created.</span></span> <span data-ttu-id="7ff1b-106">Se si ripristina un backup di un database replicato in un altro server o database, le impostazioni di replica non potranno essere mantenute.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-106">If you restore a backup of a replicated database to another server or database, replication settings cannot be preserved.</span></span> <span data-ttu-id="7ff1b-107">In questo caso sarà necessario ricreare tutte le pubblicazioni e le sottoscrizioni dopo il ripristino dei backup.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-107">In this case, you must recreate all publications and subscriptions after backups are restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ff1b-108">È possibile ripristinare un database replicato in un server di standby se si utilizza il log shipping.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-108">It is possible to restore a replicated database to a standby server if log shipping is being used.</span></span> <span data-ttu-id="7ff1b-109">Per altre informazioni, vedere [Log shipping e replica &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ff1b-109">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="7ff1b-110">Il backup dei database replicati e dei relativi sistemi associati deve essere eseguito periodicamente.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-110">Replicated databases and their associated system databases should be backed up regularly.</span></span> <span data-ttu-id="7ff1b-111">Eseguire il backup dei database seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ff1b-111">Back up the following databases:</span></span>  
  
-   <span data-ttu-id="7ff1b-112">Database di pubblicazione nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-112">The publication database at the Publisher</span></span>  
  
-   <span data-ttu-id="7ff1b-113">Database di distribuzione nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-113">The distribution database at the Distributor</span></span>  
  
-   <span data-ttu-id="7ff1b-114">Database di sottoscrizione in ogni Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-114">The subscription database at each Subscriber</span></span>  
  
-   <span data-ttu-id="7ff1b-115">Database di sistema **master** e **msdb** nel server di pubblicazione, nel database di distribuzione e in tutti i Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-115">The **master** and **msdb** system databases at the Publisher, Distributor and all Subscribers.</span></span> <span data-ttu-id="7ff1b-116">È necessario che il backup di questi database venga eseguito contemporaneamente e che venga inoltre eseguito nello stesso momento di quello del relativo database di replica.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-116">These databases should be backed up at the same time as each other and the relevant replication database.</span></span> <span data-ttu-id="7ff1b-117">Eseguire, ad esempio, il backup dei database **master** e **msdb** nel server di pubblicazione nello stesso momento in cui si esegue il backup del database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-117">For example, back up the **master** and **msdb** databases at the Publisher at the same time you back up the publication database.</span></span> <span data-ttu-id="7ff1b-118">Se il database di pubblicazione viene ripristinato, verificare che i database **master** e **msdb** siano consistenti con il database di pubblicazione in termini di impostazioni e di configurazione della replica.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-118">If the publication database is restored, ensure that the **master** and **msdb** database are consistent with the publication database in terms of replication configuration and settings.</span></span>  
  
 <span data-ttu-id="7ff1b-119">Se si eseguono backup regolari del log, le eventuali modifiche correlate alla replica dovrebbero essere incluse nei backup del log.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-119">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="7ff1b-120">Se non si eseguono i backup del log, è necessario eseguire un backup ogni volta che un'impostazione relativa alla replica viene modificata.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-120">If you do not perform log backups, a backup should be performed whenever a setting relevant to replication is changed.</span></span> <span data-ttu-id="7ff1b-121">Per altre informazioni, vedere [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span><span class="sxs-lookup"><span data-stu-id="7ff1b-121">For more information, see [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span></span>  
  
## <a name="backup-and-restore-strategies"></a><span data-ttu-id="7ff1b-122">Strategie di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="7ff1b-122">Backup and Restore Strategies</span></span>  
 <span data-ttu-id="7ff1b-123">Le strategie di backup e ripristino di ogni nodo in una topologia di replica variano in base al tipo di replica utilizzata.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-123">The strategies for backing up and restoring each node in a replication topology differ according to the type of replication used.</span></span> <span data-ttu-id="7ff1b-124">Per informazioni sulle strategie di backup e ripristino per ogni tipo di replica, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ff1b-124">For information on backup and restore strategies for each type of replication, see the following topics:</span></span>  
  
-   [<span data-ttu-id="7ff1b-125">Strategie di backup e ripristino della replica snapshot e della replica transazionale</span><span class="sxs-lookup"><span data-stu-id="7ff1b-125">Strategies for Backing Up and Restoring Snapshot and Transactional Replication</span></span>](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md)  
  
-   [<span data-ttu-id="7ff1b-126">Strategie di backup e ripristino della replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="7ff1b-126">Strategies for Backing Up and Restoring Merge Replication</span></span>](strategies-for-backing-up-and-restoring-merge-replication.md)  
  
 <span data-ttu-id="7ff1b-127">Ogni strategia di recupero include la conservazione in un luogo sicuro di uno script corrente delle impostazioni di replica.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-127">As part of any recovery strategy, always keep a current script of your replication settings in a safe location.</span></span> <span data-ttu-id="7ff1b-128">Se si verifica un errore in un server oppure è necessario configurare un ambiente di prova, è possibile modificare lo script tramite la modifica dei riferimenti ai nomi di server e quindi utilizzarlo per ricreare le impostazioni di replica.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-128">In the event of server failure or the need to set up a test environment, you can modify the script by changing server name references, and it can be used to help recreate your replication settings.</span></span> <span data-ttu-id="7ff1b-129">Oltre a creare script per le impostazioni di replica correnti, è consigliabile creare script anche per l'attivazione e la disabilitazione della replica.</span><span class="sxs-lookup"><span data-stu-id="7ff1b-129">In addition to scripting your current replication settings, you should script the enabling and disabling of replication.</span></span> <span data-ttu-id="7ff1b-130">Per informazioni sulla creazione di script per oggetti di replica, vedere [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="7ff1b-130">For information about scripting replication objects, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff1b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ff1b-131">See Also</span></span>  
 <span data-ttu-id="7ff1b-132">[Backup e ripristino di database SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="7ff1b-132">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="7ff1b-133">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="7ff1b-133">Best Practices for Replication Administration</span></span>](best-practices-for-replication-administration.md)  
  
  
