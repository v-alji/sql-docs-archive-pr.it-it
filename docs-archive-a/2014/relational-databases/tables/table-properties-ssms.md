---
title: Proprietà tabella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.tableproperties.storage.f1
- sql12.SWB.SELECTCOLUMNS.F1
- sql12.swb.tableproperties.filetable.f1
- sql12.swb.tableproperties.general.f1
- sql12.swb.tableproperties.changetracking.f1
ms.assetid: ad8a2fd4-f092-4c0f-be85-54ce8b9d725a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 037e56649d3473e3fe09b9533bcc96b4729870d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629273"
---
# <a name="table-properties"></a><span data-ttu-id="fb7b3-102">Table Properties</span><span class="sxs-lookup"><span data-stu-id="fb7b3-102">Table Properties</span></span>
  <span data-ttu-id="fb7b3-103">In questo argomento vengono descritte le proprietà della tabella visualizzate nella finestra di dialogo Proprietà tabella in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb7b3-103">This topic describes the table properties that are displayed in the Table Properties dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="fb7b3-104">Per altre informazioni su come visualizzare queste proprietà, vedere [Visualizzare la definizione di una tabella](view-the-table-definition.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-104">For more information about how to display these properties, see [View the Table Definition](view-the-table-definition.md).</span></span>  
  
 <span data-ttu-id="fb7b3-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-105">**In This Topic**</span></span>  
  
