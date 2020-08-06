---
title: Spostamento di database del server di report in un altro computer (modalità nativa SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 44a9854d-e333-44f6-bdc7-8837b9f34416
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49fd35f57cf783b262b3c690e3047e5f479ab193
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711595"
---
# <a name="moving-the-report-server-databases-to-another-computer-ssrs-native-mode"></a><span data-ttu-id="3bbca-102">Spostamento di database del server di report in un altro computer (modalità nativa SSRS)</span><span class="sxs-lookup"><span data-stu-id="3bbca-102">Moving the Report Server Databases to Another Computer (SSRS Native Mode)</span></span>
  <span data-ttu-id="3bbca-103">È possibile spostare i database del server di report utilizzati in un'installazione di in un' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] istanza di in un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="3bbca-103">You can move the report server databases that are used in an installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] to an instance that is on a different computer.</span></span> <span data-ttu-id="3bbca-104">I database reportserver e reportservertempdb devono essere spostati o copiati insieme.</span><span class="sxs-lookup"><span data-stu-id="3bbca-104">Both the reportserver and reportservertempdb databases must be moved or copied together.</span></span> <span data-ttu-id="3bbca-105">Per un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sono necessari entrambi i database. Il database reportservertempdb deve essere correlato tramite il nome al database reportserver primario che si sta spostando.</span><span class="sxs-lookup"><span data-stu-id="3bbca-105">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires both databases; the reportservertempdb database must be related by name to the primary reportserver database you are moving.</span></span>  
  
 <span data-ttu-id="3bbca-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="3bbca-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="3bbca-107">Lo spostamento di un database non influisce sulle operazioni pianificate attualmente definite per gli elementi del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-107">Moving a database does not effect scheduled operations that are currently defined for report server items.</span></span>  
  
-   <span data-ttu-id="3bbca-108">Le pianificazioni vengono ricreate la prima volta che si riavvia il servizio del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-108">Schedules will be recreated the first time that you restart the Report Server service.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3bbca-109">In Agent i processi usati per attivare una pianificazione verranno ricreati nella istanza di database.</span><span class="sxs-lookup"><span data-stu-id="3bbca-109">Agent jobs that are used to trigger a schedule will be recreated on the new database instance.</span></span> <span data-ttu-id="3bbca-110">Non è necessario spostare i processi nel nuovo computer, ma è necessario eliminare quelli che non verranno più utilizzati.</span><span class="sxs-lookup"><span data-stu-id="3bbca-110">You do not have to move the jobs to the new computer, but you might want to delete jobs on the computer that will no longer be used.</span></span>  
  
-   <span data-ttu-id="3bbca-111">Le sottoscrizioni, gli snapshot e i report memorizzati nella cache vengono mantenuti nel database spostato.</span><span class="sxs-lookup"><span data-stu-id="3bbca-111">Subscriptions, cached reports, and snapshots are preserved in the moved database.</span></span> <span data-ttu-id="3bbca-112">Se uno snapshot non esegue la scelta di dati aggiornati dopo che il database è stato spostato, deselezionare le opzioni relative in Gestione report, fare clic su **Applica** per salvare le modifiche, ricreare la pianificazione e fare nuovamente clic su **Applica** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3bbca-112">If a snapshot is not picking up refreshed data after the database is moved, clear the snapshot options in Report Manager, click **Apply** to save your changes, re-create the schedule, and click **Apply** again to save your changes.</span></span>  
  
