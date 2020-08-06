---
title: Abilitare o disabilitare le funzionalità di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, configuration
- security [Reporting Services], strategies
ms.assetid: b69db02a-43a7-4fdc-ad9b-438d817a7f83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f56f9984b5b02431db23b782652e5575af557bdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628326"
---
# <a name="turn-reporting-services-features-on-or-off"></a><span data-ttu-id="8f92f-102">Abilitare o disabilitare le funzionalità di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8f92f-102">Turn Reporting Services Features On or Off</span></span>
  <span data-ttu-id="8f92f-103">È possibile disabilitare le funzionalità del server di report non utilizzate come parte di una strategia di blocco per ridurre la superficie di attacco di un server di report di produzione.</span><span class="sxs-lookup"><span data-stu-id="8f92f-103">You can turn off report server features that you do not use as part of a lockdown strategy for reducing the attack surface of a production report server.</span></span> <span data-ttu-id="8f92f-104">Nella maggior parte dei casi, è consigliabile eseguire le funzionalità di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] simultaneamente in modo da poter utilizzare tutte le funzionalità disponibili in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f92f-104">In most cases, you will want to run [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features concurrently to use all of the functionality provided in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="8f92f-105">Tuttavia, a seconda del modello di distribuzione, è possibile disabilitare le funzionalità che non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="8f92f-105">However, depending on your deployment model, you can disable the features that you do not require.</span></span> <span data-ttu-id="8f92f-106">Ad esempio, è possibile abilitare solo l'elaborazione in background se tutte le operazioni di elaborazione dei report vengono configurate come operazioni pianificate.</span><span class="sxs-lookup"><span data-stu-id="8f92f-106">For example, you can enable only the background processing if all report processing is configured as scheduled operations.</span></span> <span data-ttu-id="8f92f-107">Analogamente, se si desidera che la generazione di report venga eseguita solo in modo interattivo e su richiesta, è possibile eseguire solo il servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="8f92f-107">Similarly, you can run just the Report Server Web service if you only want interactive, on-demand reporting.</span></span>  
  
 <span data-ttu-id="8f92f-108">Nelle procedure presenti in questo argomento viene illustrato come disabilitare le funzionalità di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="8f92f-108">The procedures in this topic show you how to turn off native mode [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="8f92f-109">Le funzionalità possono essere configurate in modi diversi, ad esempio modificando direttamente il file `RsReportServer.config` o usando il facet **Configurazione superficie di attacco per Reporting Services** della gestione basata su criteri in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f92f-109">Features can be configured in different ways, such as by editing the `RsReportServer.config` file directly or by using the **Surface Area Configuration for Reporting Services** facet of Policy-Based Management in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8f92f-110">Utilizzare i collegamenti per trovare la procedura o le procedure che illustrano come abilitare o disabilitare una funzionalità:</span><span class="sxs-lookup"><span data-stu-id="8f92f-110">Use the links to locate the procedure or procedures that explain how to turn a feature on or off:</span></span>  
  
-   [<span data-ttu-id="8f92f-111">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="8f92f-111">Report Server Web service</span></span>](#RSWebSvc)  
  
-   [<span data-ttu-id="8f92f-112">Elaborazione ed eventi pianificati</span><span class="sxs-lookup"><span data-stu-id="8f92f-112">Scheduled events and processing</span></span>](#Sched)  
  
-   [<span data-ttu-id="8f92f-113">Gestione report</span><span class="sxs-lookup"><span data-stu-id="8f92f-113">Report Manager</span></span>](#ReportManager)  
  
-   [<span data-ttu-id="8f92f-114">Generatore report</span><span class="sxs-lookup"><span data-stu-id="8f92f-114">Report Builder</span></span>](#ReportBuilder)  
  
-   [<span data-ttu-id="8f92f-115">Sicurezza integrata di Windows per le origini dati dei report</span><span class="sxs-lookup"><span data-stu-id="8f92f-115">Windows Integrated security for report data sources</span></span>](#WinIntSec)  
  
##  <a name="report-server-web-service"></a><a name="RSWebSvc"></a><span data-ttu-id="8f92f-116">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="8f92f-116">Report Server Web Service</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-editing-configuration"></a><span data-ttu-id="8f92f-117">Per abilitare o disabilitare il servizio Web ReportServer mediante la modifica della configurazione</span><span class="sxs-lookup"><span data-stu-id="8f92f-117">To turn on or off the Report Server Web service by editing configuration</span></span>  
  
1.  <span data-ttu-id="8f92f-118">Aprire il file `RsReportServer.config` in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="8f92f-118">Open the `RsReportServer.config` file in a text editor.</span></span> <span data-ttu-id="8f92f-119">Per altre informazioni, vedere [Modificare un file di configurazione di Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f92f-119">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="8f92f-120">Per abilitare il servizio Web ReportServer, impostare `IsWebServiceEnabled` su `true`:</span><span class="sxs-lookup"><span data-stu-id="8f92f-120">To turn on the Report Server Web service, set `IsWebServiceEnabled` to `true`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>true</IsWebServiceEnabled>  
    ```  
  
3.  <span data-ttu-id="8f92f-121">Per disabilitare il servizio Web ReportServer, impostare `IsWebServiceEnabled` su `false`:</span><span class="sxs-lookup"><span data-stu-id="8f92f-121">To turn off the Report Server Web service, set `IsWebServiceEnabled` to `false`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>false</IsWebServiceEnabled>  
    ```  
  
4.  <span data-ttu-id="8f92f-122">Salvare le modifiche, quindi chiudere il file.</span><span class="sxs-lookup"><span data-stu-id="8f92f-122">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-using-sql-server-management-studio"></a><span data-ttu-id="8f92f-123">Per abilitare o disabilitare il servizio Web ReportServer mediante l'utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f92f-123">To turn on or off the Report Server Web service by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="8f92f-124">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e connettersi all'istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="8f92f-124">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="8f92f-125">In Esplora oggetti fare clic con il pulsante destro del mouse sul [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nodo, scegliere **criteri**e fare clic su **facet**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-125">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="8f92f-126">Nell'elenco **Facet** selezionare **Configurazione superficie di attacco per Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-126">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="8f92f-127">In **Proprietà facet**:</span><span class="sxs-lookup"><span data-stu-id="8f92f-127">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="8f92f-128">Per attivare il servizio Web ReportServer, impostare **WebServiceAndHTTPAccessEnabled** su `True` .</span><span class="sxs-lookup"><span data-stu-id="8f92f-128">To turn on the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="8f92f-129">Per disabilitare il servizio Web ReportServer, impostare **WebServiceAndHTTPAccessEnabled** su `False` .</span><span class="sxs-lookup"><span data-stu-id="8f92f-129">To turn off the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="scheduled-events-and-delivery"></a><a name="Sched"></a> <span data-ttu-id="8f92f-130">Recapito ed eventi pianificati</span><span class="sxs-lookup"><span data-stu-id="8f92f-130">Scheduled Events and Delivery</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-editing-configuration"></a><span data-ttu-id="8f92f-131">Per abilitare o disabilitare il recapito e gli eventi pianificati mediante la modifica della configurazione</span><span class="sxs-lookup"><span data-stu-id="8f92f-131">To turn on or off scheduled events and delivery by editing configuration</span></span>  
  
1.  <span data-ttu-id="8f92f-132">Aprire il file RsReportServer.config in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="8f92f-132">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="8f92f-133">Per altre informazioni, vedere [Modificare un file di configurazione di Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f92f-133">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="8f92f-134">Per abilitare l'elaborazione e il recapito pianificati dei report, impostare `IsSchedulingService`, `IsNotificationService` e `IsEventService` su `true`:</span><span class="sxs-lookup"><span data-stu-id="8f92f-134">To turn on scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `true`:</span></span>  
  
    ```  
    <IsSchedulingService>true</IsSchedulingService>  
    <IsNotificationService>true</IsNotificationService>  
    <IsEventService>true</IsEventService>  
    ```  
  
3.  <span data-ttu-id="8f92f-135">Per disabilitare l'elaborazione e il recapito pianificati dei report, impostare `IsSchedulingService`, `IsNotificationService` e `IsEventService` su `false`:</span><span class="sxs-lookup"><span data-stu-id="8f92f-135">To turn off scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `false`:</span></span>  
  
    ```  
    <IsSchedulingService>false</IsSchedulingService>  
    <IsNotificationService>false</IsNotificationService>  
    <IsEventService>false</IsEventService>  
    ```  
  
4.  <span data-ttu-id="8f92f-136">Salvare le modifiche, quindi chiudere il file.</span><span class="sxs-lookup"><span data-stu-id="8f92f-136">Save your changes and then close the file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f92f-137">Non è possibile disabilitare completamente l'elaborazione in background, in quanto fornisce funzionalità di manutenzione dei database necessarie per le operazioni del server.</span><span class="sxs-lookup"><span data-stu-id="8f92f-137">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-using-sql-server-management-studio"></a><span data-ttu-id="8f92f-138">Per abilitare o disabilitare il recapito e gli eventi pianificati mediante l'utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f92f-138">To turn on or off scheduled events and delivery by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="8f92f-139">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e connettersi all'istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="8f92f-139">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="8f92f-140">In Esplora oggetti fare clic con il pulsante destro del mouse sul [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nodo, scegliere **criteri**e fare clic su **facet**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-140">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="8f92f-141">Nell'elenco **Facet** selezionare **Configurazione superficie di attacco per Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-141">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="8f92f-142">In **Proprietà facet**:</span><span class="sxs-lookup"><span data-stu-id="8f92f-142">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="8f92f-143">Per attivare il recapito e gli eventi pianificati, impostare **ScheduleEventsAndReportDeliveryEnabled** su `True` .</span><span class="sxs-lookup"><span data-stu-id="8f92f-143">To turn on scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="8f92f-144">Per disabilitare il recapito e gli eventi pianificati, impostare **ScheduleEventsAndReportDeliveryEnabled** su `False` .</span><span class="sxs-lookup"><span data-stu-id="8f92f-144">To turn off scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="8f92f-145">Non è possibile disabilitare completamente l'elaborazione in background, in quanto fornisce funzionalità di manutenzione dei database necessarie per le operazioni del server.</span><span class="sxs-lookup"><span data-stu-id="8f92f-145">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
##  <a name="report-manager"></a><a name="ReportManager"></a><span data-ttu-id="8f92f-146">Gestione report</span><span class="sxs-lookup"><span data-stu-id="8f92f-146">Report Manager</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-editing-configuration"></a><span data-ttu-id="8f92f-147">Per abilitare o disabilitare Gestione report mediante la modifica della configurazione</span><span class="sxs-lookup"><span data-stu-id="8f92f-147">To turn on or off Report Manager by editing configuration</span></span>  
  
1.  <span data-ttu-id="8f92f-148">Aprire il file RsReportServer.config in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="8f92f-148">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="8f92f-149">Per le istruzioni vedere [Modificare un file di configurazione di Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f92f-149">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="8f92f-150">Per abilitare Gestione report, impostare `IsReportManagerEnabled` su `true`:</span><span class="sxs-lookup"><span data-stu-id="8f92f-150">To turn on Report Manager, set `IsReportManagerEnabled` to `true`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>true</IsReportManagerEnabled>  
    ```  
  
3.  <span data-ttu-id="8f92f-151">Per disabilitare Gestione report, impostare `IsReportManagerEnabled` su `false`:</span><span class="sxs-lookup"><span data-stu-id="8f92f-151">To turn off Report Manager, set `IsReportManagerEnabled` to `false`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>false</IsReportManagerEnabled>  
    ```  
  
4.  <span data-ttu-id="8f92f-152">Salvare le modifiche, quindi chiudere il file.</span><span class="sxs-lookup"><span data-stu-id="8f92f-152">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-using-sql-server-management-studio"></a><span data-ttu-id="8f92f-153">Per abilitare o disabilitare Gestione report mediante l'utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f92f-153">To turn on or off Report Manager by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="8f92f-154">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e connettersi all'istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="8f92f-154">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="8f92f-155">In **Esplora oggetti**fare clic con il pulsante destro del mouse sul nodo di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , scegliere **Criteri**, quindi fare clic su **Facet**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-155">In **Object Explorer**, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="8f92f-156">Nell'elenco **Facet** selezionare **Configurazione superficie di attacco per Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-156">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="8f92f-157">In **Proprietà facet**:</span><span class="sxs-lookup"><span data-stu-id="8f92f-157">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="8f92f-158">Per attivare Gestione report, impostare **ReportManagerEnabled** su `True` .</span><span class="sxs-lookup"><span data-stu-id="8f92f-158">To turn on Report Manager, set **ReportManagerEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="8f92f-159">Per disattivare Gestione report, impostare **ReportManagerEnabled** su `False` .</span><span class="sxs-lookup"><span data-stu-id="8f92f-159">To turn off Report Manager, set **ReportManagerEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="report-builder"></a><span data-ttu-id="8f92f-160">Generatore report <a name="ReportBuilder"></a></span><span class="sxs-lookup"><span data-stu-id="8f92f-160"><a name="ReportBuilder"></a> Report Builder</span></span>  
  
#### <a name="to-turn-on-or-off-report-builder-by-using-sql-server-management-studio"></a><span data-ttu-id="8f92f-161">Per abilitare o disabilitare Generatore report mediante l'utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f92f-161">To turn on or off Report Builder by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="8f92f-162">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e connettersi all'istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="8f92f-162">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="8f92f-163">In Esplora oggetti fare clic con il pulsante destro del mouse sul nodo di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-163">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8f92f-164">In **Selezione pagina** nella finestra di dialogo **Proprietà server**fare clic su **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-164">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="8f92f-165">Per abilitare Generatore report, selezionare l'opzione **Consenti esecuzione report ad hoc** .</span><span class="sxs-lookup"><span data-stu-id="8f92f-165">To turn on Report Builder, select the **Enable ad hoc report executions** option.</span></span>  
  
    -   <span data-ttu-id="8f92f-166">Per disabilitare Generatore report, deselezionare l'opzione **Consenti esecuzione report ad hoc** .</span><span class="sxs-lookup"><span data-stu-id="8f92f-166">To turn off Report Builder, unselect the **Enable ad hoc report executions** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="windows-integrated-security"></a><a name="WinIntSec"></a> <span data-ttu-id="8f92f-167">Sicurezza integrata di Windows</span><span class="sxs-lookup"><span data-stu-id="8f92f-167">Windows Integrated Security</span></span>  
  
#### <a name="to-turn-on-or-off-windows-integrated-security-by-using-sql-server-management-studio"></a><span data-ttu-id="8f92f-168">Per abilitare o disabilitare la sicurezza integrata di Windows mediante l'utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f92f-168">To turn on or off Windows Integrated security by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="8f92f-169">Aprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] e connettersi all'istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="8f92f-169">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="8f92f-170">In Esplora oggetti fare clic con il pulsante destro del mouse sul nodo di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-170">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8f92f-171">In **Selezione pagina** nella finestra di dialogo **Proprietà server**fare clic su **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="8f92f-171">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="8f92f-172">Per abilitare la sicurezza integrata di Windows, selezionare l'opzione **Abilita la sicurezza integrata di Windows per le origini dati dei report** .</span><span class="sxs-lookup"><span data-stu-id="8f92f-172">To turn on Windows Integrated security, select the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
    -   <span data-ttu-id="8f92f-173">Per disabilitare la sicurezza integrata di Windows, deselezionare l'opzione **Abilita la sicurezza integrata di Windows per le origini dati dei report** .</span><span class="sxs-lookup"><span data-stu-id="8f92f-173">To turn off Windows integrated security, unselect the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f92f-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f92f-174">See Also</span></span>  
 [<span data-ttu-id="8f92f-175">Gestione configurazione Reporting Services &#40;modalità nativa&#41;</span><span class="sxs-lookup"><span data-stu-id="8f92f-175">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
