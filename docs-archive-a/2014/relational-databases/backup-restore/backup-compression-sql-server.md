---
title: Compressione dei backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], backup compression
- backup compression [SQL Server], about backup compression
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- backing up [SQL Server], backup compression
- backup compression [SQL Server]
ms.assetid: 05bc9c4f-3947-4dd4-b823-db77519bd4d2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3291a858d8ef037e7cca92eb2e6abb19aec4da8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624780"
---
# <a name="backup-compression-sql-server"></a><span data-ttu-id="aea2f-102">Compressione backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="aea2f-102">Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="aea2f-103">In questo argomento viene descritta la compressione dei backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , incluse le restrizioni, il compromesso di prestazioni previsto dalla compressione di backup, la configurazione della compressione di backup e il rapporto di compressione.</span><span class="sxs-lookup"><span data-stu-id="aea2f-103">This topic describes the compression of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups, including restrictions, performance trade-off of compressing backups, the configuration of backup compression, and the compression ratio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aea2f-104">Per informazioni sulle edizioni di che [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supportano la compressione dei backup, vedere [funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="aea2f-104">For information which editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support backup compression, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="aea2f-105">Ogni edizione di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e successiva è in grado di ripristinare un backup compresso.</span><span class="sxs-lookup"><span data-stu-id="aea2f-105">Every edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later can restore a compressed backup.</span></span>  
  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="aea2f-106">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="aea2f-106">Benefits</span></span>  
  