-   <span data-ttu-id="3bbca-113">Il report temporaneo e i dati della sessione utente archiviati nel database reportservertempdb vengono mantenuti quando si sposta il database.</span><span class="sxs-lookup"><span data-stu-id="3bbca-113">Temporary report and user session data that is stored in reportservertempdb are persisted when you move that database.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3bbca-114">sono disponibili diversi modi per spostare i database, tra cui backup e ripristino, collegamento e scollegamento e copia.</span><span class="sxs-lookup"><span data-stu-id="3bbca-114">provides several approaches for moving databases, including backup and restore, attach and detach, and copy.</span></span> <span data-ttu-id="3bbca-115">Non tutti gli approcci sono appropriati per spostare un database esistente in una nuova istanza del server.</span><span class="sxs-lookup"><span data-stu-id="3bbca-115">Not all approaches are appropriate for relocating an existing database to a new server instance.</span></span> <span data-ttu-id="3bbca-116">L'approccio da utilizzare per spostare il database del server di report dipende dai requisiti di disponibilità del sistema.</span><span class="sxs-lookup"><span data-stu-id="3bbca-116">The approach that you should use to move the report server database will vary depending on your system availability requirements.</span></span> <span data-ttu-id="3bbca-117">Il modo più semplice per spostare i database del server di report consiste nel collegarli e scollegarli.</span><span class="sxs-lookup"><span data-stu-id="3bbca-117">The easiest way to move the report server databases is to attach and detach them.</span></span> <span data-ttu-id="3bbca-118">Questo approccio richiede tuttavia di portare in modalità offline il server di report mentre lo si scollega.</span><span class="sxs-lookup"><span data-stu-id="3bbca-118">However, this approach requires that you take the report server offline while you detach the database.</span></span> <span data-ttu-id="3bbca-119">Il backup e il ripristino rappresentano un'opzione migliore se si desidera ridurre al minimo le interruzioni del servizio, tuttavia per eseguire queste operazioni è necessario usare i comandi [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bbca-119">Backup and restore is a better choice if you want to minimize service disruptions, but you must run [!INCLUDE[tsql](../../includes/tsql-md.md)] commands to perform the operations.</span></span> <span data-ttu-id="3bbca-120">La copia del database, in particolare l'utilizzo della procedura Copia guidata database, non è consigliabile in quanto non consente di mantenere le impostazioni delle autorizzazioni nel database.</span><span class="sxs-lookup"><span data-stu-id="3bbca-120">Copying the database is not recommended (specifically, by using the Copy Database Wizard); it does not preserve permission settings in the database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3bbca-121">È consigliabile eseguire la procedura descritta in questo argomento quando lo spostamento del database del server di report è l'unica modifica che si desidera apportare all'installazione esistente.</span><span class="sxs-lookup"><span data-stu-id="3bbca-121">The steps provided in this topic are recommended when relocating the report server database is the only change you are making to the existing installation.</span></span> <span data-ttu-id="3bbca-122">Per la migrazione di un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] completa, vale a dire lo spostamento del database e la modifica dell'identità del servizio Windows ReportServer usato dal database, è necessario riconfigurare le informazioni di connessione e reimpostare la chiave di crittografia.</span><span class="sxs-lookup"><span data-stu-id="3bbca-122">Migrating an entire [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation (that is, moving the database and changing the identity of the Report Server Windows service that uses the database) requires connection reconfiguration and an encryption key reset.</span></span>  
  
## <a name="detaching-and-attaching-the-report-server-databases"></a><span data-ttu-id="3bbca-123">Scollegamento e collegamento dei database del server di report</span><span class="sxs-lookup"><span data-stu-id="3bbca-123">Detaching and Attaching the Report Server Databases</span></span>  
 <span data-ttu-id="3bbca-124">Se il server di report può essere portato in modalità offline, è possibile scollegare i database per spostarli nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="3bbca-124">If you can take the report server offline, you can detach the databases to move them to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="3bbca-125">In questo modo, è possibile mantenere le autorizzazioni presenti nei database.</span><span class="sxs-lookup"><span data-stu-id="3bbca-125">This approach preserves permissions in the databases.</span></span> <span data-ttu-id="3bbca-126">Se si usa un database di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , è necessario spostarlo in un'altra istanza di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bbca-126">If you are using a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, you must move it to another [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance.</span></span> <span data-ttu-id="3bbca-127">Dopo avere spostato i database, è necessario riconfigurare la connessione del server di report al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-127">After you move the databases, you must reconfigure the report server connection to the report server database.</span></span> <span data-ttu-id="3bbca-128">Se si sta eseguendo una distribuzione con scalabilità orizzontale, è necessario riconfigurare la connessione al database del server di report per ogni server di report della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3bbca-128">If you are running a scale-out deployment, you must reconfigure the report server database connection for each report server in the deployment.</span></span>  
  
 <span data-ttu-id="3bbca-129">Per spostare i database, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3bbca-129">Use the following steps to move the databases:</span></span>  
  
1.  <span data-ttu-id="3bbca-130">Eseguire il backup delle chiavi di crittografia per il database del server di report da spostare.</span><span class="sxs-lookup"><span data-stu-id="3bbca-130">Backup the encryption keys for the report server database you want to move.</span></span> <span data-ttu-id="3bbca-131">Per eseguire questa operazione, è possibile usare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bbca-131">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool backup the keys.</span></span>  
  
2.  <span data-ttu-id="3bbca-132">Arrestare il servizio del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-132">Stop the Report Server service.</span></span> <span data-ttu-id="3bbca-133">Per eseguire questa operazione, è possibile utilizzare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bbca-133">You can use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to stop the service.</span></span>  
  
3.  <span data-ttu-id="3bbca-134">Avviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e aprire una connessione all' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanza di che ospita i database del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-134">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and open a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the report server databases.</span></span>  
  
4.  <span data-ttu-id="3bbca-135">Fare clic con il pulsante destro del mouse sul database del server di report, scegliere Attività, quindi **Scollega**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-135">Right-click the report server database, point to Tasks, and click **Detach**.</span></span> <span data-ttu-id="3bbca-136">Ripetere il passaggio per il database temporaneo del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-136">Repeat this step for the report server temporary database.</span></span>  
  
5.  <span data-ttu-id="3bbca-137">Copiare o spostare i file con estensione mdf e ldf nella cartella Dati dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="3bbca-137">Copy or move the .mdf and .ldf files to the Data folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to use.</span></span> <span data-ttu-id="3bbca-138">Poiché si stanno spostando due database, verificare di spostare o copiare tutti e quattro i file.</span><span class="sxs-lookup"><span data-stu-id="3bbca-138">Because you are moving two databases, make sure that you move or copy all four files.</span></span>  
  
6.  <span data-ttu-id="3bbca-139">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]stabilire una connessione alla nuova istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ospiterà i database del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-139">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a connection to the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that will host the report server databases.</span></span>  
  
