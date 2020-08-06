---
title: Inclusione di indicatori e misuratori in un pannello del misuratore (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dff9b67-b483-4c51-a822-6dbe706a6840
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b1107745f54cd94abd7507a3e9b5a706ca5402de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723475"
---
# <a name="include-indicators-and-gauges-in-a-gauge-panel-report-builder-and-ssrs"></a><span data-ttu-id="fb41b-102">Inclusione di indicatori e misuratori in un pannello del misuratore (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="fb41b-102">Include Indicators and Gauges in a Gauge Panel (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fb41b-103">Il pannello del misuratore è il contenitore di livello superiore in cui sono presenti uno o più misuratori e indicatori.</span><span class="sxs-lookup"><span data-stu-id="fb41b-103">The gauge panel is the top-level container that holds one or more gauges and indicators.</span></span> <span data-ttu-id="fb41b-104">Gli indicatori possono essere incorporati nei misuratori o posizionati accanto a essi nel pannello del misuratore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-104">Indicators can be embedded in gauges or placed next to them in the gauge panel.</span></span>  
  
 <span data-ttu-id="fb41b-105">Se l'indicatore e il misuratore sono adiacenti all'interno del pannello del misuratore e presentano dati di campi diversi, è consigliabile aggiungere delle etichette per precisare quali dati sono riportati dal misuratore e quali dall'indicatore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-105">If the indicator and gauge are adjacent in the gauge panel and show data from different fields, you might want to add labels to make it clear what data the gauge and indicator convey.</span></span>  
  
 <span data-ttu-id="fb41b-106">È possibile impostare le opzioni del misuratore e dell'indicatore tramite espressioni.</span><span class="sxs-lookup"><span data-stu-id="fb41b-106">Gauge and indicator options can be set by using expressions.</span></span> <span data-ttu-id="fb41b-107">Per altre informazioni, vedere [Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fb41b-107">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-indicator-in-a-gauge"></a><span data-ttu-id="fb41b-108">Per incorporare un indicatore in un misuratore</span><span class="sxs-lookup"><span data-stu-id="fb41b-108">To embed an indicator in a gauge</span></span>  
  
1.  <span data-ttu-id="fb41b-109">Aprire un report esistente o crearne uno nuovo contenente una tabella e una matrice con i dati che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="fb41b-109">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="fb41b-110">Per altre informazioni, vedere [Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) o [Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fb41b-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="fb41b-111">Inserire una colonna nella tabella o nella matrice.</span><span class="sxs-lookup"><span data-stu-id="fb41b-111">Insert a column in your table or matrix.</span></span> <span data-ttu-id="fb41b-112">Per altre informazioni, vedere [Inserire o eliminare una colonna &#40;Generatore report e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fb41b-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="fb41b-113">Nel gruppo **Aree dati** della scheda **Inserisci** fare clic su **Misuratore**e quindi fare clic su una cella nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="fb41b-113">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then, and then click a cell in the new column.</span></span> <span data-ttu-id="fb41b-114">Verrà visualizzata la finestra di dialogo **Seleziona tipo di misuratore** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-114">The **Select Gauge Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="fb41b-115">Fare clic su **Radiale**.</span><span class="sxs-lookup"><span data-stu-id="fb41b-115">Click **Radial**.</span></span> <span data-ttu-id="fb41b-116">Viene selezionato il primo misuratore radiale.</span><span class="sxs-lookup"><span data-stu-id="fb41b-116">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="fb41b-117">Fare clic sul misuratore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-117">Click the gauge.</span></span> <span data-ttu-id="fb41b-118">Viene visualizzato il riquadro **Dati del misuratore** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-118">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="fb41b-119">Nell'elenco a discesa **(Non specificato)** dell'area **Valori** fare clic sul campo di cui si vogliono visualizzare i valori nel misuratore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-119">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="fb41b-120">In alternativa, trascinare il campo da utilizzare dal set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="fb41b-120">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="fb41b-121">Fare clic con il pulsante destro del mouse sul misuratore, scegliere **Aggiungi indicatore**e quindi fare clic su **Figlio**.</span><span class="sxs-lookup"><span data-stu-id="fb41b-121">Right-click the gauge, click **Add Indicator**, and then click **Child**.</span></span> <span data-ttu-id="fb41b-122">Verrà visualizzata la finestra di dialogo **Seleziona tipo indicatore** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-122">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="fb41b-123">Nel riquadro sinistro della finestra di dialogo **Seleziona tipo indicatore** fare clic sul tipo di indicatore desiderato e quindi sul set di indicatori.</span><span class="sxs-lookup"><span data-stu-id="fb41b-123">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="fb41b-124">Fare clic sull'indicatore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-124">Click the indicator.</span></span> <span data-ttu-id="fb41b-125">Viene visualizzato il riquadro **Dati del misuratore** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-125">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="fb41b-126">Nell'elenco a discesa **(Non specificato)** dell'area **Valori** fare clic sul campo di cui si vogliono visualizzare i valori come indicatore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-126">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="fb41b-127">In alternativa, trascinare il campo da utilizzare dal set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="fb41b-127">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="fb41b-128">Il campo può essere lo stesso o diverso rispetto a quello utilizzato nel misuratore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-128">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-show-an-indicator-and-gauge-side-by-side"></a><span data-ttu-id="fb41b-129">Per visualizzare un indicatore e un misuratore affiancati</span><span class="sxs-lookup"><span data-stu-id="fb41b-129">To show an indicator and gauge side by side</span></span>  
  
1.  <span data-ttu-id="fb41b-130">Aprire un report esistente o crearne uno nuovo contenente una tabella e una matrice con i dati che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="fb41b-130">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="fb41b-131">Per altre informazioni, vedere [Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) o [Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fb41b-131">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="fb41b-132">Inserire una colonna nella tabella o nella matrice.</span><span class="sxs-lookup"><span data-stu-id="fb41b-132">Insert a column in your table or matrix.</span></span> <span data-ttu-id="fb41b-133">Per altre informazioni, vedere [Inserire o eliminare una colonna &#40;Generatore report e SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fb41b-133">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="fb41b-134">Nel gruppo **Aree dati** della scheda **Inserisci** fare clic su **Misuratore**e quindi fare clic su una cella nella colonna inserita.</span><span class="sxs-lookup"><span data-stu-id="fb41b-134">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click a cell in the column you inserted.</span></span> <span data-ttu-id="fb41b-135">Verrà visualizzata la finestra di dialogo **Seleziona tipo di misuratore** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-135">The **Select Gauge Type** dialog appears.</span></span>  
  
4.  <span data-ttu-id="fb41b-136">Fare clic su **Radiale**.</span><span class="sxs-lookup"><span data-stu-id="fb41b-136">Click **Radial**.</span></span> <span data-ttu-id="fb41b-137">Viene selezionato il primo misuratore radiale.</span><span class="sxs-lookup"><span data-stu-id="fb41b-137">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="fb41b-138">Fare clic sul misuratore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-138">Click the gauge.</span></span> <span data-ttu-id="fb41b-139">Viene visualizzato il riquadro **Dati del misuratore** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-139">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="fb41b-140">Nell'elenco a discesa **(Non specificato)** dell'area **Valori** fare clic sul campo di cui si vogliono visualizzare i valori nel misuratore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-140">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="fb41b-141">In alternativa, trascinare il campo da utilizzare dal set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="fb41b-141">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="fb41b-142">Fare clic con il pulsante destro del mouse sul misuratore, scegliere **Aggiungi indicatore**e quindi **Adiacente**.</span><span class="sxs-lookup"><span data-stu-id="fb41b-142">Right-click the gauge, click **Add Indicator**, and then click **Adjacent**.</span></span> <span data-ttu-id="fb41b-143">Verrà visualizzata la finestra di dialogo **Seleziona tipo indicatore** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-143">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="fb41b-144">Nel riquadro sinistro della finestra di dialogo **Seleziona tipo indicatore** fare clic sul tipo di indicatore desiderato e quindi sul set di indicatori.</span><span class="sxs-lookup"><span data-stu-id="fb41b-144">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="fb41b-145">Fare clic sull'indicatore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-145">Click the indicator.</span></span> <span data-ttu-id="fb41b-146">Viene visualizzato il riquadro **Dati del misuratore** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-146">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="fb41b-147">Nell'elenco a discesa **(Non specificato)** dell'area **Valori** fare clic sul campo di cui si vogliono visualizzare i valori come indicatore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-147">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="fb41b-148">In alternativa, trascinare il campo da utilizzare dal set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="fb41b-148">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="fb41b-149">Il campo può essere lo stesso o diverso rispetto a quello utilizzato nel misuratore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-149">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
14. <span data-ttu-id="fb41b-150">Fare clic con il pulsante destro del mouse sul pannello del misuratore e scegliere **Aggiungi etichetta**.</span><span class="sxs-lookup"><span data-stu-id="fb41b-150">Right-click the gauge panel and click **Add Label**.</span></span> <span data-ttu-id="fb41b-151">Al pannello del misuratore viene aggiunta un'etichetta.</span><span class="sxs-lookup"><span data-stu-id="fb41b-151">A label is added to the gauge panel.</span></span> <span data-ttu-id="fb41b-152">Ripetere ancora una volta l'operazione.</span><span class="sxs-lookup"><span data-stu-id="fb41b-152">Repeat one more time.</span></span>  
  
     <span data-ttu-id="fb41b-153">Il pannello del misuratore dispone ora di due etichette.</span><span class="sxs-lookup"><span data-stu-id="fb41b-153">The gauge panel has two labels.</span></span>  
  
15. <span data-ttu-id="fb41b-154">Trascinare ogni etichetta in una posizione accanto al misuratore o all'indicatore.</span><span class="sxs-lookup"><span data-stu-id="fb41b-154">Drag each label to a location near the gauge or indicator.</span></span>  
  
16. <span data-ttu-id="fb41b-155">Fare clic con il pulsante destro del mouse sull'etichetta accanto al misuratore, fare clic su **Proprietà etichetta**e digitare il testo nella casella **Testo** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-155">Right-click the label near the gauge, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
17. <span data-ttu-id="fb41b-156">Fare clic con il pulsante destro del mouse sull'etichetta accanto all'indicatore, selezionare **Proprietà etichette**e digitare il testo nella casella **Testo** .</span><span class="sxs-lookup"><span data-stu-id="fb41b-156">Right-click the label near the indicator, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
18. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb41b-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb41b-157">See Also</span></span>  
 [<span data-ttu-id="fb41b-158">Indicatori &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fb41b-158">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
