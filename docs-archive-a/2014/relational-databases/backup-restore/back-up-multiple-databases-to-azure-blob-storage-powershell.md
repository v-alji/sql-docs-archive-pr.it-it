---
title: Usare PowerShell per eseguire il backup di più database nel servizio di archiviazione BLOB di Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: f7008339-e69d-4e20-9265-d649da670460
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95da5d0009f88943029e62960e7429b292242bbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629444"
---
# <a name="use-powershell-to-backup-multiple-databases-to-azure-blob-storage-service"></a><span data-ttu-id="06731-102">Usare PowerShell per il backup di più database nel servizio Archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="06731-102">Use PowerShell to Backup Multiple Databases to Azure Blob Storage Service</span></span>
  <span data-ttu-id="06731-103">In questo argomento vengono illustrati alcuni script di esempio che possono essere usati per automatizzare i backup nel servizio Archiviazione BLOB di Azure tramite i cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06731-103">This topic provides sample scripts that can be used to automate backups to Azure Blob storage service using PowerShell cmdlets.</span></span>  
  
## <a name="overview-of-powershell-cmdlets-for-backup-and-restore"></a><span data-ttu-id="06731-104">Panoramica dei cmdlet di PowerShell per il backup e il ripristino</span><span class="sxs-lookup"><span data-stu-id="06731-104">Overview of PowerShell cmdlets for Backup and Restore</span></span>  
 <span data-ttu-id="06731-105">`Backup-SqlDatabase` e `Restore-SqlDatabase` sono i due principali cmdlet disponibili per eseguire le operazioni di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="06731-105">The `Backup-SqlDatabase` and `Restore-SqlDatabase` are the two main cmdlets available to do backup and restore operations.</span></span> <span data-ttu-id="06731-106">Esistono anche altri cmdlet che possono essere necessari per automatizzare i backup nel servizio di archiviazione BLOB di Azure, ad esempio il set di cmdlet **SqlCredential**. Di seguito è riportato un elenco di cmdlet di PowerShell disponibili in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usati nelle operazioni di backup e ripristino:</span><span class="sxs-lookup"><span data-stu-id="06731-106">In addition, there are other cmdlets that may be required to automate backups to Azure Blob storage like the set of **SqlCredential** cmdlets  Following is a list of PowerShell cmdlets available in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that are used in backup and restore operations:</span></span>  
  
 <span data-ttu-id="06731-107">Backup-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="06731-107">Backup-SqlDatabase</span></span>  
 <span data-ttu-id="06731-108">Questo cmdlet viene utilizzato per creare un backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="06731-108">This cmdlet is used to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Backup.</span></span>  
  
 <span data-ttu-id="06731-109">Restore-SqlDatabase</span><span class="sxs-lookup"><span data-stu-id="06731-109">Restore-SqlDatabase</span></span>  
 <span data-ttu-id="06731-110">Questo cmdlet viene utilizzato per ripristinare un database.</span><span class="sxs-lookup"><span data-stu-id="06731-110">Used to restore a database.</span></span>  
  
 <span data-ttu-id="06731-111">New-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="06731-111">New-SqlCredential</span></span>  
 <span data-ttu-id="06731-112">Questo cmdlet viene usato per creare le credenziali SQL necessarie per il backup di SQL Server in Archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="06731-112">This cmdlet is used to create a SQL Credential to use for SQL Server Backup to Azure Storage.</span></span> <span data-ttu-id="06731-113">Per ulteriori informazioni sulle credenziali e sul relativo utilizzo in SQL Server backup e ripristino, vedere [SQL Server backup e ripristino con il servizio di archiviazione BLOB di Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="06731-113">For more information on credentials and their use in SQL Server Backup and Restore, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="06731-114">Get-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="06731-114">Get-SqlCredential</span></span>  
 <span data-ttu-id="06731-115">Questo cmdlet viene utilizzato per recuperare l'oggetto Credential e le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="06731-115">This cmdlet is used to retrieve the Credential object and its properties.</span></span>  
  
 <span data-ttu-id="06731-116">Remove-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="06731-116">Remove-SqlCredential</span></span>  
 <span data-ttu-id="06731-117">Questo cmdlet viene utilizzato per eliminare un oggetto Credential di SQL.</span><span class="sxs-lookup"><span data-stu-id="06731-117">Delete a SQL Credential object</span></span>  
  
 <span data-ttu-id="06731-118">Set-SqlCredential</span><span class="sxs-lookup"><span data-stu-id="06731-118">Set-SqlCredential</span></span>  
 <span data-ttu-id="06731-119">Questo cmdlet viene utilizzato per modificare o impostare le proprietà dell'oggetto Credential di SQL.</span><span class="sxs-lookup"><span data-stu-id="06731-119">This cmdlet is used to change or set the properties of the SQL Credential Object.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="06731-120">I cmdlet relativi alle credenziali vengono usati nelle operazioni di backup e ripristino negli scenari del servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="06731-120">The Credential cmdlets are used in Backup and Restore to Azure Blob storage scenarios.</span></span>  
  
### <a name="powershell-for-multi-database-multi-instance-backup-operations"></a><span data-ttu-id="06731-121">PowerShell per le operazioni di backup di più istanze di più database</span><span class="sxs-lookup"><span data-stu-id="06731-121">PowerShell for Multi-Database, Multi-Instance Backup Operations</span></span>  
 <span data-ttu-id="06731-122">Nelle sezioni seguenti vengono forniti alcuni script per diverse operazioni quali la creazione di credenziali SQL in più istanze di SQL Server, il backup di tutti i database utente in un'istanza di SQL Server e simili.</span><span class="sxs-lookup"><span data-stu-id="06731-122">The following sections include scripts for various operations like creating a SQL Credential on multiple instance of SQL Server, backing up all user databases in an instance of SQL Server, and such.</span></span> <span data-ttu-id="06731-123">È possibile utilizzare questi script per automatizzare e pianificare le operazioni di backup in base ai requisiti dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="06731-123">You can use these scripts to automate or schedule backup operations according to the requirements of your environment.</span></span> <span data-ttu-id="06731-124">Gli script forniti di seguito sono esempi e possono essere modificati o estesi per l'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="06731-124">The scripts provided here are examples, and may be modified or extended for your environment.</span></span>  
  
 <span data-ttu-id="06731-125">Di seguito sono riportate alcune considerazioni per gli script di esempio:</span><span class="sxs-lookup"><span data-stu-id="06731-125">The following are considerations for the sample scripts:</span></span>  
  
1.  <span data-ttu-id="06731-126">**Spostamento all'interno dei percorsi di SQL Server PowerShell:** Windows PowerShell implementa alcuni cmdlet per spostarsi all'interno della struttura del percorso che rappresenta la gerarchia di oggetti supportati da un provider PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06731-126">**Navigating SQL Server PowerShell paths:** Windows PowerShell implements cmdlets to navigate the path structure that represents the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="06731-127">Quando si passa a un nodo nel percorso, è possibile utilizzare altri cmdlet per eseguire operazioni di base sull'oggetto corrente.</span><span class="sxs-lookup"><span data-stu-id="06731-127">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span>  
  
2.  <span data-ttu-id="06731-128">Cmdlet `Get-ChildItem`: le informazioni restituite da `Get-ChildItem` dipendono dal percorso di PowerShell per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06731-128">`Get-ChildItem` cmdlet: The information returned by the `Get-ChildItem` depends on the location in a SQL Server PowerShell path.</span></span> <span data-ttu-id="06731-129">Ad esempio, se il percorso è a livello di computer, questo cmdlet restituisce tutte le istanze del motore di database di SQL Server installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="06731-129">For example, if the location is at the computer level, this cmdlet returns all the SQL Server database engine instances installed on the computer.</span></span> <span data-ttu-id="06731-130">Sempre a titolo di esempio, se il percorso è a livello di oggetto come i database, questo cmdlet restituisce un elenco di oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="06731-130">As another example, if the location is at the object level such as databases, then this cmdlet returns a list of database objects.</span></span>  <span data-ttu-id="06731-131">Per impostazione predefinita il cmdlet `Get-ChildItem` non restituisce oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="06731-131">By default the `Get-ChildItem` cmdlet does not return system objects.</span></span>  <span data-ttu-id="06731-132">Se si usa il parametro -Force, è possibile visualizzare gli oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="06731-132">Using the -Force parameter you can see the system objects.</span></span>  
  
     <span data-ttu-id="06731-133">Per altre informazioni, vedere [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span><span class="sxs-lookup"><span data-stu-id="06731-133">For more information, see [Navigate SQL Server PowerShell Paths](../../powershell/navigate-sql-server-powershell-paths.md).</span></span>  
  
3.  <span data-ttu-id="06731-134">Ogni esempio di codice può essere usato in modo indipendente modificando i valori di variabili, tuttavia la creazione di un account di Archiviazione di Azure e delle credenziali SQL è un prerequisito necessario per tutte le operazioni di backup e ripristino nel servizio Archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="06731-134">Although each code sample can be tried independently by changing the variable values, creating an Azure Storage Account and a SQL Credential are prerequisites and required for all backup and restore operations to Azure Blob storage service.</span></span>  
  
### <a name="create-a-sql-credential-on-all-the-instances-of-sql-server"></a><span data-ttu-id="06731-135">Creare le credenziali SQL in tutte le istanze di SQL Server</span><span class="sxs-lookup"><span data-stu-id="06731-135">Create a SQL Credential on All the Instances of SQL Server</span></span>  
 <span data-ttu-id="06731-136">Sono disponibili due script di esempio, entrambi per la creazione delle credenziali SQL "mybackupToURL" in tutte le istanze di SQL Server in un computer.</span><span class="sxs-lookup"><span data-stu-id="06731-136">There are two sample scripts, and both create a SQL Credential "mybackupToURL" on all the instances of SQL Server on a computer.</span></span> <span data-ttu-id="06731-137">Il primo esempio è semplice e consente di creare le credenziali senza intercettare eccezioni.</span><span class="sxs-lookup"><span data-stu-id="06731-137">The first example creates is simple and creates the credential and does not trap exceptions.</span></span>  <span data-ttu-id="06731-138">Se ad esempio sono già presenti credenziali esistenti con lo stesso nome in una delle istanze del computer, lo script avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="06731-138">For example, if there was already an existing credential with the same name on one of the instances of the computer, the script would fail.</span></span> <span data-ttu-id="06731-139">Nel secondo esempio vengono intercettati gli errori consentendo allo script di continuare.</span><span class="sxs-lookup"><span data-stu-id="06731-139">The second example traps errors and allows the script to continue.</span></span>  
  
```powershell
import-module sqlps  
  
# create variables  
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#pipe the instances to new-sqlcredentail cmdlet to create SQL credential  
$instances | New-SqlCredential -Name $credentialName -Identity $storageAccount -Secret $secureString  
```  
  
```powershell
import-module sqlps  
  
# set the parameter values
$storageAccount = "mystorageaccount"  
$storageKey = "<storageaccesskeyvalue>"  
$secureString = ConvertTo-SecureString $storageKey  -asplaintext -force  
$credentialName = "mybackuptoURL"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
# get the list of instances  
$instances = Get-ChildItem  
#loop through instances and create a SQL credential, output any errors  
ForEach ($instance In $instances)  
{  
    Try  
{  
     New-SqlCredential -Name $credentialName -path "SQLServer:\SQL\$($instance.name)" -Identity $storageAccount -Secret $secureString -ea Stop
}  
Catch [Exception]  
    {
            Write-Host "instance - $($instance.name): "$_.Exception.Message
    }
 }
```  
  
### <a name="remove-a-sql-credential-from-all-the-instances-of-sql-server"></a><span data-ttu-id="06731-140">Rimuovere le credenziali SQL da tutte le istanze di SQL Server</span><span class="sxs-lookup"><span data-stu-id="06731-140">Remove A SQL Credential from All the Instances of SQL Server</span></span>  
 <span data-ttu-id="06731-141">Questo script può essere utilizzato per rimuovere credenziali specifiche da tutte le istanze di SQL Server installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="06731-141">This script can be used to remove a specific credential from all the instances of SQL Server installed on the computer.</span></span> <span data-ttu-id="06731-142">Se l'oggetto Credential non esiste in un'istanza specifica, viene visualizzato un messaggio di errore e lo script continua finché non vengono controllate tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="06731-142">If the Credential object does not exist on a specific instance, an error message is displayed, and the script continues until all instances are checked.</span></span>  
  
```powershell
import-module sqlps  
  
cd SQLServer:\SQL\COMPUTERNAME  
$credentialName = "mybackuptoURL"  
  
$instances = Get-ChildItem  
  
ForEach ($instance In $instances)  
   {
    Try  
        {  
            $path = "SQLServer:\SQL\$($instance.name)\credentials\$credentialName"   
            Remove-SqlCredential -Path $path -ea stop   
         }  
         Catch [Exception]  
         {  
            Write-Host $_.Exception.Message
        }
    }  
```  
  
### <a name="full-database-backup-for-all-databases-including-system-databases"></a><span data-ttu-id="06731-143">Backup completo del database per tutti i database (compresi i database di sistema)</span><span class="sxs-lookup"><span data-stu-id="06731-143">Full Database Backup for all Databases (INCLUDING SYSTEM DATABASES)</span></span>  
 <span data-ttu-id="06731-144">Lo script seguente consente di creare i backup di tutti i database presenti nel computer,</span><span class="sxs-lookup"><span data-stu-id="06731-144">The following script creates backups of all databases on the computer.</span></span> <span data-ttu-id="06731-145">sia database utente che database di sistema **msdb** .</span><span class="sxs-lookup"><span data-stu-id="06731-145">This includes both user databases and **msdb** system database.</span></span> <span data-ttu-id="06731-146">Nello script vengono esclusi tramite filtro i database di sistema **tempdb** e **model** .</span><span class="sxs-lookup"><span data-stu-id="06731-146">The script filters out **tempdb** and **model** system databases.</span></span>  
  
```powershell
import-module sqlps  
# set the parameter values  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the  databases -filter out tempdb and model databases  
  
 ForEach ($instance In $instances)  
 {  
   $path = "sqlserver:\sql\$($instance.name)\databases"  
   $alldatabases = Get-ChildItem -Force -path $path | Where-Object {$_.name -ne "tempdb" -and $_.name -ne "model"}   
   $alldatabases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On -script   
 }
```  
  
### <a name="full-database-backup-for-all-user-databases"></a><span data-ttu-id="06731-147">Backup completo del database per tutti i database utente</span><span class="sxs-lookup"><span data-stu-id="06731-147">Full Database Backup for ALL User Databases</span></span>  
 <span data-ttu-id="06731-148">Lo script seguente può essere utilizzato per eseguire il backup di tutti i database utente in tutte le istanze di SQL Server presenti nel computer.</span><span class="sxs-lookup"><span data-stu-id="06731-148">The following script can be used to back up all the user databases on all the instances of SQL Server on the computer.</span></span>  
  
```powershell
import-module sqlps
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackuptoURL"  
  
# cd to computer level
cd SQLServer:\SQL\COMPUTERNAME  
$instances = Get-ChildItem
# loop through each instances and backup up all the user databases  
 ForEach ($instance In $instances)  
 {  
    $databases = dir "sqlserver:\sql\$($instance.name)\databases"  
    $databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On
 }  
```  
  
### <a name="full-database-backup-for-master-and-msdb-system-databases-on-all-the-instances-of-sql-server"></a><span data-ttu-id="06731-149">Backup completo del database per MASTER e MSDB (database di sistema) in tutte le istanze di SQL Server</span><span class="sxs-lookup"><span data-stu-id="06731-149">Full Database Backup for MASTER and MSDB (SYSTEM DATABASES) On All the Instances of SQL Server</span></span>  
 <span data-ttu-id="06731-150">Lo script seguente può essere utilizzato per eseguire il backup dei database **master** e **msdb** in tutte le istanze di SQL Server installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="06731-150">The following script can be used to back up **master** and **msdb** databases on all the instances of SQL Server installed on the computer.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$credentialName = "mybackupToUrl"  
$sysDbs = "master", "msdb"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
$instances = Get-ChildItem
ForEach ($instance In $instances)  
 {  
      ForEach ($s In $sysdbs)  
     {  
        Backup-SqlDatabase -Database $s -path "sqlserver:\sql\$($instance.name)" -BackupContainer  $backupUrlContainer -SqlCredential $credentialName -Compression On   
}
 } 
```  
  
### <a name="full-database-backup-for-all-user-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="06731-151">Backup completo del database per tutti i database utente di un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="06731-151">Full Database Backup for All User Databases on an Instance of SQL Server</span></span>  
 <span data-ttu-id="06731-152">Lo script seguente viene utilizzato per eseguire il backup solo dei database utente disponibili in un'istanza denominata di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06731-152">The following script is used to back up only the user databases available on a named instance of SQL Server.</span></span> <span data-ttu-id="06731-153">Lo stesso script può essere utilizzato per l'istanza predefinita del computer modificando il valore del parametro $srvPath.</span><span class="sxs-lookup"><span data-stu-id="06731-153">The same script can be used for the default instance on the computer by changing the $srvPath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME"  # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#cd to computer level  
cd sqlserver:\sql\COMPUTERNAME  
  
#retrieves the database objects for a specific instance  
$databases = dir $srvPath\databases  
  
#backup all the user databases  
$databases | Backup-SqlDatabase -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
```  
  
### <a name="full-database-backup-for-only-system-databases-master-and-msdb-on-an-instance-of-sql-server"></a><span data-ttu-id="06731-154">Backup completo del database solo per i database di sistema (MASTER e MSDB) in un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="06731-154">Full Database Backup for Only System Databases (MASTER AND MSDB) On an Instance of SQL Server</span></span>  
 <span data-ttu-id="06731-155">Lo script seguente può essere utilizzato per eseguire il backup dei database **master** e **msdb** in un'istanza denominata di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06731-155">The full script can be used to back up the **master** and the **msdb** databases on a named instance of SQL Server.</span></span> <span data-ttu-id="06731-156">Lo stesso script può essere utilizzato per l'istanza predefinita del computer modificando il valore del parametro $srvPath.</span><span class="sxs-lookup"><span data-stu-id="06731-156">The same script can be used for the default instance on the computer by changing the $srvpath parameter value.</span></span>  
  
```powershell
import-module sqlps  
  
$storageAccount = "mystorageaccount"  
$blobContainer = "privatecontainertest"  
$backupUrlContainer = "https://$storageAccount.blob.core.windows.net/$blobContainer/"  
$srvPath = "SQLServer:\SQL\COMPUTERNAME\INSTANCENAME" # for default instance, the $srvpath variable is "SQLSERVER:\SQL\COMPUTERNAME\DEFAULT"  
$credentialName = "mybackupToUrl"  
  
#navigate to instance level  
cd $srvPath  
  
$sysDbs = "master", "msdb"  
ForEach ($s In $sysDbs)
{  
Backup-SqlDatabase -Database $s -BackupContainer $backupUrlContainer -SqlCredential $credentialName -Compression On  
}
```  
  
## <a name="see-also"></a><span data-ttu-id="06731-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06731-157">See Also</span></span>
 <span data-ttu-id="06731-158">[SQL Server backup e ripristino con il servizio di archiviazione BLOB di Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server le procedure consigliate e la risoluzione dei problemi di backup in URL](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="06731-158">[SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) [SQL Server Backup to URL Best Practices and Troubleshooting](sql-server-backup-to-url-best-practices-and-troubleshooting.md)</span></span>  