7.  <span data-ttu-id="3bbca-140">Fare clic con il pulsante destro del mouse sul nodo Database, quindi scegliere **Collega**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-140">Right-click the Databases node, and then click **Attach**.</span></span>  
  
8.  <span data-ttu-id="3bbca-141">Fare clic su **Aggiungi** per selezionare i file con estensione mdf e ldf del database del server di report che si desidera collegare.</span><span class="sxs-lookup"><span data-stu-id="3bbca-141">Click **Add** to select the report server database .mdf and .ldf files that you want to attach.</span></span> <span data-ttu-id="3bbca-142">Ripetere il passaggio per il database temporaneo del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-142">Repeat this step for the report server temporary database.</span></span>  
  
9. <span data-ttu-id="3bbca-143">Dopo aver collegato i database, verificare che `RSExecRole` sia un ruolo del database nel database del server di report e nel database temporaneo.</span><span class="sxs-lookup"><span data-stu-id="3bbca-143">After the databases are attached, verify that the `RSExecRole` is a database role in the report server database and temporary database.</span></span> <span data-ttu-id="3bbca-144">`RSExecRole`è necessario disporre delle autorizzazioni SELECT, INSERT, Update, DELETE e Reference sulle tabelle del database del server di report e delle autorizzazioni di esecuzione per le stored procedure.</span><span class="sxs-lookup"><span data-stu-id="3bbca-144">`RSExecRole` must have select, insert, update, delete, and reference permissions on the report server database tables, and execute permissions on the stored procedures.</span></span> <span data-ttu-id="3bbca-145">Per altre informazioni, vedere [Creare RSExecRole](../security/create-the-rsexecrole.md).</span><span class="sxs-lookup"><span data-stu-id="3bbca-145">For more information, see [Create the RSExecRole](../security/create-the-rsexecrole.md).</span></span>  
  
10. <span data-ttu-id="3bbca-146">Avviare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e connettersi al server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-146">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and open a connection to the report server.</span></span>  
  
11. <span data-ttu-id="3bbca-147">Nella pagina Database selezionare la nuova istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-147">On the Database page, select the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then click **Connect**.</span></span>  
  
