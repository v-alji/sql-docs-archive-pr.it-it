---
title: Crittografia dei backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 334b95a8-6061-4fe0-9e34-b32c9f1706ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6a78ae4969982fbfe5295ee4219855f48ac60793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727019"
---
# <a name="backup-encryption"></a><span data-ttu-id="5bb6c-102">Crittografia dei backup</span><span class="sxs-lookup"><span data-stu-id="5bb6c-102">Backup Encryption</span></span>
  <span data-ttu-id="5bb6c-103">In questo argomento viene fornita una panoramica delle opzioni di crittografia per i backup di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bb6c-103">This topic provides an overview of the encryption options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="5bb6c-104">Vengono illustrati i dettagli di utilizzo, i vantaggi e le procedure consigliate per eseguire la crittografia durante il backup.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-104">It includes details of the usage, benefits, and recommended practices for encrypting during backup.</span></span>  
  
  
##  <a name="overview"></a><a name="Overview"></a> <span data-ttu-id="5bb6c-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5bb6c-105">Overview</span></span>  
 <span data-ttu-id="5bb6c-106">A partire da [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], in SQL Server è possibile crittografare i dati durante la creazione di un backup.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-106">Starting in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SQL Server has the ability to encrypt the data while creating a backup.</span></span> <span data-ttu-id="5bb6c-107">Specificando l'algoritmo di crittografia e il componente di crittografia (certificato o chiave asimmetrica) durante la creazione di un backup, è possibile creare un file di backup crittografato.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-107">By specifying the encryption algorithm and the encryptor (a Certificate or Asymmetric Key) when creating a backup, you can create an encrypted backup file.</span></span> <span data-ttu-id="5bb6c-108">Sono supportate tutte le destinazioni di archiviazione, in locale e Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-108">All storage destinations: on-premises and Window Azure storage are supported.</span></span> <span data-ttu-id="5bb6c-109">Inoltre, è possibile configurare le opzioni di crittografia per le operazioni del [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] , una nuova funzionalità introdotta in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bb6c-109">In addition, encryption options can be configured for [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] operations, a new feature introduced in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="5bb6c-110">Per crittografare durante il backup, è necessario specificare un algoritmo di crittografia e un componente di crittografia per proteggere la chiave di crittografia.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-110">To encrypt during backup, you must specify an encryption algorithm, and an encryptor to secure the encryption key.</span></span> <span data-ttu-id="5bb6c-111">Di seguito sono riportate le opzioni di crittografia supportate:</span><span class="sxs-lookup"><span data-stu-id="5bb6c-111">The following are the supported encryption options:</span></span>  
  
-   <span data-ttu-id="5bb6c-112">**Algoritmo di crittografia:** gli algoritmi di crittografia supportati sono AES 128, AES 192, AES 256 e Triple DES</span><span class="sxs-lookup"><span data-stu-id="5bb6c-112">**Encryption Algorithm:** The supported encryption algorithms are: AES 128, AES 192, AES 256, and Triple DES</span></span>  
  
