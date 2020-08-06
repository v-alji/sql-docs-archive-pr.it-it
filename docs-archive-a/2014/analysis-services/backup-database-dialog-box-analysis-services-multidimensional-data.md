---
title: Finestra di dialogo Backup database (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Backup.f1
ms.assetid: 7811ce7d-6c37-4189-bfa6-ef36fb4932db
author: minewiskan
ms.author: owend
ms.openlocfilehash: 48cf094353c53213864dae656af94ae791442105
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625864"
---
# <a name="backup-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="b083d-102">Finestra di dialogo Backup database (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="b083d-102">Backup Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b083d-103">Usare la finestra di dialogo **Backup database** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per eseguire il backup di un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in un file di backup in formato file di backup di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] con estensione abf.</span><span class="sxs-lookup"><span data-stu-id="b083d-103">Use the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to back up an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b083d-104">Per ogni file di backup, l'utente che esegue il comando di backup deve disporre delle autorizzazioni per scrivere nel percorso di backup specificato per ogni file.</span><span class="sxs-lookup"><span data-stu-id="b083d-104">For each backup file, the user who runs the backup command must have permission to write to the backup location specified for each file.</span></span> <span data-ttu-id="b083d-105">Inoltre, l'utente deve avere uno dei ruoli seguenti: deve essere un membro di un ruolo del server per l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] oppure un membro di un ruolo del database con autorizzazioni Controllo completo (amministratore) sul database di cui eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="b083d-105">Also, the user must have one of the following roles: a member of a server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be backed up.</span></span>  
  
 <span data-ttu-id="b083d-106">**Per visualizzare la finestra di dialogo Backup database**</span><span class="sxs-lookup"><span data-stu-id="b083d-106">**To display the Backup Database dialog box**</span></span>  
  
-   <span data-ttu-id="b083d-107">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]fare clic con il pulsante destro del mouse sulla cartella **Database** di un'istanza [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o su un database in **Esplora oggetti**, quindi fare clic su **Backup**.</span><span class="sxs-lookup"><span data-stu-id="b083d-107">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Backup**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b083d-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b083d-108">Options</span></span>  
 <span data-ttu-id="b083d-109">**Script**</span><span class="sxs-lookup"><span data-stu-id="b083d-109">**Script**</span></span>  
 <span data-ttu-id="b083d-110">Crea uno script di backup basato sulle opzioni selezionate nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b083d-110">Creates a backup script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="b083d-111">Lo script di ripristino è scritto in ASSL ( [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="b083d-111">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="b083d-112">Facendo clic sull'icona **Script** lo script di backup viene inviato in una nuova finestra Query, per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b083d-112">Clicking the **Script** icon sends the backup script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="b083d-113">Facendo clic sulla freccia **Script** viene visualizzato un menu che consente di scegliere dove inviare lo script di backup:</span><span class="sxs-lookup"><span data-stu-id="b083d-113">Clicking the **Script** arrow displays a menu that allows you to choose where to send the backup script:</span></span>  
  
