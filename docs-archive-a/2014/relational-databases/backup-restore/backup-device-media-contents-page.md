---
title: Dispositivo di backup (pagina Contenuto supporti)| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.contents.f1
ms.assetid: 5fc7bd22-b6d8-4af1-8a58-2e7d0b994d08
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 07204b5e05ce9fc17e6ea23450066f9f58b7cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629440"
---
# <a name="backup-device-media-contents-page"></a><span data-ttu-id="4bc9c-102">Dispositivo di backup (pagina Contenuto supporti)</span><span class="sxs-lookup"><span data-stu-id="4bc9c-102">Backup Device (Media Contents Page)</span></span>
  <span data-ttu-id="4bc9c-103">Utilizzare la finestra di dialogo **Dispositivo di backup** per visualizzare le informazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-103">Use the **Backup Device** dialog box to view the backup information.</span></span> <span data-ttu-id="4bc9c-104">Vengono riportate informazioni sul dispositivo, sui supporti, sul set di supporti e sul set o i set di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="4bc9c-105">**Per utilizzare SQL Server Management Studio per visualizzare il contenuto di un dispositivo di backup**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="4bc9c-106">Visualizzare il contenuto di un nastro o di un file di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-107">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="4bc9c-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4bc9c-108">Options</span></span>  
 <span data-ttu-id="4bc9c-109">Visualizzare informazioni relative al supporto specifico, al set di supporti e ai set di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-109">View information about the individual media, media set, and backup sets.</span></span>  
  
 <span data-ttu-id="4bc9c-110">**Supporti**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-110">**Media**</span></span>  
 <span data-ttu-id="4bc9c-111">Disco o set di nastri in cui sono archiviate le informazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-111">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="4bc9c-112">**Sequenza supporti**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-112">**Media sequence**</span></span>  
 <span data-ttu-id="4bc9c-113">Consente di visualizzare il numero di sequenza dei supporti, il numero di sequenza del gruppo e l'identificatore del mirror, se disponibili.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-113">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="4bc9c-114">Ogni supporto di backup fisico è contrassegnato con un numero di sequenza dei supporti che indica l'ordine in cui i supporti sono stati utilizzati.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-114">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="4bc9c-115">Il supporto di backup iniziale è contrassegnato con 1, il secondo supporto, ovvero il primo nastro di continuità, con 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-115">The initial backup media is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="4bc9c-116">Quando viene ripristinato il set di backup, i numeri di sequenza dei supporti consentono all'operatore che esegue il ripristino del backup di caricare i supporti in base all'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-116">When the backup set is restored, the media sequence numbers ensure that the operator restoring the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="4bc9c-117">**Data creazione**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-117">**Created on**</span></span>  
 <span data-ttu-id="4bc9c-118">Consente di visualizzare la data e l'ora di creazione del set di supporti.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-118">Displays the creation date and time of the media set.</span></span>  
  
 <span data-ttu-id="4bc9c-119">**Set di supporti**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-119">**Media Set**</span></span>  
 <span data-ttu-id="4bc9c-120">Un set di supporti consiste in una raccolta ordinata di supporti di backup su cui è stata eseguita la scrittura di una o più operazioni di backup utilizzando un numero costante di dispositivi di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-120">A media set is an ordered collection of backup media to which one or more backup operations have written by using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="4bc9c-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-121">**Name**</span></span>  
 <span data-ttu-id="4bc9c-122">Consente di visualizzare il nome del set di supporti, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-122">Displays the name of the media set, if any.</span></span>  
  
 <span data-ttu-id="4bc9c-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-123">**Description**</span></span>  
 <span data-ttu-id="4bc9c-124">Consente di visualizzare la descrizione del set di supporti, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-124">Displays the description of the media set, if any.</span></span>  
  
 <span data-ttu-id="4bc9c-125">**Conteggio gruppo di supporti**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-125">**Media family count**</span></span>  
 <span data-ttu-id="4bc9c-126">Consente di visualizzare il numero di gruppi contenuti nel set di supporti.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-126">Displays the number of families in the media set.</span></span> <span data-ttu-id="4bc9c-127">Ogni set di supporti è un insieme formato da uno o più gruppi di supporti.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-127">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="4bc9c-128">L'output per un determinato dispositivo di backup individuale o per un gruppo di dispositivi di backup con mirroring forma un gruppo di supporti distinto.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-128">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="4bc9c-129">Ogni set di supporti contiene un gruppo di supporti per ciascun dispositivo distinto o per un gruppo di dispositivi con mirroring. Ad esempio, se un set di supporti utilizza due dispositivi di backup senza mirroring, il set di supporti conterrà due gruppi di supporti.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-129">Each media set contains one media family per separate device (or group of mirrored devices); for instance, if a media set uses two non-mirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="4bc9c-130">**Set di backup**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-130">**Backup sets**</span></span>  
 <span data-ttu-id="4bc9c-131">Visualizza informazioni sul set o i set di backup contenuti nel supporto.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-131">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="4bc9c-132">Un set di backup è il risultato di un'operazione di backup riuscita il cui contenuto viene distribuito tra i supporti del set di dispositivi di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-132">A backup set is the result of a successful backup operation, whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="4bc9c-133">Intestazione</span><span class="sxs-lookup"><span data-stu-id="4bc9c-133">Header</span></span>|<span data-ttu-id="4bc9c-134">Valori</span><span class="sxs-lookup"><span data-stu-id="4bc9c-134">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="4bc9c-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-135">**Name**</span></span>|<span data-ttu-id="4bc9c-136">Nome del set di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-136">The name of the backup set.</span></span>|  
