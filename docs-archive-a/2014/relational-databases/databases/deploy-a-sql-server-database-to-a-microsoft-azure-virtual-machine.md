---
title: Distribuire un database di SQL Server a una macchina virtuale di Microsoft Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.deploymentwizard.deploymentsettings.f1
- sql12.swb.deploymentwizard.progress.f1
- sql11.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.f1
- sql12.swb.deploymentwizard.azuresignin.f1
- sql11.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.azuresignin.f1
- sql12.swb.deploymentwizard.f1
- sql12.swb.sqlvmdialog.f1
- sql11.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.results.f1
- sql11.swb.deploymentwizard.progress.f1
- sql12.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.sourcesettings.f1
- sql12.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.sourcesettings.f1
- sql11.swb.deploymentwizard.results.f1
- sql12.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.deploymentsettings.f1
helpviewer_keywords:
- Deploy a database
- Deploy to Azure VM
- Migrate to Azure
- Azure virtual machine
- Migrate to Azure VM
- Migrate to the cloud
- SQL Server Management Studio
- SSMS
- Deploy database wizard
- Deploy a SQL Server database to Azure
- Azure VM
ms.assetid: 5e82e66a-262e-4d4f-aa89-39cb62696d06
author: stevestein
ms.author: sstein
ms.openlocfilehash: d48c06db038a775811cba6705fbaf1d97a960f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721487"
---
# <a name="deploy-a-sql-server-database-to-a-microsoft-azure-virtual-machine"></a><span data-ttu-id="5881f-102">Distribuire un database di SQL Server a una macchina virtuale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="5881f-102">Deploy a SQL Server Database to a Microsoft Azure Virtual Machine</span></span>
  <span data-ttu-id="5881f-103">Usare la procedura guidata **Distribuisci un database di SQL Server in una** macchina virtuale di Azure per distribuire un database da un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in una macchina virtuale (VM) di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-103">Use the **Deploy a SQL Server Database to an Azure VM** wizard to deploy a database from an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in an Azure Virtual Machine (VM).</span></span> <span data-ttu-id="5881f-104">La procedura guidata usa un'operazione di backup completo del database, pertanto copia sempre lo schema completo del database e i dati da un database utente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5881f-104">The wizard utilizes a full database backup operation, so it always copies the complete database schema and the data from a SQL Server user database.</span></span> <span data-ttu-id="5881f-105">La procedura guidata esegue inoltre tutta la configurazione della macchina virtuale di Azure automaticamente, pertanto non sono necessarie operazioni preliminari per la configurazione della VM.</span><span class="sxs-lookup"><span data-stu-id="5881f-105">The wizard also does all of the Azure VM configuration for you, so no pre-configuration of the VM is required.</span></span>  
  
 <span data-ttu-id="5881f-106">Non è possibile usare la procedura guidata per i backup differenziali perché non sovrascrive un database esistente avente lo stesso nome di database.</span><span class="sxs-lookup"><span data-stu-id="5881f-106">You cannot use the wizard for differential backups because the wizard will not overwrite an existing database that has the same database name.</span></span> <span data-ttu-id="5881f-107">Per sostituire un database esistente sulla VM, è innanzitutto necessario eliminare il database esistente o modificare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="5881f-107">To replace an existing database on the VM, you must first drop the existing database or change the database name.</span></span> <span data-ttu-id="5881f-108">Se si verifica un conflitto di denominazione tra il nome del database per un'operazione di distribuzione in transito e un database esistente sulla VM, la procedura guidata suggerirà un nome di database aggiunto per il database in transito per consentire il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5881f-108">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
##  <a name="before-you-begin"></a><a name="before_you_begin"></a> <span data-ttu-id="5881f-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5881f-109">Before You Begin</span></span>  
 <span data-ttu-id="5881f-110">Per completare questa procedura guidata, è necessario essere in grado di fornire le informazioni indicate di seguito e avere configurato le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="5881f-110">To complete this wizard, you must be able to provide the following information and have these configuration settings in place:</span></span>  
  
-   <span data-ttu-id="5881f-111">I dettagli di account Microsoft associati alla sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-111">The Microsoft account details associated with your Azure subscription.</span></span>  
  