-   <span data-ttu-id="5bb6c-113">**Componente di crittografia:** un certificato o una chiave asimmetrica</span><span class="sxs-lookup"><span data-stu-id="5bb6c-113">**Encryptor:** A certificate or asymmetric Key</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="5bb6c-114">È molto importante eseguire il backup del certificato o della chiave asimmetrica e preferibilmente in un percorso diverso dal file di backup utilizzato per la crittografia.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-114">It is very important to back up the certificate or asymmetric key, and preferably to a different location than the backup file it was used to encrypt.</span></span> <span data-ttu-id="5bb6c-115">Senza il certificato o la chiave asimmetrica, non è possibile ripristinare il backup, rendendo il file di backup inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-115">Without the certificate or asymmetric key, you cannot restore the backup, rendering the backup file unusable.</span></span>  
  
 <span data-ttu-id="5bb6c-116">**Ripristino del backup crittografato:** durante le operazioni di ripristino di SQL Server non è necessario specificare alcun parametro di crittografia.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-116">**Restoring the encrypted backup:** SQL Server restore does not require any encryption parameters to be specified during restores.</span></span> <span data-ttu-id="5bb6c-117">È necessario che la chiave asimmetrica o il certificato utilizzato per crittografare il file di backup sia disponibile nell'istanza in cui viene eseguito il ripristino.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-117">It does require that the certificate or the asymmetric key used to encrypt the backup file be available on the instance that you are restoring to.</span></span> <span data-ttu-id="5bb6c-118">L'account utente che esegue il ripristino deve disporre delle autorizzazioni `VIEW DEFINITION` per il certificato o la chiave.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-118">The user account performing the restore must have `VIEW DEFINITION` permissions on the certificate or key.</span></span> <span data-ttu-id="5bb6c-119">Se si esegue il ripristino del backup crittografato in un'istanza diversa, è necessario assicurarsi che il certificato sia disponibile in tale istanza.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-119">If you are restoring the encrypted backup to a different instance, you must make sure that the certificate is available on that instance.</span></span>  
  
 <span data-ttu-id="5bb6c-120">Se si esegue il ripristino di un backup da un database crittografato con TDE, è necessario che il certificato TDE sia disponibile nell'istanza in cui viene eseguito il ripristino.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-120">If you are restoring a backup from a TDE encrypted database, the TDE certificate should be available on the instance you are restoring to.</span></span>  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="5bb6c-121">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="5bb6c-121">Benefits</span></span>  
  
1.  <span data-ttu-id="5bb6c-122">La crittografia dei backup dei database aiuta a proteggere i dati: SQL Server consente di scegliere di crittografare i dati di backup durante la creazione di un backup.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-122">Encrypting the database backups helps secure the data: SQL Server provides the option to encrypt the backup data while creating a backup.</span></span>  
  
2.  <span data-ttu-id="5bb6c-123">La crittografia può essere utilizzata anche per i database crittografati tramite TDE.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-123">Encryption can also be used for databases that are encrypted using TDE.</span></span>  
  
3.  <span data-ttu-id="5bb6c-124">La crittografia è supportata per i backup eseguiti dal [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)], assicurando una maggiore sicurezza per i backup esterni.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-124">Encryption is supported for backups done by [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)], which provides additional security for off-site backups.</span></span>  
  
4.  <span data-ttu-id="5bb6c-125">Questa funzionalità supporta più algoritmi di crittografia fino ad AES a 256 bit,</span><span class="sxs-lookup"><span data-stu-id="5bb6c-125">This feature supports multiple encryption algorithms up to AES 256 bit.</span></span> <span data-ttu-id="5bb6c-126">offrendo la possibilità di scegliere l'algoritmo più adatto alle specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-126">This gives you the option to select an algorithm that aligns with your requirements.</span></span>  
  
5.  <span data-ttu-id="5bb6c-127">È possibile integrare le chiavi di crittografia con i provider EKM (Extended Key Management).</span><span class="sxs-lookup"><span data-stu-id="5bb6c-127">You can integrate encryption keys with Extended Key Management (EKM) providers.</span></span>  
  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="5bb6c-128">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5bb6c-128">Prerequisites</span></span>  
 <span data-ttu-id="5bb6c-129">Di seguito sono riportati i prerequisiti per crittografare un backup:</span><span class="sxs-lookup"><span data-stu-id="5bb6c-129">The following are prerequisites for encrypting a backup:</span></span>  
  
1.  <span data-ttu-id="5bb6c-130">**Creare una chiave master del database per il database master:** La chiave master del database è una chiave simmetrica utilizzata per proteggere le chiavi private dei certificati e le chiavi asimmetriche presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-130">**Create a Database Master Key for the master database:** The database master key is a symmetric key that is used to protect the private keys of certificates and asymmetric keys that are present in the database.</span></span> <span data-ttu-id="5bb6c-131">Per altre informazioni, vedere [Chiavi di crittografia del database e di SQL Server &#40;Motore di database&#41;](../security/encryption/sql-server-and-database-encryption-keys-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="5bb6c-131">For more information, see [SQL Server and Database Encryption Keys &#40;Database Engine&#41;](../security/encryption/sql-server-and-database-encryption-keys-database-engine.md).</span></span>  
  
