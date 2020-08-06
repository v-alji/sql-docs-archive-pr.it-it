---
title: 'Esercitazione: Report mappa (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8d831356-7efa-40cc-ae95-383b3eecf833
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b737bb3fe74eb3524f2944a7458cb4837b1aeedf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722420"
---
# <a name="tutorial-map-report-report-builder"></a><span data-ttu-id="8f197-102">Esercitazione: Report mappa (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="8f197-102">Tutorial: Map Report (Report Builder)</span></span>
  <span data-ttu-id="8f197-103">Questa esercitazione intende fornire un approfondimento delle funzionalità della mappa che è possibile utilizzare per visualizzare i dati del report rispetto a uno sfondo geografico.</span><span class="sxs-lookup"><span data-stu-id="8f197-103">This tutorial is designed to help you learn about the map features you can use to display report data against a geographic background.</span></span>  
  
 <span data-ttu-id="8f197-104">Le mappe sono basate su dati spaziali costituiti in genere da punti, linee e poligoni.</span><span class="sxs-lookup"><span data-stu-id="8f197-104">Maps are based on spatial data that typically consists of points, lines, and polygons.</span></span> <span data-ttu-id="8f197-105">Un poligono può ad esempio rappresentare la struttura di una regione, una riga può rappresentare una strada e un punto può rappresentare la posizione geografica di una città.</span><span class="sxs-lookup"><span data-stu-id="8f197-105">For example, a polygon can represent the outline of a county, a line can represent a road, and a point can represent the location of a city.</span></span> <span data-ttu-id="8f197-106">Ogni tipo di dati spaziali viene visualizzato su un livello mappa separato come un set di elementi mappa.</span><span class="sxs-lookup"><span data-stu-id="8f197-106">Each type of spatial data is displayed on a separate map layer as a set of map elements.</span></span>  
  
 <span data-ttu-id="8f197-107">Per variare l'aspetto degli elementi mappa, è possibile specificare un campo contenente valori corrispondenti agli elementi mappa con dati analitici provenienti da un set di dati.</span><span class="sxs-lookup"><span data-stu-id="8f197-107">To vary the appearance of map elements, you specify a field that has values that match the map elements with analytical data from a dataset.</span></span> <span data-ttu-id="8f197-108">È inoltre possibile definire regole per variare il colore, la dimensione o altre proprietà in base a intervalli di dati.</span><span class="sxs-lookup"><span data-stu-id="8f197-108">You can also define rules that vary color, size, or other properties based on ranges of data.</span></span>  
  
 <span data-ttu-id="8f197-109">In questa esercitazione verrà compilato un report mappa in cui sono visualizzate le posizioni di alcuni negozi nelle regioni dello stato di New York.</span><span class="sxs-lookup"><span data-stu-id="8f197-109">In this tutorial, you will build a map report that displays store locations in New York state counties.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="8f197-110">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="8f197-110">What You Will Learn</span></span>  
 <span data-ttu-id="8f197-111">In questa esercitazione verranno illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f197-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="8f197-112">Creare una mappa con un livello poligono dalla Creazione guidata mappa</span><span class="sxs-lookup"><span data-stu-id="8f197-112">Create a Map with a Polygon Layer from the Map Wizard</span></span>](#Map)  
  
2.  [<span data-ttu-id="8f197-113">Aggiungere un livello punto mappa per visualizzare le posizioni dei negozi</span><span class="sxs-lookup"><span data-stu-id="8f197-113">Add a Map Point Layer to Display Store Locations</span></span>](#PointLayer)  
  
3.  [<span data-ttu-id="8f197-114">Aggiungere un livello linea mappa per visualizzare un itinerario</span><span class="sxs-lookup"><span data-stu-id="8f197-114">Add a Map Line Layer to Display a Route</span></span>](#LineLayer)  
  
4.  [<span data-ttu-id="8f197-115">Aggiungere uno sfondo a tessere mappa di Bing</span><span class="sxs-lookup"><span data-stu-id="8f197-115">Add a Bing Maps Tile Background</span></span>](#TileLayer)  
  
5.  [<span data-ttu-id="8f197-116">Rendere trasparente un livello</span><span class="sxs-lookup"><span data-stu-id="8f197-116">Make a Layer Transparent</span></span>](#Transparent)  
  
6.  [<span data-ttu-id="8f197-117">Variare il colore delle regioni in base alle vendite</span><span class="sxs-lookup"><span data-stu-id="8f197-117">Vary County Color Based on Sales</span></span>](#Vary)  
  
    1.  [<span data-ttu-id="8f197-118">Compilare una relazione tra dati spaziali e dati analitici</span><span class="sxs-lookup"><span data-stu-id="8f197-118">Build a Relationship between Spatial and Analytical Data</span></span>](#Relationship)  
  
    2.  [<span data-ttu-id="8f197-119">Specificare le regole colori per i poligoni</span><span class="sxs-lookup"><span data-stu-id="8f197-119">Specify Color Rules for Polygons</span></span>](#ColorRules)  
  
    3.  [<span data-ttu-id="8f197-120">Formattare i dati nella scala dei colori come valuta</span><span class="sxs-lookup"><span data-stu-id="8f197-120">Format the Data in the Color Scale as Currency</span></span>](#ColorScale)  
  
    4.  [<span data-ttu-id="8f197-121">Creare una nuova legenda</span><span class="sxs-lookup"><span data-stu-id="8f197-121">Create a New Legend</span></span>](#NewLegend)  
  
    5.  [<span data-ttu-id="8f197-122">Associare la legenda e le regole colori</span><span class="sxs-lookup"><span data-stu-id="8f197-122">Associate Legend and Color Rules</span></span>](#Associate)  
  
    6.  [<span data-ttu-id="8f197-123">Cancellare il colore dalle regioni prive di dati</span><span class="sxs-lookup"><span data-stu-id="8f197-123">Clear Color from Counties with No Data</span></span>](#NoData)  
  
7.  [<span data-ttu-id="8f197-124">Aggiungere un punto personalizzato</span><span class="sxs-lookup"><span data-stu-id="8f197-124">Add a Custom Point</span></span>](#CustomPoint)  
  
8.  [<span data-ttu-id="8f197-125">Allineare al centro la vista mappa</span><span class="sxs-lookup"><span data-stu-id="8f197-125">Center the Map View</span></span>](#CenterView)  
  
9. [<span data-ttu-id="8f197-126">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="8f197-126">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="8f197-127">Salva il report</span><span class="sxs-lookup"><span data-stu-id="8f197-127">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="8f197-128">In questa esercitazione, i passaggi della procedura guidata sono consolidati in due procedure: una per la creazione del set di dati e un'altra per la creazione di una tabella.</span><span class="sxs-lookup"><span data-stu-id="8f197-128">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="8f197-129">Per istruzioni dettagliate su come selezionare un server di report, scegliere un'origine dati, creare un set di dati ed eseguire la procedura guidata, vedere la prima esercitazione di questa serie: [Esercitazione: Creazione di un report tabella semplice &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="8f197-129">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="8f197-130">Tempo previsto per il completamento di questa esercitazione: 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="8f197-130">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f197-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f197-131">Requirements</span></span>  
 <span data-ttu-id="8f197-132">Per informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="8f197-132">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-map-with-a-polygon-layer-from-the-map-wizard"></a><a name="Map"></a><span data-ttu-id="8f197-133">1. creare una mappa con un livello poligono dalla creazione guidata mappa</span><span class="sxs-lookup"><span data-stu-id="8f197-133">1. Create a Map with a Polygon Layer from the Map Wizard</span></span>  
 <span data-ttu-id="8f197-134">Aggiungere una mappa al report dalla raccolta mappe.</span><span class="sxs-lookup"><span data-stu-id="8f197-134">Add a map to your report from the map gallery.</span></span> <span data-ttu-id="8f197-135">La mappa dispone di un livello in cui sono visualizzate le regioni dello stato di New York.</span><span class="sxs-lookup"><span data-stu-id="8f197-135">The map has one layer that displays the counties in New York state.</span></span> <span data-ttu-id="8f197-136">La forma di ogni regione è data da un poligono basato su dati spaziali incorporati nella mappa dalla raccolta mappe.</span><span class="sxs-lookup"><span data-stu-id="8f197-136">The shape of each county is a polygon based on spatial data that is embedded in the map from the map gallery.</span></span>  
  
#### <a name="to-add-a-map-with-the-map-wizard-in-a-new-report"></a><span data-ttu-id="8f197-137">Per aggiungere una mappa con l'apposita creazione guidata in un nuovo report</span><span class="sxs-lookup"><span data-stu-id="8f197-137">To add a map with the map wizard in a new report</span></span>  
  
1.  <span data-ttu-id="8f197-138">Fare clic sul pulsante **Start**, scegliere **programmi**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Generatore report**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="8f197-138">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="8f197-139">Verrà visualizzata la finestra di dialogo Riquadro attività iniziale.</span><span class="sxs-lookup"><span data-stu-id="8f197-139">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f197-140">Se la finestra di dialogo Introduzione non viene visualizzata, dal pulsante Generatore report fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8f197-140">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="8f197-141">Nel riquadro sinistro verificare che sia selezionata l'opzione **report** .</span><span class="sxs-lookup"><span data-stu-id="8f197-141">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="8f197-142">Nel riquadro di destra fare clic su **Creazione guidata mappa**.</span><span class="sxs-lookup"><span data-stu-id="8f197-142">In the right pane, click **Map Wizard**.</span></span>  
  
4.  <span data-ttu-id="8f197-143">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="8f197-143">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="8f197-144">**Scegliere un'origine dati spaziali** pagina verificare che sia selezionata l'opzione **raccolta mappe** .</span><span class="sxs-lookup"><span data-stu-id="8f197-144">**Choose a source of spatial data** page, verify that **Map gallery** is selected.</span></span>  
  
6.  <span data-ttu-id="8f197-145">Nel riquadro raccolta mappe espandere **States by County** sotto **USA**, quindi fare clic su **New York**.</span><span class="sxs-lookup"><span data-stu-id="8f197-145">In the Map Gallery pane, expand **States by County** under **USA**, and click **New York**.</span></span>  
  
     <span data-ttu-id="8f197-146">Nel riquadro Anteprima mappe viene visualizzata la mappa della regione di New York.</span><span class="sxs-lookup"><span data-stu-id="8f197-146">The Map Preview pane displays the New York county map.</span></span>  
  
7.  <span data-ttu-id="8f197-147">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-147">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="8f197-148">Nella pagina **Scegli opzioni di dati spaziali e vista mappa** accettare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="8f197-148">On the **Choose spatial data and map view options** page, accept the defaults.</span></span> <span data-ttu-id="8f197-149">Per impostazione predefinita, gli elementi mappa di una raccolta mappe verranno incorporati automaticamente nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-149">By default, map elements from a map gallery will automatically be embedded in the report definition.</span></span>  
  
9. <span data-ttu-id="8f197-150">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-150">Click **Next**.</span></span>  
  
10. <span data-ttu-id="8f197-151">Nella pagina **Scegli vista mappa** verificare che sia selezionata l'opzione **Mappa di base** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-151">On the **Choose map visualization** page, verify **Basic Map** is selected, and click **Next**.</span></span>  
  
11. <span data-ttu-id="8f197-152">Nella pagina **Scegliere combinazione di colori e visualizzazione dati** selezionare l'opzione **Visualizza etichette** .</span><span class="sxs-lookup"><span data-stu-id="8f197-152">On the **Choose color theme and data visualization** page, select the **Display labels** option.</span></span>  
  
12. <span data-ttu-id="8f197-153">Se è selezionata, deselezionare l'opzione **Mappa a colore singolo** .</span><span class="sxs-lookup"><span data-stu-id="8f197-153">If it is selected, clear the **Single color map** option.</span></span>  
  
13. <span data-ttu-id="8f197-154">Nell'elenco a discesa **campo dati** fare clic su #COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="8f197-154">From the **Data field** drop-down list, click #COUNTYNAME.</span></span> <span data-ttu-id="8f197-155">Nel riquadro Anteprima mappe della procedura guidata vengono visualizzati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f197-155">The Map Preview pane in the wizard displays the following items:</span></span>  
  
    -   <span data-ttu-id="8f197-156">Un titolo con il testo **Titolo mappa**.</span><span class="sxs-lookup"><span data-stu-id="8f197-156">A title with the text **Map Title**.</span></span>  
  
    -   <span data-ttu-id="8f197-157">Una mappa in cui sono visualizzate le regioni di New York, ognuna con un colore diverso, con il relativo nome visualizzato nella posizione più adatta sull'area della regione.</span><span class="sxs-lookup"><span data-stu-id="8f197-157">A map that displays counties in New York where each county is a different color and the county name appears wherever it fits over the county area.</span></span>  
  
    -   <span data-ttu-id="8f197-158">Una legenda che contiene un titolo e un elenco di elementi da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="8f197-158">A legend that contains a title and a list of items 1 through 5.</span></span>  
  
    -   <span data-ttu-id="8f197-159">Una scala dei colori che contiene valori da 0 a 160 e nessun colore.</span><span class="sxs-lookup"><span data-stu-id="8f197-159">A color scale that contains values 0 to 160 and no color.</span></span>  
  
    -   <span data-ttu-id="8f197-160">Una scala distanza in cui sono visualizzati chilometri (km) e miglia (mi).</span><span class="sxs-lookup"><span data-stu-id="8f197-160">A distance scale that displays kilometers (km) and miles (mi).</span></span>  
  
14. <span data-ttu-id="8f197-161">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8f197-161">Click **Finish**.</span></span>  
  
     <span data-ttu-id="8f197-162">La mappa viene aggiunta all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8f197-162">The map is added to the design surface.</span></span>  
  
15. <span data-ttu-id="8f197-163">Fare clic sulla mappa per selezionarla e visualizzare il **riquadro livelli mappa**.</span><span class="sxs-lookup"><span data-stu-id="8f197-163">Click the map to select it and display the **Map Layers Pane**.</span></span> <span data-ttu-id="8f197-164">Il **riquadro livelli mappa** Mostra un livello poligono di tipo **incorporato**.</span><span class="sxs-lookup"><span data-stu-id="8f197-164">The **Map Layers Pane** shows one polygon layer of layer type **Embedded**.</span></span> <span data-ttu-id="8f197-165">Ogni regione è un elemento incorporato della mappa a questo livello.</span><span class="sxs-lookup"><span data-stu-id="8f197-165">Each county is an embedded map element on this layer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f197-166">Se il riquadro **livelli mappa** non è visibile, potrebbe essere visualizzato al di fuori della visualizzazione corrente.</span><span class="sxs-lookup"><span data-stu-id="8f197-166">If you do not see the **Map Layers** pane, it might be displayed outside your current view.</span></span> <span data-ttu-id="8f197-167">Utilizzare la barra di scorrimento nella parte inferiore della visualizzazione della struttura per modificare la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f197-167">Use the scroll bar at the bottom of the Design view window to change your view.</span></span> <span data-ttu-id="8f197-168">In alternativa, nella scheda **Visualizza** deselezionare l'opzione **Proprietà** o **dati report** per fornire una maggiore superficie di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8f197-168">Alternatively, in the **View** tab, clear the **Properties** or the **Report Data** option to provide more design surface area.</span></span>  
  
16. <span data-ttu-id="8f197-169">Fare clic con il pulsante destro del mouse sul titolo della mappa, quindi scegliere **Proprietà titolo**.</span><span class="sxs-lookup"><span data-stu-id="8f197-169">Right-click the map title, and then click **Title Properties**.</span></span>  
  
17. <span data-ttu-id="8f197-170">Sostituire il testo del titolo con **Sales by Store**.</span><span class="sxs-lookup"><span data-stu-id="8f197-170">Replace the title text with **Sales by Store**.</span></span>  
  
18. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
19. <span data-ttu-id="8f197-171">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-171">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-172">Nel report visualizzabile è incluso il titolo della mappa, la mappa e la scala distanza.</span><span class="sxs-lookup"><span data-stu-id="8f197-172">The rendered report displays the map title, the map, and the distance scale.</span></span> <span data-ttu-id="8f197-173">Le regioni si trovano su un livello poligono della mappa.</span><span class="sxs-lookup"><span data-stu-id="8f197-173">The counties are on a map polygon layer.</span></span> <span data-ttu-id="8f197-174">Ogni regione è data da un poligono che varia in base ai colori di una tavolozza, tuttavia i colori non sono associati ad alcun dato.</span><span class="sxs-lookup"><span data-stu-id="8f197-174">Each county is a polygon that varies by color from a color palette, but the colors are not associated with any data.</span></span> <span data-ttu-id="8f197-175">Nella scala distanza sono visualizzate le distanze sia in chilometri sia in miglia.</span><span class="sxs-lookup"><span data-stu-id="8f197-175">The distance scale displays distances in both kilometers and miles.</span></span>  
  
 <span data-ttu-id="8f197-176">La legenda della mappa e la scala dei colori non sono ancora visibili perché alle regioni non sono associati dati analitici.</span><span class="sxs-lookup"><span data-stu-id="8f197-176">The map legend and color scale do not yet appear because there is no analytical data associated with each county.</span></span> <span data-ttu-id="8f197-177">I dati analitici verranno aggiunti in seguito in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="8f197-177">You will add analytical data later in this tutorial.</span></span>  
  
##  <a name="2-add-a-map-point-layer-to-display-store-locations"></a><a name="PointLayer"></a><span data-ttu-id="8f197-178">2. aggiungere un livello punto mappa per visualizzare le posizioni dei negozi</span><span class="sxs-lookup"><span data-stu-id="8f197-178">2. Add a Map Point Layer to Display Store Locations</span></span>  
 <span data-ttu-id="8f197-179">Utilizzare la Creazione guidata livello mappa per aggiungere un livello punto in cui vengono visualizzate le posizioni dei negozi.</span><span class="sxs-lookup"><span data-stu-id="8f197-179">Use the map layer wizard to add a point layer that displays the locations of stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f197-180">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="8f197-180">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="8f197-181">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="8f197-181">This makes the query quite long.</span></span> <span data-ttu-id="8f197-182">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="8f197-182">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="8f197-183">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="8f197-183">This is for learning purposes only.</span></span>  
  
#### <a name="to-add-a-point-layer-based-on-a-sql-server-spatial-query"></a><span data-ttu-id="8f197-184">Per aggiungere un livello punto in base a una query spaziale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f197-184">To add a point layer based on a SQL Server spatial query</span></span>  
  
1.  <span data-ttu-id="8f197-185">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-185">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-186">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-186">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="8f197-187">Sulla barra degli strumenti fare clic sul pulsante **Creazione guidata nuovo livello**![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span><span class="sxs-lookup"><span data-stu-id="8f197-187">On the toolbar, click the **New layer wizard** button ![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span></span>  
  
3.  <span data-ttu-id="8f197-188">Nella pagina **Scegliere un'origine dati spaziali** selezionare **Query spaziale di SQL Server**e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-188">On the **Choose a source of spatial data** page, select **SQL Server spatial query**, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="8f197-189">Nella pagina **scegliere un set di dati con SQL Server dati spaziali** fare clic su **Aggiungi un nuovo set di dati con SQL Server dati spaziali**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-189">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="8f197-190">Nella pagina **Scegliere una connessione a un'origine dati spaziali di SQL Server** selezionare un'origine dati esistente o il server di report, quindi selezionare un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8f197-190">On the **Choose a connection to a SQL Server spatial data source** page, select an existing data source or browse to the report server and select a data source.</span></span>  
  
6.  <span data-ttu-id="8f197-191">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-191">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="8f197-192">Nella pagina Progetta query fare clic su **modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="8f197-192">On the Design a Query page, click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="8f197-193">Incollare il testo seguente nel riquadro della query:</span><span class="sxs-lookup"><span data-stu-id="8f197-193">Paste the following text in the query pane:</span></span>  
  
    ```  
    Select 114 as StoreKey, 'Contoso Albany Store' as StoreName, 1125 as SellingArea, 'Albany' as City, 'Albany' as County,   
     CAST(1000000 as money) as Sales, CAST('POINT(-73.7472924218681 42.6564617079878)' as geography) AS SpatialLocation  
    UNION ALL SELECT 115 AS StoreKey, 'Contoso New York No.1 Store' AS  StoreName, 500 as SellingArea, 'New York' AS City, 'New York City' as County,  
     CAST('2000000' as money) as Sales, CAST('POINT(-73.9922069374483 40.7549638237402)' as geography) AS SpatialLocation  
    UNION ALL Select 116 as StoreKey, 'Contoso Rochester No.1 Store' as StoreName, 462 as SellingArea, 'Rochester' as City,  'Monroe' as County,    
     CAST(3000000 as money) as Sales, CAST('POINT(-77.624041566786 43.1547066024338)' as geography)  AS SpatialLocation  
    UNION ALL Select 117 as StoreKey, 'Contoso New York No.2 Store' as StoreName, 700 as SellingArea, 'New York' as City,'New York City' as County,    
      CAST(4000000 as money) as Sales, CAST('POINT(-73.9712488 40.7830603)' as geography) AS SpatialLocation  
    UNION ALL Select 118 as StoreKey, 'Contoso Syracuse Store' as StoreName, 680 as SellingArea, 'Syracuse' as City, 'Onondaga' as County,  
     CAST(5000000 as money) as Sales, CAST('POINT(-76.1349120532546 43.0610223535974)' as geography) AS SpatialLocation  
    UNION ALL Select 120 as StoreKey, 'Contoso Plattsburgh Store' as StoreName, 560 as SellingArea, 'Plattsburgh' as City,  'Clinton' as County,  
     CAST(6000000 as money) as Sales, CAST('POINT(-73.4728622833178 44.7028831413324)' as geography) AS SpatialLocation  
    UNION ALL Select 121 as StoreKey, 'Contoso Brooklyn Store' as StoreName, 1125 as SellingArea, 'Brooklyn' as City, 'New York City' as County,  
     CAST(7000000 as money) as Sales, CAST('POINT (-73.9638533447143 40.6785123489351)' as geography) AS SpatialLocation  
    UNION ALL Select 122 as StoreKey, 'Contoso Oswego Store' as StoreName, 500 as SellingArea, 'Oswego' as City, 'Oswego' as County,    
     CAST(8000000 as money) as Sales, CAST('POINT(-76.4602850815536 43.4353224527794)' as geography) AS SpatialLocation  
    UNION ALL Select 123 as StoreKey, 'Contoso Ithaca Store' as StoreName, 460 as SellingArea, 'Ithaca' as City, 'Tompkins' as County,  
     CAST(9000000 as money) as Sales, CAST('POINT(-76.5001866085881 42.4310489934743)' as geography) AS SpatialLocation  
    UNION ALL Select 124 as StoreKey, 'Contoso Rochester No.2 Store' as StoreName, 700 as SellingArea, 'Rochester' as City, 'Monroe' as County,    
     CAST(100000 as money) as Sales, CAST('POINT(-77.6240415667866 43.1547066024338)' as geography) AS SpatialLocation  
    UNION ALL Select 125 as StoreKey, 'Contoso Queens Store' as StoreName, 700 as SellingArea,'Queens' as City, 'New York City' as County,  
     CAST(500000 as money) as Sales, CAST('POINT(-73.7930979029883 40.7152781765927)' as geography) AS SpatialLocation  
    UNION ALL Select 126 as StoreKey, 'Contoso Elmira Store' as StoreName, 680 as SellingArea, 'Elmira' as City, 'Chemung' as County,  
     CAST(800000 as money) as Sales, CAST('POINT(-76.7397414783301 42.0736492742663)' as geography) AS SpatialLocation  
    UNION ALL Select 127 as StoreKey, 'Contoso Poestenkill Store' as StoreName, 455 as SellingArea, 'Poestenkill' as City, 'Rensselaer' as County,    
    CAST(1500000 as money) as Sales, CAST('POINT(-73.5626737425063 42.6940551238618)' as geography) AS SpatialLocation  
    ```  
  
9. <span data-ttu-id="8f197-194">Sulla barra degli strumenti Progettazione query fare clic su **Esegui** (**!**).</span><span class="sxs-lookup"><span data-stu-id="8f197-194">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="8f197-195">Il set di risultati comprende sette colonne: StoreKey, StoreName, SellingArea, City, County, Sales e SpatialLocation.</span><span class="sxs-lookup"><span data-stu-id="8f197-195">The result set displays seven columns: StoreKey, StoreName, SellingArea, City, County, Sales, and SpatialLocation.</span></span> <span data-ttu-id="8f197-196">Questi dati rappresentano un set di punti vendita nello Stato di New York che vendono beni di consumo.</span><span class="sxs-lookup"><span data-stu-id="8f197-196">This data represents a set of stores in New York State that sell consumer goods.</span></span> <span data-ttu-id="8f197-197">Ogni riga del set di risultati contiene un identificatore del negozio, il nome del negozio, l'area disponibile per l'esposizione dei prodotti, la città e la regione in cui si trova il negozio, il totale vendite e la posizione indicata con longitudine e latitudine.</span><span class="sxs-lookup"><span data-stu-id="8f197-197">Each row in the result set contains a store identifier, store name, the area available for product display, the city and county where the store is located, the sales total, and the spatial location in longitude and latitude.</span></span> <span data-ttu-id="8f197-198">L'area di visualizzazione varia da 455 piedi quadrati a 1125 piedi quadrati.</span><span class="sxs-lookup"><span data-stu-id="8f197-198">The display area ranges from 455 square feet to 1125 square feet.</span></span>  
  
10. <span data-ttu-id="8f197-199">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-199">Click **Next**.</span></span>  
  
     <span data-ttu-id="8f197-200">Il set di dati del report denominato DataSet1 viene creato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8f197-200">The report dataset named DataSet1 is created for you.</span></span> <span data-ttu-id="8f197-201">Al termine della procedura guidata, è possibile utilizzare Dati report per visualizzare la relativa raccolta campi.</span><span class="sxs-lookup"><span data-stu-id="8f197-201">After you complete the wizard, you can use the Report Data to its field collection.</span></span>  
  
11. <span data-ttu-id="8f197-202">Nella pagina **Scegli opzioni di dati spaziali e vista mappa** verificare che il **campo spaziale** sia `SpatialLocation` e che il tipo di **livello** sia **punto**.</span><span class="sxs-lookup"><span data-stu-id="8f197-202">On the **Choose a spatial data and map view options** page, verify that the **Spatial field** is `SpatialLocation` and that the **Layer type** is **Point**.</span></span> <span data-ttu-id="8f197-203">Accettare le altre impostazioni predefinite di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="8f197-203">Accept the other defaults on this page.</span></span>  
  
     <span data-ttu-id="8f197-204">Nella vista mappa vengono visualizzati cerchi che indicano la posizione di ogni negozio.</span><span class="sxs-lookup"><span data-stu-id="8f197-204">The map view displays circles that mark the location of each store.</span></span>  
  
12. <span data-ttu-id="8f197-205">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-205">Click **Next**.</span></span>  
  
13. <span data-ttu-id="8f197-206">Specificare un tipo di mappa in cui vengono visualizzati marcatori che variano in base ai dati analitici.</span><span class="sxs-lookup"><span data-stu-id="8f197-206">Specify a map type that displays markers that vary by analytic data.</span></span> <span data-ttu-id="8f197-207">Nella pagina Scegli vista mappa fare clic su **mappa marcatore analitico**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-207">On the Choose map visualization page, click **Analytical Marker Map**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="8f197-208">Nella pagina **scegliere il set di dati analitici** fare clic su DataSet1.</span><span class="sxs-lookup"><span data-stu-id="8f197-208">On the **Choose the analytical dataset** page, click DataSet1.</span></span> <span data-ttu-id="8f197-209">Questo set di dati contiene sia dati analitici sia dati spaziali che verranno visualizzati al nuovo livello punto.</span><span class="sxs-lookup"><span data-stu-id="8f197-209">This dataset contains both analytical data and spatial data that will be displayed on the new point layer.</span></span>  
  
15. <span data-ttu-id="8f197-210">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-210">Click **Next**.</span></span>  
  
16. <span data-ttu-id="8f197-211">Nella pagina **Scegli tema colori e visualizzazione dati** deselezionare l'opzione **Usa colori marcatore per visualizzare i dati** , quindi selezionare l'opzione **Usa i tipi di marcatore per visualizzare i dati**.</span><span class="sxs-lookup"><span data-stu-id="8f197-211">On the **Choose color theme and data visualization** page, clear the **Use marker colors to visualize data** option, and then select the option **Use marker types to visualize data**.</span></span>  
  
17. <span data-ttu-id="8f197-212">In **campo dati**selezionare `[Sum(SellingArea)]` questa impostazione per variare i tipi di marcatore in base alle dimensioni dell'area a cui si riserva un negozio per visualizzare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="8f197-212">In **Data field**, select `[Sum(SellingArea)]` to vary marker types by the size of the area a store sets aside to display the products.</span></span>  
  
18. <span data-ttu-id="8f197-213">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8f197-213">Click **Finish**.</span></span>  
  
     <span data-ttu-id="8f197-214">Il livello mappa viene aggiunto al report.</span><span class="sxs-lookup"><span data-stu-id="8f197-214">The map layer is added to the report.</span></span> <span data-ttu-id="8f197-215">Nella legenda vengono visualizzati i tipi di marcatore in base ai valori indicati in SellingArea.</span><span class="sxs-lookup"><span data-stu-id="8f197-215">The legend displays marker types based on SellingArea values.</span></span>  
  
     <span data-ttu-id="8f197-216">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-216">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="8f197-217">Nel riquadro **Livello mappa** viene visualizzato un nuovo livello, PointLayer1, con il tipo di origine dati spaziali **DataRegion**.</span><span class="sxs-lookup"><span data-stu-id="8f197-217">The **Map Layer** pane displays a new layer, PointLayer1, with spatial data source type **DataRegion**.</span></span>  
  
19. <span data-ttu-id="8f197-218">Aggiungere un titolo della legenda.</span><span class="sxs-lookup"><span data-stu-id="8f197-218">Add a legend title.</span></span> <span data-ttu-id="8f197-219">Fare clic con il pulsante destro del mouse sul titolo della legenda, quindi scegliere **Proprietà titolo legenda**.</span><span class="sxs-lookup"><span data-stu-id="8f197-219">Right-click the legend title, and then click **Legend Title Properties**.</span></span>  
  
20. <span data-ttu-id="8f197-220">Eliminare il titolo e digitare **area di visualizzazione (piedi quadrati)**.</span><span class="sxs-lookup"><span data-stu-id="8f197-220">Delete the title, and type **Display Area (Square Feet)**.</span></span>  
  
21. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
22. <span data-ttu-id="8f197-221">Visualizzare i valori predefiniti impostati dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8f197-221">View the default values that were set by the wizard.</span></span> <span data-ttu-id="8f197-222">Nel **riquadro livelli mappa**fare clic con il pulsante destro del mouse sul livello punto, quindi scegliere **regola tipo marcatore**.</span><span class="sxs-lookup"><span data-stu-id="8f197-222">In the **Map Layers Pane**, right-click the point layer, and then click **Marker Type Rule**.</span></span>  
  
     <span data-ttu-id="8f197-223">Nella scheda **generale** i marcatori vengono elencati nell'ordine in cui sono visualizzati nella legenda.</span><span class="sxs-lookup"><span data-stu-id="8f197-223">On the **General** tab, the markers are listed in the order in which they appear in the legend.</span></span> <span data-ttu-id="8f197-224">Nella scheda **distribuzione** il numero di intervalli secondari è 5.</span><span class="sxs-lookup"><span data-stu-id="8f197-224">On the **Distribution** tab, the number of subranges is 5.</span></span> <span data-ttu-id="8f197-225">Nella scheda **Legenda** il testo della legenda è impostato in modo da visualizzare il valore iniziale e finale in ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="8f197-225">On the **Legend** tab, the legend text is set to display the start and end value in each range.</span></span>  
  
23. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
24. <span data-ttu-id="8f197-226">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-226">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-227">Sulla mappa vengono visualizzate le posizioni dei negozi nello Stato di New York.</span><span class="sxs-lookup"><span data-stu-id="8f197-227">The map displays the locations of stores in New York state.</span></span> <span data-ttu-id="8f197-228">Il tipo di marcatore per ogni negozio è basato sull'area di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f197-228">The marker type for each store is based on the display area.</span></span> <span data-ttu-id="8f197-229">Cinque intervalli dell'area di visualizzazione sono stati calcolati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8f197-229">Five ranges of display area were automatically calculated for you.</span></span>  
  
##  <a name="3-add-a-map-line-layer-to-display-a-route"></a><a name="LineLayer"></a><span data-ttu-id="8f197-230">3. aggiungere un livello linea mappa per visualizzare una route</span><span class="sxs-lookup"><span data-stu-id="8f197-230">3. Add a Map Line Layer to Display a Route</span></span>  
 <span data-ttu-id="8f197-231">Utilizzare la Creazione guidata livello mappa per aggiungere un livello mappa in cui venga visualizzata un itinerario tra due negozi.</span><span class="sxs-lookup"><span data-stu-id="8f197-231">Use the map layer wizard to add a map layer that displays a route between two stores.</span></span> <span data-ttu-id="8f197-232">In questa esercitazione il percorso viene creato da tre posizioni di negozi.</span><span class="sxs-lookup"><span data-stu-id="8f197-232">In this tutorial, the path is created from three store locations.</span></span> <span data-ttu-id="8f197-233">In un'applicazione aziendale il percorso potrebbe essere l'itinerario migliore tra negozi.</span><span class="sxs-lookup"><span data-stu-id="8f197-233">In a business application, the path might be the best route between stores.</span></span>  
  
#### <a name="to-add-a-line-layer-to-map"></a><span data-ttu-id="8f197-234">Per aggiungere un livello linea a una mappa</span><span class="sxs-lookup"><span data-stu-id="8f197-234">To add a line layer to map</span></span>  
  
1.  <span data-ttu-id="8f197-235">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-235">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-236">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-236">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="8f197-237">Sulla barra degli strumenti fare clic su **creazione guidata nuovo livello**.</span><span class="sxs-lookup"><span data-stu-id="8f197-237">On the toolbar, click **New layer wizard**.</span></span>  
  
3.  <span data-ttu-id="8f197-238">Nella pagina **scegliere un'origine dati spaziali** selezionare **SQL Server query spaziale** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-238">On the **Choose a source of spatial data** page, select **SQL Server spatial query** and click **Next**.</span></span>  
  
4.  <span data-ttu-id="8f197-239">Nella pagina **Scegliere un set di dati con dati spaziali di SQL Server** fare clic su **Aggiungere un nuovo set di dati con dati spaziali di SQL Server** , quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-239">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data** and click **Next**.</span></span>  
  
5.  <span data-ttu-id="8f197-240">In **scegliere una connessione a un'origine dati spaziali di SQL Server**selezionare DataSource1, l'origine dati creata nella prima procedura.</span><span class="sxs-lookup"><span data-stu-id="8f197-240">On the **Choose a connection to a SQL Server spatial data source**, select DataSource1, the data source that you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="8f197-241">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-241">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="8f197-242">Nella pagina **Progetta query** fare clic su **modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="8f197-242">On the **Design a Query** page, click **Edit as Text**.</span></span> <span data-ttu-id="8f197-243">Progettazione query passa alla modalità basata su testo.</span><span class="sxs-lookup"><span data-stu-id="8f197-243">The query designer switches to text-based mode.</span></span>  
  
8.  <span data-ttu-id="8f197-244">Incollare il testo seguente nel riquadro della query:</span><span class="sxs-lookup"><span data-stu-id="8f197-244">Paste the following text in the query pane:</span></span>  
  
    ```  
    SELECT N'Path' AS Name, CAST('LINESTRING(  
       -76.5001866085881 42.4310489934743,  
       -76.4602850815536 43.4353224527794,  
       -73.4728622833178 44.7028831413324)' AS geography) as Route  
    ```  
  
9. <span data-ttu-id="8f197-245">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-245">Click **Next**.</span></span>  
  
     <span data-ttu-id="8f197-246">Sulla mappa viene visualizzato un percorso tra tre negozi.</span><span class="sxs-lookup"><span data-stu-id="8f197-246">A path appears on the map that connects three stores.</span></span>  
  
10. <span data-ttu-id="8f197-247">Nella pagina **Scegli opzioni di dati spaziali e vista mappa** verificare che **Campo spaziale** sia impostato su **Route** e che **Tipo livello** sia impostato su **Linea**.</span><span class="sxs-lookup"><span data-stu-id="8f197-247">On the **Choose spatial data and map view options** page, verify that the **Spatial field** is **Route** and that the **Layer type** is **Line**.</span></span> <span data-ttu-id="8f197-248">Accettare le altre impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="8f197-248">Accept the other defaults.</span></span>  
  
     <span data-ttu-id="8f197-249">Nella vista mappa viene visualizzato un percorso da un negozio nella parte nord dello stato di New York a un negozio nella parte sud dello stesso stato.</span><span class="sxs-lookup"><span data-stu-id="8f197-249">The map view displays a path from a store in the northern part of New York state to a store in the southern part of New York state.</span></span>  
  
11. <span data-ttu-id="8f197-250">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-250">Click **Next**.</span></span>  
  
12. <span data-ttu-id="8f197-251">Nella pagina **Scegli vista mappa** fare clic su **Mappa linea di base**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8f197-251">On the **Choose map visualization** page, click **Basic Line Map**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="8f197-252">In **Scegliere combinazioni di colori e visualizzazione dati**selezionare l'opzione **Mappa a colore singolo**.</span><span class="sxs-lookup"><span data-stu-id="8f197-252">On the **Choose color theme and data visualization**, select the option **Single color map**.</span></span> <span data-ttu-id="8f197-253">Il percorso viene visualizzato in un determinato colore che dipende dal tema selezionato.</span><span class="sxs-lookup"><span data-stu-id="8f197-253">The path appears as a single color based on the selected theme.</span></span>  
  
14. <span data-ttu-id="8f197-254">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8f197-254">Click **Finish**.</span></span>  
  
 <span data-ttu-id="8f197-255">Nella mappa viene visualizzato un nuovo livello linea con il tipo di origine dati spaziali **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="8f197-255">The map displays a new line layer with spatial data source type **DataSet**.</span></span> <span data-ttu-id="8f197-256">In questo esempio i dati spaziali provengono da un set di dati, tuttavia nessun dato analitico è associato alla riga.</span><span class="sxs-lookup"><span data-stu-id="8f197-256">In this example, the spatial data comes from a dataset but no analytical data is associated with the line.</span></span>  
  
##  <a name="4-add-a-bing-maps-tile-background"></a><a name="TileLayer"></a><span data-ttu-id="8f197-257">4. aggiungere uno sfondo a tessere mappa di Bing</span><span class="sxs-lookup"><span data-stu-id="8f197-257">4. Add a Bing Maps Tile Background</span></span>  
 <span data-ttu-id="8f197-258">Aggiungere un livello mappa in cui sia visualizzato uno sfondo a tessere mappa di Bing.</span><span class="sxs-lookup"><span data-stu-id="8f197-258">Add a map layer that displays a Bing Maps tile background.</span></span>  
  
#### <a name="to-add-a-virtual-earth-tile-background"></a><span data-ttu-id="8f197-259">Per aggiungere uno sfondo a sezioni Virtual Earth</span><span class="sxs-lookup"><span data-stu-id="8f197-259">To add a Virtual Earth tile background</span></span>  
  
1.  <span data-ttu-id="8f197-260">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-260">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-261">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-261">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="8f197-262">Sulla barra degli strumenti fare clic su **Aggiungi livello**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span><span class="sxs-lookup"><span data-stu-id="8f197-262">On the toolbar, click **Add Layer**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span></span>  
  
3.  <span data-ttu-id="8f197-263">Nell'elenco a discesa fare clic su **Livello sezione**.</span><span class="sxs-lookup"><span data-stu-id="8f197-263">From the drop-down list, click **Tile Layer**.</span></span>  
  
     <span data-ttu-id="8f197-264">L'ultimo livello nel riquadro **Livello mappa** è TileLayer1.</span><span class="sxs-lookup"><span data-stu-id="8f197-264">The last layer in the **Map Layer** pane is TileLayer1.</span></span> <span data-ttu-id="8f197-265">Per impostazione predefinita, il livello sezione visualizza lo stile della mappa stradale.</span><span class="sxs-lookup"><span data-stu-id="8f197-265">By default, the tile layer displays the road map style.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f197-266">Nella procedura guidata è anche possibile aggiungere un livello sezione nella pagina **Scegli opzioni di dati spaziali e vista mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-266">In the wizard, you can also add a tile layer on the **Choose spatial data and map view options** page.</span></span> <span data-ttu-id="8f197-267">A tale scopo, selezionare **Aggiungi sfondo Bing Maps per la vista mappa**.</span><span class="sxs-lookup"><span data-stu-id="8f197-267">To do this, select **Add a Bing Maps background for this map view**.</span></span> <span data-ttu-id="8f197-268">In un report visualizzabile, lo sfondo a sezioni visualizza le tessere mappa di Bing per l'attuale livello di allineamento al centro e zoom del viewport mappa.</span><span class="sxs-lookup"><span data-stu-id="8f197-268">In a rendered report, the tile background displays Bing Maps tiles for the current map viewport center and zoom level.</span></span>  
  
4.  <span data-ttu-id="8f197-269">Fare clic sulla freccia in giù in TileLayer1, quindi fare clic su **Proprietà riquadro**.</span><span class="sxs-lookup"><span data-stu-id="8f197-269">Click the down arrow on TileLayer1, and then click **Tile Properties**.</span></span>  
  
5.  <span data-ttu-id="8f197-270">In **tipo**selezionare **aereo**.</span><span class="sxs-lookup"><span data-stu-id="8f197-270">In **Type**, select **Aerial**.</span></span> <span data-ttu-id="8f197-271">La vista aerea non contiene testo.</span><span class="sxs-lookup"><span data-stu-id="8f197-271">The aerial view does not contain text.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="5-make-a-layer-transparent"></a><a name="Transparent"></a><span data-ttu-id="8f197-272">5. rendere trasparente un livello</span><span class="sxs-lookup"><span data-stu-id="8f197-272">5. Make a Layer Transparent</span></span>  
 <span data-ttu-id="8f197-273">Per rendere visibili gli elementi su un livello attraverso un altro, è possibile regolare l'ordine dei livelli e la trasparenza di ogni livello fino a ottenere l'effetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="8f197-273">To let the items on one layer show through another layer, you can adjust the order of layers and the transparency of each layer to get the effect that you want.</span></span>  
  
#### <a name="to-set-the-transparency-of-a-layer"></a><span data-ttu-id="8f197-274">Per impostare la trasparenza di un livello</span><span class="sxs-lookup"><span data-stu-id="8f197-274">To set the transparency of a layer</span></span>  
  
1.  <span data-ttu-id="8f197-275">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-275">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-276">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-276">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="8f197-277">Fare clic sulla freccia in giù in PolygonLayer1, quindi su **dati livello**.</span><span class="sxs-lookup"><span data-stu-id="8f197-277">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="8f197-278">Viene visualizzata la finestra di dialogo **Proprietà livello poligono mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-278">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="8f197-279">Fare clic su **Visibilità**.</span><span class="sxs-lookup"><span data-stu-id="8f197-279">Click **Visibility**.</span></span>  
  
5.  <span data-ttu-id="8f197-280">In **trasparenza (%)** Digitare **30**.</span><span class="sxs-lookup"><span data-stu-id="8f197-280">In **Transparency (%)**, type **30**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="8f197-281">L'area di progettazione visualizza le regioni in modo semitrasparente.</span><span class="sxs-lookup"><span data-stu-id="8f197-281">The design surface displays the counties as semi-transparent.</span></span>  
  
##  <a name="6-vary-county-color-based-on-sales"></a><a name="Vary"></a><span data-ttu-id="8f197-282">6. variare il colore della regione in base alle vendite</span><span class="sxs-lookup"><span data-stu-id="8f197-282">6. Vary County Color Based on Sales</span></span>  
 <span data-ttu-id="8f197-283">Ogni regione del livello poligono dispone di un colore diverso perché l'elaboratore di report assegna automaticamente un valore di colore dall'apposita tavolozza in base al tema scelto nell'ultima pagina della creazione guidata mappa.</span><span class="sxs-lookup"><span data-stu-id="8f197-283">Each county on the polygon layer has a different color because the report processor automatically assigns a color value from the color palette based on the theme that you chose on the last page of the map wizard.</span></span>  
  
 <span data-ttu-id="8f197-284">Nei passaggi seguenti specificare una regola colore per associare colori specifici a un intervallo di vendite di negozi per ogni regione.</span><span class="sxs-lookup"><span data-stu-id="8f197-284">In the following steps, specify a color rule to associate specific colors with a range of store sales for each county.</span></span> <span data-ttu-id="8f197-285">I colori rosso-giallo-verde indicano vendite elevate-medie-basse.</span><span class="sxs-lookup"><span data-stu-id="8f197-285">The colors red-yellow-green indicate relative high-middle-low sales.</span></span> <span data-ttu-id="8f197-286">Formattare la scala dei colori per mostrare la valuta.</span><span class="sxs-lookup"><span data-stu-id="8f197-286">Format the color scale to show currency.</span></span> <span data-ttu-id="8f197-287">Visualizzare gli intervalli di vendite annuali in una nuova legenda.</span><span class="sxs-lookup"><span data-stu-id="8f197-287">Display the annual sales ranges in a new legend.</span></span> <span data-ttu-id="8f197-288">Per le regioni in cui non sono presenti negozi, non utilizzare alcun colore per mostrare che non ci sono dati associati.</span><span class="sxs-lookup"><span data-stu-id="8f197-288">For counties that do not contain stores, use no color to show that there is no associated data.</span></span>  
  
###  <a name="6a-build-a-relationship-between-spatial-and-analytical-data"></a><a name="Relationship"></a><span data-ttu-id="8f197-289">6a.</span><span class="sxs-lookup"><span data-stu-id="8f197-289">6a.</span></span> <span data-ttu-id="8f197-290">Compilare una relazione tra dati spaziali e dati analitici</span><span class="sxs-lookup"><span data-stu-id="8f197-290">Build a Relationship between Spatial and Analytical Data</span></span>  
 <span data-ttu-id="8f197-291">Per variare le forme delle regioni per colore in base ai dati analitici, è innanzitutto necessario associare i dati analitici a quelli spaziali.</span><span class="sxs-lookup"><span data-stu-id="8f197-291">To vary the county shapes by color based on analytical data, you first must associate the analytical data with the spatial data.</span></span> <span data-ttu-id="8f197-292">In questa esercitazione verrà utilizzato il nome della regione su cui basare la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="8f197-292">In this tutorial, you will use the county name to match on.</span></span>  
  
##### <a name="to-build-a-relationship-between-spatial-data-and-analytical-data"></a><span data-ttu-id="8f197-293">Per compilare una relazione tra i dati spaziali e i dati analitici</span><span class="sxs-lookup"><span data-stu-id="8f197-293">To build a relationship between spatial data and analytical data</span></span>  
  
1.  <span data-ttu-id="8f197-294">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-294">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-295">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-295">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="8f197-296">Fare clic sulla freccia in giù in PolygonLayer1, quindi su **dati livello**.</span><span class="sxs-lookup"><span data-stu-id="8f197-296">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="8f197-297">Viene visualizzata la finestra di dialogo **Proprietà livello poligono mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-297">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="8f197-298">Fare clic su **Dati analitici**.</span><span class="sxs-lookup"><span data-stu-id="8f197-298">Click **Analytical data**.</span></span>  
  
5.  <span data-ttu-id="8f197-299">Nell'elenco a discesa selezionare DataSet1.</span><span class="sxs-lookup"><span data-stu-id="8f197-299">From the drop-down list, select DataSet1.</span></span> <span data-ttu-id="8f197-300">Questo set di dati è stato creato dalla procedura guidata quando è stata specificata la query dei dati spaziali per le regioni.</span><span class="sxs-lookup"><span data-stu-id="8f197-300">This dataset was created by the wizard when you specified the spatial data query for the counties.</span></span>  
  
6.  <span data-ttu-id="8f197-301">In **campi da confrontare**, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8f197-301">In **Fields to match on**, click **Add**.</span></span> <span data-ttu-id="8f197-302">Viene aggiunta una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="8f197-302">A new row is added.</span></span>  
  
7.  <span data-ttu-id="8f197-303">In **from Spatial DataSet**selezionare COUNTYNAME nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8f197-303">In **From spatial dataset**, from the drop-down list, click COUNTYNAME.</span></span>  
  
8.  <span data-ttu-id="8f197-304">In **da set di dati analitici**fare clic su [County] nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8f197-304">In **From analytical dataset**, from the drop-down list, click [County].</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="8f197-305">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-305">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-306">Specificando un campo delle corrispondenze dall'origine dati spaziali e dal set di dati analitico, si consente all'elaboratore di report di raggruppare i dati analitici in base agli elementi della mappa.</span><span class="sxs-lookup"><span data-stu-id="8f197-306">By specifying a match field from the spatial data source and from the analytical dataset, you enable the report processor to group analytical data based on the map elements.</span></span> <span data-ttu-id="8f197-307">Un elemento della mappa associato a dati presenta una corrispondenza corretta per i valori specificati.</span><span class="sxs-lookup"><span data-stu-id="8f197-307">A data-bound map element has a successful match for the values that you specified.</span></span>  
  
 <span data-ttu-id="8f197-308">Ogni regione che contiene un negozio è caratterizzata da un colore basato sulla tavolozza dei colori per lo stile scelto nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8f197-308">Each county that contains a store has a color that is based on the color palette for the style that you chose in the wizard.</span></span>  
  
###  <a name="6b-specify-color-rules-for-polygons"></a><a name="ColorRules"></a><span data-ttu-id="8f197-309">6B.</span><span class="sxs-lookup"><span data-stu-id="8f197-309">6b.</span></span> <span data-ttu-id="8f197-310">Specificare le regole colori per i poligoni</span><span class="sxs-lookup"><span data-stu-id="8f197-310">Specify Color Rules for Polygons</span></span>  
 <span data-ttu-id="8f197-311">Per creare una regola per variare il colore di ogni regione in base alle vendite dei negozi, è necessario specificare i valori di intervallo, il numero di divisioni all'interno dell'intervallo che si desidera visualizzare e i colori da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8f197-311">To create a rule that varies the color of each county based store sales, you must specify the range values, the number of divisions within that range that you want to display, and the colors to use.</span></span>  
  
##### <a name="to-specify-color-rules-for-all-polygons-that-have-associated-data"></a><span data-ttu-id="8f197-312">Per specificare le regole colori per tutti i poligoni a cui sono associati dati</span><span class="sxs-lookup"><span data-stu-id="8f197-312">To specify color rules for all polygons that have associated data</span></span>  
  
1.  <span data-ttu-id="8f197-313">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-313">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-314">Fare clic sulla freccia in giù in PolygonLayer1, quindi fare clic su **regola colore poligono**.</span><span class="sxs-lookup"><span data-stu-id="8f197-314">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="8f197-315">Viene visualizzata la finestra di dialogo **Proprietà regole colori mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-315">The **Map Color Rules Properties** dialog box opens.</span></span> <span data-ttu-id="8f197-316">Si noti che l'opzione della regola colore **Visualizza dati tramite tavolozza colori** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="8f197-316">Notice that the color rule option **Visualize data by using color palette** is selected.</span></span> <span data-ttu-id="8f197-317">Questa opzione è stata impostata dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8f197-317">This option was set by the wizard.</span></span>  
  
3.  <span data-ttu-id="8f197-318">Selezionare **Visualizza dati tramite intervalli colori**.</span><span class="sxs-lookup"><span data-stu-id="8f197-318">Select **Visualize data by using color ranges**.</span></span> <span data-ttu-id="8f197-319">L'opzione della tavolozza viene sostituita dalle opzioni colore iniziale, colore intermedio e colore finale.</span><span class="sxs-lookup"><span data-stu-id="8f197-319">The palette option is replaced by start color, middle color, and end color options.</span></span>  
  
4.  <span data-ttu-id="8f197-320">Definire i valori di intervallo per le vendite per regione.</span><span class="sxs-lookup"><span data-stu-id="8f197-320">Define range values for sales per county.</span></span> <span data-ttu-id="8f197-321">In **Campo dati**selezionare `[Sum(Sales)]`nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8f197-321">In **Data field**, from the drop-down list, select `[Sum(Sales)]`.</span></span>  
  
5.  <span data-ttu-id="8f197-322">Per modificare il formato per visualizzare la valuta in migliaia, modificare l'espressione nel modo seguente: `=Sum(Fields!Sales.Value)/1000`</span><span class="sxs-lookup"><span data-stu-id="8f197-322">To change the format to display currency in thousands, change the expression to the following: `=Sum(Fields!Sales.Value)/1000`</span></span>  
  
6.  <span data-ttu-id="8f197-323">Impostare **Colore iniziale** su **Rosso**.</span><span class="sxs-lookup"><span data-stu-id="8f197-323">Change **Start color** to **Red**.</span></span>  
  
7.  <span data-ttu-id="8f197-324">Impostare **Colore finale** su **Verde**.</span><span class="sxs-lookup"><span data-stu-id="8f197-324">Change **End color** to **Green**.</span></span>  
  
     <span data-ttu-id="8f197-325">**Rosso** rappresenta valori di vendite bassi, **Giallo** rappresenta valori di vendite medi e **Verde** rappresenta valori di vendite elevati.</span><span class="sxs-lookup"><span data-stu-id="8f197-325">**Red** represents low sales values, **Yellow** represents middle sales values, and **Green** represents high sales values.</span></span> <span data-ttu-id="8f197-326">L'elaboratore di report calcola un intervallo di colori in base a questi valori e alle opzioni scelte nella pagina **Distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="8f197-326">The report processor calculates a range of colors based on these values and the options that you choose on the **Distribution** page.</span></span>  
  
8.  <span data-ttu-id="8f197-327">Fare clic su **Distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="8f197-327">Click **Distribution**.</span></span>  
  
9. <span data-ttu-id="8f197-328">Verificare che il tipo di distribuzione sia **Ottimale**.</span><span class="sxs-lookup"><span data-stu-id="8f197-328">Verify that the distribution type is **Optimal**.</span></span> <span data-ttu-id="8f197-329">Per l'espressione del passaggio 5, la distribuzione ottimale divide i valori in base a intervalli secondari che bilanciano il numero di elementi e l'estensione di ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="8f197-329">For the expression from step 5, optimal distribution divides the values into subranges that balance the number of items in each range and the span for each range.</span></span>  
  
10. <span data-ttu-id="8f197-330">Accettare i valori predefiniti per le altre opzioni di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="8f197-330">Accept the default values for other options on this page.</span></span> <span data-ttu-id="8f197-331">Quando si seleziona il tipo di distribuzione ottimale, il numero di intervalli secondari viene calcolato durante l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-331">When you select the optimal distribution type, the number of subranges are calculated when the report runs.</span></span>  
  
11. <span data-ttu-id="8f197-332">Fare clic su **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="8f197-332">Click **Legend**.</span></span>  
  
12. <span data-ttu-id="8f197-333">In **Opzioni scala dei colori**verificare che l'opzione **Mostra nella scala dei colori** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8f197-333">In **Color scale options**, verify that **Show in color scale** is selected.</span></span>  
  
13. <span data-ttu-id="8f197-334">In **Mostra in questa legenda**selezionare la riga vuota nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8f197-334">In **Show in this legend**, from the drop-down list, select the blank line.</span></span> <span data-ttu-id="8f197-335">Per il momento, gli intervalli di colore saranno visualizzati solo nella scala dei colori.</span><span class="sxs-lookup"><span data-stu-id="8f197-335">For now, you will show the color ranges only in the color scale.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="8f197-336">La scala dei colori visualizza cinque colori: rosso, arancione, giallo, verde bottiglia chiaro e verde.</span><span class="sxs-lookup"><span data-stu-id="8f197-336">The color scale displays five colors: red, orange, yellow, yellow green, and green.</span></span> <span data-ttu-id="8f197-337">Ogni colore rappresenta un intervallo di vendite che viene calcolato automaticamente in base alle vendite di ogni regione.</span><span class="sxs-lookup"><span data-stu-id="8f197-337">Each color represents a sales range that is automatically calculated based on the sales by county.</span></span>  
  
###  <a name="6c-format-the-data-in-the-color-scale-as-currency"></a><a name="ColorScale"></a><span data-ttu-id="8f197-338">6C.</span><span class="sxs-lookup"><span data-stu-id="8f197-338">6c.</span></span> <span data-ttu-id="8f197-339">Formattare i dati nella scala dei colori come valuta</span><span class="sxs-lookup"><span data-stu-id="8f197-339">Format the Data in the Color Scale as Currency</span></span>  
 <span data-ttu-id="8f197-340">Per impostazione predefinita, i dati presentano un formato generale.</span><span class="sxs-lookup"><span data-stu-id="8f197-340">By default, data has a general format.</span></span> <span data-ttu-id="8f197-341">È possibile applicare formati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8f197-341">You can apply custom formats.</span></span>  
  
##### <a name="to-set-the-format-for-the-color-scale"></a><span data-ttu-id="8f197-342">Per impostare il formato per la scala dei colori</span><span class="sxs-lookup"><span data-stu-id="8f197-342">To set the format for the color scale</span></span>  
  
1.  <span data-ttu-id="8f197-343">Fare clic con il pulsante destro del mouse sulla scala dei colori, quindi scegliere **Proprietà scala dei colori**.</span><span class="sxs-lookup"><span data-stu-id="8f197-343">Right-click the color scale, and then click **Color Scale Properties**.</span></span>  
  
2.  <span data-ttu-id="8f197-344">Fare clic su **numero**.</span><span class="sxs-lookup"><span data-stu-id="8f197-344">Click **Number**.</span></span>  
  
3.  <span data-ttu-id="8f197-345">In **categoria**fare clic su **valuta**.</span><span class="sxs-lookup"><span data-stu-id="8f197-345">In **Category**, click **Currency**.</span></span>  
  
4.  <span data-ttu-id="8f197-346">In **posizioni decimali**Digitare **0**.</span><span class="sxs-lookup"><span data-stu-id="8f197-346">In **Decimal places**, type **0**.</span></span> <span data-ttu-id="8f197-347">Questo formato non specifica alcuna cifra decimale per la valuta.</span><span class="sxs-lookup"><span data-stu-id="8f197-347">This format specifies no decimal places for currency.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8f197-348">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-348">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-349">La scala dei colori visualizza le vendite annuali nel formato della valuta per ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="8f197-349">The color scale displays annual sales in currency format for each range.</span></span>  
  
###  <a name="6d-create-a-new-legend"></a><a name="NewLegend"></a><span data-ttu-id="8f197-350">6D.</span><span class="sxs-lookup"><span data-stu-id="8f197-350">6d.</span></span> <span data-ttu-id="8f197-351">Creare una nuova legenda</span><span class="sxs-lookup"><span data-stu-id="8f197-351">Create a New Legend</span></span>  
 <span data-ttu-id="8f197-352">Per impostazione predefinita, tutte le regole vengono visualizzate nella prima legenda.</span><span class="sxs-lookup"><span data-stu-id="8f197-352">By default, all rules display in the first legend.</span></span> <span data-ttu-id="8f197-353">Per migliorare la visualizzazione per una mappa, è possibile aggiungere legende.</span><span class="sxs-lookup"><span data-stu-id="8f197-353">To improve the display for a map, you can add legends.</span></span>  
  
 <span data-ttu-id="8f197-354">Per modificare la visualizzazione predefinita, è possibile eseguire due passaggi: creare una nuova legenda e quindi associare i risultati della regola per un livello mappa alla nuova legenda.</span><span class="sxs-lookup"><span data-stu-id="8f197-354">To change the default display, there are two steps: create a new legend and then associate the rule results for a map layer with the new legend.</span></span>  
  
##### <a name="to-create-a-new-legend"></a><span data-ttu-id="8f197-355">Per creare una nuova legenda</span><span class="sxs-lookup"><span data-stu-id="8f197-355">To create a new legend</span></span>  
  
1.  <span data-ttu-id="8f197-356">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-356">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-357">Fare clic con il pulsante destro del mouse sulla mappa all'esterno del viewport, quindi scegliere **Aggiungi legenda**.</span><span class="sxs-lookup"><span data-stu-id="8f197-357">Right-click the map outside the viewport, and then click **Add Legend**.</span></span> <span data-ttu-id="8f197-358">Una nuova legenda viene aggiunta alla mappa in una posizione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8f197-358">A new legend is added to the map at a default location.</span></span>  
  
3.  <span data-ttu-id="8f197-359">Fare clic con il pulsante destro del mouse sulla legenda, quindi scegliere **Proprietà legenda**.</span><span class="sxs-lookup"><span data-stu-id="8f197-359">Right-click the legend, and then click **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="8f197-360">In **Opzioni posizione**fare clic sulla posizione che specifica il punto in cui si desidera visualizzare la legenda rispetto al viewport.</span><span class="sxs-lookup"><span data-stu-id="8f197-360">In **Position options**, click the location that specifies where you want the legend to appear relative to the viewport.</span></span> <span data-ttu-id="8f197-361">La mappa sull'area di progettazione cambia al fine di mostrare l'effetto delle selezioni.</span><span class="sxs-lookup"><span data-stu-id="8f197-361">The map on the design surface changes to show the effect of your selections.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8f197-362">Fare clic su **titolo** sulla legenda per selezionare il titolo della legenda.</span><span class="sxs-lookup"><span data-stu-id="8f197-362">Click **Title** on the legend to select the legend title.</span></span>  
  
7.  <span data-ttu-id="8f197-363">Fare nuovamente clic su **titolo** per attivare la modalità di inserimento per il testo.</span><span class="sxs-lookup"><span data-stu-id="8f197-363">Click **Title** again to enter insert mode for the text.</span></span> <span data-ttu-id="8f197-364">Sostituire **title** by **Sales (migliaia)**, quindi fare clic all'esterno del testo.</span><span class="sxs-lookup"><span data-stu-id="8f197-364">Replace **Title** by **Sales (Thousands)**, and then click outside the text.</span></span>  
  
 <span data-ttu-id="8f197-365">La legenda si espande per visualizzare il titolo.</span><span class="sxs-lookup"><span data-stu-id="8f197-365">The legend expands to display the title.</span></span>  
  
###  <a name="6e-associate-legend-and-color-rules"></a><a name="Associate"></a><span data-ttu-id="8f197-366">6e.</span><span class="sxs-lookup"><span data-stu-id="8f197-366">6e.</span></span> <span data-ttu-id="8f197-367">Associare la legenda e le regole colori</span><span class="sxs-lookup"><span data-stu-id="8f197-367">Associate Legend and Color Rules</span></span>  
 <span data-ttu-id="8f197-368">Ogni legenda può visualizzare uno o più set di risultati della regola.</span><span class="sxs-lookup"><span data-stu-id="8f197-368">Each legend can display one or more sets of rule results.</span></span>  
  
##### <a name="to-associate-a-legend-with-color-rules"></a><span data-ttu-id="8f197-369">Per associare una legenda alle regole colori</span><span class="sxs-lookup"><span data-stu-id="8f197-369">To associate a legend with color rules</span></span>  
  
1.  <span data-ttu-id="8f197-370">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-370">Double-click the map to display the **Map Layer** pane.</span></span>  
  
2.  <span data-ttu-id="8f197-371">Fare clic sulla freccia in giù in PolygonLayer1, quindi fare clic su **regola colore poligono**.</span><span class="sxs-lookup"><span data-stu-id="8f197-371">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="8f197-372">Viene visualizzata la finestra di dialogo **Proprietà regole colori mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-372">The **Map Color Rules Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="8f197-373">Fare clic su **Legenda**.</span><span class="sxs-lookup"><span data-stu-id="8f197-373">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="8f197-374">In **Opzioni scala colori**deselezionare **Mostra nella scala colori**.</span><span class="sxs-lookup"><span data-stu-id="8f197-374">In **Color scale options**, clear **Show in color scale**.</span></span>  
  
5.  <span data-ttu-id="8f197-375">In **Opzioni legenda**selezionare legend2 dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8f197-375">In **Legend options**, from the drop-down list, select Legend2.</span></span> <span data-ttu-id="8f197-376">Viene visualizzata l'opzione del testo della legenda.</span><span class="sxs-lookup"><span data-stu-id="8f197-376">The legend text option appears.</span></span> <span data-ttu-id="8f197-377">Per impostazione predefinita, il testo della legenda viene formattato con una stringa di formato [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] generale.</span><span class="sxs-lookup"><span data-stu-id="8f197-377">By default, legend text is formatted with a general [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] format string.</span></span> <span data-ttu-id="8f197-378">Gli 0 in N0 indicano nessuna cifra decimale.</span><span class="sxs-lookup"><span data-stu-id="8f197-378">The 0 in N0 specifies no decimal digits.</span></span>  
  
6.  <span data-ttu-id="8f197-379">Nel **testo della legenda**usare il formato seguente per specificare la valuta senza cifre decimali:`#FROMVALUE {C0} - #TOVALUE {C0}`</span><span class="sxs-lookup"><span data-stu-id="8f197-379">In **Legend text**, use the following format to specify currency with no decimal digits: `#FROMVALUE {C0} - #TOVALUE {C0}`</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="8f197-380">Sull'area di progettazione la legenda visualizza gli intervalli di colori con dati di esempio formattati come valuta.</span><span class="sxs-lookup"><span data-stu-id="8f197-380">On the design surface, the legend displays the color ranges with sample data formatted as currency.</span></span>  
  
8.  <span data-ttu-id="8f197-381">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-381">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-382">Le regioni a cui sono associati negozi e vendite vengono visualizzate in base alle regole colori.</span><span class="sxs-lookup"><span data-stu-id="8f197-382">The counties that have associated stores and sales display according to the color rules.</span></span> <span data-ttu-id="8f197-383">Le regioni a cui non sono associate vendite non presentano colori.</span><span class="sxs-lookup"><span data-stu-id="8f197-383">Counties that have no sales have no color.</span></span>  
  
###  <a name="6f-change-color-for-counties-with-no-data"></a><a name="NoData"></a><span data-ttu-id="8f197-384">6F.</span><span class="sxs-lookup"><span data-stu-id="8f197-384">6f.</span></span> <span data-ttu-id="8f197-385">Modificare il colore per le regioni prive di dati</span><span class="sxs-lookup"><span data-stu-id="8f197-385">Change Color for Counties with No Data</span></span>  
 <span data-ttu-id="8f197-386">È possibile impostare le opzioni di visualizzazione predefinite per tutti gli elementi della mappa su un livello.</span><span class="sxs-lookup"><span data-stu-id="8f197-386">You can set the default display options for all map elements on a layer.</span></span> <span data-ttu-id="8f197-387">Le regole colori hanno la precedenza su queste opzioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f197-387">Color rules take precedence over these display options.</span></span>  
  
##### <a name="to-set-the-display-properties-for-all-elements-on-a-layer"></a><span data-ttu-id="8f197-388">Per impostare le proprietà di visualizzazione per tutti gli elementi su un livello</span><span class="sxs-lookup"><span data-stu-id="8f197-388">To set the display properties for all elements on a layer</span></span>  
  
1.  <span data-ttu-id="8f197-389">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-389">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-390">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-390">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="8f197-391">Fare clic sulla freccia giù per PolygonLayer1, quindi su **Proprietà poligono**.</span><span class="sxs-lookup"><span data-stu-id="8f197-391">Click the down arrow on PolygonLayer1, and then click **Polygon Properties**.</span></span> <span data-ttu-id="8f197-392">Viene visualizzata la finestra di dialogo **Proprietà poligono mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-392">The **Map Polygon Properties** dialog box opens.</span></span> <span data-ttu-id="8f197-393">Le opzioni di visualizzazione impostate in questa finestra di dialogo sono applicabili a tutti i poligoni del livello prima che vengano applicate le opzioni di visualizzazione basate su regola.</span><span class="sxs-lookup"><span data-stu-id="8f197-393">Display options set in this dialog box apply to all polygons on the layer before rule-based display options are applied.</span></span>  
  
4.  <span data-ttu-id="8f197-394">Fare clic su **Fill**.</span><span class="sxs-lookup"><span data-stu-id="8f197-394">Click **Fill**.</span></span>  
  
5.  <span data-ttu-id="8f197-395">Verificare che lo stile di riempimento sia **solido.**</span><span class="sxs-lookup"><span data-stu-id="8f197-395">Verify that the fill style is **Solid.**</span></span> <span data-ttu-id="8f197-396">Le sfumature e i modelli si applicano a tutti i colori.</span><span class="sxs-lookup"><span data-stu-id="8f197-396">Gradients and patterns apply to all colors.</span></span>  
  
6.  <span data-ttu-id="8f197-397">In **colore**fare clic sulla freccia verso il basso, quindi fare clic su **blu chiaro**.</span><span class="sxs-lookup"><span data-stu-id="8f197-397">In **Color**, click the down arrow, and then click **Light Steel Blue**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="8f197-398">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-398">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-399">Le regioni a cui non sono associati dati vengono visualizzate in blu.</span><span class="sxs-lookup"><span data-stu-id="8f197-399">Counties that have no associated data display as blue.</span></span> <span data-ttu-id="8f197-400">Solo le contee a cui sono associati dati analitici vengono visualizzate in **rosso** tramite colori **verdi** dalle regole colori specificate.</span><span class="sxs-lookup"><span data-stu-id="8f197-400">Only counties that have associated analytical data appear in the **Red** through **Green** colors from the color rules that you specified.</span></span>  
  
##  <a name="7-add-a-custom-point"></a><a name="CustomPoint"></a><span data-ttu-id="8f197-401">7. aggiungere un punto personalizzato</span><span class="sxs-lookup"><span data-stu-id="8f197-401">7. Add a Custom Point</span></span>  
 <span data-ttu-id="8f197-402">Per rappresentare un nuovo negozio che non è ancora stato compilato, specificare un punto e usare il tipo di marcatore **puntina da disegno** .</span><span class="sxs-lookup"><span data-stu-id="8f197-402">To represent a new store that has not yet been built, specify a point and use the **PushPin** marker type.</span></span>  
  
#### <a name="to-add-a-custom-point"></a><span data-ttu-id="8f197-403">Per aggiungere un punto personalizzato</span><span class="sxs-lookup"><span data-stu-id="8f197-403">To add a custom point</span></span>  
  
1.  <span data-ttu-id="8f197-404">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-404">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-405">Fare doppio clic sulla mappa per visualizzare il riquadro **Livello mappa** .</span><span class="sxs-lookup"><span data-stu-id="8f197-405">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="8f197-406">Sulla barra degli strumenti fare clic su **Aggiungi livello**, quindi su **livello punto**.</span><span class="sxs-lookup"><span data-stu-id="8f197-406">On the toolbar, click **Add Layer**, and then click **Point Layer**.</span></span>  
  
     <span data-ttu-id="8f197-407">Un nuovo livello punto viene aggiunto alla mappa.</span><span class="sxs-lookup"><span data-stu-id="8f197-407">A new point layer is added to the map.</span></span> <span data-ttu-id="8f197-408">Per impostazione predefinita, il livello punto usa il tipo di dati spaziali **Incorporato**.</span><span class="sxs-lookup"><span data-stu-id="8f197-408">By default, the point layer has spatial data type **Embedded**.</span></span>  
  
3.  <span data-ttu-id="8f197-409">Fare clic sulla freccia in giù in PointLayer2, quindi fare clic su **Aggiungi punto**.</span><span class="sxs-lookup"><span data-stu-id="8f197-409">Click the down arrow on PointLayer2, and then click **Add Point**.</span></span>  
  
4.  <span data-ttu-id="8f197-410">Spostare il puntatore sul viewport mappa.</span><span class="sxs-lookup"><span data-stu-id="8f197-410">Move the pointer over the map viewport.</span></span> <span data-ttu-id="8f197-411">Il cursore passa alla selezione di precisione.</span><span class="sxs-lookup"><span data-stu-id="8f197-411">The cursor changes to crosshairs.</span></span>  
  
5.  <span data-ttu-id="8f197-412">Fare clic sulla posizione sulla mappa in cui si desidera aggiungere un punto.</span><span class="sxs-lookup"><span data-stu-id="8f197-412">Click the location on the map where you want to add a point.</span></span> <span data-ttu-id="8f197-413">In questa esercitazione fare clic su una posizione in una regione accanto all'inizio dell'itinerario.</span><span class="sxs-lookup"><span data-stu-id="8f197-413">In this tutorial, click a location in a county next to the start of the route.</span></span> <span data-ttu-id="8f197-414">Un punto contrassegnato da un cerchio viene aggiunto al livello nella posizione selezionata.</span><span class="sxs-lookup"><span data-stu-id="8f197-414">A point marked by a circle is added to the layer at the location where you clicked.</span></span> <span data-ttu-id="8f197-415">Per impostazione predefinita, il punto viene selezionato.</span><span class="sxs-lookup"><span data-stu-id="8f197-415">By default, the point is selected.</span></span>  
  
6.  <span data-ttu-id="8f197-416">Fare clic con il pulsante destro del mouse sul punto aggiunto, quindi scegliere **Proprietà punto incorporato**.</span><span class="sxs-lookup"><span data-stu-id="8f197-416">Right-click the point you added, and then click **Embedded Point Properties**.</span></span>  
  
7.  <span data-ttu-id="8f197-417">Selezionare l'opzione **Sostituisci opzioni punto per questo livello**.</span><span class="sxs-lookup"><span data-stu-id="8f197-417">Select the option **Override point options for this layer**.</span></span> <span data-ttu-id="8f197-418">Nella finestra di dialogo vengono visualizzate pagine aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="8f197-418">Additional pages appear in the dialog box.</span></span> <span data-ttu-id="8f197-419">I valori impostati qui hanno la precedenza sulle opzioni di visualizzazione per il livello o per le regole colori.</span><span class="sxs-lookup"><span data-stu-id="8f197-419">Values that you set here take precedence over display options for the layer or for color rules.</span></span>  
  
8.  <span data-ttu-id="8f197-420">Fare clic su **marcatore**.</span><span class="sxs-lookup"><span data-stu-id="8f197-420">Click **Marker**.</span></span>  
  
9. <span data-ttu-id="8f197-421">Per **tipo di marcatore**selezionare **stella**.</span><span class="sxs-lookup"><span data-stu-id="8f197-421">For **Marker type**, select **Star**.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="8f197-422">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-422">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-423">Il nuovo punto aggiunto viene visualizzato come **stella**.</span><span class="sxs-lookup"><span data-stu-id="8f197-423">The new point you added appears as a **Star**.</span></span>  
  
#### <a name="to-add-a-label-for-the-custom-point"></a><span data-ttu-id="8f197-424">Per aggiungere un'etichetta per il punto personalizzato</span><span class="sxs-lookup"><span data-stu-id="8f197-424">To add a label for the custom point</span></span>  
  
1.  <span data-ttu-id="8f197-425">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-425">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-426">Fare clic con il pulsante destro del mouse sul punto appena aggiunto, quindi scegliere **Proprietà punto incorporato**.</span><span class="sxs-lookup"><span data-stu-id="8f197-426">Right-click the point you just added, and then click **Embedded Point Properties**.</span></span>  
  
3.  <span data-ttu-id="8f197-427">Fare clic su **etichette**.</span><span class="sxs-lookup"><span data-stu-id="8f197-427">Click **Labels**.</span></span>  
  
4.  <span data-ttu-id="8f197-428">In **testo etichetta**digitare **nuovo negozio**.</span><span class="sxs-lookup"><span data-stu-id="8f197-428">In **Label text**, type **New Store**.</span></span>  
  
5.  <span data-ttu-id="8f197-429">In **Posizione**fare clic su **Torna all'inizio**.</span><span class="sxs-lookup"><span data-stu-id="8f197-429">In **Placement**, click **Top**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="8f197-430">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-430">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-431">L'etichetta viene visualizzata sopra la posizione del negozio.</span><span class="sxs-lookup"><span data-stu-id="8f197-431">The label appears above the store location.</span></span>  
  
##  <a name="center-the-map-view"></a><a name="CenterView"></a><span data-ttu-id="8f197-432">Centrare la visualizzazione mappa</span><span class="sxs-lookup"><span data-stu-id="8f197-432">Center the Map View</span></span>  
 <span data-ttu-id="8f197-433">Modificare livello di allineamento al centro e zoom del viewport mappa.</span><span class="sxs-lookup"><span data-stu-id="8f197-433">Change the map viewport center and zoom level.</span></span>  
  
#### <a name="to-change-the-viewport"></a><span data-ttu-id="8f197-434">Per modificare il viewport</span><span class="sxs-lookup"><span data-stu-id="8f197-434">To change the viewport</span></span>  
  
1.  <span data-ttu-id="8f197-435">Fare clic con il pulsante destro del mouse sul viewport mappa, quindi scegliere **Proprietà viewport**.</span><span class="sxs-lookup"><span data-stu-id="8f197-435">Right-click the map viewport, and then click **Viewport Properties**.</span></span>  
  
2.  <span data-ttu-id="8f197-436">Fare clic su **Centra e zoom**.</span><span class="sxs-lookup"><span data-stu-id="8f197-436">Click **Center and Zoom**.</span></span>  
  
3.  <span data-ttu-id="8f197-437">Verificare che sia selezionata l'opzione **imposta un livello di centramento e di zoom della vista** .</span><span class="sxs-lookup"><span data-stu-id="8f197-437">Verify that the option **Set a view center and zoom level** is selected.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="8f197-438">Fare clic con il pulsante sinistro del mouse sul viewport mappa e trascinarne il centro fino al punto desiderato.</span><span class="sxs-lookup"><span data-stu-id="8f197-438">Left-click the map viewport, and drag the center of the viewport to the location that you want.</span></span>  
  
6.  <span data-ttu-id="8f197-439">Utilizzare la rotella del mouse per modificare il livello di zoom del viewport.</span><span class="sxs-lookup"><span data-stu-id="8f197-439">Use the mouse wheel to change the zoom level of the viewport.</span></span>  
  
7.  <span data-ttu-id="8f197-440">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-440">Preview the report.</span></span>  
  
 <span data-ttu-id="8f197-441">Nella visualizzazione della struttura la mappa nell'area di visualizzazione e la visualizzazione sono basate su dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="8f197-441">In Design view, the map on the display surface and the view is based on sample data.</span></span> <span data-ttu-id="8f197-442">Nel report visualizzabile, la vista mappa è allineata al centro della vista specificata.</span><span class="sxs-lookup"><span data-stu-id="8f197-442">In the rendered report, the map view is centered on the view that you specified.</span></span>  
  
##  <a name="add-a-report-title"></a><a name="Title"></a><span data-ttu-id="8f197-443">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="8f197-443">Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="8f197-444">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="8f197-444">To add a report title</span></span>  
  
1.  <span data-ttu-id="8f197-445">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="8f197-445">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="8f197-446">Digitare **Vendite nei punti vendita di New York** , quindi fare clic all'esterno della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="8f197-446">Type **Sales in New York Stores** and then click outside the text box.</span></span>  
  
 <span data-ttu-id="8f197-447">Il titolo verrà visualizzato nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="8f197-447">This title will appear at the top of the report.</span></span> <span data-ttu-id="8f197-448">Quando non è definita un'intestazione di pagina, gli elementi nella parte superiore del corpo del report equivalgono a un'intestazione di report.</span><span class="sxs-lookup"><span data-stu-id="8f197-448">Items at the top of the report body when there is no page header defined are the equivalent of a report header.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="8f197-449">Salva il report</span><span class="sxs-lookup"><span data-stu-id="8f197-449">Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="8f197-450">Per salvare il report</span><span class="sxs-lookup"><span data-stu-id="8f197-450">To save the report</span></span>  
  
1.  <span data-ttu-id="8f197-451">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="8f197-451">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="8f197-452">Fare clic sul pulsante Generatore report , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="8f197-452">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="8f197-453">In **Nome**digitare **Punti vendita di New York - vendite**.</span><span class="sxs-lookup"><span data-stu-id="8f197-453">In **Name**, type **Store Sales in New York**.</span></span>  
  
 <span data-ttu-id="8f197-454">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8f197-454">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8f197-455">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8f197-455">Next Steps</span></span>  
 <span data-ttu-id="8f197-456">Questa operazione conclude la procedura dettagliata per l'aggiunta di una mappa al report.</span><span class="sxs-lookup"><span data-stu-id="8f197-456">This concludes the walkthrough for how to add a map to your report.</span></span>  
  
 <span data-ttu-id="8f197-457">Per ulteriori informazioni, vedere [mappe &#40;Generatore report e SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) e il post di Blog sulla [regolazione cartografica dei dati spaziali per SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) in Blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="8f197-457">For more information, see [Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) and the blog entry [Cartographic Adjustment of Spatial Data for SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) on blogs.msdn.com.</span></span>  
  
 <span data-ttu-id="8f197-458">Per altre esercitazioni, vedere [esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="8f197-458">For more tutorials, see [Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f197-459">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f197-459">See Also</span></span>  
 <span data-ttu-id="8f197-460">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="8f197-460">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="8f197-461">[Generatore report SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="8f197-461">[Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="8f197-462">[Creazione guidata mappa e creazione guidata livello mappa &#40;Generatore report e SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8f197-462">[Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8f197-463">Variare la visualizzazione di poligoni, linee e punti in base a regole e dati analitici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8f197-463">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
