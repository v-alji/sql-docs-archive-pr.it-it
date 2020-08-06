---
title: Pubblicazione di origini dati e report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing data sources [Reporting Services]
- publishing reports [Reporting Services]
- data sources [Reporting Services], managing
ms.assetid: 3a740f8a-1060-4ec3-938b-2305b6887ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 941362afde1cfe5dd3d235c9f243fb17875adadc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712716"
---
# <a name="publishing-data-sources-and-reports"></a><span data-ttu-id="297ad-102">Pubblicazione di origini dati e report</span><span class="sxs-lookup"><span data-stu-id="297ad-102">Publishing Data Sources and Reports</span></span>
  <span data-ttu-id="297ad-103">Prima di pubblicare il report, è necessario visualizzare l'anteprima del report per verificarne l'aspetto durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="297ad-103">Before publishing your report, you should preview the report to see how it will look when it is run.</span></span> <span data-ttu-id="297ad-104">È possibile modificare la progettazione finché non si è soddisfatti dei risultati.</span><span class="sxs-lookup"><span data-stu-id="297ad-104">You can continue to refine the design until you are satisfied with the results.</span></span>  
  
 <span data-ttu-id="297ad-105">Dopo aver progettato e aver verificato il report, è possibile condividerlo con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="297ad-105">After you design and test your report, you may want to share it with other individuals.</span></span> <span data-ttu-id="297ad-106">Per condividere il report, è necessario pubblicarlo o *distribuirlo*, in un server di report o in un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="297ad-106">To share your report, you need to publish, or *deploy*, it to a report server or SharePoint site.</span></span> <span data-ttu-id="297ad-107">Dopo la pubblicazione, il report potrà essere eseguito dagli utenti che dispongono delle autorizzazioni per il server di report o per il sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="297ad-107">After it has been published, individuals who have permissions to the report server or the SharePoint site can run your report.</span></span> <span data-ttu-id="297ad-108">Gli utenti con autorizzazioni di amministratore sul server di report possono inoltre creare sottoscrizioni al report per consentire l'aggiornamento e l'invio del report agli utenti a intervalli specifici.</span><span class="sxs-lookup"><span data-stu-id="297ad-108">In addition, a person with administrator permissions on the report server can create subscriptions to your report so that the report can be updated and sent to users on a regular schedule.</span></span>  
  
 <span data-ttu-id="297ad-109">Se per la creazione del report è stata utilizzata un'origine dei dati condivisa, è necessario pubblicarla nello stesso percorso del report.</span><span class="sxs-lookup"><span data-stu-id="297ad-109">If you used a shared data source to create your report, you need to publish it to the same location as the report.</span></span> <span data-ttu-id="297ad-110">Analogamente ai report, le origini dei dati condivise possono essere gestite separatamente sul server di report.</span><span class="sxs-lookup"><span data-stu-id="297ad-110">Like reports, shared data sources can be managed separately on the report server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="297ad-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="297ad-111">In This Section</span></span>  
 [<span data-ttu-id="297ad-112">Visualizzazione in anteprima di report</span><span class="sxs-lookup"><span data-stu-id="297ad-112">Previewing Reports</span></span>](previewing-reports.md)  
 <span data-ttu-id="297ad-113">Viene descritto come visualizzare l'anteprima di un report prima di pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="297ad-113">Describes how to preview a report before you publish it.</span></span>  
  
 [<span data-ttu-id="297ad-114">Pubblicazione dei report in un server di report</span><span class="sxs-lookup"><span data-stu-id="297ad-114">Publishing Reports to a Report Server</span></span>](publishing-reports-to-a-report-server.md)  
 <span data-ttu-id="297ad-115">Viene descritto come pubblicare un report in un server di report.</span><span class="sxs-lookup"><span data-stu-id="297ad-115">Describes how to publish a report to a report server.</span></span>  
  
 [<span data-ttu-id="297ad-116">Esempi di URL per elementi di report pubblicati in un server di report in modalità SharePoint &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="297ad-116">URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;</span></span>](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md)  
 <span data-ttu-id="297ad-117">Viene descritto come pubblicare un report in un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="297ad-117">Describes how to publish a report to a SharePoint site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="297ad-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="297ad-118">See Also</span></span>  
 <span data-ttu-id="297ad-119">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="297ad-119">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="297ad-120">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="297ad-120">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="297ad-121">[Layout di pagina e rendering &#40;Generatore report e SSRS&#41;](../report-design/page-layout-and-rendering-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="297ad-121">[Page Layout and Rendering &#40;Report Builder and SSRS&#41;](../report-design/page-layout-and-rendering-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="297ad-122">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="297ad-122">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="297ad-123">[Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="297ad-123">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="297ad-124">[Esportazione di report &#40;Generatore report e SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="297ad-124">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="297ad-125">Stampa di report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="297ad-125">Print Reports &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/print-reports-report-builder-and-ssrs.md)  
  
  
