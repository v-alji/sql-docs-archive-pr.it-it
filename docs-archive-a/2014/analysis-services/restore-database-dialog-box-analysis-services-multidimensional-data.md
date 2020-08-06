---
title: Finestra di dialogo Ripristina database (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Restore.f1
ms.assetid: a3990d47-55e2-424e-8eac-87edc937e806
author: minewiskan
ms.author: owend
ms.openlocfilehash: f45a41eb10e81e1cfe1100045cc4d00353cb11fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727207"
---
# <a name="restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d76ac-102">Finestra di dialogo Ripristina Database (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="d76ac-102">Restore Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d76ac-103">Usare la finestra di dialogo **Ripristina database** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per ripristinare un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] da un file di backup usando il formato file di backup di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] con estensione abf.</span><span class="sxs-lookup"><span data-stu-id="d76ac-103">Use the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database from a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d76ac-104">Per ogni file di backup, l'utente che esegue il comando di ripristino deve disporre delle autorizzazioni per leggere dal percorso di backup specificato per ogni file.</span><span class="sxs-lookup"><span data-stu-id="d76ac-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="d76ac-105">Per ripristinare un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] non installato nel server, l'utente deve inoltre essere un membro del ruolo del server per l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] specifica.</span><span class="sxs-lookup"><span data-stu-id="d76ac-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="d76ac-106">Per sovrascrivere un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , l'utente deve avere uno dei ruoli seguenti: deve essere un membro del ruolo del server per l'istanza [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o un membro di un ruolo del database con autorizzazioni Controllo completo (amministratore) sul database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="d76ac-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d76ac-107">Dopo avere ripristinato un database esistente, l'utente che ha effettuato l'operazione potrebbe perdere l'accesso al database ripristinato.</span><span class="sxs-lookup"><span data-stu-id="d76ac-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="d76ac-108">Può verificarsi questa perdita di accesso se, al momento dell’esecuzione del backup, l'utente non era un membro del ruolo del server o non era un membro del ruolo del database con autorizzazioni Controllo completo (amministratore).</span><span class="sxs-lookup"><span data-stu-id="d76ac-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="d76ac-109">**Per visualizzare la finestra di dialogo Ripristina database**</span><span class="sxs-lookup"><span data-stu-id="d76ac-109">**To display the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="d76ac-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], fare clic con il pulsante destro del mouse sulla cartella **Database** di un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o su un database in **Esplora oggetti**e quindi fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="d76ac-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Restore**.</span></span>  
  
 <span data-ttu-id="d76ac-111">La finestra di dialogo **Ripristina database** include le seguenti pagine.</span><span class="sxs-lookup"><span data-stu-id="d76ac-111">The **Restore Database** dialog box contains the following pages.</span></span>  
  
## <a name="pages"></a><span data-ttu-id="d76ac-112">Pagine</span><span class="sxs-lookup"><span data-stu-id="d76ac-112">Pages</span></span>  
 <span data-ttu-id="d76ac-113">**Generalee**</span><span class="sxs-lookup"><span data-stu-id="d76ac-113">**General**</span></span>  
 <span data-ttu-id="d76ac-114">Utilizzare questa pagina per selezionare il database da ripristinare, il file di backup dal quale eseguire il ripristino del database, le opzioni generali e la password da utilizzare per il ripristino del database.</span><span class="sxs-lookup"><span data-stu-id="d76ac-114">Use this page to select the database to restore, the backup file from which to restore the database, as well as the general options and password to use while restoring the database.</span></span> <span data-ttu-id="d76ac-115">Per altre informazioni su questa pagina, vedere [Generale &#40;finestra di dialogo Ripristina database&#41; &#40;Analysis Services - Dati multidimensionali&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="d76ac-115">For more information about this page, see [General &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="d76ac-116">**Partizioni**</span><span class="sxs-lookup"><span data-stu-id="d76ac-116">**Partitions**</span></span>  
 <span data-ttu-id="d76ac-117">Utilizzare questa pagina per ripristinare le partizioni locali nei percorsi specificati e per ripristinare le partizioni remote da file di backup remoti.</span><span class="sxs-lookup"><span data-stu-id="d76ac-117">Use this page to restore local partitions to specified locations, and to restore remote partitions from remote backup files.</span></span> <span data-ttu-id="d76ac-118">Per altre informazioni su questa pagina, vedere [Partizioni &#40;finestra di dialogo Ripristina database&#41; &#40;Analysis Services - Dati multidimensionali&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="d76ac-118">For more information about this page, see [Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76ac-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d76ac-119">See Also</span></span>  
 <span data-ttu-id="d76ac-120">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d76ac-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d76ac-121">Backup e ripristino di database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d76ac-121">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
