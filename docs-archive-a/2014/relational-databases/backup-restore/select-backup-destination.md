---
title: Seleziona destinazione di backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdest.f1
ms.assetid: f79e824b-1525-45de-8ede-513563af41b6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ffd1d2529dd13e42689bcf168c972d757fb5499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635661"
---
# <a name="select-backup-destination"></a><span data-ttu-id="28b9f-102">Seleziona destinazione di backup</span><span class="sxs-lookup"><span data-stu-id="28b9f-102">Select Backup Destination</span></span>
  <span data-ttu-id="28b9f-103">Usare la finestra di dialogo **Seleziona destinazione di backup** per selezionare un dispositivo come destinazione di backup.</span><span class="sxs-lookup"><span data-stu-id="28b9f-103">Use the **Select Backup Destination** dialog box to select a device as your backup destination.</span></span> <span data-ttu-id="28b9f-104">La destinazione di backup può essere un disco o un dispositivo di backup logico.</span><span class="sxs-lookup"><span data-stu-id="28b9f-104">A backup destination can be either a disk or a logical backup device.</span></span>  
  
 <span data-ttu-id="28b9f-105">**Per utilizzare SQL Server Management Studio per l'esecuzione del backup di un database**</span><span class="sxs-lookup"><span data-stu-id="28b9f-105">**To use SQL Server Management Studio to back up a database**</span></span>  
  
-   [<span data-ttu-id="28b9f-106">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28b9f-106">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="28b9f-107">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28b9f-107">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="28b9f-108">Backup di file e filegroup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28b9f-108">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="28b9f-109">Eseguire il backup di un log delle transazioni &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28b9f-109">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="28b9f-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="28b9f-110">Options</span></span>  
 <span data-ttu-id="28b9f-111">Le opzioni disponibili in questa finestra di dialogo variano a seconda che si selezioni una destinazione su disco o su nastro.</span><span class="sxs-lookup"><span data-stu-id="28b9f-111">The options of this dialog box depend on whether you are selecting a destination on disk or on tape.</span></span>  
  
 <span data-ttu-id="28b9f-112">**Destinazioni su disco**</span><span class="sxs-lookup"><span data-stu-id="28b9f-112">**Destination on disk**</span></span>  
 <span data-ttu-id="28b9f-113">Per specificare una destinazione di backup, scegliere una delle opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="28b9f-113">To specify a backup destination, choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28b9f-114">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="28b9f-114">**File name**</span></span>|<span data-ttu-id="28b9f-115">Scegliere questa opzione per immettere il nome di un file locale o remoto da utilizzare come destinazione di backup nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="28b9f-115">Choose this option to enter a local or remote file as the backup destination in the text box.</span></span><br /><br /> <span data-ttu-id="28b9f-116">Per specificare un file locale, fare clic sul pulsante Sfoglia a destra della casella di testo e individuare il file nei dischi rigidi del computer che esegue il server oppure digitare direttamente il nome e il percorso completo del file, ad esempio `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak`.</span><span class="sxs-lookup"><span data-stu-id="28b9f-116">To specify a local file, click the browse button to the right of the text box and navigate to a file on the fixed drives of the computer running the server, or enter the full path and file name directly; for example, `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak`.</span></span><br /><br /> <span data-ttu-id="28b9f-117">Per specificare un file remoto come destinazione di backup, utilizzare il nome completo in formato UNC (Universal Naming Convention).</span><span class="sxs-lookup"><span data-stu-id="28b9f-117">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="28b9f-118">Per altre informazioni, vedere [Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28b9f-118">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span><br /><br /> <span data-ttu-id="28b9f-119">**\*\* Importante \*\*** L'esecuzione del backup dei dati in rete può essere soggetta a errori di rete, quindi è consigliabile verificare l'operazione di backup dopo il suo completamento.</span><span class="sxs-lookup"><span data-stu-id="28b9f-119">**\*\* Important \*\*** Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="28b9f-120">Per altre informazioni, vedere [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="28b9f-120">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>|  
|<span data-ttu-id="28b9f-121">**Dispositivo di backup**</span><span class="sxs-lookup"><span data-stu-id="28b9f-121">**Backup device**</span></span>|<span data-ttu-id="28b9f-122">Scegliere questa opzione per selezionare un dispositivo di backup logico.</span><span class="sxs-lookup"><span data-stu-id="28b9f-122">Choose this option to select a logical backup device.</span></span><br /><br /> <span data-ttu-id="28b9f-123">Nota: per informazioni su come creare un dispositivo di backup su disco, vedere [Definizione di un dispositivo di backup logico per un file su disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28b9f-123">Note: For information about how to create a disk backup device, see [Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span></span>|  
  
 <span data-ttu-id="28b9f-124">**Destinazioni su nastro**</span><span class="sxs-lookup"><span data-stu-id="28b9f-124">**Destination on tape**</span></span>  
 <span data-ttu-id="28b9f-125">Consente di specificare una destinazione di backup su un'unità nastro fisicamente collegata al computer che esegue il server, ovvero l'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28b9f-125">Specify a backup destination on a tape drive physically connected to the computer running the server (that is, the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span></span> <span data-ttu-id="28b9f-126">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="28b9f-126">Choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28b9f-127">**Unità nastro**</span><span class="sxs-lookup"><span data-stu-id="28b9f-127">**Tape drive**</span></span>|<span data-ttu-id="28b9f-128">Scegliere questa opzione per selezionare un'unità nastro come destinazione del backup dall'elenco delle unità nastro fisicamente collegate al computer che esegue l'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="28b9f-128">Choose this option to select a tape drive as the backup destination from the list of tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="28b9f-129">Nota: I dispositivi di backup su nastro collegati a computer remoti non rappresentano destinazioni di backup valide.</span><span class="sxs-lookup"><span data-stu-id="28b9f-129">Note: Tape backup devices on remote computers are not valid backup destinations.</span></span>|  
|<span data-ttu-id="28b9f-130">**Dispositivo di backup**</span><span class="sxs-lookup"><span data-stu-id="28b9f-130">**Backup device**</span></span>|<span data-ttu-id="28b9f-131">Scegliere questa opzione per selezionare un dispositivo di backup logico esistente.</span><span class="sxs-lookup"><span data-stu-id="28b9f-131">Choose this option to select an existing logical backup device.</span></span> <span data-ttu-id="28b9f-132">Questi dispositivi di backup logici corrispondono a unità nastro fisicamente collegate al computer che esegue l'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="28b9f-132">These logical backup devices correspond to tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="28b9f-133">Nota: per informazioni su come creare un dispositivo di backup su nastro, vedere [Definizione di un dispositivo di backup logico per un'unità nastro &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28b9f-133">Note: For information about how to create a tape backup device, see [Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28b9f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28b9f-134">See Also</span></span>  
 <span data-ttu-id="28b9f-135">[Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28b9f-135">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="28b9f-136">Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28b9f-136">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
