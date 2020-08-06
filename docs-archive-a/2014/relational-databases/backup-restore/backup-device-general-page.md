---
title: Dispositivo di backup (pagina Generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.general.f1
ms.assetid: c557e37d-319e-4adb-a0c1-94189b15d2ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d73bdf3ce4b88214286b5f232924d811716a247e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624778"
---
# <a name="backup-device-general-page"></a><span data-ttu-id="bebd6-102">Dispositivo di backup (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="bebd6-102">Backup Device (General Page)</span></span>
  <span data-ttu-id="bebd6-103">Utilizzare la pagina **Generale** per specificare o visualizzare le proprietà generali di un dispositivo di backup logica.</span><span class="sxs-lookup"><span data-stu-id="bebd6-103">Use the **General** page to specify or view the general properties of a logical backup device.</span></span>  
  
 <span data-ttu-id="bebd6-104">**Per utilizzare SQL Server Management Studio per visualizzare il contenuto di un dispositivo di backup**</span><span class="sxs-lookup"><span data-stu-id="bebd6-104">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="bebd6-105">Visualizzare il contenuto di un nastro o di un file di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-105">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-106">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-106">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="bebd6-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bebd6-107">Options</span></span>  
 <span data-ttu-id="bebd6-108">**Nome dispositivo**</span><span class="sxs-lookup"><span data-stu-id="bebd6-108">**Device name**</span></span>  
 <span data-ttu-id="bebd6-109">Consente di visualizzare il nome di un dispositivo di backup logico esistente o di specificare il nome di un nuovo dispositivo di backup logico.</span><span class="sxs-lookup"><span data-stu-id="bebd6-109">View the name of an existing logical backup device or specify the name of a new logical backup device.</span></span>  
  
 <span data-ttu-id="bebd6-110">**Nastro**</span><span class="sxs-lookup"><span data-stu-id="bebd6-110">**Tape**</span></span>  
 <span data-ttu-id="bebd6-111">Consente di visualizzare o selezionare il dispositivo nastro di destinazione nell'elenco **Nastro** .</span><span class="sxs-lookup"><span data-stu-id="bebd6-111">View or select the destination tape device in the **Tape** list.</span></span> <span data-ttu-id="bebd6-112">L'opzione è disponibile solo se un'unità nastro è collegata al computer su cui è in esecuzione l'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bebd6-112">This option is available only if a tape drive is attached to the computer that is running the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bebd6-113">I dispositivi di backup su nastro collegati a computer remoti non rappresentano destinazioni di backup valide.</span><span class="sxs-lookup"><span data-stu-id="bebd6-113">Tape backup devices on remote computers are not valid backup destinations.</span></span>  
  
 <span data-ttu-id="bebd6-114">**File**</span><span class="sxs-lookup"><span data-stu-id="bebd6-114">**File**</span></span>  
 <span data-ttu-id="bebd6-115">Consente di visualizzare il file di destinazione di un dispositivo di backup logico esistente o di specificare un file di destinazione per un nuovo dispositivo di backup logico.</span><span class="sxs-lookup"><span data-stu-id="bebd6-115">View the destination file of an existing logical backup device, or specify a destination file for a new logical backup device.</span></span>  
  
-   <span data-ttu-id="bebd6-116">Per un dispositivo di backup logico esistente, viene visualizzato il percorso del file di backup.</span><span class="sxs-lookup"><span data-stu-id="bebd6-116">For an existing logical backup device, the path of the backup file is displayed.</span></span> <span data-ttu-id="bebd6-117">Il campo **File** non è modificabile e il pulsante (...) non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="bebd6-117">The **File** field is not editable, and the Browse button is unavailable.</span></span>  
  
-   <span data-ttu-id="bebd6-118">Per un nuovo dispositivo di backup logico, è necessario specificare il percorso del file di backup per il quale si sta definendo il dispositivo di backup logico.</span><span class="sxs-lookup"><span data-stu-id="bebd6-118">For a new logical backup device, you must supply the path of the backup file for which you are defining the logical backup device.</span></span> <span data-ttu-id="bebd6-119">Non è necessario che il file sia già esistente.</span><span class="sxs-lookup"><span data-stu-id="bebd6-119">This file does not have to exist yet.</span></span>  
  
     <span data-ttu-id="bebd6-120">Per specificare un file di backup locale, è possibile fare clic sul pulsante (...) a destra della casella di testo **File** .</span><span class="sxs-lookup"><span data-stu-id="bebd6-120">To specify a local backup file, you can click the Browse button to the right of the **File** text box.</span></span> <span data-ttu-id="bebd6-121">Quindi, nella finestra di dialogo **Individua file di database** è possibile passare a qualsiasi posizione su una delle unità fisse del computer sul quale è in esecuzione l'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="bebd6-121">Then, in the **Locate Database Files** dialog box, you can navigate to any location on any of the fixed drives on the computer running the server instance.</span></span> <span data-ttu-id="bebd6-122">Se il file di backup non esiste ancora, è necessario immettere il nome del file che si desidera utilizzare nel campo **Nome file** della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="bebd6-122">If the backup file does not exist yet, you must enter the filename you want to use in the **File name** field of that dialog box.</span></span>  
  
     <span data-ttu-id="bebd6-123">In alternativa, è possibile modificare il campo **File** manualmente per ignorare il percorso, il nome del file e l'estensione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="bebd6-123">Alternatively, you can edit the **File** field manually to override the default path, file name, and extension.</span></span> <span data-ttu-id="bebd6-124">Per specificare un file remoto come destinazione di backup, utilizzare il nome completo in formato UNC (Universal Naming Convention).</span><span class="sxs-lookup"><span data-stu-id="bebd6-124">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="bebd6-125">Per altre informazioni, vedere [Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bebd6-125">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bebd6-126">Poiché l'esecuzione del backup dei dati in rete può essere soggetta a errori di rete, è consigliabile verificare l'operazione di backup dopo il suo completamento.</span><span class="sxs-lookup"><span data-stu-id="bebd6-126">Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="bebd6-127">Per altre informazioni, vedere [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bebd6-127">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bebd6-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bebd6-128">Remarks</span></span>  
 <span data-ttu-id="bebd6-129">I backup disponibili in un set di uno o più dispositivi di backup costituiscono un singolo set di supporti.</span><span class="sxs-lookup"><span data-stu-id="bebd6-129">The backups on a set of one or more backup devices compose a single media set.</span></span> <span data-ttu-id="bebd6-130">Un *set di supporti* è una raccolta ordinata di supporti di backup, nastri o file su disco, su cui una o più operazioni di backup hanno eseguito la scrittura utilizzando un tipo e un numero fisso di dispositivi di backup.</span><span class="sxs-lookup"><span data-stu-id="bebd6-130">A *media set* is an ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span> <span data-ttu-id="bebd6-131">Per informazioni sui set di supporti, vedere [Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bebd6-131">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="bebd6-132">Il dispositivo di backup fisico corrisponde a un dispositivo di backup logico che viene inizializzata quando il primo backup nel set di supporti viene scritto sul dispositivo di backup logico.</span><span class="sxs-lookup"><span data-stu-id="bebd6-132">The physical backup device corresponding to a logical backup device is initialized when the first backup in the media set is written to the logical backup device.</span></span> <span data-ttu-id="bebd6-133">Se il dispositivo di backup fisico è un file non ancora esistente, viene creato in quel momento.</span><span class="sxs-lookup"><span data-stu-id="bebd6-133">If the physical backup device is a file that does not exist yet, it is created at that time.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="bebd6-134">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="bebd6-134">Related Tasks</span></span>  
  
-   [<span data-ttu-id="bebd6-135">Definire un dispositivo di backup logico per un file su disco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-135">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-136">Definizione di un dispositivo di backup logico per un'unità nastro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-136">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-137">Specificare un disco o un nastro come destinazione di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-137">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-138">Eliminare un dispositivo di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-138">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-139">Impostazione della data di scadenza di un backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-139">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-140">Visualizzare il contenuto di un nastro o di un file di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-140">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-141">Visualizzare i file di dati e i file di log in un set di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-141">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-142">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-142">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="bebd6-143">Ripristinare un backup da un dispositivo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-143">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="bebd6-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bebd6-144">See Also</span></span>  
 <span data-ttu-id="bebd6-145">[Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bebd6-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="bebd6-146">Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bebd6-146">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
