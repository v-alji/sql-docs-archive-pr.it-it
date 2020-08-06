---
title: URL Gestione report (modalità nativa SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.reportmanagervirtualdirectory.f1
ms.assetid: 45768952-23a6-45a5-b541-e7bf192b4a78
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ec43c91bb2d24bb96cc6541d93311ce6dd234ed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630264"
---
# <a name="report-manager-url-ssrs-native-mode"></a><span data-ttu-id="e17f8-102">URL di Gestione report (modalità nativa SSRS)</span><span class="sxs-lookup"><span data-stu-id="e17f8-102">Report Manager URL (SSRS Native Mode)</span></span>
  <span data-ttu-id="e17f8-103">Utilizzare la pagina URL Gestione report per configurare o modificare l'URL utilizzato per accedere a Gestione report.</span><span class="sxs-lookup"><span data-stu-id="e17f8-103">Use the Report Manager URL page to configure or modify the URL used to access Report Manager.</span></span> <span data-ttu-id="e17f8-104">Per impostazione predefinita, l'URL di Gestione report eredita il prefisso, l'indirizzo IP e la porta dell'URL del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="e17f8-104">By default, the Report Manager URL inherits the prefix, IP address, and port of the Report Server Web service URL.</span></span> <span data-ttu-id="e17f8-105">Ciò è dovuto al fatto che Gestione report fornisce accesso front-end al servizio Web in cui è in esecuzione lo stesso servizio del server di report.</span><span class="sxs-lookup"><span data-stu-id="e17f8-105">This is because Report Manager provides front-end access to the Web service that runs within the same Report Server service.</span></span> <span data-ttu-id="e17f8-106">Se si isolano le applicazioni del servizio e si utilizza Gestione report per accedere a un servizio Web ReportServer in un computer diverso, è necessario modificare il file RSReportServer.config perché Gestione report punti a un'istanza diversa.</span><span class="sxs-lookup"><span data-stu-id="e17f8-106">If you are isolating the service applications and using Report Manager to access a Report Server Web service on a different computer, you must edit RSReportServer.config file to point Report Manager to a different instance.</span></span> <span data-ttu-id="e17f8-107">Per ulteriori informazioni sulla configurazione di una connessione Gestione report a un server di report remoto, vedere [Reporting Services Configuration Manager &#40;modalità nativa&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e17f8-107">For more information about configuring a Report Manager connection to a remote report server, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
 [!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="e17f8-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="e17f8-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="e17f8-109">Se il server di report viene configurato per l'esecuzione in modalità integrata SharePoint, non creare un URL di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="e17f8-109">If you are configuring the report server to run in SharePoint integrated mode, do not create a Report Manager URL.</span></span> <span data-ttu-id="e17f8-110">Gestione report non è supportato nei server di report eseguiti in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e17f8-110">Report Manager is not supported on a report server that runs in SharePoint integrated mode.</span></span> <span data-ttu-id="e17f8-111">Se è già presente un URL per Gestione report, l'URL non sarà più disponibile in seguito alla configurazione del server di report per l'esecuzione in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e17f8-111">If a URL already exists for Report Manager, it will become unavailable after you configure the report server to run in SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="e17f8-112">Per aprire questa pagina, avviare Gestione configurazione [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e fare clic su **URL Gestione report** nel riquadro di navigazione.</span><span class="sxs-lookup"><span data-stu-id="e17f8-112">To open this page, start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and click **Report Manager URL** in the navigation pane.</span></span> <span data-ttu-id="e17f8-113">Per ulteriori informazioni su come avviare la Configuration Manager, vedere [Reporting Services Configuration Manager &#40;modalità nativa&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e17f8-113">For more information about how to start the Configuration Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e17f8-114">Se Gestione report non è abilitato, non è possibile impostare le opzioni in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="e17f8-114">If Report Manager is not enabled, you cannot set options on this page.</span></span> <span data-ttu-id="e17f8-115">Per ulteriori informazioni sull'abilitazione di Gestione report, vedere [Reporting Services Configuration Manager &#40;modalità nativa&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e17f8-115">For more information about enabling Report Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e17f8-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e17f8-116">Options</span></span>  
 <span data-ttu-id="e17f8-117">**Directory virtuale**</span><span class="sxs-lookup"><span data-stu-id="e17f8-117">**Virtual Directory**</span></span>  
 <span data-ttu-id="e17f8-118">Consente di specificare il nome della directory virtuale per Gestione report.</span><span class="sxs-lookup"><span data-stu-id="e17f8-118">Specifies the virtual directory name for Report Manager.</span></span> <span data-ttu-id="e17f8-119">È possibile specificare un solo nome di directory virtuale per ogni istanza di Gestione report nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="e17f8-119">You can only have one virtual directory name for each Report Manager instance on the same computer.</span></span>  
  
 <span data-ttu-id="e17f8-120">**URL**</span><span class="sxs-lookup"><span data-stu-id="e17f8-120">**URLs**</span></span>  
 <span data-ttu-id="e17f8-121">Consente di visualizzare l'URL definito per l'istanza corrente di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="e17f8-121">Displays the URL defined for the current Report Manager instance.</span></span>  
  
 <span data-ttu-id="e17f8-122">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="e17f8-122">**Advanced**</span></span>  
 <span data-ttu-id="e17f8-123">Consente di aggiungere un altro URL per l'istanza corrente di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="e17f8-123">Add an additional URL for the current Report Manager instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e17f8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e17f8-124">See Also</span></span>  
 <span data-ttu-id="e17f8-125">[Configurare un URL &#40;Configuration Manager SSRS&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e17f8-125">[Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="e17f8-126">[URL nei file di configurazione &#40;Configuration Manager SSRS&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e17f8-126">[URLs in Configuration Files  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="e17f8-127">Configurare gli URL del server di report &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e17f8-127">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
