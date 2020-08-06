---
title: Ordinamento interattivo, mappe documento e collegamenti (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cc6ef408-4a76-408a-9d3f-033481fe21cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35d88e89ed14a205153374d44562e6d3fda92e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723427"
---
# <a name="interactive-sort-document-maps-and-links-report-builder-and-ssrs"></a><span data-ttu-id="1186c-102">Ordinamento interattivo, mappe documento e collegamenti (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="1186c-102">Interactive Sort, Document Maps, and Links (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1186c-103">In ambienti basati sul Web è possibile aggiungere alcune caratteristiche per consentire agli utenti di interagire con i report.</span><span class="sxs-lookup"><span data-stu-id="1186c-103">In Web-based environments, you can add a number of features that let your users interact with reports.</span></span> <span data-ttu-id="1186c-104">Gli utenti possono inoltre modificare l'ordinamento dei valori nel report, visualizzare o nascondere elementi nel report oppure fare clic sui collegamenti che consentono di passare ad altri report o pagine Web.</span><span class="sxs-lookup"><span data-stu-id="1186c-104">Your users can change the sort order of values in your report, show or hide items in the report, or click links that go to other reports or Web pages.</span></span> <span data-ttu-id="1186c-105">È inoltre possibile aggiungere un sommario o una mappa documento.</span><span class="sxs-lookup"><span data-stu-id="1186c-105">You can also add a table of contents or document map.</span></span> <span data-ttu-id="1186c-106">Gli utenti del report possono fare clic su elementi nel sommario o mappa documento per passare alle aree all'interno di un report.</span><span class="sxs-lookup"><span data-stu-id="1186c-106">Your report users can click items in the table of contents or document map to jump to areas within a report.</span></span>  
  
 <span data-ttu-id="1186c-107">Generatore report e Progettazione report supportano tre tipi di collegamenti, a cui sono associate le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1186c-107">Report Builder and Report Designer support three types of links with the following actions:</span></span>  
  
-   <span data-ttu-id="1186c-108">**Collegamenti a segnalibro** Consentono di passare ad altre aree all'interno del report.</span><span class="sxs-lookup"><span data-stu-id="1186c-108">**Bookmark links** Jump to other areas within the report.</span></span>  
  
-   <span data-ttu-id="1186c-109">**Collegamenti ipertestuali** Consentono di passare agli URL che specificano l'indirizzo di pagine Web o di report in un server di report usando l'accesso tramite URL.</span><span class="sxs-lookup"><span data-stu-id="1186c-109">**Hyperlinks** Jump to URLs that specify the address of Web pages or reports on a report server by using URL access.</span></span>  
  
-   <span data-ttu-id="1186c-110">**Collegamenti a report drill-through** Consentono di passare ad altri report nello stesso server di report.</span><span class="sxs-lookup"><span data-stu-id="1186c-110">**Drillthrough report links** Jump to other reports on the same report server.</span></span> <span data-ttu-id="1186c-111">Per altre informazioni, vedere [Report drill-through &#40;Generatore report e SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1186c-111">For more information, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1186c-112">I collegamenti associati ai campi del set di dati possono essere esposti ad alterazioni per finalità dannose.</span><span class="sxs-lookup"><span data-stu-id="1186c-112">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="1186c-113">Per altre informazioni, vedere [Garantire la sicurezza di report e risorse](../security/secure-reports-and-resources.md) nella [documentazione online](https://go.microsoft.com/fwlink/?LinkId=154888) di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sul sito msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1186c-113">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="1186c-114">È inoltre possibile consentire agli utenti di controllare la visualizzazione e il contenuto dei report progettando espressioni che includano riferimenti a parametri per l'ordinamento, i filtri e la visibilità.</span><span class="sxs-lookup"><span data-stu-id="1186c-114">You can also let your users control report display and content by designing expressions that include parameter references for sort, filter, and visibility.</span></span> <span data-ttu-id="1186c-115">Per altre informazioni, vedere [Parametri report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md), [Filtro, raggruppamento e ordinamento di dati &40#;Generatore report e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md), e [Aggiungere filtri per set di dati, aree dati e gruppi &40#;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span><span class="sxs-lookup"><span data-stu-id="1186c-115">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md), [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md), and [Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="1186c-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1186c-116">In This Section</span></span>  
 [<span data-ttu-id="1186c-117">Ordinamento interattivo &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1186c-117">Interactive Sort &#40;Report Builder and SSRS&#41;</span></span>](interactive-sort-report-builder-and-ssrs.md)  
 <span data-ttu-id="1186c-118">Viene illustrato come aggiungere pulsanti di ordinamento interattivi alle intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="1186c-118">Explains how to add interactive sort buttons to column headers.</span></span>  
  
 [<span data-ttu-id="1186c-119">Creare una mappa documento &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1186c-119">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
 <span data-ttu-id="1186c-120">Viene illustrato come aggiungere un sommario per supportare la navigazione all'interno di un report di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="1186c-120">Explains how to add a table of contents to support navigation in a large report.</span></span>  
  
 [<span data-ttu-id="1186c-121">Aggiungere un segnalibro a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1186c-121">Add a Bookmark to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-bookmark-to-a-report-report-builder-and-ssrs.md)  
 <span data-ttu-id="1186c-122">Viene illustrato come aggiungere segnalibri per creare collegamenti all'interno di un report.</span><span class="sxs-lookup"><span data-stu-id="1186c-122">Explains how to add bookmarks to create links within a report.</span></span>  
  
 [<span data-ttu-id="1186c-123">Aggiungere un collegamento ipertestuale a un URL &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1186c-123">Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;</span></span>](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md)  
 <span data-ttu-id="1186c-124">Viene illustrato come aggiungere un collegamento dal report a un URL.</span><span class="sxs-lookup"><span data-stu-id="1186c-124">Explains how to add a link from your report to a URL</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1186c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1186c-125">See Also</span></span>  
 [<span data-ttu-id="1186c-126">Drill-through, drill-down, sottoreport e aree dati annidate &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1186c-126">Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;</span></span>](drillthrough-drilldown-subreports-and-nested-data-regions.md)  
  
  
