---
title: Inizializzare una sottoscrizione transazionale da un backup (programmazione Transact-SQL della replica) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: d0637fc4-27cc-4046-98ea-dc86b7a3bd75
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1563d58f2d54f77680781e22a162112ade1658e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624584"
---
# <a name="initialize-a-transactional-subscription-from-a-backup-replication-transact-sql-programming"></a><span data-ttu-id="c5b97-102">Inizializzazione di una sottoscrizione transazionale da un backup (programmazione Transact-SQL della replica)</span><span class="sxs-lookup"><span data-stu-id="c5b97-102">Initialize a Transactional Subscription from a Backup (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="c5b97-103">Anche se una sottoscrizione di una pubblicazione transazionale viene in genere inizializzata con uno snapshot, è possibile inizializzarla da un backup utilizzando le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="c5b97-103">Although a subscription to a transactional publication is typically initialized with a snapshot, a subscription can be initialized from a backup using replication stored procedures.</span></span> <span data-ttu-id="c5b97-104">Per altre informazioni, vedere [Inizializzazione di una sottoscrizione transazionale senza uno snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="c5b97-104">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
### <a name="to-initialize-a-transactional-subscriber-from-a-backup"></a><span data-ttu-id="c5b97-105">Per inizializzare un Sottoscrittore transazionale da un backup</span><span class="sxs-lookup"><span data-stu-id="c5b97-105">To initialize a transactional subscriber from a backup</span></span>  
  
