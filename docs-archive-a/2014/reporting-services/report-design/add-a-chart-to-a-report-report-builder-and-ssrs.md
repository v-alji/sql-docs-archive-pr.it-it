---
title: Aggiungere un grafico a un report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6b595dc-f775-4a53-8554-74a0bf9335ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 789dd6cce10b0425833ea63f2f7941ea75970a25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623810"
---
# <a name="add-a-chart-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="3bf27-102">Aggiungere un grafico a un report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="3bf27-102">Add a Chart to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="3bf27-103">Se si desidera riepilogare i dati in formato visivo, utilizzare un'area dati del grafico.</span><span class="sxs-lookup"><span data-stu-id="3bf27-103">When you want to summarize data in a visual format, use a Chart data region.</span></span> <span data-ttu-id="3bf27-104">È importante scegliere un tipo di grafico appropriato per il tipo di dati da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="3bf27-104">It is important to choose an appropriate chart type for the type of data that you are presenting.</span></span> <span data-ttu-id="3bf27-105">Tale scelta influirà sull'interpretazione dei dati visualizzati nel grafico.</span><span class="sxs-lookup"><span data-stu-id="3bf27-105">This affects how well the data can be interpreted when put in chart form.</span></span> <span data-ttu-id="3bf27-106">Per altre informazioni, vedere [Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3bf27-106">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="3bf27-107">La soluzione più semplice per aggiungere un'area dati del grafico al report è l'esecuzione della procedura guidata Nuovo grafico.</span><span class="sxs-lookup"><span data-stu-id="3bf27-107">The simplest way to add a Chart data region to your report is to run the New Chart Wizard.</span></span> <span data-ttu-id="3bf27-108">La procedura guidata offre istogrammi, grafici a linee, a torta, a barre e ad area.</span><span class="sxs-lookup"><span data-stu-id="3bf27-108">The wizard offers column, line, pie, bar, and area charts.</span></span> <span data-ttu-id="3bf27-109">Per questi ed altri tipi di grafico, è possibile anche aggiungere un grafico manualmente.</span><span class="sxs-lookup"><span data-stu-id="3bf27-109">For these and other chart types, you can also add a chart manually.</span></span>  
  
 <span data-ttu-id="3bf27-110">Dopo avere aggiunto un'area dati del grafico all'area di progettazione, è possibile trascinare campi del set di dati del report relativi a dati numerici e non numerici nel riquadro Dati grafico del grafico.</span><span class="sxs-lookup"><span data-stu-id="3bf27-110">After you add a Chart data region to the design surface, you can drag report dataset fields for numeric and non-numeric data to the Chart Data pane of the chart.</span></span> <span data-ttu-id="3bf27-111">Fare clic sul grafico per visualizzare il riquadro Dati grafico con le tre aree: Gruppi di serie, Gruppi di categorie e Valori.</span><span class="sxs-lookup"><span data-stu-id="3bf27-111">Click the chart to display the Chart Data pane with its three areas: Series Groups, Category Groups, and Values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-chart-to-a-report-by-using-the-chart-wizard"></a><span data-ttu-id="3bf27-112">Per aggiungere un grafico a un report tramite la Creazione guidata grafico</span><span class="sxs-lookup"><span data-stu-id="3bf27-112">To add a chart to a report by using the Chart Wizard</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="3bf27-113">La Creazione guidata grafico è disponibile unicamente in Generatore report.</span><span class="sxs-lookup"><span data-stu-id="3bf27-113">The Chart Wizard is only available in Report Builder.</span></span>  
  
     <span data-ttu-id="3bf27-114">Nella scheda **Inserisci** fare clic su **Grafico**, quindi su **Creazione guidata grafico**.</span><span class="sxs-lookup"><span data-stu-id="3bf27-114">On the **Insert** tab, click **Chart**, and then click **Chart Wizard**.</span></span>  
  
2.  <span data-ttu-id="3bf27-115">Seguire i passaggi della procedura guidata **Nuovo grafico** .</span><span class="sxs-lookup"><span data-stu-id="3bf27-115">Follow the steps in the **New** Chart wizard.</span></span>  
  
3.  <span data-ttu-id="3bf27-116">Nella scheda **Home** fare clic su **Esegui** per mostrare il report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="3bf27-116">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="3bf27-117">Nella scheda **Esegui** fare clic su **Progettazione** per continuare a utilizzare il report.</span><span class="sxs-lookup"><span data-stu-id="3bf27-117">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-chart-to-a-report"></a><span data-ttu-id="3bf27-118">Per aggiungere un grafico a un report</span><span class="sxs-lookup"><span data-stu-id="3bf27-118">To add a chart to a report</span></span>  
  
