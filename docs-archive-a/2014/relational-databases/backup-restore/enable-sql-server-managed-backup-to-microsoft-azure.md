---
title: Configurazione di SQL Server backup gestito in Azure | Microsoft Docs
ms.custom: ''
ms.date: 08/04/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 68ebb53e-d5ad-4622-af68-1e150b94516e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9e3b86fde91028106263310aad8a1952fc041a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636733"
---
# <a name="setting-up-sql-server-managed-backup-to-azure"></a><span data-ttu-id="22202-102">Configurazione del backup gestito di SQL Server in Azure</span><span class="sxs-lookup"><span data-stu-id="22202-102">Setting up SQL Server Managed Backup to Azure</span></span>
  <span data-ttu-id="22202-103">In questo argomento vengono illustrate due esercitazioni:</span><span class="sxs-lookup"><span data-stu-id="22202-103">This topic includes two tutorials:</span></span>  
  
 <span data-ttu-id="22202-104">Configurare il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] a livello di database, abilitare la notifica tramite posta elettronica e monitorare l'attività di backup.</span><span class="sxs-lookup"><span data-stu-id="22202-104">Set up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="22202-105">Configurare il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] a livello di istanza, abilitare la notifica tramite posta elettronica e monitorare l'attività di backup.</span><span class="sxs-lookup"><span data-stu-id="22202-105">Setting up  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the instance level, enable email notification, and monitor backup activity.</span></span>  
  
 <span data-ttu-id="22202-106">Per un'esercitazione sulla configurazione [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per i gruppi di disponibilità, vedere [configurazione di SQL Server Backup gestito Microsoft Azure per i gruppi di disponibilità](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="22202-106">For a tutorial on setting up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for Availability Groups, see [Setting up SQL Server Managed Backup to Microsoft Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
## <a name="setting-up-ss_smartbackup"></a><span data-ttu-id="22202-107">Configurazione del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22202-107">Setting Up [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)]</span></span>  
  
### <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><span data-ttu-id="22202-108">Abilitare e configurare [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per un database</span><span class="sxs-lookup"><span data-stu-id="22202-108">Enable and Configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="22202-109">In questa esercitazione vengono descritti i passaggi necessari per abilitare e configurare il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per un database (TestDB), nonché i passaggi per abilitare il monitoraggio dello stato di integrità del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22202-109">This tutorial describes the steps necessary to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a database (TestDB), followed by steps to enable monitoring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="22202-110">**Autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="22202-110">**Permissions:**</span></span>  
  
-   <span data-ttu-id="22202-111">È richiesta l'appartenenza al ruolo **db_backupoperator** database, con autorizzazioni **ALTER ANY CREDENTIAL** e `EXECUTE` autorizzazioni per **sp_delete_backuphistory**stored procedure.</span><span class="sxs-lookup"><span data-stu-id="22202-111">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="22202-112">Sono richieste le autorizzazioni **Select** per la funzione **smart_admin. fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="22202-112">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="22202-113">`EXECUTE`Sono necessarie le autorizzazioni per il stored procedure **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="22202-113">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="22202-114">È inoltre richiesta l'autorizzazione `VIEW SERVER STATE` poiché vengono chiamati internamente altri oggetti di sistema che richiedono tale autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="22202-114">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  
  
-   <span data-ttu-id="22202-115">`EXECUTE`Sono necessarie le autorizzazioni per le `smart_admin.sp_set_instance_backup` `smart_admin.sp_backup_master_switch` stored procedure e.</span><span class="sxs-lookup"><span data-stu-id="22202-115">Requires `EXECUTE` permissions on the `smart_admin.sp_set_instance_backup` and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  