-   <span data-ttu-id="5881f-112">Profilo di pubblicazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-112">Your Azure publishing profile.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="5881f-113">SQL Server supporta attualmente la versione del profilo di pubblicazione 2.0.</span><span class="sxs-lookup"><span data-stu-id="5881f-113">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="5881f-114">Per scaricare la versione supportata del profilo di pubblicazione, vedere [Download del profilo di pubblicazione 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="5881f-114">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
-   <span data-ttu-id="5881f-115">Il certificato di gestione caricato nella sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-115">The management certificate uploaded to your Azure subscription.</span></span>  
  
-   <span data-ttu-id="5881f-116">Il certificato di gestione salvato nell'archivio certificati personale sul computer in cui viene eseguita la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5881f-116">The management certificate saved into the personal certificate store on the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="5881f-117">È necessario disporre di un percorso di archiviazione temporaneo nel computer in cui è ospitato il database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5881f-117">You must have a temporary storage location that is available to the computer where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is hosted.</span></span> <span data-ttu-id="5881f-118">Il percorso di archiviazione temporaneo deve essere disponibile nel computer in cui viene eseguita la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5881f-118">The temporary storage location must also be available to the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="5881f-119">Se si distribuisce il database a un macchina virtuale esistente, l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve essere configurata per rimanere in attesa su una porta TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="5881f-119">If you are deploying the database to an existing VM, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured to listen on a TCP/IP port.</span></span>  
  
-   <span data-ttu-id="5881f-120">Una macchina virtuale o un'immagine della raccolta di Azure che si intende usare per la creazione della macchina virtuale deve avere la SQL Server adattatore del cloud configurata e in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5881f-120">Either an Azure VM or Gallery image you plan to use for creation of the VM must have the SQL Server Cloud Adapter configured and running.</span></span>  
  
-   <span data-ttu-id="5881f-121">È necessario configurare un endpoint aperto per il SQL Server adattatore del cloud sul gateway di Azure con la porta privata 11435.</span><span class="sxs-lookup"><span data-stu-id="5881f-121">You must configure an open endpoint for your SQL Server Cloud Adapter on the Azure gateway with private port 11435.</span></span>  
  
 <span data-ttu-id="5881f-122">Inoltre, se si prevede di distribuire il database in una macchina virtuale di Azure esistente, è necessario essere in grado di fornire:</span><span class="sxs-lookup"><span data-stu-id="5881f-122">In addition, if you plan to deploy your database into an existing Azure VM, you must also be able to provide:</span></span>  
  
-   <span data-ttu-id="5881f-123">Nome DNS del servizio cloud che ospita la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="5881f-123">The DNS name of the cloud service that hosts your VM.</span></span>  
  
-   <span data-ttu-id="5881f-124">Credenziali dell'amministratore per la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="5881f-124">Administrator credentials for the VM.</span></span>  
  
-   <span data-ttu-id="5881f-125">Credenziali con privilegi dell'operatore di backup nel database che si desidera distribuire, dall'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]di origine.</span><span class="sxs-lookup"><span data-stu-id="5881f-125">Credentials with Backup operator privileges on the database you plan to deploy, from the source instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5881f-126">Per altre informazioni sull'esecuzione di SQL Server in macchine virtuali di Azure, vedere [preparazione della migrazione a SQL Server in macchine virtuali di Azure](https://msdn.microsoft.com/library/dn133142.aspx).</span><span class="sxs-lookup"><span data-stu-id="5881f-126">For more information about running SQL Server in Azure virtual machines, see [Getting Ready to Migrate to SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133142.aspx).</span></span>  
  
 <span data-ttu-id="5881f-127">Nei computer che eseguono sistemi operativi Windows Server, è necessario usare le seguenti impostazioni di configurazione per eseguire questa procedura guidata:</span><span class="sxs-lookup"><span data-stu-id="5881f-127">On computers running Windows Server operating systems, you must use the following configuration settings to run this wizard:</span></span>  
  
-   <span data-ttu-id="5881f-128">Disabilitare la configurazione della sicurezza avanzata: usare Server Manager > Server locale per impostare la configurazione della sicurezza avanzata di Internet Explorer (ESC) su **DISATTIVATO**.</span><span class="sxs-lookup"><span data-stu-id="5881f-128">Turn off Enhanced Security Configuration:  Use Server Manager > Local Server to set Internet Explorer Enhanced Security Configuration (ESC) to **OFF**.</span></span>  
  
