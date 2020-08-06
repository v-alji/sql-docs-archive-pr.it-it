---
title: Aggiornare Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- upgrading databases
- databases [Analysis Services], upgrading
- installing Analysis Services, side-by-side installations
- Analysis Services upgrades
- Analysis Services upgrades, about upgrading Analysis Services
- SSAS, database migration
- upgrading Analysis Services
- installing Analysis Services, upgrading
- SSAS, upgrading
ms.assetid: a131d329-386e-4470-aaa9-ffcde4e5ec0c
author: Minewiskan
ms.author: owend
ms.openlocfilehash: 78bf7f27233bcfd46bc1f189324eddc72adcc961
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626870"
---
# <a name="upgrade-analysis-services"></a><span data-ttu-id="89fe5-102">Aggiornare Analysis Services</span><span class="sxs-lookup"><span data-stu-id="89fe5-102">Upgrade Analysis Services</span></span>
  <span data-ttu-id="89fe5-103">Utilizzare il programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per aggiornare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89fe5-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="89fe5-104">Per informazioni dettagliate sull'aggiornamento [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità SharePoint, vedere [upgrade PowerPivot per SharePoint](upgrade-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="89fe5-104">For detailed information on upgrading [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in SharePoint mode, see [Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md).</span></span> <span data-ttu-id="89fe5-105">Per ulteriori informazioni sull'aggiornamento di un'istanza di SQL Server esistente, vedere [eseguire l'aggiornamento a SQL Server 2014 utilizzando l'installazione guidata &#40;&#41;di ](upgrade-sql-server-using-the-installation-wizard-setup.md)installazione.</span><span class="sxs-lookup"><span data-stu-id="89fe5-105">For more information about upgrading an existing SQL Server instance, see [Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;](upgrade-sql-server-using-the-installation-wizard-setup.md).</span></span>  
  
## <a name="known-upgrade-issues"></a><span data-ttu-id="89fe5-106">Problemi di aggiornamento noti</span><span class="sxs-lookup"><span data-stu-id="89fe5-106">Known Upgrade Issues</span></span>  
 <span data-ttu-id="89fe5-107">Prima di effettuare l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="89fe5-107">Before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], review the following:</span></span>  
  