1.  <span data-ttu-id="22202-116">**Creare un account di archiviazione Microsoft Azure:** I backup vengono archiviati nel servizio di archiviazione Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="22202-116">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="22202-117">Se non si dispone già di un account, è necessario creare prima un account di archiviazione Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="22202-117">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="22202-118">SQL Server 2014 USA i BLOB di pagine, che sono diversi dai BLOB in blocchi e di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="22202-118">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="22202-119">Pertanto, è necessario creare un account per utilizzo generico e non un account BLOB.</span><span class="sxs-lookup"><span data-stu-id="22202-119">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="22202-120">Per altre informazioni, vedere [Informazioni sugli account di archiviazione di Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="22202-120">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="22202-121">Prendere nota del nome dell'account di archiviazione e delle chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="22202-121">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="22202-122">Le informazioni sul nome dell'account di archiviazione e sulla chiave di accesso vengono utilizzate per creare le credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="22202-122">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="22202-123">Le credenziali SQL vengono utilizzate per l'autenticazione dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="22202-123">The SQL Credential is used to authenticate to the storage account.</span></span>  
 
2.  <span data-ttu-id="22202-124">**Creare credenziali SQL:** Creare credenziali SQL usando il nome dell'account di archiviazione come identità e la chiave di accesso alle archiviazione come password.</span><span class="sxs-lookup"><span data-stu-id="22202-124">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="22202-125">**Verificare che SQL Server Agent servizio sia avviato e in esecuzione:**  Avviare SQL Server Agent se non è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="22202-125">**Ensure SQL Server Agent service is Started and Running:**  Start SQL Server Agent if it is not currently running.</span></span>  [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="22202-126">è necessaria l'esecuzione di SQL Server Agent nell'istanza per poter eseguire le operazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="22202-126">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="22202-127">Per assicurarsi che le operazioni in questione vengano eseguite regolarmente, è possibile impostare l'esecuzione automatica di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="22202-127">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="22202-128">**Determinare il periodo di conservazione:** determinare il periodo di conservazione per i file di backup.</span><span class="sxs-lookup"><span data-stu-id="22202-128">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="22202-129">Il periodo di memorizzazione viene specificato in giorni in un intervallo compreso tra 1 e 30.</span><span class="sxs-lookup"><span data-stu-id="22202-129">The retention period is specified in days and can range from 1 to 30.</span></span>  
  
5.  <span data-ttu-id="22202-130">**Abilitare e configurare [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** avviare SQL Server Management Studio e connettersi all'istanza in cui è installato il database.</span><span class="sxs-lookup"><span data-stu-id="22202-130">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance where the database is installed.</span></span> <span data-ttu-id="22202-131">Nella finestra Query eseguire l'istruzione riportata di seguito dopo aver modificato i valori per le opzioni relative al nome del database, alle credenziali SQL, al periodo di memorizzazione e alla crittografia in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="22202-131">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="22202-132">Per ulteriori informazioni sulla creazione di un certificato per la crittografia, vedere il passaggio **creare un certificato di backup** in [creare un backup crittografato](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="22202-132">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@retention_days=30   
                    ,@credential_name='MyCredential'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
                    ,@enable_backup=1;  
    GO  
  
    ```  
  
     [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="22202-133">ora è abilitato nel database specificato.</span><span class="sxs-lookup"><span data-stu-id="22202-133">is now enabled on the database you specified.</span></span> <span data-ttu-id="22202-134">L'inizio delle operazioni di backup nel database può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="22202-134">It may take up to 15 minutes for the backup operations on the database to start to run.</span></span>  
  
6.  <span data-ttu-id="22202-135">**Esaminare la configurazione predefinita degli eventi estesi:** esaminare le impostazioni degli eventi estesi eseguendo l'istruzione transact-SQL seguente.</span><span class="sxs-lookup"><span data-stu-id="22202-135">**Review Extended Event Default Configuration:** Review the Extended Event settings by running the following transact-SQL statement.</span></span>  
  
    ```  
    SELECT * FROM smart_admin.fn_get_current_xevent_settings()  
    ```  
  
     <span data-ttu-id="22202-136">Verificare che gli eventi dei canali amministrativo, operativo e analitico siano abilitati per impostazione predefinita e che non possano essere disabilitati.</span><span class="sxs-lookup"><span data-stu-id="22202-136">You should see that Admin, Operational, and Analytical channel events are enabled by default and cannot be disabled.</span></span> <span data-ttu-id="22202-137">Questa verifica dovrebbe essere sufficiente per monitorare gli eventi per i quali è richiesto un intervento manuale.</span><span class="sxs-lookup"><span data-stu-id="22202-137">This should be sufficient to monitor the events that require manual intervention.</span></span>  <span data-ttu-id="22202-138">È possibile abilitare eventi di debug, ma nei canali di debug sono inclusi eventi informativi e di debug utilizzati dal [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per rilevare eventuali problemi e risolverli.</span><span class="sxs-lookup"><span data-stu-id="22202-138">You can enable debug events, but the debug channels include informational and debug events that [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] uses to detect issues and solve them.</span></span> <span data-ttu-id="22202-139">Per altre informazioni, vedere [monitorare SQL Server backup gestito Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="22202-139">For more information, see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
7.  <span data-ttu-id="22202-140">**Abilitare e configurare notifiche per lo stato di integrità:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] contiene una stored procedure che consente di creare un processo dell'agente per inviare notifiche via posta elettronica di errori o avvisi che potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="22202-140">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span> <span data-ttu-id="22202-141">Nei passaggi seguenti viene illustrato il processo per abilitare e configurare le notifiche tramite posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="22202-141">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="22202-142">Configurare Posta elettronica database se non è già abilitato nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="22202-142">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="22202-143">Per altre informazioni, vedere [Configurare Posta elettronica database](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="22202-143">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="22202-144">Configurare la notifica di SQL Server Agent per l'uso di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="22202-144">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="22202-145">Per altre informazioni, vedere [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="22202-145">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="22202-146">**Abilitare le notifiche di posta elettronica per ricevere avvisi ed errori di backup:** nella finestra di query eseguire le istruzioni Transact-SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="22202-146">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email1;email2>'  
  
        ```  
  
         <span data-ttu-id="22202-147">Per ulteriori informazioni e per uno script di esempio completo, vedere [monitorare SQL Server backup gestito Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="22202-147">For more information, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
8.  <span data-ttu-id="22202-148">**Visualizzare i file di backup nell'account di archiviazione Microsoft Azure** : connettersi all'account di archiviazione da SQL Server Management Studio o dal portale di gestione di Azure.</span><span class="sxs-lookup"><span data-stu-id="22202-148">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="22202-149">Verrà visualizzato un contenitore per l'istanza di SQL Server in cui viene ospitato il database configurato per utilizzare il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22202-149">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="22202-150">È inoltre possibile visualizzare un database e un backup del log entro 15 minuti dall'abilitazione del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per il database.</span><span class="sxs-lookup"><span data-stu-id="22202-150">You may also see a database and a log backup within 15 minutes of enabling [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the database.</span></span>  
  
9. <span data-ttu-id="22202-151">**Monitorare lo stato di integrità:**  è possibile eseguire il monitoraggio attraverso notifiche tramite posta elettronica configurate in precedenza o monitorare attivamente gli eventi registrati.</span><span class="sxs-lookup"><span data-stu-id="22202-151">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="22202-152">Di seguito sono riportate alcune istruzioni Transact-SQL di esempio utilizzate per visualizzare gli eventi:</span><span class="sxs-lookup"><span data-stu-id="22202-152">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    -- to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="22202-153">I passaggi descritti in questa sezione riguardano in modo specifico la configurazione del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per la prima volta nel database.</span><span class="sxs-lookup"><span data-stu-id="22202-153">The steps described in this section are specifically for configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the first time on the database.</span></span> <span data-ttu-id="22202-154">È possibile modificare le configurazioni esistenti utilizzando lo stesso sistema stored procedure **smart_admin. sp_set_db_backup** e specificare i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="22202-154">You can modify the existing configurations using the same system stored procedure **smart_admin.sp_set_db_backup** and provide the new values.</span></span> <span data-ttu-id="22202-155">Per ulteriori informazioni, vedere [SQL Server backup gestito in impostazioni di archiviazione e conservazione Microsoft Azure](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span><span class="sxs-lookup"><span data-stu-id="22202-155">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md).</span></span>  
  
### <a name="enable-ss_smartbackup-for-the-instance-with-default-settings"></a><span data-ttu-id="22202-156">Abilitare il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per l'istanza con le impostazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="22202-156">Enable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the Instance with Default Settings</span></span>  
 <span data-ttu-id="22202-157">In questa esercitazione vengono descritti i passaggi per abilitare e configurare [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per l'istanza, ovvero "istanza", \\ .</span><span class="sxs-lookup"><span data-stu-id="22202-157">This tutorial describes the steps to enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for the instance, 'MyInstance',\\.</span></span> <span data-ttu-id="22202-158">Sono inclusi i passaggi per abilitare il monitoraggio dello stato di integrità del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22202-158">It includes steps to enable monitoring the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] health status.</span></span>  
  
 <span data-ttu-id="22202-159">**Autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="22202-159">**Permissions:**</span></span>  
  
-   <span data-ttu-id="22202-160">È richiesta l'appartenenza al ruolo **db_backupoperator** database, con autorizzazioni **ALTER ANY CREDENTIAL** e `EXECUTE` autorizzazioni per **sp_delete_backuphistory**stored procedure.</span><span class="sxs-lookup"><span data-stu-id="22202-160">Requires membership in **db_backupoperator** database role, with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on **sp_delete_backuphistory**stored procedure.</span></span>  
  
-   <span data-ttu-id="22202-161">Sono richieste le autorizzazioni **Select** per la funzione **smart_admin. fn_get_current_xevent_settings**.</span><span class="sxs-lookup"><span data-stu-id="22202-161">Requires **SELECT** permissions on the **smart_admin.fn_get_current_xevent_settings**function.</span></span>  
  
-   <span data-ttu-id="22202-162">`EXECUTE`Sono necessarie le autorizzazioni per il stored procedure **smart_admin. sp_get_backup_diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="22202-162">Requires `EXECUTE` permissions on the **smart_admin.sp_get_backup_diagnostics** stored procedure.</span></span> <span data-ttu-id="22202-163">È inoltre richiesta l'autorizzazione `VIEW SERVER STATE` poiché vengono chiamati internamente altri oggetti di sistema che richiedono tale autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="22202-163">In addition, it requires `VIEW SERVER STATE` permissions as it internally calls other system objects that require this permission.</span></span>  


1.  <span data-ttu-id="22202-164">**Creare un account di archiviazione Microsoft Azure:** I backup vengono archiviati nel servizio di archiviazione Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="22202-164">**Create a Microsoft Azure storage account:** The backups are stored in the Microsoft Azure storage service.</span></span> <span data-ttu-id="22202-165">Se non si dispone già di un account, è necessario creare prima un account di archiviazione Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="22202-165">You must first create a Microsoft Azure storage account, if you do not already have an account.</span></span>
    - <span data-ttu-id="22202-166">SQL Server 2014 USA i BLOB di pagine, che sono diversi dai BLOB in blocchi e di Accodamento.</span><span class="sxs-lookup"><span data-stu-id="22202-166">SQL Server 2014 uses page blobs, which are different than block and append blobs.</span></span> <span data-ttu-id="22202-167">Pertanto, è necessario creare un account per utilizzo generico e non un account BLOB.</span><span class="sxs-lookup"><span data-stu-id="22202-167">Therefore you must create a general purpose account, and not a blob account.</span></span> <span data-ttu-id="22202-168">Per altre informazioni, vedere [Informazioni sugli account di archiviazione di Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span><span class="sxs-lookup"><span data-stu-id="22202-168">For more information, see [About Azure storage accounts](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/).</span></span>
    - <span data-ttu-id="22202-169">Prendere nota del nome dell'account di archiviazione e delle chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="22202-169">Make a note of the storage account name, and the access keys.</span></span> <span data-ttu-id="22202-170">Le informazioni sul nome dell'account di archiviazione e sulla chiave di accesso vengono utilizzate per creare le credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="22202-170">The storage account name and access key information is used to create a SQL Credential.</span></span> <span data-ttu-id="22202-171">Le credenziali SQL vengono utilizzate per l'autenticazione dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="22202-171">The SQL Credential is used to authenticate to the storage account.</span></span>  
  
2.  <span data-ttu-id="22202-172">**Creare credenziali SQL:** Creare credenziali SQL usando il nome dell'account di archiviazione come identità e la chiave di accesso alle archiviazione come password.</span><span class="sxs-lookup"><span data-stu-id="22202-172">**Create a SQL Credential:** Create a SQL Credential using the name of the storage account as the Identity and the storage access key as the password.</span></span>  
  
3.  <span data-ttu-id="22202-173">**Assicurarsi che il servizio SQL Server Agent sia avviato e in esecuzione:** se non è in esecuzione, avviare SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="22202-173">**Ensure SQL Server Agent service is Started and Running:** Start SQL Server Agent if it is not currently running.</span></span> [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] <span data-ttu-id="22202-174">è necessaria l'esecuzione di SQL Server Agent nell'istanza per poter eseguire le operazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="22202-174">requires SQL Server Agent to be running on the instance to perform backup operations.</span></span>  <span data-ttu-id="22202-175">Per assicurarsi che le operazioni in questione vengano eseguite regolarmente, è possibile impostare l'esecuzione automatica di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="22202-175">You may want to set SQL Server Agent to run automatically to make sure that backup operations can occur regularly.</span></span>  
  
4.  <span data-ttu-id="22202-176">**Determinare il periodo di conservazione:** determinare il periodo di conservazione per i file di backup.</span><span class="sxs-lookup"><span data-stu-id="22202-176">**Determine the retention period:** Determine the retention period for the backup files.</span></span> <span data-ttu-id="22202-177">Il periodo di memorizzazione viene specificato in giorni in un intervallo compreso tra 1 e 30.</span><span class="sxs-lookup"><span data-stu-id="22202-177">The retention period is specified in days and can range from 1 to 30.</span></span> <span data-ttu-id="22202-178">Dopo avere abilitato il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] a livello di istanza con le impostazioni predefinite, tutti i nuovi database creati successivamente erediteranno le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="22202-178">Once [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is enabled at the instance level with the defaults all new databases created thereafter will inherit the settings.</span></span> <span data-ttu-id="22202-179">Solo i database impostati sui modelli di recupero con registrazione completa o con registrazione minima delle operazioni bulk sono supportati e saranno configurati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="22202-179">Only databases that are set to full or bulk-logged recovery models are supported and will be configured automatically.</span></span> <span data-ttu-id="22202-180">È possibile disabilitare il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per un database specifico in qualsiasi momento se non si vuole che [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] venga configurato.</span><span class="sxs-lookup"><span data-stu-id="22202-180">You may disable [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] for a specific database at any time if you  do not want [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configured.</span></span> <span data-ttu-id="22202-181">È inoltre possibile modificare la configurazione per un database specifico configurando il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] a livello di database.</span><span class="sxs-lookup"><span data-stu-id="22202-181">You can also change the configuration for a specific database by configuring [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
5.  <span data-ttu-id="22202-182">**Abilitare e configurare [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** avviare SQL Server Management Studio e connettersi all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="22202-182">**Enable and configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] :** Start SQL Server Management Studio and connect to the instance of SQL Server.</span></span> <span data-ttu-id="22202-183">Nella finestra Query eseguire l'istruzione riportata di seguito dopo aver modificato i valori per le opzioni relative al nome del database, alle credenziali SQL, al periodo di memorizzazione e alla crittografia in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="22202-183">From the query window run the following statement after you modify the values for the database name, SQL Credential, retention period, and the encryption options per your requirements:</span></span>  
  
     <span data-ttu-id="22202-184">Per ulteriori informazioni sulla creazione di un certificato per la crittografia, vedere il passaggio **creare un certificato di backup** in [creare un backup crittografato](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="22202-184">For more information on creating a certificate for encryption, see the **Create a Backup Certificate** step in [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
    ```  
    Use msdb;  
    Go  
       EXEC smart_admin.sp_set_instance_backup  
                     @enable_backup=1  
                    ,@retention_days=30   
                    ,@credential_name='sqlbackuptoURL'  
                    ,@encryption_algorithm ='AES_128'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert';  
    GO  
  
    ```  
  
     <span data-ttu-id="22202-185">A questo punto il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] è abilitato nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="22202-185">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] is now enabled on the instance.</span></span>  
  
6.  <span data-ttu-id="22202-186">Verificare le impostazioni di configurazione eseguendo l'istruzione Transact-SQL riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="22202-186">Verify the configuration settings by running the following Transact-SQL statement:</span></span>  
  
    ```  
    Use msdb;  
    GO  
    SELECT * FROM smart_admin.fn_backup_instance_config ();  
  
    ```  
  
7.  <span data-ttu-id="22202-187">Creare un nuovo database nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="22202-187">Create a new database on the instance.</span></span> <span data-ttu-id="22202-188">Eseguire l'istruzione Transact-SQL riportata di seguito per visualizzare le impostazioni di configurazione del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] per il database:</span><span class="sxs-lookup"><span data-stu-id="22202-188">Run the following Transact-SQL statement to view the [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] configuration settings for the database:</span></span>  
  
    ```  
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('NewDB')  
    ```  
  
     <span data-ttu-id="22202-189">La visualizzazione delle impostazioni e l'inizio delle operazioni di backup nel database può richiedere fino a 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="22202-189">It may take up to 15 minutes for the settings to show and backup operations on the database to start to run.</span></span>  
  
8.  <span data-ttu-id="22202-190">**Abilitare e configurare notifiche per lo stato di integrità:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] contiene una stored procedure che consente di creare un processo dell'agente per inviare notifiche via posta elettronica di errori o avvisi che potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="22202-190">**Enable and Configure Notification for Health Status:** [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] has a stored procedure that creates an agent job to send out e-mail notifications of errors or warnings that may require attention.</span></span>  <span data-ttu-id="22202-191">Per ricevere notifiche di questo tipo, è necessario eseguire la stored procedure per creare un processo di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="22202-191">To receive such notifications, you must enable run the stored procedure which creates a SQL Server Agent Job.</span></span> <span data-ttu-id="22202-192">Nei passaggi seguenti viene illustrato il processo per abilitare e configurare le notifiche tramite posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="22202-192">The following steps describe the process to enable and configure e-mail notifications:</span></span>  
  
    1.  <span data-ttu-id="22202-193">Configurare Posta elettronica database se non è già abilitato nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="22202-193">Setup Database Mail if it is not already enabled on the instance.</span></span> <span data-ttu-id="22202-194">Per altre informazioni, vedere [Configurare Posta elettronica database](../database-mail/configure-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="22202-194">For more information, see [Configure Database Mail](../database-mail/configure-database-mail.md).</span></span>  
  
    2.  <span data-ttu-id="22202-195">Configurare la notifica di SQL Server Agent per l'uso di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="22202-195">Configure SQL Server Agent Notification to use Database Mail.</span></span> <span data-ttu-id="22202-196">Per altre informazioni, vedere [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span><span class="sxs-lookup"><span data-stu-id="22202-196">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md).</span></span>  
  
    3.  <span data-ttu-id="22202-197">**Abilitare le notifiche di posta elettronica per ricevere avvisi ed errori di backup:** nella finestra di query eseguire le istruzioni Transact-SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="22202-197">**Enable e-mail notifications to receive backup errors and warnings:** From the query window, run the following Transact-SQL statements:</span></span>  
  
        ```  
        EXEC msdb.smart_admin.sp_set_parameter  
        @parameter_name = 'SSMBackup2WANotificationEmailIds',  
        @parameter_value = '<email address>'  
  
        ```  
  
         <span data-ttu-id="22202-198">Per ulteriori informazioni sul monitoraggio e su uno script di esempio completo, vedere [monitorare SQL Server backup gestito Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="22202-198">For more information about how to monitor, and a full sample script see [Monitor SQL Server Managed Backup to Microsoft Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
9. <span data-ttu-id="22202-199">**Visualizzare i file di backup nell'account di archiviazione Microsoft Azure** : connettersi all'account di archiviazione da SQL Server Management Studio o dal portale di gestione di Azure.</span><span class="sxs-lookup"><span data-stu-id="22202-199">**View backup files in the Microsoft Azure Storage Account:** Connect to the storage account from SQL Server Management Studio or the Azure Management Portal.</span></span> <span data-ttu-id="22202-200">Verrà visualizzato un contenitore per l'istanza di SQL Server in cui viene ospitato il database configurato per utilizzare il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22202-200">You will see a container for the instance of SQL Server that hosts the database you configured to use [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="22202-201">È inoltre possibile visualizzare un database e un backup del log entro 15 minuti dalla creazione di un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="22202-201">You may also see a database and a log backup within 15 minutes of creating a new database.</span></span>  
  
10. <span data-ttu-id="22202-202">**Monitorare lo stato di integrità:**  è possibile eseguire il monitoraggio attraverso notifiche tramite posta elettronica configurate in precedenza o monitorare attivamente gli eventi registrati.</span><span class="sxs-lookup"><span data-stu-id="22202-202">**Monitor the Health Status:**  You can monitor through e-mail notifications you configured previously, or actively monitor the events logged.</span></span> <span data-ttu-id="22202-203">Di seguito sono riportate alcune istruzioni Transact-SQL di esempio utilizzate per visualizzare gli eventi:</span><span class="sxs-lookup"><span data-stu-id="22202-203">The following are some example Transact-SQL Statements used to view the events:</span></span>  
  
    ```  
    --  view all admin events  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    DECLARE @eventresult TABLE  
    (event_type nvarchar(512),  
    event nvarchar (512),  
    timestamp datetime  
    )  
  
    INSERT INTO @eventresult  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek  
  
    SELECT * from @eventresult  
    WHERE event_type LIKE '%admin%'  
  
    ```  
  
    ```  
    --  to enable debug events  
    Use msdb;  
    Go  
             EXEC smart_admin.sp_set_parameter 'FileRetentionDebugXevent', 'True'  
  
    ```  
  
    ```  
    --  View all events in the current week  
    Use msdb;  
    Go  
    DECLARE @startofweek datetime  
    DECLARE @endofweek datetime  
    SET @startofweek = DATEADD(Day, 1-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)   
    SET @endofweek = DATEADD(Day, 7-DATEPART(WEEKDAY, CURRENT_TIMESTAMP), CURRENT_TIMESTAMP)  
  
    EXEC smart_admin.sp_get_backup_diagnostics @begin_time = @startofweek, @end_time = @endofweek;  
  
    ```  
  
 <span data-ttu-id="22202-204">Le impostazioni predefinite del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] possono essere ignorate per un database specifico configurando le impostazioni in particolare a livello di database.</span><span class="sxs-lookup"><span data-stu-id="22202-204">[!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] default settings can be overridden for a specific database by configuring the settings specifically at the database level.</span></span> <span data-ttu-id="22202-205">È inoltre possibile sospendere e riprendere temporaneamente il servizio del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22202-205">You can also pause and resume [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] service temporarily.</span></span> <span data-ttu-id="22202-206">Per altre informazioni, vedere [SQL Server backup gestito in impostazioni di archiviazione e memorizzazione Microsoft Azure](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)</span><span class="sxs-lookup"><span data-stu-id="22202-206">For more information, see [SQL Server Managed Backup to Microsoft Azure - Retention and Storage Settings](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)</span></span>  
  
  
