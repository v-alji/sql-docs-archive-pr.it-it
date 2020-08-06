---
title: Generale (finestra di dialogo Ripristina database) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.restoredbdialog.f1
ms.assetid: 319e7ef5-c9c7-4e50-8690-02a90aed006f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25a49e17227fc2ed6b7b18d2e0964cd8812cbdcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637492"
---
# <a name="general-restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="70ebb-102">Generale (finestra di dialogo Ripristina Database) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="70ebb-102">General (Restore Database Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="70ebb-103">Utilizzare la pagina **Generale** della finestra di dialogo **Ripristina database** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per specificare il file di backup e le impostazioni generali da utilizzare per ripristinare un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70ebb-103">Use the **General** page of the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to specify the backup file and general settings to use when restoring an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="70ebb-104">Per ogni file di backup, l'utente che esegue il comando di ripristino deve disporre delle autorizzazioni per leggere dal percorso di backup specificato per ogni file.</span><span class="sxs-lookup"><span data-stu-id="70ebb-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="70ebb-105">Per ripristinare un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] non installato nel server, l'utente deve inoltre essere un membro del ruolo del server per l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] specifica.</span><span class="sxs-lookup"><span data-stu-id="70ebb-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="70ebb-106">Per sovrascrivere un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , l'utente deve avere uno dei ruoli seguenti: deve essere un membro del ruolo del server per l'istanza [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o un membro di un ruolo del database con autorizzazioni Controllo completo (amministratore) sul database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="70ebb-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70ebb-107">Dopo avere ripristinato un database esistente, l'utente che ha effettuato l'operazione potrebbe perdere l'accesso al database ripristinato.</span><span class="sxs-lookup"><span data-stu-id="70ebb-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="70ebb-108">Può verificarsi questa perdita di accesso se, al momento dell’esecuzione del backup, l'utente non era un membro del ruolo del server o non era un membro del ruolo del database con autorizzazioni Controllo completo (amministratore).</span><span class="sxs-lookup"><span data-stu-id="70ebb-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="70ebb-109">**Per visualizzare la pagina Generale nella finestra di dialogo Ripristina Database**</span><span class="sxs-lookup"><span data-stu-id="70ebb-109">**To display the General page in the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="70ebb-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], fare clic con il pulsante destro del mouse sulla cartella **Database** di un'istanza [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o sul database in **Esplora oggetti**, fare clic su **Ripristina**, quindi su **Seleziona una pagina**fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="70ebb-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, click **Restore**, and then under **Select a page**, click **General**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70ebb-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="70ebb-111">Options</span></span>  
 <span data-ttu-id="70ebb-112">**Script**</span><span class="sxs-lookup"><span data-stu-id="70ebb-112">**Script**</span></span>  
 <span data-ttu-id="70ebb-113">Crea uno script di ripristino basato sulle opzioni selezionate nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="70ebb-113">Creates a restore script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="70ebb-114">Lo script di ripristino è scritto in ASSL ( [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="70ebb-114">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="70ebb-115">Facendo clic sull'icona **Script** lo script di ripristino viene inviato in una nuova finestra Query, per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="70ebb-115">Clicking the **Script** icon sends the restore script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="70ebb-116">Facendo clic sulla freccia **Script** viene visualizzato un menu che consente di scegliere dove inviare lo script di ripristino:</span><span class="sxs-lookup"><span data-stu-id="70ebb-116">Clicking the **Script** arrow displays a menu that allows you to choose where to send the restore script:</span></span>  
  
-   <span data-ttu-id="70ebb-117">A una nuova finestra Query (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="70ebb-117">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="70ebb-118">A un file.</span><span class="sxs-lookup"><span data-stu-id="70ebb-118">To a file.</span></span>  
  
-   <span data-ttu-id="70ebb-119">Negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="70ebb-119">To the clipboard.</span></span>  
  
-   <span data-ttu-id="70ebb-120">A un processo.</span><span class="sxs-lookup"><span data-stu-id="70ebb-120">To a job.</span></span>  
  
 <span data-ttu-id="70ebb-121">**RESTORE DATABASE**</span><span class="sxs-lookup"><span data-stu-id="70ebb-121">**Restore database**</span></span>  
 <span data-ttu-id="70ebb-122">Consente di selezionare il database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="70ebb-122">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to restore.</span></span>  
  
 <span data-ttu-id="70ebb-123">**Da file di backup**</span><span class="sxs-lookup"><span data-stu-id="70ebb-123">**From backup file**</span></span>  
 <span data-ttu-id="70ebb-124">Consente di selezionare il file di backup dal quale ripristinare il database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selezionato.</span><span class="sxs-lookup"><span data-stu-id="70ebb-124">Select the backup file from which to restore the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="70ebb-125">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="70ebb-125">**Browse**</span></span>  
 <span data-ttu-id="70ebb-126">Fare clic su questo pulsante per visualizzare la finestra di dialogo **Trova file di database** e selezionare il percorso e il nome del file di backup da usare.</span><span class="sxs-lookup"><span data-stu-id="70ebb-126">Click to display the **Locate Database Files** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="70ebb-127">Per altre informazioni sulla finestra di dialogo **Trova file di database**, vedere [Finestra di dialogo Individua file di database &#40;Analysis Services - Dati multidimensionali&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="70ebb-127">For more information about the **Locate Database Files** dialog box, see [Locate Database Files Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="70ebb-128">**Consenti sostituzione database**</span><span class="sxs-lookup"><span data-stu-id="70ebb-128">**Allow database overwrite**</span></span>  
 <span data-ttu-id="70ebb-129">Selezionare questa opzione per consentire a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] di ripristinare il contenuto del file di backup selezionato sostituendolo a qualsiasi oggetto esistente nel database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selezionato.</span><span class="sxs-lookup"><span data-stu-id="70ebb-129">Select to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to restore the contents of the selected backup file over any existing objects in the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="70ebb-130">**Includi informazioni di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="70ebb-130">**Include security information**</span></span>  
 <span data-ttu-id="70ebb-131">Selezionare questa opzione per copiare le eventuali informazioni di sicurezza archiviate nel file di backup sul database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70ebb-131">Select to copy any security information stored in the backup file to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="70ebb-132">Selezionando questa opzione viene reso disponibile un elenco a discesa che consente di scegliere la quantità di informazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="70ebb-132">If this option is selected, you can choose the amount of security information from the drop-down list enabled by selecting this option.</span></span> <span data-ttu-id="70ebb-133">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="70ebb-133">The following options are available:</span></span>  
  
|<span data-ttu-id="70ebb-134">Opzione</span><span class="sxs-lookup"><span data-stu-id="70ebb-134">Option</span></span>|<span data-ttu-id="70ebb-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70ebb-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="70ebb-136">**Copia tutto**</span><span class="sxs-lookup"><span data-stu-id="70ebb-136">**Copy All**</span></span>|<span data-ttu-id="70ebb-137">Ripristina i ruoli del database inclusi nel file di backup, nonché agli account utente associati ai ruoli.</span><span class="sxs-lookup"><span data-stu-id="70ebb-137">Restores the database roles contained in the backup file, as well as the user accounts associated with the roles.</span></span>|  
|<span data-ttu-id="70ebb-138">**Ignora appartenenze**</span><span class="sxs-lookup"><span data-stu-id="70ebb-138">**Skip Membership**</span></span>|<span data-ttu-id="70ebb-139">Ripristina i ruoli del database inclusi nel file di backup, ma non ripristina gli account utente associati ai ruoli.</span><span class="sxs-lookup"><span data-stu-id="70ebb-139">Restores the database roles contained in the backup file, but does not restore the user accounts associated with the roles.</span></span>|  
  
 <span data-ttu-id="70ebb-140">**Password**</span><span class="sxs-lookup"><span data-stu-id="70ebb-140">**Password**</span></span>  
 <span data-ttu-id="70ebb-141">Se il file di backup è crittografato, digitare la password utilizzata per crittografare il file di backup.</span><span class="sxs-lookup"><span data-stu-id="70ebb-141">If the backup file is encrypted, type the password used to encrypt the backup file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ebb-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70ebb-142">See Also</span></span>  
 <span data-ttu-id="70ebb-143">[Finestra di dialogo Ripristina database &#40;Analysis Services-Dati multidimensionali&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="70ebb-143">[Restore Database Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="70ebb-144">[Partizioni &#40;finestra di dialogo Ripristina database&#41; &#40;Analysis Services Dati multidimensionali&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="70ebb-144">[Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="70ebb-145">Backup e ripristino di database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="70ebb-145">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
