---
title: Backup e ripristino di indici e cataloghi full-text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], backing up
- full-text search [SQL Server], back up and restore
- recovery [full-text search]
- backups [SQL Server], full-text indexes
- full-text indexes [SQL Server], restoring
- restore operations [full-text search]
ms.assetid: 6a4080d9-e43f-4b7b-a1da-bebf654c1194
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c0df49c03325da375427c6566799f374fcc9dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636656"
---
# <a name="back-up-and-restore-full-text-catalogs-and-indexes"></a><span data-ttu-id="73cc2-102">Backup e ripristino di indici e cataloghi full-text</span><span class="sxs-lookup"><span data-stu-id="73cc2-102">Back Up and Restore Full-Text Catalogs and Indexes</span></span>
  <span data-ttu-id="73cc2-103">In questo argomento viene illustrato come eseguire il backup e il ripristino di indici full-text creati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73cc2-103">This topic explains how to back up and restore full-text indexes created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="73cc2-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]il catalogo full-text è un concetto logico e non è contenuto in un filegroup.</span><span class="sxs-lookup"><span data-stu-id="73cc2-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the full-text catalog is a logical concept and does not reside in a filegroup.</span></span> <span data-ttu-id="73cc2-105">Pertanto, per eseguire il backup di un catalogo full-text in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è necessario identificare ogni filegroup che contiene un indice full-text appartenente al catalogo,</span><span class="sxs-lookup"><span data-stu-id="73cc2-105">Therefore, to back up a full-text catalog in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must identify every filegroup that contains a full-text index that belongs to the catalog.</span></span> <span data-ttu-id="73cc2-106">quindi eseguirne il backup uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="73cc2-106">Then you must back up those filegroups, one by one.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="73cc2-107">È possibile importare cataloghi full-text quando si aggiorna un database di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73cc2-107">It is possible to import full-text catalogs when upgrading a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database.</span></span> <span data-ttu-id="73cc2-108">Ogni catalogo full-text importato è un file di database nel proprio filegroup.</span><span class="sxs-lookup"><span data-stu-id="73cc2-108">Each imported full-text catalog is a database file in its own filegroup.</span></span> <span data-ttu-id="73cc2-109">Per eseguire il backup di un catalogo importato, eseguire il backup del relativo filegroup.</span><span class="sxs-lookup"><span data-stu-id="73cc2-109">To back up an imported catalog, simply back up its filegroup.</span></span> <span data-ttu-id="73cc2-110">Per altre informazioni, vedere [Backup e ripristino di cataloghi full-text](https://go.microsoft.com/fwlink/?LinkID=121052)nella documentazione online di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73cc2-110">For more information, see [Backing Up and Restoring Full-Text Catalogs](https://go.microsoft.com/fwlink/?LinkID=121052), in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Books Online.</span></span>  
  
##  <a name="backing-up-the-full-text-indexes-of-a-full-text-catalog"></a><a name="backingup"></a> <span data-ttu-id="73cc2-111">Backup degli indici full-text di un catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="73cc2-111">Backing Up the Full-Text Indexes of a Full-Text Catalog</span></span>  
  
###  <a name="finding-the-full-text-indexes-of-a-full-text-catalog"></a><a name="Find_FTIs_of_a_Catalog"></a> <span data-ttu-id="73cc2-112">Individuazione degli indici full-text di un catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="73cc2-112">Finding the Full-Text Indexes of a Full-Text Catalog</span></span>  
 <span data-ttu-id="73cc2-113">È possibile recuperare le proprietà degli indici full-text usando l'istruzione [SELECT](/sql/t-sql/queries/select-transact-sql) seguente che consente di selezionare le colonne dalle viste del catalogo [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) e [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="73cc2-113">You can retrieve the properties of the full-text indexes by using the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement, which selects columns from the [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) and [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) catalog views.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @TableID int;  
SET @TableID = (SELECT OBJECT_ID('AdventureWorks2012.Production.Product'));  
SELECT object_name(@TableID), i.is_enabled, i.change_tracking_state,   
   i.has_crawl_completed, i.crawl_type, c.name as fulltext_catalog_name   
   FROM sys.fulltext_indexes i, sys.fulltext_catalogs c   
   WHERE i.fulltext_catalog_id = c.fulltext_catalog_id;  
GO  
```  
  

  
###  <a name="finding-the-filegroup-or-file-that-contains-a-full-text-index"></a><a name="Find_FG_of_FTI"></a> <span data-ttu-id="73cc2-114">Individuazione del filegroup o del file che contiene un indice full-text</span><span class="sxs-lookup"><span data-stu-id="73cc2-114">Finding the Filegroup or File That Contains a Full-Text Index</span></span>  
 <span data-ttu-id="73cc2-115">Quando viene creato, l'indice full-text viene inserito in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="73cc2-115">When a full-text index is created, it is placed in one of the following locations:</span></span>  
  
-   <span data-ttu-id="73cc2-116">Filegroup specificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="73cc2-116">A user-specified filegroup.</span></span>  
  
-   <span data-ttu-id="73cc2-117">Lo stesso filegroup della vista o della tabella di base, per una tabella non partizionata.</span><span class="sxs-lookup"><span data-stu-id="73cc2-117">The same filegroup as base table or view, for a nonpartitioned table.</span></span>  
  
-   <span data-ttu-id="73cc2-118">Filegroup primario, per una tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="73cc2-118">The primary filegroup, for a partitioned table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73cc2-119">Per informazioni sulla creazione di un indice full-text, vedere [Creare e gestire indici full-text](create-and-manage-full-text-indexes.md) e [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="73cc2-119">For information about creating a full-text index, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) and [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="73cc2-120">Per trovare il filegroup dell'indice full-text in una tabella o vista, usare la query seguente, dove *object_name* rappresenta il nome della tabella o della vista:</span><span class="sxs-lookup"><span data-stu-id="73cc2-120">To find the filegroup of full-text index on a table or view, use the following query, where *object_name* is the name of the table or view:</span></span>  
  
```  
SELECT name FROM sys.filegroups f, sys.fulltext_indexes i   
   WHERE f.data_space_id = i.data_space_id   
      and i.object_id = object_id('object_name');  
GO  
  
```  
  

  
###  <a name="backing-up-the-filegroups-that-contain-full-text-indexes"></a><a name="Back_up_FTIs_of_FTC"></a> <span data-ttu-id="73cc2-121">Backup dei filegroup che contengono gli indici full-text</span><span class="sxs-lookup"><span data-stu-id="73cc2-121">Backing Up the Filegroups That Contain Full-Text Indexes</span></span>  
 <span data-ttu-id="73cc2-122">Dopo avere trovato i filegroup che contengono gli indici di un catalogo full-text, è necessario eseguire il backup di ognuno.</span><span class="sxs-lookup"><span data-stu-id="73cc2-122">After you find the filegroups that contain the indexes of a full-text catalog, you need back up each of the filegroups.</span></span> <span data-ttu-id="73cc2-123">Durante il processo di backup non è consentito eliminare o aggiungere cataloghi full-text.</span><span class="sxs-lookup"><span data-stu-id="73cc2-123">During the backup process, full-text catalogs may not be dropped or added.</span></span>  
  
 <span data-ttu-id="73cc2-124">Il primo backup di un filegroup deve essere un backup di file completo.</span><span class="sxs-lookup"><span data-stu-id="73cc2-124">The first backup of a filegroup must be a full file backup.</span></span> <span data-ttu-id="73cc2-125">Dopo avere creato un backup di file completo per un filegroup, è possibile eseguire il backup delle sole modifiche avvenute in un filegroup creando una serie di uno o più backup di file differenziali basati sul backup di file completo.</span><span class="sxs-lookup"><span data-stu-id="73cc2-125">After you have created a full file backup for a filegroup, you could back up only the changes in a filegroup by creating a series of one or more differential file backups that are based on the full file backup.</span></span>  
  
 <span data-ttu-id="73cc2-126">**Per eseguire il backup di file e filegroup**</span><span class="sxs-lookup"><span data-stu-id="73cc2-126">**To back up files and filegroups**</span></span>  
  
-   [<span data-ttu-id="73cc2-127">Backup di file e filegroup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="73cc2-127">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="73cc2-128">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="73cc2-128">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  

  
##  <a name="restoring-a-full-text-index"></a><a name="Restore_FTI"></a> <span data-ttu-id="73cc2-129">Ripristino di un indice full-text</span><span class="sxs-lookup"><span data-stu-id="73cc2-129">Restoring a Full-Text Index</span></span>  
 <span data-ttu-id="73cc2-130">Il ripristino del backup di un filegroup include il ripristino dei file di indice full-text e degli altri file nel filegroup.</span><span class="sxs-lookup"><span data-stu-id="73cc2-130">Restoring a backed-up filegroup restores the full-text index files, as well as the other files in the filegroup.</span></span> <span data-ttu-id="73cc2-131">Per impostazione predefinita, il filegroup viene ripristinato nel percorso del disco in cui è stato eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="73cc2-131">By default, the filegroup is restored to the disk location on which the filegroup was backed up.</span></span>  
  
 <span data-ttu-id="73cc2-132">Se alla creazione del backup era online una tabella indicizzata full-text con un popolamento in corso, quest'ultimo verrà ripreso dopo il ripristino.</span><span class="sxs-lookup"><span data-stu-id="73cc2-132">If a full-text indexed table was online and a population was running when the backup was created, the population is resumed after the restore.</span></span>  
  
 <span data-ttu-id="73cc2-133">**Per ripristinare un filegroup**</span><span class="sxs-lookup"><span data-stu-id="73cc2-133">**To restore a filegroup**</span></span>  
  
-   [<span data-ttu-id="73cc2-134">Ripristino di file e filegroup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="73cc2-134">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="73cc2-135">Ripristinare file e filegroup sovrascrivendo file esistenti &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="73cc2-135">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="73cc2-136">Ripristino dei file in una nuova posizione &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="73cc2-136">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="73cc2-137">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="73cc2-137">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  

  
## <a name="see-also"></a><span data-ttu-id="73cc2-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73cc2-138">See Also</span></span>  
 <span data-ttu-id="73cc2-139">[Gestione e monitoraggio della ricerca full-text per un'istanza del server](manage-and-monitor-full-text-search-for-a-server-instance.md) </span><span class="sxs-lookup"><span data-stu-id="73cc2-139">[Manage and Monitor Full-Text Search for a Server Instance](manage-and-monitor-full-text-search-for-a-server-instance.md) </span></span>  
 [<span data-ttu-id="73cc2-140">Aggiornare la ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="73cc2-140">Upgrade Full-Text Search</span></span>](upgrade-full-text-search.md)  
  
  
