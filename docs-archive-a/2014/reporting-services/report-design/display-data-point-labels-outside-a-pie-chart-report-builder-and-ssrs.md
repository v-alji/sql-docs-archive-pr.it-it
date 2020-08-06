---
title: Visualizzare le etichette dei punti dati al di fuori di un grafico a torta (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 959b7574-cf43-470b-b592-4944d8a9948f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dd4f38f24d2729acacfa3520635b93d8af2e9433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721180"
---
# <a name="display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="65451-102">Visualizzazione delle etichette dei punti dati al di fuori di un grafico a torta (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="65451-102">Display Data Point Labels Outside a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="65451-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]le etichette del grafico a torta sono ottimizzate per essere visualizzate solo su diverse sezioni di dati.</span><span class="sxs-lookup"><span data-stu-id="65451-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], pie chart labeling is optimized to display labels on only several slices of data.</span></span> <span data-ttu-id="65451-104">Se il grafico a torta contiene un numero eccessivo di sezioni, è possibile che le etichette si sovrappongano.</span><span class="sxs-lookup"><span data-stu-id="65451-104">Labels may overlap if the pie chart contains too many slices.</span></span> <span data-ttu-id="65451-105">Per risolvere questo problema, è possibile visualizzare le etichette al di fuori del grafico a torta, lasciando più spazio per le etichette dati più lunghe.</span><span class="sxs-lookup"><span data-stu-id="65451-105">One solution is to display the labels outside the pie chart, which may create more room for longer data labels.</span></span> <span data-ttu-id="65451-106">Se le etichette continuano a sovrapporsi, è possibile creare più spazio abilitando gli effetti 3D.</span><span class="sxs-lookup"><span data-stu-id="65451-106">If you find that your labels still overlap, you can create more space for them by enabling 3D.</span></span> <span data-ttu-id="65451-107">In questo modo il diametro del grafico a torta viene ridotto, creando uno spazio maggiore intorno al grafico.</span><span class="sxs-lookup"><span data-stu-id="65451-107">This reduces the diameter of the pie chart, creating more space around the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-data-point-labels-inside-a-pie-chart"></a><span data-ttu-id="65451-108">Per visualizzare le etichette dei punti dati all'interno di un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="65451-108">To display data point labels inside a pie chart</span></span>  
  
1.  <span data-ttu-id="65451-109">Aggiungere un grafico a torta al report.</span><span class="sxs-lookup"><span data-stu-id="65451-109">Add a pie chart to your report.</span></span> <span data-ttu-id="65451-110">Per altre informazioni, vedere [Aggiungere un grafico a un report &#40;Generatore report e SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="65451-110">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="65451-111">Nell'area di progettazione fare clic con il pulsante destro del mouse sul grafico, quindi scegliere **Mostra etichette dati**.</span><span class="sxs-lookup"><span data-stu-id="65451-111">On the design surface, right-click on the chart and select **Show Data Labels**.</span></span>  
  
### <a name="to-display-data-point-labels-outside-a-pie-chart"></a><span data-ttu-id="65451-112">Per visualizzare le etichette dei punti dati al di fuori di un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="65451-112">To display data point labels outside a pie chart</span></span>  
  
1.  <span data-ttu-id="65451-113">Creare un grafico a torta e visualizzare le etichette dati.</span><span class="sxs-lookup"><span data-stu-id="65451-113">Create a pie chart and display the data labels.</span></span>  
  
2.  <span data-ttu-id="65451-114">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="65451-114">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="65451-115">Nell'area di progettazione fare clic sulla torta stessa per visualizzare le proprietà **Categoria** nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="65451-115">On the design surface, click on the pie itself to display the **Category** properties in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="65451-116">Espandere il nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="65451-116">Expand the **CustomAttributes** node.</span></span> <span data-ttu-id="65451-117">Verrà visualizzato un elenco di attributi per il grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="65451-117">A list of attributes for the pie chart is displayed.</span></span>  
  
5.  <span data-ttu-id="65451-118">Impostare la proprietà **PieLabelStyle** su **Outside**.</span><span class="sxs-lookup"><span data-stu-id="65451-118">Set the **PieLabelStyle** property to **Outside**.</span></span>  
  
6.  <span data-ttu-id="65451-119">Impostare la `PieLineColor` proprietà su **nero**.</span><span class="sxs-lookup"><span data-stu-id="65451-119">Set the `PieLineColor` property to **Black**.</span></span> <span data-ttu-id="65451-120">La proprietà PieLineColor definisce le righe di callout per ogni etichetta di punti dati.</span><span class="sxs-lookup"><span data-stu-id="65451-120">The PieLineColor property defines callout lines for each data point label.</span></span>  
  
### <a name="to-prevent-overlapping-labels-displayed-outside-a-pie-chart"></a><span data-ttu-id="65451-121">Per impedire la sovrapposizione delle etichette visualizzate all'esterno di un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="65451-121">To prevent overlapping labels displayed outside a pie chart</span></span>  
  
1.  <span data-ttu-id="65451-122">Creare un grafico a torta con etichette esterne.</span><span class="sxs-lookup"><span data-stu-id="65451-122">Create a pie chart with external labels.</span></span>  
  
2.  <span data-ttu-id="65451-123">Nell'area di progettazione fare clic con il pulsante destro del mouse all'esterno del grafico a torta, ma all'interno dei bordi del grafico e selezionare **Proprietà area grafico**. Viene visualizzata la finestra di dialogo **Proprietà area grafico** .</span><span class="sxs-lookup"><span data-stu-id="65451-123">On the design surface, right-click outside the pie chart but inside the chart borders and select **Chart Area Properties**.The **Chart AreaProperties** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="65451-124">Nella scheda **Opzioni 3D** selezionare **Abilita 3D**.</span><span class="sxs-lookup"><span data-stu-id="65451-124">On the **3D Options** tab, select **Enable 3D**.</span></span>  
  
4.  <span data-ttu-id="65451-125">Se si desidera maggior spazio nel grafico per le etichette mantenendo un aspetto bidimensionale, impostare le proprietà **Rotazione** e **Inclinazione** su **0**.</span><span class="sxs-lookup"><span data-stu-id="65451-125">If you want the chart to have more room for labels but still appear two-dimensional, set the **Rotation** and **Inclination** properties to **0**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65451-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65451-126">See Also</span></span>  
 <span data-ttu-id="65451-127">[Grafici a torta &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="65451-127">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="65451-128">[Raccogliere piccole sezioni in un grafico a torta &#40;Generatore report e SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="65451-128">[Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="65451-129">Visualizzazione di valori percentuale in un grafico a torta &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="65451-129">Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
