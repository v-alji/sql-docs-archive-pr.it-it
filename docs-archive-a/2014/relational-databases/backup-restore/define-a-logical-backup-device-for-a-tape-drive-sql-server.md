---
title: Definire un dispositivo di backup logico per un'unità nastro (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- tape backup devices, creating
ms.assetid: 66f36e1d-0287-4fac-8a51-71f9f0d7ad5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8728df2cc0b5907e51da84ed9e77d897a1718d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726015"
---
# <a name="define-a-logical-backup-device-for-a-tape-drive-sql-server"></a><span data-ttu-id="44407-102">Definizione di un dispositivo di backup logico per un'unità nastro (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="44407-102">Define a Logical Backup Device for a Tape Drive (SQL Server)</span></span>
  <span data-ttu-id="44407-103">In questo argomento viene descritto come definire un dispositivo di backup logico per un'unità nastro in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44407-103">This topic describes how to define a logical backup device for a tape drive in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="44407-104">Un dispositivo logico è un nome definito dall'utente tramite cui viene fatto riferimento a un dispositivo di backup fisico specifico, ovvero un file su disco o un'unità nastro.</span><span class="sxs-lookup"><span data-stu-id="44407-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="44407-105">L'inizializzazione del dispositivo fisico viene eseguita successivamente, quando viene scritto un backup nel dispositivo di backup.</span><span class="sxs-lookup"><span data-stu-id="44407-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44407-106">Il supporto per i dispositivi di backup su nastro verrà rimosso in una versione futura di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44407-106">Support for tape backup devices will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="44407-107">Evitare di usare questa funzionalità in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui è attualmente implementata.</span><span class="sxs-lookup"><span data-stu-id="44407-107">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="44407-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="44407-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="44407-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="44407-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="44407-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="44407-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="44407-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="44407-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="44407-112">**Per definire un dispositivo di backup logico per un'unità nastro utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="44407-112">**To define a logical backup device for a tape drive, using:**</span></span>  
  
     [<span data-ttu-id="44407-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44407-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="44407-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44407-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="44407-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="44407-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="44407-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="44407-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="44407-117">Le unità nastro devono essere supportate dal sistema operativo Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="44407-117">The tape drive or drives must be supported by the Microsoft Windows operating system.</span></span>  
  
-   <span data-ttu-id="44407-118">Il dispositivo nastro deve essere collegato fisicamente al computer in cui è in esecuzione un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44407-118">The tape device must be connected physically to the computer that is running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="44407-119">Il backup su dispositivi nastro remoti non è supportato.</span><span class="sxs-lookup"><span data-stu-id="44407-119">Backing up to remote tape devices is not supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="44407-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="44407-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="44407-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="44407-121">Permissions</span></span>  
 <span data-ttu-id="44407-122">È richiesta l'appartenenza al ruolo predefinito del server **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="44407-122">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="44407-123">Richiede l'autorizzazione di scrittura sul disco.</span><span class="sxs-lookup"><span data-stu-id="44407-123">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="44407-124">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44407-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="44407-125">Per definire un dispositivo di backup logico per un'unità nastro</span><span class="sxs-lookup"><span data-stu-id="44407-125">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="44407-126">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="44407-126">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="44407-127">Espandere **Oggetti server**, quindi fare clic con il pulsante destro del mouse su **Dispositivi di backup**.</span><span class="sxs-lookup"><span data-stu-id="44407-127">Expand **Server Objects**, and then right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="44407-128">Scegliere **Nuovo dispositivo di backup**e verrà aperta la finestra di dialogo **Dispositivo di backup** .</span><span class="sxs-lookup"><span data-stu-id="44407-128">Click **New Backup Device**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="44407-129">Immettere un nome di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44407-129">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="44407-130">Per la destinazione, fare clic su **Nastro** e selezionare un'unità nastro non ancora associata a un altro dispositivo di backup.</span><span class="sxs-lookup"><span data-stu-id="44407-130">For the destination, click **Tape** and select a tape drive that is not already associated with another backup device.</span></span> <span data-ttu-id="44407-131">Se non sono disponibili unità nastro con queste caratteristiche, l'opzione **Nastro** non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="44407-131">If no such tape drives are available, the **Tape** option is inactive.</span></span>  
  
6.  <span data-ttu-id="44407-132">Per definire il nuovo dispositivo, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44407-132">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="44407-133">Per eseguire il backup in questo nuovo dispositivo, aggiungerlo al campo **Backup su** nella finestra di dialogo **Backup database** (**Generale**).</span><span class="sxs-lookup"><span data-stu-id="44407-133">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="44407-134">Per altre informazioni, vedere [Creare un backup completo del database &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44407-134">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="44407-135">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44407-135">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="44407-136">Per definire un dispositivo di backup logico per un'unità nastro</span><span class="sxs-lookup"><span data-stu-id="44407-136">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="44407-137">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44407-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="44407-138">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="44407-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="44407-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="44407-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="44407-140">Questo esempio mostra come usare [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) per definire un dispositivo di backup logico per un'unità nastro.</span><span class="sxs-lookup"><span data-stu-id="44407-140">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a tape.</span></span> <span data-ttu-id="44407-141">Nell'esempio seguente viene aggiunto il dispositivo di backup su nastro `tapedump1`con nome fisico `\\.\tape0`.</span><span class="sxs-lookup"><span data-stu-id="44407-141">The example adds the tape backup device named `tapedump1`, with the physical name `\\.\tape0`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'tape', 'tapedump1', '\\.\tape0' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="44407-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44407-142">See Also</span></span>  
 <span data-ttu-id="44407-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44407-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="44407-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44407-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="44407-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44407-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="44407-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44407-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="44407-147">[Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="44407-147">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="44407-148">[Definire un dispositivo di backup logico per un file su disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="44407-148">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="44407-149">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="44407-149">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
