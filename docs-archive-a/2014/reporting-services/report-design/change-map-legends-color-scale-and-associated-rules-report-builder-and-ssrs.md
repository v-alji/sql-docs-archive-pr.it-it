---
title: Modificare legende della mappa, scala di colori e regole associate (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.maprulesdistribution.f1
- "10512"
- "10539"
- "10533"
- sql12.rtp.rptdesigner.mappointlayerproperties.typerules.f1
- "10534"
- sql12.rtp.rptdesigner.maplegendproperties.general.f1
- sql12.rtp.rptdesigner.mapdistancescaleproperties.general.f1
- "10516"
- sql12.rtp.rptdesigner.mapcolorscaleproperties.labels.f1
- sql12.rtp.rptdesigner.maplegendtitleproperties.general.f1
- "10514"
- sql12.rtp.rptdesigner.shared.mapruleslegend.f1
- sql12.rtp.rptdesigner.mapcolorscaleproperties.general.f1
- sql12.rtp.rptdesigner.shared.embeddedlabels.f1
- "10513"
- sql12.rtp.rptdesigner.mappointlayerproperties.sizerules.f1
- sql12.rtp.rptdesigner.mapcolorscaletitleproperties.general.f1
- "10510"
- "10509"
- "10540"
- "10517"
ms.assetid: a1d691b2-c5ae-420f-af60-b7c54a7385a4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 17220c12e672ce49d3c5b1023f2a00db04e7613e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626509"
---
# <a name="change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs"></a><span data-ttu-id="437c5-102">Modificare legende della mappa, scala dei colori e regole associate (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="437c5-102">Change Map Legends, Color Scale, and Associated Rules (Report Builder and SSRS)</span></span>
  <span data-ttu-id="437c5-103">In una mappa possono essere incluse legende, una scala dei colori e una scala distanza.</span><span class="sxs-lookup"><span data-stu-id="437c5-103">A map can contain map legends, a color scale, and a distance scale.</span></span> <span data-ttu-id="437c5-104">Questi parti di una mappa consentono agli utenti di interpretare la visualizzazione dei dati sulla mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-104">These parts of a map help users interpret the data visualization on the map.</span></span>  
  
 <span data-ttu-id="437c5-105">Le legende includono le parti seguenti di una mappa:</span><span class="sxs-lookup"><span data-stu-id="437c5-105">Legends include the following parts of a map:</span></span>  
  
-   <span data-ttu-id="437c5-106">**Legenda mappa** Visualizza una guida che agevola l'interpretazione dei dati analitici che variano la visualizzazione degli elementi di una mappa su un livello mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-106">**Map legend** Displays a guide to help interpret the analytical data that varies the display of a map elements on a map layer.</span></span> <span data-ttu-id="437c5-107">Una mappa può presentare più legende.</span><span class="sxs-lookup"><span data-stu-id="437c5-107">A map can have multiple legends.</span></span> <span data-ttu-id="437c5-108">Per ogni livello mappa, specificare quale legenda utilizzare.</span><span class="sxs-lookup"><span data-stu-id="437c5-108">For each map layer, you A specify which legend to use.</span></span> <span data-ttu-id="437c5-109">Una legenda può fornire una guida a più di un livello mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-109">A legend can provide a guide to more than one map layer.</span></span>  
  
-   <span data-ttu-id="437c5-110">**Scala dei colori** Visualizza una guida che agevola l'interpretazione dei colori sulla mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-110">**Color scale** Displays a guide to help interpret colors on the map.</span></span> <span data-ttu-id="437c5-111">Una mappa dispone di una scala dei colori.</span><span class="sxs-lookup"><span data-stu-id="437c5-111">A map has one color scale.</span></span> <span data-ttu-id="437c5-112">Più livelli possono fornire i dati per la scala dei colori.</span><span class="sxs-lookup"><span data-stu-id="437c5-112">Multiple layers can provide the data for the color scale.</span></span>  
  
-   <span data-ttu-id="437c5-113">**Scala distanza** Visualizza una guida che agevola l'interpretazione della scala della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-113">**Distance scale** Displays a guide to help interpret the scale of the map.</span></span> <span data-ttu-id="437c5-114">Una mappa dispone di una scala distanza.</span><span class="sxs-lookup"><span data-stu-id="437c5-114">A map has one distance scale.</span></span> <span data-ttu-id="437c5-115">Il valore di zoom corrente del viewport mappa determina la scala distanza.</span><span class="sxs-lookup"><span data-stu-id="437c5-115">The current map viewport zoom value determines the distance scale.</span></span>  
  
 <span data-ttu-id="437c5-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span><span class="sxs-lookup"><span data-stu-id="437c5-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><a name="Viewport"></a> <span data-ttu-id="437c5-117">Per modificare la posizione di una legenda rispetto al viewport</span><span class="sxs-lookup"><span data-stu-id="437c5-117">To change the position of a legend relative to the viewport</span></span>  
  
#### <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><span data-ttu-id="437c5-118">Per modificare la posizione di una legenda rispetto al viewport</span><span class="sxs-lookup"><span data-stu-id="437c5-118">To change the position of a legend relative to the viewport</span></span>  
  
1.  <span data-ttu-id="437c5-119">Nella visualizzazione della struttura fare clic con il pulsante destro del mouse sulla legenda e aprire la _\<report item->_ pagina **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="437c5-119">In Design view, right-click the legend and open the _\<report item->_**Properties** page.</span></span>  
  
2.  <span data-ttu-id="437c5-120">In **Posizione**fare clic sulla posizione che specifica il punto in cui visualizzare la legenda rispetto al viewport.</span><span class="sxs-lookup"><span data-stu-id="437c5-120">In **Position**, click the location that specifies where to display the legend relative to the viewport.</span></span>  
  
3.  <span data-ttu-id="437c5-121">Per visualizzare la legenda al di fuori del viewport, selezionare **Mostra \<report item> all'esterno del viewport**.</span><span class="sxs-lookup"><span data-stu-id="437c5-121">To display the legend outside the viewport, select **Show \<report item> outside viewport**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="437c5-122">Nell'anteprima, le legende della mappa e la scala dei colori vengono visualizzate solo se sono disponibili i risultati delle regole correlate a tale legenda.</span><span class="sxs-lookup"><span data-stu-id="437c5-122">In preview, map legends and the color scale appear only when there are results from the rules related to that legend.</span></span> <span data-ttu-id="437c5-123">Se non vi sono elementi da visualizzare, la legenda non viene mostrata nel report di cui è stato eseguito il rendering.</span><span class="sxs-lookup"><span data-stu-id="437c5-123">If there are no items to display, the legend does not appear in the rendered report.</span></span>  
  
  
  
##  <a name="to-change-the-layout-of-a-map-legend"></a><a name="MapLegend"></a> <span data-ttu-id="437c5-124">Per modificare il layout della legenda di una mappa</span><span class="sxs-lookup"><span data-stu-id="437c5-124">To change the layout of a map legend</span></span>  
  
#### <a name="to-change-the-layout-of-a-map-legend"></a><span data-ttu-id="437c5-125">Per modificare il layout della legenda di una mappa</span><span class="sxs-lookup"><span data-stu-id="437c5-125">To change the layout of a map legend</span></span>  
  
1.  <span data-ttu-id="437c5-126">Nella visualizzazione struttura fare clic con il pulsante destro del mouse sulla legenda e aprire la pagina **Proprietà legenda** .</span><span class="sxs-lookup"><span data-stu-id="437c5-126">In Design view, right-click the legend and open the **Legend Properties** page.</span></span>  
  
2.  <span data-ttu-id="437c5-127">In **Layout legenda**fare clic sul layout della tabella da usare per la legenda.</span><span class="sxs-lookup"><span data-stu-id="437c5-127">In **Legend layout**, click the table layout that you want to use for the legend.</span></span> <span data-ttu-id="437c5-128">Selezionando opzioni diverse, il layout sull'area di progettazione cambia.</span><span class="sxs-lookup"><span data-stu-id="437c5-128">As you click different options, the layout on the design surface changes.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-show-or-hide-a-map-legend-title"></a><a name="MapLegendTitle"></a> <span data-ttu-id="437c5-129">Per mostrare o nascondere il titolo della legenda di una mappa</span><span class="sxs-lookup"><span data-stu-id="437c5-129">To show or hide a map legend title</span></span>  
  
#### <a name="to-show-or-hide-a-map-legend-title"></a><span data-ttu-id="437c5-130">Per mostrare o nascondere il titolo della legenda di una mappa</span><span class="sxs-lookup"><span data-stu-id="437c5-130">To show or hide a map legend title</span></span>  
  
-   <span data-ttu-id="437c5-131">Fare clic con il pulsante destro del mouse sulla legenda della mappa nell'area di progettazione e quindi scegliere **Mostra titolo legenda**.</span><span class="sxs-lookup"><span data-stu-id="437c5-131">Right-click the map legend on the design surface, and then click **Show Legend Title**.</span></span>  
  
  
  
##  <a name="to-show-or-hide-a-color-scale-title"></a><a name="ColorScaleTitle"></a> <span data-ttu-id="437c5-132">Per mostrare o nascondere il titolo della scala dei colori</span><span class="sxs-lookup"><span data-stu-id="437c5-132">To show or hide a color scale title</span></span>  
  
#### <a name="to-show-or-hide-a-color-scale-title"></a><span data-ttu-id="437c5-133">Per mostrare o nascondere il titolo della scala dei colori</span><span class="sxs-lookup"><span data-stu-id="437c5-133">To show or hide a color scale title</span></span>  
  
-   <span data-ttu-id="437c5-134">Fare clic con il pulsante destro del mouse sulla scala dei colori nell'area di progettazione e quindi scegliere **Mostra titolo scala dei colori**.</span><span class="sxs-lookup"><span data-stu-id="437c5-134">Right-click the color scale on the design surface, and then click **Show Color Scale Title**.</span></span>  
  
  
  
##  <a name="to-move-items-out-of-the-first-legend"></a><a name="MoveItems"></a> <span data-ttu-id="437c5-135">Per spostare elementi all'esterno della prima legenda</span><span class="sxs-lookup"><span data-stu-id="437c5-135">To move items out of the first legend</span></span>  
 <span data-ttu-id="437c5-136">Creare il numero di legende aggiuntive desiderato, quindi aggiornare le regole per ogni livello mappa per specificare in quale legenda visualizzare i risultati delle regole.</span><span class="sxs-lookup"><span data-stu-id="437c5-136">Create as many additional legends as you need and then update the rules for each map layer specify which legend to display the rule results in.</span></span>  
  
#### <a name="to-create-a-new-legend"></a><span data-ttu-id="437c5-137">Per creare una nuova legenda</span><span class="sxs-lookup"><span data-stu-id="437c5-137">To create a new legend</span></span>  
  
-   <span data-ttu-id="437c5-138">Nella visualizzazione della struttura fare clic con il pulsante destro del mouse sulla mappa all'esterno del viewport e quindi scegliere **Aggiungi legenda**.</span><span class="sxs-lookup"><span data-stu-id="437c5-138">In Design view, right-click the map outside the map viewport, and then click **Add Legend**.</span></span>  
  
     <span data-ttu-id="437c5-139">Una nuova legenda verrà visualizzata sulla mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-139">A new legend appears on the map.</span></span>  
  
#### <a name="to-display-rule-results-in-a-legend"></a><span data-ttu-id="437c5-140">Per visualizzare i risultati delle regole in una legenda</span><span class="sxs-lookup"><span data-stu-id="437c5-140">To display rule results in a legend</span></span>  
  
1.  <span data-ttu-id="437c5-141">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-141">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-142">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola colore**.</span><span class="sxs-lookup"><span data-stu-id="437c5-142">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-143">Fare clic su **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="437c5-143">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="437c5-144">Nell'elenco a discesa **Mostra in questa legenda** fare clic sul nome della legenda in cui visualizzare i risultati della regola.</span><span class="sxs-lookup"><span data-stu-id="437c5-144">In the **Show in this legend** drop-down list, click the name of the legend to display the rule results in.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-a-template-style"></a><a name="TemplateStyle"></a> <span data-ttu-id="437c5-145">Per variare i colori degli elementi della mappa in base a uno stile modello</span><span class="sxs-lookup"><span data-stu-id="437c5-145">To vary map element colors based on a template style</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-a-template-style"></a><span data-ttu-id="437c5-146">Per variare i colori degli elementi della mappa in base a uno stile modello</span><span class="sxs-lookup"><span data-stu-id="437c5-146">To vary map element colors based on a template style</span></span>  
  
1.  <span data-ttu-id="437c5-147">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-147">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-148">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola colore**.</span><span class="sxs-lookup"><span data-stu-id="437c5-148">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-149">Fare clic su **Applica stile modello**.</span><span class="sxs-lookup"><span data-stu-id="437c5-149">Click **Apply template style**.</span></span>  
  
     <span data-ttu-id="437c5-150">Uno stile modello consente di specificare lo stile del carattere e del bordo, nonché la tavolozza colori.</span><span class="sxs-lookup"><span data-stu-id="437c5-150">A template style specifies font, border style, and color palette.</span></span> <span data-ttu-id="437c5-151">A ogni elemento della mappa viene assegnato un colore diverso dall'apposita tavolozza per il tema specificato nella Creazione guidata mappa o Creazione guidata livello mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-151">Each map element is assigned a different color from the color palette for the theme that was specified in the Map Wizard or Map Layer Wizard.</span></span> <span data-ttu-id="437c5-152">Si tratta dell'unica opzione che si applica ai livelli che non dispongono di dati analitici associati.</span><span class="sxs-lookup"><span data-stu-id="437c5-152">This is the only option that applies to layers that do not have associated analytical data.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-palette"></a><a name="ColorPalette"></a> <span data-ttu-id="437c5-153">Per variare i colori degli elementi della mappa in base a una tavolozza colori</span><span class="sxs-lookup"><span data-stu-id="437c5-153">To vary map element colors based on color palette</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-palette"></a><span data-ttu-id="437c5-154">Per variare i colori degli elementi della mappa in base a una tavolozza colori</span><span class="sxs-lookup"><span data-stu-id="437c5-154">To vary map element colors based on color palette</span></span>  
  
1.  <span data-ttu-id="437c5-155">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-155">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-156">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola colore**.</span><span class="sxs-lookup"><span data-stu-id="437c5-156">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-157">Fare clic su **Visualizza dati tramite tavolozza colori**.</span><span class="sxs-lookup"><span data-stu-id="437c5-157">Click **Visualize data by using color palette**.</span></span>  
  
     <span data-ttu-id="437c5-158">Questa opzione consente di utilizzare una tavolozza predefinita o personalizzata specificata.</span><span class="sxs-lookup"><span data-stu-id="437c5-158">This option uses a built-in or custom palette that you specify.</span></span> <span data-ttu-id="437c5-159">A seconda dei dati analitici correlati, a ogni elemento della mappa viene assegnato un colore o una sfumatura di colore diverso dalla tavolozza.</span><span class="sxs-lookup"><span data-stu-id="437c5-159">Based on related analytical data, each map element is assigned a different color or shade of color from the palette.</span></span>  
  
4.  <span data-ttu-id="437c5-160">In **Campo dati**digitare il nome del campo che contiene i dati analitici da visualizzare per colore.</span><span class="sxs-lookup"><span data-stu-id="437c5-160">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="437c5-161">In **Tavolozza**selezionare il nome della tavolozza da usare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="437c5-161">In **Palette**, from the drop-down list, select the name of the palette to use.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-ranges"></a><a name="ColorRanges"></a> <span data-ttu-id="437c5-162">Per variare i colori degli elementi della mappa in base a intervalli di colori</span><span class="sxs-lookup"><span data-stu-id="437c5-162">To vary map element colors based on color ranges</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-ranges"></a><span data-ttu-id="437c5-163">Per variare i colori degli elementi della mappa in base a intervalli di colori</span><span class="sxs-lookup"><span data-stu-id="437c5-163">To vary map element colors based on color ranges</span></span>  
  
1.  <span data-ttu-id="437c5-164">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-164">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-165">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola colore**.</span><span class="sxs-lookup"><span data-stu-id="437c5-165">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-166">Fare clic su **Visualizza dati tramite intervalli colori**.</span><span class="sxs-lookup"><span data-stu-id="437c5-166">Click **Visualize data by using color ranges**.</span></span>  
  
     <span data-ttu-id="437c5-167">Questa opzione, combinata con i colori iniziale, intermedio e finale indicati in questa pagina e le opzioni che si specificano nella pagina **Distribuzione** , consentono di dividere i dati analitici correlati in intervalli.</span><span class="sxs-lookup"><span data-stu-id="437c5-167">This option, combined with the start, middle, and end colors that you specify on this page and the options that you specify on the **Distribution** page, divide the related analytical data into ranges.</span></span> <span data-ttu-id="437c5-168">L'elaboratore di report assegna il colore adatto a ogni elemento della mappa in base ai relativi dati associati e all'intervallo di cui fa parte.</span><span class="sxs-lookup"><span data-stu-id="437c5-168">The report processor assigns the appropriate color to each map element based on the its associated data and the range that it falls into.</span></span>  
  
4.  <span data-ttu-id="437c5-169">In **Campo dati**digitare il nome del campo che contiene i dati analitici da visualizzare per colore.</span><span class="sxs-lookup"><span data-stu-id="437c5-169">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="437c5-170">In **Colore iniziale**specificare il colore da usare per l'intervallo minimo.</span><span class="sxs-lookup"><span data-stu-id="437c5-170">In **Start color**, specify the color to use for the lowest range.</span></span>  
  
6.  <span data-ttu-id="437c5-171">In **Colore intermedio**specificare il colore da usare per l'intervallo intermedio.</span><span class="sxs-lookup"><span data-stu-id="437c5-171">In **Middle color**, specify the color to use for the middle range.</span></span>  
  
7.  <span data-ttu-id="437c5-172">In **Colore finale**specificare il colore da usare per l'intervallo massimo.</span><span class="sxs-lookup"><span data-stu-id="437c5-172">In **End color**, specify the color to use for the highest range.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-custom-colors"></a><a name="CustomColors"></a> <span data-ttu-id="437c5-173">Per variare i colori degli elementi della mappa in base a colori personalizzati</span><span class="sxs-lookup"><span data-stu-id="437c5-173">To vary map element colors based on custom colors</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-custom-colors"></a><span data-ttu-id="437c5-174">Per variare i colori degli elementi della mappa in base a colori personalizzati</span><span class="sxs-lookup"><span data-stu-id="437c5-174">To vary map element colors based on custom colors</span></span>  
  
1.  <span data-ttu-id="437c5-175">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-175">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-176">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola colore**.</span><span class="sxs-lookup"><span data-stu-id="437c5-176">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-177">Fare clic su **Visualizza dati tramite colori personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="437c5-177">Click **Visualize data by using custom colors**.</span></span>  
  
     <span data-ttu-id="437c5-178">Questa opzione consente di utilizzare l'elenco di colori specificato.</span><span class="sxs-lookup"><span data-stu-id="437c5-178">This option uses the list of colors that you specify.</span></span> <span data-ttu-id="437c5-179">A seconda dei dati analitici correlati, a ogni elemento della mappa viene assegnato un colore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="437c5-179">Based on related analytical data, each map element is assigned a color from the list.</span></span> <span data-ttu-id="437c5-180">Se il numero di elementi della mappa è maggiore dei colori disponibili, non viene assegnato nessun colore.</span><span class="sxs-lookup"><span data-stu-id="437c5-180">If there are more map elements than colors, no color is assigned.</span></span>  
  
4.  <span data-ttu-id="437c5-181">In **Campo dati**digitare il nome del campo che contiene i dati analitici da visualizzare per colore.</span><span class="sxs-lookup"><span data-stu-id="437c5-181">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="437c5-182">In **Colori personalizzati**fare clic su **Aggiungi** per specificare ogni colore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="437c5-182">In **Custom colors**, click **Add** to specify each custom color.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-set-distribution-options-for-a-legend"></a><a name="DistributionOptions"></a> <span data-ttu-id="437c5-183">Per impostare opzioni di distribuzione per una legenda</span><span class="sxs-lookup"><span data-stu-id="437c5-183">To set distribution options for a legend</span></span>  
  
#### <a name="to-set-distribution-options-for-a-legend"></a><span data-ttu-id="437c5-184">Per impostare opzioni di distribuzione per una legenda</span><span class="sxs-lookup"><span data-stu-id="437c5-184">To set distribution options for a legend</span></span>  
  
1.  <span data-ttu-id="437c5-185">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-185">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-186">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola colore**.</span><span class="sxs-lookup"><span data-stu-id="437c5-186">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-187">Selezionare l'opzione **Visualizza dati tramite** \<rule type\> .</span><span class="sxs-lookup"><span data-stu-id="437c5-187">Select the **Visualize data by using** \<rule type\> option.</span></span> <span data-ttu-id="437c5-188">Per usare le opzioni di distribuzione, è necessario creare intervalli nella pagina **Distribuzione** in base ai dati analitici associati al livello.</span><span class="sxs-lookup"><span data-stu-id="437c5-188">To use distribution options, you must create ranges on the **Distribution** page based on analytical data that is associated with the layer.</span></span>  
  
4.  <span data-ttu-id="437c5-189">Fare clic su **Distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="437c5-189">Click **Distribution**.</span></span>  
  
5.  <span data-ttu-id="437c5-190">Selezionare uno dei seguenti tipi di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="437c5-190">Select one of the following distribution types:</span></span>  
  
    -   <span data-ttu-id="437c5-191">**Intervallo equo**.</span><span class="sxs-lookup"><span data-stu-id="437c5-191">**EqualInterval**.</span></span> <span data-ttu-id="437c5-192">Specifica gli intervalli che dividono i dati in intervalli equi.</span><span class="sxs-lookup"><span data-stu-id="437c5-192">Specifies ranges that divide the data into equal range intervals.</span></span>  
  
    -   <span data-ttu-id="437c5-193">**Distribuzione equa**.</span><span class="sxs-lookup"><span data-stu-id="437c5-193">**EqualDistribution**.</span></span> <span data-ttu-id="437c5-194">Specifica gli intervalli che dividono i dati in modo che ogni intervallo disponga di un numero uguale di elementi.</span><span class="sxs-lookup"><span data-stu-id="437c5-194">Specifies ranges that divide that data so that each range has an equal number of items.</span></span>  
  
    -   <span data-ttu-id="437c5-195">**Ottimale**.</span><span class="sxs-lookup"><span data-stu-id="437c5-195">**Optimal**.</span></span> <span data-ttu-id="437c5-196">Specifica gli intervalli che regolano automaticamente la distribuzione per creare intervalli secondari equilibrati.</span><span class="sxs-lookup"><span data-stu-id="437c5-196">Specifies ranges that automatically adjust distribution to create balanced subranges.</span></span>  
  
    -   <span data-ttu-id="437c5-197">**Personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="437c5-197">**Custom**.</span></span> <span data-ttu-id="437c5-198">Specifica il numero di intervalli per controllare la distribuzione di valori.</span><span class="sxs-lookup"><span data-stu-id="437c5-198">Specify your own number of ranges to control the distribution of values.</span></span>  
  
     <span data-ttu-id="437c5-199">Per altre informazioni sulle opzioni di distribuzione, vedere [Variare la visualizzazione di poligoni, linee e punti in base a regole e dati analitici &#40;Generatore report e SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="437c5-199">For more information about distribution options, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
6.  <span data-ttu-id="437c5-200">In **Numero di intervalli secondari**digitare il numero di intervalli secondari da usare.</span><span class="sxs-lookup"><span data-stu-id="437c5-200">In **Number of subranges**, type the number of subranges to use.</span></span> <span data-ttu-id="437c5-201">Se il tipo di distribuzione è **Ottimale**, il numero di intervalli secondari viene calcolato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="437c5-201">When the distribution type is **Optimal**, the number of subranges is automatically calculated.</span></span>  
  
7.  <span data-ttu-id="437c5-202">In **Inizio intervallo**digitare un valore di intervallo minimo.</span><span class="sxs-lookup"><span data-stu-id="437c5-202">In **Range start**, type a minimum range value.</span></span> <span data-ttu-id="437c5-203">Tutti i valori inferiori a questo numero corrispondono al minimo dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="437c5-203">All values less than this number are the same as the range minimum.</span></span>  
  
8.  <span data-ttu-id="437c5-204">In **Fine intervallo**digitare un valore di intervallo massimo.</span><span class="sxs-lookup"><span data-stu-id="437c5-204">In **Range end**, type a maximum range value.</span></span> <span data-ttu-id="437c5-205">Tutti i valori superiori a questo numero corrispondono al massimo dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="437c5-205">All values larger than this number are the same as the range maximum.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-a-rule-legend"></a><a name="RuleLegend"></a> <span data-ttu-id="437c5-206">Per modificare il contenuto di una legenda di regole</span><span class="sxs-lookup"><span data-stu-id="437c5-206">To change the contents of a rule legend</span></span>  
  
#### <a name="to-change-the-contents-of-a-color-size-width-or-marker-type-legend"></a><span data-ttu-id="437c5-207">Per modificare il contenuto di una legenda di tipo dimensioni, spessore o tipo di marcatore</span><span class="sxs-lookup"><span data-stu-id="437c5-207">To change the contents of a color, size, width, or marker type legend</span></span>  
  
1.  <span data-ttu-id="437c5-208">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-208">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-209">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola**.</span><span class="sxs-lookup"><span data-stu-id="437c5-209">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-210">Verificare che **Visualizza dati** tramite \<*rule type*> sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="437c5-210">Verify that **Visualize data by using** \<*rule type*> is selected.</span></span>  
  
4.  <span data-ttu-id="437c5-211">In **Campo dati**verificare che vengano selezionati i dati analitici visualizzati sul livello.</span><span class="sxs-lookup"><span data-stu-id="437c5-211">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="437c5-212">Se nell'elenco a discesa non viene visualizzato alcun campo, fare clic con il pulsante destro del mouse sul livello, scegliere **Dati livello** per aprire la pagina Dati analitici della finestra di dialogo Proprietà dati livello mappa e verificare che siano stati specificati i dati analitici per questo livello.</span><span class="sxs-lookup"><span data-stu-id="437c5-212">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="437c5-213">Fare clic su **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="437c5-213">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="437c5-214">In **Mostra in questa legenda**selezionare la legenda della mappa da usare per visualizzare i risultati della regola.</span><span class="sxs-lookup"><span data-stu-id="437c5-214">In **Show in this legend**, select the map legend to use to display the rule results.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-the-color-scale"></a><a name="ColorScale"></a> <span data-ttu-id="437c5-215">Per modificare il contenuto della scala dei colori</span><span class="sxs-lookup"><span data-stu-id="437c5-215">To change the contents of the color scale</span></span>  
  
#### <a name="to-change-the-contents-of-the-color-scale-or-a-color-legend"></a><span data-ttu-id="437c5-216">Per modificare il contenuto della legenda della scala dei colori o dei colori</span><span class="sxs-lookup"><span data-stu-id="437c5-216">To change the contents of the color scale or a color legend</span></span>  
  
1.  <span data-ttu-id="437c5-217">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-217">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-218">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola colore**.</span><span class="sxs-lookup"><span data-stu-id="437c5-218">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-219">Selezionare l'opzione della regola colore da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="437c5-219">Select the color rule option to use.</span></span> <span data-ttu-id="437c5-220">Per visualizzare gli elementi in una legenda della mappa o in una scala dei colori, è necessario selezionare una delle opzioni **Visualizza dati** tramite \<rule type> .</span><span class="sxs-lookup"><span data-stu-id="437c5-220">To display items in a map legend or color scale, you must select one of the **Visualize data by using** \<rule type> options.</span></span>  
  
4.  <span data-ttu-id="437c5-221">In **Campo dati**verificare che vengano selezionati i dati analitici visualizzati sul livello.</span><span class="sxs-lookup"><span data-stu-id="437c5-221">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="437c5-222">Se nell'elenco a discesa non viene visualizzato alcun campo, fare clic con il pulsante destro del mouse sul livello, scegliere **Dati livello** per aprire la pagina Dati analitici della finestra di dialogo Proprietà dati livello mappa e verificare che siano stati specificati i dati analitici per questo livello.</span><span class="sxs-lookup"><span data-stu-id="437c5-222">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="437c5-223">Fare clic su **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="437c5-223">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="437c5-224">In **Opzioni scala dei colori**selezionare **Mostra nella scala dei colori** per visualizzare i risultati della regola nella scala dei colori.</span><span class="sxs-lookup"><span data-stu-id="437c5-224">In **Color scale options**, select **Show in color scale** to display the rule results in the color scale.</span></span> <span data-ttu-id="437c5-225">Questa opzione può essere specificata per più di una regola colore.</span><span class="sxs-lookup"><span data-stu-id="437c5-225">You can specify this option for more than one color rule.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-remove-all-items-from-a-legend"></a><a name="HideItems"></a> <span data-ttu-id="437c5-226">Per rimuovere tutti gli elementi da una legenda</span><span class="sxs-lookup"><span data-stu-id="437c5-226">To remove all items from a legend</span></span>  
  
#### <a name="to-hide-items-based-on-a-rule"></a><span data-ttu-id="437c5-227">Per nascondere elementi in base a una regola</span><span class="sxs-lookup"><span data-stu-id="437c5-227">To hide items based on a rule</span></span>  
  
1.  <span data-ttu-id="437c5-228">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-228">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-229">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola**.</span><span class="sxs-lookup"><span data-stu-id="437c5-229">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-230">Fare clic su **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="437c5-230">Click **Legend**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-format-of-content-in-a-legend"></a><a name="ChangeFormatItems"></a> <span data-ttu-id="437c5-231">Per modificare il formato del contenuto in una legenda</span><span class="sxs-lookup"><span data-stu-id="437c5-231">To change the format of content in a legend</span></span>  
 <span data-ttu-id="437c5-232">Impostare le opzioni legenda per la regola associata alla legenda della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-232">Set legend options for the rule that is associated with the map legend.</span></span>  
  
#### <a name="to-change-the-format-of-content-in-a-legend"></a><span data-ttu-id="437c5-233">Per modificare il formato del contenuto in una legenda</span><span class="sxs-lookup"><span data-stu-id="437c5-233">To change the format of content in a legend</span></span>  
  
1.  <span data-ttu-id="437c5-234">In visualizzazione struttura fare clic sulla mappa finché non viene visualizzato il riquadro della mappa.</span><span class="sxs-lookup"><span data-stu-id="437c5-234">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="437c5-235">Fare clic con il pulsante destro del mouse sul livello che dispone dei dati desiderati, quindi scegliere _\<map element type\>_ **regola**.</span><span class="sxs-lookup"><span data-stu-id="437c5-235">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="437c5-236">Fare clic su **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="437c5-236">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="437c5-237">**Testo legenda** visualizza le parole chiave che specificano quali dati compaiono nella legenda.</span><span class="sxs-lookup"><span data-stu-id="437c5-237">**Legend text** displays keywords that specify which data appears in the legend.</span></span> <span data-ttu-id="437c5-238">Utilizzare parole chiave e formati personalizzati per controllare il formato del testo della legenda.</span><span class="sxs-lookup"><span data-stu-id="437c5-238">Use map keywords and custom formats to help control the format of legend text.</span></span> <span data-ttu-id="437c5-239">Ad esempio, #FROMVALUE {C2} specifica un formato valuta con due cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="437c5-239">For example, #FROMVALUE {C2} specifies a currency format with two decimal places.</span></span> <span data-ttu-id="437c5-240">Per altre informazioni, vedere [Variare la visualizzazione di poligoni, linee e punti in base a regole e dati analitici &#40;Generatore report e SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="437c5-240">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="437c5-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="437c5-241">See Also</span></span>  
 <span data-ttu-id="437c5-242">[Mappe &#40;Generatore report e SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="437c5-242">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="437c5-243">[Aggiungere, modificare o eliminare una mappa o un livello mappa &#40;Generatore report e SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="437c5-243">[Add, Change, or Delete a Map or Map Layer &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="437c5-244">[Personalizzare i dati e la visualizzazione di una mappa o di un livello mappa &#40;Generatore report e SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="437c5-244">[Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="437c5-245">[Risoluzione dei problemi relativi alle parti del report: report mappa &#40;Generatore report e SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="437c5-245">[Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="437c5-246">Creazione guidata mappa e Creazione guidata livello mappa &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="437c5-246">Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;</span></span>](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)  
  
  
