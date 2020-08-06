---
title: Pubblicare un'origine dati condivisa in una raccolta di SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], publishing to a SharePoint library
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 966ed425-3ce2-4e76-8237-3c1c977954ae
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77ee25535ccb98638ae02ca64e3bcbfc88291c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712723"
---
# <a name="publish-a-shared-data-source-to-a-sharepoint-library"></a><span data-ttu-id="3d3e4-102">Pubblicare un'origine dati condivisa in una raccolta di SharePoint</span><span class="sxs-lookup"><span data-stu-id="3d3e4-102">Publish a Shared Data Source to a SharePoint Library</span></span>
  <span data-ttu-id="3d3e4-103">Per pubblicare un'origine dati condivisa in un server di report eseguito in modalità integrata SharePoint, è necessario impostare le proprietà del progetto report in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-103">To publish a shared data source to a report server that is running in SharePoint integrated mode, you must set the report project properties in Report Designer.</span></span> <span data-ttu-id="3d3e4-104">Nelle proprietà del progetto tutti i riferimenti a server, report e origini dati condivise devono essere URL completi.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span>  
  
 <span data-ttu-id="3d3e4-105">È necessario disporre dell'autorizzazione **Membro** o **Proprietario** il sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-105">You must have **Member** or **Owner** permission on the SharePoint site.</span></span> <span data-ttu-id="3d3e4-106">Per altre informazioni, vedere [Esempi di URL per elementi di report pubblicati in un server di report in modalità SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3d3e4-106">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-shared-data-source-to-a-sharepoint-site"></a><span data-ttu-id="3d3e4-107">Per pubblicare un'origine dati condivisa in un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="3d3e4-107">To publish a shared data source to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="3d3e4-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire un progetto del server di report esistente o nuovo.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open your existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="3d3e4-109">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-109">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="3d3e4-110">Verrà visualizzata la finestra di _\<project>_ dialogo **pagine delle proprietà** .</span><span class="sxs-lookup"><span data-stu-id="3d3e4-110">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="3d3e4-111">Nella casella **Configurazione** scegliere quella da utilizzare per la pubblicazione in un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-111">Choose the **Configuration** you use to publish to a SharePoint site.</span></span>  
  
4.  <span data-ttu-id="3d3e4-112">Se si desidera pubblicare le origini dati condivise nel progetto e sovrascrivere origini dati condivise pubblicate in precedenza, impostare **OverwriteDataSources** su **True**.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-112">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="3d3e4-113">(Facoltativo) Per **TargetDataSourceFolder**, digitare un URL a una raccolta di SharePoint oppure a una cartella della raccolta,</span><span class="sxs-lookup"><span data-stu-id="3d3e4-113">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder.</span></span> <span data-ttu-id="3d3e4-114">ad esempio *http://TestServer/TestSite/Documents/DataSources*.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-114">For example, *http://TestServer/TestSite/Documents/DataSources*.</span></span>  
  
     <span data-ttu-id="3d3e4-115">Se non si specifica alcun valore, verrà utilizzato il valore **TargetReportFolder** .</span><span class="sxs-lookup"><span data-stu-id="3d3e4-115">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="3d3e4-116">Per **TargetReportFolder**, digitare l'URL di una raccolta o di una cartella della raccolta,</span><span class="sxs-lookup"><span data-stu-id="3d3e4-116">For **TargetReportFolder**, type a URL to a library or library folder.</span></span> <span data-ttu-id="3d3e4-117">ad esempio http:*//TestServer/TestSite/Documents/Reports*.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-117">For example, http:*//TestServer/TestSite/Documents/Reports*.</span></span>  
  
7.  <span data-ttu-id="3d3e4-118">Per **TargetServerURL**, digitare l'URL di un sito principale o secondario di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="3d3e4-119">Se non si specifica un sito, verrà utilizzato il sito principale predefinito,</span><span class="sxs-lookup"><span data-stu-id="3d3e4-119">If you do not specify a site, the default top-level site is used.</span></span> <span data-ttu-id="3d3e4-120">Ad esempio, http://*nomeserver*, http://*nomeserver*/*sito*o http://*nomeserver*/*sito*/*sitosecondario*.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-120">For example, http://*servername*, http://*servername*/*site*, or http://*servername*/*site*/*subsite*.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="3d3e4-121">In Esplora soluzioni fare clic con il pulsante destro del mouse sull'origine dati condivisa da pubblicare e quindi scegliere **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-121">In Solution Explorer, right-click the shared data source you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="3d3e4-122">L'origine dei dati verrà pubblicata nel percorso specificato in **TargetDataSourceFolder**.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-122">The data source is published to the location specified in **TargetDataSourceFolder**.</span></span> <span data-ttu-id="3d3e4-123">Gli eventuali errori di distribuzioni verranno visualizzati nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-123">Deployment errors appear in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3d3e4-124">Dopo la pubblicazione di un'origine dati condivisa in un sito di SharePoint, l'estensione del file viene cambiata in rsds.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-124">After you publish a shared data source to a SharePoint site, the file name extension is changed to .rsds.</span></span> <span data-ttu-id="3d3e4-125">È possibile modificare e gestire direttamente un'origine dati condivisa nel sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d3e4-125">You can edit and manage a shared data source directly on the SharePoint site.</span></span> <span data-ttu-id="3d3e4-126">Per altre informazioni, vedere [Creare e gestire origini dati condivise &#40;Reporting Services in modalità integrata SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3d3e4-126">For more information, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d3e4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d3e4-127">See Also</span></span>  
 <span data-ttu-id="3d3e4-128">[Pubblicare un report in una raccolta di SharePoint](publish-a-report-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="3d3e4-128">[Publish a Report to a SharePoint Library](publish-a-report-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="3d3e4-129">[Esempi di URL per elementi di report pubblicati in un server di report in modalità SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="3d3e4-129">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="3d3e4-130">[Finestra di dialogo Pagine delle proprietà del progetto](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="3d3e4-130">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="3d3e4-131">[Impostare le proprietà di distribuzione &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="3d3e4-131">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="3d3e4-132">[Pubblicazione di report in un server di report](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="3d3e4-132">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 [<span data-ttu-id="3d3e4-133">Usare una connessione Office Data Connection &#40;.odc&#41; ai report &#40;Reporting Services in modalità integrata SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="3d3e4-133">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