1.  [<span data-ttu-id="fb7b3-106">Pagina Generale</span><span class="sxs-lookup"><span data-stu-id="fb7b3-106">General Page</span></span>](#GeneralPage)  
  
2.  [<span data-ttu-id="fb7b3-107">Pagina Rilevamento modifiche</span><span class="sxs-lookup"><span data-stu-id="fb7b3-107">Change Tracking Page</span></span>](#ChangeTracking)  
  
3.  [<span data-ttu-id="fb7b3-108">Pagina di Tabella di File</span><span class="sxs-lookup"><span data-stu-id="fb7b3-108">File Table Page</span></span>](#FileTable)  
  
4.  [<span data-ttu-id="fb7b3-109">Pagina Archivio</span><span class="sxs-lookup"><span data-stu-id="fb7b3-109">Storage Page</span></span>](#Storage)  
  
##  <a name="general-page"></a><a name="GeneralPage"></a> <span data-ttu-id="fb7b3-110">Pagina Generale</span><span class="sxs-lookup"><span data-stu-id="fb7b3-110">General Page</span></span>  
 <span data-ttu-id="fb7b3-111">**Database**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-111">**Database**</span></span>  
 <span data-ttu-id="fb7b3-112">Nome del database che contiene la tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-112">The name of the database containing this table.</span></span>  
  
 <span data-ttu-id="fb7b3-113">**Server**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-113">**Server**</span></span>  
 <span data-ttu-id="fb7b3-114">Nome dell'istanza del server corrente.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-114">The name of the current server instance.</span></span>  
  
 <span data-ttu-id="fb7b3-115">**Utente**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-115">**User**</span></span>  
 <span data-ttu-id="fb7b3-116">Nome dell'utente della connessione.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-116">The name of the user of this connection.</span></span>  
  
 <span data-ttu-id="fb7b3-117">**Data creazione**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-117">**Created Date**</span></span>  
 <span data-ttu-id="fb7b3-118">Data e ora di creazione della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-118">The date and time that the table was created.</span></span>  
  
 <span data-ttu-id="fb7b3-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-119">**Name**</span></span>  
 <span data-ttu-id="fb7b3-120">Nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-120">The name of the table.</span></span>  
  
 <span data-ttu-id="fb7b3-121">**Schema**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-121">**Schema**</span></span>  
 <span data-ttu-id="fb7b3-122">Schema proprietario della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-122">The schema that owns the table.</span></span>  
  
 <span data-ttu-id="fb7b3-123">**Oggetto di sistema**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-123">**System object**</span></span>  
 <span data-ttu-id="fb7b3-124">Indica che la tabella è una tabella di sistema usata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per contenere informazioni interne.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-124">Indicates this table is a system table, used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to contain internal information.</span></span> <span data-ttu-id="fb7b3-125">È consigliabile non modificare direttamente le tabelle di sistema o fare riferimento a tali tabelle.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-125">Users should not directly change or reference system tables.</span></span>  
  
 <span data-ttu-id="fb7b3-126">**ANSI NULLs**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-126">**ANSI NULLs**</span></span>  
 <span data-ttu-id="fb7b3-127">Indica se l'oggetto è stato creato con l'opzione ANSI NULLs impostata su ON.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-127">Indicates if the object was created with the ANSI NULLs option set to ON.</span></span> <span data-ttu-id="fb7b3-128">Per altre informazioni, vedere [SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-128">For more information, see [SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql)</span></span>  
  
 <span data-ttu-id="fb7b3-129">**Identificatore delimitato**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-129">**Quoted identifier**</span></span>  
 <span data-ttu-id="fb7b3-130">Indica se l'oggetto è stato creato con l'opzione quoted identifier impostata su ON.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-130">Indicates if the object was created with the quoted identifier option set to ON.</span></span> <span data-ttu-id="fb7b3-131">Per altre informazioni, vedere [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-131">For more information, see [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql)</span></span>  
  
 <span data-ttu-id="fb7b3-132">**Escalation blocchi**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-132">**Lock Escalation**</span></span>  
 <span data-ttu-id="fb7b3-133">Indica la granularità dell'escalation dei blocchi della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-133">Indicates the lock escalation granularity of the table.</span></span> <span data-ttu-id="fb7b3-134">Per altre informazioni sui blocchi nel motore di database, vedere [Guida per il controllo delle versioni delle righe e il blocco della transazione di SQL Server](https://msdn.microsoft.com/library/jj856598.aspx).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-134">For more information about locking in the Database Engine, see [SQL Server Transaction Locking and Row Versioning Guide](https://msdn.microsoft.com/library/jj856598.aspx).</span></span> <span data-ttu-id="fb7b3-135">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fb7b3-135">Possible values are:</span></span>  
  
 <span data-ttu-id="fb7b3-136">AUTO</span><span class="sxs-lookup"><span data-stu-id="fb7b3-136">AUTO</span></span>  
 <span data-ttu-id="fb7b3-137">Questa opzione consente al [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] di selezionare la granularità dell'escalation dei blocchi appropriata per lo schema della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-137">This option allows the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to select the lock escalation granularity that is appropriate for the table schema.</span></span>  
  
-   <span data-ttu-id="fb7b3-138">Se la tabella è partizionata, sarà consentita l'escalation dei blocchi nella granularità a livello di heap o albero B (HoBT).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-138">If the table is partitioned, lock escalation will be allowed to the heap or B-tree (HoBT) granularity.</span></span> <span data-ttu-id="fb7b3-139">Una volta eseguita l'escalation del blocco nel livello HoBT, non verrà eseguita alcuna successiva escalation del blocco nella granularità TABLE.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-139">After the lock is escalated to the HoBT level, the lock will not be escalated later to TABLE granularity.</span></span>  
  
-   <span data-ttu-id="fb7b3-140">Se la tabella non è partizionata, l'escalation blocchi verrà eseguita nella granularità TABLE.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-140">If the table is not partitioned, the lock escalation will be done to the TABLE granularity.</span></span>  
  
 <span data-ttu-id="fb7b3-141">TABLE</span><span class="sxs-lookup"><span data-stu-id="fb7b3-141">TABLE</span></span>  
 <span data-ttu-id="fb7b3-142">L'escalation dei blocchi viene eseguita con una granularità a livello di tabella, indipendentemente dal fatto che la tabella sia o meno partizionata.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-142">Lock escalation will be done at table-level granularity regardless of whether the table is partitioned or not partitioned.</span></span> <span data-ttu-id="fb7b3-143">TABLE rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-143">TABLE is the default value.</span></span>  
  
 <span data-ttu-id="fb7b3-144">DISABLE</span><span class="sxs-lookup"><span data-stu-id="fb7b3-144">DISABLE</span></span>  
 <span data-ttu-id="fb7b3-145">Evita che venga eseguita l'escalation blocchi nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-145">Prevents lock escalation in most cases.</span></span> <span data-ttu-id="fb7b3-146">I blocchi a livello di tabella non vengono completamente disattivati.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-146">Table-level locks are not completely disallowed.</span></span> <span data-ttu-id="fb7b3-147">Quando si esegue l'analisi di una tabella che non dispone di alcun indice cluster nel livello di isolamento serializzabile, il [!INCLUDE[ssDE](../../includes/ssde-md.md)] deve acquisire un blocco di tabella per proteggere l'integrità dei dati.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-147">For example, when you are scanning a table that has no clustered index under the serializable isolation level, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] must take a table lock to protect data integrity.</span></span>  
  
 <span data-ttu-id="fb7b3-148">**Tabella replicata**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-148">**Table is replicated**</span></span>  
 <span data-ttu-id="fb7b3-149">Indica se la tabella è stata replicata in un altro database usando la replica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb7b3-149">Indicates when the table is replicated to another database using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span> <span data-ttu-id="fb7b3-150">I possibili valori sono `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-150">Possible values are `True` or `False`.</span></span>  
  
##  <a name="change-tracking-page"></a><a name="ChangeTracking"></a><span data-ttu-id="fb7b3-151">Pagina Rilevamento modifiche</span><span class="sxs-lookup"><span data-stu-id="fb7b3-151">Change Tracking Page</span></span>  
 <span data-ttu-id="fb7b3-152">**Rilevamento delle modifiche**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-152">**Change Tracking**</span></span>  
 <span data-ttu-id="fb7b3-153">Indica se il rilevamento delle modifiche è abilitato per la tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-153">Indicates whether change tracking is enabled for the table.</span></span> <span data-ttu-id="fb7b3-154">Il valore predefinito è `False`.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-154">The default value is `False`.</span></span>  
  
 <span data-ttu-id="fb7b3-155">Questa opzione è disponibile solo quando il rilevamento delle modifiche è abilitato per il database.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-155">This option is available only when change tracking is enabled for the database.</span></span>  
  
 <span data-ttu-id="fb7b3-156">Per abilitare il rilevamento delle modifiche, è necessario che la tabella disponga di una chiave primaria e che si disponga dell'autorizzazione per modificare la tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-156">To enable change tracking, the table must have a primary key, and you must have permission to modify the table.</span></span> <span data-ttu-id="fb7b3-157">È anche possibile configurare il rilevamento delle modifiche usando [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-157">You can configure change tracking by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
 <span data-ttu-id="fb7b3-158">**Colonne di rilevamento aggiornate**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-158">**Track Columns Updated**</span></span>  
 <span data-ttu-id="fb7b3-159">Indica se [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] rileva le colonne che sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-159">Indicates whether the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] tracks which columns were updated.</span></span>  
  
 <span data-ttu-id="fb7b3-160">Per altre informazioni sul rilevamento delle modifiche, vedere [Informazioni sul rilevamento delle modifiche &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-160">For more information about Change Tracking, see [About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md).</span></span>  
  
##  <a name="filetable-page"></a><a name="FileTable"></a><span data-ttu-id="fb7b3-161">Pagina FileTable</span><span class="sxs-lookup"><span data-stu-id="fb7b3-161">FileTable Page</span></span>  
 <span data-ttu-id="fb7b3-162">Consente di visualizzare le proprietà della tabella correlate alle tabelle FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-162">Displays properties of the table related to FileTables.</span></span> <span data-ttu-id="fb7b3-163">Per altre informazioni, vedere [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-163">For more information, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span>  
  
 <span data-ttu-id="fb7b3-164">**Regole di confronto colonna Name tabella FileTable**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-164">**FileTable name column collation**</span></span>  
 <span data-ttu-id="fb7b3-165">Regole di confronto applicate alla colonna **Name** in una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-165">The collation that is applied to the **Name** column in a FileTable.</span></span> <span data-ttu-id="fb7b3-166">La colonna **Name** contiene i nomi di file e directory.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-166">The **Name** column contains file and directory names.</span></span>  
  
 <span data-ttu-id="fb7b3-167">**Nome di directory FileTable**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-167">**FileTable directory name**</span></span>  
 <span data-ttu-id="fb7b3-168">Cartella radice per la tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-168">The root folder for the FileTable.</span></span>  
  
 <span data-ttu-id="fb7b3-169">**Spazio dei nomi FileTable abilitato**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-169">**FileTable namespace enabled**</span></span>  
 <span data-ttu-id="fb7b3-170">Se impostato su `True`, questo valore indica che la tabella è una tabella FileTable.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-170">When `True`, this value indicates that the table is a FileTable.</span></span> <span data-ttu-id="fb7b3-171">Se si modifica questo valore in `False`, la tabella FileTable viene modificata in una comune tabella utente.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-171">If you change this value to `False`, you are changing the FileTable to an ordinary user table.</span></span> <span data-ttu-id="fb7b3-172">Se in seguito si desidera modificare di nuovo la tabella in tabella FileTable, questa dovrà superare un controllo di coerenza per tabelle FileTable affinché la conversione riesca.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-172">If you later want to change the table back to a FileTable, the table will have to pass a FileTable consistency check before the conversion succeeds.</span></span>  
  
##  <a name="storage-page"></a><a name="Storage"></a><span data-ttu-id="fb7b3-173">Pagina archiviazione</span><span class="sxs-lookup"><span data-stu-id="fb7b3-173">Storage Page</span></span>  
 <span data-ttu-id="fb7b3-174">Consente di visualizzare le proprietà relative all'archiviazione della tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-174">Displays the storage related properties of the selected table.</span></span>  
  
### <a name="compression"></a><span data-ttu-id="fb7b3-175">Compressione</span><span class="sxs-lookup"><span data-stu-id="fb7b3-175">Compression</span></span>  
 <span data-ttu-id="fb7b3-176">**Tipo di compressione**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-176">**Compression type**</span></span>  
 <span data-ttu-id="fb7b3-177">Tipo di compressione della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-177">The compression type of the table.</span></span> <span data-ttu-id="fb7b3-178">Questa proprietà è disponibile solo per le tabelle non partizionate.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-178">This property is only available for tables that are not partitioned.</span></span> <span data-ttu-id="fb7b3-179">Per altre informazioni, vedere [Data Compression](../data-compression/data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-179">For more information, see [Data Compression](../data-compression/data-compression.md).</span></span>  
  
 <span data-ttu-id="fb7b3-180">**Partizioni che usano la compressione di pagina**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-180">**Partitions using page compression**</span></span>  
 <span data-ttu-id="fb7b3-181">Numeri di partizioni che usano la compressione di pagina.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-181">The partition numbers that are using page compression.</span></span> <span data-ttu-id="fb7b3-182">Questa proprietà è disponibile solo per le tabelle partizionate.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-182">This property is only available for partitioned tables.</span></span>  
  
 <span data-ttu-id="fb7b3-183">**Partizioni non compresse**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-183">**Partitions not compressed**</span></span>  
 <span data-ttu-id="fb7b3-184">Numeri di partizioni non compresse.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-184">The partition numbers that are not compressed.</span></span> <span data-ttu-id="fb7b3-185">Questa proprietà è disponibile solo per le tabelle partizionate.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-185">This property is only available for partitioned tables.</span></span>  
  
 <span data-ttu-id="fb7b3-186">**Partizioni che usano la compressione di riga**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-186">**Partitions using row compression**</span></span>  
 <span data-ttu-id="fb7b3-187">Numeri di partizioni che usano la compressione di riga.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-187">The partition numbers that are using row compression.</span></span> <span data-ttu-id="fb7b3-188">Questa proprietà è disponibile solo per le tabelle partizionate.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-188">This property is only available for partitioned tables.</span></span>  
  
### <a name="filegroup"></a><span data-ttu-id="fb7b3-189">Filegroup</span><span class="sxs-lookup"><span data-stu-id="fb7b3-189">Filegroup</span></span>  
 <span data-ttu-id="fb7b3-190">**Filegroup dati di testo**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-190">**Text filegroup**</span></span>  
 <span data-ttu-id="fb7b3-191">Nome del filegroup che contiene i dati di testo della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-191">The name of the filegroup that contains the text data for the table.</span></span>  
  
 <span data-ttu-id="fb7b3-192">**Filegroup**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-192">**Filegroup**</span></span>  
 <span data-ttu-id="fb7b3-193">Nome del filegroup che contiene la tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-193">The name of the filegroup that contains the table.</span></span>  
  
 <span data-ttu-id="fb7b3-194">**Tabella partizionata**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-194">**Table is partitioned**</span></span>  
 <span data-ttu-id="fb7b3-195">I valori possibili sono `True` e `False`.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-195">Possible values are `True` and `False`.</span></span>  
  
 <span data-ttu-id="fb7b3-196">**Filegroup FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-196">**Filestream filegroup**</span></span>  
 <span data-ttu-id="fb7b3-197">Specificare il nome del filegroup di dati FILESTREAM se la tabella contiene una colonna `varbinary(max)` con l'attributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-197">Specify the name of the FILESTREAM data filegroup if the table has a `varbinary(max)` column that has the FILESTREAM attribute.</span></span> <span data-ttu-id="fb7b3-198">Il filegroup di dati FILESTREAM predefinito è indicato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-198">The default value is the default FILESTREAM data filegroup.</span></span>  
  
 <span data-ttu-id="fb7b3-199">Se la tabella non contiene dati FILESTREAM, il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-199">If the table does not contain FILESTREAM data, the field is blank.</span></span>  
  
### <a name="general"></a><span data-ttu-id="fb7b3-200">Generale</span><span class="sxs-lookup"><span data-stu-id="fb7b3-200">General</span></span>  
 <span data-ttu-id="fb7b3-201">**Formato di archiviazione vardecimal abilitato**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-201">**Vardecimal storage format is enabled**</span></span>  
 <span data-ttu-id="fb7b3-202">Se `True` , questo valore di sola lettura indica che `decimal` `numeric` i tipi di dati e vengono archiviati utilizzando il formato di archiviazione vardecimal.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-202">When `True`, this read-only value indicates that `decimal` and `numeric` data types are stored by using the vardecimal storage format.</span></span> <span data-ttu-id="fb7b3-203">Per modificare questa opzione, usare l' `vardecimal storage format` opzione di [sp_tableoption](/sql/relational-databases/system-stored-procedures/sp-tableoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-203">To change this option, use the `vardecimal storage format` option of [sp_tableoption](/sql/relational-databases/system-stored-procedures/sp-tableoption-transact-sql).</span></span> <span data-ttu-id="fb7b3-204">Il formato di archiviazione vardecimal è deprecato.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-204">Vardecimal storage format is deprecated.</span></span> <span data-ttu-id="fb7b3-205">ed è necessario usare il tipo di compressione ROW.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-205">Use ROW compression instead.</span></span>  
  
 <span data-ttu-id="fb7b3-206">**Spazio degli indici**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-206">**Index space**</span></span>  
 <span data-ttu-id="fb7b3-207">Quantità di spazio occupata dagli indici nella tabella, espresso in megabyte.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-207">The amount of space in megabytes that the indexes occupy in the table.</span></span> <span data-ttu-id="fb7b3-208">Questo valore non include lo spazio usato dagli indici XML per la tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-208">This value does not include XML index space usage for the table.</span></span> <span data-ttu-id="fb7b3-209">Se gli indici XML appartengono alla tabella, usare in alternativa [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="fb7b3-209">If XML indexes belong to the table, use [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="fb7b3-210">**Conteggio righe**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-210">**Row count**</span></span>  
 <span data-ttu-id="fb7b3-211">Numero di righe nella tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-211">The number of rows in the table.</span></span>  
  
 <span data-ttu-id="fb7b3-212">**Spazio dati**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-212">**Data space**</span></span>  
 <span data-ttu-id="fb7b3-213">Quantità di spazio occupata dai dati nella tabella, espressa in megabyte.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-213">The amount of space in megabytes that the data occupies in the table.</span></span>  
  
### <a name="partitioning"></a><span data-ttu-id="fb7b3-214">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="fb7b3-214">Partitioning</span></span>  
 <span data-ttu-id="fb7b3-215">Questa sezione è disponibile solo se la tabella è partizionata.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-215">This section is only available if the table is partitioned.</span></span> <span data-ttu-id="fb7b3-216">Per ulteriori informazioni, vedere [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b3-216">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="fb7b3-217">**Colonna di partizione**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-217">**Partition column**</span></span>  
 <span data-ttu-id="fb7b3-218">Nome della colonna in relazione alla quale è partizionata la tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-218">The name of the column on which the table is partitioned.</span></span>  
  
 <span data-ttu-id="fb7b3-219">**Schema di partizione**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-219">**Partition scheme**</span></span>  
 <span data-ttu-id="fb7b3-220">Nome dello schema di partizione, se la tabella è partizionata.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-220">Name of the partition scheme if the table is partitioned.</span></span> <span data-ttu-id="fb7b3-221">Se la tabella non è partizionata, il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-221">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="fb7b3-222">**Numero di partizioni**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-222">**Number of partitions**</span></span>  
 <span data-ttu-id="fb7b3-223">Numero di partizioni della tabella.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-223">The number of partitions in the table.</span></span>  
  
 <span data-ttu-id="fb7b3-224">**Schema di partizione FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="fb7b3-224">**FILESTREAM partition scheme**</span></span>  
 <span data-ttu-id="fb7b3-225">Nome dello schema di partizione FILESTREAM, se la tabella è partizionata.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-225">The name of the FILESTREAM partition scheme if the table is partitioned.</span></span> <span data-ttu-id="fb7b3-226">Se la tabella non è partizionata, il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fb7b3-226">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="fb7b3-227">Lo schema di partizione FILESTREAM deve essere simmetrico rispetto allo schema specificato nell'opzione **Schema partizione** .</span><span class="sxs-lookup"><span data-stu-id="fb7b3-227">The FILESTREAM partition scheme must be symmetric to the scheme that is specified in the **Partition scheme** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7b3-228">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb7b3-228">See Also</span></span>  
 <span data-ttu-id="fb7b3-229">[Visualizzare la definizione della tabella](view-the-table-definition.md) </span><span class="sxs-lookup"><span data-stu-id="fb7b3-229">[View the Table Definition](view-the-table-definition.md) </span></span>  
 [<span data-ttu-id="fb7b3-230">Modificare colonne &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="fb7b3-230">Modify Columns &#40;Database Engine&#41;</span></span>](../tables/modify-columns-database-engine.md)  
  
  
