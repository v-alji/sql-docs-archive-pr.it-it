---
title: Eliminazione dei file BLOB di backup con lease attivi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 13a8f879-274f-4934-a722-b4677fc9a782
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02aea910589633a5c3ec79e283c757727b4d92cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627842"
---
# <a name="deleting-backup-blob-files-with-active-leases"></a><span data-ttu-id="eee71-102">Eliminazione dei file BLOB di backup con lease attivi</span><span class="sxs-lookup"><span data-stu-id="eee71-102">Deleting Backup Blob Files with Active Leases</span></span>
  <span data-ttu-id="eee71-103">Quando si esegue il backup o il ripristino da archiviazione di Azure, SQL Server acquisisce un lease infinito per bloccare l'accesso esclusivo al BLOB.</span><span class="sxs-lookup"><span data-stu-id="eee71-103">When backing up to or restoring from Azure storage, SQL Server acquires an infinite lease in order to lock exclusive access to the blob.</span></span> <span data-ttu-id="eee71-104">Quando il processo di backup o ripristino viene completato correttamente, il lease viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="eee71-104">When the backup or restore process is successfully completed, the lease is released.</span></span> <span data-ttu-id="eee71-105">Se il backup o il ripristino non viene completato, il processo di backup tenta di eliminare i BLOB non validi.</span><span class="sxs-lookup"><span data-stu-id="eee71-105">If a backup or restore fails, the backup process attempts to clean up any invalid blob.</span></span> <span data-ttu-id="eee71-106">Tuttavia, se il backup non viene completato a causa di un problema di connettività di rete che persiste nel tempo, è possibile che il processo di backup non sia in grado di accedere al BLOB e che quindi quest'ultimo rimanga orfano.</span><span class="sxs-lookup"><span data-stu-id="eee71-106">However, if the backup fails due to prolonged or sustained network connectivity failure, the backup  process may not be able gain access to the blob and the blob may remain orphaned.</span></span> <span data-ttu-id="eee71-107">Di conseguenza, il BLOB non può essere scritto o eliminato finché il lease non viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="eee71-107">This means that the blob cannot be written to or deleted until the lease is released.</span></span> <span data-ttu-id="eee71-108">In questo argomento viene descritto come rilasciare il lease ed eliminare il BLOB.</span><span class="sxs-lookup"><span data-stu-id="eee71-108">This topic describes how to release the lease and deleting the blob..</span></span>  
  
 <span data-ttu-id="eee71-109">Per altre informazioni sui tipi di lease, leggere questo [articolo](https://go.microsoft.com/fwlink/?LinkId=275664).</span><span class="sxs-lookup"><span data-stu-id="eee71-109">For more information on the types of leases, read this [article](https://go.microsoft.com/fwlink/?LinkId=275664).</span></span>  
  
 <span data-ttu-id="eee71-110">Il mancato completamento dell'operazione di backup potrebbe generare un file di backup non valido.</span><span class="sxs-lookup"><span data-stu-id="eee71-110">If the backup operation fails, it can result in a backup file that is not valid.</span></span>  <span data-ttu-id="eee71-111">Anche nel file BLOB di backup potrebbe essere presente un lease attivo, impedendone l'eliminazione o la sovrascrittura.</span><span class="sxs-lookup"><span data-stu-id="eee71-111">The backup blob file might also have an active lease, preventing it from being deleted or overwritten.</span></span>  <span data-ttu-id="eee71-112">Per eliminare o sovrascrivere questi BLOB, è innanzitutto necessario interrompere il lease. Se si verificano errori di backup, è consigliabile rimuovere i lease ed eliminare i BLOB.</span><span class="sxs-lookup"><span data-stu-id="eee71-112">In order to delete or overwrite such blobs, the lease should first be broken.If there are backup failures, we recommend that you clean up leases and delete blobs.</span></span> <span data-ttu-id="eee71-113">È inoltre possibile scegliere di effettuare rimozioni periodiche come parte delle attività di gestione della memoria.</span><span class="sxs-lookup"><span data-stu-id="eee71-113">You can also choose cleanup periodically as part of storage management tasks.</span></span>  
  
 <span data-ttu-id="eee71-114">Se si verifica un errore di ripristino, i ripristini successivi non vengono bloccati e pertanto il lease attivo potrebbe non essere un problema.</span><span class="sxs-lookup"><span data-stu-id="eee71-114">If there is a restore failure, subsequent restores are not blocked, and therefore the active lease may not be an issue.</span></span> <span data-ttu-id="eee71-115">L'interruzione del lease è necessaria solo quando si deve sovrascrivere o eliminare il BLOB.</span><span class="sxs-lookup"><span data-stu-id="eee71-115">Breaking the lease is only necessary when you have to overwrite or delete the blob.</span></span>  
  
## <a name="managing-orphaned-blobs"></a><span data-ttu-id="eee71-116">Gestione dei BLOB orfani</span><span class="sxs-lookup"><span data-stu-id="eee71-116">Managing Orphaned Blobs</span></span>  
 <span data-ttu-id="eee71-117">Nei passaggi seguenti viene descritto come effettuare una rimozione dopo un backup non riuscito o un'attività di ripristino.</span><span class="sxs-lookup"><span data-stu-id="eee71-117">The follow steps describe how to clean up after failed backup or restore activity.</span></span> <span data-ttu-id="eee71-118">Tutti i passaggi possono essere effettuati utilizzando gli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eee71-118">All the steps can be done using PowerShell scripts.</span></span> <span data-ttu-id="eee71-119">Nella sezione seguente è disponibile un esempio di codice:</span><span class="sxs-lookup"><span data-stu-id="eee71-119">A code example is provided in the following section:</span></span>  
  
1.  <span data-ttu-id="eee71-120">**Identificazione di BLOB con lease:** se si dispone di uno script o un processo in cui vengono eseguiti i processi di backup, è possibile rilevare l'errore nello script o nel processo e usarlo per rimuovere i BLOB.</span><span class="sxs-lookup"><span data-stu-id="eee71-120">**Identifying blobs that have leases:** If you have a script or a process that runs the backup processes, you might be able to capture the failure within the script or process and use that to clean up the blobs.</span></span>   <span data-ttu-id="eee71-121">È inoltre possibile utilizzare le proprietà LeastState e LeaseStats per identificare i BLOB con lease.</span><span class="sxs-lookup"><span data-stu-id="eee71-121">You can also use the LeaseStats and LeastState properties to identify the blobs that have leases on them.</span></span> <span data-ttu-id="eee71-122">Dopo aver identificato i BLOB, è consigliabile rivedere l'elenco e verificare la validità del file di backup prima di eliminare il BLOB.</span><span class="sxs-lookup"><span data-stu-id="eee71-122">Once you have identified the blobs, we recommend that you review the list, verify the validity of the backup file before deleting the blob.</span></span>  
  
2.  <span data-ttu-id="eee71-123">**Interruzione del lease:** tramite una richiesta autorizzata è possibile interrompere il lease senza specificare un relativo ID.</span><span class="sxs-lookup"><span data-stu-id="eee71-123">**Breaking the lease:** An authorized request can break the lease without supplying a lease ID.</span></span> <span data-ttu-id="eee71-124">Per altre informazioni, fare clic [qui](https://go.microsoft.com/fwlink/?LinkID=275664) .</span><span class="sxs-lookup"><span data-stu-id="eee71-124">See [here](https://go.microsoft.com/fwlink/?LinkID=275664) for more information.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="eee71-125">Tramite SQL Server viene generato un ID lease per stabilire l'accesso esclusivo durante l'operazione di ripristino.</span><span class="sxs-lookup"><span data-stu-id="eee71-125">SQL Server issues a lease ID to establish exclusive access during the restore operation.</span></span> <span data-ttu-id="eee71-126">L'ID lease di ripristino è BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span><span class="sxs-lookup"><span data-stu-id="eee71-126">The restore lease ID is BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2.</span></span>  
  
3.  <span data-ttu-id="eee71-127">**Eliminazione del BLOB:** per eliminare un BLOB con un lease attivo è innanzitutto necessario interrompere il lease.</span><span class="sxs-lookup"><span data-stu-id="eee71-127">**Deleting the Blob:** To delete a blob that has an active lease, you must first break the lease.</span></span>  
  
###  <a name="powershell-script-example"></a><a name="Code_Example"></a><span data-ttu-id="eee71-128">Esempio di script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee71-128">PowerShell Script Example</span></span>  
 <span data-ttu-id="eee71-129">Importante se si esegue PowerShell 2,0, è possibile che si verifichino problemi durante il caricamento dell'assembly di Microsoft WindowsAzure.Storage.dll. \*\* \* \* \* \* \*\*</span><span class="sxs-lookup"><span data-stu-id="eee71-129">**\*\* Important \*\*** If you are running PowerShell 2.0, you may have problems loading the Microsoft WindowsAzure.Storage.dll assembly.</span></span> <span data-ttu-id="eee71-130">È consigliabile effettuare l'aggiornamento a Powershell 3.0 per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="eee71-130">We recommend that you upgrade to Powershell 3.0 to solve the issue.</span></span> <span data-ttu-id="eee71-131">È inoltre possibile utilizzare la soluzione alternativa per PowerShell 2.0:</span><span class="sxs-lookup"><span data-stu-id="eee71-131">You may also use the following workaround for PowerShell 2.0:</span></span>  
  
-   <span data-ttu-id="eee71-132">Creare o modificare il file powershell.exe.config per caricare gli assembly .NET 2.0 e .NET 4.0 in fase di esecuzione con quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="eee71-132">Create or modify the powershell.exe.config file to load .NET 2.0 and .NET 4.0 assemblies at runtime with the following:</span></span>  
  
    ```xml
    <?xml version="1.0"?>
    <configuration>
        <startup useLegacyV2RuntimeActivationPolicy="true">
            <supportedRuntime version="v4.0.30319"/>
            <supportedRuntime version="v2.0.50727"/>
        </startup>
    </configuration>
    ```  
  
 <span data-ttu-id="eee71-133">Nell'esempio seguente vengono illustrate l'identificazione dei BLOB con lease attivi e la relativa interruzione.</span><span class="sxs-lookup"><span data-stu-id="eee71-133">The following example illustrates identifying blobs that have active leases and then breaking them.</span></span> <span data-ttu-id="eee71-134">Nell'esempio viene anche descritto come applicare i filtri per gli ID lease di rilascio.</span><span class="sxs-lookup"><span data-stu-id="eee71-134">The example also demonstrates how filter for release lease IDs.</span></span>  
  
 <span data-ttu-id="eee71-135">Suggerimenti per l'esecuzione di questo script</span><span class="sxs-lookup"><span data-stu-id="eee71-135">Tips on running this script</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="eee71-136">Se un backup nel servizio di archiviazione BLOB di Azure è in esecuzione contemporaneamente a questo script, il backup può avere esito negativo perché questo script interrompe il lease che il backup sta tentando di acquisire nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="eee71-136">If a backup to Azure Blob storage service is running at the same time as this script, the backup can fail since this script will break the lease that the backup is trying to acquire at the same time.</span></span> <span data-ttu-id="eee71-137">È consigliabile eseguire questo script durante un periodo di manutenzione o quando non sono previste esecuzioni di backup.</span><span class="sxs-lookup"><span data-stu-id="eee71-137">We recommend running this script during a maintenance windows or when no backups are expected to run.</span></span>  
  
1.  <span data-ttu-id="eee71-138">Quando si esegue questo script, verrà richiesto di specificare i valori per l'account di archiviazione, la chiave di archiviazione, il contenitore e i parametri del percorso e del nome dell'assembly di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="eee71-138">When you run this script, you will be prompted to provide values for the storage account, storage key, container, and the Azure storage assembly path and name parameters.</span></span> <span data-ttu-id="eee71-139">Il percorso dell'assembly di archiviazione è la directory di installazione dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eee71-139">The path of the storage is assembly is the installation directory of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eee71-140">Il nome del file per l'assembly di archiviazione è Microsoft.WindowsAzure.Storage.dll.</span><span class="sxs-lookup"><span data-stu-id="eee71-140">The file name for the storage assembly is Microsoft.WindowsAzure.Storage.dll.</span></span> <span data-ttu-id="eee71-141">Di seguito è riportato un esempio delle richieste e dei valori immessi:</span><span class="sxs-lookup"><span data-stu-id="eee71-141">Following is an example of the prompts and values entered:</span></span>  
  
    ```  
    cmdlet  at command pipeline position 1  
    Supply values for the following parameters:  
    storageAccount: mycloudstorageaccount  
    storageKey: 0BopKY7eEha3gBnistYk+904nf  
    blobContainer: mycontainer   
    storageAssemblyPath: C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Microsoft.WindowsAzure.Storage.dll  
    ```  
  
2.  <span data-ttu-id="eee71-142">Se non è presente alcun BLOB con lease bloccati, dovrebbe essere visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="eee71-142">If there are no blobs that have locked leases you should see the following message:</span></span>  
  
     <span data-ttu-id="eee71-143">**Nessun BLOB con stato lease bloccato**</span><span class="sxs-lookup"><span data-stu-id="eee71-143">**There are no blobs with locked lease status**</span></span>  
  
     <span data-ttu-id="eee71-144">Se sono presenti BLOB con lease bloccati, dovrebbero essere visualizzati i messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="eee71-144">If there are blobs with locked leases, you should see the following messages:</span></span>  
  
     <span data-ttu-id="eee71-145">**Interruzione lease**</span><span class="sxs-lookup"><span data-stu-id="eee71-145">**Breaking Leases**</span></span>  
  
     <span data-ttu-id="eee71-146">**Il lease in \<URL of the Blob> è un lease di ripristino: questo messaggio verrà visualizzato solo se è presente un BLOB con un lease di ripristino ancora attivo.**</span><span class="sxs-lookup"><span data-stu-id="eee71-146">**The lease on \<URL of the Blob> is a restore lease: You will see this message only if you have a blob with a restore lease that is still active.**</span></span>  
  
     <span data-ttu-id="eee71-147">**Il lease on \<URL of the Blob> non è un lease di ripristino in cui si interrompe il lease \<URL of the Bob> .**</span><span class="sxs-lookup"><span data-stu-id="eee71-147">**The lease on \<URL of the Blob> is not a restore lease Breaking lease on \<URL of the Bob>.**</span></span>  
  
```powershell
param(  
       [Parameter(Mandatory=$true)]  
       [string]$storageAccount,  
       [Parameter(Mandatory=$true)]  
       [string]$storageKey,  
       [Parameter(Mandatory=$true)]  
       [string]$blobContainer,  
       [Parameter(Mandatory=$true)]  
       [string]$storageAssemblyPath  
)  
  
# Well known Restore Lease ID  
$restoreLeaseId = "BAC2BAC2BAC2BAC2BAC2BAC2BAC2BAC2"  
  
# Load the storage assembly without locking the file for the duration of the PowerShell session  
$bytes = [System.IO.File]::ReadAllBytes($storageAssemblyPath)  
[System.Reflection.Assembly]::Load($bytes)  
  
$cred = New-Object 'Microsoft.WindowsAzure.Storage.Auth.StorageCredentials' $storageAccount, $storageKey  
$client = New-Object 'Microsoft.WindowsAzure.Storage.Blob.CloudBlobClient' "https://$storageAccount.blob.core.windows.net", $cred  
$container = $client.GetContainerReference($blobContainer)  
  
#list all the blobs  
$allBlobs = $container.ListBlobs()
  
$lockedBlobs = @()  
# filter blobs that are have Lease Status as "locked"  
foreach($blob in $allBlobs)  
{  
    $blobProperties = $blob.Properties
    if($blobProperties.LeaseStatus -eq "Locked")  
    {  
        $lockedBlobs += $blob  
    }  
}  
  
if ($lockedBlobs.Count -eq 0)  
{
    Write-Host " There are no blobs with locked lease status"  
}

if($lockedBlobs.Count -gt 0)  
{  
    Write-Host "Breaking leases"  
    foreach($blob in $lockedBlobs )
    {  
        try  
        {  
            $blob.AcquireLease($null, $restoreLeaseId, $null, $null, $null)  
            Write-Host "The lease on $($blob.Uri) is a restore lease"  
        }  
        catch [Microsoft.WindowsAzure.Storage.StorageException]  
        {  
            if($_.Exception.RequestInformation.HttpStatusCode -eq 409)  
            {  
                Write-Host "The lease on $($blob.Uri) is not a restore lease"  
            }  
        }  
  
        Write-Host "Breaking lease on $($blob.Uri)"  
        $blob.BreakLease($(New-TimeSpan), $null, $null, $null) | Out-Null  
    }  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="eee71-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eee71-148">See Also</span></span>  
 [<span data-ttu-id="eee71-149">Procedure consigliate e risoluzione dei problemi per il backup di SQL Server nell'URL</span><span class="sxs-lookup"><span data-stu-id="eee71-149">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
