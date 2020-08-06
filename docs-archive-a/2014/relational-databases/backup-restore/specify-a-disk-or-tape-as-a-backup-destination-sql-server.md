---
title: Specificare un disco o un nastro come destinazione di backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
- backups [SQL Server], creating
- tape backup devices, backing up
ms.assetid: e391f452-ed8c-4b40-b846-ac3881271b94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a0f8ec5d9741e42f3b7d8eda8ebdba23622982d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715412"
---
# <a name="specify-a-disk-or-tape-as-a-backup-destination-sql-server"></a><span data-ttu-id="88ea0-102">Specificare un disco o un nastro come destinazione di backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="88ea0-102">Specify a Disk or Tape As a Backup Destination (SQL Server)</span></span>
  <span data-ttu-id="88ea0-103">In questo argomento si descrive come specificare un disco o un nastro come destinazione di backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88ea0-103">This topic describes how to specify a disk or tape as a backup destination in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88ea0-104">Il supporto per i dispositivi di backup su nastro verrà rimosso in una versione futura di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="88ea0-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="88ea0-105">Evitare di usare questa funzionalità in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui è attualmente implementata.</span><span class="sxs-lookup"><span data-stu-id="88ea0-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="88ea0-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="88ea0-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="88ea0-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="88ea0-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="88ea0-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="88ea0-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="88ea0-109">**Per specificare un disco o un nastro come destinazione di backup mediante:**</span><span class="sxs-lookup"><span data-stu-id="88ea0-109">**To specify a disk or tape as a backup destination, using:**</span></span>  
  
     [<span data-ttu-id="88ea0-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="88ea0-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="88ea0-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="88ea0-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="88ea0-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="88ea0-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="88ea0-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="88ea0-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="88ea0-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="88ea0-114">Permissions</span></span>  
 <span data-ttu-id="88ea0-115">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="88ea0-115">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="88ea0-116">Eventuali problemi correlati alla proprietà e alle autorizzazioni sul file fisico del dispositivo di backup possono interferire con l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="88ea0-116">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="88ea0-117">sia possibile leggere e scrivere sul dispositivo e che l'account utilizzato per eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="88ea0-117">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="88ea0-118">Le autorizzazioni di accesso ai file, tuttavia, non vengono controllate dalla stored procedure [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)che aggiunge una voce per un dispositivo di backup nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="88ea0-118">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="88ea0-119">Di conseguenza, i problemi relativi all'accesso e alla proprietà del file fisico del dispositivo di backup potrebbero emergere solo in fase di accesso alla risorsa fisica durante un tentativo di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="88ea0-119">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="88ea0-120">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="88ea0-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="88ea0-121">Per specificare un disco o un nastro come destinazione di backup</span><span class="sxs-lookup"><span data-stu-id="88ea0-121">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="88ea0-122">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="88ea0-122">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="88ea0-123">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="88ea0-123">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="88ea0-124">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Backup**.</span><span class="sxs-lookup"><span data-stu-id="88ea0-124">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="88ea0-125">Verrà visualizzata la finestra di dialogo **Backup database** .</span><span class="sxs-lookup"><span data-stu-id="88ea0-125">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="88ea0-126">Nella sezione **Destinazione** della scheda **Generale** fare clic su **Disco** o **Nastro**.</span><span class="sxs-lookup"><span data-stu-id="88ea0-126">In the **Destination** section of the **General** page, click **Disk** or **Tape**.</span></span> <span data-ttu-id="88ea0-127">Per selezionare i percorsi per un massimo di 64 unità disco o nastro contenenti un singolo set di supporti, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="88ea0-127">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span>  
  
     <span data-ttu-id="88ea0-128">Per rimuovere una destinazione di backup, selezionarla e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="88ea0-128">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="88ea0-129">Per visualizzare il contenuto di una destinazione di backup, selezionarla e fare clic su **Contenuto**.</span><span class="sxs-lookup"><span data-stu-id="88ea0-129">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="88ea0-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="88ea0-130">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="88ea0-131">Per specificare un disco o un nastro come destinazione di backup</span><span class="sxs-lookup"><span data-stu-id="88ea0-131">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="88ea0-132">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88ea0-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="88ea0-133">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="88ea0-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="88ea0-134">Nell'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) specificare il file o il dispositivo e il relativo nome fisico.</span><span class="sxs-lookup"><span data-stu-id="88ea0-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the file or device and its physical name.</span></span> <span data-ttu-id="88ea0-135">In questo esempio viene eseguito il backup del database `AdventureWorks2012` nel file su disco `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span><span class="sxs-lookup"><span data-stu-id="88ea0-135">This example backs up the `AdventureWorks2012` database to the disk file `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="88ea0-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88ea0-136">See Also</span></span>  
 <span data-ttu-id="88ea0-137">[Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="88ea0-137">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="88ea0-138">[Backup di file e filegroup &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="88ea0-138">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="88ea0-139">[Definire un dispositivo di backup logico per un file su disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="88ea0-139">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 <span data-ttu-id="88ea0-140">[Creare un backup differenziale del database &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="88ea0-140">[Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="88ea0-141">Definizione di un dispositivo di backup logico per un'unità nastro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="88ea0-141">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