-   <span data-ttu-id="aea2f-107">Poiché le dimensioni di un backup compresso sono minori di quelle di un backup non compresso degli stessi dati, la compressione di un backup richiede una minore quantità di I/O del dispositivo e pertanto la velocità del backup aumenta in genere in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="aea2f-107">Because a compressed backup is smaller than an uncompressed backup of the same data, compressing a backup typically requires less device I/O and therefore usually increases backup speed significantly.</span></span>  
  
     <span data-ttu-id="aea2f-108">Per ulteriori informazioni, vedere [Impatto sulle prestazioni della compressione di backup](#PerfImpact), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="aea2f-108">For more information, see [Performance Impact of Compressing Backups](#PerfImpact), later in this topic.</span></span>  
  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="aea2f-109">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="aea2f-109">Restrictions</span></span>  
 <span data-ttu-id="aea2f-110">Ai backup compressi vengono applicate le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aea2f-110">The following restrictions apply to compressed backups:</span></span>  
  
-   <span data-ttu-id="aea2f-111">I backup compressi e non compressi non possono coesistere in un set di supporti.</span><span class="sxs-lookup"><span data-stu-id="aea2f-111">Compressed and uncompressed backups cannot co-exist in a media set.</span></span>  
  
-   <span data-ttu-id="aea2f-112">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è possibile leggere i backup compressi.</span><span class="sxs-lookup"><span data-stu-id="aea2f-112">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read compressed backups.</span></span>  
  
-   <span data-ttu-id="aea2f-113">NTbackups non può condividere un nastro con backup compressi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aea2f-113">NTbackups cannot share a tape with compressed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
  
##  <a name="performance-impact-of-compressing-backups"></a><a name="PerfImpact"></a> <span data-ttu-id="aea2f-114">Impatto sulle prestazioni della compressione di backup</span><span class="sxs-lookup"><span data-stu-id="aea2f-114">Performance Impact of Compressing Backups</span></span>  
 <span data-ttu-id="aea2f-115">Per impostazione predefinita, la compressione aumenta significativamente l'utilizzo della CPU, il che può avere un impatto negativo sulle operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="aea2f-115">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="aea2f-116">Quindi potrebbe essere necessario creare backup compressi con priorità bassa in una sessione in cui l'utilizzo della CPU è limitato da[Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="aea2f-116">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="aea2f-117">Per ulteriori informazioni, vedere [Utilizzo di Resource Governor per limitare l'utilizzo della CPU da parte della compressione dei backup &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="aea2f-117">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
 <span data-ttu-id="aea2f-118">Per conoscere le prestazioni di I/O del backup, è possibile isolare l'I/O del backup in/da dispositivi valutando i seguenti ordinamenti di contatori delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="aea2f-118">To obtain a good picture of your backup I/O performance, you can isolate the backup I/O to or from devices by evaluating the following sorts of performance counters:</span></span>  
  
-   <span data-ttu-id="aea2f-119">Contatori delle prestazioni di I/O di Windows, ad esempio i contatori del disco fisico</span><span class="sxs-lookup"><span data-stu-id="aea2f-119">Windows I/O performance counters, such as the physical-disk counters</span></span>  
  
-   <span data-ttu-id="aea2f-120">Contatore **Byte/sec velocità effettiva dispositivo** dell'oggetto [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md)</span><span class="sxs-lookup"><span data-stu-id="aea2f-120">The **Device Throughput Bytes/sec** counter of the [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md) object</span></span>  
  
-   <span data-ttu-id="aea2f-121">Contatore **Velocità effettiva backup o ripristino/sec** dell'oggetto [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md)</span><span class="sxs-lookup"><span data-stu-id="aea2f-121">The **Backup/Restore Throughput/sec** counter of the [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md) object</span></span>  
  
 <span data-ttu-id="aea2f-122">Per informazioni sui contatori di Windows, vedere la Guida di Windows.</span><span class="sxs-lookup"><span data-stu-id="aea2f-122">For information about Windows counters, see Windows help.</span></span> <span data-ttu-id="aea2f-123">Per informazioni su come usare i contatori di SQL Server, vedere [Utilizzare oggetti di SQL Server](../performance-monitor/use-sql-server-objects.md).</span><span class="sxs-lookup"><span data-stu-id="aea2f-123">For information about how to work with SQL Server counters, see [Use SQL Server Objects](../performance-monitor/use-sql-server-objects.md).</span></span>  
  
  
##  <a name="calculate-the-compression-ratio-of-a-compressed-backup"></a><a name="CompressionRatio"></a> <span data-ttu-id="aea2f-124">Calcolare il rapporto di compressione di un backup compresso</span><span class="sxs-lookup"><span data-stu-id="aea2f-124">Calculate the Compression Ratio of a Compressed Backup</span></span>  
 <span data-ttu-id="aea2f-125">Per calcolare il rapporto di compressione di un backup, usare i valori per il backup nelle colonne **backup_size** e **compressed_backup_size** della tabella di cronologia [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) , come segue:</span><span class="sxs-lookup"><span data-stu-id="aea2f-125">To calculate the compression ratio of a backup, use the values for the backup in the **backup_size** and **compressed_backup_size** columns of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) history table, as follows:</span></span>  
  
 <span data-ttu-id="aea2f-126">**backup_size**:**compressed_backup_size**</span><span class="sxs-lookup"><span data-stu-id="aea2f-126">**backup_size**:**compressed_backup_size**</span></span>  
  
 <span data-ttu-id="aea2f-127">Una compressione 3:1, ad esempio, indica un risparmio approssimativo del 66% di spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="aea2f-127">For example, a 3:1 compression ratio indicates that you are saving about 66% on disk space.</span></span> <span data-ttu-id="aea2f-128">Per eseguire una query su queste colonne, è possibile utilizzare la seguente istruzione Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="aea2f-128">To query on these columns, you can use the following Transact-SQL statement:</span></span>  
  
```  
SELECT backup_size/compressed_backup_size FROM msdb..backupset;  
```  
  
 <span data-ttu-id="aea2f-129">Il rapporto di compressione di un backup compresso dipende dai dati compressi.</span><span class="sxs-lookup"><span data-stu-id="aea2f-129">The compression ratio of a compressed backup depends on the data that has been compressed.</span></span> <span data-ttu-id="aea2f-130">Vari fattori possono avere un impatto sul rapporto di compressione ottenuto.</span><span class="sxs-lookup"><span data-stu-id="aea2f-130">A variety of factors can impact the compression ratio obtained.</span></span> <span data-ttu-id="aea2f-131">Di seguito vengono indicati alcuni dei fattori principali:</span><span class="sxs-lookup"><span data-stu-id="aea2f-131">Major factors include:</span></span>  
  
-   <span data-ttu-id="aea2f-132">Tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="aea2f-132">The type of data.</span></span>  
  
     <span data-ttu-id="aea2f-133">I dati di tipo carattere vengono compressi maggiormente rispetto ad altri tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="aea2f-133">Character data compresses more than other types of data.</span></span>  
  
-   <span data-ttu-id="aea2f-134">Coerenza dei dati tra le righe in una pagina.</span><span class="sxs-lookup"><span data-stu-id="aea2f-134">The consistency of the data among rows on a page.</span></span>  
  
     <span data-ttu-id="aea2f-135">In genere, se una pagina contiene molte righe in cui un campo contiene lo stesso valore, potrebbe verificarsi una significativa compressione per tale valore.</span><span class="sxs-lookup"><span data-stu-id="aea2f-135">Typically, if a page contains several rows in which a field contains the same value, significant compression might occur for that value.</span></span> <span data-ttu-id="aea2f-136">Invece, per un database che contiene dati casuali o che contiene solo una grande riga per pagina, un backup compresso avrebbe pressoché le stesse dimensioni di un backup non compresso.</span><span class="sxs-lookup"><span data-stu-id="aea2f-136">In contrast, for a database that contains random data or that contains only one large row per page, a compressed backup would be almost as large as an uncompressed backup.</span></span>  
  
-   <span data-ttu-id="aea2f-137">Crittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="aea2f-137">Whether the data is encrypted.</span></span>  
  
     <span data-ttu-id="aea2f-138">I dati crittografati vengono compressi molto meno rispetto ai dati equivalenti non crittografati.</span><span class="sxs-lookup"><span data-stu-id="aea2f-138">Encrypted data compresses significantly less than equivalent unencrypted data.</span></span> <span data-ttu-id="aea2f-139">Se si utilizza Transparent Data Encryption per crittografare un intero database, la compressione dei backup potrebbe non garantire una riduzione significativa, e in alcuni casi neanche minima, delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="aea2f-139">If transparent data encryption is used to encrypt an entire database, compressing backups might not reduce their size by much, if at all.</span></span>  
  
-   <span data-ttu-id="aea2f-140">Compressione del database,</span><span class="sxs-lookup"><span data-stu-id="aea2f-140">Whether the database is compressed.</span></span>  
  
     <span data-ttu-id="aea2f-141">Se il database è compresso, la compressione potrebbe ridurre di poco o non ridurre le dimensioni dei backup.</span><span class="sxs-lookup"><span data-stu-id="aea2f-141">If the database is compressed, compressing backups might not reduce their size by much, if at all.</span></span>  
  
  
##  <a name="allocation-of-space-for-the-backup-file"></a><a name="Allocation"></a> <span data-ttu-id="aea2f-142">Allocazione di spazio per il file di backup</span><span class="sxs-lookup"><span data-stu-id="aea2f-142">Allocation of Space for the Backup File</span></span>  
 <span data-ttu-id="aea2f-143">Per i backup compressi le dimensioni dei file di backup finale dipende dal livello di compressione dei dati e questo valore non è noto finché l'operazione di backup non viene completata.</span><span class="sxs-lookup"><span data-stu-id="aea2f-143">For compressed backups, the size of the final backup file depends on how compressible the data is, and this is unknown before the backup operation finishes.</span></span>  <span data-ttu-id="aea2f-144">Per impostazione predefinita, quando si esegue il backup di un database mediante compressione, il motore di database utilizza pertanto un algoritmo di preallocazione per il file di backup.</span><span class="sxs-lookup"><span data-stu-id="aea2f-144">Therefore, by default, when backing up a database using compression, the Database Engine uses a pre-allocation algorithm for the backup file.</span></span> <span data-ttu-id="aea2f-145">Tramite questo algoritmo viene preallocata una percentuale predefinita delle dimensioni del database per il file di backup.</span><span class="sxs-lookup"><span data-stu-id="aea2f-145">This algorithm pre-allocates a predefined percentage of the size of the database for the backup file.</span></span> <span data-ttu-id="aea2f-146">Se durante un'operazione di backup è necessaria una quantità di spazio maggiore, il motore di database aumenta le dimensioni del file.</span><span class="sxs-lookup"><span data-stu-id="aea2f-146">If more space is needed during the backup operation, the Database Engine grows the file.</span></span> <span data-ttu-id="aea2f-147">Se le dimensioni finali sono inferiori allo spazio allocato, al termine dell'operazione di backup il motore di database compatta il file in base alle dimensioni finali effettive del backup.</span><span class="sxs-lookup"><span data-stu-id="aea2f-147">If the final size is less than the allocated space, at the end of the backup operation, the Database Engine shrinks the file to the actual final size of the backup.</span></span>  
  
 <span data-ttu-id="aea2f-148">Per consentire l'aumento del file di backup solo di quanto necessario per raggiungere le relative dimensioni finali, utilizzare il flag di traccia 3042.</span><span class="sxs-lookup"><span data-stu-id="aea2f-148">To allow the backup file to grow only as needed to reach its final size, use trace flag 3042.</span></span> <span data-ttu-id="aea2f-149">Il flag di traccia 3042 fa in modo che durante l'operazione di backup venga ignorato l'algoritmo di preallocazione di compressione di backup predefinito.</span><span class="sxs-lookup"><span data-stu-id="aea2f-149">Trace flag 3042 causes the backup operation to bypass the default backup compression pre-allocation algorithm.</span></span> <span data-ttu-id="aea2f-150">Questo flag di traccia è utile se è necessario risparmiare spazio allocando solo le dimensioni effettive necessarie per il backup compresso.</span><span class="sxs-lookup"><span data-stu-id="aea2f-150">This trace flag is useful if you need to save on space by allocating only the actual size required for the compressed backup.</span></span> <span data-ttu-id="aea2f-151">L'utilizzo di questo flag di traccia può tuttavia comportare un effetto leggermente negativo sulle prestazioni, vale a dire un possibile aumento della durata dell'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="aea2f-151">However, using this trace flag might cause a slight performance penalty (a possible increase in the duration of the backup operation).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="aea2f-152">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="aea2f-152">Related Tasks</span></span>  
  
-   [<span data-ttu-id="aea2f-153">Configura compressione backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aea2f-153">Configure Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
-   [<span data-ttu-id="aea2f-154">Visualizzare o configurare l'opzione di configurazione del server backup compression default</span><span class="sxs-lookup"><span data-stu-id="aea2f-154">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
-   [<span data-ttu-id="aea2f-155">Utilizzo di Resource Governor per limitare l'utilizzo della CPU da parte della compressione dei backup &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aea2f-155">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="aea2f-156">DBCC TRACEON &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aea2f-156">DBCC TRACEON &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql)  
  
-   [<span data-ttu-id="aea2f-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aea2f-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceoff-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="aea2f-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aea2f-158">See Also</span></span>  
 <span data-ttu-id="aea2f-159">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aea2f-159">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="aea2f-160">Flag di traccia &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aea2f-160">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