-   <span data-ttu-id="89fe5-108">[Note sulla versione di SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="89fe5-108">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
-   <span data-ttu-id="89fe5-109">Per informazioni sulle [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] funzionalità e le funzionalità che sono state sospese, deprecate o modificate, vedere [Analysis Services compatibilità con le versioni precedenti](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span><span class="sxs-lookup"><span data-stu-id="89fe5-109">To learn which [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] features and functionality have been discontinued, deprecated, or changed see [Analysis Services Backward Compatibility](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span></span>  
  
## <a name="pre-upgrade-checklist"></a><span data-ttu-id="89fe5-110">Elenco di controllo preliminare all'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="89fe5-110">Pre-Upgrade Checklist</span></span>  
 <span data-ttu-id="89fe5-111">Prima di eseguire l'aggiornamento, vedere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89fe5-111">Before upgrading, review the following information:</span></span>  
  
-   [<span data-ttu-id="89fe5-112">Aggiornamenti di versione ed edizione supportati</span><span class="sxs-lookup"><span data-stu-id="89fe5-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="89fe5-113">Requisiti hardware e software per l'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="89fe5-113">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
-   [<span data-ttu-id="89fe5-114">Parametri di controllo di Controllo configurazione sistema</span><span class="sxs-lookup"><span data-stu-id="89fe5-114">Check Parameters for the System Configuration Checker</span></span>](check-parameters-for-the-system-configuration-checker.md)  
  
-   [<span data-ttu-id="89fe5-115">Considerazioni sulla sicurezza per un'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="89fe5-115">Security Considerations for a SQL Server Installation</span></span>](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
-   [<span data-ttu-id="89fe5-116">Backup e ripristino di database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="89fe5-116">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
-   [<span data-ttu-id="89fe5-117">Usare la Preparazione aggiornamento per preparare gli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="89fe5-117">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
## <a name="upgrading-analysis-services"></a><span data-ttu-id="89fe5-118">Aggiornamento di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="89fe5-118">Upgrading Analysis Services</span></span>  
 <span data-ttu-id="89fe5-119">È possibile scegliere diversi approcci per aggiornare il server e i dati:</span><span class="sxs-lookup"><span data-stu-id="89fe5-119">You can choose from several approaches to upgrade server and data:</span></span>  
  
-   <span data-ttu-id="89fe5-120">Un **aggiornamento sul posto** sostituisce i file di programma esistenti con [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] i file di programma.</span><span class="sxs-lookup"><span data-stu-id="89fe5-120">An **in-place upgrade** replaces the existing program files with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] program files.</span></span> <span data-ttu-id="89fe5-121">I database rimangono nello stesso percorso.</span><span class="sxs-lookup"><span data-stu-id="89fe5-121">Databases remain in the same location.</span></span> <span data-ttu-id="89fe5-122">Le cartelle del programma vengono aggiornate in modo da riflettere il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="89fe5-122">Program folders are updated to reflect the new name.</span></span>  
  
-   <span data-ttu-id="89fe5-123">Un **aggiornamento affiancato** è una nuova installazione di nello [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] stesso computer in cui è presente un'istanza di Analysis Services esistente.</span><span class="sxs-lookup"><span data-stu-id="89fe5-123">A **side-by-side upgrade** is a new installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on the same computer that has an existing Analysis Services instance.</span></span> <span data-ttu-id="89fe5-124">È possibile spostare database nella nuova istanza dello stesso computer, quindi disinstallare la versione precedente se non viene più utilizzata.</span><span class="sxs-lookup"><span data-stu-id="89fe5-124">You can move databases over to the new instance on the same computer, and then uninstall the old version if you no longer use it.</span></span>  
  
-   <span data-ttu-id="89fe5-125">È possibile inoltre installare Analysis Services in un nuovo hardware e, successivamente, eseguire la migrazione dei database esistenti in tale server.</span><span class="sxs-lookup"><span data-stu-id="89fe5-125">You can also install Analysis Services on new hardware and then migrate existing databases to that server.</span></span>  
  
## <a name="in-place-upgrade"></a><span data-ttu-id="89fe5-126">Aggiornamento sul posto</span><span class="sxs-lookup"><span data-stu-id="89fe5-126">In-place Upgrade</span></span>  
 <span data-ttu-id="89fe5-127">È possibile aggiornare un'istanza esistente di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e, come parte del processo di aggiornamento, eseguire automaticamente la migrazione dei database esistenti dall'istanza precedente alla nuova istanza di.</span><span class="sxs-lookup"><span data-stu-id="89fe5-127">You can upgrade an existing instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and, as part of the upgrade process, automatically migrate existing databases from the old instance to the new instance.</span></span> <span data-ttu-id="89fe5-128">Poiché i metadati e i dati binari sono compatibili tra le due versioni, i dati verranno mantenuti in seguito all'aggiornamento e non sarà necessario eseguirne la migrazione manuale.</span><span class="sxs-lookup"><span data-stu-id="89fe5-128">Because the metadata and binary data is compatible between the two versions, you will retain the data after you upgrade and you do not have to manually migrate the data.</span></span>  
  
 <span data-ttu-id="89fe5-129">Per aggiornare un'istanza esistente, eseguire il programma di installazione e specificare il nome dell'istanza esistente come nome della nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="89fe5-129">To upgrade an existing instance, run Setup and specify the name of the existing instance as the name of the new instance.</span></span>  
  
## <a name="upgrading-databases"></a><span data-ttu-id="89fe5-130">Aggiornamento di database</span><span class="sxs-lookup"><span data-stu-id="89fe5-130">Upgrading Databases</span></span>  
 <span data-ttu-id="89fe5-131">I database creati in versioni precedenti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] vengono eseguiti nel server aggiornato con un'impostazione del livello di compatibilità di database precedente.</span><span class="sxs-lookup"><span data-stu-id="89fe5-131">Databases that were created in previous versions of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] run on the upgraded server under an older database compatibility level setting.</span></span> <span data-ttu-id="89fe5-132">I database creati nelle versioni seguenti dispongono di un livello di compatibilità del database pari a 105.</span><span class="sxs-lookup"><span data-stu-id="89fe5-132">Databases created in the following versions, have a database compatibility level of 105.</span></span> <span data-ttu-id="89fe5-133">È possibile modificare il livello di compatibilità se si desidera utilizzare funzionalità che richiedono un livello di compatibilità del database più recente.</span><span class="sxs-lookup"><span data-stu-id="89fe5-133">You can change the compatibility level if you want to use features that require a newer database compatibility level.</span></span> <span data-ttu-id="89fe5-134">In caso contrario, i database possono essere eseguiti nel server aggiornato utilizzando le impostazioni originali.</span><span class="sxs-lookup"><span data-stu-id="89fe5-134">Otherwise, you can run the databases on the upgraded server using the original settings.</span></span> <span data-ttu-id="89fe5-135">Per ulteriori informazioni, vedere [impostare il livello di compatibilità di un database multidimensionale &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="89fe5-135">For more information, see [Set the Compatibility Level of a Multidimensional Database &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span></span>  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="89fe5-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89fe5-136">See Also</span></span>  
 <span data-ttu-id="89fe5-137">[Funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="89fe5-137">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="89fe5-138">[Pianificazione di un'installazione di SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="89fe5-138">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="89fe5-139">[Informazioni sull'architettura Microsoft OLAP](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span><span class="sxs-lookup"><span data-stu-id="89fe5-139">[Understanding Microsoft OLAP Architecture](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span></span>  
 <span data-ttu-id="89fe5-140">[PowerPivot per SharePoint di aggiornamento](upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="89fe5-140">[Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="89fe5-141">[Installare Analysis Services in modalità multidimensionale e di data mining](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span><span class="sxs-lookup"><span data-stu-id="89fe5-141">[Install Analysis Services in Multidimensional and Data Mining Mode](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span></span>  
 [<span data-ttu-id="89fe5-142">Installazione di PowerPivot per SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="89fe5-142">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
