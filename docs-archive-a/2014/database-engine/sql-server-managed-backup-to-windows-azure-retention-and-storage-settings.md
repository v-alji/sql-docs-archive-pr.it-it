---
title: SQL Server il backup gestito in Azure-impostazioni di archiviazione e memorizzazione | Microsoft Docs
description: In questo argomento viene descritto come configurare SQL Server backup gestito per Microsoft Azure per un database e per configurare le impostazioni predefinite per l'istanza.
ms.custom: ''
ms.date: 08/23/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: c4aa26ea-5465-40cc-8b83-f50603cb9db1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8ebdb81f8aa9edb9cd9326bcb1d286d5d3fe632c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721724"
---
# <a name="sql-server-managed-backup-to-azure---retention-and-storage-settings"></a><span data-ttu-id="3a335-103">Backup gestito di SQL Server in Azure - Impostazioni di archiviazione e di memorizzazione</span><span class="sxs-lookup"><span data-stu-id="3a335-103">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>
  <span data-ttu-id="3a335-104">In questo argomento vengono descritti i passaggi di base per configurare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per un database e per configurare le impostazioni predefinite per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-104">This topic describes the basic steps to configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database and to configure default settings for the instance.</span></span> <span data-ttu-id="3a335-105">Vengono inoltre descritti i passaggi necessari per sospendere e riprendere i servizi [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-105">The topic also describes the steps necessary to pause and resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for the instance.</span></span>  
  
 <span data-ttu-id="3a335-106">Per una procedura dettagliata completa della configurazione [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , vedere [configurazione di SQL Server backup gestito in Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) e [configurazione di SQL Server backup gestito in Azure per i gruppi di disponibilità](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3a335-106">For a complete walkthrough of setting up [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] see [Setting up SQL Server Managed Backup to Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3a335-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3a335-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3a335-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3a335-108">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3a335-109">Non abilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] nei database in cui sono attualmente in uso piani di manutenzione o il log shipping.</span><span class="sxs-lookup"><span data-stu-id="3a335-109">Do not enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on databases that are currently using maintenance plans or log shipping.</span></span> <span data-ttu-id="3a335-110">Per altre informazioni sull'interoperabilità e la coesistenza con altre funzionalità di SQL Server, vedere [SQL Server backup gestito in Azure: interoperabilità e coesistenza](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span><span class="sxs-lookup"><span data-stu-id="3a335-110">For more information on interoperability and coexistence with other SQL Server features, see [SQL Server Managed Backup to Azure: Interoperability and Coexistence](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3a335-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3a335-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="3a335-112">SQL Server Agent deve essere in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3a335-112">SQL Server Agent should be running.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="3a335-113">Se SQL Server Agent viene arrestato per un periodo di tempo e poi riavviato, è possibile che venga visualizzata una maggiore attività di backup a seconda della quantità di tempo trascorso tra l'arresto e l'avvio di SQL Agent e che sia in attesa di esecuzione un backlog di backup del log.</span><span class="sxs-lookup"><span data-stu-id="3a335-113">If SQL Server Agent is stopped for a period of time and then restarted, you may see an increased backup activity depending on the length of time elapsed between the stop and start of SQL Agent, and there might be a backlog of log backups waiting to run.</span></span> <span data-ttu-id="3a335-114">Provare a configurare SQL Server Agent in modo tale che all'avvio venga avviato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a335-114">Consider configuring SQL Server Agent to start automatically on start up.</span></span>  
  
-   <span data-ttu-id="3a335-115">Prima di configurare un account di archiviazione di Azure e le credenziali SQL che archiviano le informazioni di autenticazione nell'account di archiviazione [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a335-115">A Azure storage account and a SQL Credential that stores the authentication information to the storage account should both be created before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="3a335-116">Per altre informazioni, vedere la sezione [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) dell'argomento **Backup di SQL Server nell'URL** e [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="3a335-116">For more information see [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) section of the **SQL Server Backup to URL** topic, and [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3a335-117">Tramite [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] vengono creati i contenitori necessari per archiviare i backup.</span><span class="sxs-lookup"><span data-stu-id="3a335-117">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] creates the necessary containers to store the backups.</span></span> <span data-ttu-id="3a335-118">Il nome del contenitore viene creato utilizzando il formato "nome computer-nome istanza".</span><span class="sxs-lookup"><span data-stu-id="3a335-118">The container name is created using 'machine name-instance name' format.</span></span> <span data-ttu-id="3a335-119">Nel caso dei gruppi di disponibilità AlwaysOn, il contenitore viene denominato utilizzando il GUID del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="3a335-119">For AlwaysOn Availability Groups the container is named using the GUID of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3a335-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3a335-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3a335-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3a335-121">Permissions</span></span>  
 <span data-ttu-id="3a335-122">Per eseguire le stored procedure che abilitano [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , è necessario essere un `System Administrator` membro o nel ruolo del database **Db_backupoperator** con autorizzazioni **ALTER ANY CREDENTIAL** , nonché le `EXECUTE` autorizzazioni per l' **sp_delete_backuphistory**e `smart_admin.sp_backup_master_switch` le stored procedure.</span><span class="sxs-lookup"><span data-stu-id="3a335-122">To run the stored procedures that enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], you must be a  either a `System Administrator` or  member  in the **db_backupoperator** database role with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on the **sp_delete_backuphistory**, and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  <span data-ttu-id="3a335-123">Per le stored procedure e le funzioni utilizzate per esaminare le impostazioni esistenti sono in genere richieste rispettivamente le autorizzazioni `Execute` per la stored procedure e `Select` per la funzione.</span><span class="sxs-lookup"><span data-stu-id="3a335-123">Stored procedures and functions used to review the existing settings typically require `Execute` permissions on the stored procedure and `Select` on the function respectively.</span></span>  
  

  
###  <a name="considerations-for-enabling-ss_smartbackup-for-databases-and-instances"></a><a name="Considerations"></a><span data-ttu-id="3a335-124">Considerazioni sull'abilitazione [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] di per database e istanze</span><span class="sxs-lookup"><span data-stu-id="3a335-124">Considerations for enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for Databases and Instances</span></span>  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="3a335-125">può essere abilitato separatamente per singoli database o per l'intera istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-125">can be enabled for individual databases separately or for the entire instance.</span></span> <span data-ttu-id="3a335-126">Le scelte dipendono dai requisiti di recuperabilità per i database nell'istanza, dai requisiti per la gestione di più database e istanze e dall'uso strategico dell'archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3a335-126">The choices depend on the recoverability requirements for the databases on the instance, requirements for managing multiple databases and instances, and using Azure storage strategically.</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-database-level"></a><span data-ttu-id="3a335-127">Abilitazione di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] a livello di database</span><span class="sxs-lookup"><span data-stu-id="3a335-127">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Database Level</span></span>  
 <span data-ttu-id="3a335-128">Se un database presenta requisiti specifici per il backup e il periodo di memorizzazione (SLA di recuperabilità) diversi da altri database nell'istanza, configurare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] a livello di database per il database in questione.</span><span class="sxs-lookup"><span data-stu-id="3a335-128">If a database has specific requirements for backup and retention period (recoverability SLA) that is different from other databases on the instance, configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level for this database.</span></span> <span data-ttu-id="3a335-129">Le impostazioni a livello di database hanno la priorità sulle impostazioni di configurazione a livello di istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-129">Database level settings override instance level configuration settings.</span></span> <span data-ttu-id="3a335-130">Tuttavia entrambe queste opzioni possono essere utilizzate insieme nella stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-130">However both these options can be used together on the same instance.</span></span> <span data-ttu-id="3a335-131">Di seguito è riportato un elenco dei vantaggi e delle considerazioni in caso di abilitazione di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] a livello di database.</span><span class="sxs-lookup"><span data-stu-id="3a335-131">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
-   <span data-ttu-id="3a335-132">Più dettagliato: impostazioni di configurazione diverse per ogni database.</span><span class="sxs-lookup"><span data-stu-id="3a335-132">More granular: Separate configuration settings for each database.</span></span> <span data-ttu-id="3a335-133">Può supportare periodi di memorizzazione diversi per i singoli database.</span><span class="sxs-lookup"><span data-stu-id="3a335-133">Can support different retention periods for individual databases.</span></span>  
  
-   <span data-ttu-id="3a335-134">Vengono ignorate le impostazioni a livello di istanza per il database.</span><span class="sxs-lookup"><span data-stu-id="3a335-134">Overrides instance level settings for the database.</span></span>  
  
-   <span data-ttu-id="3a335-135">Può essere utilizzato per ridurre i costi di archiviazione selezionando i singoli database di cui eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="3a335-135">Can be used to reduce storage costs by selecting individual databases to be backed up.</span></span>  
  
-   <span data-ttu-id="3a335-136">Richiede la gestione di ogni database.</span><span class="sxs-lookup"><span data-stu-id="3a335-136">Requires managing each database</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-instance-level-with-default-settings"></a><span data-ttu-id="3a335-137">Abilitazione di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] a livello di istanza con le impostazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="3a335-137">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level with Default Settings</span></span>  
 <span data-ttu-id="3a335-138">Utilizzare questa impostazione se la maggior parte dei database nell'istanza presenta gli stessi requisiti per il backup e i criteri di conservazione o se si desidera l'esecuzione automatica del backup delle nuove istanze di database durante la creazione.</span><span class="sxs-lookup"><span data-stu-id="3a335-138">Use this setting if most of the databases in the instance have the same requirements for backup and retention policies, or if you want new database instances to automatically be backed up on creation.</span></span> <span data-ttu-id="3a335-139">Alcuni database che fanno eccezione ai criteri possono comunque essere configurati singolarmente.</span><span class="sxs-lookup"><span data-stu-id="3a335-139">A few databases that are exception to the policy can still be configured individually.</span></span> <span data-ttu-id="3a335-140">Di seguito è riportato un elenco dei vantaggi e delle considerazioni in caso di abilitazione di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] a livello di istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-140">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the instance level.</span></span>  
  
-   <span data-ttu-id="3a335-141">Automazione a livello di istanza: impostazioni comuni applicate automaticamente ai nuovi database aggiunti in seguito.</span><span class="sxs-lookup"><span data-stu-id="3a335-141">Automation at the instance level: Common settings applied to automatically for new databases added thereafter.</span></span>  
  
-   <span data-ttu-id="3a335-142">Il backup dei nuovi database verrà eseguito automaticamente subito dopo la creazione di questi ultimi nelle istanze.</span><span class="sxs-lookup"><span data-stu-id="3a335-142">New databases will be automatically backed up soon after they are created on the instances</span></span>  
  
-   <span data-ttu-id="3a335-143">Può essere applicato ai database che presentano gli stessi requisiti del periodo di memorizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a335-143">Can be applied to databases that have the same retention period requirements.</span></span>  
  
-   <span data-ttu-id="3a335-144">È comunque possibile configurare singoli database per cui è richiesto un periodo di memorizzazione diverso anche con il backup di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] abilitato a livello di istanza con le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="3a335-144">You can still configure individual databases that require a different retention period even with [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] backup enabled at in instance level with default settings.</span></span> <span data-ttu-id="3a335-145">È anche possibile disabilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per i database se non si intende usare l'archiviazione di Azure per i backup.</span><span class="sxs-lookup"><span data-stu-id="3a335-145">You can also disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for databases if you do not intend to use Azure storage for the backups.</span></span>  
  
##  <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><a name="DatabaseConfigure"></a><span data-ttu-id="3a335-146">Abilitare e configurare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per un database</span><span class="sxs-lookup"><span data-stu-id="3a335-146">Enable and Configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="3a335-147">La stored procedure di sistema `smart_admin.sp_set_db_backup` viene utilizzata per abilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per un database specifico.</span><span class="sxs-lookup"><span data-stu-id="3a335-147">The system stored procedure `smart_admin.sp_set_db_backup` is used to enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database.</span></span> <span data-ttu-id="3a335-148">Quando [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] viene abilitato per la prima volta nel database, è necessario specificare le informazioni seguenti oltre ad abilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3a335-148">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time on the database, the following information must be specified in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span></span>  
  
-   <span data-ttu-id="3a335-149">Nome del database.</span><span class="sxs-lookup"><span data-stu-id="3a335-149">The name of the database.</span></span>  
  
-   <span data-ttu-id="3a335-150">Periodo di memorizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a335-150">The retention period.</span></span>  
  
-   <span data-ttu-id="3a335-151">Credenziali SQL usate per l'autenticazione nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3a335-151">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="3a335-152">Specificare di non crittografare utilizzando \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** o specificare un algoritmo di crittografia supportato.</span><span class="sxs-lookup"><span data-stu-id="3a335-152">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="3a335-153">Per ulteriori informazioni sulla crittografia, vedere [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="3a335-153">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="3a335-154">per la configurazione a livello di database è supportato solo tramite Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3a335-154">for database level configuration is only supported through Transact-SQL.</span></span>  
  
 <span data-ttu-id="3a335-155">Una volta abilitato [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per un database, queste informazioni sono persistenti.</span><span class="sxs-lookup"><span data-stu-id="3a335-155">Once [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for a database this information is persisted.</span></span> <span data-ttu-id="3a335-156">Se si modifica la configurazione, saranno necessari solo il nome del database e l'impostazione da modificare. Se non specificati, in [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] verranno utilizzati i valori esistenti per gli altri parametri.</span><span class="sxs-lookup"><span data-stu-id="3a335-156">If you are changing the configuration, only the database name and the setting you want to change is required, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values for other parameters when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3a335-157">Prima di configurarlo in un database, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] potrebbe essere utile nella configurazione esistente, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="3a335-157">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on a database it might be useful to existing configuration if any.</span></span> <span data-ttu-id="3a335-158">Il passaggio per verificare le impostazioni di configurazione per un database è illustrato più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3a335-158">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
-   <span data-ttu-id="3a335-159">**Uso di Transact-SQL:**</span><span class="sxs-lookup"><span data-stu-id="3a335-159">**Using Transact-SQL:**</span></span>  
  
     <span data-ttu-id="3a335-160">Se si sta abilitando [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per la prima volta, i parametri obbligatori sono: \* \@ database_name*, \* \@ credential_name*, \* \@ encryption_algorithm\* \* \@ enable_backup\* il parametro \* \@ storage_url\* è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3a335-160">If you are enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the first time, the required parameters are: *\@database_name*, *\@credential_name*, *\@encryption_algorithm*,  *\@enable_backup* The *\@storage_url* parameter is optional.</span></span> <span data-ttu-id="3a335-161">Se non si specifica un valore per il @storage_url parametro, il valore viene derivato usando le informazioni sull'account di archiviazione delle credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="3a335-161">If you do not provide a value for  the @storage_url parameter, the value is derived using the storage account information from the SQL Credential.</span></span> <span data-ttu-id="3a335-162">Se si specifica l'URL di archiviazione, fornire solo l'URL per la radice dell'account di archiviazione, che deve corrispondere alle informazioni specificate nelle credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="3a335-162">If you provide the storage URL you should only provide the URL for the root of the storage account, and must match the information in the SQL Credential you specified.</span></span>  
  
    1.  <span data-ttu-id="3a335-163">Connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-163">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
    2.  <span data-ttu-id="3a335-164">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3a335-164">From the Standard bar, click **New Query**.</span></span>  
  
    3.  <span data-ttu-id="3a335-165">Copiare e incollare l'esempio seguente nella finestra query, quindi fare clic su `Execute` .</span><span class="sxs-lookup"><span data-stu-id="3a335-165">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="3a335-166">In questo esempio viene abilitato [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per il database ' testdb '.</span><span class="sxs-lookup"><span data-stu-id="3a335-166">This example enables [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the database 'TestDB'.</span></span> <span data-ttu-id="3a335-167">Il periodo di memorizzazione è impostato su 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="3a335-167">The retention period is set to 30 days.</span></span> <span data-ttu-id="3a335-168">In questo esempio vengono utilizzate l'opzione di crittografia tramite cui viene specificato l'algoritmo di crittografia e le informazioni sul componente di crittografia.</span><span class="sxs-lookup"><span data-stu-id="3a335-168">This sample uses the encryption option by specifying the encryption algorithm and the encryptor information.</span></span>  
  
    ```sql
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@enable_backup=1  
                    ,@retention_days =30   
                    ,@credential_name ='MyCredential'  
                    ,@encryption_algorithm ='AES_256'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
    GO
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3a335-169">Il periodo di memorizzazione può essere impostato su un valore compreso tra 1 e 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="3a335-169">The retention period can be set to any value from 1 to 30 days.</span></span>  
    >   
    >  <span data-ttu-id="3a335-170">Per ulteriori informazioni sulla creazione di un certificato per la crittografia, vedere il passaggio Creare un certificato di backup in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="3a335-170">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
     <span data-ttu-id="3a335-171">Per ulteriori informazioni su questa stored procedure, vedere [smart_admin. set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="3a335-171">For more information on this stored procedure, see [smart_admin.set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span></span>  
  
     <span data-ttu-id="3a335-172">Per verificare le impostazioni di configurazione per un database, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="3a335-172">To review the configuration settings for a database use the following query:</span></span>  
  
    ```sql
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('TestDB')  
    ```  
  
##  <a name="enable-and-configure-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceConfigure"></a><span data-ttu-id="3a335-173">Abilitare e configurare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] le impostazioni predefinite per l'istanza</span><span class="sxs-lookup"><span data-stu-id="3a335-173">Enable and Configure Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="3a335-174">È possibile abilitare e configurare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] le impostazioni predefinite a livello di istanza in due modi: usando il stored procedure di sistema `smart_admin.set_instance_backup` o **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="3a335-174">You can enable and configure default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings at the instance level in two ways:  By using the system stored procedure `smart_admin.set_instance_backup` or **SQL Server Management Studio**.</span></span> <span data-ttu-id="3a335-175">I due metodi sono illustrati di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a335-175">The two methods are explained below:</span></span>  
  
 <span data-ttu-id="3a335-176">**smart_admin. set_instance_backup:**.</span><span class="sxs-lookup"><span data-stu-id="3a335-176">**smart_admin.set_instance_backup:**.</span></span> <span data-ttu-id="3a335-177">Specificando il valore **1** per il parametro \* \@ enable_backup\* , è possibile abilitare il backup e impostare le configurazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="3a335-177">By specifying the value **1** for *\@enable_backup* parameter, you can enable backup and set the default configurations.</span></span> <span data-ttu-id="3a335-178">Una volta applicate a livello di istanza, queste impostazioni predefinite sono valide per qualsiasi nuovo database aggiunto a questa istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-178">Once applied at the instance level, these default settings are applied to any new database that is added to this instance.</span></span>  <span data-ttu-id="3a335-179">Quando [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] viene abilitato per la prima volta, è necessario specificare le informazioni seguenti oltre ad abilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] nell'istanza:</span><span class="sxs-lookup"><span data-stu-id="3a335-179">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time, the following information must be provided in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on the instance:</span></span>  
  
-   <span data-ttu-id="3a335-180">Periodo di memorizzazione.</span><span class="sxs-lookup"><span data-stu-id="3a335-180">The retention period.</span></span>  
  
-   <span data-ttu-id="3a335-181">Credenziali SQL usate per l'autenticazione nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3a335-181">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="3a335-182">Opzione di crittografia.</span><span class="sxs-lookup"><span data-stu-id="3a335-182">The encryption option.</span></span> <span data-ttu-id="3a335-183">Specificare di non crittografare utilizzando \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** o specificare un algoritmo di crittografia supportato.</span><span class="sxs-lookup"><span data-stu-id="3a335-183">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="3a335-184">Per ulteriori informazioni sulla crittografia, vedere [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="3a335-184">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 <span data-ttu-id="3a335-185">Una volta abilitate, queste impostazioni sono persistenti.</span><span class="sxs-lookup"><span data-stu-id="3a335-185">Once enabled these settings are persisted.</span></span> <span data-ttu-id="3a335-186">Se si modifica la configurazione, saranno necessari solo il nome del database e l'impostazione da modificare.</span><span class="sxs-lookup"><span data-stu-id="3a335-186">If you are changing the configuration, only the database name and the setting you want to change is required.</span></span> <span data-ttu-id="3a335-187">Se non specificati, in [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] verranno utilizzati i valori esistenti.</span><span class="sxs-lookup"><span data-stu-id="3a335-187">[!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3a335-188">Prima di configurarlo in un'istanza, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] potrebbe essere utile per verificare la configurazione esistente, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="3a335-188">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on an instance, it might be useful to check for existing configuration, if any.</span></span> <span data-ttu-id="3a335-189">Il passaggio per verificare le impostazioni di configurazione per un database è illustrato più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3a335-189">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
 <span data-ttu-id="3a335-190">**SQL Server Management Studio:** per eseguire questa attività in SQL Server Management Studio, aprire Esplora oggetti, espandere il nodo **Gestione** , fare clic con il pulsante destro del mouse su **Backup gestito**.</span><span class="sxs-lookup"><span data-stu-id="3a335-190">**SQL Server Management Studio:** To do this task in SQL Server Management Studio, go the object explorer, expand the **Management** node, and right click on **Managed Backup**.</span></span> <span data-ttu-id="3a335-191">Selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="3a335-191">Select **Configure**.</span></span> <span data-ttu-id="3a335-192">Viene aperta la finestra di dialogo **Backup gestito** .</span><span class="sxs-lookup"><span data-stu-id="3a335-192">This opens the **Managed Backup** dialog.</span></span> <span data-ttu-id="3a335-193">Utilizzare questa finestra di dialogo per specificare il periodo di memorizzazione, le credenziali SQL, l'URL di archiviazione e le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="3a335-193">Use this dialog to specify the retention period, SQL Credential, Storage URL, and the encryption settings.</span></span> <span data-ttu-id="3a335-194">Per informazioni specifiche su questa finestra di dialogo, vedere [configurare il backup gestito &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3a335-194">For specific help with this dialog, see [Configure Managed Backup &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span></span>  
  
#### <a name="using-transact-sql"></a><span data-ttu-id="3a335-195">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a335-195">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="3a335-196">Connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-196">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a335-197">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3a335-197">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a335-198">Copiare e incollare l'esempio seguente nella finestra query, quindi fare clic su `Execute` .</span><span class="sxs-lookup"><span data-stu-id="3a335-198">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
   EXEC smart_admin.sp_set_instance_backup  
                @retention_days=30   
                ,@credential_name='sqlbackuptoURL'  
                ,@encryption_algorithm ='AES_128'  
                ,@encryptor_type= 'Certificate'  
                ,@encryptor_name='MyBackupCert'  
                ,@enable_backup=1;  
GO  
  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3a335-199">Il periodo di memorizzazione può essere impostato su un valore compreso tra 1 e 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="3a335-199">The retention period can be set to any value from 1 to 30 days.</span></span>  
>   
>  <span data-ttu-id="3a335-200">Per ulteriori informazioni sulla creazione di un certificato per la crittografia, vedere il passaggio Creare un certificato di backup in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="3a335-200">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
 <span data-ttu-id="3a335-201">Per visualizzare le impostazioni di configurazione predefinite per l'istanza, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="3a335-201">To view the default configuration settings for the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_instance_config ();
```  
  
#### <a name="using-powershell"></a><span data-ttu-id="3a335-202">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a335-202">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="3a335-203">Avviare un'istanza di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a335-203">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="3a335-204">Eseguire lo script riportato di seguito dopo averlo modificato per rispettare le impostazioni</span><span class="sxs-lookup"><span data-stu-id="3a335-204">Run the following script after modifying it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    $encryptionOption = New-SqlBackupEncryptionOption -EncryptionAlgorithm Aes128 -EncryptorType ServerCertificate -EncryptorName "MyBackupCert"  
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -BackupEnabled $True -BackupRetentionPeriodInDays 10 -EncryptionOption $encryptionOption  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3a335-205">Quando si crea un nuovo database dopo la configurazione delle impostazioni predefinite, potrebbero essere necessari fino a 15 minuti per configurarlo con le impostazioni in questione.</span><span class="sxs-lookup"><span data-stu-id="3a335-205">When you create a new database after configuring the default settings, it may take up to 15 minutes for the database to be configured with the default settings.</span></span> <span data-ttu-id="3a335-206">Lo stesso vale anche per i database il cui modello di recupero viene modificato da **Simple** a **Full** o **Bulk-Logged**</span><span class="sxs-lookup"><span data-stu-id="3a335-206">This also applies to databases that are changed from **Simple** to **Full** or **Bulk-Logged** recovery model.</span></span>  
  
##  <a name="disable-ss_smartbackup-for-a-database"></a><a name="DatabaseDisable"></a> <span data-ttu-id="3a335-207">Disabilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per un database</span><span class="sxs-lookup"><span data-stu-id="3a335-207">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database</span></span>  
 <span data-ttu-id="3a335-208">È possibile disabilitare le impostazioni di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] utilizzando la stored procedure di sistema `sp_set_db_backup`.</span><span class="sxs-lookup"><span data-stu-id="3a335-208">You can disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings by using the `sp_set_db_backup` system stored procedure.</span></span> <span data-ttu-id="3a335-209">\* \@ Enableparameter\* viene utilizzato per abilitare e disabilitare le [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurazioni per un database specifico, dove 1 Abilita e 0 Disabilita le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3a335-209">The *\@enableparameter* is used to enable and disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurations for a specific database, where 1 enables and 0 disables the configuration settings.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-for-a-specific-database"></a><span data-ttu-id="3a335-210">Per disabilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per un database specifico:</span><span class="sxs-lookup"><span data-stu-id="3a335-210">To Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database:</span></span>  
  
1.  <span data-ttu-id="3a335-211">Connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-211">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a335-212">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3a335-212">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a335-213">Copiare e incollare l'esempio seguente nella finestra query, quindi fare clic su `Execute` .</span><span class="sxs-lookup"><span data-stu-id="3a335-213">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin.sp_set_db_backup   
                @database_name='TestDB'   
                ,@enable_backup=0;  
GO
```  
  
##  <a name="disable-ss_smartbackup-for-all-the-databases-on-the-instance"></a><a name="DatabaseAllDisable"></a> <span data-ttu-id="3a335-214">Disabilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per tutti i database dell'istanza</span><span class="sxs-lookup"><span data-stu-id="3a335-214">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for all the databases on the Instance</span></span>  
 <span data-ttu-id="3a335-215">La procedura seguente viene utilizzata quando si desidera disabilitare le impostazioni di configurazione di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] da tutti i database con [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] abilitato attualmente nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-215">The following procedure is for when you want to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configuration settings from all the databases that currently have [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled on the instance.</span></span>  <span data-ttu-id="3a335-216">Le impostazioni di configurazione come l'URL di archiviazione, la memorizzazione e le credenziali SQL rimarranno nei metadati e possono essere utilizzate se [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] viene abilitato per il database in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3a335-216">The configuration settings like the storage URL, retention, and the SQL Credential will remain in the metadata and can be used  if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the database at a later time.</span></span> <span data-ttu-id="3a335-217">Se si desidera sospendere solo temporaneamente i servizi [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , è possibile utilizzare il parametro master descritto nelle sezioni seguenti, più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3a335-217">If you want to just pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services temporarily, you can use the master switch explained in the following sections later in this topic.</span></span>  
  
#### <a name="to-disable-ss_smartbackupfor-all-the-databases"></a><span data-ttu-id="3a335-218">Per disabilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]per tutti i database:</span><span class="sxs-lookup"><span data-stu-id="3a335-218">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]for all the databases:</span></span>  
  
1.  <span data-ttu-id="3a335-219">Connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-219">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a335-220">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3a335-220">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a335-221">Copiare e incollare l'esempio seguente nella finestra query, quindi fare clic su `Execute` .</span><span class="sxs-lookup"><span data-stu-id="3a335-221">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="3a335-222">Nell'esempio seguente viene identificato se [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] è configurato a livello di istanza e in tutti i database abilitati da [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] nell'istanza e viene eseguita la stored procedure di sistema `sp_set_db_backup` per disabilitare [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-222">The following example identifies if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured at the instance level and all the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled databases on the instance, and executes the system stored procedure `sp_set_db_backup` to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span>  
  
```sql
-- Create a working table to store the database names  
Declare @DBNames TABLE  
  
       (  
             RowID int IDENTITY PRIMARY KEY  
             ,DBName varchar(500)  
  
       )  
-- Define the variables  
DECLARE @rowid int  
DECLARE @dbname varchar(500)  
DECLARE @SQL varchar(2000)  
-- Get the database names from the system function  
  
INSERT INTO @DBNames (DBName)  
  
SELECT db_name  
       FROM
  
       smart_admin.fn_backup_db_config (NULL)  
       WHERE is_smart_backup_enabled = 1  
  
       --Select DBName from @DBNames 
       select @rowid = min(RowID) FROM @DBNames  
  
       WHILE @rowID IS NOT NULL  
       Begin
             Set @dbname = (Select DBName From @DBNames Where RowID = @rowid)  
             Begin  
             Set @SQL = 'EXEC smart_admin.sp_set_db_backup    
                @database_name= '''+'' + @dbname+ ''+''',   
                @enable_backup=0'  
  
            EXECUTE (@SQL)  
  
             END  
             Select @rowid = min(RowID)  
             From @DBNames Where RowID > @rowid  
  
       END
```  
  
 <span data-ttu-id="3a335-223">Per verificare le impostazioni di configurazione per tutti i database nell'istanza, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="3a335-223">To review the configuration settings for all the databases on the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_db_config (NULL);  
GO
```  
  
##  <a name="disable-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceDisable"></a> <span data-ttu-id="3a335-224">Disabilitare le impostazioni predefinite di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per l'istanza</span><span class="sxs-lookup"><span data-stu-id="3a335-224">Disable Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="3a335-225">Le impostazioni predefinite a livello di istanza vengono applicate a tutti i nuovi database creati nell'istanza in questione.</span><span class="sxs-lookup"><span data-stu-id="3a335-225">Default settings at the instance level apply to all new databases created on that instance.</span></span>  <span data-ttu-id="3a335-226">Se le impostazioni predefinite non sono più necessarie o richieste, è possibile disabilitare questa configurazione usando la stored procedure di sistema **smart_admin.sp_set_instance_backup** .</span><span class="sxs-lookup"><span data-stu-id="3a335-226">If you no longer need or require default settings, you can disable this configuration by using the **smart_admin.sp_set_instance_backup** System stored procedure.</span></span> <span data-ttu-id="3a335-227">La disabilitazione non comporta la rimozione delle altre impostazioni di configurazione come l'URL di archiviazione, l'impostazione di memorizzazione o il nome delle credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="3a335-227">Disabling does not remove the other configuration settings like the storage URL, retention setting, or the SQL Credential name.</span></span> <span data-ttu-id="3a335-228">Queste impostazioni verranno utilizzate se [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] viene abilitato per l'istanza in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3a335-228">These settings will be used if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the instance at a later time.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-default-configuration-settings"></a><span data-ttu-id="3a335-229">Per disabilitare le impostazioni di configurazione predefinite di [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="3a335-229">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] default configuration settings:</span></span>  
  
1.  <span data-ttu-id="3a335-230">Connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-230">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a335-231">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3a335-231">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a335-232">Copiare e incollare l'esempio seguente nella finestra query, quindi fare clic su `Execute` .</span><span class="sxs-lookup"><span data-stu-id="3a335-232">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
    ```sql
    Use msdb;  
    Go  
    EXEC smart_admin.sp_set_instance_backup  
                    @enable_backup=0;  
    GO
    ```  
  
#### <a name="using-powershell"></a><span data-ttu-id="3a335-233">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a335-233">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="3a335-234">Avviare un'istanza di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a335-234">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="3a335-235">Eseguire lo script riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a335-235">Run the following script:</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Set-SqlSmartAdmin -BackupEnabled $False  
    ```  
  
##  <a name="pause-ss_smartbackup-at-the-instance-level"></a><a name="InstancePause"></a> <span data-ttu-id="3a335-236">Sospendere [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] a livello di istanza</span><span class="sxs-lookup"><span data-stu-id="3a335-236">Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level</span></span>  
 <span data-ttu-id="3a335-237">In alcuni casi è possibile che sia necessario sospendere temporaneamente i servizi [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] per un breve periodo.</span><span class="sxs-lookup"><span data-stu-id="3a335-237">There might be times when you need to temporarily pause the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for a short period time.</span></span>  <span data-ttu-id="3a335-238">La stored procedure di sistema `smart_admin.sp_backup_master_switch` consente di disabilitare il servizio [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] a livello di istanza.</span><span class="sxs-lookup"><span data-stu-id="3a335-238">The `smart_admin.sp_backup_master_switch` system stored procedure allows you to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] service at the instance level.</span></span>  <span data-ttu-id="3a335-239">La stessa stored procedure viene utilizzata per riprendere [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-239">The same stored procedure is used to resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="3a335-240">Il parametro @state viene usato per definire se [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] deve essere disabilitato o abilitato.</span><span class="sxs-lookup"><span data-stu-id="3a335-240">The @state parameter is used to define whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] should be turned off or on.</span></span>  
  
#### <a name="to-pause-ss_smartbackup-services-using-transact-sql"></a><span data-ttu-id="3a335-241">Per sospendere i servizi [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] tramite Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="3a335-241">To Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Services Using Transact-SQL:</span></span>  
  
1.  <span data-ttu-id="3a335-242">Connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-242">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a335-243">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3a335-243">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a335-244">Copiare e incollare l'esempio seguente nella finestra query, quindi fare clic su`Execute`</span><span class="sxs-lookup"><span data-stu-id="3a335-244">Copy and paste the following example into the query window and then click `Execute`</span></span>  
  
```sql
Use msdb;  
GO  
EXEC smart_admin.sp_backup_master_switch @new_state=0;  
Go  
  
```  
  
#### <a name="to-pause-ss_smartbackup-using-powershell"></a><span data-ttu-id="3a335-245">Per sospendere [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a335-245">To pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="3a335-246">Avviare un'istanza di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a335-246">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="3a335-247">Eseguire lo script riportato di seguito dopo averlo modificato per rispettare le impostazioni</span><span class="sxs-lookup"><span data-stu-id="3a335-247">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $False  
    ```  
  
#### <a name="to-resume-ss_smartbackup-using-transact-sql"></a><span data-ttu-id="3a335-248">Per riprendere [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a335-248">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="3a335-249">Connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a335-249">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a335-250">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3a335-250">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3a335-251">Copiare e incollare l'esempio seguente nella finestra query, quindi fare clic su `Execute` .</span><span class="sxs-lookup"><span data-stu-id="3a335-251">Copy and paste the following example into the query window and then click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin. sp_backup_master_switch @new_state=1;  
GO
```  
  
#### <a name="to-resume-ss_smartbackup-using-powershell"></a><span data-ttu-id="3a335-252">Per riprendere [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a335-252">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="3a335-253">Avviare un'istanza di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a335-253">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="3a335-254">Eseguire lo script riportato di seguito dopo averlo modificato per rispettare le impostazioni</span><span class="sxs-lookup"><span data-stu-id="3a335-254">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $True  
    ```  
