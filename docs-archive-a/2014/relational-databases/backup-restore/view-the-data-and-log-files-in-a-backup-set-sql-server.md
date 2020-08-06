---
title: Visualizzare i file di dati e i file di log in un set di backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], viewing backup sets
- viewing backup set information
- backup sets [SQL Server], viewing files in
- displaying backup set information
- transaction log backups [SQL Server], viewing backup sets
- backing up [SQL Server], viewing backup sets
ms.assetid: abb6420c-f809-426e-aeb4-d0a74989cf39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7dbcb14a658b49aba6f5f2ebe3425a2ab5759efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718300"
---
# <a name="view-the-data-and-log-files-in-a-backup-set-sql-server"></a><span data-ttu-id="b11a2-102">Visualizzare i file di dati e i file di log in un set di backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b11a2-102">View the Data and Log Files in a Backup Set (SQL Server)</span></span>
  <span data-ttu-id="b11a2-103">In questo argomento viene descritto come visualizzare i file di log e di dati in un set di backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b11a2-103">This topic describes how to view the data and log files in a backup set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b11a2-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b11a2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b11a2-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b11a2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b11a2-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b11a2-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b11a2-107">**Per visualizzare i file di dati e i file di log in un set di backup utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="b11a2-107">**To view the data and log files in a backup set, using:**</span></span>  
  
     [<span data-ttu-id="b11a2-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b11a2-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b11a2-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b11a2-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b11a2-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b11a2-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b11a2-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b11a2-111">Security</span></span>  
 <span data-ttu-id="b11a2-112">Per informazioni sulla sicurezza, vedere [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b11a2-112">For information about security, see [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b11a2-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b11a2-113">Permissions</span></span>  
 <span data-ttu-id="b11a2-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versioni successive, per ottenere informazioni su un set o un dispositivo di backup è necessario disporre dell'autorizzazione CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="b11a2-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="b11a2-115">Per altre informazioni, vedere [GRANT - autorizzazioni per database &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b11a2-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b11a2-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b11a2-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="b11a2-117">Per visualizzare i file di dati e i file di log in un set di backup</span><span class="sxs-lookup"><span data-stu-id="b11a2-117">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="b11a2-118">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="b11a2-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b11a2-119">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="b11a2-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="b11a2-120">Fare clic con il pulsante destro del mouse sul database e quindi scegliere **Proprietà**per visualizzare la finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="b11a2-120">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="b11a2-121">Nel riquadro **Selezione pagina** fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="b11a2-121">In the **Select a Page** pane, click **Files**.</span></span>  
  
5.  <span data-ttu-id="b11a2-122">Nella griglia **File di database** è visualizzato un elenco dei file di dati e dei file di log e delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="b11a2-122">Look in the **Database files** grid for a list of the data and log files and their properties.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b11a2-123">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b11a2-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="b11a2-124">Per visualizzare i file di dati e i file di log in un set di backup</span><span class="sxs-lookup"><span data-stu-id="b11a2-124">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="b11a2-125">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b11a2-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b11a2-126">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b11a2-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b11a2-127">Utilizzare l'istruzione [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="b11a2-127">Use the [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) statement.</span></span> <span data-ttu-id="b11a2-128">In questo esempio vengono restituite informazioni sul secondo set di backup (`FILE=2`) nel dispositivo di backup `AdventureWorksBackups` .</span><span class="sxs-lookup"><span data-stu-id="b11a2-128">This example returns information about the second backup set (`FILE=2`) on the `AdventureWorksBackups` backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE FILELISTONLY FROM AdventureWorksBackups   
   WITH FILE=2;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b11a2-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b11a2-129">See Also</span></span>  
 <span data-ttu-id="b11a2-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b11a2-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="b11a2-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b11a2-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="b11a2-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b11a2-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="b11a2-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b11a2-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="b11a2-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b11a2-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 [<span data-ttu-id="b11a2-135">Dispositivi di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b11a2-135">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