12. <span data-ttu-id="3bbca-148">Selezionare il database del server di report appena spostato, quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-148">Select the report server database that you just moved, and then click **Apply**.</span></span>  
  
13. <span data-ttu-id="3bbca-149">Nella pagina Chiavi di crittografia fare clic su Ripristina.</span><span class="sxs-lookup"><span data-stu-id="3bbca-149">On the Encryption Keys page, click Restore.</span></span> <span data-ttu-id="3bbca-150">Specificare il file che contiene la copia di backup delle chiavi e la password per sbloccare il file.</span><span class="sxs-lookup"><span data-stu-id="3bbca-150">Specify the file that contains the backup copy of the keys and the password to unlock the file.</span></span>  
  
14. <span data-ttu-id="3bbca-151">Riavviare il servizio del server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-151">Restart the Report Server service.</span></span>  
  
## <a name="backing-up-and-restoring-the-report-server-databases"></a><span data-ttu-id="3bbca-152">Backup e ripristino dei database del server di report</span><span class="sxs-lookup"><span data-stu-id="3bbca-152">Backing Up and Restoring the Report Server Databases</span></span>  
 <span data-ttu-id="3bbca-153">Se il server di report non può essere portato in modalità offline, è possibile rilocare i database del server di report tramite backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="3bbca-153">If you cannot take the report server offline, you can use backup and restore to relocate the report server databases.</span></span> <span data-ttu-id="3bbca-154">Per eseguire queste due operazioni, è necessario usare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bbca-154">You must use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to do the backup and restore.</span></span> <span data-ttu-id="3bbca-155">Dopo aver ripristinato i database, è necessario configurare il server di report per utilizzare il database nella nuova istanza del server.</span><span class="sxs-lookup"><span data-stu-id="3bbca-155">After you restore the databases, you must configure the report server to use the database on the new server instance.</span></span> <span data-ttu-id="3bbca-156">Per ulteriori informazioni, vedere le istruzioni alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3bbca-156">For more information, see the instructions at the end of this topic.</span></span>  
  
### <a name="using-backup-and-copy_only-to-backup-the-report-server-databases"></a><span data-ttu-id="3bbca-157">Utilizzo di BACKUP e COPY_ONLY per eseguire il backup dei database del server di report</span><span class="sxs-lookup"><span data-stu-id="3bbca-157">Using BACKUP and COPY_ONLY to Backup the Report Server Databases</span></span>  
 <span data-ttu-id="3bbca-158">Quando si esegue il backup dei database, impostare l'argomento COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="3bbca-158">When backing up the databases, set the COPY_ONLY argument.</span></span> <span data-ttu-id="3bbca-159">Accertarsi di eseguire il backup di entrambi i database e dei file di log.</span><span class="sxs-lookup"><span data-stu-id="3bbca-159">Be sure to back up both of the databases and log files.</span></span>  
  
```  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServer  
   SET RECOVERY FULL  
  
-- If the ReportServerData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerData',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerData.bak'  
  
-- Create a logical backup device, ReportServerLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\BACKUP\ReportServerLog.bak'  
  
-- Back up the full ReportServer database.  
BACKUP DATABASE ReportServer  
   TO ReportServerData  
   WITH COPY_ONLY  
  
-- Back up the ReportServer log.  
BACKUP LOG ReportServer  
   TO ReportServerLog  
   WITH COPY_ONLY  
  
-- To permit log backups, before the full database backup, alter the database   
-- to use the full recovery model.  
USE master;  
GO  
ALTER DATABASE ReportServerTempdb  
   SET RECOVERY FULL  
  
-- If the ReportServerTempDBData device does not exist yet, create it.   
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBData',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBData.bak'  
  
-- Create a logical backup device, ReportServerTempDBLog.  
USE master  
GO  
EXEC sp_addumpdevice 'disk', 'ReportServerTempDBLog',   
'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\BACKUP\ReportServerTempDBLog.bak'  
  
-- Back up the full ReportServerTempDB database.  
BACKUP DATABASE ReportServerTempDB  
   TO ReportServerTempDBData  
   WITH COPY_ONLY  
  
-- Back up the ReportServerTempDB log.  
BACKUP LOG ReportServerTempDB  
   TO ReportServerTempDBLog  
   WITH COPY_ONLY  
```  
  
