---
title: Procedure consigliate e risoluzione dei problemi per il backup di SQL Server nell'URL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: de676bea-cec7-479d-891a-39ac8b85664f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06127b5e4b422750554c30fae23b6190107cb643
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629878"
---
# <a name="sql-server-backup-to-url-best-practices-and-troubleshooting"></a><span data-ttu-id="e595b-102">Procedure consigliate e risoluzione dei problemi per il backup di SQL Server nell'URL</span><span class="sxs-lookup"><span data-stu-id="e595b-102">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>
  <span data-ttu-id="e595b-103">In questo argomento sono inclusi i suggerimenti per la risoluzione dei problemi e le procedure consigliate relativi al backup e ripristino di SQL Server nel servizio BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="e595b-103">This topic includes best practices and troubleshooting tips for SQL Server backup and restores to the Azure Blob service.</span></span>  
  
 <span data-ttu-id="e595b-104">Per altre informazioni sull'uso del servizio di archiviazione BLOB di Azure per le operazioni di backup e ripristino di SQL Server, vedere:</span><span class="sxs-lookup"><span data-stu-id="e595b-104">For more information about using Azure Blob storage service for SQL Server backup or restore operations, see:</span></span>  
  
-   [<span data-ttu-id="e595b-105">Backup e ripristino di SQL Server con il servizio Archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="e595b-105">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
-   [<span data-ttu-id="e595b-106">Esercitazione: Backup e ripristino di SQL Server nel servizio di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="e595b-106">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="managing-backups"></a><span data-ttu-id="e595b-107">Gestione dei backup</span><span class="sxs-lookup"><span data-stu-id="e595b-107">Managing Backups</span></span>  
 <span data-ttu-id="e595b-108">Nell'elenco seguente sono inclusi i consigli generali sulla gestione dei backup:</span><span class="sxs-lookup"><span data-stu-id="e595b-108">The following list includes general recommendations to manage backups:</span></span>  
  
-   <span data-ttu-id="e595b-109">Per evitare la sovrascrittura accidentale dei BLOB, è consigliabile l'utilizzo di un nome file univoco per ogni backup.</span><span class="sxs-lookup"><span data-stu-id="e595b-109">Unique file name for every backup is recommended to prevent accidentally overwriting the blobs.</span></span>  
  
-   <span data-ttu-id="e595b-110">Quando si crea un contenitore, è consigliabile impostare il livello di accesso su **privato**, in modo che solo gli utenti o account che possono fornire le informazioni di autenticazione richieste possano leggere o scrivere i BLOB nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="e595b-110">When creating a container, it is recommended that you set the access level to **private**, so only users or accounts that can provide the required authentication information can read or write the blobs in the container.</span></span>  
  
-   <span data-ttu-id="e595b-111">Per SQL Server database in un'istanza di SQL Server in esecuzione in una macchina virtuale di Azure, usare un account di archiviazione nella stessa area della macchina virtuale per evitare i costi di trasferimento dei dati tra le aree.</span><span class="sxs-lookup"><span data-stu-id="e595b-111">For SQL Server databases on an instance of SQL Server running in an Azure Virtual Machine, use a storage account in the same region as the virtual machine to avoid data transfer costs between regions.</span></span> <span data-ttu-id="e595b-112">L'utilizzo della stessa area garantisce anche prestazioni ottimali per le operazioni di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="e595b-112">Using the same region also ensures optimal performance for backup and restore operations.</span></span>  
  
-   <span data-ttu-id="e595b-113">Un'attività di backup non completata correttamente può generare un file di backup non valido.</span><span class="sxs-lookup"><span data-stu-id="e595b-113">Failed backup activity can result in an invalid backup file.</span></span> <span data-ttu-id="e595b-114">Sono consigliate l'identificazione periodica dei backup non completati e l'eliminazione dei file BLOB.</span><span class="sxs-lookup"><span data-stu-id="e595b-114">We recommend periodic identification of failed backups and deleting the blob files.</span></span> <span data-ttu-id="e595b-115">Per altre informazioni, vedere [Eliminazione dei file BLOB di backup con lease attivi](deleting-backup-blob-files-with-active-leases.md)</span><span class="sxs-lookup"><span data-stu-id="e595b-115">For more information, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
-   <span data-ttu-id="e595b-116">L'utilizzo dell'opzione `WITH COMPRESSION` durante il backup consente di ridurre i costi di archiviazione e quelli delle transazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e595b-116">Using the `WITH COMPRESSION` option during backup can minimize your storage costs and storage transaction costs.</span></span> <span data-ttu-id="e595b-117">Inoltre, tramite questa opzione è possibile diminuire il tempo necessario per completare il processo di backup.</span><span class="sxs-lookup"><span data-stu-id="e595b-117">It can also decrease the time taken to complete the backup process.</span></span>  
  
## <a name="handling-large-files"></a><span data-ttu-id="e595b-118">Gestione di file di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="e595b-118">Handling Large Files</span></span>  
  
-   <span data-ttu-id="e595b-119">Nell'operazione di backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono usati più thread per ottimizzare il trasferimento dei dati ai servizi di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="e595b-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup operation uses multiple threads to optimize data transfer to Azure Blob storage services.</span></span>  <span data-ttu-id="e595b-120">Le prestazioni, tuttavia, dipendono da vari fattori, ad esempio la larghezza di banda del fornitore di software indipendente e le dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="e595b-120">However the performance depends on various factors, such as ISV bandwidth and size of the database.</span></span> <span data-ttu-id="e595b-121">Se si intende eseguire il backup di database o filegroup di grandi dimensioni da un database di SQL Server locale, si consiglia di eseguire innanzitutto alcuni test della velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="e595b-121">If you plan to back up large databases or filegroups from an on-premise SQL Server database, it is recommended that you do some throughput testing first.</span></span> <span data-ttu-id="e595b-122">I [contratti di contratto di archiviazione di Azure](https://go.microsoft.com/fwlink/?LinkId=271619) hanno tempi di elaborazione massimi per i BLOB che è possibile prendere in considerazione.</span><span class="sxs-lookup"><span data-stu-id="e595b-122">[Azure storage SLA's](https://go.microsoft.com/fwlink/?LinkId=271619) have maximum processing times for blobs that you can take into consideration.</span></span>  
  
-   <span data-ttu-id="e595b-123">L'uso dell'opzione `WITH COMPRESSION` come consigliato nella sezione **Gestione dei backup** è molto importante quando si esegue il backup di file di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e595b-123">Using the `WITH COMPRESSION` option as recommended in the **Managing Backup** section, it is very important when backing up large files.</span></span>  
  
## <a name="troubleshooting-backup-to-or-restore-from-url"></a><span data-ttu-id="e595b-124">Risoluzione dei problemi di backup nell'URL e di ripristino dallo stesso</span><span class="sxs-lookup"><span data-stu-id="e595b-124">Troubleshooting Backup To or Restore from URL</span></span>  
 <span data-ttu-id="e595b-125">Di seguito sono elencate alcune modalità rapide per la risoluzione di errori durante l'esecuzione del backup nel servizio di archiviazione BLOB di Azure o del ripristino dallo stesso.</span><span class="sxs-lookup"><span data-stu-id="e595b-125">Following are some quick ways to troubleshoot errors when backing up to or restoring from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="e595b-126">Per evitare errori a causa di opzioni o limitazioni non supportate, esaminare l'elenco delle limitazioni e il supporto per le informazioni sui comandi di BACKUP e ripristino nell'articolo [SQL Server backup e ripristino con il servizio di archiviazione BLOB di Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="e595b-126">To avoid errors due to unsupported options or limitations, review the list of limitations, and support for BACKUP and RESTORE commands information in the [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) article.</span></span>  
  
 <span data-ttu-id="e595b-127">**Errori di autenticazione:**</span><span class="sxs-lookup"><span data-stu-id="e595b-127">**Authentication Errors:**</span></span>  
  
-   <span data-ttu-id="e595b-128">WITH CREDENTIAL è una nuova opzione ed è necessario eseguire il backup o il ripristino dal servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="e595b-128">WITH CREDENTIAL is a new option and required to back up to or restore from the Azure Blob storage service.</span></span> <span data-ttu-id="e595b-129">Di seguito sono riportati i possibili errori correlati alle credenziali:</span><span class="sxs-lookup"><span data-stu-id="e595b-129">Failures related to credential could be the following:</span></span>  
  
     <span data-ttu-id="e595b-130">Le credenziali specificate nel comando `BACKUP` o `RESTORE` non esistono.</span><span class="sxs-lookup"><span data-stu-id="e595b-130">The credential specified in the `BACKUP` or `RESTORE` command does not exist.</span></span> <span data-ttu-id="e595b-131">Per evitare questo problema, è possibile includere istruzioni T-SQL per creare le credenziali qualora non siano presenti nell'istruzione di backup.</span><span class="sxs-lookup"><span data-stu-id="e595b-131">To avoid this issue, you can include T-SQL statements to create the credential if one does not exist in the backup statement.</span></span> <span data-ttu-id="e595b-132">Di seguito è riportato un esempio pratico:</span><span class="sxs-lookup"><span data-stu-id="e595b-132">The following is an example you can use:</span></span>  
  
    ```  
    IF NOT EXISTS  
    (SELECT * FROM sys.credentials   
    WHERE credential_identity = 'mycredential')  
    CREATE CREDENTIAL <credential name> WITH IDENTITY = 'mystorageaccount'  
    ,SECRET = '<storage access key> ;  
  
    ```  
  
-   <span data-ttu-id="e595b-133">Le credenziali esistono, ma all'account di accesso utilizzato per eseguire il comando di backup non sono associate autorizzazioni per accedere alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="e595b-133">The credential exists but the login account that is used to run the backup command does not have permissions to access the credentials.</span></span> <span data-ttu-id="e595b-134">Usare un account di accesso nel ruolo **db_backupoperator** con autorizzazioni **Modifica qualsiasi credenziale** .</span><span class="sxs-lookup"><span data-stu-id="e595b-134">Use a login account in the **db_backupoperator** role with **Alter any credential** permissions.</span></span>  
  
-   <span data-ttu-id="e595b-135">Verificare il nome dell'account di archiviazione e i valori di chiave.</span><span class="sxs-lookup"><span data-stu-id="e595b-135">Verify the storage account name and key values.</span></span> <span data-ttu-id="e595b-136">Le informazioni archiviate nelle credenziali devono corrispondere ai valori delle proprietà dell'account di archiviazione di Azure usati nelle operazioni di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="e595b-136">The information stored in the credential must match the property values of the Azure storage account you are using in the backup and restore operations.</span></span>  
  
 <span data-ttu-id="e595b-137">**Errori di backup:**</span><span class="sxs-lookup"><span data-stu-id="e595b-137">**Backup Errors/Failures:**</span></span>  
  
-   <span data-ttu-id="e595b-138">L'esecuzione di backup paralleli nello stesso BLOB comporta il mancato completamento di uno dei backup con conseguente errore **Inizializzazione non riuscita** .</span><span class="sxs-lookup"><span data-stu-id="e595b-138">Parallel backups to the same blob cause one of the backups to fail with an **Initialization failed** error.</span></span>  
  
-   <span data-ttu-id="e595b-139">Utilizzare i log degli errori seguenti per facilitare la risoluzione degli errori di backup:</span><span class="sxs-lookup"><span data-stu-id="e595b-139">Use the following error logs to help with troubleshooting backup errors:</span></span>  
  
    -   <span data-ttu-id="e595b-140">Impostare il flag di traccia 3051 per abilitare la registrazione in un log degli errori specifico con il formato seguente in:</span><span class="sxs-lookup"><span data-stu-id="e595b-140">Set trace flag 3051 to turn on logging to a specific error log with the following format in:</span></span>  
  
         <span data-ttu-id="e595b-141">BackupToUrl- \<instname> - \<dbname> -Action- \<PID> . log in cui \<action> è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e595b-141">BackupToUrl-\<instname>-\<dbname>-action-\<PID>.log Where \<action> is one of:</span></span>  
  
        -   `DB`  
  
        -   `FILELISTONLY`  
  
        -   `LABELONLY`  
  
        -   `HEADERONLY`  
  
        -   `VERIFYONLY`  
  
    -   <span data-ttu-id="e595b-142">È anche possibile trovare informazioni esaminando il registro eventi di Windows in registri applicazioni con il nome "SQLBackupToUrl".</span><span class="sxs-lookup"><span data-stu-id="e595b-142">You can also find information by reviewing the Windows Event Log - Under Application logs with the name 'SQLBackupToUrl'.</span></span>  
  
-   <span data-ttu-id="e595b-143">Quando si esegue il ripristino da un backup compresso, è possibile che venga visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="e595b-143">When restoring from a compressed backup, you might see the following error:</span></span>  
  
    -   <span data-ttu-id="e595b-144">**Si è verificato il 3284 SqlException. Gravità: 16 stato: 5**</span><span class="sxs-lookup"><span data-stu-id="e595b-144">**SqlException 3284 occurred. Severity: 16 State: 5**</span></span>  
        <span data-ttu-id="e595b-145">**Il contrassegno dei messaggi nel dispositivo ' https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak ' non è allineato. Eseguire nuovamente l'istruzione RESTORE con le stesse dimensioni del blocco utilizzate per creare il set di backupset:' 65536' è un possibile valore.**</span><span class="sxs-lookup"><span data-stu-id="e595b-145">**Message Filemark on device 'https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak' is not aligned. Reissue the Restore statement with the same block size used to create the backupset: '65536' looks like a possible value.**</span></span>  
  
         <span data-ttu-id="e595b-146">Per risolvere il problema, eseguire nuovamente l'istruzione `BACKUP` con il valore `BLOCKSIZE = 65536` specificato.</span><span class="sxs-lookup"><span data-stu-id="e595b-146">To solve this error, reissue the `BACKUP` statement with `BLOCKSIZE = 65536` specified.</span></span>  
  
-   <span data-ttu-id="e595b-147">Errore durante il backup a causa di BLOB con lease attivi: l'attività di backup non completata può generare BLOB con lease attivi.</span><span class="sxs-lookup"><span data-stu-id="e595b-147">Error during backup due to blobs that have active lease on them: Failed backup activity can result in blobs with active leases.</span></span>  
  
     <span data-ttu-id="e595b-148">Se si tenta di nuovo un'istruzione di backup, quest'ultimo potrebbe non essere completato e potrebbe essere visualizzato un errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e595b-148">If a backup statement is reattempted, backup operation might fail with an error similar to the following:</span></span>  
  
     <span data-ttu-id="e595b-149">**Il backup nell'URL ha ricevuto un'eccezione dall'endpoint remoto. Messaggio eccezione: Il server remoto ha restituito un errore: (412) Attualmente esiste un lease nel BLOB ma nella richiesta non è stato specificato alcun ID lease**.</span><span class="sxs-lookup"><span data-stu-id="e595b-149">**Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (412) There is currently a lease on the blob and no lease ID was specified in the request**.</span></span>  
  
     <span data-ttu-id="e595b-150">Se un'istruzione RESTORE viene tentata in un file BLOB di backup con un lease attivo, l'operazione di ripristino non viene completata e viene visualizzato un errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e595b-150">If a restore statement is attempted on a backup blob file that has an active lease, the restore operation fails with an error similar to the following:</span></span>  
  
     <span data-ttu-id="e595b-151">**Messaggio eccezione: Il server remoto ha restituito un errore: (409) Conflitto.**</span><span class="sxs-lookup"><span data-stu-id="e595b-151">**Exception Message: The remote server returned an error: (409) Conflict..**</span></span>  
  
     <span data-ttu-id="e595b-152">Quando si verifica un errore di questo tipo, i file BLOB devono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="e595b-152">When such error occurs, the blob files need to be deleted.</span></span> <span data-ttu-id="e595b-153">Per altre informazioni su questo scenario e su come risolvere il problema, vedere [Eliminazione dei file BLOB di backup con lease attivi](deleting-backup-blob-files-with-active-leases.md)</span><span class="sxs-lookup"><span data-stu-id="e595b-153">For more information on this scenario and how to correct this problem, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
## <a name="proxy-errors"></a><span data-ttu-id="e595b-154">Errori del proxy</span><span class="sxs-lookup"><span data-stu-id="e595b-154">Proxy Errors</span></span>  
 <span data-ttu-id="e595b-155">Se si utilizzano server proxy per accedere a Internet, è possibile che si verifichino i problemi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="e595b-155">If you are using Proxy Servers to access the internet, you may see the following issues:</span></span>  
  
 <span data-ttu-id="e595b-156">**Limitazione della connessione da parte dei server proxy**</span><span class="sxs-lookup"><span data-stu-id="e595b-156">**Connection throttling by Proxy Servers:**</span></span>  
  
 <span data-ttu-id="e595b-157">Nei server proxy possono essere presenti impostazioni che limitano il numero di connessioni al minuto.</span><span class="sxs-lookup"><span data-stu-id="e595b-157">Proxy Servers can have settings that limit the number of connections per minute.</span></span> <span data-ttu-id="e595b-158">Il backup su URL è un processo multithread e pertanto può superare il limite.</span><span class="sxs-lookup"><span data-stu-id="e595b-158">The Backup to URL process is a multi-threaded process and hence can go over this limit.</span></span> <span data-ttu-id="e595b-159">In questo caso, il server proxy termina la connessione.</span><span class="sxs-lookup"><span data-stu-id="e595b-159">If this happens, the proxy server kills the connection.</span></span> <span data-ttu-id="e595b-160">Per risolvere il problema, modificare le impostazioni del proxy in modo che non venga utilizzato in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e595b-160">To resolve this issue, change the proxy settings so SQL Server is not using the proxy.</span></span>   <span data-ttu-id="e595b-161">Di seguito sono riportati alcuni esempi di tipi o messaggi di errore visualizzati nel log degli errori:</span><span class="sxs-lookup"><span data-stu-id="e595b-161">Following are some examples of the types or error messages you may see in the error log:</span></span>  
  
-   <span data-ttu-id="e595b-162">Scrittura in " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak " non riuscita: il backup nell'URL ha ricevuto un'eccezione dall'endpoint remoto.</span><span class="sxs-lookup"><span data-stu-id="e595b-162">Write on "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak" failed: Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="e595b-163">Messaggio di eccezione: Impossibile leggere dati dalla connessione del trasporto. La connessione è stata chiusa.</span><span class="sxs-lookup"><span data-stu-id="e595b-163">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
-   <span data-ttu-id="e595b-164">Si è verificato un errore di I/O irreversibile nel file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Impossibile recuperare l'errore dall'endpoint remoto.</span><span class="sxs-lookup"><span data-stu-id="e595b-164">A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Error could not be gathered from Remote Endpoint.</span></span>  
  
     <span data-ttu-id="e595b-165">Messaggio 3013, livello 16, stato 1, riga 2</span><span class="sxs-lookup"><span data-stu-id="e595b-165">Msg 3013, Level 16, State 1, Line 2</span></span>  
  
     <span data-ttu-id="e595b-166">Interruzione anomala di BACKUP DATABASE in corso.</span><span class="sxs-lookup"><span data-stu-id="e595b-166">BACKUP DATABASE is terminating abnormally.</span></span>  
  
-   <span data-ttu-id="e595b-167">BackupIoRequest:: ReportIoError: errore di scrittura nel dispositivo di backup ' http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak '.</span><span class="sxs-lookup"><span data-stu-id="e595b-167">BackupIoRequest::ReportIoError: write failure on backup device 'http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak'.</span></span> <span data-ttu-id="e595b-168">Errore del sistema operativo: Il backup nell'URL ha ricevuto un'eccezione dall'endpoint remoto.</span><span class="sxs-lookup"><span data-stu-id="e595b-168">Operating system error Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="e595b-169">Messaggio di eccezione: Impossibile leggere dati dalla connessione del trasporto. La connessione è stata chiusa.</span><span class="sxs-lookup"><span data-stu-id="e595b-169">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
 <span data-ttu-id="e595b-170">Se si abilita la registrazione dettagliata mediante il flag di traccia 3051, è inoltre possibile che nei log venga visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="e595b-170">If you turn on the verbose logging using the trace flag 3051 you may also see the following message in the logs:</span></span>  
  
 <span data-ttu-id="e595b-171">Codice di stato HTTP 502. Messaggio di stato HTTP: errore del proxy (Il numero di richieste HTTP al minuto supera il limite configurato.</span><span class="sxs-lookup"><span data-stu-id="e595b-171">HTTP status code 502, HTTP Status Message Proxy Error ( The number of HTTP requests per minute exceeded the configured limit.</span></span> <span data-ttu-id="e595b-172">Contattare l'amministratore di ISA Server).</span><span class="sxs-lookup"><span data-stu-id="e595b-172">Contact your ISA Server administrator.</span></span>  <span data-ttu-id="e595b-173">)</span><span class="sxs-lookup"><span data-stu-id="e595b-173">)</span></span>  
  
 <span data-ttu-id="e595b-174">**Impostazioni proxy predefinite non rilevate:**</span><span class="sxs-lookup"><span data-stu-id="e595b-174">**Default Proxy Settings not picked up:**</span></span>  
  
 <span data-ttu-id="e595b-175">Talvolta le impostazioni predefinite non vengono prelevate, causando errori di autenticazione del proxy come quello riportato di seguito:*si è verificato un errore di i/O irreversibile nel file " http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: ". il backup nell'URL ha ricevuto un'eccezione dall'endpoint remoto. Messaggio eccezione: il server remoto ha restituito un errore: (407)* è **richiesta l'autenticazione proxy**.</span><span class="sxs-lookup"><span data-stu-id="e595b-175">Sometimes the default settings are not picked up causing proxy authentication errors such as the one shown below:*A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (407)* **Proxy Authentication Required**.</span></span>  
  
 <span data-ttu-id="e595b-176">Per risolvere il problema, creare un file di configurazione che consenta al processo di backup su URL di utilizzare le impostazioni predefinite del proxy effettuando i passaggi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="e595b-176">To resolve this issue, create a configuration file that allows the Backup to URL process to use the default proxy settings using the following steps:</span></span>  
  
1.  <span data-ttu-id="e595b-177">Creare un file di configurazione denominato BackuptoURL.exe.config con il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="e595b-177">Create a configuration file named BackuptoURL.exe.config  with the following xml:</span></span>  
  
    ```  
    <?xml version ="1.0"?>  
    <configuration>   
                    <system.net>   
                                    <defaultProxy enabled="true" useDefaultCredentials="true">   
                                                    <proxy usesystemdefault="true" />   
                                    </defaultProxy>   
                    </system.net>  
    </configuration>  
  
    ```  
  
2.  <span data-ttu-id="e595b-178">Inserire il file di configurazione nella cartella Binn dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e595b-178">Place the configuration file in the Binn folder of the SQL Server Instance.</span></span> <span data-ttu-id="e595b-179">Se, ad esempio, il SQL Server è installato nell'unità C del computer, inserire il file di configurazione in: *C:\Programmi\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\Binn*.</span><span class="sxs-lookup"><span data-stu-id="e595b-179">For example, if my SQL Server is installed on the C drive of the machine, place the configuration file here: *C:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Binn*.</span></span>  
  
## <a name="troubleshooting-sql-server-managed-backup-to-azure"></a><span data-ttu-id="e595b-180">Risoluzione dei problemi relativi al backup gestito di SQL Server in Azure</span><span class="sxs-lookup"><span data-stu-id="e595b-180">Troubleshooting SQL Server Managed Backup to Azure</span></span>  
 <span data-ttu-id="e595b-181">Poiché Backup gestito di SQL Server è compilato in Backup nell'URL, i suggerimenti per la risoluzione di problemi descritti nelle sezioni precedenti vengono applicati ai database o alle istanze tramite Backup gestito di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e595b-181">Since SQL Server Managed Backup is built on top of Backup to URL, the troubleshooting tips described in the earlier sections apply to databases or instances using SQL Server Managed Backup.</span></span>  <span data-ttu-id="e595b-182">Informazioni dettagliate sulla risoluzione dei problemi di SQL Server backup gestito in Azure sono descritte in [risoluzione dei problemi di SQL Server backup gestito in Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="e595b-182">Information about troubleshooting SQL Server Managed Backup to Azure is described in detail in [Troubleshooting SQL Server Managed  Backup to Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e595b-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e595b-183">See Also</span></span>  
 [<span data-ttu-id="e595b-184">Ripristino da backup archiviati in Azure</span><span class="sxs-lookup"><span data-stu-id="e595b-184">Restoring From Backups Stored in Azure</span></span>](restoring-from-backups-stored-in-microsoft-azure.md)  
  
  