2.  <span data-ttu-id="5bb6c-132">Creare un certificato o una chiave asimmetrica da utilizzare per la crittografia dei backup.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-132">Create a certificate or asymmetric Key to use for backup encryption.</span></span> <span data-ttu-id="5bb6c-133">Per altre informazioni sulla creazione di un certificato, vedere [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bb6c-133">For more information on creating a certificate, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span> <span data-ttu-id="5bb6c-134">Per altre informazioni sulla creazione di una chiave asimmetrica, vedere [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bb6c-134">For more information on creating an asymmetric key, see [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5bb6c-135">Sono supportate solo le chiavi asimmetriche che risiedono in un provider EKM (Extended Key Management).</span><span class="sxs-lookup"><span data-stu-id="5bb6c-135">Only asymmetric keys residing in an Extended Key Management (EKM) are supported.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5bb6c-136">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="5bb6c-136">Restrictions</span></span>  
 <span data-ttu-id="5bb6c-137">Di seguito sono riportate le restrizioni applicate alle opzioni di crittografia:</span><span class="sxs-lookup"><span data-stu-id="5bb6c-137">The following are restrictions that apply to the encryption options:</span></span>  
  
-   <span data-ttu-id="5bb6c-138">Se si utilizza la chiave asimmetrica per crittografare i dati di backup, sono supportate solo le chiavi asimmetriche che risiedono nel provider EKM.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-138">If you are using asymmetric key to encrypt the backup data, only asymmetric keys residing in the EKM provider are supported.</span></span>  
  
-   <span data-ttu-id="5bb6c-139">SQL Server Express e SQL Server Web non supportano la crittografia durante il backup.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-139">SQL Server Express and SQL Server Web do not support encryption during backup.</span></span> <span data-ttu-id="5bb6c-140">È tuttavia supportato il ripristino da un backup crittografato in un'istanza di SQL Server Express o SQL Server Web.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-140">However restoring from an encrypted backup to an instance of SQL Server Express or SQL Server Web is supported.</span></span>  
  
-   <span data-ttu-id="5bb6c-141">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è possibile leggere i backup crittografati.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-141">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read encrypted backups.</span></span>  
  
-   <span data-ttu-id="5bb6c-142">L'opzione Accoda al set di backup esistente non è supportata per i backup crittografati.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-142">Appending to an existing backup set option is not supported for encrypted backups.</span></span>  
  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5bb6c-143">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5bb6c-143">Permissions</span></span>  
 <span data-ttu-id="5bb6c-144">**Per crittografare un backup o per eseguire il ripristino da un backup crittografato:**</span><span class="sxs-lookup"><span data-stu-id="5bb6c-144">**To encrypt a backup or to restore from an encrypted backup:**</span></span>  
  
 <span data-ttu-id="5bb6c-145">Autorizzazione `VIEW DEFINITION` per la chiave asimmetrica o il certificato utilizzato per crittografare il backup del database.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-145">`VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database backup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5bb6c-146">L'accesso al certificato TDE non è necessario per eseguire il backup o il ripristino di un database protetto con TDE.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-146">Access to the TDE certificate is not required to back up or restore a TDE protected database.</span></span>  
  
##  <a name="backup-encryption-methods"></a><a name="Methods"></a> <span data-ttu-id="5bb6c-147">Metodi di crittografia dei backup</span><span class="sxs-lookup"><span data-stu-id="5bb6c-147">Backup Encryption Methods</span></span>  
 <span data-ttu-id="5bb6c-148">Nelle sezioni seguenti viene fornita una breve introduzione ai passaggi per crittografare i dati durante il backup.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-148">The sections below provide a brief introduction to the steps to encrypting the data during backup.</span></span> <span data-ttu-id="5bb6c-149">Per una procedura dettagliata completa per la crittografia del backup con Transact-SQL, vedere [Creare un backup crittografato](create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="5bb6c-149">For a complete walkthrough of the different steps of encrypting your backup using Transact-SQL, see [Create an Encrypted Backup](create-an-encrypted-backup.md).</span></span>  
  
### <a name="using-sql-server-management-studio"></a><span data-ttu-id="5bb6c-150">Utilizzare SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5bb6c-150">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5bb6c-151">È possibile crittografare un backup durante la creazione del backup di un database in una delle finestre di dialogo seguenti:</span><span class="sxs-lookup"><span data-stu-id="5bb6c-151">You can encrypt a backup when creating the backup of a database in any of the following dialog boxes:</span></span>  
  
1.  <span data-ttu-id="5bb6c-152">[Backup database &#40;pagina Opzioni di backup&#41;](back-up-database-backup-options-page.md) Nella pagina **Opzioni di backup** è possibile selezionare **Crittografia** e specificare l'algoritmo di crittografia e il certificato o la chiave asimmetrica da usare per la crittografia.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-152">[Back Up Database &#40;Backup Options Page&#41;](back-up-database-backup-options-page.md) On the **Backup Options** page, you can select **Encryption**, and specify the encryption algorithm and the certificate or asymmetric key to use for the encryption.</span></span>  
  
2.  <span data-ttu-id="5bb6c-153">[Utilizzo di Creazione guidata piano di manutenzione](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure) Quando si seleziona un'attività di backup, nella scheda **Opzioni** della pagina **Definizione attività Backup database ()** è possibile selezionare **Crittografia backup**e specificare l'algoritmo di crittografia e il certificato o la chiave da usare per la crittografia.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-153">[Using Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md#SSMSProcedure) When you select a backup task, on the **Options** tab of the **Define Backup ()Task** page, you can select **Backup Encryption**, and specify the encryption algorithm and the certificate or key to use for the encryption.</span></span>  
  
### <a name="using-transact-sql"></a><span data-ttu-id="5bb6c-154">Utilizzo di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5bb6c-154">Using Transact SQL</span></span>  
 <span data-ttu-id="5bb6c-155">Di seguito è riportata un'istruzione Transact-SQL di esempio per crittografare il file di backup:</span><span class="sxs-lookup"><span data-stu-id="5bb6c-155">Following is a sample Transact-SQL statement to encrypt the backup file:</span></span>  
  
```sql
BACKUP DATABASE [MYTestDB]  
TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
WITH  
  COMPRESSION,  
  ENCRYPTION   
   (  
   ALGORITHM = AES_256,  
   SERVER CERTIFICATE = BackupEncryptCert  
   ),  
  STATS = 10  
GO
```  
  
 <span data-ttu-id="5bb6c-156">Per la sintassi completa dell'istruzione Transact-SQL, vedere [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5bb6c-156">For the full Transact-SQL statement syntax, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
### <a name="using-powershell"></a><span data-ttu-id="5bb6c-157">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bb6c-157">Using PowerShell</span></span>  
 <span data-ttu-id="5bb6c-158">Questo esempio illustra come creare le opzioni di crittografia, usate come valore di parametro nel cmdlet **Backup-SqlDatabase** per creare un backup crittografato.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-158">This example creates the encryption options and uses it as a parameter value in **Backup-SqlDatabase** cmdlet to create an encrypted backup.</span></span>  
  
```powershell
$encryptionOption = New-SqlBackupEncryptionOption -Algorithm Aes256 -EncryptorType ServerCertificate -EncryptorName "BackupCert"  
Backup-SqlDatabase -ServerInstance . -Database "MyTestDB" -BackupFile "MyTestDB.bak" -CompressionOption On -EncryptionOption $encryptionOption  
```  
  
##  <a name="recommended-practices"></a><a name="RecommendedPractices"></a> <span data-ttu-id="5bb6c-159">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="5bb6c-159">Recommended Practices</span></span>  
 <span data-ttu-id="5bb6c-160">Creare un backup del certificato e delle chiavi di crittografia in un percorso diverso dal computer locale in cui è installata l'istanza.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-160">Create a backup of the encryption certificate and keys to a location other than your local machine where the instance is installed.</span></span> <span data-ttu-id="5bb6c-161">Tenendo in considerazione gli scenari di ripristino di emergenza, è consigliabile archiviare un backup del certificato o della chiave in una posizione esterna.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-161">To account for disaster recovery scenarios, consider storing a backup of the certificate or key to an off-site location.</span></span> <span data-ttu-id="5bb6c-162">Non è possibile ripristinare un backup crittografato senza il certificato utilizzato per crittografarlo.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-162">You cannot restore an encrypted backup without the certificate used to encrypt the backup.</span></span>  
  
 <span data-ttu-id="5bb6c-163">Per ripristinare un backup crittografato, è necessario che il certificato originale utilizzato durante la creazione del backup con l'identificazione digitale corrispondente sia disponibile nell'istanza in cui viene eseguito il ripristino.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-163">To restore an encrypted backup, the original certificate used when the backup was taken with the matching thumbprint should be available on the instance you are restoring to.</span></span> <span data-ttu-id="5bb6c-164">Pertanto, il certificato non deve essere rinnovato alla scadenza né modificato in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-164">Therefore, the certificate should not be renewed on expiry or changed in any way.</span></span> <span data-ttu-id="5bb6c-165">Il rinnovo può comportare un aggiornamento del certificato con conseguente modifica dell'identificazione digitale, rendendo pertanto il certificato non valido per il file di backup.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-165">Renewal can result in updating the certificate triggering the change of the thumbprint, therefore making the certificate invalid for the backup file.</span></span> <span data-ttu-id="5bb6c-166">L'account che esegue il ripristino deve disporre delle autorizzazioni VIEW DEFINITION per la chiave asimmetrica o il certificato utilizzato per eseguire la crittografia durante il backup.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-166">The account performing the restore should have VIEW DEFINITION permissions on the certificate or the asymmetric key used to encrypt during backup.</span></span>  
  
 <span data-ttu-id="5bb6c-167">I backup del database del gruppo di disponibilità vengono in genere eseguiti nella replica di backup preferita.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-167">Availability Group database backups are typically performed on the preferred backup replica.</span></span>  <span data-ttu-id="5bb6c-168">Se si ripristina un backup in una replica diversa da dove è stato eseguito il backup, verificare che il certificato originale utilizzato per il backup sia disponibile nella replica a cui si esegue il ripristino.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-168">If restoring a backup on a replica other than where the backup was taken from, ensure that the original certificate used for backup is available on the replica you are restoring to.</span></span>  
  
 <span data-ttu-id="5bb6c-169">Se per il database è abilitata la funzionalità TDE, scegliere certificati o chiavi asimmetriche diverse per crittografare il database e il backup in modo da aumentare il livello di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-169">If the database is TDE enabled, choose different certificates or asymmetric keys for encrypting the database and the backup to increase security.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5bb6c-170">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="5bb6c-170">Related Tasks</span></span>  
  
|<span data-ttu-id="5bb6c-171">Argomento/Attività</span><span class="sxs-lookup"><span data-stu-id="5bb6c-171">Topic/Task</span></span>|<span data-ttu-id="5bb6c-172">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bb6c-172">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="5bb6c-173">Creare un backup crittografato</span><span class="sxs-lookup"><span data-stu-id="5bb6c-173">Create an Encrypted Backup</span></span>](create-an-encrypted-backup.md)|<span data-ttu-id="5bb6c-174">Vengono descritti i passaggi di base necessari per creare un backup crittografato</span><span class="sxs-lookup"><span data-stu-id="5bb6c-174">Describes the basic steps required to create an encrypted backup</span></span>|  
|[<span data-ttu-id="5bb6c-175">Backup gestito di SQL Server in Azure - Impostazioni di archiviazione e di memorizzazione</span><span class="sxs-lookup"><span data-stu-id="5bb6c-175">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>](../../database-engine/sql-server-managed-backup-to-windows-azure-retention-and-storage-settings.md)|<span data-ttu-id="5bb6c-176">Vengono descritti i passaggi di base necessari per configurare il [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] con le opzioni di crittografia specificate.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-176">Describes the basic steps required to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with the encryption options specified.</span></span>|  
|[<span data-ttu-id="5bb6c-177">Extensible Key Management con l'insieme di credenziali delle chiavi di Azure &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5bb6c-177">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md)|<span data-ttu-id="5bb6c-178">Fornisce un esempio di creazione di un backup crittografato protetto da chiavi nell'insieme di credenziali delle chiavi di Azure.</span><span class="sxs-lookup"><span data-stu-id="5bb6c-178">Provides an example of creating an encrypted backup protected by keys in the Azure Key Vault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bb6c-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bb6c-179">See Also</span></span>  
 [<span data-ttu-id="5bb6c-180">Panoramica del backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5bb6c-180">Backup Overview &#40;SQL Server&#41;</span></span>](backup-overview-sql-server.md)  
  
  
