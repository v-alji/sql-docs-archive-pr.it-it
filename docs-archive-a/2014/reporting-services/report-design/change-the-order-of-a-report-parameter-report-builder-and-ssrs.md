---
title: Modificare l'ordine di un parametro del report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: abd61e19-dba3-423c-a26c-e8bc43197d3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad9dd25be7a87fee089a48849fcc716e682e4c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722519"
---
# <a name="change-the-order-of-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="dc604-102">Modificare l'ordine di un parametro del report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="dc604-102">Change the Order of a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dc604-103">Modificare l'ordine dei parametri del report quando un parametro dipendente è elencato prima del parametro da cui dipende.</span><span class="sxs-lookup"><span data-stu-id="dc604-103">Change the order of report parameters when you have a dependent parameter that is listed before the parameter it is dependent on.</span></span> <span data-ttu-id="dc604-104">L'ordine dei parametri è importante quando sono presenti parametri di propagazione o quando si desidera indicare il valore predefinito di un parametro prima che gli utenti scelgano i valori per altri parametri.</span><span class="sxs-lookup"><span data-stu-id="dc604-104">Parameter order is important when you have cascading parameters, or when you want to show users the default value for one parameter before they choose values for other parameters.</span></span> <span data-ttu-id="dc604-105">Un parametro dipendente del report contiene un riferimento, nella query dei valori predefiniti o in quella dei valori validi, a un parametro di query che punta a un parametro del report successivo nell'elenco dei parametri contenuto nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="dc604-105">A dependent report parameter contains a reference, in either its default values query or valid values query, to a query parameter that points to a report parameter that is after it in the parameter list in the Report Data pane.</span></span>  
  
 <span data-ttu-id="dc604-106">L'ordine in cui i parametri vengono visualizzati sulla barra degli strumenti del visualizzatore di report è determinato dall'ordine dei parametri nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="dc604-106">The order that you see parameters display on the report viewer toolbar is determined by the order of the parameters in the Report Data pane.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-order-of-report-parameters"></a><span data-ttu-id="dc604-107">Per modificare l'ordine dei parametri del report</span><span class="sxs-lookup"><span data-stu-id="dc604-107">To change the order of report parameters</span></span>  
  
1.  <span data-ttu-id="dc604-108">Nel riquadro dei dati del report espandere il nodo Parametri.</span><span class="sxs-lookup"><span data-stu-id="dc604-108">In the Report Data pane, expand the Parameters node.</span></span>  
  
2.  <span data-ttu-id="dc604-109">Fare clic su un parametro e utilizzare i pulsanti freccia Su e freccia Giù sulla barra degli strumenti del riquadro dei dati del report per spostare il parametro in una posizione superiore o inferiore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dc604-109">Click a parameter and use the up and down arrow buttons on the Report Data pane toolbar to move the parameter higher or lower in the list.</span></span> <span data-ttu-id="dc604-110">La figura seguente mostra il riquadro Dati report in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="dc604-110">The following image shows the Report Data pane in Report Builder.</span></span>  
  
     <span data-ttu-id="dc604-111">![Riquadro dei dati del report](../media/reportdatapane.png "Riquadro dei dati del report")</span><span class="sxs-lookup"><span data-stu-id="dc604-111">![Report Data Pane](../media/reportdatapane.png "Report Data Pane")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc604-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc604-112">See Also</span></span>  
 <span data-ttu-id="dc604-113">[Parametri del report &#40;Generatore report e Progettazione report&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="dc604-113">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="dc604-114">[Guida Generatore report per finestre di dialogo, riquadri e procedure guidate](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="dc604-114">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="dc604-115">[Aggiungere parametri di propagazione a un report &#40;Generatore report e SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc604-115">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dc604-116">[Esercitazione: aggiungere un parametro al report &#40;Generatore report&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="dc604-116">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="dc604-117">[Aggiungere filtri del set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="dc604-117">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="dc604-118">Riferimenti alla raccolta dei parametri &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc604-118">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
