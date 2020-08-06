---
title: Abilitare o disabilitare il checksum di backup durante il backup o il ripristino (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup checksums [SQL Server]
- disabling checksums
- checksums [SQL Server]
ms.assetid: 6786bd1e-ad97-430a-8dfb-d4ba952d6c4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a239dcdfca689be8555117104264d66a2ac037f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726012"
---
# <a name="enable-or-disable-backup-checksums-during-backup-or-restore-sql-server"></a><span data-ttu-id="3e80b-102">Abilitazione o disabilitazione di checksum di backup durante il backup o il ripristino (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3e80b-102">Enable or Disable Backup Checksums During Backup or Restore (SQL Server)</span></span>
  <span data-ttu-id="3e80b-103">In questo argomento viene descritto come abilitare o disabilitare i checksum di backup quando si esegue il backup o il ripristina di un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e80b-103">This topic describes how to enable or disable backup checksums when you are backing up or restoring a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3e80b-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3e80b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3e80b-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3e80b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3e80b-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3e80b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3e80b-107">**Per abilitare o disabilitare i checksum per i backup utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="3e80b-107">**To enable or disable backup checksums, using:**</span></span>  
  
     [<span data-ttu-id="3e80b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e80b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3e80b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e80b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3e80b-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3e80b-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e80b-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3e80b-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3e80b-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3e80b-112">Permissions</span></span>  
 <span data-ttu-id="3e80b-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="3e80b-113">BACKUP</span></span>  
 <span data-ttu-id="3e80b-114">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="3e80b-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="3e80b-115">Eventuali problemi correlati alla proprietà e alle autorizzazioni sul file fisico del dispositivo di backup possono interferire con l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="3e80b-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3e80b-116">sia possibile leggere e scrivere sul dispositivo e che l'account utilizzato per eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="3e80b-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="3e80b-117">Le autorizzazioni di accesso ai file, tuttavia, non vengono controllate dalla stored procedure [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)che aggiunge una voce per un dispositivo di backup nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="3e80b-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="3e80b-118">Di conseguenza, i problemi relativi all'accesso e alla proprietà del file fisico del dispositivo di backup potrebbero emergere solo in fase di accesso alla risorsa fisica durante un tentativo di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="3e80b-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="3e80b-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="3e80b-119">RESTORE</span></span>  
 <span data-ttu-id="3e80b-120">Se il database da ripristinare non esiste, per eseguire un'operazione RESTORE l'utente deve disporre delle autorizzazioni CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3e80b-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="3e80b-121">Se il database esiste, le autorizzazioni per l'istruzione RESTORE vengono assegnate per impostazione predefinita ai membri dei ruoli predefiniti del server **sysadmin** e **dbcreator** e al proprietario (**dbo**) del database. Per l'opzione FROM DATABASE_SNAPSHOT, il database esiste sempre.</span><span class="sxs-lookup"><span data-stu-id="3e80b-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="3e80b-122">Le autorizzazioni per l'istruzione RESTORE vengono assegnate ai ruoli in cui le informazioni sull'appartenenza sono sempre disponibili per il server.</span><span class="sxs-lookup"><span data-stu-id="3e80b-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="3e80b-123">Poiché è possibile controllare l'appartenenza ai ruoli predefiniti del database solo quando il database è accessibile e non è danneggiato, condizioni che non risultano sempre vere quando si esegue un'operazione RESTORE, i membri del ruolo predefinito del database **db_owner** non dispongono delle autorizzazioni per l'istruzione RESTORE.</span><span class="sxs-lookup"><span data-stu-id="3e80b-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3e80b-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3e80b-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-or-disable-checksums-during-a-backup-operation"></a><span data-ttu-id="3e80b-125">Per abilitare o disabilitare i checksum durante un'operazione di backup</span><span class="sxs-lookup"><span data-stu-id="3e80b-125">To enable or disable checksums during a backup operation</span></span>  
  
1.  <span data-ttu-id="3e80b-126">Seguire i passaggi per [creare un backup di database](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3e80b-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="3e80b-127">Nella sezione **Affidabilità** della pagina **Opzioni** fare clic su **Esegui checksum prima della scrittura nei supporti**.</span><span class="sxs-lookup"><span data-stu-id="3e80b-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3e80b-128">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3e80b-128">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-backup-operation"></a><span data-ttu-id="3e80b-129">Per abilitare o disabilitare i checksum di backup per un'operazione di backup</span><span class="sxs-lookup"><span data-stu-id="3e80b-129">To enable or disable backup checksum for a backup operation</span></span>  
  
1.  <span data-ttu-id="3e80b-130">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e80b-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3e80b-131">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3e80b-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3e80b-132">Per abilitare i checksum di backup, specificare l'opzione WITH CHECKSUM in un'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3e80b-132">To enable backup checksums in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="3e80b-133">Per disabilitare i checksum di backup, specificare l'opzione WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="3e80b-133">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="3e80b-134">Si tratta del comportamento predefinito, tranne nel caso di un backup compresso.</span><span class="sxs-lookup"><span data-stu-id="3e80b-134">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="3e80b-135">Nell'esempio seguente si specifica che vengano eseguiti i checksum.</span><span class="sxs-lookup"><span data-stu-id="3e80b-135">The following example specifies that checksums be performed.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-restore-operation"></a><span data-ttu-id="3e80b-136">Per abilitare o disabilitare i checksum di backup per un'operazione di ripristino</span><span class="sxs-lookup"><span data-stu-id="3e80b-136">To enable or disable backup checksum for a restore operation</span></span>  
  
1.  <span data-ttu-id="3e80b-137">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e80b-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3e80b-138">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3e80b-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3e80b-139">Per abilitare i checksum di backup, specificare l'opzione WITH CHECKSUM in un'istruzione [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3e80b-139">To enable backup checksums in a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="3e80b-140">Questo comportamento è quello predefinito per un backup compresso.</span><span class="sxs-lookup"><span data-stu-id="3e80b-140">This is the default behavior for a compressed backup.</span></span> <span data-ttu-id="3e80b-141">Per disabilitare i checksum di backup, specificare l'opzione WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="3e80b-141">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="3e80b-142">Si tratta del comportamento predefinito, tranne nel caso di un backup compresso.</span><span class="sxs-lookup"><span data-stu-id="3e80b-142">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="3e80b-143">Nell'esempio seguente si specifica che vengano eseguiti i checksum di backup.</span><span class="sxs-lookup"><span data-stu-id="3e80b-143">The following example specifies that backup checksums be performed.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
> [!WARNING]  
>  <span data-ttu-id="3e80b-144">Se si richiede in modo esplicito l'opzione CHECKSUM per un'operazione di ripristino e il backup contiene checksum del backup, verranno verificati sia i checksum del backup che quelli delle pagine, come nel caso predefinito.</span><span class="sxs-lookup"><span data-stu-id="3e80b-144">If you explicitly request CHECKSUM for a restore operation and if the backup contains backup checksums, backup checksums and page checksums are both verified, as in the default case.</span></span> <span data-ttu-id="3e80b-145">Se tuttavia per il set di backup non sono disponibili checksum del backup, l'operazione di ripristino verrà interrotta con un messaggio in cui si indica che i checksum non sono presenti.</span><span class="sxs-lookup"><span data-stu-id="3e80b-145">However, if the backup set lacks backup checksums, the restore operation fails with a message indicating that checksums are not present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e80b-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e80b-146">See Also</span></span>  
 <span data-ttu-id="3e80b-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e80b-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="3e80b-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e80b-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="3e80b-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e80b-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="3e80b-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e80b-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="3e80b-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e80b-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="3e80b-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e80b-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="3e80b-153">[Argomenti dell'istruzione RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e80b-153">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="3e80b-154">[Possibili errori relativi ai supporti durante il backup e il ripristino &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e80b-154">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="3e80b-155">Specifica se un'operazione di backup o ripristino viene arrestata o prosegue in seguito a un errore &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e80b-155">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
  