### <a name="using-restore-and-move-to-relocate-the-report-server-databases"></a><span data-ttu-id="3bbca-160">Utilizzo di RESTORE e MOVE per spostare i database del server di report</span><span class="sxs-lookup"><span data-stu-id="3bbca-160">Using RESTORE and MOVE to Relocate the Report Server Databases</span></span>  
 <span data-ttu-id="3bbca-161">Quando si ripristinano i database, accertarsi di includere l'argomento MOVE per poter specificare un percorso.</span><span class="sxs-lookup"><span data-stu-id="3bbca-161">When restoring the databases, be sure to include the MOVE argument so that you can specify a path.</span></span> <span data-ttu-id="3bbca-162">Utilizzare l'argomento NORECOVERY per eseguire il ripristino iniziale. In questo modo, il database viene mantenuto in uno stato RESTORING, consentendo di analizzare i backup dei log per determinare quali ripristinare.</span><span class="sxs-lookup"><span data-stu-id="3bbca-162">Use the NORECOVERY argument to perform the initial restore; this keeps the database in a RESTORING state, giving you time to review log backups to determine which one to restore.</span></span> <span data-ttu-id="3bbca-163">Nel passaggio finale l'operazione RESTORE viene ripetuta con l'argomento RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="3bbca-163">The final step repeats the RESTORE operation with the RECOVERY argument.</span></span>  
  
 <span data-ttu-id="3bbca-164">Per l'argomento MOVE viene utilizzato il nome logico del file di dati.</span><span class="sxs-lookup"><span data-stu-id="3bbca-164">The MOVE argument uses the logical name of the data file.</span></span> <span data-ttu-id="3bbca-165">Per individuare il nome logico, eseguire l'istruzione `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="3bbca-165">To find the logical name, execute the following statement: `RESTORE FILELISTONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="3bbca-166">Negli esempi seguenti viene incluso l'argomento FILE in modo che sia possibile specificare la posizione del file di log da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="3bbca-166">The following examples include the FILE argument so that you can specify the file position of the log file to restore.</span></span> <span data-ttu-id="3bbca-167">Per individuare la posizione del file, eseguire l'istruzione `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span><span class="sxs-lookup"><span data-stu-id="3bbca-167">To find the file position, execute the following statement: `RESTORE HEADERONLY FROM DISK='C:\ReportServerData.bak';`</span></span>  
  
 <span data-ttu-id="3bbca-168">Durante il ripristino del database e dei file di log, eseguire ogni operazione RESTORE separatamente.</span><span class="sxs-lookup"><span data-stu-id="3bbca-168">When restoring the database and log files, you should run each RESTORE operation separately.</span></span>  
  
```  
-- Restore the report server database and move to new instance folder   
RESTORE DATABASE ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore the report server log file to new instance folder   
RESTORE LOG ReportServer  
   FROM DISK='C:\ReportServerData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServer' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer.mdf',   
      MOVE 'ReportServer_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServer_Log.ldf';  
GO  
  
-- Restore and move the report server temporary database  
RESTORE DATABASE ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY,   
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Restore the temporary database log file to new instance folder   
RESTORE LOG ReportServerTempdb  
   FROM DISK='C:\ReportServerTempDBData.bak'  
   WITH NORECOVERY, FILE=2  
      MOVE 'ReportServerTempDB' TO   
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\ReportServerTempDB.mdf',   
      MOVE 'ReportServerTempDB_log' TO  
         'C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Data\REportServerTempDB_Log.ldf';  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServer  
   WITH RECOVERY  
GO  
  
-- Perform final restore  
RESTORE DATABASE ReportServerTempDB  
   WITH RECOVERY  
