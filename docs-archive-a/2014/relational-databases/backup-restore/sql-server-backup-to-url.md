---
title: Backup di SQL Server nell'URL | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 11be89e9-ff2a-4a94-ab5d-27d8edf9167d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6918a099e00b1de9e773320b5c6c0e4089859e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718329"
---
# <a name="sql-server-backup-to-url"></a><span data-ttu-id="09d0d-102">Backup di SQL Server nell'URL</span><span class="sxs-lookup"><span data-stu-id="09d0d-102">SQL Server Backup to URL</span></span>
  <span data-ttu-id="09d0d-103">Questo argomento introduce i concetti, i requisiti e i componenti necessari per usare il servizio di archiviazione BLOB di Azure come destinazione di backup.</span><span class="sxs-lookup"><span data-stu-id="09d0d-103">This topic introduces the concepts, requirements and components necessary to use the Azure Blob storage service as a backup destination.</span></span> <span data-ttu-id="09d0d-104">La funzionalità di backup e ripristino è uguale o simile a quella delle opzioni DISK e TAPE, con alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="09d0d-104">The backup and restore functionality are same or similar to when using DISK or TAPE, with a few differences.</span></span> <span data-ttu-id="09d0d-105">Nell'argomento sono descritte le differenze e le eccezioni rilevanti e sono inclusi alcuni esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="09d0d-105">The differences are and any notable exceptions, and a few code examples are included in this topic.</span></span>  
  
## <a name="requirements-components-and-concepts"></a><span data-ttu-id="09d0d-106">Requisiti, componenti e concetti</span><span class="sxs-lookup"><span data-stu-id="09d0d-106">Requirements, Components, and Concepts</span></span>  
 <span data-ttu-id="09d0d-107">**Contenuto della sezione:**</span><span class="sxs-lookup"><span data-stu-id="09d0d-107">**In this section:**</span></span>  
  
