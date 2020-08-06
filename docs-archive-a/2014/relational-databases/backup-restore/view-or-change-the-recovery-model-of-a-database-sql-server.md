---
title: Visualizzare o modificare il modello di recupero di un database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], recovery models
- recovery [SQL Server], recovery model
- backing up databases [SQL Server], recovery models
- recovery models [SQL Server], switching
- recovery models [SQL Server], viewing
- database restores [SQL Server], recovery models
- modifying database recovery models
ms.assetid: 94918d1d-7c10-4be7-bf9f-27e00b003a0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889080301109938f0514bd6b81265c100237ab60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718306"
---
# <a name="view-or-change-the-recovery-model-of-a-database-sql-server"></a><span data-ttu-id="0dfd2-102">Visualizzazione o modifica del modello di recupero di un database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0dfd2-102">View or Change the Recovery Model of a Database (SQL Server)</span></span>
  <span data-ttu-id="0dfd2-103">In questo argomento viene illustrato come visualizzare o modificare il modello di recupero di un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dfd2-103">This topic describes how to view or change the recovery model of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0dfd2-104">Un *modello di recupero* è una proprietà del database che determina la modalità di registrazione delle transazioni, se è necessario e possibile eseguire il backup del log delle transazioni e quali tipi di operazioni di ripristino sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-104">A *recovery model* is a database property that controls how transactions are logged, whether the transaction log requires (and allows) backing up, and what kinds of restore operations are available.</span></span> <span data-ttu-id="0dfd2-105">Sono tre i modelli di recupero disponibili: con registrazione minima, con registrazione completa e con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-105">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="0dfd2-106">In genere, un database utilizza il modello di recupero con registrazione completa o con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-106">Typically, a database uses the full recovery model or simple recovery model.</span></span> <span data-ttu-id="0dfd2-107">In un database è possibile passare a un modello di recupero diverso in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-107">A database can be switched to another recovery model at any time.</span></span> <span data-ttu-id="0dfd2-108">Il database **modello** imposta il modello di recupero predefinito dei nuovi database.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-108">The **model** database sets the default recovery model of new databases.</span></span>  
  
 <span data-ttu-id="0dfd2-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0dfd2-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0dfd2-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0dfd2-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0dfd2-111">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="0dfd2-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="0dfd2-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0dfd2-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0dfd2-113">**Per visualizzare o modificare il modello di recupero di un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="0dfd2-113">**To view or change the recovery model of a database, using:**</span></span>  
  
     [<span data-ttu-id="0dfd2-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0dfd2-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0dfd2-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0dfd2-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="0dfd2-116">**Indicazioni sul completamento:**  [Dopo la modifica del modello di recupero](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="0dfd2-116">**Follow Up Recommendations:**  [After You Change the Recovery Model](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="0dfd2-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0dfd2-117">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0dfd2-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0dfd2-118">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="0dfd2-119">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="0dfd2-119">Recommendations</span></span>  
  
-   <span data-ttu-id="0dfd2-120">Prima di passare dal modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk, eseguire il backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-120">Before switching from the full recovery or bulk-logged recovery model, back up the transaction log.</span></span>  
  
-   <span data-ttu-id="0dfd2-121">Il recupero temporizzato non è possibile con il modello di recupero con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-121">Point-in-time recovery is not possible with bulk-logged model.</span></span> <span data-ttu-id="0dfd2-122">Pertanto, se si eseguono transazioni nel modello di recupero con registrazione minima delle operazioni bulk durante le quali potrebbe essere richiesto il ripristino di un log delle transazioni, queste ultime potrebbero essere esposte alla perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-122">Therefore, if you run transactions under the bulk-logged recovery model that might require a transaction log restore, these transactions could be exposed to data loss.</span></span> <span data-ttu-id="0dfd2-123">Per ottimizzare la recuperabilità in uno scenario di recupero di emergenza, è consigliabile passare al modello di recupero con registrazione minima delle operazioni bulk esclusivamente nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dfd2-123">To maximize data recoverability in a disaster-recovery scenario, we recommend that you switch to the bulk-logged recovery model only under the following conditions:</span></span>  
  
    -   <span data-ttu-id="0dfd2-124">Agli utenti non è attualmente consentito l'accesso al database.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-124">Users are currently not allowed in the database.</span></span>  
  
    -   <span data-ttu-id="0dfd2-125">Tutte le modifiche effettuate durante l'elaborazione bulk possano essere recuperate senza dipendere da un backup del log, ad esempio ripetendo i processi bulk.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-125">All modifications made during bulk processing are recoverable without depending on taking a log backup; for example, by re-running the bulk processes.</span></span>  
  
     <span data-ttu-id="0dfd2-126">Se queste due condizioni sono soddisfatte, l'utente non sarà esposto ad alcuna perdita di dati durante il ripristino di un log delle transazioni di cui è stato eseguito il backup nel modello di recupero con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-126">If you satisfy these two conditions, you will not be exposed to any data loss while restoring a transaction log that was backed up under the bulk-logged recovery model..</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0dfd2-127">Se si passa al modello di recupero con registrazione completa durante un'operazione bulk, la registrazione dell'operazione bulk cambia da registrazione minima a completa, e viceversa.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-127">If you switch to the full recovery model during a bulk operation, the logging of the bulk operation changes from minimal logging to full logging, and vice versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0dfd2-128">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0dfd2-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0dfd2-129">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0dfd2-129">Permissions</span></span>  
 <span data-ttu-id="0dfd2-130">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-130">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0dfd2-131">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0dfd2-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-recovery-model"></a><span data-ttu-id="0dfd2-132">Per visualizzare o modificare il modello di recupero</span><span class="sxs-lookup"><span data-stu-id="0dfd2-132">To view or change the recovery model</span></span>  
  
1.  <span data-ttu-id="0dfd2-133">Dopo aver effettuato la connessione all'istanza appropriata del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-133">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="0dfd2-134">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-134">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="0dfd2-135">Fare clic con il pulsante destro del mouse sul database e quindi scegliere **Proprietà**per visualizzare la finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="0dfd2-135">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="0dfd2-136">Nel riquadro **Selezione pagina** fare clic su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-136">In the **Select a page** pane, click **Options**.</span></span>  
  
5.  <span data-ttu-id="0dfd2-137">Il modello di recupero attualmente implementato è visualizzato nella casella di riepilogo **Modello di recupero** .</span><span class="sxs-lookup"><span data-stu-id="0dfd2-137">The current recovery model is displayed in the **Recovery model** list box.</span></span>  
  
6.  <span data-ttu-id="0dfd2-138">Se desiderato, è possibile modificare il modello di recupero selezionandone uno differente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-138">Optionally, to change the recovery model select a different model list.</span></span> <span data-ttu-id="0dfd2-139">Le scelte possibili sono **Con registrazione completa**, **Con registrazione minima delle operazioni bulk**e **Con registrazione minima**.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-139">The choices are **Full**, **Bulk-logged**, or **Simple**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0dfd2-140">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0dfd2-140">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-recovery-model"></a><span data-ttu-id="0dfd2-141">Per visualizzare il modello di recupero</span><span class="sxs-lookup"><span data-stu-id="0dfd2-141">To view the recovery model</span></span>  
  
1.  <span data-ttu-id="0dfd2-142">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dfd2-142">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0dfd2-143">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0dfd2-144">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0dfd2-145">In questo esempio viene mostrato come eseguire una query sulla vista del catalogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) per individuare il modello di recupero del database **model** .</span><span class="sxs-lookup"><span data-stu-id="0dfd2-145">This example shows how to query the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to learn the recovery model of the **model** database.</span></span>  
  
