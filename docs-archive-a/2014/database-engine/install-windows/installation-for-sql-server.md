---
title: Installazione per SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 09/09/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
f1_keywords:
- sql12.portal.Installation.f1
helpviewer_keywords:
- installing SQL Server, initial installation
- installation [SQL Server]
- initial installation [SQL Server]
ms.assetid: edd75f68-dc62-4479-a596-57ce8ad632e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 62630400f276b00de8acfa875244558cdb39e47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713428"
---
# <a name="installation-for-sql-server-2014"></a><span data-ttu-id="0dc4e-102">Installazione per SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0dc4e-102">Installation for SQL Server 2014</span></span>
 ## <a name="download-sql-server-2014-express"></a>[<span data-ttu-id="0dc4e-103">Scarica SQL Server 2014 Express</span><span class="sxs-lookup"><span data-stu-id="0dc4e-103">Download SQL Server 2014 Express</span></span>](http://www.hanselman.com/blog/DownloadSQLServerExpress.aspx)
  <span data-ttu-id="0dc4e-104">**Grazie a [Scott Hansel](http://www.hanselman.com/) per la raccolta di tutti i collegamenti al pacchetto di installazione in un'unica posizione.**</span><span class="sxs-lookup"><span data-stu-id="0dc4e-104">**Thank you to [Scott Hanselman](http://www.hanselman.com/) for collecting all of the installer package links in one place!**</span></span>
  
  <span data-ttu-id="0dc4e-105">L'Installazione guidata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornisce un singolo albero delle funzionalità per installare tutti i componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="0dc4e-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard provides a single feature tree to install all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]  
  
-   [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]  
  
-   <span data-ttu-id="0dc4e-106">Strumenti di gestione</span><span class="sxs-lookup"><span data-stu-id="0dc4e-106">Management tools</span></span>  
  
-   <span data-ttu-id="0dc4e-107">Componenti di connettività</span><span class="sxs-lookup"><span data-stu-id="0dc4e-107">Connectivity components</span></span>  
  
 <span data-ttu-id="0dc4e-108">È possibile installare singolarmente ogni componente o selezionare una combinazione dei componenti elencati sopra.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-108">You can install each component individually or select a combination of the components listed above.</span></span> <span data-ttu-id="0dc4e-109">Per effettuare la scelta migliore tra le edizioni e i componenti disponibili in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [edizioni e componenti di SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) e [funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="0dc4e-109">To make the best choice among the editions and components available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) and [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="0dc4e-110">è disponibile nelle edizioni a 32 bit e a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-110">is available in 32-bit and 64-bit editions.</span></span>
 
 <span data-ttu-id="0dc4e-111">**Prova:**</span><span class="sxs-lookup"><span data-stu-id="0dc4e-111">**Try it out:**</span></span>  
  
-   <span data-ttu-id="0dc4e-112">Se si ha un account di Azure,</span><span class="sxs-lookup"><span data-stu-id="0dc4e-112">Have an Azure account?</span></span>  <span data-ttu-id="0dc4e-113">Fare clic **[qui](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** per creare rapidamente una macchina virtuale con SQL Server 2014 Service Pack 1 (SP1) già installato.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-113">Then go **[Here](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** to spin up a Virtual Machine with SQL Server 2014 Service Pack 1 (SP1) already installed.</span></span> <span data-ttu-id="0dc4e-114">Per ulteriori informazioni su SQL Server 2014 (SP1), vedere [le informazioni sulla versione di SQL Server 2014 Service Pack 1](https://support.microsoft.com/kb/3058865).</span><span class="sxs-lookup"><span data-stu-id="0dc4e-114">For more information on SQL Server 2014 (SP1), see [SQL Server 2014 Service Pack 1 release information](https://support.microsoft.com/kb/3058865).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0dc4e-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0dc4e-115">In This Section</span></span>  
 <span data-ttu-id="0dc4e-116">Sia che si utilizzi l'Installazione guidata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o il prompt dei comandi per installare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il processo di installazione prevede i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-116">Regardless of whether you use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or the command prompt to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Setup involves the following steps:</span></span>  
  
 [<span data-ttu-id="0dc4e-117">Pianificazione di un'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0dc4e-117">Planning a SQL Server Installation</span></span>](../../sql-server/install/planning-a-sql-server-installation.md)  
 <span data-ttu-id="0dc4e-118">Viene descritto come preparare il computer per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0dc4e-118">Describes how to prepare your computer for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="0dc4e-119">Requisiti hardware e software.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-119">Hardware and software requirements.</span></span>  
  
-   <span data-ttu-id="0dc4e-120">Requisiti di Controllo configurazione sistema e problemi di blocco.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-120">System Configuration Checker requirements and blocking issues.</span></span>  
  
-   <span data-ttu-id="0dc4e-121">Considerazioni relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-121">Security considerations.</span></span>  
  
 [<span data-ttu-id="0dc4e-122">Installare SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0dc4e-122">Install SQL Server 2014</span></span>](install-sql-server.md)  
 <span data-ttu-id="0dc4e-123">Vengono descritte le opzioni di installazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dc4e-123">Describes installation options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="0dc4e-124">Aggiornamento a SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0dc4e-124">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
 <span data-ttu-id="0dc4e-125">Vengono descritte le opzioni per l'aggiornamento a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dc4e-125">Describes options for upgrading to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="0dc4e-126">Disinstallare SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0dc4e-126">Uninstall SQL Server 2014</span></span>](../../sql-server/install/uninstall-sql-server.md)  
 <span data-ttu-id="0dc4e-127">Vengono descritte le routine per disinstallare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dc4e-127">Describes procedures to uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span></span>  
  
 [<span data-ttu-id="0dc4e-128">Installazione del cluster di failover di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0dc4e-128">SQL Server Failover Cluster Installation</span></span>](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md)  
 <span data-ttu-id="0dc4e-129">In questa sezione della documentazione relativa al programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono descritte le modalità di installazione e configurazione del cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0dc4e-129">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install, and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
 [<span data-ttu-id="0dc4e-130">Installare le funzionalità di business intelligence di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0dc4e-130">Install SQL Server 2014 BI Features</span></span>](../../sql-server/install/install-sql-server-business-intelligence-features.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0dc4e-131">le funzionalità che fanno parte della piattaforma di Microsoft Business Intelligence includono [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e diverse applicazioni client usate per la creazione o l'uso di dati analitici.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-131">features that are part of the Microsoft BI platform include [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and several client applications used for creating or working with analytical data.</span></span> <span data-ttu-id="0dc4e-132">In questa sezione della documentazione relativa al programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene descritto come installare [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dc4e-132">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0dc4e-133">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0dc4e-133">Related Sections</span></span>  
 [<span data-ttu-id="0dc4e-134">Procedure per l'installazione</span><span class="sxs-lookup"><span data-stu-id="0dc4e-134">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
 <span data-ttu-id="0dc4e-135">Vengono forniti i collegamenti agli argomenti sulle procedure per installare [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite l'Installazione guidata, il prompt dei comandi, i file di configurazione e SysPrep.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-135">Provides links to procedural topics for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from the installation wizard, from the command prompt, by using configuration files, and by using SysPrep.</span></span>  
  
 [<span data-ttu-id="0dc4e-136">Installare SQL Server funzionalità di business intelligence con SharePoint &#40;PowerPivot e Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0dc4e-136">Install SQL Server BI Features with SharePoint &#40;PowerPivot and Reporting Services&#41;</span></span>](../../sql-server/install/install-sql-server-bi-features-sharepoint-powerpivot-reporting-services.md)  
 <span data-ttu-id="0dc4e-137">In questa sezione viene illustrato come installare funzionalità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un ambiente SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-137">This section explains how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features in a SharePoint environment.</span></span> <span data-ttu-id="0dc4e-138">e vengono identificate le funzionalità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibili in una versione ed edizione specifiche di SharePoint</span><span class="sxs-lookup"><span data-stu-id="0dc4e-138">It identifies which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features are available given a specific version and edition of SharePoint.</span></span> <span data-ttu-id="0dc4e-139">Nella sezione sono inoltre incluse procedure di installazione per PowerPivot per SharePoint e per Reporting Services in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-139">It also includes installation procedures for PowerPivot for SharePoint and Reporting Services in SharePoint mode.</span></span>  
  
 [<span data-ttu-id="0dc4e-140">Installazione degli esempi e dei database di esempio di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0dc4e-140">Installing SQL Server Samples and Sample Databases</span></span>](https://sqlserversamples.codeplex.com/)  
 <span data-ttu-id="0dc4e-141">Viene descritto come installare e configurare gli esempi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e i database di esempio.</span><span class="sxs-lookup"><span data-stu-id="0dc4e-141">Describes how to install and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples and sample databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc4e-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dc4e-142">See Also</span></span>  
 <span data-ttu-id="0dc4e-143">[Novità nell'installazione di SQL Server](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="0dc4e-143">[What's New in SQL Server Installation](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="0dc4e-144">Requisiti hardware e software per l'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0dc4e-144">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
