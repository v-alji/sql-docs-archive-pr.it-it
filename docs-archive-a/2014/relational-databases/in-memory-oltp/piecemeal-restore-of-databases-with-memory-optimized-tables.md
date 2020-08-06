---
title: Ripristino a fasi di database con tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 732c9721-8dd4-481d-8ff9-1feaaa63f84f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ed23f08d40e23b1d43c1b642f4089fe77646b675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722812"
---
# <a name="piecemeal-restore-of-databases-with-memory-optimized-tables"></a><span data-ttu-id="72a9b-102">Ripristino a fasi di database con tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="72a9b-102">Piecemeal Restore of Databases With Memory-Optimized Tables</span></span>
  <span data-ttu-id="72a9b-103">Nei database con tabelle ottimizzate per la memoria è supportato il ripristino a fasi, tranne per la restrizione descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="72a9b-103">Piecemeal restore is supported on databases with memory-optimized tables except for one restriction described below.</span></span> <span data-ttu-id="72a9b-104">Per altre informazioni sul backup e sul ripristino a fasi, vedere[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) e [Ripristini a fasi &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="72a9b-104">For more information about piecemeal backup and restore, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [Piecemeal Restores &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span></span>  
  
 <span data-ttu-id="72a9b-105">Il backup e ripristino di un filegroup ottimizzato per la memoria deve essere eseguito insieme al filegroup primario:</span><span class="sxs-lookup"><span data-stu-id="72a9b-105">A memory-optimized filegroup must be backed up and restored together with the primary filegroup:</span></span>  
  
-   <span data-ttu-id="72a9b-106">Se si esegue il backup (o ripristino) del filegroup primario, è necessario specificare il filegroup ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="72a9b-106">If you back up (or restore) the primary filegroup you must specify the memory-optimized filegroup.</span></span>  
  
-   <span data-ttu-id="72a9b-107">Se si esegue il backup (o ripristino) del filegroup ottimizzato per la memoria, è necessario specificare il filegroup primario.</span><span class="sxs-lookup"><span data-stu-id="72a9b-107">If you backup (or restore) the memory-optimized filegroup you must specify the primary filegroup.</span></span>  
  
 <span data-ttu-id="72a9b-108">Di seguito sono riportati gli scenari principali per il backup e ripristino a fasi.</span><span class="sxs-lookup"><span data-stu-id="72a9b-108">Key scenarios for piecemeal backup and restore are,</span></span>  
  
-   <span data-ttu-id="72a9b-109">Il backup a fasi consente di ridurre le dimensioni del backup.</span><span class="sxs-lookup"><span data-stu-id="72a9b-109">Piecemeal backup allows you to reduce the size of backup.</span></span> <span data-ttu-id="72a9b-110">Di seguito alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="72a9b-110">Some examples:</span></span>  
  
    -   <span data-ttu-id="72a9b-111">Configurare l'esecuzione del backup del database in ore o giorni diversi per ridurre l'impatto sul carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72a9b-111">Configure the database backup to occur at different times or days to minimize the impact on the workload.</span></span> <span data-ttu-id="72a9b-112">Un esempio è rappresentato da un database di dimensioni molto estese (maggiore di 1 TB) in cui non è possibile completare un backup completo del database nel tempo allocato per la manutenzione del database.</span><span class="sxs-lookup"><span data-stu-id="72a9b-112">One example is a very large database (greater than 1 TB) where a full database backup cannot complete in the time allocated for database maintenance.</span></span> <span data-ttu-id="72a9b-113">In questo caso, è possibile utilizzare il backup a fasi per eseguire il backup completo del database in più backup a fasi.</span><span class="sxs-lookup"><span data-stu-id="72a9b-113">In that situation, you can use piecemeal backup to backup the full database in multiple piecemeal backups.</span></span>  
  
    -   <span data-ttu-id="72a9b-114">Se un filegroup è di sola lettura, non è necessario un backup del log delle transazioni dopo essere stato contrassegnato come di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="72a9b-114">If a filegroup is marked read-only, it does not require a transaction log backup after it was marked read-only.</span></span> <span data-ttu-id="72a9b-115">È possibile scegliere di eseguire il backup del filegroup solo una volta dopo averlo contrassegnato come di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="72a9b-115">You can choose to back up the filegroup only once after marking it read-only.</span></span>  
  
-   <span data-ttu-id="72a9b-116">Ripristino a fasi.</span><span class="sxs-lookup"><span data-stu-id="72a9b-116">Piecemeal restore.</span></span>  
  
    -   <span data-ttu-id="72a9b-117">L'obiettivo di un ripristino a fasi è portare online le parti fondamentali del database, senza attendere tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="72a9b-117">The goal of a piecemeal restore is to bring the critical parts of database online without waiting for all the data.</span></span> <span data-ttu-id="72a9b-118">Un esempio è il caso in cui i dati di un database sono partizionati, in modo che le partizioni meno recenti vengono utilizzate solo raramente.</span><span class="sxs-lookup"><span data-stu-id="72a9b-118">One example is if a database has partitioned data, such that older partitions are only used rarely.</span></span> <span data-ttu-id="72a9b-119">È possibile eseguirne il ripristino solo in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="72a9b-119">You can restore them only on an as-needed basis.</span></span> <span data-ttu-id="72a9b-120">Lo stesso vale per i filegroup in cui sono contenuti, ad esempio, i dati cronologici.</span><span class="sxs-lookup"><span data-stu-id="72a9b-120">Similar for filegroups that contain, for example, historical data.</span></span>  
  
    -   <span data-ttu-id="72a9b-121">Con la correzione della pagina, è possibile correggere i danneggiamenti di pagina ripristinando in particolare la pagina.</span><span class="sxs-lookup"><span data-stu-id="72a9b-121">Using page repair, you can fix page corruption by specifically restoring the page.</span></span> <span data-ttu-id="72a9b-122">Per altre informazioni, vedere [Ripristinare pagine &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="72a9b-122">For more information, see [Restore Pages &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span></span>  
  
## <a name="samples"></a><span data-ttu-id="72a9b-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="72a9b-123">Samples</span></span>  
 <span data-ttu-id="72a9b-124">Negli esempi viene utilizzato lo schema seguente:</span><span class="sxs-lookup"><span data-stu-id="72a9b-124">The examples use the following schema:</span></span>  
  
```  
CREATE DATABASE imoltp  
ON PRIMARY (name = imoltp_primary1, filename = 'c:\data\imoltp_data1.mdf')  
LOG ON (name = imoltp_log, filename = 'c:\data\imoltp_log.ldf')  
GO  
  
ALTER DATABASE imoltp ADD FILE (name = imoltp_primary2, filename = 'c:\data\imoltp_data2.ndf')  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_secondary  
ALTER DATABASE imoltp ADD FILE (name = imoltp_secondary, filename = 'c:\data\imoltp_secondary.ndf') TO FILEGROUP imoltp_secondary  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_mod CONTAINS MEMORY_OPTIMIZED_DATA   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod1', filename='c:\data\imoltp_mod1') TO FILEGROUP imoltp_mod   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod2', filename='c:\data\imoltp_mod2') TO FILEGROUP imoltp_mod   
GO  
```  
  
### <a name="backup"></a><span data-ttu-id="72a9b-125">Backup</span><span class="sxs-lookup"><span data-stu-id="72a9b-125">Backup</span></span>  
 <span data-ttu-id="72a9b-126">In questo esempio viene illustrato come eseguire il backup del filegroup primario e di quello ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="72a9b-126">This sample shows how to backup the primary filegroup and the memory-optimized filegroup.</span></span> <span data-ttu-id="72a9b-127">È necessario specificare insieme sia il filegroup primario sia quello ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="72a9b-127">You must specify both primary and memory-optimized filegroup together.</span></span>  
  
```  
backup database imoltp filegroup='primary', filegroup='imoltp_mod' to disk='c:\data\imoltp.dmp' with init  
```  
  
 <span data-ttu-id="72a9b-128">Nell'esempio seguente viene illustrato che il funzionamento di un backup di filegroup diversi dai filegroup primari e ottimizzati per la memoria è simile ai database senza tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="72a9b-128">The following sample shows that a back up of filegroup(s) other than primary and memory-optimized filegroup works similar to the databases without memory-optimized tables.</span></span> <span data-ttu-id="72a9b-129">Tramite il comando riportato di seguito viene eseguito il backup del filegroup secondario</span><span class="sxs-lookup"><span data-stu-id="72a9b-129">The following command backups up the secondary filegroup</span></span>  
  
```  
backup database imoltp filegroup='imoltp_secondary' to disk='c:\data\imoltp_secondary.dmp' with init  
```  
  
### <a name="restore"></a><span data-ttu-id="72a9b-130">Restore</span><span class="sxs-lookup"><span data-stu-id="72a9b-130">Restore</span></span>  
 <span data-ttu-id="72a9b-131">Nell'esempio seguente viene illustrato come ripristinare insieme il filegroup primario e quello ottimizzato per la memoria.</span><span class="sxs-lookup"><span data-stu-id="72a9b-131">The following sample shows how to restore the primary filegroup and memory-optimized filegroup together.</span></span>  
  
```  
restore database imoltp filegroup = 'primary', filegroup = 'imoltp_mod'   
from disk='c:\data\imoltp.dmp' with partial, norecovery  
  
--restore the transaction log  
 RESTORE LOG [imoltp] FROM DISK = N'c:\data\imoltp_log.dmp' WITH  FILE = 1,  NOUNLOAD,  STATS = 10  
GO  
```  
  
 <span data-ttu-id="72a9b-132">Nell'esempio successivo viene illustrato che il funzionamento del ripristino di filegroup diversi dai filegroup primari e ottimizzati per la memoria è simile ai database senza tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="72a9b-132">The next sample shows that restoring filegroup(s) other than the primary and memory-optimized filegroup works similar to the databases without memory-optimized tables</span></span>  
  
```  
RESTORE DATABASE [imoltp] FILE = N'imoltp_secondary'   
FROM  DISK = N'c:\data\imoltp_secondary.dmp' WITH  FILE = 1,  RECOVERY,  NOUNLOAD,  STATS = 10  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="72a9b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72a9b-133">See Also</span></span>  
 [<span data-ttu-id="72a9b-134">Eseguire il backup, ripristinare e recuperare tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="72a9b-134">Backup, Restore, and Recovery of Memory-Optimized Tables</span></span>](../../database-engine/backup-restore-and-recovery-of-memory-optimized-tables.md)  
  
  
