---
title: Impostare la data di scadenza di un backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], expiration dates
- expiration [SQL Server]
- database backups [SQL Server], expiration dates
ms.assetid: 76e814df-6487-4893-9f09-7759f1863a5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9185222df93e0a1150256535526ba910c593cf6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626815"
---
# <a name="set-the-expiration-date-on-a-backup-sql-server"></a><span data-ttu-id="b741f-102">Impostazione della data di scadenza di un backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b741f-102">Set the Expiration Date on a Backup (SQL Server)</span></span>
  <span data-ttu-id="b741f-103">In questo argomento viene descritto come impostare la data di scadenza in un backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b741f-103">This topic describes how to set the expiration date on a backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b741f-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b741f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b741f-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b741f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b741f-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b741f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b741f-107">**Per impostare la data di scadenza di un backup utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="b741f-107">**To set the expiration date on a backup, using:**</span></span>  
  
     [<span data-ttu-id="b741f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b741f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b741f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b741f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b741f-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b741f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b741f-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b741f-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b741f-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b741f-112">Permissions</span></span>  
 <span data-ttu-id="b741f-113">Le autorizzazioni BACKUP DATABASE e BACKUP LOG vengono assegnate per impostazione predefinita ai membri del ruolo predefinito del server **sysadmin** e dei ruoli predefiniti del database **db_owner** e **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="b741f-113">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="b741f-114">Eventuali problemi correlati alla proprietà e alle autorizzazioni sul file fisico del dispositivo di backup possono interferire con l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="b741f-114">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b741f-115">sia possibile leggere e scrivere sul dispositivo e che l'account utilizzato per eseguire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga delle autorizzazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="b741f-115">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="b741f-116">Le autorizzazioni di accesso ai file, tuttavia, non vengono controllate dalla stored procedure [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)che aggiunge una voce per un dispositivo di backup nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="b741f-116">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="b741f-117">Di conseguenza, i problemi relativi all'accesso e alla proprietà del file fisico del dispositivo di backup potrebbero emergere solo in fase di accesso alla risorsa fisica durante un tentativo di backup o ripristino.</span><span class="sxs-lookup"><span data-stu-id="b741f-117">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b741f-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b741f-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="b741f-119">Per impostare la data di scadenza di un backup</span><span class="sxs-lookup"><span data-stu-id="b741f-119">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="b741f-120">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="b741f-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b741f-121">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="b741f-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="b741f-122">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Backup**.</span><span class="sxs-lookup"><span data-stu-id="b741f-122">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="b741f-123">Verrà visualizzata la finestra di dialogo **Backup database** .</span><span class="sxs-lookup"><span data-stu-id="b741f-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b741f-124">Nella pagina **Generale** , in **Scadenza set di backup**specificare una data di scadenza, ovvero la data in cui il backup può essere sovrascritto da un altro backup:</span><span class="sxs-lookup"><span data-stu-id="b741f-124">On the **General** page, for **Backup set will expire**, specify an expiration date to indicate when the backup set can be overwritten by another backup:</span></span>  
  
    -   <span data-ttu-id="b741f-125">Per impostare la scadenza del set di backup dopo un numero di giorni specifico, fare clic su **Dopo** (opzione predefinita) e immettere il numero di giorni dopo la creazione del set trascorsi i quali il set scadrà.</span><span class="sxs-lookup"><span data-stu-id="b741f-125">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="b741f-126">È possibile impostare un valore compreso nell'intervallo da 0 a 99999 giorni. L'impostazione del valore 0 giorni indica che il set di backup non ha scadenza.</span><span class="sxs-lookup"><span data-stu-id="b741f-126">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="b741f-127">Il valore predefinito viene impostato nell'opzione **Periodo di memorizzazione predefinito supporti di backup (giorni)** della finestra di dialogo **Proprietà server** (pagina**Impostazioni database** ).</span><span class="sxs-lookup"><span data-stu-id="b741f-127">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="b741f-128">Per accedere alla pagina, fare clic con il pulsante destro del mouse sul nome del server in Esplora oggetti e scegliere Proprietà, quindi selezionare la pagina **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="b741f-128">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="b741f-129">Per impostare una data di scadenza specifica per il set di backup, fare clic su **Il**e immettere la data di scadenza del set.</span><span class="sxs-lookup"><span data-stu-id="b741f-129">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b741f-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b741f-130">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="b741f-131">Per impostare la data di scadenza di un backup</span><span class="sxs-lookup"><span data-stu-id="b741f-131">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="b741f-132">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b741f-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b741f-133">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b741f-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b741f-134">Nell'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) , specificare l'opzione EXPIREDATE o RETAINDAYS per determinare quando il [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] può ricoprire il backup.</span><span class="sxs-lookup"><span data-stu-id="b741f-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify either the EXPIREDATE or RETAINDAYS option to determine when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] can overwrite the backup.</span></span> <span data-ttu-id="b741f-135">Se nessuna delle due opzioni viene specificata, la data di scadenza è determinata dall'impostazione di configurazione [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) del server.</span><span class="sxs-lookup"><span data-stu-id="b741f-135">If neither option is specified, the expiration date is determined by the [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) server configuration setting.</span></span> <span data-ttu-id="b741f-136">In questo esempio viene utilizzata l'opzione `EXPIREDATE` per specificare la data di scadenza 30 giugno 2015 (`6/30/2015`).</span><span class="sxs-lookup"><span data-stu-id="b741f-136">This example uses the `EXPIREDATE` option to specify an expiration date of June 30, 2015 (`6/30/2015`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH EXPIREDATE = '6/30/2015' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b741f-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b741f-137">See Also</span></span>  
 <span data-ttu-id="b741f-138">[Creare un backup completo del database &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b741f-138">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="b741f-139">[Backup di file e filegroup &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b741f-139">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="b741f-140">[Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b741f-140">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="b741f-141">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b741f-141">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