-   <span data-ttu-id="5881f-129">Abilitare JavaScript: Internet Explorer > Opzioni Internet > Sicurezza > Livello personalizzato > Esecuzione script > Esecuzione script attivo: **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="5881f-129">Enable JavaScript:  Internet Explorer > Internet Options > Security > Customer Level > Scripting > Active Scripting: **Enable**.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="limitations"></a> <span data-ttu-id="5881f-130">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5881f-130">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5881f-131">Il limite per le dimensioni del database per questa operazione è di 1 TB.</span><span class="sxs-lookup"><span data-stu-id="5881f-131">The database size limitation for this operation is 1 TB.</span></span>  
  
 <span data-ttu-id="5881f-132">Questa funzionalità di distribuzione è disponibile in SQL Server Management Studio per [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5881f-132">This deployment feature is available in SQL Server Management Studio for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="5881f-133">Questa funzionalità di distribuzione è destinata solo ai database utente. La distribuzione dei database di sistema non è supportata.</span><span class="sxs-lookup"><span data-stu-id="5881f-133">This deployment feature is for use only with user databases; deploying system databases is not supported.</span></span>  
  
 <span data-ttu-id="5881f-134">La funzionalità di distribuzione non supporta i servizi ospitati associati a un gruppo di affinità.</span><span class="sxs-lookup"><span data-stu-id="5881f-134">The deployment feature does not support hosted services that are associated with an Affinity Group.</span></span> <span data-ttu-id="5881f-135">Ad esempio, gli account di archiviazione associati a un gruppo di affinità non possono essere selezionati per l'uso nella pagina **Impostazioni di distribuzione** di questa procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5881f-135">For example, storage accounts associated with an Affinity Group cannot be selected for use on the **Deployment Settings** page of this wizard.</span></span>  
  
 <span data-ttu-id="5881f-136">La versione di SQL Server nella macchina virtuale deve essere uguale o successiva alla versione di SQL Server di origine.</span><span class="sxs-lookup"><span data-stu-id="5881f-136">The SQL Server version in the VM must be the same or later than the source SQL Server version.</span></span> <span data-ttu-id="5881f-137">SQL Server versioni del database che possono essere distribuite in una macchina virtuale di Azure tramite questa procedura guidata:</span><span class="sxs-lookup"><span data-stu-id="5881f-137">SQL Server database versions that can be deployed to an Azure VM using this wizard:</span></span>  
  
-   <span data-ttu-id="5881f-138">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="5881f-138">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="5881f-139">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5881f-139">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="5881f-140">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="5881f-140">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="5881f-141">SQL Server le versioni di database in esecuzione in un database di macchine virtuali di Azure possono essere distribuite in:</span><span class="sxs-lookup"><span data-stu-id="5881f-141">SQL Server database versions running in an Azure VM database can be deployed to:</span></span>  
  
-   <span data-ttu-id="5881f-142">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="5881f-142">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="5881f-143">Se si verifica un conflitto di denominazione tra il nome del database per un'operazione di distribuzione in transito e un database esistente sulla VM, la procedura guidata suggerirà un nome di database aggiunto per il database in transito per consentire il completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="5881f-143">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
###  <a name="considerations-for-deploying-a-filestream-enabled-database-to-an-azure-vm"></a><a name="filestream"></a> <span data-ttu-id="5881f-144">Considerazioni per la distribuzione di un database abilitato per FILESTREAM in una macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="5881f-144">Considerations for Deploying a FILESTREAM-enabled Database to an Azure VM</span></span>  
 <span data-ttu-id="5881f-145">Tenere presenti le linee guida e le limitazioni seguenti per la distribuzione di database con BLOB archiviati in oggetti FILESTREAM:</span><span class="sxs-lookup"><span data-stu-id="5881f-145">Note the following guidelines and restrictions when deploying databases that have BLOBS stored in FILESTREAM objects:</span></span>  
  
-   <span data-ttu-id="5881f-146">La funzionalità di distribuzione non permette di distribuire un database abilitato per FILESTREAM in una nuova macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="5881f-146">The deployment feature cannot deploy a FILESTREAM-enabled database into a new VM.</span></span> <span data-ttu-id="5881f-147">Se FILESTREAM non è abilitato nella macchina virtuale prima di eseguire la procedura guidata, l'operazione di ripristino del database avrà esito negativo e l'operazione della procedura guidata non sarà completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5881f-147">If FILESTREAM is not enabled in the VM before you run the wizard, the database restore operation will fail and the wizard operation will not be able to complete successfully.</span></span> <span data-ttu-id="5881f-148">Per distribuire correttamente un database che usa FILESTREAM, abilitare FILESTREAM nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nella macchina virtuale host prima di avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5881f-148">To successfully deploy a database that uses FILESTREAM, enable FILESTREAM in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the host VM before launching the wizard.</span></span> <span data-ttu-id="5881f-149">Per altre informazioni, vedere [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span><span class="sxs-lookup"><span data-stu-id="5881f-149">For more information, see [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span></span>  
  
-   <span data-ttu-id="5881f-150">Se il database usa OLTP in memoria, è possibile distribuirlo in una macchina virtuale di Azure senza apportare alcuna modifica al database.</span><span class="sxs-lookup"><span data-stu-id="5881f-150">If your database utilizes In-Memory OLTP, you can deploy the database to an Azure VM without any modifications to the database.</span></span> <span data-ttu-id="5881f-151">Per altre informazioni, vedere [OLTP in memoria (ottimizzazione per la memoria)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="5881f-151">For more information, see [In-Memory OLTP (In-Memory Optimization)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span></span>  
  
###  <a name="considerations-for-geographic-distribution-of-assets"></a><a name="geography"></a><span data-ttu-id="5881f-152">Considerazioni sulla distribuzione geografica delle risorse</span><span class="sxs-lookup"><span data-stu-id="5881f-152">Considerations for Geographic Distribution of Assets</span></span>  
 <span data-ttu-id="5881f-153">Si noti che le risorse seguenti devono essere collocate nella stessa area geografica:</span><span class="sxs-lookup"><span data-stu-id="5881f-153">Note that the following assets must be located in the same geographic region:</span></span>  
  
-   <span data-ttu-id="5881f-154">Servizio cloud</span><span class="sxs-lookup"><span data-stu-id="5881f-154">Cloud Service</span></span>  
  
-   <span data-ttu-id="5881f-155">Ubicazione della macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="5881f-155">VM Location</span></span>  
  
-   <span data-ttu-id="5881f-156">Servizio di archiviazione su disco di dati</span><span class="sxs-lookup"><span data-stu-id="5881f-156">Data Disk Storage Service</span></span>  
  
 <span data-ttu-id="5881f-157">Se le risorse elencate sopra non si trovano nella stessa area geografica, non sarà possibile completare correttamente la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5881f-157">If the assets listed above are not co-located, the wizard will not be able to complete successfully.</span></span>  
  
###  <a name="wizard-configuration-settings"></a><a name="configuration_settings"></a> <span data-ttu-id="5881f-158">Impostazioni di configurazione della procedura guidata</span><span class="sxs-lookup"><span data-stu-id="5881f-158">Wizard Configuration Settings</span></span>  
 <span data-ttu-id="5881f-159">Usare i dettagli di configurazione seguenti per modificare le impostazioni per una distribuzione del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in una macchina virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-159">Use the following configuration details to modify settings for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database deployment to an Azure VM.</span></span>  
  
-   <span data-ttu-id="5881f-160">**Percorso predefinito per il file di configurazione** - %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span><span class="sxs-lookup"><span data-stu-id="5881f-160">**Default path for the configuration file** - %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span></span>  
  
-   <span data-ttu-id="5881f-161">**Struttura dei file di configurazione**</span><span class="sxs-lookup"><span data-stu-id="5881f-161">**Configuration file structure**</span></span>  
  
    -   \<DeploymentSettings>  
  
        -   <span data-ttu-id="5881f-162"><OtherSettings</span><span class="sxs-lookup"><span data-stu-id="5881f-162"><OtherSettings</span></span>  
  
            -   <span data-ttu-id="5881f-163">TraceLevel = "debug"\<!-- Logging level --></span><span class="sxs-lookup"><span data-stu-id="5881f-163">TraceLevel="Debug" \<!-- Logging level --></span></span>  
  
            -   <span data-ttu-id="5881f-164">BackupPath = " \\ \\ [nome server] \\ [volume] \\ "\<!-- The last used path for backup. Used as default in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="5881f-164">BackupPath="\\\\[server name]\\[volume]\\" \<!-- The last used path for backup. Used as default in the wizard. --></span></span>  
  
            -   <span data-ttu-id="5881f-165">CleanupDisabled = false/>\<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span><span class="sxs-lookup"><span data-stu-id="5881f-165">CleanupDisabled = False /> \<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span></span>  
  
        -   <span data-ttu-id="5881f-166"><PublishProfile\<!-- The last used publish profile information. --></span><span class="sxs-lookup"><span data-stu-id="5881f-166"><PublishProfile \<!-- The last used publish profile information. --></span></span>  
  
            -   <span data-ttu-id="5881f-167">Certificate = "12A34B567890123ABCD4EF567A8"\<!-- The certificate for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="5881f-167">Certificate="12A34B567890123ABCD4EF567A8" \<!-- The certificate for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="5881f-168">Subscription = "1a2b34c5-67d8-90EF-AB12-xxxxxxxxxxxxx"\<!-- The subscription for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="5881f-168">Subscription="1a2b34c5-67d8-90ef-ab12-xxxxxxxxxxxxx" \<!-- The subscription for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="5881f-169">Nome = "sottoscrizione personale"\<!-- The name of the subscription. --></span><span class="sxs-lookup"><span data-stu-id="5881f-169">Name="My Subscription" \<!-- The name of the subscription. --></span></span>  
  
            -   <span data-ttu-id="5881f-170">Publisher="" /></span><span class="sxs-lookup"><span data-stu-id="5881f-170">Publisher="" /></span></span>  
  
    -   \</DeploymentSettings>  
  
 <span data-ttu-id="5881f-171">**Valori del file di configurazione**</span><span class="sxs-lookup"><span data-stu-id="5881f-171">**Configuration file values**</span></span>  
  
###  <a name="permissions"></a><a name="permissions"></a> <span data-ttu-id="5881f-172">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5881f-172">Permissions</span></span>  
 <span data-ttu-id="5881f-173">Il database distribuito deve essere in uno stato normale e accessibile per l'account utente che esegue la procedura guidata. L'account utente deve disporre delle autorizzazioni per eseguire un'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="5881f-173">The database being deployed must be in a normal state, the database must be accessible to the user account running the wizard, and the user account must have permissions to perform a backup operation.</span></span>  
  
##  <a name="using-the-deploy-database-to-azure-vm-wizard"></a><a name="launch_wizard"></a><span data-ttu-id="5881f-174">Uso della procedura guidata Distribuisci database in una macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="5881f-174">Using the Deploy Database to Azure VM Wizard</span></span>  
 <span data-ttu-id="5881f-175">**Per avviare la procedura guidata, effettuare i passaggi seguenti:**</span><span class="sxs-lookup"><span data-stu-id="5881f-175">**To launch the wizard, use the following steps:**</span></span>  
  
1.  <span data-ttu-id="5881f-176">Usare SQL Server Management Studio per connettere l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al database che si desidera distribuire.</span><span class="sxs-lookup"><span data-stu-id="5881f-176">Use SQL Server Management Studio to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the database you want to deploy.</span></span>  
  
2.  <span data-ttu-id="5881f-177">In **Esplora oggetti**espandere il nome dell'istanza, quindi il nodo **Database** .</span><span class="sxs-lookup"><span data-stu-id="5881f-177">In **Object Explorer**, expand the instance name, then expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="5881f-178">Fare clic con il pulsante destro del mouse sul database che si desidera distribuire, selezionare **attività**, quindi scegliere **Distribuisci database in macchina virtuale di Azure.**</span><span class="sxs-lookup"><span data-stu-id="5881f-178">Right-click the database you want to deploy, select **Tasks**, and then select **Deploy Database to Azure VM...**</span></span>  
  

  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="5881f-179">Pagina Introduzione</span><span class="sxs-lookup"><span data-stu-id="5881f-179">Introduction Page</span></span>  
 <span data-ttu-id="5881f-180">Questa pagina descrive la procedura guidata **Distribuisci un database di SQL Server in una macchina virtuale di Azure** .</span><span class="sxs-lookup"><span data-stu-id="5881f-180">This page describes the **Deploy a SQL Server Database to an Azure VM** wizard.</span></span>  
  
 <span data-ttu-id="5881f-181">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="5881f-181">**Options**</span></span>  
  
-   <span data-ttu-id="5881f-182">**Non visualizzare più questa pagina**</span><span class="sxs-lookup"><span data-stu-id="5881f-182">**Do not show this page again.**</span></span> <span data-ttu-id="5881f-183">- Selezionare questa casella di controllo per evitare che la pagina Introduzione venga visualizzata nuovamente in futuro.</span><span class="sxs-lookup"><span data-stu-id="5881f-183">- Click this check box to stop the Introduction page from being displayed in the future.</span></span>  
  
-   <span data-ttu-id="5881f-184">**Avanti** : passa alla pagina **Impostazioni di origine** .</span><span class="sxs-lookup"><span data-stu-id="5881f-184">**Next** - Proceeds to the **Source Settings** page.</span></span>  
  
-   <span data-ttu-id="5881f-185">**Annulla** : Annulla l'operazione e chiude la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5881f-185">**Cancel** - Cancels the operation and closes the wizard.</span></span>  
  
-   <span data-ttu-id="5881f-186">**Guida** : avvia l'argomento della Guida di MSDN per la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5881f-186">**Help** - Launches the MSDN Help topic for the wizard.</span></span>  
  
##  <a name="source-settings"></a><a name="Source_settings"></a><span data-ttu-id="5881f-187">Impostazioni di origine</span><span class="sxs-lookup"><span data-stu-id="5881f-187">Source Settings</span></span>  
 <span data-ttu-id="5881f-188">Usare questa pagina per connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ospita il database da distribuire nella macchina virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-188">Use this page to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database you want to deploy to the Azure VM.</span></span> <span data-ttu-id="5881f-189">Verrà inoltre specificato un percorso temporaneo per i file da salvare dal computer locale prima che vengano trasferiti in Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-189">You will also specify a temporary location for files to be saved from the local machine before they are transferred to Azure.</span></span> <span data-ttu-id="5881f-190">Può essere un percorso di rete condiviso.</span><span class="sxs-lookup"><span data-stu-id="5881f-190">This can be a shared, network location.</span></span>  
  
 <span data-ttu-id="5881f-191">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="5881f-191">**Options**</span></span>  
  
-   <span data-ttu-id="5881f-192">Fare clic su **Connetti** e quindi specificare i dettagli della connessione per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ospita il database da distribuire.</span><span class="sxs-lookup"><span data-stu-id="5881f-192">Click **Connect...** and then specify connection details for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database to deploy.</span></span>  
  
-   <span data-ttu-id="5881f-193">Usare l'elenco a discesa **Selezione database** per specificare il database da distribuire.</span><span class="sxs-lookup"><span data-stu-id="5881f-193">Use the **Select Database** drop-down list to specify the database to deploy.</span></span>  
  
-   <span data-ttu-id="5881f-194">Nel campo **altre impostazioni** specificare una cartella condivisa che sarà accessibile al servizio VM di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-194">In the **Other Settings** field, specify a shared folder that will be accessible to the Azure VM service.</span></span>  
  
##  <a name="azure-sign-in"></a><a name="Azure_sign-in"></a><span data-ttu-id="5881f-195">Accesso ad Azure</span><span class="sxs-lookup"><span data-stu-id="5881f-195">Azure Sign-in</span></span>  
 <span data-ttu-id="5881f-196">Usare questa pagina per connettersi ad Azure e fornire il certificato di gestione o i dettagli del profilo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5881f-196">Use this page to connect to Azure and provide management certificate or publishing profile details.</span></span>  
  
 <span data-ttu-id="5881f-197">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="5881f-197">**Options**</span></span>  
  
-   <span data-ttu-id="5881f-198">**Certificato di gestione** : usare questa opzione per specificare un certificato dall'archivio certificati locale corrispondente al certificato di gestione di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-198">**Management Certificate** - Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span>  
  
-   <span data-ttu-id="5881f-199">**Profilo di pubblicazione** : usare questa opzione se si dispone già di un profilo di pubblicazione scaricato nel computer.</span><span class="sxs-lookup"><span data-stu-id="5881f-199">**Publishing Profile** - Use this option if you already have a publishing profile downloaded to your computer.</span></span>  
  
-   <span data-ttu-id="5881f-200">**Accedi** : usare questa opzione per accedere ad Azure usando un account Microsoft, ad esempio un account Live ID o Hotmail, per generare e scaricare un nuovo certificato di gestione.</span><span class="sxs-lookup"><span data-stu-id="5881f-200">**Sign In** - Use this option to sign in to Azure using a Microsoft account - for example, a Live ID or Hotmail account - to generate and download a new management certificate.</span></span> <span data-ttu-id="5881f-201">Si noti che il numero di certificati per ogni sottoscrizione è limitato.</span><span class="sxs-lookup"><span data-stu-id="5881f-201">Note that the number of certificates per subscription is limited.</span></span>  
  
-   <span data-ttu-id="5881f-202">**Sottoscrizione** : selezionare, digitare o incollare l'ID sottoscrizione di Azure corrispondente al certificato di gestione dall'archivio certificati locale o da un profilo di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5881f-202">**Subscription** - Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store or a publishing profile.</span></span>  
  
##  <a name="deployment-settings-page"></a><a name="Deployment_settings"></a><span data-ttu-id="5881f-203">Pagina Impostazioni distribuzione</span><span class="sxs-lookup"><span data-stu-id="5881f-203">Deployment Settings Page</span></span>  
 <span data-ttu-id="5881f-204">Usare questa pagina per specificare il server di destinazione e fornire i dettagli sul nuovo database.</span><span class="sxs-lookup"><span data-stu-id="5881f-204">Use this page to specify the destination server and to provide details about your new database.</span></span>  
  
 <span data-ttu-id="5881f-205">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="5881f-205">**Options**</span></span>  
  
-   <span data-ttu-id="5881f-206">**Macchina virtuale di Azure** : specificare i dettagli della macchina virtuale che ospiterà il database di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="5881f-206">**Azure Virtual Machine** - Specify details for the VM that will host the SQL Server database:</span></span>  
  
-   <span data-ttu-id="5881f-207">**Nome servizio cloud** : specificare il nome del servizio che ospita la macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="5881f-207">**Cloud Service name** - Specify the name of the service that hosts the VM.</span></span> <span data-ttu-id="5881f-208">Per creare un nuovo servizio cloud, specificare un nome per il nuovo servizio cloud.</span><span class="sxs-lookup"><span data-stu-id="5881f-208">To create a new Cloud Service, specify a name for the new Cloud Service.</span></span>  
  
-   <span data-ttu-id="5881f-209">**Nome macchina virtuale** : specificare il nome della macchina virtuale che ospiterà il database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5881f-209">**Virtual Machine name** - Specify the name of the VM that will host the SQL Server database.</span></span> <span data-ttu-id="5881f-210">Per creare una nuova macchina virtuale di Azure, specificare un nome per la nuova macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="5881f-210">To create a new Azure VM, specify a name for the new VM.</span></span>  
  
-   <span data-ttu-id="5881f-211">**Impostazioni** : usare il pulsante impostazioni per creare una nuova macchina virtuale per ospitare il database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5881f-211">**Settings** - Use the Settings button to create a new VM to host the SQL Server database.</span></span> <span data-ttu-id="5881f-212">Se si usa una macchina virtuale esistente, le informazioni immesse saranno usate per autenticare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="5881f-212">If you are using an existing VM, the information you provide will be used to authenticate your credentials.</span></span>  
  
-   <span data-ttu-id="5881f-213">**Account di archiviazione** : selezionare l'account di archiviazione dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5881f-213">**Storage account** - Select the storage account from the drop-down list.</span></span> <span data-ttu-id="5881f-214">Per creare un nuovo account di archiviazione, specificare un nome per il nuovo account.</span><span class="sxs-lookup"><span data-stu-id="5881f-214">To create a new storage account, specify a name for the new account.</span></span> <span data-ttu-id="5881f-215">Si noti che gli account di archiviazione associati a un gruppo di affinità non saranno disponibili nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5881f-215">Note that storage accounts associated with an Affinity Group will not be available in the drop-down list.</span></span>  
  
-   <span data-ttu-id="5881f-216">**Database di destinazione** : specificare i dettagli per il database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5881f-216">**Target Database** - Specify details for the target database.</span></span>  
  
-   <span data-ttu-id="5881f-217">**Connessione server** : dettagli della connessione per il server.</span><span class="sxs-lookup"><span data-stu-id="5881f-217">**Server Connection** - Connection details for the server.</span></span>  
  
-   <span data-ttu-id="5881f-218">**Database** : specificare o confermare il nome di un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="5881f-218">**Database** - Specify or confirm the name of a new database.</span></span> <span data-ttu-id="5881f-219">Se il nome del database esiste già nell'istanza di destinazione di SQL Server, specificare un nome di database modificato.</span><span class="sxs-lookup"><span data-stu-id="5881f-219">If the database name already exists on the destination SQL Server instance, we suggest that you specify a modified database name.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="5881f-220">Pagina Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5881f-220">Summary Page</span></span>  
 <span data-ttu-id="5881f-221">Usare questa pagina per esaminare le impostazioni specificate per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="5881f-221">Use this page to review the specified settings for the operation.</span></span> <span data-ttu-id="5881f-222">Per completare l'operazione di distribuzione usando le impostazioni specificate, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5881f-222">To complete the deploy operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="5881f-223">Per annullare l'operazione di distribuzione e chiudere la procedura guidata, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="5881f-223">To cancel the deploy operation and exit the wizard, click **Cancel**.</span></span>  
  
 <span data-ttu-id="5881f-224">È possibile che siano necessari passaggi manuali per distribuire i dettagli del database nel database di SQL Server nella macchina virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="5881f-224">There may be manual steps required to deploy database details to the SQL Server database on the Azure VM.</span></span> <span data-ttu-id="5881f-225">Tali passaggi saranno descritti in dettaglio automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5881f-225">These steps will be outlined in detail for you.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="5881f-226">Pagina dei risultati</span><span class="sxs-lookup"><span data-stu-id="5881f-226">Results Page</span></span>  
 <span data-ttu-id="5881f-227">In questa pagina è riportato l'esito positivo o negativo dell'operazione di distribuzione, indicante i risultati di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="5881f-227">This page reports the success or failure of the deploy operation, showing the results of each action.</span></span> <span data-ttu-id="5881f-228">Per ogni azione per la quale è stato rilevato un errore sarà presente un'indicazione nella colonna **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="5881f-228">Any action that encountered an error will have an indication in the **Result** column.</span></span> <span data-ttu-id="5881f-229">Fare clic sul collegamento per visualizzare un report dell'errore relativo all'azione.</span><span class="sxs-lookup"><span data-stu-id="5881f-229">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="5881f-230">Fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5881f-230">Click **Finish** to close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5881f-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5881f-231">See Also</span></span>  
 <span data-ttu-id="5881f-232">[adattatore del cloud per SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5881f-232">[Cloud Adapter for SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span></span>  
 <span data-ttu-id="5881f-233">[Gestione del ciclo di vita del database](../database-lifecycle-management.md) </span><span class="sxs-lookup"><span data-stu-id="5881f-233">[Database Lifecycle Management](../database-lifecycle-management.md) </span></span>  
 <span data-ttu-id="5881f-234">[Esportare un'applicazione livello dati](../data-tier-applications/export-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="5881f-234">[Export a Data-tier Application](../data-tier-applications/export-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="5881f-235">[Importare un file BACPAC per creare un nuovo database utente](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span><span class="sxs-lookup"><span data-stu-id="5881f-235">[Import a BACPAC File to Create a New User Database](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span></span>  
 <span data-ttu-id="5881f-236">[Backup e ripristino del database SQL di Azure](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span><span class="sxs-lookup"><span data-stu-id="5881f-236">[Azure SQL Database Backup and Restore](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span></span>  
 <span data-ttu-id="5881f-237">[Distribuzione SQL Server in macchine virtuali di Azure](https://msdn.microsoft.com/library/dn133141.aspx) </span><span class="sxs-lookup"><span data-stu-id="5881f-237">[SQL Server Deployment in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx) </span></span>  
 [<span data-ttu-id="5881f-238">Preparazione della migrazione a SQL Server in Macchine virtuali di Azure</span><span class="sxs-lookup"><span data-stu-id="5881f-238">Getting Ready to Migrate to SQL Server in Azure Virtual Machines</span></span>](https://msdn.microsoft.com/library/dn133142.aspx)  
  
  
