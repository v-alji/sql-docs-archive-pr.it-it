---
title: Backup di log delle transazioni [SQL Server] | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up [SQL Server], transaction logs
- transaction log backups [SQL Server], creating
- log backups [SQL Server[
- transaction log backups [SQL Server], sequencing
ms.assetid: f4a44a35-0f44-4a42-91d5-d73ac658a3b0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 752447d6c38a2df0fcbdce72fbba12edd7a9eeb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718317"
---
# <a name="transaction-log-backups-sql-server"></a><span data-ttu-id="6687e-102">Backup di log delle transazioni (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6687e-102">Transaction Log Backups (SQL Server)</span></span>
  <span data-ttu-id="6687e-103">Le informazioni contenute in questo argomento sono rilevanti solo per i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che utilizzano i modelli di recupero con registrazione completa o con registrazione minima delle operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="6687e-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span> <span data-ttu-id="6687e-104">In questo argomento viene illustrata l'esecuzione del backup del log delle transazioni di un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6687e-104">This topic discusses backing up the transaction log of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="6687e-105">Per poter creare backup dei log è necessario aver creato almeno un backup completo.</span><span class="sxs-lookup"><span data-stu-id="6687e-105">Minimally, you must have created at least one full backup before you can create any log backups.</span></span> <span data-ttu-id="6687e-106">A quel punto, è possibile eseguire il backup del log delle transazioni in qualsiasi momento a meno che non sia già stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="6687e-106">After that, the transaction log can be backed up at any time unless the log is already being backed up.</span></span> <span data-ttu-id="6687e-107">È consigliabile eseguire backup del log spesso, sia per ridurre al minimo il rischio di perdita dei dati sia per consentire il troncamento del log.</span><span class="sxs-lookup"><span data-stu-id="6687e-107">We recommend that you take log backups frequently, both to minimize work loss exposure and to truncate the transaction log.</span></span> <span data-ttu-id="6687e-108">In genere, un amministratore del database crea un backup completo occasionale del database, ad esempio con cadenza settimanale ed eventualmente crea una serie di backup differenziali a intervalli più brevi, ad esempio giornalmente.</span><span class="sxs-lookup"><span data-stu-id="6687e-108">Typically, a database administrator creates a full database backup occasionally, such as weekly, and, optionally, creates a series of differential database backup at a shorter interval, such as daily.</span></span> <span data-ttu-id="6687e-109">Indipendentemente dei backup di database, l'amministratore esegue il backup del log delle transazioni a intervalli frequenti, ad esempio ogni 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="6687e-109">Independently of the database backups, the database administrator backs up the transaction log at frequent intervals, such as every 10 minutes.</span></span> <span data-ttu-id="6687e-110">L'intervallo ottimale per un determinato tipo di backup dipende da fattori quali l'importanza dei dati, le dimensioni del database e il carico di lavoro del server.</span><span class="sxs-lookup"><span data-stu-id="6687e-110">For a given type of backup, the optimal interval depends on factors such as the importance of the data, the size of the database, and the workload of the server.</span></span>  
  
 <span data-ttu-id="6687e-111">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="6687e-111">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="6687e-112">Modalità di funzionamento di una sequenza di backup del log</span><span class="sxs-lookup"><span data-stu-id="6687e-112">How a Sequence of Log Backups Works</span></span>](#LogBackupSequence)  
  
-   [<span data-ttu-id="6687e-113">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="6687e-113">Recommendations</span></span>](#Recommendations)  
  
-   [<span data-ttu-id="6687e-114">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="6687e-114">Related Tasks</span></span>](#RelatedTasks)  
  
-   [<span data-ttu-id="6687e-115">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="6687e-115">Related Content</span></span>](#RelatedContent)  
  
##  <a name="how-a-sequence-of-log-backups-works"></a><a name="LogBackupSequence"></a><span data-ttu-id="6687e-116">Modalità di funzionamento di una sequenza di backup del log</span><span class="sxs-lookup"><span data-stu-id="6687e-116">How a Sequence of Log Backups Works</span></span>  
 <span data-ttu-id="6687e-117">La sequenza della *catena di log* dei backup del log delle transazioni è indipendente dai backup dei dati.</span><span class="sxs-lookup"><span data-stu-id="6687e-117">The sequence of transaction log backups *log chain* is independent of data backups.</span></span> <span data-ttu-id="6687e-118">Si consideri ad esempio la sequenza di eventi seguente:</span><span class="sxs-lookup"><span data-stu-id="6687e-118">For example, assume the following sequence of events.</span></span>  
  
|<span data-ttu-id="6687e-119">Tempo</span><span class="sxs-lookup"><span data-stu-id="6687e-119">Time</span></span>|<span data-ttu-id="6687e-120">Event</span><span class="sxs-lookup"><span data-stu-id="6687e-120">Event</span></span>|  
|----------|-----------|  
|<span data-ttu-id="6687e-121">8\.00</span><span class="sxs-lookup"><span data-stu-id="6687e-121">8:00 A.M.</span></span>|<span data-ttu-id="6687e-122">Backup del database</span><span class="sxs-lookup"><span data-stu-id="6687e-122">Back up database.</span></span>|  
|<span data-ttu-id="6687e-123">12.00</span><span class="sxs-lookup"><span data-stu-id="6687e-123">Noon</span></span>|<span data-ttu-id="6687e-124">Backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="6687e-124">Back up transaction log.</span></span>|  
|<span data-ttu-id="6687e-125">16.00</span><span class="sxs-lookup"><span data-stu-id="6687e-125">4:00 P.M.</span></span>|<span data-ttu-id="6687e-126">Backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="6687e-126">Back up transaction log.</span></span>|  
|<span data-ttu-id="6687e-127">18.00</span><span class="sxs-lookup"><span data-stu-id="6687e-127">6:00 P.M.</span></span>|<span data-ttu-id="6687e-128">Backup del database</span><span class="sxs-lookup"><span data-stu-id="6687e-128">Back up database.</span></span>|  
|<span data-ttu-id="6687e-129">20.00</span><span class="sxs-lookup"><span data-stu-id="6687e-129">8:00 P.M.</span></span>|<span data-ttu-id="6687e-130">Backup del log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="6687e-130">Back up transaction log.</span></span>|  
  
 <span data-ttu-id="6687e-131">Il backup del log delle transazioni creato alle 20.00</span><span class="sxs-lookup"><span data-stu-id="6687e-131">The transaction log backup created at 8:00 P.M.</span></span> <span data-ttu-id="6687e-132">contiene record del log delle transazioni a partire dalle 16.00</span><span class="sxs-lookup"><span data-stu-id="6687e-132">contains transaction log records from 4:00 P.M.</span></span> <span data-ttu-id="6687e-133">fino alle 20.00, il che include l'ora in cui è stato creato il backup del database completo, ovvero le 18.00.</span><span class="sxs-lookup"><span data-stu-id="6687e-133">through 8:00 P.M., spanning the time when the full database backup was created at 6:00 P.M.</span></span> <span data-ttu-id="6687e-134">La sequenza di backup del log delle transazioni è continua dal backup del database completo iniziale creato alle 8.00</span><span class="sxs-lookup"><span data-stu-id="6687e-134">The sequence of transaction log backups is continuous from the initial full database backup created at 8:00 A.M.</span></span> <span data-ttu-id="6687e-135">all'ultimo backup del log delle transazioni creato alle 20.00.</span><span class="sxs-lookup"><span data-stu-id="6687e-135">to the last transaction log backup created at 8:00 P.M.</span></span> <span data-ttu-id="6687e-136">Per informazioni su come applicare i backup del log, vedere l'esempio in [Applicare backup log delle transazioni &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6687e-136">For information about how to apply these log backups, see the example in [Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6687e-137">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="6687e-137">Recommendations</span></span>  
  
-   <span data-ttu-id="6687e-138">Se un log delle transazioni è danneggiato, il lavoro eseguito dopo il backup valido più recente viene perso.</span><span class="sxs-lookup"><span data-stu-id="6687e-138">If a transaction log is damaged, work that is performed since the most recent valid backup is lost.</span></span> <span data-ttu-id="6687e-139">Pertanto è consigliabile inserire i file di log in una risorsa di archiviazione con tolleranza di errore.</span><span class="sxs-lookup"><span data-stu-id="6687e-139">Therefore we strongly recommend that you put your log files on fault-tolerant storage.</span></span>  
  
-   <span data-ttu-id="6687e-140">Se un database è danneggiato oppure deve essere ripristinato, è consigliabile creare un [backup della parte finale del log](tail-log-backups-sql-server.md) per consentire il ripristino del database al momento corrente.</span><span class="sxs-lookup"><span data-stu-id="6687e-140">If a database is damaged or you are about to restore the database, we recommend that you create a [tail-log backup](tail-log-backups-sql-server.md) to enable you to restore the database to the current point in time.</span></span>  
  
-   <span data-ttu-id="6687e-141">Per impostazione predefinita, per ogni operazione di backup eseguita in modo corretto viene aggiunta una voce al log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e al registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="6687e-141">By default, every successful backup operation adds an entry in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and in the system event log.</span></span> <span data-ttu-id="6687e-142">Se il backup del log viene eseguito di frequente, questi messaggi possono aumentare rapidamente, provocando la creazione di log degli errori di dimensioni elevate e rendendo difficile l'individuazione di altri messaggi.</span><span class="sxs-lookup"><span data-stu-id="6687e-142">If back up the log very frequently, these success messages accumulate quickly, resulting in huge error logs that can make finding other messages difficult.</span></span> <span data-ttu-id="6687e-143">In questi casi è possibile eliminare tali voci di log utilizzando il flag di traccia 3226 se nessuno degli script dipende da esse.</span><span class="sxs-lookup"><span data-stu-id="6687e-143">In such cases you can suppress these log entries by using trace flag 3226 if none of your scripts depend on those entries.</span></span> <span data-ttu-id="6687e-144">Per altre informazioni, vedere [Flag di traccia &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6687e-144">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6687e-145">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="6687e-145">Related Tasks</span></span>  
 <span data-ttu-id="6687e-146">**Per creare un backup del log delle transazioni**</span><span class="sxs-lookup"><span data-stu-id="6687e-146">**To create a transaction log backup**</span></span>  
  
-   [<span data-ttu-id="6687e-147">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6687e-147">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   <span data-ttu-id="6687e-148"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="6687e-148"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="6687e-149">Per pianificare i processi di backup, vedere [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6687e-149">To schedule backup jobs, see [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="6687e-150">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="6687e-150">Related Content</span></span>  
 <span data-ttu-id="6687e-151">No.</span><span class="sxs-lookup"><span data-stu-id="6687e-151">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6687e-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6687e-152">See Also</span></span>  
 <span data-ttu-id="6687e-153">[Log delle transazioni &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6687e-153">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="6687e-154">[Backup e ripristino di database SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="6687e-154">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="6687e-155">[Backup della parte finale del log &#40;SQL Server&#41;](tail-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6687e-155">[Tail-Log Backups &#40;SQL Server&#41;](tail-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="6687e-156">Applicare backup di log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6687e-156">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](transaction-log-backups-sql-server.md)  
  
  