1.  <span data-ttu-id="c5b97-106">Per una pubblicazione esistente, assicurarsi che la pubblicazione supporti la funzionalità di inizializzazione da backup eseguendo [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) nel database di pubblicazione del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="c5b97-106">For an existing publication, ensure that the publication supports the ability to initialize from backup by executing [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="c5b97-107">Si noti il valore di **allow_initialize_from_backup** nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="c5b97-107">Note the value of **allow_initialize_from_backup** in the result set.</span></span>  
  
    -   <span data-ttu-id="c5b97-108">Se il valore è **1**, la pubblicazione supporta questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c5b97-108">If the value is **1**, the publication supports this functionality.</span></span>  
  
    -   <span data-ttu-id="c5b97-109">Se il valore è **0**, eseguire [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) nel database di pubblicazione nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="c5b97-109">If the value is **0**, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="c5b97-110">Specificare il valore **allow_initialize_from_backup** per \*\* \@ Property\*\* e il valore `true` per \*\* \@ value\*\*.</span><span class="sxs-lookup"><span data-stu-id="c5b97-110">Specify a value of **allow_initialize_from_backup** for **\@property** and a value of `true` for **\@value**.</span></span>  
  
2.  <span data-ttu-id="c5b97-111">Per una nuova pubblicazione, eseguire [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) nel database di pubblicazione nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="c5b97-111">For a new publication, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="c5b97-112">Specificare il valore `true` per **allow_initialize_from_backup**.</span><span class="sxs-lookup"><span data-stu-id="c5b97-112">Specify a value of `true` for **allow_initialize_from_backup**.</span></span> <span data-ttu-id="c5b97-113">Per altre informazioni, vedere [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c5b97-113">For more information, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="c5b97-114">Per evitare la mancanza di dati del Sottoscrittore, quando si utilizza **sp_addpublication** con `@allow_initialize_from_backup = N'true'`, utilizzare sempre `@immediate_sync = N'true'`.</span><span class="sxs-lookup"><span data-stu-id="c5b97-114">To avoid missing subscriber data, when using **sp_addpublication** with `@allow_initialize_from_backup = N'true'`, always use `@immediate_sync = N'true'`.</span></span>  
  
3.  <span data-ttu-id="c5b97-115">Creare un backup del database di pubblicazione usando l'istruzione [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c5b97-115">Create a backup of the publication database using the [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
4.  <span data-ttu-id="c5b97-116">Ripristinare il backup nel Sottoscrittore usando l'istruzione [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c5b97-116">Restore the backup on the Subscriber using the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement.</span></span>  
  
5.  <span data-ttu-id="c5b97-117">Nel database di pubblicazione del server di pubblicazione eseguire la stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c5b97-117">At the Publisher on the publication database, execute the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="c5b97-118">Specificare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5b97-118">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="c5b97-119">\*\* \@ sync_type\*\* : valore **Initialize with backup**.</span><span class="sxs-lookup"><span data-stu-id="c5b97-119">**\@sync_type** - a value of **initialize with backup**.</span></span>  
  
    -   <span data-ttu-id="c5b97-120">\*\* \@ backupdevicetype\*\* : tipo di dispositivo di backup, ovvero **Logical** (impostazione predefinita), **disk**o **Tape**.</span><span class="sxs-lookup"><span data-stu-id="c5b97-120">**\@backupdevicetype** - the type of backup device: **logical** (default), **disk**, or **tape**.</span></span>  
  
    -   <span data-ttu-id="c5b97-121">\*\* \@ backupdevicename\*\* : dispositivo di backup logico o fisico da usare per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="c5b97-121">**\@backupdevicename** - the logical or physical backup device to use for the restore.</span></span>  
  
         <span data-ttu-id="c5b97-122">Per un dispositivo logico, specificare il nome del dispositivo di backup indicato durante la creazione dello stesso tramite **sp_addumpdevice** .</span><span class="sxs-lookup"><span data-stu-id="c5b97-122">For a logical device, specify the name of the backup device specified when **sp_addumpdevice** was used to create the device.</span></span>  
  
         <span data-ttu-id="c5b97-123">Per un dispositivo fisico, specificare un nome e un percorso completo di file, ad esempio `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` o `TAPE = '\\.\TAPE0'`.</span><span class="sxs-lookup"><span data-stu-id="c5b97-123">For a physical device, specify a complete path and file name, such as `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` or `TAPE = '\\.\TAPE0'`.</span></span>  
  
    -   <span data-ttu-id="c5b97-124">Opzionale \*\* \@ password\*\* : password fornita al momento della creazione del set di backup.</span><span class="sxs-lookup"><span data-stu-id="c5b97-124">(Optional) **\@password** - a password that was provided when the backup set was created.</span></span>  
  
    -   <span data-ttu-id="c5b97-125">Opzionale \*\* \@ MEDIAPASSWORD\*\* : password specificata durante la formattazione del set di supporti.</span><span class="sxs-lookup"><span data-stu-id="c5b97-125">(Optional) **\@mediapassword** - a password that was provided when the media set was formatted.</span></span>  
  
    -   <span data-ttu-id="c5b97-126">Opzionale \*\* \@ fileidhint\*\* : identificatore per il set di backup da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="c5b97-126">(Optional) **\@fileidhint** - identifier for the backup set to be restored.</span></span> <span data-ttu-id="c5b97-127">Ad esempio, **1** indica il primo set di backup sul supporto, mentre **2** indica il secondo set di backup.</span><span class="sxs-lookup"><span data-stu-id="c5b97-127">For example, specifying **1** indicates the first backup set on the backup medium and **2** indicates the second backup set.</span></span>  
  
    -   <span data-ttu-id="c5b97-128">(Facoltativo per i dispositivi a nastro) \*\* \@ unload\*\* : specificare il valore **1** (impostazione predefinita) se il nastro deve essere scaricato dall'unità al termine del ripristino e **0** se non deve essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="c5b97-128">(Optional for tape devices) **\@unload** - specify a value of **1** (default) if the tape should be unloaded from the drive after the restore is complete and **0** if it should not be unloaded.</span></span>  
  
6.  <span data-ttu-id="c5b97-129">(Facoltativo) Per una sottoscrizione pull, eseguire [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) e [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) nel database di sottoscrizione del Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="c5b97-129">(Optional) For a pull subscription, execute [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) and [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="c5b97-130">Per altre informazioni, vedere [Creazione di una sottoscrizione pull](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c5b97-130">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
7.  <span data-ttu-id="c5b97-131">(Facoltativo) Avviare l'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c5b97-131">(Optional) Start the Distribution Agent.</span></span> <span data-ttu-id="c5b97-132">Per ulteriori informazioni, vedere [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) o [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c5b97-132">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) or [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b97-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5b97-133">See Also</span></span>  
 <span data-ttu-id="c5b97-134">[Copiare database tramite backup e ripristino](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="c5b97-134">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="c5b97-135">Backup e ripristino di database SQL Server</span><span class="sxs-lookup"><span data-stu-id="c5b97-135">Back Up and Restore of SQL Server Databases</span></span>](../backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
  
