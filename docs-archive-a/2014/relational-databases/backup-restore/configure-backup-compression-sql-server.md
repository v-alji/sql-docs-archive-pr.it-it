---
title: Configurare la compressione dei backup (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 430905eb-d218-458c-bd48-aeee6fbb7446
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f70994eb64cb6a50b538fd87f03ce7ea2fafe857
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637928"
---
# <a name="configure-backup-compression-sql-server"></a><span data-ttu-id="0777d-102">Configura compressione backup (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0777d-102">Configure Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="0777d-103">In fase di installazione, la compressione dei backup è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0777d-103">At installation, backup compression is off by default.</span></span> <span data-ttu-id="0777d-104">Il comportamento predefinito della compressione dei backup è determinato dall'opzione di configurazione a livello di server **backup compression default** .</span><span class="sxs-lookup"><span data-stu-id="0777d-104">The default behavior for backup compression is defined by the **backup compression default** Option server-level configuration option.</span></span> <span data-ttu-id="0777d-105">È possibile tuttavia eseguire l'override dell'impostazione predefinita a livello del server durante la creazione di un singolo backup o la pianificazione di una serie di backup di routine.</span><span class="sxs-lookup"><span data-stu-id="0777d-105">However, you can override the server-level default when creating a single backup or scheduling a series of routine backups.</span></span> <span data-ttu-id="0777d-106">Per modificare il valore predefinito a livello di server, vedere [Visualizzare o configurare l'opzione di configurazione del server backup compression default](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="0777d-106">To change the server-level default, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
## <a name="override-the-backup-compression-default"></a><span data-ttu-id="0777d-107">Eseguire l'override dell'impostazione predefinita della compressione dei backup</span><span class="sxs-lookup"><span data-stu-id="0777d-107">Override the Backup Compression Default</span></span>  
 <span data-ttu-id="0777d-108">È possibile modificare il comportamento della compressione dei backup per un singolo backup, processo di backup o configurazione per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="0777d-108">You can change the backup compression behavior for an individual backup, backup job, or log shipping configuration.</span></span>  
  
-   **[!INCLUDE[tsql](../../includes/tsql-md.md)]**  
  
     <span data-ttu-id="0777d-109">Per eseguire l'override del valore predefinito di compressione dei backup del server durante la creazione di un backup, usare WITH NO_COMPRESSION o WITH COMPRESSION nell'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0777d-109">To override the server backup-compression default when creating a backup, use either WITH NO_COMPRESSION or WITH COMPRESSION in you [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
     <span data-ttu-id="0777d-110">Per una configurazione per il log shipping, è possibile determinare il comportamento della compressione dei backup dei log usando [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0777d-110">For a log shipping configuration, you can control the backup compression behavior of log backups by using [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span></span>  
  
-   **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
     <span data-ttu-id="0777d-111">Per informazioni su come visualizzare o configurare l'opzione di configurazione del server backup compression default per un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Visualizzare o configurare l'opzione di configurazione del server backup compression default](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="0777d-111">For information about how to view or configure the backup compression default option for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
     <span data-ttu-id="0777d-112">È possibile eseguire l'override dell'opzione backup compression default del server durante la creazione di un backup specificando **Comprimi backup** o **Non comprimere il backup** in una delle finestre di dialogo seguenti:</span><span class="sxs-lookup"><span data-stu-id="0777d-112">You can override the server backup-compression default when creating a backup by specifying **Compress backup** or **Do not compress backup** in any of the following dialog boxes:</span></span>  
  
    -   [<span data-ttu-id="0777d-113">Backup database (pagina Opzioni)</span><span class="sxs-lookup"><span data-stu-id="0777d-113">Back Up Database (Options Page)</span></span>](back-up-database-backup-options-page.md)  
  
         <span data-ttu-id="0777d-114">Quando si esegue il backup di un database, è possibile determinare la compressione dei backup per il backup di un singolo database, file o log.</span><span class="sxs-lookup"><span data-stu-id="0777d-114">When backing up a database, you can control backup compression for an individual database, file, or log backup.</span></span>  
  
    -   [<span data-ttu-id="0777d-115">Utilizzare la Creazione guidata piano di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0777d-115">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
         <span data-ttu-id="0777d-116">La Creazione guidata piano di manutenzione consente di controllare la compressione dei backup per ciascun set di backup completo o differenziale del database o backup del log pianificati.</span><span class="sxs-lookup"><span data-stu-id="0777d-116">The Maintenance Plan Wizard enables you to control backup compression for each set full or differential database backups or log backups that you schedule.</span></span>  
  
    -   <span data-ttu-id="0777d-117">Integration Services (SSIS) [Attività backup database](../../integration-services/control-flow/back-up-database-task.md)</span><span class="sxs-lookup"><span data-stu-id="0777d-117">Integration Services (SSIS) [Back Up Database task](../../integration-services/control-flow/back-up-database-task.md)</span></span>  
  
         <span data-ttu-id="0777d-118">È possibile controllare il comportamento della compressione dei backup durante la creazione di un pacchetto per l'esecuzione del backup di un singolo database o di più database.</span><span class="sxs-lookup"><span data-stu-id="0777d-118">You can control the backup compression behavior when creating a package for backing up a single database or multiple databases.</span></span>  
  
    -   [<span data-ttu-id="0777d-119">Log shipping - Impostazioni backup log delle transazioni</span><span class="sxs-lookup"><span data-stu-id="0777d-119">Log Shipping Transaction Log Backup Settings</span></span>](../databases/log-shipping-transaction-log-backup-settings.md)  
  
         <span data-ttu-id="0777d-120">È possibile determinare il comportamento della compressione dei backup dei log.</span><span class="sxs-lookup"><span data-stu-id="0777d-120">You can control the backup compression behavior of log backups.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="0777d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0777d-121">See Also</span></span>  
 [<span data-ttu-id="0777d-122">Compressione backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0777d-122">Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
  
