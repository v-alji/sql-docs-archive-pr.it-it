---
title: Pubblicare report | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], publishing
- publishing reports [Reporting Services]
ms.assetid: ef5a514e-e818-4041-a8b0-15835f9a046b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb54308a6b15260d4c336950f231d0ee40836430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623871"
---
# <a name="publish-reports"></a><span data-ttu-id="ff775-102">Pubblicazione di report</span><span class="sxs-lookup"><span data-stu-id="ff775-102">Publish Reports</span></span>
  <span data-ttu-id="ff775-103">In[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]è possibile pubblicare un solo report oppure pubblicare tutti i report e le origini dati condivise di un progetto server di report in un server di report distribuendo il progetto.</span><span class="sxs-lookup"><span data-stu-id="ff775-103">From[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can publish either all the reports and shared data sources in a Report Server project to a report server by deploying the project, or you can publish a single report.</span></span> <span data-ttu-id="ff775-104">Prima di pubblicare un report è necessario specificare l'URL del server di report di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ff775-104">Before you can publish a report you must specify the URL of the target report server.</span></span> <span data-ttu-id="ff775-105">Per altre informazioni, vedere [Impostare le proprietà di distribuzione &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ff775-105">For more information, see [Set Deployment Properties &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span></span>  
  
 <span data-ttu-id="ff775-106">È possibile utilizzare la versione [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per aprire, modificare, visualizzare in anteprima, salvare e pubblicare i report di [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] e di [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ff775-106">You can use the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] version of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to open, modify, preview, save, and publish both [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] and [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] reports.</span></span> <span data-ttu-id="ff775-107">Per altre informazioni, vedere [Distribuzione e supporto della versione in SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ff775-107">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
### <a name="to-publish-all-reports-in-a-project"></a><span data-ttu-id="ff775-108">Per pubblicare tutti i report di un progetto</span><span class="sxs-lookup"><span data-stu-id="ff775-108">To publish all reports in a project</span></span>  
  
-   <span data-ttu-id="ff775-109">Scegliere \*\*Distribuisci \<report project name> \*\*dal menu **Compila** .</span><span class="sxs-lookup"><span data-stu-id="ff775-109">On the **Build** menu, click **Deploy \<report project name>**.</span></span> <span data-ttu-id="ff775-110">In alternativa, in Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto report e scegliere **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="ff775-110">Alternatively, in Solution Explorer, right-click the report project and then click **Deploy**.</span></span> <span data-ttu-id="ff775-111">È possibile visualizzare lo stato del processo di pubblicazione nella finestra Output.</span><span class="sxs-lookup"><span data-stu-id="ff775-111">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff775-112">Quando si distribuisce un progetto server di report, vengono distribuite anche le origini dati condivise nel progetto report.</span><span class="sxs-lookup"><span data-stu-id="ff775-112">When you deploy a Report Server project, the shared data sources in the report project are also deployed.</span></span>  
  
### <a name="to-publish-a-single-report"></a><span data-ttu-id="ff775-113">Per pubblicare un solo report</span><span class="sxs-lookup"><span data-stu-id="ff775-113">To publish a single report</span></span>  
  
-   <span data-ttu-id="ff775-114">In Esplora soluzioni fare clic con il pulsante destro del mouse sul report e scegliere **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="ff775-114">In Solution Explorer, right-click the report and then click **Deploy**.</span></span> <span data-ttu-id="ff775-115">È possibile visualizzare lo stato del processo di pubblicazione nella finestra Output.</span><span class="sxs-lookup"><span data-stu-id="ff775-115">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff775-116">Quando si pubblica un report, è necessario distribuire anche le origini dati condivise utilizzate dal report.</span><span class="sxs-lookup"><span data-stu-id="ff775-116">When you publish a report, you must also deploy the shared data sources that the report uses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff775-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff775-117">See Also</span></span>  
 <span data-ttu-id="ff775-118">[Pubblicazione di origini dati e report](reports/publishing-data-sources-and-reports.md) </span><span class="sxs-lookup"><span data-stu-id="ff775-118">[Publishing Data Sources and Reports](reports/publishing-data-sources-and-reports.md) </span></span>  
 <span data-ttu-id="ff775-119">[Visualizzazione in anteprima di report](reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="ff775-119">[Previewing Reports](reports/previewing-reports.md) </span></span>  
 <span data-ttu-id="ff775-120">[Pubblicazione di report in un server di report](reports/publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="ff775-120">[Publishing Reports to a Report Server](reports/publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="ff775-121">[Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ff775-121">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ff775-122">Esportazione di report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ff775-122">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](report-builder/export-reports-report-builder-and-ssrs.md)  
  
  
