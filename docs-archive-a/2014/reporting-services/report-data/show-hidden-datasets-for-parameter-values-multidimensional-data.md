---
title: Visualizzazione di set di dati nascosti per i valori dei parametri per dati multidimensionali (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb01c4ca-4fd6-4629-b595-f0d2565915df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9c005b6e7c8927316c19a3302e32f4407f9885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726535"
---
# <a name="show-hidden-datasets-for-parameter-values-for-multidimensional-data-report-builder-and-ssrs"></a><span data-ttu-id="dc2e2-102">Visualizzare set di dati nascosti per i valori dei parametri di dati multidimensionali (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="dc2e2-102">Show Hidden Datasets for Parameter Values for Multidimensional Data (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dc2e2-103">Il report potrebbe includere set di dati generati automaticamente (noti anche come set di dati nascosti) che per impostazione predefinita non vengono visualizzati nel riquadro dei dati del report.</span><span class="sxs-lookup"><span data-stu-id="dc2e2-103">Your report might include automatically-generated datasets (also known as hidden datasets) that do not appear by default in the Report Data pane.</span></span> <span data-ttu-id="dc2e2-104">Tali set di dati vengono creati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc2e2-104">These datasets are created in the following ways:</span></span>  
  
-   <span data-ttu-id="dc2e2-105">In alcune finestre Progettazione query per i database multidimensionali, è possibile specificare i campi da filtrare nell'area del filtro del riquadro Query e scegliere se creare un parametro di query per il filtro.</span><span class="sxs-lookup"><span data-stu-id="dc2e2-105">In some query designers for multidimensional databases, you can specify fields to filter on in the filter area of the query pane, and select whether to create a query parameter for the filter.</span></span> <span data-ttu-id="dc2e2-106">Se si seleziona l'opzione del parametro, i set di dati del report vengono creati automaticamente per fornire i valori validi per il parametro del report.</span><span class="sxs-lookup"><span data-stu-id="dc2e2-106">If you select the parameter option, report datasets are automatically created to provide valid values for the report parameter.</span></span>  
  
-   <span data-ttu-id="dc2e2-107">Se si importa una query basata su database multidimensionali, è possibile inoltre includere set di dati nascosti nel report.</span><span class="sxs-lookup"><span data-stu-id="dc2e2-107">If you import a query based on multidimensional databases, you might also include hidden datasets in your report.</span></span>  
  
 <span data-ttu-id="dc2e2-108">I set di dati nascosti non possono essere utilizzati da una procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="dc2e2-108">Hidden datasets are not available to use from a wizard.</span></span>  
  
 <span data-ttu-id="dc2e2-109">È possibile modificare la vista nel riquadro dei dati del report per visualizzare tutti i set di dati nel report.</span><span class="sxs-lookup"><span data-stu-id="dc2e2-109">You can change the view in the Report Data pane to display all datasets in the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-hidden-datasets"></a><span data-ttu-id="dc2e2-110">Per visualizzare set di dati nascosti</span><span class="sxs-lookup"><span data-stu-id="dc2e2-110">To display hidden datasets</span></span>  
  
-   <span data-ttu-id="dc2e2-111">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sulla cartella Datasets e quindi fare clic su **Mostra set di dati nascosti**.</span><span class="sxs-lookup"><span data-stu-id="dc2e2-111">In the Report Data pane, right-click the Datasets folder, and then click **Show Hidden Datasets**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2e2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc2e2-112">See Also</span></span>  
 <span data-ttu-id="dc2e2-113">[Progettazione query &#40;Generatore report&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="dc2e2-113">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="dc2e2-114">[Strumenti di progettazione query in Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="dc2e2-114">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 <span data-ttu-id="dc2e2-115">[Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc2e2-115">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dc2e2-116">Aggiungere dati a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc2e2-116">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
  
  
