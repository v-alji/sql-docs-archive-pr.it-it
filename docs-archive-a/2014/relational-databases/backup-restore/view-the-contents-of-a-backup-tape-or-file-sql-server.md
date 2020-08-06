---
title: Visualizzare il contenuto di un nastro o di un file di backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- displaying backup content
- viewing backup content
- tape backup devices, viewing contents
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
ms.assetid: cd6674a2-ca55-4b5a-a971-878ba001821e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 044519b64d41fbbdfc9302ce24369ab282727f67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718305"
---
# <a name="view-the-contents-of-a-backup-tape-or-file-sql-server"></a><span data-ttu-id="b007a-102">Visualizzare il contenuto di un nastro o di un file di backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b007a-102">View the Contents of a Backup Tape or File (SQL Server)</span></span>
  <span data-ttu-id="b007a-103">In questo argomento si illustra come visualizzare il contenuto di un nastro o file di backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b007a-103">This topic describes how to view the content of a backup tape or file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b007a-104">Il supporto per i dispositivi di backup su nastro verrà rimosso in una versione futura di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b007a-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="b007a-105">Evitare di usare questa funzionalità in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui è attualmente implementata.</span><span class="sxs-lookup"><span data-stu-id="b007a-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="b007a-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b007a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b007a-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b007a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b007a-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b007a-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b007a-109">**Per visualizzare il contenuto di un nastro o di un file di backup utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="b007a-109">**To view the content of a backup tape or file, using:**</span></span>  
  
     [<span data-ttu-id="b007a-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b007a-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b007a-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b007a-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b007a-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b007a-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b007a-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b007a-113">Security</span></span>  
 <span data-ttu-id="b007a-114">Per informazioni sulla sicurezza, vedere [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b007a-114">For information about security, see [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b007a-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b007a-115">Permissions</span></span>  
 <span data-ttu-id="b007a-116">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versioni successive, per ottenere informazioni su un set o un dispositivo di backup è necessario disporre dell'autorizzazione CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="b007a-116">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="b007a-117">Per altre informazioni, vedere [GRANT - autorizzazioni per database &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b007a-117">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b007a-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b007a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="b007a-119">Per visualizzare il contenuto di un nastro o di un file di backup</span><span class="sxs-lookup"><span data-stu-id="b007a-119">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="b007a-120">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="b007a-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b007a-121">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="b007a-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="b007a-122">Fare clic con il pulsante destro del mouse sul database di cui eseguire il backup, scegliere **Attività**e quindi fare clic su **Backup**.</span><span class="sxs-lookup"><span data-stu-id="b007a-122">Right-click the database you want to backup, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="b007a-123">Verrà visualizzata la finestra di dialogo **Backup database** .</span><span class="sxs-lookup"><span data-stu-id="b007a-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b007a-124">Nella sezione **Destinazione** della pagina **Generale** fare clic su **Disco** o **Nastro**.</span><span class="sxs-lookup"><span data-stu-id="b007a-124">In the **Destination** section of the **General** page, click either **Disk** or **Tape**.</span></span> <span data-ttu-id="b007a-125">Nella casella di riepilogo **Backup su** cercare il file su disco o il nastro desiderato.</span><span class="sxs-lookup"><span data-stu-id="b007a-125">In the **Back up to** list box, look for the disk file or tape you want.</span></span>  
  
     <span data-ttu-id="b007a-126">Se il file su disco o il nastro non è visualizzato nella casella di riepilogo, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b007a-126">If the disk file or tape is not displayed in the list-box, click **Add**.</span></span> <span data-ttu-id="b007a-127">Selezionare un nome file o un'unità nastro.</span><span class="sxs-lookup"><span data-stu-id="b007a-127">Select a file name or tape drive.</span></span> <span data-ttu-id="b007a-128">Per aggiungere l'elemento alla casella di riepilogo **Backup su** , fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b007a-128">To add it to the **Back up to** list-box, click **OK**.</span></span>  
  
5.  <span data-ttu-id="b007a-129">Nella casella di riepilogo **Backup su** selezionare il percorso del disco o dell'unità nastro che si desidera visualizzare e quindi fare clic su **Contenuto**.</span><span class="sxs-lookup"><span data-stu-id="b007a-129">In the **Back up to** list-box, select the path of the disk or tape drive you want to view, and click **Contents**.</span></span> <span data-ttu-id="b007a-130">Verrà visualizzata la finestra di dialogo **Contenuto dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="b007a-130">This opens the **Device Contents** dialog box.</span></span>  
  
6.  <span data-ttu-id="b007a-131">Il riquadro di destra visualizza informazioni sul set di supporti e i set di backup sul nastro o sul file selezionato.</span><span class="sxs-lookup"><span data-stu-id="b007a-131">The right-hand pane displays information about the media set and backup sets on the selected tape or file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b007a-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b007a-132">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="b007a-133">Per visualizzare il contenuto di un nastro o di un file di backup</span><span class="sxs-lookup"><span data-stu-id="b007a-133">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="b007a-134">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b007a-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b007a-135">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b007a-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b007a-136">Utilizzare l'istruzione [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="b007a-136">Use the [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) statement.</span></span> <span data-ttu-id="b007a-137">In questo esempio vengono restituite informazioni sul fine denominato `AdventureWorks2012-FullBackup.bak`.</span><span class="sxs-lookup"><span data-stu-id="b007a-137">This example returns information about the file named `AdventureWorks2012-FullBackup.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
RESTORE HEADERONLY   
FROM DISK = N'C:\AdventureWorks2012-FullBackup.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b007a-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b007a-138">See Also</span></span>  
 <span data-ttu-id="b007a-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b007a-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="b007a-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b007a-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="b007a-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b007a-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="b007a-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b007a-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="b007a-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b007a-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="b007a-144">[Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b007a-144">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="b007a-145">[Definire un dispositivo di backup logico per un file su disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b007a-145">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="b007a-146">Definizione di un dispositivo di backup logico per un'unità nastro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b007a-146">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
