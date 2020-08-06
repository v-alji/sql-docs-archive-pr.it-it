---
title: Attività Pulizia file manutenzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.maintenancecleanuptask.f1
helpviewer_keywords:
- deleting files
- removing files
- Maintenance Cleanup task
ms.assetid: 73ad3cd6-9a6d-44cf-905f-c56aa658bf42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4d39dd775402adadbe51eaadc530f4feb288ab9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627323"
---
# <a name="maintenance-cleanup-task"></a><span data-ttu-id="7ac91-102">Pulizia file manutenzione - attività</span><span class="sxs-lookup"><span data-stu-id="7ac91-102">Maintenance Cleanup Task</span></span>
  <span data-ttu-id="7ac91-103">L'attività Pulizia file manutenzione consente di rimuovere i file correlati ai piani di manutenzione, inclusi i file di backup dei database e i report creati dai piani di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="7ac91-103">The Maintenance Cleanup task removes files related to maintenance plans, including database backup files and reports created by maintenance plans.</span></span> <span data-ttu-id="7ac91-104">Per altre informazioni, vedere [Piani di manutenzione](../../relational-databases/maintenance-plans/maintenance-plans.md) e [Backup e ripristino di database SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7ac91-104">For more information, see [Maintenance Plans](../../relational-databases/maintenance-plans/maintenance-plans.md) and [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="7ac91-105">Tramite l'attività Pulizia file manutenzione un pacchetto può rimuovere dal server specificato i file di backup o i report creati dai piani di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="7ac91-105">By using the Maintenance Cleanup task, a package can remove the backup files or maintenance plan reports on the specified server.</span></span> <span data-ttu-id="7ac91-106">L'attività Pulizia file manutenzione include un'opzione che consente di rimuovere un file specifico oppure un gruppo di file in una cartella.</span><span class="sxs-lookup"><span data-stu-id="7ac91-106">The Maintenance Cleanup task includes an option to remove a specific file or remove a group of files in a folder.</span></span> <span data-ttu-id="7ac91-107">Facoltativamente è possibile specificare l'estensione dei file da eliminare.</span><span class="sxs-lookup"><span data-stu-id="7ac91-107">Optionally you can specify the extension of the files to delete.</span></span>  
  
 <span data-ttu-id="7ac91-108">Quando si configura l'attività Pulizia file manutenzione per la rimozione dei file di backup, l'estensione predefinita è BAK per i file di database</span><span class="sxs-lookup"><span data-stu-id="7ac91-108">When you configure the Maintenance Cleanup task to remove backup files, the default file name extension is BAK.</span></span> <span data-ttu-id="7ac91-109">e TXT per i file di report.</span><span class="sxs-lookup"><span data-stu-id="7ac91-109">For report files, the default file name extension is TXT.</span></span> <span data-ttu-id="7ac91-110">Tali estensioni possono essere modificate in base alle esigenze, purché abbiano una lunghezza inferiore a 256 caratteri.</span><span class="sxs-lookup"><span data-stu-id="7ac91-110">You can update the extensions to suit your needs; the only limitation is that extensions must be less than 256 characters long.</span></span>  
  
 <span data-ttu-id="7ac91-111">Poiché in genere è necessario rimuovere i file obsoleti non più utilizzati, l'attività Pulizia file manutenzione può essere configurata per l'eliminazione dei file che hanno raggiunto un periodo di memorizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="7ac91-111">Typically, you want to remove old files that are no longer needed, and the Maintenance Cleanup task can be configured to delete files that have reached a specified age.</span></span> <span data-ttu-id="7ac91-112">È ad esempio possibile configurare l'attività in modo da eliminare i file che hanno più di quattro settimane.</span><span class="sxs-lookup"><span data-stu-id="7ac91-112">For example, the task can be configured to delete files that are older than four weeks.</span></span> <span data-ttu-id="7ac91-113">Il periodo di memorizzazione dei file da eliminare può essere specificato in giorni, settimane, mesi o anni.</span><span class="sxs-lookup"><span data-stu-id="7ac91-113">You can specify the age of files to delete by using days, weeks, months, or years.</span></span> <span data-ttu-id="7ac91-114">Se non viene specificato il periodo di memorizzazione minimo dei file da eliminare, verranno eliminati tutti i file del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="7ac91-114">If you do not specify the minimum age of files to delete, all files of the specified type are deleted.</span></span>  
  
 <span data-ttu-id="7ac91-115">Diversamente dalle precedenti versioni dell'attività Pulizia file manutenzione, la versione disponibile in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non elimina automaticamente i file presenti nelle sottodirectory della directory specificata.</span><span class="sxs-lookup"><span data-stu-id="7ac91-115">In contrast to earlier versions of the Maintenance Cleanup task, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version of the task does not automatically delete files in the subdirectories of the specified directory.</span></span> <span data-ttu-id="7ac91-116">Questo vincolo riduce la superficie esposta a qualsiasi attacco che potrebbe sfruttare le funzionalità dell'attività Pulizia file manutenzione per eliminare file senza disporre della relativa autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ac91-116">This constraint reduces the surface area of any attack that could exploit the functionality of the Maintenance Cleanup task to delete files maliciously.</span></span> <span data-ttu-id="7ac91-117">Per eliminare le sottocartelle di primo livello è necessario scegliere esplicitamente di eseguire l'operazione selezionando l'opzione **Includi sottocartelle di primo livello** nella finestra di dialogo **Attività Pulizia file manutenzione** .</span><span class="sxs-lookup"><span data-stu-id="7ac91-117">To delete the first-level subfolders, you must explicitly elect to do this by checking the **Include first-level subfolders** option in the **Maintenance Cleanup Task** dialog box.</span></span>  
  
## <a name="configuration-of-the-maintenance-cleanup-task"></a><span data-ttu-id="7ac91-118">Configurazione dell'attività Pulizia file manutenzione</span><span class="sxs-lookup"><span data-stu-id="7ac91-118">Configuration of the Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="7ac91-119">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ac91-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="7ac91-120">Questa attività è disponibile nella sezione **Attività di manutenzione** della **casella degli strumenti** di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ac91-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7ac91-121">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="7ac91-121">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7ac91-122">Attività Pulizia file manutenzione &#40;Piano di manutenzione&#41;</span><span class="sxs-lookup"><span data-stu-id="7ac91-122">Maintenance Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/maintenance-cleanup-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="7ac91-123">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7ac91-123">Related Tasks</span></span>  
 <span data-ttu-id="7ac91-124">Per informazioni dettagliate su come impostare queste proprietà in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Impostazione delle proprietà di un'attività o di un contenitore](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="7ac91-124">For details about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac91-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ac91-125">See Also</span></span>  
 <span data-ttu-id="7ac91-126">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="7ac91-126">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="7ac91-127">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="7ac91-127">Control Flow</span></span>](control-flow.md)  
  
  
