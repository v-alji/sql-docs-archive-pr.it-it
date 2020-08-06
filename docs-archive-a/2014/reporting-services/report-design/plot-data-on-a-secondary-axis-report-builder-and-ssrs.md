---
title: Tracciare i dati su un asse secondario (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 094f39bf-3634-4852-9fc3-3adec4b266e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cec58820e0373bb1e9ef2d50d022e5b4ef7e962b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711612"
---
# <a name="plot-data-on-a-secondary-axis-report-builder-and-ssrs"></a><span data-ttu-id="ed64b-102">Traccia di dati su un asse secondario (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="ed64b-102">Plot Data on a Secondary Axis (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ed64b-103">Nel grafico sono inclusi due tipi di asse: principale e secondario.</span><span class="sxs-lookup"><span data-stu-id="ed64b-103">The chart has two axis types: primary and secondary.</span></span> <span data-ttu-id="ed64b-104">L'asse secondario risulta utile quando si confrontano due set di valori con due intervalli di dati diversi che condividono una categoria comune.</span><span class="sxs-lookup"><span data-stu-id="ed64b-104">The secondary axis is useful when comparing two value sets with two distinct data ranges that share a common category.</span></span>  
  
 <span data-ttu-id="ed64b-105">Si supponga ad esempio che in un grafico vengano calcolati i valori relativi ai ricavi rispetto alle imposte nell'anno 2008.</span><span class="sxs-lookup"><span data-stu-id="ed64b-105">For example, suppose you have a chart that calculates Revenue vs. Tax for the year 2008.</span></span> <span data-ttu-id="ed64b-106">In questo caso, il periodo di tempo 2008 è comune a entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="ed64b-106">In this case, the 2008 time period is common to both value sets.</span></span> <span data-ttu-id="ed64b-107">Tuttavia, quando le due serie vengono tracciate sullo stesso asse Y, non è possibile effettuare un confronto utile, perché la scala di quest'asse è ottimizzata per i valori maggiori nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="ed64b-107">However, when both series are plotted on the same y-axis, we cannot make a useful comparison because the scale of the y-axis is optimized for the largest values in the dataset.</span></span> <span data-ttu-id="ed64b-108">Indicando i ricavi sull'asse principale e le imposte su quello secondario, è possibile visualizzare ogni serie su un proprio asse Y con una scala di valori specifica.</span><span class="sxs-lookup"><span data-stu-id="ed64b-108">If we show Revenue on the primary axis, and Tax on the secondary axis, we can display each series on its own y-axis with its own scale of values.</span></span> <span data-ttu-id="ed64b-109">Le serie condividono un asse X comune.</span><span class="sxs-lookup"><span data-stu-id="ed64b-109">The series still share a common x-axis.</span></span>  
  
 <span data-ttu-id="ed64b-110">Nelle situazioni in cui è necessario confrontare più di due serie, è consigliabile un approccio diverso per il confronto e la visualizzazione di più serie in un grafico.</span><span class="sxs-lookup"><span data-stu-id="ed64b-110">In situations where there are more than two series to be compared, consider a different approach for comparing and displaying multiple series in a chart.</span></span> <span data-ttu-id="ed64b-111">Per altre informazioni, vedere [Più serie in un grafico &#40;Generatore report e SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ed64b-111">For more information, see [Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="ed64b-112">Un esempio di questo grafico è disponibile come report di esempio.</span><span class="sxs-lookup"><span data-stu-id="ed64b-112">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="ed64b-113">Per altre informazioni sul download di questo e di altri report di esempio, vedere la pagina relativa ai [report di esempio per Generatore report e Progettazione report](https://go.microsoft.com/fwlink/?LinkId=198283) di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed64b-113">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-plot-a-series-on-the-secondary-axis"></a><span data-ttu-id="ed64b-114">Per tracciare una serie sull'asse secondario</span><span class="sxs-lookup"><span data-stu-id="ed64b-114">To plot a series on the secondary axis</span></span>  
  
1.  <span data-ttu-id="ed64b-115">Fare clic con il pulsante destro del mouse sulla serie nel grafico oppure in un campo dell'area **Valori** che si vuole visualizzare sull'asse secondario, quindi scegliere **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="ed64b-115">Right-click the series in the chart or right-click on a field in the **Values** area that you want to display on the secondary axis and click **Series Properties**.</span></span> <span data-ttu-id="ed64b-116">Verrà visualizzata la finestra di dialogo **Proprietà serie** .</span><span class="sxs-lookup"><span data-stu-id="ed64b-116">The **Series Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="ed64b-117">Fare clic su **Assi e area grafico**, quindi selezionare quale degli assi secondari si desidera abilitare, l'asse dei valori o l'asse delle categorie.</span><span class="sxs-lookup"><span data-stu-id="ed64b-117">Click **Axes and Chart Area**, and select which of the secondary axes you want to enable, the value axis or the category axis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed64b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed64b-118">See Also</span></span>  
 <span data-ttu-id="ed64b-119">[Formattazione delle etichette degli assi in un grafico &#40;Generatore report e SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ed64b-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ed64b-120">Specificare un intervallo dell'asse &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ed64b-120">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