-   <span data-ttu-id="b083d-114">A una nuova finestra Query (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="b083d-114">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="b083d-115">A un file.</span><span class="sxs-lookup"><span data-stu-id="b083d-115">To a file.</span></span>  
  
-   <span data-ttu-id="b083d-116">Negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="b083d-116">To the clipboard.</span></span>  
  
-   <span data-ttu-id="b083d-117">A un processo.</span><span class="sxs-lookup"><span data-stu-id="b083d-117">To a job.</span></span>  
  
 <span data-ttu-id="b083d-118">**Database**</span><span class="sxs-lookup"><span data-stu-id="b083d-118">**Database**</span></span>  
 <span data-ttu-id="b083d-119">Consente di visualizzare il nome del database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="b083d-119">Displays the name of the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="b083d-120">**File di backup**</span><span class="sxs-lookup"><span data-stu-id="b083d-120">**Backup file**</span></span>  
 <span data-ttu-id="b083d-121">Consente di digitare il percorso completo e il nome di file del file di backup da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b083d-121">Type the full path and file name of the backup file to use.</span></span>  
  
 <span data-ttu-id="b083d-122">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="b083d-122">**Browse**</span></span>  
 <span data-ttu-id="b083d-123">Fare clic su questo pulsante per visualizzare la finestra di dialogo **Salva file con nome** e selezionare il percorso e il nome di file del file di backup da usare.</span><span class="sxs-lookup"><span data-stu-id="b083d-123">Click to display the **Save File As** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="b083d-124">Per altre informazioni sulla finestra di dialogo **Salva file con nome** vedere [Finestra di dialogo Salva file con nome &#40;Analysis Services - Dati multidimensionali&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b083d-124">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b083d-125">**Consenti sostituzione file**</span><span class="sxs-lookup"><span data-stu-id="b083d-125">**Allow file overwrite**</span></span>  
 <span data-ttu-id="b083d-126">Selezionare questa opzione per sovrascrivere un file di backup esistente o un file di backup remoto, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="b083d-126">Select to overwrite an existing backup file or remote backup file, if one exists.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b083d-127"> Se questa opzione non viene selezionata e il file di backup specificato in **File di backup** o il file di backup remoto specificato in **File di backup remoto** esiste, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="b083d-127">If this option is not selected and the backup file specified in **Backup file** or a remote backup file specified in **Remote backup file** exists, an error occurs.</span></span>  
  
 <span data-ttu-id="b083d-128">**Applica compressione**</span><span class="sxs-lookup"><span data-stu-id="b083d-128">**Apply compression**</span></span>  
 <span data-ttu-id="b083d-129">Selezionare questa opzione per comprimere il contenuto del file di backup e dei file di backup remoti eventualmente specificati.</span><span class="sxs-lookup"><span data-stu-id="b083d-129">Select to compress the contents of the backup file and, if specified, remote backup files.</span></span>  
  
 <span data-ttu-id="b083d-130">**Crittografa file di backup**</span><span class="sxs-lookup"><span data-stu-id="b083d-130">**Encrypt backup file**</span></span>  
 <span data-ttu-id="b083d-131">Selezionare questa opzione per crittografare il file di backup utilizzando la password specificata in **Password**.</span><span class="sxs-lookup"><span data-stu-id="b083d-131">Select to encrypt the backup file using the password supplied in **Password**.</span></span>  
  
 <span data-ttu-id="b083d-132">**Password**</span><span class="sxs-lookup"><span data-stu-id="b083d-132">**Password**</span></span>  
 <span data-ttu-id="b083d-133">Consente di digitare la password da utilizzare per la crittografia del file di backup e dei file di backup remoti eventualmente specificati.</span><span class="sxs-lookup"><span data-stu-id="b083d-133">Type the password to use when encrypting the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b083d-134"> Questa opzione è attivata solo se viene selezionato **Crittografa file di backup** .</span><span class="sxs-lookup"><span data-stu-id="b083d-134">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="b083d-135">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="b083d-135">**Confirm Password**</span></span>  
 <span data-ttu-id="b083d-136">Consente di digitare la password immessa in **Password** per confermare la password per il file di backup e i file di backup remoti eventualmente specificati.</span><span class="sxs-lookup"><span data-stu-id="b083d-136">Type the password entered in **Password** to confirm the password for the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b083d-137"> Questa opzione è attivata solo se viene selezionato **Crittografa file di backup** .</span><span class="sxs-lookup"><span data-stu-id="b083d-137">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="b083d-138">**Backup partizioni remote**</span><span class="sxs-lookup"><span data-stu-id="b083d-138">**Backup remote partition(s)**</span></span>  
 <span data-ttu-id="b083d-139">Selezionare questa opzione per includere le informazioni sulla partizione e i dati per le partizioni remote nel file di backup.</span><span class="sxs-lookup"><span data-stu-id="b083d-139">Select to include location information and data for remote partitions in the backup file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b083d-140">Questa opzione è attivata solo se il database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] attualmente selezionato utilizza partizioni remote.</span><span class="sxs-lookup"><span data-stu-id="b083d-140">This option is enabled only if the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database uses remote partitions.</span></span>  
  
 <span data-ttu-id="b083d-141">**Percorso backup partizioni remote**</span><span class="sxs-lookup"><span data-stu-id="b083d-141">**Remote partition backup location**</span></span>  
 <span data-ttu-id="b083d-142">Consente di visualizzare il percorso delle partizioni remote associate al database selezionato, nonché il file di backup remoto utilizzato per il backup di dati e metadati per le partizioni remote.</span><span class="sxs-lookup"><span data-stu-id="b083d-142">Displays the location of remote partitions associated with the selected database, as well as the remote backup file used to back up the data and metadata for the remote partitions.</span></span> <span data-ttu-id="b083d-143">Sono disponibili le colonne seguenti.</span><span class="sxs-lookup"><span data-stu-id="b083d-143">The following columns are available:</span></span>  
  
|<span data-ttu-id="b083d-144">Colonna</span><span class="sxs-lookup"><span data-stu-id="b083d-144">Column</span></span>|<span data-ttu-id="b083d-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b083d-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b083d-146">**Server**</span><span class="sxs-lookup"><span data-stu-id="b083d-146">**Server**</span></span>|<span data-ttu-id="b083d-147">Visualizza l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] che gestisce le partizioni remote.</span><span class="sxs-lookup"><span data-stu-id="b083d-147">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that manages the remote partitions.</span></span>|  
|<span data-ttu-id="b083d-148">**Database**</span><span class="sxs-lookup"><span data-stu-id="b083d-148">**Database**</span></span>|<span data-ttu-id="b083d-149">Visualizza il database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] che contiene le partizioni remote.</span><span class="sxs-lookup"><span data-stu-id="b083d-149">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that contains the remote partitions.</span></span>|  
|<span data-ttu-id="b083d-150">**Elenco partizioni**</span><span class="sxs-lookup"><span data-stu-id="b083d-150">**Partition List**</span></span>|<span data-ttu-id="b083d-151">Visualizza l'elenco delle partizioni remote contenute nel database visualizzato in **Database**.</span><span class="sxs-lookup"><span data-stu-id="b083d-151">Displays the list of remote partitions contained by the database displayed in **Database**.</span></span>|  
|<span data-ttu-id="b083d-152">**File di backup remoto**</span><span class="sxs-lookup"><span data-stu-id="b083d-152">**Remote backup file**</span></span>|<span data-ttu-id="b083d-153">Digitare il percorso completo e il nome di file del file di backup remoto da usare oppure fare clic sul pulsante con i puntini di sospensione (**...**) per visualizzare la finestra di dialogo **Salva file con nome** e selezionare il percorso e il nome di file del file di backup remoto da usare.</span><span class="sxs-lookup"><span data-stu-id="b083d-153">Type the full path and file name of the remote backup file to use, or click the ellipsis button (**...**) to display the **Save File As** dialog box and select the path and file name of the remote backup file to use.</span></span> <span data-ttu-id="b083d-154">Per altre informazioni sulla finestra di dialogo **Salva file con nome** vedere [Finestra di dialogo Salva file con nome &#40;Analysis Services - Dati multidimensionali&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b083d-154">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b083d-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b083d-155">See Also</span></span>  
 <span data-ttu-id="b083d-156">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b083d-156">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b083d-157">Backup e ripristino di database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b083d-157">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