```sql  
SELECT name, recovery_model_desc  
   FROM sys.databases  
      WHERE name = 'model' ;  
GO  
  
```  
  
#### <a name="to-change-the-recovery-model"></a><span data-ttu-id="0dfd2-146">Per modificare il modello di recupero</span><span class="sxs-lookup"><span data-stu-id="0dfd2-146">To change the recovery model</span></span>  
  
1.  <span data-ttu-id="0dfd2-147">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dfd2-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0dfd2-148">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0dfd2-149">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0dfd2-150">In questo esempio viene mostrato come impostare il modello di recupero nel database `model` su `FULL` utilizzando l'opzione `SET RECOVERY` dell'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="0dfd2-150">This example shows how to change the recovery model in the `model` database to `FULL` by using the `SET RECOVERY` option of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement.</span></span>  
  
```sql  
USE master ;  
ALTER DATABASE model SET RECOVERY FULL ;  
```  
  
##  <a name="follow-up-recommendations-after-you-change-the-recovery-model"></a><a name="FollowUp"></a><span data-ttu-id="0dfd2-151">Suggerimenti per il completamento: dopo la modifica del modello di recupero</span><span class="sxs-lookup"><span data-stu-id="0dfd2-151">Follow Up Recommendations: After You Change the Recovery Model</span></span>  
  
