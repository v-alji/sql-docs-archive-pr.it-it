---
title: Contenuto dispositivo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.bnrdevicecontents.f1
ms.assetid: 95e1902e-8c7a-4830-bdf9-1a6aca414a24
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c904718eca671b1965a95d0d400f3f6fa075b500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627840"
---
# <a name="device-contents-sql-server"></a><span data-ttu-id="a75b4-102">Contenuto dispositivo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a75b4-102">Device Contents (SQL Server)</span></span>
  <span data-ttu-id="a75b4-103">Utilizzare questa finestra di dialogo per visualizzazione le informazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-103">Use this dialog box to view the backup information.</span></span> <span data-ttu-id="a75b4-104">Vengono riportate informazioni sul dispositivo, sui supporti, sul set di supporti e sul set o i set di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="a75b4-105">**Per utilizzare SQL Server Management Studio per visualizzare il contenuto di un dispositivo di backup**</span><span class="sxs-lookup"><span data-stu-id="a75b4-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="a75b4-106">Visualizzare il contenuto di un nastro o di un file di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a75b4-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="a75b4-107">Visualizzare le proprietà e il contenuto di un dispositivo di backup logico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a75b4-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="a75b4-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a75b4-108">Options</span></span>  
 <span data-ttu-id="a75b4-109">**Supporti**</span><span class="sxs-lookup"><span data-stu-id="a75b4-109">**Media**</span></span>  
 <span data-ttu-id="a75b4-110">Disco o set di nastri in cui sono archiviate le informazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-110">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="a75b4-111">**Sequenza supporti**</span><span class="sxs-lookup"><span data-stu-id="a75b4-111">**Media sequence**</span></span>  
 <span data-ttu-id="a75b4-112">Consente di visualizzare il numero di sequenza dei supporti, il numero di sequenza del gruppo e l'identificatore del mirror, se disponibili.</span><span class="sxs-lookup"><span data-stu-id="a75b4-112">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="a75b4-113">Ogni supporto di backup fisico è contrassegnato con un numero di sequenza dei supporti che indica l'ordine in cui i supporti sono stati utilizzati.</span><span class="sxs-lookup"><span data-stu-id="a75b4-113">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="a75b4-114">Il supporto di backup iniziale è contrassegnato con 1, il secondo supporto, ovvero il primo nastro di continuità, con 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="a75b4-114">The initial backup medium is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="a75b4-115">Durante il ripristino del set di backup, i numeri di sequenza dei supporti consentono all'operatore che esegue il ripristino del backup di caricare i supporti in base all'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="a75b4-115">When the backup set is restored, the media sequence numbers ensure that the operator that restores the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="a75b4-116">**Data creazione**</span><span class="sxs-lookup"><span data-stu-id="a75b4-116">**Created on**</span></span>  
 <span data-ttu-id="a75b4-117">Visualizza la data dei supporti.</span><span class="sxs-lookup"><span data-stu-id="a75b4-117">Displays the media date.</span></span>  
  
 <span data-ttu-id="a75b4-118">**Set di supporti**</span><span class="sxs-lookup"><span data-stu-id="a75b4-118">**Media Set**</span></span>  
 <span data-ttu-id="a75b4-119">Un set di supporti consiste in una raccolta ordinata di supporti di backup sui quali è stata eseguita la scrittura di una o più operazioni di backup utilizzando un numero costante di dispositivi di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-119">A media set is an ordered collection of backup media to which one or more backup operations have written using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="a75b4-120">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a75b4-120">**Name**</span></span>  
 <span data-ttu-id="a75b4-121">Visualizza il nome del set di supporti.</span><span class="sxs-lookup"><span data-stu-id="a75b4-121">Displays the name of the media set.</span></span>  
  
 <span data-ttu-id="a75b4-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a75b4-122">**Description**</span></span>  
 <span data-ttu-id="a75b4-123">Visualizza la descrizione del set di supporti.</span><span class="sxs-lookup"><span data-stu-id="a75b4-123">Displays the description media set.</span></span>  
  
 <span data-ttu-id="a75b4-124">**Conteggio gruppo di supporti**</span><span class="sxs-lookup"><span data-stu-id="a75b4-124">**Media family count**</span></span>  
 <span data-ttu-id="a75b4-125">Visualizza il conteggio del gruppo di supporti.</span><span class="sxs-lookup"><span data-stu-id="a75b4-125">Displays the media family count.</span></span> <span data-ttu-id="a75b4-126">Ogni set di supporti è un insieme formato da uno o più gruppi di supporti.</span><span class="sxs-lookup"><span data-stu-id="a75b4-126">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="a75b4-127">L'output per un determinato dispositivo di backup individuale o per un gruppo di dispositivi di backup con mirroring forma un gruppo di supporti distinto.</span><span class="sxs-lookup"><span data-stu-id="a75b4-127">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="a75b4-128">Ogni set di supporti contiene un gruppo di supporti per un dispositivo distinto o per un gruppo di dispositivi con mirroring. Ad esempio, se un set di supporti utilizza due dispositivi di backup senza mirroring, il set di supporti conterrà due gruppi di supporti.</span><span class="sxs-lookup"><span data-stu-id="a75b4-128">Each media set contains one media family per separate device (or group of mirrored devices); for example, if a media set uses two nonmirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="a75b4-129">**Set di backup**</span><span class="sxs-lookup"><span data-stu-id="a75b4-129">**Backup sets**</span></span>  
 <span data-ttu-id="a75b4-130">Visualizza informazioni sul set o i set di backup contenuti nel supporto.</span><span class="sxs-lookup"><span data-stu-id="a75b4-130">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="a75b4-131">Un set di backup è il risultato di un'operazione di backup riuscita, il cui contenuto viene distribuito tra i supporti del set di dispositivi di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-131">A backup set is the result of a successful backup operation whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="a75b4-132">Intestazione</span><span class="sxs-lookup"><span data-stu-id="a75b4-132">Header</span></span>|<span data-ttu-id="a75b4-133">Valori</span><span class="sxs-lookup"><span data-stu-id="a75b4-133">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="a75b4-134">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a75b4-134">**Name**</span></span>|<span data-ttu-id="a75b4-135">Nome del set di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-135">The name of the backup set.</span></span>|  
