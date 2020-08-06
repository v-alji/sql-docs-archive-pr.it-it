---
title: Consente di specificare se un'operazione di backup o ripristino viene arrestata o prosegue in seguito a un errore (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], backups
- backing up databases [SQL Server], errors
- backups [SQL Server], errors
- database backups [SQL Server], errors
ms.assetid: 042be17a-b9b0-4629-b6bb-b87a8bc6c316
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 87cccec6f7eea18f2750d3b0be81b577b0eb170a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636730"
---
# <a name="specify-whether-a-backup-or-restore-operation-continues-or-stops-after-encountering-an-error-sql-server"></a><span data-ttu-id="8dccf-102">Specifica se un'operazione di backup o ripristino viene arrestata o prosegue in seguito a un errore (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8dccf-102">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error (SQL Server)</span></span>
  <span data-ttu-id="8dccf-103">In questo argomento viene descritto come specificare se un'operazione di backup o ripristino si arresta o prosegue quando si verifica un errore in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dccf-103">This topic describes how to specify whether a backup or restore operation continues or stops after encountering an error in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8dccf-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8dccf-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8dccf-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8dccf-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8dccf-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8dccf-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8dccf-107">**Per specificare se un'operazione di backup o ripristino viene arrestata o prosegue in seguito a un errore utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="8dccf-107">**To specify whether a backup or restore operation continues after encountering an error, using:**</span></span>  
  
     [<span data-ttu-id="8dccf-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8dccf-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8dccf-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8dccf-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8dccf-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8dccf-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8dccf-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8dccf-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8dccf-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8dccf-112">Permissions</span></span>  
 <span data-ttu-id="8dccf-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="8dccf-113">BACKUP</span></span>  
 <span data-ttu-id="8dccf-114">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="8dccf-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="8dccf-115">Eventuali problemi correlati alla proprietà e alle autorizzazioni sul file fisico del dispositivo di backup possono interferire con l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="8dccf-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8dccf-116">sia possibile leggere e scrivere sul dispositivo e che l'account utilizzato per eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="8dccf-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="8dccf-117">Le autorizzazioni di accesso ai file, tuttavia, non vengono controllate dalla stored procedure [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)che aggiunge una voce per un dispositivo di backup nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="8dccf-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="8dccf-118">Di conseguenza, i problemi relativi all'accesso e alla proprietà del file fisico del dispositivo di backup potrebbero emergere solo in fase di accesso alla risorsa fisica durante un tentativo di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="8dccf-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="8dccf-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="8dccf-119">RESTORE</span></span>  
 <span data-ttu-id="8dccf-120">Se il database da ripristinare non esiste, per eseguire un'operazione RESTORE l'utente deve disporre delle autorizzazioni CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="8dccf-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="8dccf-121">Se il database esiste, le autorizzazioni per l'istruzione RESTORE vengono assegnate per impostazione predefinita ai membri dei ruoli predefiniti del server **sysadmin** e **dbcreator** e al proprietario (**dbo**) del database. Per l'opzione FROM DATABASE_SNAPSHOT, il database esiste sempre.</span><span class="sxs-lookup"><span data-stu-id="8dccf-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="8dccf-122">Le autorizzazioni per l'istruzione RESTORE vengono assegnate ai ruoli in cui le informazioni sull'appartenenza sono sempre disponibili per il server.</span><span class="sxs-lookup"><span data-stu-id="8dccf-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="8dccf-123">Poiché è possibile controllare l'appartenenza ai ruoli predefiniti del database solo quando il database è accessibile e non è danneggiato, condizioni che non risultano sempre vere quando si esegue un'operazione RESTORE, i membri del ruolo predefinito del database **db_owner** non dispongono delle autorizzazioni per l'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="8dccf-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8dccf-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8dccf-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-whether-backup-continues-or-stops-after-an-error-is-encountered"></a><span data-ttu-id="8dccf-125">Per specificare se il backup viene arrestato o prosegue se viene rilevato un errore</span><span class="sxs-lookup"><span data-stu-id="8dccf-125">To specify whether backup continues or stops after an error is encountered</span></span>  
  
1.  <span data-ttu-id="8dccf-126">Seguire i passaggi per [creare un backup di database](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8dccf-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="8dccf-127">Nella sezione **Affidabilità** della pagina **Opzioni** fare clic su **Esegui checksum prima della scrittura nei supporti** e **Continua in caso di errori**.</span><span class="sxs-lookup"><span data-stu-id="8dccf-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media** and **Continue on error**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8dccf-128">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8dccf-128">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-whether-a-backup-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="8dccf-129">Per specificare se un'operazione di backup viene arrestata o prosegue in seguito a un errore</span><span class="sxs-lookup"><span data-stu-id="8dccf-129">To specify whether a backup operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="8dccf-130">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dccf-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8dccf-131">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8dccf-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8dccf-132">Nell'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) specificare l'opzione CONTINUE_AFTER ERROR per continuare o l'opzione STOP_ON_ERROR per interrompere.</span><span class="sxs-lookup"><span data-stu-id="8dccf-132">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="8dccf-133">Il comportamento predefinito è l'arresto nel caso venga rilevato un errore.</span><span class="sxs-lookup"><span data-stu-id="8dccf-133">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="8dccf-134">In questo esempio si indica all'operazione di backup di continuare nonostante sia stato rilevato un errore.</span><span class="sxs-lookup"><span data-stu-id="8dccf-134">This example instructs the backup operation to continue despite encountering an error.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
#### <a name="to-specify-whether-a-restore-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="8dccf-135">Per specificare se un'operazione di ripristino viene arrestata o prosegue in seguito a un errore</span><span class="sxs-lookup"><span data-stu-id="8dccf-135">To specify whether a restore operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="8dccf-136">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dccf-136">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8dccf-137">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8dccf-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8dccf-138">Nell'istruzione [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) specificare l'opzione CONTINUE_AFTER ERROR per continuare o l'opzione STOP_ON_ERROR per interrompere.</span><span class="sxs-lookup"><span data-stu-id="8dccf-138">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="8dccf-139">Il comportamento predefinito è l'arresto nel caso venga rilevato un errore.</span><span class="sxs-lookup"><span data-stu-id="8dccf-139">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="8dccf-140">In questo esempio si indica all'operazione di ripristino di continuare nonostante sia stato rilevato un errore.</span><span class="sxs-lookup"><span data-stu-id="8dccf-140">This example instructs the restore operation to continue despite encountering an error.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'   
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8dccf-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8dccf-141">See Also</span></span>  
 <span data-ttu-id="8dccf-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dccf-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="8dccf-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dccf-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="8dccf-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dccf-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="8dccf-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dccf-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="8dccf-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dccf-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="8dccf-147">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dccf-147">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="8dccf-148">[Argomenti dell'istruzione RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dccf-148">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="8dccf-149">[Possibili errori relativi ai supporti durante il backup e il ripristino &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8dccf-149">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="8dccf-150">Abilitare o disabilitare il checksum di backup durante il backup o il ripristino &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8dccf-150">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
  