1.  <span data-ttu-id="3bf27-119">Creare un report e definire un set di dati.</span><span class="sxs-lookup"><span data-stu-id="3bf27-119">Create a report and define a dataset.</span></span> <span data-ttu-id="3bf27-120">Per ulteriori informazioni, vedere [aggiungere dati a un Report &#40;Generatore report e SSRS&#41;](../report-data/report-datasets-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3bf27-120">For more information, see [Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="3bf27-121">Nella scheda **Inserisci** fare clic su **Grafico**, quindi su **Inserisci grafico**.</span><span class="sxs-lookup"><span data-stu-id="3bf27-121">On the **Insert** tab, click **Chart**, and then click **Insert Chart**.</span></span>  
  
3.  <span data-ttu-id="3bf27-122">Fare clic sul punto in cui si desidera posizionare l'angolo superiore sinistro del grafico nell'area di progettazione, quindi trascinare fino al punto in cui si desidera posizionare l'angolo inferiore destro.</span><span class="sxs-lookup"><span data-stu-id="3bf27-122">Click on the design surface where you want the upper-left corner of the chart, and then drag to where you want the lower-right corner of the chart.</span></span>  
  
     <span data-ttu-id="3bf27-123">Viene visualizzata la finestra di dialogo **Seleziona tipo di grafico** .</span><span class="sxs-lookup"><span data-stu-id="3bf27-123">The **Select Chart Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="3bf27-124">Selezionare il tipo di grafico da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="3bf27-124">Select the type of chart you want to add.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="3bf27-125">Fare clic nel grafico per visualizzare il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="3bf27-125">Click the chart to display the **Chart Data** pane.</span></span>  
  
6.  <span data-ttu-id="3bf27-126">Aggiungere uno o più campi all'area **Valori** .</span><span class="sxs-lookup"><span data-stu-id="3bf27-126">Add one or more fields to the **Values** area.</span></span> <span data-ttu-id="3bf27-127">Queste informazioni verranno tracciate sull'asse dei valori.</span><span class="sxs-lookup"><span data-stu-id="3bf27-127">This information will be plotted on the value axis.</span></span>  
  
7.  <span data-ttu-id="3bf27-128">Aggiungere un campo di raggruppamento all'area **Gruppi di categorie** .</span><span class="sxs-lookup"><span data-stu-id="3bf27-128">Add a grouping field to the **Category Groups** area.</span></span> <span data-ttu-id="3bf27-129">Quando si aggiunge questo campo all'area **Gruppi di categorie** , viene creato automaticamente un campo di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="3bf27-129">When you add this field to the **Category Groups** area, a grouping field is automatically created for you.</span></span> <span data-ttu-id="3bf27-130">Ogni gruppo rappresenta un punto dati nella serie.</span><span class="sxs-lookup"><span data-stu-id="3bf27-130">Each group represents a data point in your series.</span></span>  
  
8.  <span data-ttu-id="3bf27-131">Per riepilogare i dati in base alla categoria, fare clic con il pulsante destro del mouse sul campo dati e scegliere **Proprietà serie**.</span><span class="sxs-lookup"><span data-stu-id="3bf27-131">To summarize the data by category, right-click the data field and click **Series Properties**.</span></span> <span data-ttu-id="3bf27-132">Nella casella **Categoria** selezionare il campo categoria nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3bf27-132">In the **Category** box, select the category field from the drop-down list.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="3bf27-133">Nella scheda **Home** fare clic su **Esegui** per mostrare il report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="3bf27-133">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
10. <span data-ttu-id="3bf27-134">Nella scheda **Esegui** fare clic su **Progettazione** per continuare a utilizzare il report.</span><span class="sxs-lookup"><span data-stu-id="3bf27-134">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
 <span data-ttu-id="3bf27-135">Su grafici con assi, ad esempio grafici a barra e istogrammi, potrebbe non essere possibile visualizzare tutte le etichette sull'asse delle categorie.</span><span class="sxs-lookup"><span data-stu-id="3bf27-135">On charts with axes, such as bar and column charts, the category axis may not display all the category labels.</span></span> <span data-ttu-id="3bf27-136">Per altre informazioni su come modificare le etichette dell'asse, vedere [Specificare un intervallo dell'asse &#40;Generatore report e SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3bf27-136">For more information about how to change the axis labels, see [Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf27-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bf27-137">See Also</span></span>  
 <span data-ttu-id="3bf27-138">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3bf27-138">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3bf27-139">[Tipi di grafico &#40;Generatore report e SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3bf27-139">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3bf27-140">[Punti dati vuoti e Null nei grafici &#40;Generatore report e SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3bf27-140">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3bf27-141">[Esercitazione: Aggiunta di un grafico a barre al report (Generatore report)](https://go.microsoft.com/fwlink/?LinkId=198052) </span><span class="sxs-lookup"><span data-stu-id="3bf27-141">[Tutorial: Adding a Bar Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198052) </span></span>  
 <span data-ttu-id="3bf27-142">[Esercitazione: Aggiunta di un grafico a barre a un report (Progettazione report)](https://go.microsoft.com/fwlink/?LinkId=198042) </span><span class="sxs-lookup"><span data-stu-id="3bf27-142">[Tutorial: Adding a Bar Chart to a Report (Report Designer)](https://go.microsoft.com/fwlink/?LinkId=198042) </span></span>  
 <span data-ttu-id="3bf27-143">[Esercitazione: Aggiunta di un grafico a torta al report (Generatore report)](https://go.microsoft.com/fwlink/?LinkId=198051) </span><span class="sxs-lookup"><span data-stu-id="3bf27-143">[Tutorial: Adding a Pie Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198051) </span></span>  
 [<span data-ttu-id="3bf27-144">Esercitazione: Aggiunta di un grafico a torta a un report (Progettazione report)</span><span class="sxs-lookup"><span data-stu-id="3bf27-144">Tutorial: Adding a Pie Chart to a Report (Report Designer)</span></span>](https://go.microsoft.com/fwlink/?LinkId=198041)  
  
  
