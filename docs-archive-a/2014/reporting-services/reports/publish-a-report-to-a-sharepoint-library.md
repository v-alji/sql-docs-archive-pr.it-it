---
title: Pubblicare un report in una raccolta di SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- deploying [Reporting Services], reports in SharePoint integrated mode
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 3f6dfc28-50d8-4231-bd25-871b5f77cce6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23b74ffb04bf1e13523dcf6ec5d774089d80f73b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712727"
---
# <a name="publish-a-report-to-a-sharepoint-library"></a><span data-ttu-id="a4696-102">Pubblicare un report in una raccolta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a4696-102">Publish a Report to a SharePoint Library</span></span>
  <span data-ttu-id="a4696-103">Per pubblicare un report in un sito di SharePoint configurato per l'integrazione con SharePoint, è necessario impostare le proprietà del progetto in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="a4696-103">To publish a report to a SharePoint site configured for SharePoint integration, you must set the project properties in Report Designer.</span></span> <span data-ttu-id="a4696-104">Nelle proprietà del progetto tutti i riferimenti a server, report e origini dati condivise devono essere URL completi.</span><span class="sxs-lookup"><span data-stu-id="a4696-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span> <span data-ttu-id="a4696-105">Nella definizione di un report tutti i riferimenti a sottoreport, report drill-through e risorse quali immagini basate su Web devono essere rappresentati da URL completi.</span><span class="sxs-lookup"><span data-stu-id="a4696-105">In the report definition, all references to subreports, drillthrough reports, and resources such as Web-based images, must be fully qualified URLS.</span></span>  
  
 <span data-ttu-id="a4696-106">Per impostare le proprietà del progetto, è necessario disporre dell'autorizzazione **Membro** o **Proprietario** per il sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a4696-106">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span> <span data-ttu-id="a4696-107">Per altre informazioni, vedere [Esempi di URL per elementi di report pubblicati in un server di report in modalità SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a4696-107">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-report-to-a-sharepoint-site"></a><span data-ttu-id="a4696-108">Per pubblicare un report in un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="a4696-108">To publish a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="a4696-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire un progetto del server di report esistente o nuovo.</span><span class="sxs-lookup"><span data-stu-id="a4696-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open an existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="a4696-110">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a4696-110">From the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="a4696-111">Verrà visualizzata la finestra di _\<project>_ dialogo **pagine delle proprietà** .</span><span class="sxs-lookup"><span data-stu-id="a4696-111">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a4696-112">Nell'elenco **Configurazione** selezionare il nome di una configurazione della build della soluzione da usare per compilare e pubblicare il report.</span><span class="sxs-lookup"><span data-stu-id="a4696-112">In the **Configuration** list, select the name of a solution build configuration to use to build and publish your report.</span></span> <span data-ttu-id="a4696-113">La configurazione corrente è elencata come **attiva**( *\<configuration>* ).</span><span class="sxs-lookup"><span data-stu-id="a4696-113">The current configuration is listed as **Active**(*\<configuration>*).</span></span>  
  
4.  <span data-ttu-id="a4696-114">Se si desidera pubblicare le origini dati condivise nel progetto e sovrascrivere origini dati condivise pubblicate in precedenza, impostare **OverwriteDataSources** su **True**.</span><span class="sxs-lookup"><span data-stu-id="a4696-114">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="a4696-115">Opzionale Per **TargetDataSourceFolder**, digitare l'URL di una raccolta di SharePoint o di una cartella della raccolta, ad esempio *http://TestServer/TestSite/Documents/DataSources)* .</span><span class="sxs-lookup"><span data-stu-id="a4696-115">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder (for example, *http://TestServer/TestSite/Documents/DataSources)*.</span></span>  
  
     <span data-ttu-id="a4696-116">Se non si specifica alcun valore, verrà utilizzato il valore **TargetReportFolder** .</span><span class="sxs-lookup"><span data-stu-id="a4696-116">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="a4696-117">Per **TargetReportFolder**, digitare l'URL di una raccolta o di una cartella della raccolta, ad esempio *http://TestServer/TestSite/Documents/Reports)* .</span><span class="sxs-lookup"><span data-stu-id="a4696-117">For **TargetReportFolder**, type a URL to a library or library folder (for example, *http://TestServer/TestSite/Documents/Reports)*.</span></span>  
  
7.  <span data-ttu-id="a4696-118">Per **TargetServerURL**, digitare l'URL di un sito principale o secondario di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a4696-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="a4696-119">Se non si specifica un sito, viene utilizzato il sito principale predefinito, ad esempio,, *http://servername* *http://servername/site* o *http://servername/site/subsite* .</span><span class="sxs-lookup"><span data-stu-id="a4696-119">If you do not specify a site, the default top-level site is used (for example, *http://servername*, *http://servername/site*, or *http://servername/site/subsite*).</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="a4696-120">In Esplora soluzioni fare clic con il pulsante destro del mouse sul report da pubblicare, quindi scegliere **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="a4696-120">In Solution Explorer, right-click the report you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="a4696-121">Il report verrà pubblicato nel percorso specificato in **TargetReportFolder**.</span><span class="sxs-lookup"><span data-stu-id="a4696-121">The report is published to the location specified in **TargetReportFolder**.</span></span> <span data-ttu-id="a4696-122">Gli eventuali errori di distribuzioni verranno visualizzati nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="a4696-122">Deployment errors appear in the Output window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4696-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4696-123">See Also</span></span>  
 <span data-ttu-id="a4696-124">[Finestra di dialogo Pagine delle proprietà del progetto](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="a4696-124">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="a4696-125">[Impostare le proprietà di distribuzione &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="a4696-125">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="a4696-126">[Pubblicazione di report in un server di report](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="a4696-126">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="a4696-127">[Esempi di URL per elementi di report pubblicati in un server di report in modalità SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a4696-127">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 [<span data-ttu-id="a4696-128">Usare una connessione Office Data Connection &#40;.odc&#41; ai report &#40;Reporting Services in modalità integrata SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="a4696-128">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
