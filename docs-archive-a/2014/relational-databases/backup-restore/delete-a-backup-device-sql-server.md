---
title: Eliminare un dispositivo di backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], deleting devices
- backup devices [SQL Server], deleting
- deleting backup devices
- removing backup devices
- backing up databases [SQL Server], backup devices
ms.assetid: 7be62480-ed6a-4262-a071-1feba73b1c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8734e587a8ecde315fb17120511455a59e38901
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627843"
---
# <a name="delete-a-backup-device-sql-server"></a><span data-ttu-id="0a719-102">Eliminazione di un dispositivo di backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0a719-102">Delete a Backup Device (SQL Server)</span></span>
  <span data-ttu-id="0a719-103">In questo argomento viene descritto come eliminare un dispositivo di backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a719-103">This topic describes how to delete a backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0a719-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0a719-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0a719-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0a719-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0a719-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0a719-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0a719-107">**Per eliminare un dispositivo di backup utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="0a719-107">**To delete a backup device, using:**</span></span>  
  
     [<span data-ttu-id="0a719-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a719-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0a719-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a719-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a719-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0a719-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0a719-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0a719-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0a719-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0a719-112">Permissions</span></span>  
 <span data-ttu-id="0a719-113">È richiesta l'appartenenza al ruolo predefinito del server **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="0a719-113">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0a719-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a719-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="0a719-115">Per eliminare un dispositivo di backup</span><span class="sxs-lookup"><span data-stu-id="0a719-115">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="0a719-116">Dopo aver effettuato la connessione all'istanza appropriata del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="0a719-116">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="0a719-117">Espandere **Oggetti server**e quindi **Dispositivi di backup**.</span><span class="sxs-lookup"><span data-stu-id="0a719-117">Expand **Server Objects**, and then expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="0a719-118">Fare clic con il pulsante destro del mouse sul dispositivo desiderato, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0a719-118">Right-click the device you want, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="0a719-119">Verificare che nella colonna **Nome oggetto** della finestra di dialogo **Elimina oggetto** sia visualizzato il nome corretto del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a719-119">In the **Delete Object** dialog box, verify that the correct device name appears in the **Object Name** column.</span></span>  
  
5.  <span data-ttu-id="0a719-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a719-120">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0a719-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a719-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="0a719-122">Per eliminare un dispositivo di backup</span><span class="sxs-lookup"><span data-stu-id="0a719-122">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="0a719-123">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a719-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0a719-124">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0a719-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0a719-125">Copiare e incollare l'esempio seguente nella query.</span><span class="sxs-lookup"><span data-stu-id="0a719-125">Copy and paste the following example into the query.</span></span> <span data-ttu-id="0a719-126">Questo esempio mostra come usare [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) per eliminare un dispositivo di backup.</span><span class="sxs-lookup"><span data-stu-id="0a719-126">This example shows how to use [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) to delete a backup device.</span></span> <span data-ttu-id="0a719-127">Eseguire il primo esempio per creare il dispositivo di backup `mybackupdisk` e il nome fisico `c:\backup\backup1.bak`.</span><span class="sxs-lookup"><span data-stu-id="0a719-127">Execute the first example to create the `mybackupdisk` backup device and the physical name `c:\backup\backup1.bak`.</span></span> <span data-ttu-id="0a719-128">Eseguire `sp_dropdevice` per eliminare il dispositivo di backup `mybackupdisk`.</span><span class="sxs-lookup"><span data-stu-id="0a719-128">Execute `sp_dropdevice` to delete the `mybackupdisk` backup device.</span></span> <span data-ttu-id="0a719-129">Il parametro `delfile` consente di eliminare il nome fisico.</span><span class="sxs-lookup"><span data-stu-id="0a719-129">The `delfile` parameter deletes the physical name.</span></span>  
  
```sql  
--Define a backup device and physical name.   
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mybackupdisk', 'c:\backup\backup1.bak' ;  
GO  
--Delete the backup device and the physical name.  
USE AdventureWorks2012 ;  
GO  
EXEC sp_dropdevice ' mybackupdisk ', 'delfile' ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a719-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a719-130">See Also</span></span>  
 <span data-ttu-id="0a719-131">[Visualizzazione delle proprietà e del contenuto di un dispositivo di backup logico &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a719-131">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="0a719-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0a719-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="0a719-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0a719-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="0a719-134">[Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a719-134">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="0a719-135">sp_addumpdevice &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0a719-135">sp_addumpdevice &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)  
  
  