|<span data-ttu-id="a75b4-136">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a75b4-136">**Type**</span></span>|<span data-ttu-id="a75b4-137">Tipo di operazione di backup eseguita: Completo, Differenziale o Log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="a75b4-137">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="a75b4-138">**Componente**</span><span class="sxs-lookup"><span data-stu-id="a75b4-138">**Component**</span></span>|<span data-ttu-id="a75b4-139">Componente di cui è stato eseguito il backup: database, file o *\<blank>* , nel caso dei log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="a75b4-139">The backed-up component: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="a75b4-140">**Server**</span><span class="sxs-lookup"><span data-stu-id="a75b4-140">**Server**</span></span>|<span data-ttu-id="a75b4-141">Nome dell'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-141">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="a75b4-142">**Database**</span><span class="sxs-lookup"><span data-stu-id="a75b4-142">**Database**</span></span>|<span data-ttu-id="a75b4-143">Nome del database di cui è stato eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-143">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="a75b4-144">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="a75b4-144">**Position**</span></span>|<span data-ttu-id="a75b4-145">Posizione del set di backup nel volume.</span><span class="sxs-lookup"><span data-stu-id="a75b4-145">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="a75b4-146">**Data**</span><span class="sxs-lookup"><span data-stu-id="a75b4-146">**Date**</span></span>|<span data-ttu-id="a75b4-147">Data e ora di fine dell'operazione di backup, visualizzate in base alle impostazioni internazionali del client.</span><span class="sxs-lookup"><span data-stu-id="a75b4-147">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="a75b4-148">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="a75b4-148">**Size**</span></span>|<span data-ttu-id="a75b4-149">Dimensioni in byte del set di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-149">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="a75b4-150">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="a75b4-150">**User Name**</span></span>|<span data-ttu-id="a75b4-151">Nome dell'utente che ha eseguito l'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-151">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="a75b4-152">**Scadenza**</span><span class="sxs-lookup"><span data-stu-id="a75b4-152">**Expiration**</span></span>|<span data-ttu-id="a75b4-153">Data e ora di scadenza del set di backup.</span><span class="sxs-lookup"><span data-stu-id="a75b4-153">The date and time the backup set expires.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a75b4-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a75b4-154">See Also</span></span>  
 [<span data-ttu-id="a75b4-155">Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a75b4-155">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
