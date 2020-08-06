---
title: Definire un dispositivo di backup logico per un file su disco (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
ms.assetid: 86331d43-c738-4523-ae3d-7d6700348ed1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8aa92296da81f984f260deace887c15f13443b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726020"
---
# <a name="define-a-logical-backup-device-for-a-disk-file-sql-server"></a><span data-ttu-id="8b21a-102">Definizione di un dispositivo di backup logico per un file su disco (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8b21a-102">Define a Logical Backup Device for a Disk File (SQL Server)</span></span>
  <span data-ttu-id="8b21a-103">In questo argomento viene descritto come definire un dispositivo di backup logico per un file su disco in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b21a-103">This topic describes how to define a logical backup device for a disk file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8b21a-104">Un dispositivo logico è un nome definito dall'utente tramite cui viene fatto riferimento a un dispositivo di backup fisico specifico, ovvero un file su disco o un'unità nastro.</span><span class="sxs-lookup"><span data-stu-id="8b21a-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="8b21a-105">L'inizializzazione del dispositivo fisico viene eseguita successivamente, quando viene scritto un backup nel dispositivo di backup.</span><span class="sxs-lookup"><span data-stu-id="8b21a-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
 <span data-ttu-id="8b21a-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8b21a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8b21a-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8b21a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8b21a-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8b21a-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8b21a-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="8b21a-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="8b21a-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8b21a-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8b21a-111">**Per definire un dispositivo di backup logico per un file su disco utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="8b21a-111">**To define a logical backup device for a disk file, using:**</span></span>  
  
     [<span data-ttu-id="8b21a-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8b21a-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8b21a-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8b21a-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8b21a-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8b21a-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8b21a-115">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="8b21a-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8b21a-116">Il nome del dispositivo logico deve essere univoco tra tutti i dispositivi di backup logici nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="8b21a-116">The logical device name must be unique among all the logical backup devices on the server instance.</span></span> <span data-ttu-id="8b21a-117">Per visualizzare i nomi dei dispositivi logici esistenti, eseguire una query nella vista del catalogo [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8b21a-117">To view the existing logical device names, query the [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) catalog view.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="8b21a-118">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="8b21a-118">Recommendations</span></span>  
  
-   <span data-ttu-id="8b21a-119">È consigliabile utilizzare come disco di backup un disco diverso da quelli in cui sono archiviati i dati di database e i log.</span><span class="sxs-lookup"><span data-stu-id="8b21a-119">We recommend that a backup disk be a different disk than the database data and log disks.</span></span> <span data-ttu-id="8b21a-120">Questa condizione è necessaria per garantire l'accesso ai backup in caso di errore del disco contenente il log o i dati.</span><span class="sxs-lookup"><span data-stu-id="8b21a-120">This is necessary to make sure that you can access the backups if the data or log disk fails.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8b21a-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8b21a-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8b21a-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8b21a-122">Permissions</span></span>  
 <span data-ttu-id="8b21a-123">È richiesta l'appartenenza al ruolo predefinito del server **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="8b21a-123">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="8b21a-124">Richiede l'autorizzazione di scrittura sul disco.</span><span class="sxs-lookup"><span data-stu-id="8b21a-124">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8b21a-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8b21a-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-disk-file"></a><span data-ttu-id="8b21a-126">Per definire un dispositivo di backup logico per un file su disco</span><span class="sxs-lookup"><span data-stu-id="8b21a-126">To define a logical backup device for a disk file</span></span>  
  
1.  <span data-ttu-id="8b21a-127">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="8b21a-127">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="8b21a-128">Espandere **Oggetti server**e fare clic con il pulsante destro del mouse su **Dispositivi di backup**.</span><span class="sxs-lookup"><span data-stu-id="8b21a-128">Expand **Server Objects**, and right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="8b21a-129">Fare clic su **Nuovo dispositivo di backup**.</span><span class="sxs-lookup"><span data-stu-id="8b21a-129">Click **New Backup Device**.</span></span> <span data-ttu-id="8b21a-130">Verrà visualizzata la finestra di dialogo **Dispositivo di backup** .</span><span class="sxs-lookup"><span data-stu-id="8b21a-130">The **Backup Device** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="8b21a-131">Immettere un nome di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b21a-131">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="8b21a-132">Per la destinazione fare clic su **File** e specificare il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="8b21a-132">For the destination, click **File** and specify the full path of the file.</span></span>  
  
6.  <span data-ttu-id="8b21a-133">Per definire il nuovo dispositivo, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b21a-133">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="8b21a-134">Per eseguire il backup in questo nuovo dispositivo, aggiungerlo al campo **Backup su** nella finestra di dialogo **Backup database** (**Generale**).</span><span class="sxs-lookup"><span data-stu-id="8b21a-134">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="8b21a-135">Per altre informazioni, vedere [Creare un backup completo del database &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8b21a-135">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8b21a-136">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8b21a-136">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-for-a-disk-file"></a><span data-ttu-id="8b21a-137">Per definire un backup logico per un file su disco</span><span class="sxs-lookup"><span data-stu-id="8b21a-137">To define a logical backup for a disk file</span></span>  
  
1.  <span data-ttu-id="8b21a-138">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b21a-138">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8b21a-139">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8b21a-139">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8b21a-140">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8b21a-140">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8b21a-141">Questo esempio mostra come usare [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) per definire un dispositivo di backup logico per un file su disco.</span><span class="sxs-lookup"><span data-stu-id="8b21a-141">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a disk file.</span></span> <span data-ttu-id="8b21a-142">L'esempio aggiunge il dispositivo di backup del disco denominato `mydiskdump`, con il nome fisico `c:\dump\dump1.bak`.</span><span class="sxs-lookup"><span data-stu-id="8b21a-142">The example adds the disk backup device named `mydiskdump`, with the physical name `c:\dump\dump1.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mydiskdump', 'c:\dump\dump1.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b21a-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b21a-143">See Also</span></span>  
 <span data-ttu-id="8b21a-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b21a-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="8b21a-145">[Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8b21a-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="8b21a-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b21a-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="8b21a-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b21a-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="8b21a-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b21a-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="8b21a-149">[Definizione di un dispositivo di backup logico per un'unità nastro &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8b21a-149">[Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span></span>  
 [<span data-ttu-id="8b21a-150">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b21a-150">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