-   [<span data-ttu-id="09d0d-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="09d0d-108">Security</span></span>](#security)  
  
-   [<span data-ttu-id="09d0d-109">Introduzione ai componenti e ai concetti chiave</span><span class="sxs-lookup"><span data-stu-id="09d0d-109">Introduction to Key Components and Concepts</span></span>](#intorkeyconcepts)  
  
-   [<span data-ttu-id="09d0d-110">Servizio di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="09d0d-110">Azure Blob Storage Service</span></span>](#Blob)  
  
-   [<span data-ttu-id="09d0d-111">Componenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="09d0d-111">SQL Server Components</span></span>](#sqlserver)  
  
-   [<span data-ttu-id="09d0d-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="09d0d-112">Limitations</span></span>](#limitations)  
  
-   [<span data-ttu-id="09d0d-113">Supporto per le istruzioni backup/restore</span><span class="sxs-lookup"><span data-stu-id="09d0d-113">Support for Backup/Restore Statements</span></span>](#Support)  
  
-   [<span data-ttu-id="09d0d-114">Utilizzo dell'attività di backup in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09d0d-114">Using Backup Task in SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#BackupTaskSSMS)  
  
-   [<span data-ttu-id="09d0d-115">Backup di SQL Server nell'URL tramite la Creazione guidata piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="09d0d-115">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>](sql-server-backup-to-url.md#MaintenanceWiz)  
  
-   [<span data-ttu-id="09d0d-116">Ripristino da Archiviazione di Azure mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09d0d-116">Restoring from Azure storage Using SQL Server Management Studio</span></span>](sql-server-backup-to-url.md#RestoreSSMS)  
  
###  <a name="security"></a><a name="security"></a> <span data-ttu-id="09d0d-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="09d0d-117">Security</span></span>  
 <span data-ttu-id="09d0d-118">Di seguito sono riportati i requisiti e le considerazioni sulla sicurezza per il backup o il ripristino dai servizi di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-118">The following are security considerations and requirements when backing up to or restoring from the Azure Blob storage services.</span></span>  
  
-   <span data-ttu-id="09d0d-119">Quando si crea un contenitore per il servizio di archiviazione BLOB di Azure, è consigliabile impostare l'accesso su **privato**.</span><span class="sxs-lookup"><span data-stu-id="09d0d-119">When creating a container for the Azure Blob storage service, we recommend that you set the access to **private**.</span></span> <span data-ttu-id="09d0d-120">In questo modo si limita l'accesso a utenti o account in grado di specificare le informazioni necessarie per l'autenticazione all'account di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-120">Setting the access to private restricts the access to users or accounts able to provide the necessary information to authenticate to the Azure account.</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="09d0d-121">richiede l'archiviazione del nome dell'account di Azure e della chiave di accesso in una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credenziale.</span><span class="sxs-lookup"><span data-stu-id="09d0d-121">requires Azure account name and access key authentication to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential.</span></span> <span data-ttu-id="09d0d-122">Queste informazioni vengono usate per eseguire l'autenticazione all'account di Azure quando vengono eseguite operazioni di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="09d0d-122">This information is used to authenticate to the Azure account when it performs backup or restore operations.</span></span>  
  
-   <span data-ttu-id="09d0d-123">All'account utente usato per eseguire i comandi BACKUP o RESTORE deve essere associato il ruolo del database **db_backup operator** con autorizzazioni **Modifica qualsiasi credenziale** .</span><span class="sxs-lookup"><span data-stu-id="09d0d-123">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
###  <a name="introduction-to-key-components-and-concepts"></a><a name="intorkeyconcepts"></a><span data-ttu-id="09d0d-124">Introduzione ai componenti e ai concetti chiave</span><span class="sxs-lookup"><span data-stu-id="09d0d-124">Introduction to Key Components and Concepts</span></span>  
 <span data-ttu-id="09d0d-125">Le due sezioni seguenti introducono il servizio di archiviazione BLOB di Azure e i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componenti usati durante il backup o il ripristino dal servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-125">The following two sections introduce the Azure Blob storage service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components used when backing up to or restoring from the Azure Blob storage service.</span></span> <span data-ttu-id="09d0d-126">È importante comprendere i componenti e l'interazione tra di essi per eseguire un backup o il ripristino dal servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-126">It is important to understand the components and the interaction between them to do a backup to or restore from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="09d0d-127">La creazione di un account Azure è il primo passaggio per questo processo.</span><span class="sxs-lookup"><span data-stu-id="09d0d-127">Creating an Azure account is the first step to this process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="09d0d-128">Usa il **nome dell'account di archiviazione di Azure** e i relativi valori della **chiave di accesso** per autenticare e scrivere e leggere i BLOB nel servizio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="09d0d-128">uses the **Azure storage account name** and its **access key** values to authenticate and write and read blobs to the storage service.</span></span> <span data-ttu-id="09d0d-129">Le credenziali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tramite cui vengono archiviate queste informazioni di autenticazione, vengono utilizzate durante le operazioni di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="09d0d-129">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential stores this authentication information and is used during the backup or restore operations.</span></span> <span data-ttu-id="09d0d-130">Per una procedura dettagliata completa per la creazione di un account di archiviazione e l'esecuzione di un ripristino semplice, vedere [esercitazione sull'uso del servizio di archiviazione di Azure per SQL Server backup e ripristino](https://go.microsoft.com/fwlink/?LinkId=271615).</span><span class="sxs-lookup"><span data-stu-id="09d0d-130">For a complete walkthrough of creating a storage account and performing a simple restore, see [Tutorial Using Azure Storage Service for SQL Server Backup and Restore](https://go.microsoft.com/fwlink/?LinkId=271615).</span></span>  
  
 <span data-ttu-id="09d0d-131">![Mapping dell'account di archiviazione alle credenziali SQL](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "Mapping dell'account di archiviazione alle credenziali SQL")</span><span class="sxs-lookup"><span data-stu-id="09d0d-131">![mapping storage account to sql credentials](../../tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
###  <a name="azure-blob-storage-service"></a><a name="Blob"></a><span data-ttu-id="09d0d-132">Servizio di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="09d0d-132">Azure Blob Storage Service</span></span>  
 <span data-ttu-id="09d0d-133">**Account di archiviazione:** l'account di archiviazione è il punto di partenza per tutti i servizi di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="09d0d-133">**Storage Account:** The storage account is the starting point for all storage services.</span></span> <span data-ttu-id="09d0d-134">Per accedere al servizio di archiviazione BLOB di Azure, creare prima un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-134">To access the Azure Blob Storage service, first create an Azure storage account.</span></span> <span data-ttu-id="09d0d-135">Il **nome dell'account di archiviazione** e le relative proprietà **chiave di accesso** sono necessari per eseguire l'autenticazione nel servizio di archiviazione BLOB di Azure e nei relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="09d0d-135">The **storage account name** and its **access key** properties are required to authenticate to the Azure Blob Storage service and its components.</span></span>  
  
 <span data-ttu-id="09d0d-136">**Contenitore:** Un contenitore fornisce un raggruppamento di un set di BLOB e può archiviare un numero illimitato di BLOB.</span><span class="sxs-lookup"><span data-stu-id="09d0d-136">**Container:** A container provides a grouping of a set of Blobs, and can store an unlimited number of Blobs.</span></span> <span data-ttu-id="09d0d-137">Per scrivere un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup nel servizio BLOB di Azure, è necessario che sia stato creato almeno il contenitore radice.</span><span class="sxs-lookup"><span data-stu-id="09d0d-137">To write a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to the Azure Blob service, you must have at least the root container created.</span></span>  
  
 <span data-ttu-id="09d0d-138">**BLOB:** file di qualsiasi tipo e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="09d0d-138">**Blob:** A file of any type and size.</span></span> <span data-ttu-id="09d0d-139">Esistono due tipi di BLOB che è possibile archiviare nel servizio di archiviazione BLOB di Azure: BLOB in blocchi e di pagine.</span><span class="sxs-lookup"><span data-stu-id="09d0d-139">There are two types of blobs that can be stored in the Azure Blob storage service: block and page blobs.</span></span> <span data-ttu-id="09d0d-140">Nel backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] il tipo di BLOB utilizzato è quello di pagine.</span><span class="sxs-lookup"><span data-stu-id="09d0d-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup uses page Blobs as the Blob type.</span></span> <span data-ttu-id="09d0d-141">I BLOB sono indirizzabili usando il formato di URL seguente: https:// \<storage account> . blob.Core.Windows.NET/\<container>/\<blob></span><span class="sxs-lookup"><span data-stu-id="09d0d-141">Blobs are addressable using the following URL format: https://\<storage account>.blob.core.windows.net/\<container>/\<blob></span></span>  
  
 <span data-ttu-id="09d0d-142">![Archiviazione BLOB di Azure](../../database-engine/media/backuptocloud-blobarchitecture.gif "Archiviazione BLOB di Azure")</span><span class="sxs-lookup"><span data-stu-id="09d0d-142">![Azure Blob Storage](../../database-engine/media/backuptocloud-blobarchitecture.gif "Azure Blob Storage")</span></span>  
  
 <span data-ttu-id="09d0d-143">Per altre informazioni sul servizio di archiviazione BLOB di Azure, vedere [come usare il servizio di archiviazione BLOB di Azure](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span><span class="sxs-lookup"><span data-stu-id="09d0d-143">For more information about the Azure Blob storage service, see [How to use the Azure Blob Storage Service](https://www.windowsazure.com/develop/net/how-to-guides/blob-storage/)</span></span>  
  
 <span data-ttu-id="09d0d-144">Per altre informazioni sui BLOB di pagine, vedere [Informazioni sui BLOB in blocchi, sui BLOB di aggiunta e sui BLOB di pagine](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span><span class="sxs-lookup"><span data-stu-id="09d0d-144">For more information about page Blobs, see [Understanding Block and Page Blobs](https://msdn.microsoft.com/library/windowsazure/ee691964.aspx)</span></span>  
  
###  <a name="ssnoversion-components"></a><a name="sqlserver"></a> <span data-ttu-id="09d0d-145">Componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d0d-145">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components</span></span>  
 <span data-ttu-id="09d0d-146">**URL:** un URL specifica un URI (Uniform Resource Identifier) in un file di backup univoco.</span><span class="sxs-lookup"><span data-stu-id="09d0d-146">**URL:** A URL specifies a Uniform Resource Identifier (URI) to a unique backup file.</span></span> <span data-ttu-id="09d0d-147">L'URL viene utilizzato per specificare il percorso e il nome del file di backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="09d0d-147">The URL is used to provide the location and name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup file.</span></span> <span data-ttu-id="09d0d-148">In questa implementazione, l'unico URL valido è quello che punta a un BLOB di pagine in un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-148">In this implementation, the only valid URL is one that points to a page Blob in an Azure storage account.</span></span> <span data-ttu-id="09d0d-149">L'URL deve puntare a un BLOB effettivo, non solo a un contenitore.</span><span class="sxs-lookup"><span data-stu-id="09d0d-149">The URL must point to an actual Blob, not just a container.</span></span> <span data-ttu-id="09d0d-150">Se il BLOB non è disponibile, viene creato.</span><span class="sxs-lookup"><span data-stu-id="09d0d-150">If the Blob does not exist, it is created.</span></span> <span data-ttu-id="09d0d-151">Se viene specificato un BLOB esistente, il BACKUP ha esito negativo, a meno che non sia stata specificata l'opzione "WITH FORMAT".</span><span class="sxs-lookup"><span data-stu-id="09d0d-151">If an existing Blob is specified, BACKUP fails, unless the "WITH FORMAT" option is specified.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="09d0d-152">Se si sceglie di copiare e caricare un file di backup nel servizio di archiviazione BLOB di Azure, usare il BLOB di pagine come opzione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="09d0d-152">If you choose to copy and upload a backup file to the Azure Blob storage service, use page blob as your storage option.</span></span> <span data-ttu-id="09d0d-153">I ripristini dai BLOB in blocchi non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="09d0d-153">Restores from Block Blobs are not supported.</span></span> <span data-ttu-id="09d0d-154">Il ripristino da un BLOB in blocchi non viene completato e viene visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="09d0d-154">RESTORE from a block blob type fails with an error.</span></span>  
  
 <span data-ttu-id="09d0d-155">Di seguito è riportato un valore URL di esempio: http [s]://ACCOUNTNAME.Blob.core.windows.net/ \<CONTAINER> / \<FILENAME.bak> .</span><span class="sxs-lookup"><span data-stu-id="09d0d-155">Here is a sample URL value: http[s]://ACCOUNTNAME.Blob.core.windows.net/\<CONTAINER>/\<FILENAME.bak>.</span></span> <span data-ttu-id="09d0d-156">Anche se non richiesto, è consigliabile utilizzare HTTPS.</span><span class="sxs-lookup"><span data-stu-id="09d0d-156">HTTPS is not required, but is recommended.</span></span>  
  
 <span data-ttu-id="09d0d-157">**Credenziale:** una credenziale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è un oggetto usato per archiviare le informazioni di autenticazione necessarie per la connessione a una risorsa all'esterno di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09d0d-157">**Credential:** A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="09d0d-158">Qui, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i processi di backup e ripristino usano le credenziali per eseguire l'autenticazione nel servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-158">Here, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="09d0d-159">Nelle credenziali vengono archiviati il nome dell'account di archiviazione e i relativi valori della **chiave di accesso** .</span><span class="sxs-lookup"><span data-stu-id="09d0d-159">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="09d0d-160">Una volta create, le credenziali devono essere specificate nell'opzione WITH CREDENTIAL durante l'esecuzione delle istruzioni BACKUP/RESTORE.</span><span class="sxs-lookup"><span data-stu-id="09d0d-160">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="09d0d-161">Per altre informazioni su come visualizzare, copiare o rigenerare le **access keys**dell'account di archiviazione, vedere la pagina relativa alle [chiavi di accesso dell'account di archiviazione](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="09d0d-161">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="09d0d-162">Per istruzioni dettagliate sulla creazione di credenziali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere l'esempio [Create a Credential](#credential) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="09d0d-162">For step by step instructions about how to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Credential, see [Create a Credential](#credential) example later in this topic.</span></span>  
  
 <span data-ttu-id="09d0d-163">Per informazioni generali sulle credenziali, vedere [Credenziali](../security/authentication-access/credentials-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="09d0d-163">For general information about credentials, see [Credentials](../security/authentication-access/credentials-database-engine.md)</span></span>  
  
 <span data-ttu-id="09d0d-164">Per informazioni su altri esempi in cui vengono usate le credenziali, vedere [creare un Proxy SQL Server Agent](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="09d0d-164">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
###  <a name="limitations"></a><a name="limitations"></a> <span data-ttu-id="09d0d-165">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="09d0d-165">Limitations</span></span>  
  
-   <span data-ttu-id="09d0d-166">Il backup in Archiviazione Premium non è supportato.</span><span class="sxs-lookup"><span data-stu-id="09d0d-166">Backup to premium storage is not supported.</span></span>  
  
-   <span data-ttu-id="09d0d-167">Le dimensioni massime di backup supportate sono 1 TB.</span><span class="sxs-lookup"><span data-stu-id="09d0d-167">The maximum backup size supported is 1 TB.</span></span>  
  
-   <span data-ttu-id="09d0d-168">È possibile eseguire istruzioni di backup o ripristino tramite TSQL, SMO o cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09d0d-168">You can issue backup or restore statements by using TSQL, SMO, or PowerShell cmdlets.</span></span> <span data-ttu-id="09d0d-169">Il backup o il ripristino dal servizio di archiviazione BLOB di Azure tramite SQL Server Management Studio backup o ripristino guidato non è attualmente abilitato.</span><span class="sxs-lookup"><span data-stu-id="09d0d-169">A backup to or restoring from the Azure Blob storage service by using SQL Server Management Studio Backup or Restore wizard is not currently enabled.</span></span>  
  
-   <span data-ttu-id="09d0d-170">La creazione di un nome di dispositivo logico non è supportata.</span><span class="sxs-lookup"><span data-stu-id="09d0d-170">Creating a logical device name is not supported.</span></span> <span data-ttu-id="09d0d-171">Di conseguenza, non è supportata neanche l'aggiunta di un URL come dispositivo di backup tramite sp_dumpdevice o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="09d0d-171">So adding URL as a backup device using sp_dumpdevice or through SQL Server Management Studio is not supported.</span></span>  
  
-   <span data-ttu-id="09d0d-172">L'accodamento ai BLOB di backup esistenti non è supportato.</span><span class="sxs-lookup"><span data-stu-id="09d0d-172">Appending to existing backup blobs is not supported.</span></span> <span data-ttu-id="09d0d-173">I backup in un BLOB esistente possono solo essere sovrascritti tramite l'opzione WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="09d0d-173">Backups to an existing Blob can only be overwritten by using the WITH FORMAT option.</span></span>  
  
-   <span data-ttu-id="09d0d-174">Il backup in più BLOB effettuato con una singola operazione non è supportato.</span><span class="sxs-lookup"><span data-stu-id="09d0d-174">Backup to multiple blobs in a single backup operation is not supported.</span></span> <span data-ttu-id="09d0d-175">Ad esempio, se si esegue l'operazione riportata di seguito viene restituito un errore:</span><span class="sxs-lookup"><span data-stu-id="09d0d-175">For example, the following returns an error:</span></span>  
  
    ```sql
    BACKUP DATABASE AdventureWorks2012
    TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_1.bak'
       URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_2.bak'
          WITH CREDENTIAL = 'mycredential'
         ,STATS = 5;  
    GO
    ```  
  
-   <span data-ttu-id="09d0d-176">La specifica delle dimensioni del blocco con `BACKUP` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="09d0d-176">Specifying a block size with `BACKUP` is not supported.</span></span>  
  
-   <span data-ttu-id="09d0d-177">La specifica di `MAXTRANSFERSIZE` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="09d0d-177">Specifying `MAXTRANSFERSIZE` is not supported.</span></span>  
  
-   <span data-ttu-id="09d0d-178">La specifica delle opzioni del set di backup, `RETAINDAYS` e `EXPIREDATE`, non è supportata.</span><span class="sxs-lookup"><span data-stu-id="09d0d-178">Specifying backupset options - `RETAINDAYS` and `EXPIREDATE` are not supported.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="09d0d-179">è previsto un limite massimo di 259 caratteri per il nome di un dispositivo di backup.</span><span class="sxs-lookup"><span data-stu-id="09d0d-179">has a maximum limit of 259 characters for a backup device name.</span></span> <span data-ttu-id="09d0d-180">BACKUP TO URL utilizza 36 caratteri per gli elementi necessari usati per specificare l'URL (https://.blob.core.windows.net//.bak ) lasciando 223 caratteri per i nomi dell'account, del contenitore e del BLOB.</span><span class="sxs-lookup"><span data-stu-id="09d0d-180">The BACKUP TO URL consumes 36 characters for the required elements used to specify the URL - 'https://.blob.core.windows.net//.bak', leaving 223 characters for account, container, and blob names put together.</span></span>  
  
###  <a name="support-for-backuprestore-statements"></a><a name="Support"></a> <span data-ttu-id="09d0d-181">Supporto per le istruzioni di backup/ripristino</span><span class="sxs-lookup"><span data-stu-id="09d0d-181">Support for Backup/Restore Statements</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="09d0d-182">Istruzione di backup/ripristino</span><span class="sxs-lookup"><span data-stu-id="09d0d-182">Backup/Restore Statement</span></span>|<span data-ttu-id="09d0d-183">Supportato</span><span class="sxs-lookup"><span data-stu-id="09d0d-183">Supported</span></span>|<span data-ttu-id="09d0d-184">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="09d0d-184">Exceptions</span></span>|<span data-ttu-id="09d0d-185">Commenti</span><span class="sxs-lookup"><span data-stu-id="09d0d-185">Comments</span></span>|  
|<span data-ttu-id="09d0d-186">BACKUP</span><span class="sxs-lookup"><span data-stu-id="09d0d-186">BACKUP</span></span>|<span data-ttu-id="09d0d-187">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-187">&#x2713;</span></span>|<span data-ttu-id="09d0d-188">BLOCKSIZE e MAXTRANSFERSIZE non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="09d0d-188">BLOCKSIZE, and MAXTRANSFERSIZE are not supported.</span></span>|<span data-ttu-id="09d0d-189">Richiede la specifica di WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-189">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="09d0d-190">RESTORE</span><span class="sxs-lookup"><span data-stu-id="09d0d-190">RESTORE</span></span>|<span data-ttu-id="09d0d-191">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-191">&#x2713;</span></span>||<span data-ttu-id="09d0d-192">Richiede la specifica di WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-192">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="09d0d-193">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="09d0d-193">RESTORE FILELISTONLY</span></span>|<span data-ttu-id="09d0d-194">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-194">&#x2713;</span></span>||<span data-ttu-id="09d0d-195">Richiede la specifica di WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-195">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="09d0d-196">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="09d0d-196">RESTORE HEADERONLY</span></span>|<span data-ttu-id="09d0d-197">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-197">&#x2713;</span></span>||<span data-ttu-id="09d0d-198">Richiede la specifica di WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-198">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="09d0d-199">RESTORE LABELONLY</span><span class="sxs-lookup"><span data-stu-id="09d0d-199">RESTORE LABELONLY</span></span>|<span data-ttu-id="09d0d-200">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-200">&#x2713;</span></span>||<span data-ttu-id="09d0d-201">Richiede la specifica di WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-201">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="09d0d-202">RESTORE VERIFYONLY</span><span class="sxs-lookup"><span data-stu-id="09d0d-202">RESTORE VERIFYONLY</span></span>|<span data-ttu-id="09d0d-203">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-203">&#x2713;</span></span>||<span data-ttu-id="09d0d-204">Richiede la specifica di WITH CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-204">Requires WITH CREDENTIAL specified</span></span>|  
|<span data-ttu-id="09d0d-205">RESTORE REWINDONLY</span><span class="sxs-lookup"><span data-stu-id="09d0d-205">RESTORE REWINDONLY</span></span>|<span data-ttu-id="09d0d-206">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-206">&#x2713;</span></span>|||  
  
 <span data-ttu-id="09d0d-207">Per la sintassi e informazioni generali sulle istruzioni di backup, vedere [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09d0d-207">For syntax and general information about backup statements, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
 <span data-ttu-id="09d0d-208">Per la sintassi e informazioni generali sulle istruzioni di ripristino, vedere [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09d0d-208">For syntax and general information about restore statements, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>  
  
### <a name="support-for-backup-arguments"></a><span data-ttu-id="09d0d-209">Supporto per gli argomenti dell'istruzione BACKUP</span><span class="sxs-lookup"><span data-stu-id="09d0d-209">Support for Backup Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="09d0d-210">Argomento</span><span class="sxs-lookup"><span data-stu-id="09d0d-210">Argument</span></span>|<span data-ttu-id="09d0d-211">Supportato</span><span class="sxs-lookup"><span data-stu-id="09d0d-211">Supported</span></span>|<span data-ttu-id="09d0d-212">Eccezione</span><span class="sxs-lookup"><span data-stu-id="09d0d-212">Exception</span></span>|<span data-ttu-id="09d0d-213">Commenti</span><span class="sxs-lookup"><span data-stu-id="09d0d-213">Comments</span></span>|  
|<span data-ttu-id="09d0d-214">DATABASE</span><span class="sxs-lookup"><span data-stu-id="09d0d-214">DATABASE</span></span>|<span data-ttu-id="09d0d-215">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-215">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-216">LOG</span><span class="sxs-lookup"><span data-stu-id="09d0d-216">LOG</span></span>|<span data-ttu-id="09d0d-217">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-217">&#x2713;</span></span>|||  
||  
|<span data-ttu-id="09d0d-218">TO (URL)</span><span class="sxs-lookup"><span data-stu-id="09d0d-218">TO (URL)</span></span>|<span data-ttu-id="09d0d-219">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-219">&#x2713;</span></span>|<span data-ttu-id="09d0d-220">Diversamente da DISK e TAPE, l'URL non supporta la specifica o la creazione di un nome logico.</span><span class="sxs-lookup"><span data-stu-id="09d0d-220">Unlike DISK and TAPE, URL does not support specifying or creating a logical name.</span></span>|<span data-ttu-id="09d0d-221">Questo argomento viene utilizzato per specificare il percorso URL del file di backup.</span><span class="sxs-lookup"><span data-stu-id="09d0d-221">This argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="09d0d-222">MIRROR TO</span><span class="sxs-lookup"><span data-stu-id="09d0d-222">MIRROR TO</span></span>|<span data-ttu-id="09d0d-223">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-223">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-224">**OPZIONI WITH:**</span><span class="sxs-lookup"><span data-stu-id="09d0d-224">**WITH OPTIONS:**</span></span>||||  
|<span data-ttu-id="09d0d-225">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-225">CREDENTIAL</span></span>|<span data-ttu-id="09d0d-226">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-226">&#x2713;</span></span>||<span data-ttu-id="09d0d-227">WITH CREDENTIAL è supportato solo quando si usa l'opzione BACKUP TO URL per eseguire il backup nel servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-227">WITH CREDENTIAL is only supported when using BACKUP TO URL option to back up to the Azure Blob storage service.</span></span>|  
|<span data-ttu-id="09d0d-228">DIFFERENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-228">DIFFERENTIAL</span></span>|<span data-ttu-id="09d0d-229">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-229">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-230">COPY_ONLY</span><span class="sxs-lookup"><span data-stu-id="09d0d-230">COPY_ONLY</span></span>|<span data-ttu-id="09d0d-231">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-231">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-232">COMPRESSION&#124;NO_COMPRESSION</span><span class="sxs-lookup"><span data-stu-id="09d0d-232">COMPRESSION&#124;NO_COMPRESSION</span></span>|<span data-ttu-id="09d0d-233">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-233">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-234">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="09d0d-234">DESCRIPTION</span></span>|<span data-ttu-id="09d0d-235">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-235">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-236">NAME</span><span class="sxs-lookup"><span data-stu-id="09d0d-236">NAME</span></span>|<span data-ttu-id="09d0d-237">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-237">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-238">EXPIREDATE &#124; RETAINDAYS</span><span class="sxs-lookup"><span data-stu-id="09d0d-238">EXPIREDATE &#124; RETAINDAYS</span></span>|<span data-ttu-id="09d0d-239">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-239">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-240">NOINIT &#124; INIT</span><span class="sxs-lookup"><span data-stu-id="09d0d-240">NOINIT &#124; INIT</span></span>|<span data-ttu-id="09d0d-241">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-241">&#x2713;</span></span>||<span data-ttu-id="09d0d-242">Se utilizzata, questa opzione è ignorata.</span><span class="sxs-lookup"><span data-stu-id="09d0d-242">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="09d0d-243">L'accodamento ai BLOB non è consentito.</span><span class="sxs-lookup"><span data-stu-id="09d0d-243">Appending to blobs is not possible.</span></span> <span data-ttu-id="09d0d-244">Per sovrascrivere un backup, utilizzare l'argomento FORMAT.</span><span class="sxs-lookup"><span data-stu-id="09d0d-244">To overwrite a backup use the FORMAT argument.</span></span>|  
|<span data-ttu-id="09d0d-245">NOSKIP &#124; SKIP</span><span class="sxs-lookup"><span data-stu-id="09d0d-245">NOSKIP &#124; SKIP</span></span>|<span data-ttu-id="09d0d-246">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-246">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-247">NOFORMAT &#124; FORMAT</span><span class="sxs-lookup"><span data-stu-id="09d0d-247">NOFORMAT &#124; FORMAT</span></span>|<span data-ttu-id="09d0d-248">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-248">&#x2713;</span></span>||<span data-ttu-id="09d0d-249">Se utilizzata, questa opzione è ignorata.</span><span class="sxs-lookup"><span data-stu-id="09d0d-249">This option is ignored if used.</span></span><br /><br /> <span data-ttu-id="09d0d-250">Un backup eseguito in un BLOB esistente non viene completato a meno che non venga specificato WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="09d0d-250">A backup taken to an existing blob fails unless WITH FORMAT is specified.</span></span> <span data-ttu-id="09d0d-251">Il BLOB esistente viene sovrascritto quando viene specificato WITH FORMAT.</span><span class="sxs-lookup"><span data-stu-id="09d0d-251">The existing blob is overwritten when WITH FORMAT is specified.</span></span>|  
|<span data-ttu-id="09d0d-252">MEDIADESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="09d0d-252">MEDIADESCRIPTION</span></span>|<span data-ttu-id="09d0d-253">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-253">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-254">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="09d0d-254">MEDIANAME</span></span>|<span data-ttu-id="09d0d-255">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-255">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-256">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="09d0d-256">BLOCKSIZE</span></span>|<span data-ttu-id="09d0d-257">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-257">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-258">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="09d0d-258">BUFFERCOUNT</span></span>|<span data-ttu-id="09d0d-259">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-259">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-260">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="09d0d-260">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="09d0d-261">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-261">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-262">NO_CHECKSUM &#124; CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="09d0d-262">NO_CHECKSUM &#124; CHECKSUM</span></span>|<span data-ttu-id="09d0d-263">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-263">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="09d0d-264">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="09d0d-265">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-265">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-266">STATS (Statistiche)</span><span class="sxs-lookup"><span data-stu-id="09d0d-266">STATS</span></span>|<span data-ttu-id="09d0d-267">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-267">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-268">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="09d0d-268">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="09d0d-269">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-269">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-270">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="09d0d-270">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="09d0d-271">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-271">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-272">NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="09d0d-272">NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="09d0d-273">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-273">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-274">NO_TRUNCATE</span><span class="sxs-lookup"><span data-stu-id="09d0d-274">NO_TRUNCATE</span></span>|<span data-ttu-id="09d0d-275">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-275">&#x2713;</span></span>|||  
  
 <span data-ttu-id="09d0d-276">Per altre informazioni sugli argomenti di backup, vedere [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09d0d-276">For more information about backup arguments, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="support-for-restore-arguments"></a><span data-ttu-id="09d0d-277">Supporto per gli argomenti dell'istruzione RESTORE</span><span class="sxs-lookup"><span data-stu-id="09d0d-277">Support for Restore Arguments</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="09d0d-278">Argomento</span><span class="sxs-lookup"><span data-stu-id="09d0d-278">Argument</span></span>|<span data-ttu-id="09d0d-279">Supportato</span><span class="sxs-lookup"><span data-stu-id="09d0d-279">Supported</span></span>|<span data-ttu-id="09d0d-280">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="09d0d-280">Exceptions</span></span>|<span data-ttu-id="09d0d-281">Commenti</span><span class="sxs-lookup"><span data-stu-id="09d0d-281">Comments</span></span>|  
|<span data-ttu-id="09d0d-282">DATABASE</span><span class="sxs-lookup"><span data-stu-id="09d0d-282">DATABASE</span></span>|<span data-ttu-id="09d0d-283">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-283">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-284">LOG</span><span class="sxs-lookup"><span data-stu-id="09d0d-284">LOG</span></span>|<span data-ttu-id="09d0d-285">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-285">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-286">FROM (URL)</span><span class="sxs-lookup"><span data-stu-id="09d0d-286">FROM (URL)</span></span>|<span data-ttu-id="09d0d-287">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-287">&#x2713;</span></span>||<span data-ttu-id="09d0d-288">L'argomento FROM URL viene utilizzato per specificare il percorso URL del file di backup.</span><span class="sxs-lookup"><span data-stu-id="09d0d-288">The FROM URL argument is used to specify the URL path for the backup file.</span></span>|  
|<span data-ttu-id="09d0d-289">**WITH Options:**</span><span class="sxs-lookup"><span data-stu-id="09d0d-289">**WITH Options:**</span></span>||||  
|<span data-ttu-id="09d0d-290">CREDENTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-290">CREDENTIAL</span></span>|<span data-ttu-id="09d0d-291">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-291">&#x2713;</span></span>||<span data-ttu-id="09d0d-292">WITH CREDENTIAL è supportato solo quando si usa l'opzione RESTOre FROM URL per eseguire il ripristino dal servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-292">WITH CREDENTIAL is only supported when using RESTORE FROM URL option to restore from Azure Blob Storage service.</span></span>|  
|<span data-ttu-id="09d0d-293">PARTIAL</span><span class="sxs-lookup"><span data-stu-id="09d0d-293">PARTIAL</span></span>|<span data-ttu-id="09d0d-294">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-294">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span><span class="sxs-lookup"><span data-stu-id="09d0d-295">RECOVERY &#124; NORECOVERY &#124; STANDBY</span></span>|<span data-ttu-id="09d0d-296">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-296">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-297">LOADHISTORY</span><span class="sxs-lookup"><span data-stu-id="09d0d-297">LOADHISTORY</span></span>|<span data-ttu-id="09d0d-298">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-298">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-299">MOVE</span><span class="sxs-lookup"><span data-stu-id="09d0d-299">MOVE</span></span>|<span data-ttu-id="09d0d-300">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-300">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-301">REPLACE</span><span class="sxs-lookup"><span data-stu-id="09d0d-301">REPLACE</span></span>|<span data-ttu-id="09d0d-302">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-302">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-303">RESTART</span><span class="sxs-lookup"><span data-stu-id="09d0d-303">RESTART</span></span>|<span data-ttu-id="09d0d-304">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-304">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-305">RESTRICTED_USER</span><span class="sxs-lookup"><span data-stu-id="09d0d-305">RESTRICTED_USER</span></span>|<span data-ttu-id="09d0d-306">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-306">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-307">FILE</span><span class="sxs-lookup"><span data-stu-id="09d0d-307">FILE</span></span>|<span data-ttu-id="09d0d-308">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-308">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-309">PASSWORD</span><span class="sxs-lookup"><span data-stu-id="09d0d-309">PASSWORD</span></span>|<span data-ttu-id="09d0d-310">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-310">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-311">MEDIANAME</span><span class="sxs-lookup"><span data-stu-id="09d0d-311">MEDIANAME</span></span>|<span data-ttu-id="09d0d-312">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-312">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-313">MEDIAPASSWORD</span><span class="sxs-lookup"><span data-stu-id="09d0d-313">MEDIAPASSWORD</span></span>|<span data-ttu-id="09d0d-314">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-314">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-315">BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="09d0d-315">BLOCKSIZE</span></span>|<span data-ttu-id="09d0d-316">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-316">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-317">BUFFERCOUNT</span><span class="sxs-lookup"><span data-stu-id="09d0d-317">BUFFERCOUNT</span></span>|<span data-ttu-id="09d0d-318">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-318">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-319">MAXTRANSFERSIZE</span><span class="sxs-lookup"><span data-stu-id="09d0d-319">MAXTRANSFERSIZE</span></span>|<span data-ttu-id="09d0d-320">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-320">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-321">CHECKSUM &#124; NO_CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="09d0d-321">CHECKSUM &#124; NO_CHECKSUM</span></span>|<span data-ttu-id="09d0d-322">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-322">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span><span class="sxs-lookup"><span data-stu-id="09d0d-323">STOP_ON_ERROR &#124; CONTINUE_AFTER_ERROR</span></span>|<span data-ttu-id="09d0d-324">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-324">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-325">FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="09d0d-325">FILESTREAM</span></span>|<span data-ttu-id="09d0d-326">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-326">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-327">STATS (Statistiche)</span><span class="sxs-lookup"><span data-stu-id="09d0d-327">STATS</span></span>|<span data-ttu-id="09d0d-328">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-328">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-329">REWIND &#124; NOREWIND</span><span class="sxs-lookup"><span data-stu-id="09d0d-329">REWIND &#124; NOREWIND</span></span>|<span data-ttu-id="09d0d-330">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-330">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-331">UNLOAD &#124; NOUNLOAD</span><span class="sxs-lookup"><span data-stu-id="09d0d-331">UNLOAD &#124; NOUNLOAD</span></span>|<span data-ttu-id="09d0d-332">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-332">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-333">KEEP_REPLICATION</span><span class="sxs-lookup"><span data-stu-id="09d0d-333">KEEP_REPLICATION</span></span>|<span data-ttu-id="09d0d-334">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-334">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-335">KEEP_CDC</span><span class="sxs-lookup"><span data-stu-id="09d0d-335">KEEP_CDC</span></span>|<span data-ttu-id="09d0d-336">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-336">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span><span class="sxs-lookup"><span data-stu-id="09d0d-337">ENABLE_BROKER &#124; ERROR_BROKER_CONVERSATIONS &#124; NEW_BROKER</span></span>|<span data-ttu-id="09d0d-338">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-338">&#x2713;</span></span>|||  
|<span data-ttu-id="09d0d-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span><span class="sxs-lookup"><span data-stu-id="09d0d-339">STOPAT &#124; STOPATMARK &#124; STOPBEFOREMARK</span></span>|<span data-ttu-id="09d0d-340">&#x2713;</span><span class="sxs-lookup"><span data-stu-id="09d0d-340">&#x2713;</span></span>|||  
  
 <span data-ttu-id="09d0d-341">Per altre informazioni sugli argomenti di ripristino, vedere [Argomenti dell'istruzione RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09d0d-341">For more information about Restore arguments, see [RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql).</span></span>  
  
##  <a name="using-backup-task-in-sql-server-management-studio"></a><a name="BackupTaskSSMS"></a><span data-ttu-id="09d0d-342">Utilizzo dell'attività di backup in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09d0d-342">Using Backup Task in SQL Server Management Studio</span></span>  
 <span data-ttu-id="09d0d-343">L'attività di backup in SQL Server Management Studio è stata migliorata per includere l'URL come una delle opzioni di destinazione e altri oggetti di supporto necessari per eseguire il backup in archiviazione di Azure come le credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="09d0d-343">The Backup task in SQL Server Management Studio has been enhanced to include URL as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span>  
  
 <span data-ttu-id="09d0d-344">I passaggi seguenti descrivono le modifiche apportate all'attività Backup database per consentire il backup in archiviazione di Azure.:</span><span class="sxs-lookup"><span data-stu-id="09d0d-344">The following steps describe the changes made to the Back Up Database task to allow for backing up to Azure storage.:</span></span>  
  
1.  <span data-ttu-id="09d0d-345">Avviare SQL Server Management Studio e connettersi all'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09d0d-345">Start SQL Server Management Studio and connect to the SQL Server instance.</span></span>  <span data-ttu-id="09d0d-346">Selezionare un database di cui si desidera eseguire il backup e fare clic con il pulsante destro del mouse su **attività**e selezionare **backup..**. Verrà visualizzata la finestra di dialogo Backup database.</span><span class="sxs-lookup"><span data-stu-id="09d0d-346">Select a database you want to backup, and right click on **Tasks**, and select **Back Up..**. This opens the Back Up Database dialog box.</span></span>  
  
2.  <span data-ttu-id="09d0d-347">Nella pagina generale viene usata l'opzione **URL** per creare un backup in archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-347">On the general page the **URL** option is used to create a backup to Azure storage.</span></span> <span data-ttu-id="09d0d-348">Quando si seleziona questa opzione, nella pagina verranno abilitate altre opzioni:</span><span class="sxs-lookup"><span data-stu-id="09d0d-348">When you select this option, you see other options enabled on this page:</span></span>  
  
    1.  <span data-ttu-id="09d0d-349">**Nome file:** nome del file di backup.</span><span class="sxs-lookup"><span data-stu-id="09d0d-349">**File Name:** Name of the backup file.</span></span>  
  
    2.  <span data-ttu-id="09d0d-350">**Credenziali SQL:** È possibile specificare una credenziale di SQL Server esistente o crearne una nuova facendo clic sul pulsante **Crea** accanto alla casella credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="09d0d-350">**SQL Credential:** You can either specify an existing SQL Server Credential, or can create a new one by clicking on the **Create** next to the SQL Credential box.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="09d0d-351">La finestra di dialogo visualizzata quando si fa clic su **Crea** richiede un certificato di gestione o il profilo di pubblicazione per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="09d0d-351">The dialog that opens when you click **Create** requires a management certificate or the publishing profile for the subscription.</span></span> <span data-ttu-id="09d0d-352">SQL Server supporta attualmente la versione del profilo di pubblicazione 2.0.</span><span class="sxs-lookup"><span data-stu-id="09d0d-352">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="09d0d-353">Per scaricare la versione supportata del profilo di pubblicazione, vedere [Download del profilo di pubblicazione 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="09d0d-353">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
        >   
        >  <span data-ttu-id="09d0d-354">Se non si dispone dell'accesso al certificato di gestione o al profilo di pubblicazione, è possibile creare le credenziali di SQL specificando il nome dell'account di archiviazione e le informazioni sulla chiave di accesso tramite Transact-SQL o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="09d0d-354">If you do not have access to the management certificate or publishing profile, you can create a SQL Credential by specifying the storage account name and access key information using Transact-SQL or SQL Server Management Studio.</span></span> <span data-ttu-id="09d0d-355">Vedere il codice di esempio nella sezione [Creare credenziali](#credential) per creare le credenziali tramite Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="09d0d-355">See the sample code in the [Create a Credential](#credential) section to create a credential using Transact-SQL.</span></span> <span data-ttu-id="09d0d-356">In alternativa, utilizzando SQL Server Management Studio, dall'istanza del motore di database, fare clic con il pulsante destro del mouse su **Sicurezza**, scegliere **Nuovo**e selezionare **Credenziale**.</span><span class="sxs-lookup"><span data-stu-id="09d0d-356">Alternatively, using SQL Server Management Studio, from the database engine instance, right click **Security**, select **New**, and select **Credential**.</span></span> <span data-ttu-id="09d0d-357">Specificare il nome dell'account di archiviazione per **Identity** e la chiave di accesso nel campo **Password** .</span><span class="sxs-lookup"><span data-stu-id="09d0d-357">Specify the storage account name for **Identity** and the access key in the **Password** field.</span></span>  
  
    3.  <span data-ttu-id="09d0d-358">**Contenitore di archiviazione di Azure:** Nome del contenitore di archiviazione di Azure in cui archiviare i file di backup.</span><span class="sxs-lookup"><span data-stu-id="09d0d-358">**Azure storage container:** The name of the Azure storage container to store the backup files.</span></span>  
  
    4.  <span data-ttu-id="09d0d-359">**Prefisso URL:** viene compilato automaticamente utilizzando le informazioni specificate nei campi descritti nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="09d0d-359">**URL prefix:** This is built automatically using the information specified in the fields described in the previous steps.</span></span> <span data-ttu-id="09d0d-360">Se si modifica questo valore manualmente, assicurarsi che corrisponda alle altre informazioni fornite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="09d0d-360">If you do edit this value manually, make sure it matches with the other information you provided previously.</span></span> <span data-ttu-id="09d0d-361">Se ad esempio si modifica l'URL di archiviazione, assicurarsi che le credenziali SQL siano impostate per l'autenticazione dello stesso account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="09d0d-361">For example if you modify the storage URL, make sure the SQL Credential is set to authenticate to the same storage account.</span></span>  
  
 <span data-ttu-id="09d0d-362">Quando si seleziona un URL come destinazione, alcune opzioni nella pagina **Opzioni supporti** vengono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="09d0d-362">When you select URL as the destination, certain options in the **Media Options** page are disabled.</span></span>  <span data-ttu-id="09d0d-363">Negli argomenti seguenti vengono fornite ulteriori informazioni sulla finestra di dialogo Backup database:</span><span class="sxs-lookup"><span data-stu-id="09d0d-363">The following topics have more information on the Back Up Database dialog:</span></span>  
  
 [<span data-ttu-id="09d0d-364">Backup database &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="09d0d-364">Back Up Database &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
 [<span data-ttu-id="09d0d-365">Back Up Database &#40;pagina Opzioni supporti&#41;</span><span class="sxs-lookup"><span data-stu-id="09d0d-365">Back Up Database &#40;Media Options Page&#41;</span></span>](back-up-database-media-options-page.md)  
  
 [<span data-ttu-id="09d0d-366">Backup database &#40;pagina Opzioni di backup&#41;</span><span class="sxs-lookup"><span data-stu-id="09d0d-366">Back Up Database &#40;Backup Options Page&#41;</span></span>](back-up-database-backup-options-page.md)  
  
 [<span data-ttu-id="09d0d-367">Creare le credenziali - Eseguire l'autenticazione nel servizio di archiviazione Azure</span><span class="sxs-lookup"><span data-stu-id="09d0d-367">Create Credential - Authenticate to Azure Storage</span></span>](create-credential-authenticate-to-azure-storage.md)  
  
##  <a name="sql-server-backup-to-url-using-maintenance-plan-wizard"></a><a name="MaintenanceWiz"></a><span data-ttu-id="09d0d-368">SQL Server backup nell'URL tramite la creazione guidata piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="09d0d-368">SQL Server Backup to URL Using Maintenance Plan Wizard</span></span>  
 <span data-ttu-id="09d0d-369">Analogamente all'attività di backup descritta in precedenza, la creazione guidata piano di manutenzione in SQL Server Management Studio è stata migliorata per includere l' **URL** come una delle opzioni di destinazione e altri oggetti di supporto necessari per eseguire il backup in archiviazione di Azure come le credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="09d0d-369">Similar to the backup task described previously, the Maintenance Plan Wizard in SQL Server Management Studio has been enhanced to include **URL** as one of the destination options, and other supporting objects required to backup to Azure storage like the SQL Credential.</span></span> <span data-ttu-id="09d0d-370">Per altre informazioni, vedere la sezione **Definire attività di backup** in [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span><span class="sxs-lookup"><span data-stu-id="09d0d-370">For more information, see  the **Define Backup Tasks** section in [Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure).</span></span>  
  
##  <a name="restoring-from-azure-storage-using-sql-server-management-studio"></a><a name="RestoreSSMS"></a><span data-ttu-id="09d0d-371">Ripristino da archiviazione di Azure tramite SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09d0d-371">Restoring from Azure storage Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="09d0d-372">Se si ripristina un database, l' **URL** viene incluso come dispositivo da cui eseguire il ripristino.</span><span class="sxs-lookup"><span data-stu-id="09d0d-372">If you are restoring a database, **URL** is included as the device to restore from.</span></span> <span data-ttu-id="09d0d-373">Nei passaggi seguenti vengono descritte le modifiche apportate all'attività di ripristino per consentire il ripristino da archiviazione di Azure:</span><span class="sxs-lookup"><span data-stu-id="09d0d-373">Following steps describe the changes in the Restore task to allow restoring from Azure storage:</span></span>  
  
1.  <span data-ttu-id="09d0d-374">Quando si seleziona **Dispositivi** nella pagina **Generale** dell'attività di ripristino in SQL Server Management Studio, viene visualizzata la finestra di dialogo **Seleziona dispositivi di backup** che include **URL** come tipo di supporti di backup.</span><span class="sxs-lookup"><span data-stu-id="09d0d-374">When you select **Devices** in the **General** page of the Restore task in SQL Server Management Studio, this takes you to the **Select backup devices** dialog box which includes **URL** as a backup media type.</span></span>  
  
2.  <span data-ttu-id="09d0d-375">Quando si seleziona **URL** e si fa clic su **Aggiungi**, viene visualizzata la finestra di dialogo **Connessione a Servizio di archiviazione Windows Azure** .</span><span class="sxs-lookup"><span data-stu-id="09d0d-375">When you select **URL** and click **Add**, this opens the **Connect to Azure storage** dialog.</span></span> <span data-ttu-id="09d0d-376">Specificare le informazioni sulle credenziali SQL per l'autenticazione in archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-376">Specify the SQL Credential information to authenticate to Azure storage.</span></span>  
  
3.  <span data-ttu-id="09d0d-377">SQL Server quindi si connette ad archiviazione di Azure usando le informazioni sulle credenziali SQL fornite e apre la finestra **di dialogo Individua file di backup in Azure** .</span><span class="sxs-lookup"><span data-stu-id="09d0d-377">SQL Server then connects to Azure storage using the SQL Credential information you provided and opens the **Locate Backup File in Azure** dialog.</span></span> <span data-ttu-id="09d0d-378">In questa pagina vengono visualizzati i file di backup che si trovano nello spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="09d0d-378">The backup files residing in the storage are displayed on this page.</span></span> <span data-ttu-id="09d0d-379">Selezionare il file che si desidera ripristinare, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="09d0d-379">Select the file you want to use to restore and click **OK**.</span></span> <span data-ttu-id="09d0d-380">Viene visualizzata di nuovo la finestra di dialogo **Seleziona dispositivi di backup** . Se si fa clic su **OK** in questa finestra di dialogo, viene visualizzata di nuovo la finestra di dialogo principale **Ripristina** in cui sarà possibile completare il ripristino.</span><span class="sxs-lookup"><span data-stu-id="09d0d-380">This takes you back to the **Select Backup Devices** dialog, and Clicking **OK** on this dialog takes you back to the main **Restore** dialog where you will be able complete the restore.</span></span>  <span data-ttu-id="09d0d-381">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="09d0d-381">For more information see, the following topics:</span></span>  
  
     [<span data-ttu-id="09d0d-382">Ripristina database &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="09d0d-382">Restore Database &#40;General Page&#41;</span></span>](restore-database-general-page.md)  
  
     [<span data-ttu-id="09d0d-383">Ripristina database &#40;pagina File&#41;</span><span class="sxs-lookup"><span data-stu-id="09d0d-383">Restore Database &#40;Files Page&#41;</span></span>](restore-database-files-page.md)  
  
     [<span data-ttu-id="09d0d-384">Ripristina database &#40;pagina Opzioni&#41;</span><span class="sxs-lookup"><span data-stu-id="09d0d-384">Restore Database &#40;Options Page&#41;</span></span>](restore-database-options-page.md)  
  
##  <a name="code-examples"></a><a name="Examples"></a> <span data-ttu-id="09d0d-385">Esempi di codice</span><span class="sxs-lookup"><span data-stu-id="09d0d-385">Code Examples</span></span>  
 <span data-ttu-id="09d0d-386">In questa sezione sono disponibili gli esempi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="09d0d-386">This section contains the following examples.</span></span>  
  
-   [<span data-ttu-id="09d0d-387">Creare credenziali</span><span class="sxs-lookup"><span data-stu-id="09d0d-387">Create a Credential</span></span>](#credential)  
  
-   [<span data-ttu-id="09d0d-388">Backup di un database completo</span><span class="sxs-lookup"><span data-stu-id="09d0d-388">Backing up a complete database</span></span>](#complete)  
  
-   [<span data-ttu-id="09d0d-389">Backup del database e del log</span><span class="sxs-lookup"><span data-stu-id="09d0d-389">Backing up the database and log</span></span>](#databaselog)  
  
-   [<span data-ttu-id="09d0d-390">Creazione di un backup di file completo del filegroup primario</span><span class="sxs-lookup"><span data-stu-id="09d0d-390">Creating a full file backup of the primary filegroup</span></span>](#filebackup)  
  
-   [<span data-ttu-id="09d0d-391">Creazione di un backup di file differenziale dei filegroup primari</span><span class="sxs-lookup"><span data-stu-id="09d0d-391">Creating a differential file backup of the primary filegroups</span></span>](#differential)  
  
-   [<span data-ttu-id="09d0d-392">Ripristino di un database e spostamento dei file</span><span class="sxs-lookup"><span data-stu-id="09d0d-392">Restoring a database and move files</span></span>](#restoredbwithmove)  
  
-   [<span data-ttu-id="09d0d-393">Ripristino temporizzato tramite STOPAT</span><span class="sxs-lookup"><span data-stu-id="09d0d-393">Restoring to a point-in-time using STOPAT</span></span>](#PITR)  
  
###  <a name="create-a-credential"></a><a name="credential"></a> <span data-ttu-id="09d0d-394">Creare credenziali</span><span class="sxs-lookup"><span data-stu-id="09d0d-394">Create a Credential</span></span>  
 <span data-ttu-id="09d0d-395">L'esempio seguente crea una credenziale che archivia le informazioni di autenticazione di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-395">The following example creates a credential that stores the Azure Storage authentication information.</span></span>  

   ```sql
   IF NOT EXISTS  
   (SELECT * FROM sys.credentials   
   WHERE credential_identity = 'mycredential')  
   CREATE CREDENTIAL mycredential WITH IDENTITY = 'mystorageaccount'  
   ,SECRET = '<storage access key>' ;  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
   string secret = "<storage access key>";  
  
   // Create a Credential  
   string credentialName = "mycredential";  
   Credential credential = new Credential(server, credentialName);  
   credential.Create(identity, secret);  
   ```  
  
   ```powershell
   # create variables  
   $storageAccount = "mystorageaccount"  
   $storageKey = "<storage access key>"  
   $secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
   $credentialName = "mycredential"  
  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Create a credential  
   New-SqlCredential -Name $credentialName -Path $srvpath -Identity $storageAccount -Secret $secureString
   ```  
  
###  <a name="backing-up-a-complete-database"></a><a name="complete"></a><span data-ttu-id="09d0d-396">Esecuzione del backup di un database completo</span><span class="sxs-lookup"><span data-stu-id="09d0d-396">Backing up a complete database</span></span>  
 <span data-ttu-id="09d0d-397">Nell'esempio seguente viene eseguito il backup del database AdventureWorks2012 nel servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="09d0d-397">The following example backs up the AdventureWorks2012 database to the Azure Blob storage service.</span></span>
  
   ```sql
   BACKUP DATABASE AdventureWorks2012   
   TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
         WITH CREDENTIAL = 'mycredential'   
         ,COMPRESSION  
         ,STATS = 5;  
   GO
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);  
   ```
  
   ```powershell
   # create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"   
   # for default instance, the $srvpath varilable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance  
   CD $srvPath   
   $backupFile = $backupUrlContainer + "AdventureWorks2012" +  ".bak"  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On
   ```  
  
###  <a name="backing-up-the-database-and-log"></a><a name="databaselog"></a><span data-ttu-id="09d0d-398">Backup del database e del log</span><span class="sxs-lookup"><span data-stu-id="09d0d-398">Backing up the database and log</span></span>  
 <span data-ttu-id="09d0d-399">Nell'esempio riportato di seguito viene eseguito il backup del database di esempio AdventureWorks2012 per il quale viene utilizzato, per impostazione predefinita, il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="09d0d-399">The following example backups up the AdventureWorks2012 sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="09d0d-400">Per consentire il backup del log, il database AdventureWorks2012 viene modificato per l'utilizzo del modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="09d0d-400">To support log backups, the AdventureWorks2012 database is modified to use the full recovery model.</span></span> <span data-ttu-id="09d0d-401">Nell'esempio viene quindi creato un backup completo del database nel BLOB di Azure e, dopo un periodo di attività di aggiornamento, viene eseguito il backup del log.</span><span class="sxs-lookup"><span data-stu-id="09d0d-401">The example then creates a full database backup to Azure Blob, and after a period of update activity, backs up the log.</span></span> <span data-ttu-id="09d0d-402">In questo esempio viene creato il nome di un file di backup con un indicatore datetime.</span><span class="sxs-lookup"><span data-stu-id="09d0d-402">This example creates a backup file name with a datetime stamp.</span></span>  
  
   ```sql
   -- To permit log backups, before the full database backup, modify the database   
   -- to use the full recovery model.  
   USE master;  
   GO  
   ALTER DATABASE AdventureWorks2012  
      SET RECOVERY FULL;  
   GO  
  
   -- Back up the full AdventureWorks2012 database.  
          -- First create a file name for the backup file with DateTime stamp  
  
   DECLARE @Full_Filename AS VARCHAR (300);  
   SET @Full_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Full_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.bak';   
   --Back up Adventureworks2012 database  
  
   BACKUP DATABASE AdventureWorks2012  
   TO URL =  @Full_Filename  
   WITH CREDENTIAL = 'mycredential';  
   ,COMPRESSION  
   GO  
   -- Back up the AdventureWorks2012 log.  
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url for data backup  
   string urlDataBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Data-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database to Url  
   Backup backupData = new Backup();  
   backupData.CredentialName = credentialName;  
   backupData.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupData.Devices.AddDevice(urlDataBackup, DeviceType.Url);  
   backupData.SqlBackup(server);  
  
   // Generate Unique Url for data backup  
   string urlLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}_Log-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Database Log to Url  
   Backup backupLog = new Backup();  
   backupLog.CredentialName = credentialName;  
   backupLog.Database = dbName;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backupLog.Devices.AddDevice(urlLogBackup, DeviceType.Url);  
   backupLog.Action = BackupActionType.Log;  
   backupLog.SqlBackup(server);  
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to theSQL Server Instance
   CD $srvPath   
   #Create a unique file name for the full database backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Backup Database to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Database    
  
   #Create a unique file name for log backup  
  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup Log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Log
   ```  
  
###  <a name="creating-a-full-file-backup-of-the-primary-filegroup"></a><a name="filebackup"></a><span data-ttu-id="09d0d-403">Creazione di un backup completo del filegroup primario</span><span class="sxs-lookup"><span data-stu-id="09d0d-403">Creating a full file backup of the primary filegroup</span></span>  
 <span data-ttu-id="09d0d-404">Nell'esempio seguente viene creato un backup di file completo del filegroup primario.</span><span class="sxs-lookup"><span data-stu-id="09d0d-404">The following example creates a full file backup of the primary filegroup.</span></span>
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012files.bck'  
       WITH CREDENTIAL = 'mycredential'  
       ,COMPRESSION;  
   GO  
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bck",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to the SQL Server Instance  
  
   CD $srvPath   
   #Create a unique file name for the file backup  
   $backupFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bck"  
  
   #Backup Primary File Group to URL  
  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary
   ```  
  
###  <a name="creating-a-differential-file-backup-of-the-primary-filegroup"></a><a name="differential"></a><span data-ttu-id="09d0d-405">Creazione di un backup differenziale del filegroup primario</span><span class="sxs-lookup"><span data-stu-id="09d0d-405">Creating a differential file backup of the primary filegroup</span></span>  
 <span data-ttu-id="09d0d-406">Nell'esempio seguente viene creato un backup di file differenziale del filegroup primario.</span><span class="sxs-lookup"><span data-stu-id="09d0d-406">The following example creates a differential file backup of the primary filegroup.</span></span>  
  
   ```sql
   --Back up the files in Primary:  
   BACKUP DATABASE AdventureWorks2012  
       FILEGROUP = 'Primary'  
       TO URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012filesdiff.bck'  
       WITH   
          CREDENTIAL = 'mycredential'  
          ,COMPRESSION  
      ,DIFFERENTIAL;  
   GO
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string url = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Action = BackupActionType.Files;  
   backup.DatabaseFileGroups.Add("PRIMARY");  
   backup.Incremental = true;  
   backup.CompressionOption = BackupCompressionOptions.On;  
   backup.Devices.AddDevice(url, DeviceType.Url);  
   backup.SqlBackup(server); 
   ```

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   #Create a differential backup of the primary filegroup
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName -CompressionOption On -BackupAction Files -DatabaseFileGroup Primary -Incremental
   ```  
  
###  <a name="restore-a-database-and-move-files"></a><a name="restoredbwithmove"></a><span data-ttu-id="09d0d-407">Ripristinare un database e spostare i file</span><span class="sxs-lookup"><span data-stu-id="09d0d-407">Restore a database and move files</span></span>  
 <span data-ttu-id="09d0d-408">Per ripristinare un backup completo del database e spostare il database ripristinato nella directory C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data, attenersi ai passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="09d0d-408">To restore a full database backup and move the restored database to C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data directory, use the following steps.</span></span>
  
   ```sql
   -- Backup the tail of the log first
   DECLARE @Log_Filename AS VARCHAR (300);  
   SET @Log_Filename = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012_Log_'+   
   REPLACE (REPLACE (REPLACE (CONVERT (VARCHAR (40), GETDATE (), 120), '-','_'),':', '_'),' ', '_') + '.trn';  
   BACKUP LOG AdventureWorks2012  
    TO URL = @Log_Filename  
    WITH CREDENTIAL = 'mycredential'  
    ,NORECOVERY;  
   GO  
  
   RESTORE DATABASE AdventureWorks2012 FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'  
   WITH CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,MOVE 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,STATS = 5
   ```
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for tail log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath  + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName+ "_Log", newLogFilePath));  
   restore.SqlRestore(server);
   ```  

   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTNACENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # navigate to SQL Server Instance
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On      
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery    
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath)
   ```  
  
###  <a name="restoring-to-a-point-in-time-using-stopat"></a><a name="PITR"></a> <span data-ttu-id="09d0d-409">Ripristino temporizzato tramite STOPAT</span><span class="sxs-lookup"><span data-stu-id="09d0d-409">Restoring to a point-in-time using STOPAT</span></span>  
 <span data-ttu-id="09d0d-410">Nell'esempio seguente viene ripristinato lo stato di un database in un momento preciso e viene illustrata un'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="09d0d-410">The following example restores a database to its state to a point in time, and shows a restore operation.</span></span>  
  
   ```sql
   RESTORE DATABASE AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.bak'   
   WITH   
     CREDENTIAL = 'mycredential'  
    ,MOVE 'AdventureWorks2012_data' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf'  
    ,Move 'AdventureWorks2012_log' to 'C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf'  
    ,NORECOVERY  
    --,REPLACE  
    ,STATS = 5;  
   GO   
  
   RESTORE LOG AdventureWorks FROM URL = 'https://mystorageaccount.blob.core.windows.net/mycontainer/AdventureWorks2012.trn'   
   WITH CREDENTIAL = 'mycredential'  
    ,RECOVERY   
    ,STOPAT = 'Oct 23, 2012 5:00 PM'   
   GO  
   ```  
  
   ```csharp
   // Connect to default sql server instance on local machine  
   Server server = new Server(".");  
   string identity = "mystorageaccount";  
  
   string credentialName = "mycredential";  
   string dbName = "AdventureWorks2012";  
   string blobContainerName = "mycontainer";  
  
   // Generate Unique Url  
   string urlBackupData = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-Data{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup to Url  
   Backup backup = new Backup();  
   backup.CredentialName = credentialName;  
   backup.Database = dbName;  
   backup.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   backup.SqlBackup(server);  
  
   // Generate Unique Url for Tail Log backup  
   string urlTailLogBackup = String.Format(@"https://{0}.blob.core.windows.net/{1}/{2}-TailLog{3}.bak",  
            identity,  
            blobContainerName,  
            dbName,  
            DateTime.Now.ToString("s").Replace(":", "-"));  
  
   // Backup Tail Log to Url  
   Backup backupTailLog = new Backup();  
   backupTailLog.CredentialName = credentialName;  
   backupTailLog.Database = dbName;  
   backupTailLog.Action = BackupActionType.Log;  
   backupTailLog.NoRecovery = true;  
   backupTailLog.Devices.AddDevice(urlTailLogBackup, DeviceType.Url);  
   backupTailLog.SqlBackup(server);  
  
   // Restore a database and move files  
   string newDataFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".mdf";  
   string newLogFilePath = server.MasterDBLogPath + @"\" + dbName + DateTime.Now.ToString("s").Replace(":", "-") + ".ldf";  
  
   Restore restore = new Restore();  
   restore.CredentialName = credentialName;  
   restore.Database = dbName;  
   restore.ReplaceDatabase = true;  
   restore.NoRecovery = true;  
   restore.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restore.RelocateFiles.Add(new RelocateFile(dbName, newDataFilePath));  
   restore.RelocateFiles.Add(new RelocateFile(dbName + "_Log", newLogFilePath));  
   restore.SqlRestore(server);  
      
   // Restore transaction Log with stop at   
   Restore restoreLog = new Restore();  
   restoreLog.CredentialName = credentialName;  
   restoreLog.Database = dbName;  
   restoreLog.Action = RestoreActionType.Log;  
   restoreLog.Devices.AddDevice(urlBackupData, DeviceType.Url);  
   restoreLog.ToPointInTime = DateTime.Now.ToString();   
   restoreLog.SqlRestore(server);
   ```
  
   ```powershell
   #create variables  
   $backupUrlContainer = "https://mystorageaccount.blob.core.windows.net/mycontainer/"  
   $credentialName = "mycredential"  
   $srvPath = "SQLSERVER:\SQL\COMPUTERNAME\INSTANCENAME"  
   # for default instance, the $srvpath variable would be "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
  
   # Navigate to SQL Server Instance Directory
   CD $srvPath   
  
   #create a unique file name for the full backup  
   $backupdbFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".bak"  
  
   # Full database backup to URL  
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupdbFile  -SqlCredential $credentialName -CompressionOption On     
  
   #Create a unique file name for the tail log backup  
   $backuplogFile = $backupUrlContainer + "AdventureWorks2012_" + (Get-Date).ToString("s").Replace("-","_").Replace(":", "_").Replace(" ","_").Replace("/", "_") +  ".trn"  
  
   #Backup tail log to URL
   Backup-SqlDatabase -Database AdventureWorks2012 -backupFile $backupFile  -SqlCredential $credentialName  -BackupAction Log -NoRecovery     
  
   # Restore Database and move files
   $newDataFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile ("AdventureWorks_Data","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.mdf")  
   $newLogFilePath = New-Object Microsoft.SqlServer.Management.Smo.RelocateFile("AdventureWorks_Log","C:\Program Files\Microsoft SQL Server\myinstance\MSSQL\DATA\AdventureWorks2012.ldf")  
  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backupdbFile -RelocateFile @($newDataFilePath,$newLogFilePath) -NoRecovery    
  
   # Restore Transaction log with Stop At:  
   Restore-SqlDatabase -Database AdventureWorks2012 -SqlCredential $credentialName -BackupFile $backuplogFile  -ToPointInTime (Get-Date).ToString()
   ```  
  
## <a name="see-also"></a><span data-ttu-id="09d0d-411">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09d0d-411">See Also</span></span>  
 <span data-ttu-id="09d0d-412">[Procedure consigliate e risoluzione dei problemi per il backup di SQL Server nell'URL](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="09d0d-412">[SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md) </span></span>  
 [<span data-ttu-id="09d0d-413">Backup e ripristino di database di sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="09d0d-413">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](back-up-and-restore-of-system-databases-sql-server.md)   
