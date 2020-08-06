---
title: Backup di sola copia (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- copy-only backups [SQL Server]
- COPY_ONLY option [BACKUP statement]
- backups [SQL Server], copy-only backups
ms.assetid: f82d6918-a5a7-4af8-868e-4247f5b00c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc74d7b1bba2a0163ac9edefb5d465c54ef6296c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637922"
---
# <a name="copy-only-backups-sql-server"></a><span data-ttu-id="35d15-102">Backup di sola copia (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="35d15-102">Copy-Only Backups (SQL Server)</span></span>
  <span data-ttu-id="35d15-103">Un *backup di sola copia* è un backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indipendente dalla sequenza di backup convenzionali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35d15-103">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="35d15-104">In genere, l'esecuzione di un backup comporta la modifica del database e influisce sulla modalità di ripristino dei backup successivi.</span><span class="sxs-lookup"><span data-stu-id="35d15-104">Usually, taking a backup changes the database and affects how later backups are restored.</span></span> <span data-ttu-id="35d15-105">In alcuni casi, tuttavia, è utile eseguire un backup per uno scopo speciale senza influire sulle procedure generali di backup e ripristino del database.</span><span class="sxs-lookup"><span data-stu-id="35d15-105">However, occasionally, it is useful to take a backup for a special purpose without affecting the overall backup and restore procedures for the database.</span></span> <span data-ttu-id="35d15-106">I backup di sola copia hanno questo scopo.</span><span class="sxs-lookup"><span data-stu-id="35d15-106">Copy-only backups serve this purpose.</span></span>  
  
 <span data-ttu-id="35d15-107">I tipi di backup di sola copia sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="35d15-107">The types of copy-only backups are as follows:</span></span>  
  
-   <span data-ttu-id="35d15-108">Backup completi di sola copia (tutti i modelli di recupero)</span><span class="sxs-lookup"><span data-stu-id="35d15-108">Copy-only full backups (all recovery models)</span></span>  
  
     <span data-ttu-id="35d15-109">Un backup di sola copia non può essere utilizzato come base differenziale o come backup differenziale e non influisce sulla base differenziale.</span><span class="sxs-lookup"><span data-stu-id="35d15-109">A copy-only backup cannot serve as a differential base or differential backup and does not affect the differential base.</span></span>  
  
     <span data-ttu-id="35d15-110">Ripristinare un backup completo di sola copia equivale al ripristino di un qualsiasi altro backup completo.</span><span class="sxs-lookup"><span data-stu-id="35d15-110">Restoring a copy-only full backup is the same as restoring any other full backup.</span></span>  
  
-   <span data-ttu-id="35d15-111">Backup del log di sola copia (solo modello di recupero con registrazione completa e modello di recupero con registrazione minima delle operazioni bulk)</span><span class="sxs-lookup"><span data-stu-id="35d15-111">Copy-only log backups (full recovery model and bulk-logged recovery model only)</span></span>  
  
     <span data-ttu-id="35d15-112">Un backup del log di sola copia mantiene il punto di archiviazione del log esistente e pertanto non influisce sulla sequenza dei backup del log regolari.</span><span class="sxs-lookup"><span data-stu-id="35d15-112">A copy-only log backup preserves the existing log archive point and, therefore, does not affect the sequencing of regular log backups.</span></span> <span data-ttu-id="35d15-113">I backup del log di sola copia in genere non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="35d15-113">Copy-only log backups are typically unnecessary.</span></span> <span data-ttu-id="35d15-114">È invece possibile creare un nuovo backup del log di routine (con WITH NORECOVERY) e quindi utilizzare il backup in questione insieme a tutti i backup del log precedenti necessari per la sequenza di ripristino.</span><span class="sxs-lookup"><span data-stu-id="35d15-114">Instead, you can create a new routine log backup (using WITH NORECOVERY) and use that backup together with any previous log backups that are required for the restore sequence.</span></span> <span data-ttu-id="35d15-115">Tuttavia, un backup del log di sola copia può talvolta essere utile per eseguire un ripristino in linea.</span><span class="sxs-lookup"><span data-stu-id="35d15-115">However, a copy-only log backup can sometimes be useful for performing an online restore.</span></span> <span data-ttu-id="35d15-116">Per un esempio, vedere [Esempio: Ripristino online di un file di lettura/scrittura &#40;modello di recupero con registrazione completa&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="35d15-116">For an example of this, see [Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span></span>  
  
     <span data-ttu-id="35d15-117">Il log delle transazioni non viene mai troncato dopo un backup di sola copia.</span><span class="sxs-lookup"><span data-stu-id="35d15-117">The transaction log is never truncated after a copy-only backup.</span></span>  
  
 <span data-ttu-id="35d15-118">I backup di sola copia vengono registrati nella colonna **is_copy_only** della tabella [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="35d15-118">Copy-only backups are recorded in the **is_copy_only** column of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) table.</span></span>  
  
## <a name="to-create-a-copy-only-backup"></a><span data-ttu-id="35d15-119">Per creare un backup di sola copia</span><span class="sxs-lookup"><span data-stu-id="35d15-119">To Create a Copy-Only Backup</span></span>  
 <span data-ttu-id="35d15-120">È possibile creare un backup di sola copia utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35d15-120">You can create a copy-only backup by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="35d15-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35d15-121">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="35d15-122">Nella pagina **Generale** della finestra di dialogo **Backup database** selezionare l'opzione **Backup di sola copia**.</span><span class="sxs-lookup"><span data-stu-id="35d15-122">On the **General** page of the **Back Up Database** dialog box, select the **Copy Only Backup** option.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="35d15-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35d15-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="35d15-124">La sintassi [!INCLUDE[tsql](../../../includes/tsql-md.md)] essenziale è la seguente:</span><span class="sxs-lookup"><span data-stu-id="35d15-124">The essential [!INCLUDE[tsql](../../../includes/tsql-md.md)] syntax is as follows:</span></span>  
  
-   <span data-ttu-id="35d15-125">Per un backup completo di sola copia:</span><span class="sxs-lookup"><span data-stu-id="35d15-125">For a copy-only full backup:</span></span>  
  
     <span data-ttu-id="35d15-126">BACKUP DATABASE *database_name* to \<backup_device*> \*... CON COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="35d15-126">BACKUP DATABASE *database_name* TO \<backup_device*>\* ... WITH COPY_ONLY ...</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="35d15-127">L'opzione COPY_ONLY non ha alcun effetto quando specificata con l'opzione DIFFERENTIAL.</span><span class="sxs-lookup"><span data-stu-id="35d15-127">COPY_ONLY has no effect when specified with the DIFFERENTIAL option.</span></span>  
  
-   <span data-ttu-id="35d15-128">Per un backup del log di sola copia:</span><span class="sxs-lookup"><span data-stu-id="35d15-128">For a copy-only log backup:</span></span>  
  
     <span data-ttu-id="35d15-129">BACKUP del LOG *database_name* a *\<*backup_device*>* ... CON COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="35d15-129">BACKUP LOG *database_name* TO *\<*backup_device*>* ... WITH COPY_ONLY ...</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="35d15-130">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="35d15-130">Using PowerShell</span></span>  
  
<span data-ttu-id="35d15-131">Utilizzare il cmdlet `Backup-SqlDatabase` con il parametro `-CopyOnly`.</span><span class="sxs-lookup"><span data-stu-id="35d15-131">Use the `Backup-SqlDatabase` cmdlet with the `-CopyOnly` parameter.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="35d15-132">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="35d15-132">Related Tasks</span></span>  

### <a name="to-create-a-full-or-log-backup"></a><span data-ttu-id="35d15-133">Per creare un backup completo o del log</span><span class="sxs-lookup"><span data-stu-id="35d15-133">To create a full or log backup</span></span>
  
-   [<span data-ttu-id="35d15-134">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35d15-134">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="35d15-135">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35d15-135">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
### <a name="to-view-copy-only-backups"></a><span data-ttu-id="35d15-136">Per visualizzare backup di sola copia</span><span class="sxs-lookup"><span data-stu-id="35d15-136">To view copy-only backups</span></span>
  
-   [<span data-ttu-id="35d15-137">backupset &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="35d15-137">backupset &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
### <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><span data-ttu-id="35d15-138">Per impostare e utilizzare il provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="35d15-138">To set up and use the SQL Server PowerShell provider</span></span>
  
-   [<span data-ttu-id="35d15-139">Provider PowerShell per SQL Server</span><span class="sxs-lookup"><span data-stu-id="35d15-139">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  

## <a name="see-also"></a><span data-ttu-id="35d15-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35d15-140">See Also</span></span>  
 <span data-ttu-id="35d15-141">[Panoramica del backup &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="35d15-141">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="35d15-142">[Modelli di recupero &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="35d15-142">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="35d15-143">[Copiare database tramite backup e ripristino](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="35d15-143">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="35d15-144">Panoramica del ripristino e del recupero &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35d15-144">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
