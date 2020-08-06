---
title: Concetto dei parametri di report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b0aa2159-4e49-4713-8824-5ef9a9edbc62
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b740362daea83b50a62f0b4453ce818ab21ace7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713851"
---
# <a name="report-parameters-concept-report-builder-and-ssrs"></a><span data-ttu-id="c9121-102">Concetto dei parametri di report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c9121-102">Report Parameters Concept (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c9121-103">È possibile aggiungere parametri a un report per collegare report correlati, controllare l'aspetto del report, filtrare i dati del report o per limitare l'ambito di un report a percorsi o utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="c9121-103">You can add parameters to a report to link related reports, to control the report appearance, to filter report data, or to narrow the scope of a report to specific users or locations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="c9121-104">I parametri di report vengono creati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9121-104">Report parameters are created in the following ways:</span></span>  
  
-   <span data-ttu-id="c9121-105">Automaticamente, quando si definisce la query del set di dati contenente le variabili di query.</span><span class="sxs-lookup"><span data-stu-id="c9121-105">Automatically, when you define dataset query that contains query variables.</span></span> <span data-ttu-id="c9121-106">Per ogni variabile di query, vengono creati un parametro del report e un parametro di query del set di dati con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="c9121-106">For each query variable, a corresponding dataset query parameter and report parameter with the same names are created.</span></span> <span data-ttu-id="c9121-107">Un parametro di query può essere un riferimento a una variabile do query o a un parametro di input per una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c9121-107">A query parameter can be a reference to a query variable or to an input parameter for a stored procedure.</span></span>  
  
-   <span data-ttu-id="c9121-108">Automaticamente, quando si aggiunge un riferimento a un set di dati condiviso contenente parametri di query.</span><span class="sxs-lookup"><span data-stu-id="c9121-108">Automatically, when you add a reference to a shared dataset that contains query parameters.</span></span>  
  
-   <span data-ttu-id="c9121-109">Manualmente, quando si creano parametri del report nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="c9121-109">Manually, when you create report parameters in the Report Data pane.</span></span> <span data-ttu-id="c9121-110">I parametri rappresentano una delle raccolte predefinite che è possibile includere in un'espressione di un report.</span><span class="sxs-lookup"><span data-stu-id="c9121-110">Parameters are one of the built-in collections that you can include in an expression in a report.</span></span> <span data-ttu-id="c9121-111">Poiché le espressioni sono usate per definire valori nell'intera definizione di un report, è possibile usare i parametri per controllare l'aspetto del report o per passare i valori ai sottoreport o report correlati che usano anch'essi i parametri.</span><span class="sxs-lookup"><span data-stu-id="c9121-111">Because expressions are used to define values throughout a report definition, you can use parameters to control report appearance or to pass values to related subreports or reports that also use parameters.</span></span>  
  
 <span data-ttu-id="c9121-112">Per ulteriori informazioni, vedere la pagina relativa al [Parametri report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c9121-112">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md).</span></span>  
  
 <span data-ttu-id="c9121-113">I parametri sono usati di frequente per filtrare i dati del report sia prima che dopo la restituzione dei dati al report.</span><span class="sxs-lookup"><span data-stu-id="c9121-113">Parameters are frequently used to filter report data both before and after the data is returned to the report.</span></span> <span data-ttu-id="c9121-114">Per altre informazioni, vedere [Filtro, raggruppamento e ordinamento di dati &#40;Generatore report e SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c9121-114">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="c9121-115">Quando si progetta un report, i parametri corrispondenti vengono salvati nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="c9121-115">When you design a report, report parameters are saved in the report definition.</span></span> <span data-ttu-id="c9121-116">Quando si pubblica un report, i parametri corrispondenti vengono salvati e gestiti separatamente della definizione del report.</span><span class="sxs-lookup"><span data-stu-id="c9121-116">When you publish a report, report parameters are saved and managed separately from the report definition.</span></span> <span data-ttu-id="c9121-117">Una volta salvato il report nel server di report, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9121-117">After you save the report to the report server, you can do the following:</span></span>  
  
-   <span data-ttu-id="c9121-118">Modificare i valori dei parametri del report direttamente nel server di report indipendentemente dalla definizione del report.</span><span class="sxs-lookup"><span data-stu-id="c9121-118">Change report parameter values directly on the report server independently from the report definition.</span></span>  
  
-   <span data-ttu-id="c9121-119">Creare più report collegati in cui ogni report collegato è un collegamento alla definizione del report con un set di valori di parametro separato che può essere gestito indipendentemente nel server di report.</span><span class="sxs-lookup"><span data-stu-id="c9121-119">Create multiple linked reports in which each linked report is a link to the report definition with a separate set of parameter values that can be managed independently on the report server.</span></span>  
  
 <span data-ttu-id="c9121-120">Se si intende creare snapshot, cronologie o sottoscrizioni di report in un report pubblicato, è necessario capire come i parametri del report influiscono sui requisiti di progettazione per il report.</span><span class="sxs-lookup"><span data-stu-id="c9121-120">If you plan to create report snapshots, histories, or subscriptions to a published report, you must understand how report parameters affect the design requirements for the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9121-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9121-121">See Also</span></span>  
 <span data-ttu-id="c9121-122">[Concetti relativi alla creazione di report &#40;Generatore report e SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c9121-122">[Report Authoring Concepts &#40;Report Builder and SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c9121-123">[Set di set di impostazioni e set di impostazioni di set di report incorporati &#40;Generatore report e SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c9121-123">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c9121-124">Esercitazione: Aggiungere un parametro al report &#40;Generatore report&#41;</span><span class="sxs-lookup"><span data-stu-id="c9121-124">Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;</span></span>](../tutorial-add-a-parameter-to-your-report-report-builder.md)  
  
  