GO  
```  
  
### <a name="how-to-configure-the-report-server-database-connection"></a><span data-ttu-id="3bbca-169">Come configurare la connessione al database del server di report</span><span class="sxs-lookup"><span data-stu-id="3bbca-169">How to Configure the Report Server Database Connection</span></span>  
  
1.  <span data-ttu-id="3bbca-170">Avviare Gestione configurazione [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e connettersi al server di report.</span><span class="sxs-lookup"><span data-stu-id="3bbca-170">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and open a connection to the report server.</span></span>  
  
2.  <span data-ttu-id="3bbca-171">Nella pagina Database fare clic su **Cambia database**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-171">On the Database page, click **Change Database**.</span></span> <span data-ttu-id="3bbca-172">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-172">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="3bbca-173">Fare clic su **Scegli un database del server di report esistente**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-173">Click **Choose an existing report server database**.</span></span> <span data-ttu-id="3bbca-174">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-174">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="3bbca-175">Selezionare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ospita attualmente il database del server di report, quindi fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-175">Select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that now hosts the report server database and click **Test Connection**.</span></span> <span data-ttu-id="3bbca-176">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-176">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="3bbca-177">In Nome database selezionare il database del server di report da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="3bbca-177">In Database Name, select the report server database that you want to use.</span></span> <span data-ttu-id="3bbca-178">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-178">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="3bbca-179">In Credenziali specificare le credenziali che il server di report utilizzerà per la connessione al database relativo.</span><span class="sxs-lookup"><span data-stu-id="3bbca-179">In Credentials, specify the credentials that the report server will use to connect to the report server database.</span></span> <span data-ttu-id="3bbca-180">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-180">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="3bbca-181">Fare clic su **Avanti** , quindi su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="3bbca-181">Click **Next** and then **Finish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3bbca-182">Per un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è necessario che nell'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] sia incluso il ruolo `RSExecRole`.</span><span class="sxs-lookup"><span data-stu-id="3bbca-182">A [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation requires that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance include the `RSExecRole` role.</span></span> <span data-ttu-id="3bbca-183">Quando si imposta la connessione al database del server di report tramite lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , vengono eseguite le operazioni di creazione dei ruoli, registrazione dell'account di accesso e assegnazione di ruoli.</span><span class="sxs-lookup"><span data-stu-id="3bbca-183">Role creation, login registration, and role assignments occur when you set the report server database connection through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="3bbca-184">Se per configurare la connessione si utilizzano approcci alternativi, in particolare l'utilità della riga di comando rsconfig.exe, il server di report non si troverà in uno stato attivo.</span><span class="sxs-lookup"><span data-stu-id="3bbca-184">If you use alternate approaches (specifically, if you use the rsconfig.exe command prompt utility) to configure the connection, the report server will not be in a working state.</span></span> <span data-ttu-id="3bbca-185">Per renderlo disponibile il server di report, potrebbe essere necessario scrivere codice WMI.</span><span class="sxs-lookup"><span data-stu-id="3bbca-185">You might have to write WMI code to make the report server available.</span></span> <span data-ttu-id="3bbca-186">Per altre informazioni, vedere [Accedere al provider WMI per Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="3bbca-186">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbca-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bbca-187">See Also</span></span>  
 <span data-ttu-id="3bbca-188">[Creare il RSExecRole](../security/create-the-rsexecrole.md) </span><span class="sxs-lookup"><span data-stu-id="3bbca-188">[Create the RSExecRole](../security/create-the-rsexecrole.md) </span></span>  
 <span data-ttu-id="3bbca-189">[Avviare e arrestare il servizio del server di report](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="3bbca-189">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 <span data-ttu-id="3bbca-190">[Configurare una connessione al database del server di report &#40;Configuration Manager SSRS&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3bbca-190">[Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="3bbca-191">[Configurare l'account di esecuzione automatica &#40;Configuration Manager SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3bbca-191">[Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="3bbca-192">[Gestione configurazione Reporting Services &#40;modalità nativa&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="3bbca-192">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="3bbca-193">[Utilità rsconfig &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3bbca-193">[rsconfig Utility &#40;SSRS&#41;](../tools/rsconfig-utility-ssrs.md) </span></span>  
 <span data-ttu-id="3bbca-194">[Configurare e gestire chiavi di crittografia &#40;Configuration Manager SSRS&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span><span class="sxs-lookup"><span data-stu-id="3bbca-194">[Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) </span></span>  
 [<span data-ttu-id="3bbca-195">Database del server di report &#40;modalità nativa SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3bbca-195">Report Server Database &#40;SSRS Native Mode&#41;</span></span>](report-server-database-ssrs-native-mode.md)  
  
  