|<span data-ttu-id="4bc9c-137">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-137">**Type**</span></span>|<span data-ttu-id="4bc9c-138">Oggetto di cui è stato eseguito il backup: database, file o *\<blank>* , nel caso dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-138">The backed-up object: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="4bc9c-139">**Componente**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-139">**Component**</span></span>|<span data-ttu-id="4bc9c-140">Tipo di operazione di backup eseguita: Completo, Differenziale o Log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-140">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="4bc9c-141">**Server**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-141">**Server**</span></span>|<span data-ttu-id="4bc9c-142">Nome dell'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-142">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="4bc9c-143">**Database**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-143">**Database**</span></span>|<span data-ttu-id="4bc9c-144">Nome del database di cui è stato eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-144">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="4bc9c-145">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-145">**Position**</span></span>|<span data-ttu-id="4bc9c-146">Posizione del set di backup nel volume.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-146">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="4bc9c-147">**Data**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-147">**Date**</span></span>|<span data-ttu-id="4bc9c-148">Data e ora di fine dell'operazione di backup, visualizzate in base alle impostazioni internazionali del client.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-148">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="4bc9c-149">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-149">**Size**</span></span>|<span data-ttu-id="4bc9c-150">Dimensioni in byte del set di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-150">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="4bc9c-151">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-151">**User Name**</span></span>|<span data-ttu-id="4bc9c-152">Nome dell'utente che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-152">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="4bc9c-153">**Scadenza**</span><span class="sxs-lookup"><span data-stu-id="4bc9c-153">**Expiration**</span></span>|<span data-ttu-id="4bc9c-154">Data e ora di scadenza del set di backup.</span><span class="sxs-lookup"><span data-stu-id="4bc9c-154">The date and time the backup set expires.</span></span>|  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4bc9c-155">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4bc9c-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4bc9c-156">Definire un dispositivo di backup logico per un file su disco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-156">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-157">Definizione di un dispositivo di backup logico per un'unità nastro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-157">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-158">Specificare un disco o un nastro come destinazione di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-158">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-159">Eliminare un dispositivo di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-159">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-160">Impostazione della data di scadenza di un backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-160">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-161">Visualizzare il contenuto di un nastro o di un file di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-161">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-162">Visualizzare i file di dati e i file di log in un set di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-162">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-163">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-163">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="4bc9c-164">Ripristinare un backup da un dispositivo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-164">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4bc9c-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bc9c-165">See Also</span></span>  
 <span data-ttu-id="4bc9c-166">[Dispositivi di backup &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4bc9c-166">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="4bc9c-167">Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4bc9c-167">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
