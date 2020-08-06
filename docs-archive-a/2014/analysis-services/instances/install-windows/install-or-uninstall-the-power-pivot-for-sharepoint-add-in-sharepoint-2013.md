---
title: Installare o disinstallare il componente aggiuntivo PowerPivot per SharePoint (SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: fe13ce8b-9369-4126-928a-9426f9119424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7df54d11021163167149e5b0c1edd960fee1a2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713600"
---
# <a name="install-or-uninstall-the-powerpivot-for-sharepoint-add-in-sharepoint-2013"></a><span data-ttu-id="3a8ee-102">Installare o disinstallare il componente aggiuntivo PowerPivot per SharePoint (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="3a8ee-102">Install or Uninstall the PowerPivot for SharePoint Add-in (SharePoint 2013)</span></span>
  [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="3a8ee-103">è una raccolta di servizi back-end e componenti del server applicazioni che forniscono l'accesso a dati [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in una farm di [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a8ee-103">is a collection of application server components and back-end services that provide [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] data access in a [!INCLUDE[SPS2013](../../../includes/sps2013-md.md)] farm.</span></span> <span data-ttu-id="3a8ee-104">Il componente aggiuntivo [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] per SharePoint (**spPowerpivot.msi**) è un pacchetto di installazione utilizzato per installare i componenti del server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-104">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint add-in (**spPowerpivot.msi**) is an installer package used to install the application server components.</span></span>

-   <span data-ttu-id="3a8ee-105">Il componente aggiuntivo non è necessario per le distribuzioni di SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-105">The add-in is not required for SharePoint 2010 deployments.</span></span>

-   <span data-ttu-id="3a8ee-106">Il componente aggiuntivo non è necessario in una distribuzione a server singolo che prevede SharePoint 2013 e [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-106">The add-in is not required on a single server deployment that includes SharePoint 2013 and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="3a8ee-107">I componenti installati con il componente aggiuntivo vengono inclusi quando si installa un server [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-107">The components installed by the add-in are included when you install an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server in SharePoint mode.</span></span> <span data-ttu-id="3a8ee-108">Per i diagrammi di distribuzioni di esempio con il componente aggiuntivo, vedere [topologie di distribuzione per SQL Server le funzionalità di business intelligence in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="3a8ee-108">For diagrams of example deployments with the add-in, see [Deployment Topologies for SQL Server BI Features in SharePoint](../../../sql-server/install/deployment-topologies-for-sql-server-bi-features-in-sharepoint.md).</span></span>

 <span data-ttu-id="3a8ee-109">**Nota:** in questo argomento vengono fornite informazioni sull'installazione dei file di soluzione [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] e dello strumento di configurazione di [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] per SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-109">**Note:** This topic describes installing the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] solution files and [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span> <span data-ttu-id="3a8ee-110">Al termine dell'installazione, vedere l'argomento seguente per informazioni sullo strumento di configurazione e sulle funzionalità aggiuntive, [configurare PowerPivot e distribuire soluzioni &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="3a8ee-110">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

 <span data-ttu-id="3a8ee-111">Per informazioni su come scaricare **spPowerPivot.msi**, vedere la pagina relativa a [Microsoft® SQL Server® 2014 PowerPivot® per Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span><span class="sxs-lookup"><span data-stu-id="3a8ee-111">For information on how to download **spPowerPivot.msi**, see [Microsoft® SQL Server® 2014 PowerPivot® for Microsoft SharePoint®](https://go.microsoft.com/fwlink/?LinkID=324854).</span></span>

 <span data-ttu-id="3a8ee-112">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="3a8ee-112">**In this topic:**</span></span>

-   [<span data-ttu-id="3a8ee-113">Background</span><span class="sxs-lookup"><span data-stu-id="3a8ee-113">Background</span></span>](#bkmk_background)

-   [<span data-ttu-id="3a8ee-114">Dove installare spPowerPivot.msi?</span><span class="sxs-lookup"><span data-stu-id="3a8ee-114">Where to Install spPowerPivot.msi?</span></span>](#bkmk_where_to_install)

-   [<span data-ttu-id="3a8ee-115">Requisiti e prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3a8ee-115">Requirements and Prerequisites</span></span>](#bkmk_prereq)

-   [<span data-ttu-id="3a8ee-116">Per installare PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="3a8ee-116">To Install PowerPivot for SharePoint</span></span>](#bkmk_install)

-   [<span data-ttu-id="3a8ee-117">Distribuire i file di soluzione di SharePoint con lo strumento di configurazione di PowerPivot per SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="3a8ee-117">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>](#bkmk_deploy_solution)

-   [<span data-ttu-id="3a8ee-118">Disinstallare o ripristinare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="3a8ee-118">Uninstall or repair the add-in</span></span>](#bkmk_remove_addin)

##  <a name="background"></a><a name="bkmk_background"></a> <span data-ttu-id="3a8ee-119">Background</span><span class="sxs-lookup"><span data-stu-id="3a8ee-119">Background</span></span>

-   <span data-ttu-id="3a8ee-120">**Server applicazioni:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in SharePoint 2013 sono inclusi l'uso delle cartelle di lavoro come origine dati, l'aggiornamento dati pianificato e il dashboard di gestione [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a8ee-120">**Application Server:** [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] functionality in SharePoint 2013 includes using workbooks as a data source, scheduled data refresh, and the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] Management Dashboard.</span></span>

     [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] <span data-ttu-id="3a8ee-121">è un pacchetto di Windows Installer [!INCLUDE[msCoName](../../../includes/msconame-md.md)] (**spPowerpivot.msi**) tramite il quale vengono distribuite le librerie client di Analysis Services e vengono copiati i file di installazione di [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] nel computer.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-121">is a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Installer package (**spPowerpivot.msi**) that deploys Analysis Services client libraries and copies [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] installation files to the computer.</span></span> <span data-ttu-id="3a8ee-122">Tramite il programma di installazione non vengono distribuite né configurate le funzionalità di [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-122">The installer does not deploy or configure [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] features in SharePoint.</span></span> <span data-ttu-id="3a8ee-123">I componenti seguenti vengono installati per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-123">The following components install by default:</span></span>

    -   [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] <span data-ttu-id="3a8ee-124">2013. In questo componente sono inclusi script di PowerShell (file con estensione ps1), pacchetti della soluzione SharePoint (con estensione wsp) e lo strumento di configurazione di [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 per distribuire [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in una farm di SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-124">2013. This component includes PowerShell scripts (.ps1 files), SharePoint solution packages (.wsp), and the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] 2013 configuration tool to deploy [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] in a SharePoint 2013 farm.</span></span>

    -   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="3a8ee-125">Provider OLE DB per Analysis Services (MSOLAP).</span><span class="sxs-lookup"><span data-stu-id="3a8ee-125">OLE DB Provider for Analysis Services (MSOLAP).</span></span>

    -   <span data-ttu-id="3a8ee-126">Provider di dati ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-126">ADOMD.NET data provider.</span></span>

    -   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="3a8ee-127">Analysis Management Objects.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-127">Analysis Management Objects.</span></span>

-   <span data-ttu-id="3a8ee-128">**Servizi back-end:** se si utilizza [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] per Excel per creare cartelle di lavoro contenenti dati analitici, è necessario configurare Excel Services con un server BI in cui è eseguito [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in modalità SharePoint per accedere a questi dati in un ambiente server.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-128">**Backend services:** If you use [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for Excel to create workbooks that contain analytical data, you must have Excel Services configured with a BI server running [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode to access that data in a server environment.</span></span> <span data-ttu-id="3a8ee-129">Il programma di installazione di SQL Server può essere eseguito in un computer in cui è installato SharePoint Server 2013 o in uno diverso in cui non è disponibile il software SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-129">You can run SQL Server Setup on a computer that has SharePoint Server 2013 installed, or on a different computer that has no SharePoint software.</span></span> <span data-ttu-id="3a8ee-130">In Analysis Services non è presente alcuna dipendenza da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-130">Analysis Services does not have any dependencies on SharePoint.</span></span>

     <span data-ttu-id="3a8ee-131">Per ulteriori informazioni sull'installazione, sulla disinstallazione e sulla configurazione di servizi back-end, vedere l'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-131">For more information on installing, uninstalling, and configuring the backend services, see the following:</span></span>

    -   [<span data-ttu-id="3a8ee-132">Installazione di PowerPivot per SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="3a8ee-132">PowerPivot for SharePoint 2013 Installation</span></span>](https://docs.microsoft.com/analysis-services/instances/install-windows/install-analysis-services-in-power-pivot-mode)

    -   [<span data-ttu-id="3a8ee-133">Disinstallare PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="3a8ee-133">Uninstall PowerPivot for SharePoint</span></span>](../../../sql-server/install/uninstall-power-pivot-for-sharepoint.md)

##  <a name="where-to-install-sppowerpivotmsi"></a><a name="bkmk_where_to_install"></a> <span data-ttu-id="3a8ee-134">Percorso in cui installare il file spPowerPivot.msi</span><span class="sxs-lookup"><span data-stu-id="3a8ee-134">Where to Install spPowerPivot.msi?</span></span>
 <span data-ttu-id="3a8ee-135">Una procedura consigliata consiste nell'installare il file **spPowerPivot.msi** in tutti i server nella farm di SharePoint per coerenza di configurazione, inclusi i server applicazioni e quelli front-end Web.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-135">A recommended best practice is to install **spPowerPivot.msi** on all servers in the SharePoint farm for configuration consistency, including application servers and web-front end servers.</span></span> <span data-ttu-id="3a8ee-136">Nel pacchetto di installazione sono inclusi i provider di dati di Analysis Services, nonché lo strumento di configurazione di [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a8ee-136">The installer package includes the Analysis Services data providers as well as the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] configuration tool.</span></span> <span data-ttu-id="3a8ee-137">Quando si installa il file **spPowerPivot.msi** è possibile personalizzare l'installazione escludendo singoli componenti.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-137">When you install **spPowerPivot.msi** you can customize the installation by excluding individual components.</span></span>

 <span data-ttu-id="3a8ee-138">**Provider di dati:** in diverse tecnologie SharePoint e di SQL Server vengono utilizzati i provider di dati di Analysis Services, tra cui Excel Services, PerformancePoint Services e Power View.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-138">**Data providers:** Several SharePoint and SQL Server technologies use the Analysis Services data providers including Excel Services, PerformancePoint Services, and Power View.</span></span> <span data-ttu-id="3a8ee-139">Installando il file **spPowerPivot.msi** in tutti i server SharePoint si garantiscono la disponibilità in modo coerente del set completo di provider di dati di Analysis Services e la connettività di PowerPivot nella farm.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-139">Installing **spPowerPivot.msi** on all SharePoint servers ensures the full set of Analysis Services data providers and PowerPivot connectivity is consistently available across the farm.</span></span>

> [!NOTE]
>  <span data-ttu-id="3a8ee-140">È necessario installare i provider di dati di Analysis Services in un server SharePoint 2013 tramite **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-140">You must install the Analysis Services data providers on a SharePoint 2013 server using **spPowerPivot.msi**.</span></span> <span data-ttu-id="3a8ee-141">Gli altri pacchetti di installazione disponibili in [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] Feature Pack non sono supportati in quanto in essi non sono inclusi i file di supporto di SharePoint 2013 richiesti dai provider di dati in questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-141">Other installer packages available in the [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] Feature Pack are not supported because these packages do not include the SharePoint 2013 support files that the data providers require in this environment.</span></span>

 <span data-ttu-id="3a8ee-142">**Strumento di configurazione:** lo strumento di configurazione di PowerPivot per SharePoint 2013 è obbligatorio in uno solo dei server SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-142">**Configuration Tool:** The PowerPivot for SharePoint 2013 configuration tool is required on only one of the SharePoint servers.</span></span> <span data-ttu-id="3a8ee-143">Tuttavia, una procedura consigliata nelle farm con più server consiste nell'installare lo strumento di configurazione in almeno due server in modo da poter disporre dell'accesso allo strumento qualora uno dei due server sia offline.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-143">However a recommended best practice in multi-server farms is to install the configuration tool on at least two servers so you have access to the configuration tool if one of the two servers is offline.</span></span>

##  <a name="requirements-and-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="3a8ee-144">Requisiti e prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3a8ee-144">Requirements and Prerequisites</span></span>

-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="3a8ee-145">SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-145">SharePoint Server 2013.</span></span>

-   <span data-ttu-id="3a8ee-146">Il file**spPowerPivot.msi** è solo a 64 bit, in base ai requisiti di prodotti e tecnologie SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-146">**spPowerPivot.msi** is 64-bit only, in accordance with the requirements of SharePoint products and technologies.</span></span>

-   <span data-ttu-id="3a8ee-147">Un server [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] in modalità PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-147">A [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] server in PowerPivot mode.</span></span> <span data-ttu-id="3a8ee-148">In Excel Services verrà utilizzata l'istanza di SQL Server Analysis Services come server di PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-148">Excel Services will use the SQL Server Analysis Services instance as a PowerPivot server.</span></span> <span data-ttu-id="3a8ee-149">Analysis Services può essere eseguito nel computer locale o in uno remoto.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-149">Analysis Services can run on the local or a remote computer.</span></span>

-   <span data-ttu-id="3a8ee-150">**Autorizzazioni:** per installare [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], è necessario che l'utente corrente sia un amministratore nel computer e un membro del gruppo di amministratori farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-150">**Permissions:** To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)], the current user is required to be an administrator on the computer and a SharePoint Farm Administrators group.</span></span>

-   <span data-ttu-id="3a8ee-151">Per ulteriori informazioni sui [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] requisiti e i prerequisiti, vedere la pagina relativa ai [requisiti hardware e Software per Analysis Services server in modalità SharePoint &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3a8ee-151">For more information on [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] requirements and pre-requisites, go to [Hardware and Software Requirements for Analysis Services Server in SharePoint Mode &#40;SQL Server 2014&#41;](../../../sql-server/install/hardware-software-requirements-analysis-services-server-sharepoint-mode.md).</span></span>

##  <a name="to-install-powerpivot-for-sharepoint"></a><a name="bkmk_install"></a><span data-ttu-id="3a8ee-152">Per installare PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="3a8ee-152">To Install PowerPivot for SharePoint</span></span>
 <span data-ttu-id="3a8ee-153">Il pacchetto di installazione **spPowerpivot.msi** supporta sia la modalità interfaccia utente grafica sia quella da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-153">The **spPowerpivot.msi** installer package supports both a graphical user interface and a command-line mode.</span></span> <span data-ttu-id="3a8ee-154">Per entrambi i metodi di installazione è richiesta l'esecuzione del file con estensione msi con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-154">Both methods of installation require that you run the .msi with administrator privileges.</span></span> <span data-ttu-id="3a8ee-155">Al termine dell'installazione, vedere l'argomento seguente per informazioni sullo strumento di configurazione e sulle funzionalità aggiuntive, [configurare PowerPivot e distribuire soluzioni &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span><span class="sxs-lookup"><span data-stu-id="3a8ee-155">After the installation, see the following topic for information on the configuration tool and additional features, [Configure PowerPivot and Deploy Solutions &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/configure-power-pivot-and-deploy-solutions-sharepoint-2013).</span></span>

### <a name="user-interface-installation"></a><span data-ttu-id="3a8ee-156">Installazione tramite l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3a8ee-156">User interface installation</span></span>
 <span data-ttu-id="3a8ee-157">Per installare [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] con l'interfaccia utente grafica, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-157">To install [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] with the graphical user interface, complete the following steps:</span></span>

1.  <span data-ttu-id="3a8ee-158">Eseguire il file **SpPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-158">Run **SpPowerPivot.msi**.</span></span>

2.  <span data-ttu-id="3a8ee-159">Nella pagina iniziale fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-159">Click **Next** on the Welcome page.</span></span>

3.  <span data-ttu-id="3a8ee-160">Esaminare e accettare il contratto di licenza, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-160">Review and accept the license agreement, then click **Next**.</span></span>

4.  <span data-ttu-id="3a8ee-161">Nella pagina **Selezione funzionalità** tutte le funzionalità sono selezionate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-161">On the **Feature Selection** page, all of the features are selected by default.</span></span>

5.  <span data-ttu-id="3a8ee-162">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-162">Click **Next**.</span></span>

6.  <span data-ttu-id="3a8ee-163">Per terminare l'installazione, fare clic su **Installa** per installare.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-163">Click **Install** to install to finish the installation.</span></span>

### <a name="command-line-installation"></a><span data-ttu-id="3a8ee-164">Installazione dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="3a8ee-164">Command Line Installation</span></span>
 <span data-ttu-id="3a8ee-165">Per un'installazione dalla riga di comando, aprire un prompt dei comandi con autorizzazioni amministrative, quindi eseguire il file **spPowerPivot.msi**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-165">For a command-line installation, open a command prompt with administrative permissions, and then run the **spPowerPivot.msi**.</span></span> <span data-ttu-id="3a8ee-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-166">For example:</span></span>

 <span data-ttu-id="3a8ee-167">`Msiexec.exe /i SpPowerPivot.msi`.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-167">`Msiexec.exe /i SpPowerPivot.msi`.</span></span>

 <span data-ttu-id="3a8ee-168">Per creare un log dell'installazione, utilizzare le opzioni di registrazione standard MsiExec.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-168">To create an installation log, use the standard MsiExec logging switches.</span></span> <span data-ttu-id="3a8ee-169">Nell'esempio seguente viene creato il file di log "Install_Log.txt" utilizzando l'opzione di registrazione dettagliata "v".</span><span class="sxs-lookup"><span data-stu-id="3a8ee-169">The following example creates the log file "Install_Log.txt" using the "v" verbose logging switch.</span></span>

```cmd
Msiexec.exe /i SpPowerPivot.msi /L v c:\test\Install_Log.txt
```

### <a name="quiet-command-line-installation-for-scripting"></a><span data-ttu-id="3a8ee-170">Installazione dalla riga di comando non interattiva per lo scripting</span><span class="sxs-lookup"><span data-stu-id="3a8ee-170">Quiet Command Line Installation for scripting</span></span>
 <span data-ttu-id="3a8ee-171">È possibile utilizzare le opzioni **/q** o **/quiet** per un'installazione "non interattiva" in cui non vengono visualizzate finestre di dialogo o avvisi.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-171">You can use the **/q** or **/quiet** switches for a "quiet" installation that will not display any dialogs or warnings.</span></span> <span data-ttu-id="3a8ee-172">L'installazione non interattiva è utile se si desidera creare uno script dell'installazione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-172">The quiet installation is useful if you want to script the installation of the add-in.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="3a8ee-173">Se si usa l'opzione **/q** per un'installazione da riga di comando invisibile all'utente, il contratto di licenza con l'utente finale non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-173">If you use the **/q** switch for a silent command line installation, the end-user license agreement will not be displayed.</span></span> <span data-ttu-id="3a8ee-174">Indipendentemente dal metodo di installazione, l'utilizzo di questo software è governato da un contratto di licenza e l'utente è tenuto a rispettarlo.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-174">Regardless of the installation method, the use of this software is governed by a license agreement and you are responsible for complying with the license agreement.</span></span>

#### <a name="to-perform-a-quiet-installation"></a><span data-ttu-id="3a8ee-175">Per eseguire un'installazione non interattiva</span><span class="sxs-lookup"><span data-stu-id="3a8ee-175">To perform a quiet installation</span></span>

1.  <span data-ttu-id="3a8ee-176">Aprire un prompt dei comandi **con autorizzazioni di amministratore**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-176">Open a command prompt **with administrator permissions**.</span></span>

2.  <span data-ttu-id="3a8ee-177">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-177">Run the following command:</span></span>

    ```cmd
    Msiexec.exe /i spPowerPivot.msi /q
    ```

### <a name="command-line-installation-to-include-specific-components"></a><span data-ttu-id="3a8ee-178">Installazione dalla riga di comando per includere componenti specifici</span><span class="sxs-lookup"><span data-stu-id="3a8ee-178">Command Line Installation to include specific components</span></span>
 <span data-ttu-id="3a8ee-179">Lo strumento di configurazione di [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] non è obbligatorio nei server SharePoint, tuttavia se ne consiglia l'installazione in almeno due server in modo da renderlo disponibile quando necessario.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-179">The [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool is not required on every SharePoint server, however it is recommended to install it on at least two servers so the configuration tool is available when you need it.</span></span>

 <span data-ttu-id="3a8ee-180">Quando si installa spPowerPivot.msi, è possibile utilizzare le opzioni della riga di comando per installare elementi specifici, ad esempio i provider di dati e non lo strumento di configurazione di [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a8ee-180">When you install the spPowerPivot.msi, you can use the command line options to install specific items, such as the data providers and not the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration tool.</span></span> <span data-ttu-id="3a8ee-181">La riga di comando seguente è un esempio di installazione di tutti i componenti, eccetto lo strumento di configurazione:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-181">The following command line is an example of installing all components except the configuration tool:</span></span>

```
Msiexec /i spPowerPivot.msi AGREETOLICENSE="yes" ADDLOCAL=" SQL_OLAPDM,SQL_ADOMD,SQL_AMO,SQLAS_SP_Common"
```

|<span data-ttu-id="3a8ee-182">Opzione</span><span class="sxs-lookup"><span data-stu-id="3a8ee-182">Option</span></span>|<span data-ttu-id="3a8ee-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a8ee-183">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="3a8ee-184">Analysis_Server_SP_addin</span><span class="sxs-lookup"><span data-stu-id="3a8ee-184">Analysis_Server_SP_addin</span></span>|<span data-ttu-id="3a8ee-185">Configurazione di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="3a8ee-185">PowerPivot Configuration</span></span>|
|<span data-ttu-id="3a8ee-186">SQL_OLAPDM</span><span class="sxs-lookup"><span data-stu-id="3a8ee-186">SQL_OLAPDM</span></span>|<span data-ttu-id="3a8ee-187">MSOLAP</span><span class="sxs-lookup"><span data-stu-id="3a8ee-187">MSOLAP</span></span>|
|<span data-ttu-id="3a8ee-188">SQL_ADOMD</span><span class="sxs-lookup"><span data-stu-id="3a8ee-188">SQL_ADOMD</span></span>|<span data-ttu-id="3a8ee-189">Provider ADOMD.net</span><span class="sxs-lookup"><span data-stu-id="3a8ee-189">ADOMD.net provider</span></span>|
|<span data-ttu-id="3a8ee-190">SQL_AMO</span><span class="sxs-lookup"><span data-stu-id="3a8ee-190">SQL_AMO</span></span>|<span data-ttu-id="3a8ee-191">Provider AMO</span><span class="sxs-lookup"><span data-stu-id="3a8ee-191">AMO provider</span></span>|
|<span data-ttu-id="3a8ee-192">SQLAS_SP_Common</span><span class="sxs-lookup"><span data-stu-id="3a8ee-192">SQLAS_SP_Common</span></span>|<span data-ttu-id="3a8ee-193">Componenti comuni di Analysis Services per SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="3a8ee-193">Analysis Services common components for SharePoint 2013</span></span>|

##  <a name="deploy-the-sharepoint-solution-files-with-the-powerpivot-for-sharepoint-2013-configuration-tool"></a><a name="bkmk_deploy_solution"></a><span data-ttu-id="3a8ee-194">Distribuire i file della soluzione di SharePoint con lo strumento di configurazione PowerPivot per SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="3a8ee-194">Deploy the SharePoint Solution Files with the PowerPivot for SharePoint 2013 Configuration Tool</span></span>
 <span data-ttu-id="3a8ee-195">Tre dei file copiati nel disco rigido tramite spPowerPivot.msi sono file di soluzione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-195">Three of the files copied to the hard drive by spPowerPivot.msi are SharePoint solution files.</span></span> <span data-ttu-id="3a8ee-196">L'ambito di un file della soluzione è il livello applicazione Web mentre quello degli altri file è il livello farm.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-196">The scope of one solution file is the Web application level while the scope of the other files is the farm level.</span></span> <span data-ttu-id="3a8ee-197">I file sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-197">The files are the following:</span></span>

-   `PowerPivotFarmSolution.wsp`

-   `PowerPivotFarm14Solution.wsp`

-   `PowerPivotWebApplicationSolution.wsp`

 <span data-ttu-id="3a8ee-198">I file della soluzione vengono copiati nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-198">The solution files are copied to the following folder:</span></span>

 `C:\Program Files\Microsoft SQL Server\120\Tools\PowerPivotTools\SPAddinConfiguration\Resources`

 <span data-ttu-id="3a8ee-199">Dopo l'installazione del file con estensione msi, eseguire lo strumento di configurazione di [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] per configurare e distribuire le soluzioni nella farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-199">Following the .msi installation, run the [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] Configuration Tool to configure and deploy the solutions in the SharePoint farm.</span></span>

### <a name="to-start-the-configuration-tool"></a><span data-ttu-id="3a8ee-200">Per avviare lo strumento di configurazione</span><span class="sxs-lookup"><span data-stu-id="3a8ee-200">To start the configuration tool</span></span> 

 <span data-ttu-id="3a8ee-201">Dalla schermata iniziale di Windows digitare "Power" e nei risultati di ricerca per le app fare clic su **configurazione di PowerPivot per SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-201">From the Windows Start screen type "power" and in the Apps search results, click **PowerPivot for SharePoint 2013 Configuration**.</span></span> <span data-ttu-id="3a8ee-202">I risultati della ricerca possono includere due collegamenti perché con l'installazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vengono installati separatamente gli strumenti di configurazione di [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] per SharePoint 2010 e SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-202">Note that the search results may include two links because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup installs separate [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] configuration tools for SharePoint 2010 and SharePoint 2013.</span></span> <span data-ttu-id="3a8ee-203">Assicurarsi di avviare [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] per lo strumento di configurazione di SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-203">Make sure you start the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] for SharePoint 2013 Configuration tool.</span></span>

 <span data-ttu-id="3a8ee-204">![due strumenti di configurazione PowerPivot](../../media/as-powerpivot-configtools-bothicons.gif "due strumenti di configurazione PowerPivot")</span><span class="sxs-lookup"><span data-stu-id="3a8ee-204">![two powerpivot configuration tools](../../media/as-powerpivot-configtools-bothicons.gif "two powerpivot configuration tools")</span></span>

 <span data-ttu-id="3a8ee-205">**O**</span><span class="sxs-lookup"><span data-stu-id="3a8ee-205">**Or**</span></span>

1.  <span data-ttu-id="3a8ee-206">Andare a **Start**, **Tutti i programmi**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-206">Go to **Start**, **All Programs**.</span></span>

2.  <span data-ttu-id="3a8ee-207">Fare clic su **Microsoft SQL Server 2014**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-207">Click **Microsoft SQL Server 2014**.</span></span>

3.  <span data-ttu-id="3a8ee-208">Fare clic su **Strumenti di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-208">Click **Configuration Tools**.</span></span>

4.  <span data-ttu-id="3a8ee-209">Scegliere **Configurazione di PowerPivot per SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-209">Click **PowerPivot for SharePoint 2013 Configuration**.</span></span>

 <span data-ttu-id="3a8ee-210">Per ulteriori informazioni sullo strumento di configurazione, vedere [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3a8ee-210">For more information on the configuration tool, see [PowerPivot Configuration Tools](../../power-pivot-sharepoint/power-pivot-configuration-tools.md).</span></span>

##  <a name="uninstall-or-repair-the-add-in"></a><a name="bkmk_remove_addin"></a><span data-ttu-id="3a8ee-211">Disinstallare o ripristinare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="3a8ee-211">Uninstall or repair the add-in</span></span>

> [!CAUTION]
>  <span data-ttu-id="3a8ee-212">Se si disinstalla **spPowerPivot.msi** , i provider di dati e lo strumento di configurazione vengono disinstallati.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-212">If you uninstall **spPowerPivot.msi** the data providers and the configuration tool are uninstalled.</span></span> <span data-ttu-id="3a8ee-213">Disinstallando i provider di dati, non sarà più possibile connettere il server a PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-213">Uninstalling the data providers will cause the server to be unable to connect to PowerPivot.</span></span>

 <span data-ttu-id="3a8ee-214">È possibile disinstallare o ripristinare [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] tramite uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-214">You can uninstall or repair [!INCLUDE[ssGeminiShortvnext](../../../includes/ssgeminishortvnext-md.md)] using one of the following methods:</span></span>

1.  <span data-ttu-id="3a8ee-215">**Pannello di controllo di Windows:** selezionare **Microsoft SQL Server 2012 PowerPivot per SharePoint 2013**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-215">**Windows control panel:** Select **Microsoft SQL Server 2012 PowerPivot for SharePoint 2013**.</span></span> <span data-ttu-id="3a8ee-216">Fare clic su **Disinstalla** o **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="3a8ee-216">Click either **Uninstall** or **Repair**.</span></span>

2.  <span data-ttu-id="3a8ee-217">Eseguire spPowerPivot.msi e selezionare l'opzione **Rimuovi** o **Ripristina** .</span><span class="sxs-lookup"><span data-stu-id="3a8ee-217">Run the spPowerPivot.msi and select the **Remove** option or the **Repair** option.</span></span>

 <span data-ttu-id="3a8ee-218">**Riga di comando:** per ripristinare o disinstallare PowerPivot per SharePoint 2013 tramite la riga di comando, aprire un prompt dei comandi **con le autorizzazioni di amministratore** ed eseguire uno dei comandi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-218">**Command Line:** To repair or uninstall PowerPivot for SharePoint 2013 using the command line, open a command prompt **with administrator permissions** and run one of the following commands:</span></span>

-   <span data-ttu-id="3a8ee-219">Per effettuare il ripristino, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-219">To Repair, run the following command:</span></span>

    ```cmd
    msiexec.exe /f spPowerPivot.msi
    ```

 <span data-ttu-id="3a8ee-220">OR</span><span class="sxs-lookup"><span data-stu-id="3a8ee-220">OR</span></span>

-   <span data-ttu-id="3a8ee-221">Per effettuare la disinstallazione, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a8ee-221">To uninstall, run the following command:</span></span>

    ```cmd
    msiexec.exe /uninstall spPowerPivot.msi
    ```