-   <span data-ttu-id="0dfd2-152">**Dopo il passaggio tra i modelli di recupero con registrazione completa e con registrazione minima delle operazioni bulk**</span><span class="sxs-lookup"><span data-stu-id="0dfd2-152">**After switching between the full and bulk-logged recovery models**</span></span>  
  
    -   <span data-ttu-id="0dfd2-153">Dopo il completamento delle operazioni bulk, tornare immediatamente alla modalità di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-153">After completing the bulk operations, immediately switch back to full recovery mode.</span></span>  
  
    -   <span data-ttu-id="0dfd2-154">Dopo il passaggio dal modello di recupero con registrazione minima delle operazioni bulk al modello di recupero con registrazione completa, eseguire il backup del log.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-154">After switching from the bulk-logged recovery model back to the full recovery model, back up the log.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0dfd2-155">La strategia di backup rimane invariata, cioè continua l'esecuzione di backup del database, del log e differenziali periodici.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-155">Your backup strategy remains the same: continue performing periodic database, log, and differential backups.</span></span>  
  
-   <span data-ttu-id="0dfd2-156">**Dopo il passaggio dal modello di recupero con registrazione minima**</span><span class="sxs-lookup"><span data-stu-id="0dfd2-156">**After switching from the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="0dfd2-157">Immediatamente dopo il passaggio al modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk, eseguire un backup di database completo o differenziale per avviare la catena di log.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-157">Immediately after switching to the full recovery model or bulk-logged recovery model, take a full or differential database backup to start the log chain.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0dfd2-158">Il passaggio al modello di recupero con registrazione completa o con registrazione minima delle operazioni bulk ha effetto solo dopo il primo backup dei dati.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-158">The switch to the full or bulk-logged recovery model takes effect only after the first data backup.</span></span>  
  
    -   <span data-ttu-id="0dfd2-159">Pianificare backup regolari dei log e aggiornare il piano di ripristino di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-159">Schedule regular log backups, and update your restore plan accordingly.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="0dfd2-160">Se non si esegue il backup del log con la necessaria frequenza, il log delle transazioni può espandersi fino a esaurire lo spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-160">If you do not back up the log frequently enough, the transaction log can expand until it runs out of disk space.</span></span>  
  
-   <span data-ttu-id="0dfd2-161">**Dopo il passaggio al modello di recupero con registrazione minima**</span><span class="sxs-lookup"><span data-stu-id="0dfd2-161">**After switching to the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="0dfd2-162">Interrompere tutti i processi pianificati per l'esecuzione del backup del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-162">Discontinue any scheduled jobs for backing up the transaction log.</span></span>  
  
    -   <span data-ttu-id="0dfd2-163">Verificare la pianificazione di backup di database periodici.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-163">Ensure periodic database backups are scheduled.</span></span> <span data-ttu-id="0dfd2-164">Il backup del database è essenziale sia per proteggere i dati sia per troncare la porzione inattiva del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="0dfd2-164">Backing up your database is essential both to protect your data and to truncate the inactive portion of the transaction log.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0dfd2-165">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0dfd2-165">Related Tasks</span></span>  
  
-   [<span data-ttu-id="0dfd2-166">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0dfd2-166">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="0dfd2-167">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0dfd2-167">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="0dfd2-168">Creazione di un processo</span><span class="sxs-lookup"><span data-stu-id="0dfd2-168">Create a Job</span></span>](../../ssms/agent/create-a-job.md)  
  
-   [<span data-ttu-id="0dfd2-169">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="0dfd2-169">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="0dfd2-170">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="0dfd2-170">Related Content</span></span>  
  
-   <span data-ttu-id="0dfd2-171">[Database Maintenance Plans](../maintenance-plans/maintenance-plans.md) nella documentazione online di [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dfd2-171">[Database Maintenance Plans](../maintenance-plans/maintenance-plans.md) (in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dfd2-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dfd2-172">See Also</span></span>  
 <span data-ttu-id="0dfd2-173">[Modelli di recupero &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0dfd2-173">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="0dfd2-174">[Log delle transazioni &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0dfd2-174">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="0dfd2-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0dfd2-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="0dfd2-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0dfd2-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="0dfd2-177">Modelli di recupero &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0dfd2-177">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
