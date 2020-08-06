---
title: 'Esercitazione: Aggiunta di un indicatore di prestazioni chiave al report (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1bf77859-0b33-4f40-abaf-ebeeb6ebb1f8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 405978721068583597adf5c4257978a222121078
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720940"
---
# <a name="tutorial-adding-a-kpi-to-your-report-report-builder"></a><span data-ttu-id="1c16d-102">Esercitazione: Aggiunta di un indicatore di prestazioni chiave al report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="1c16d-102">Tutorial: Adding a KPI to Your Report (Report Builder)</span></span>
  <span data-ttu-id="1c16d-103">Un indicatore di prestazioni di chiave (KPI) è un valore misurabile dotato di significato aziendale.</span><span class="sxs-lookup"><span data-stu-id="1c16d-103">A key performance indicator (KPI) is a measurable value that has business significance.</span></span> <span data-ttu-id="1c16d-104">In questa esercitazione verrà illustrato come includere un indicatore KPI in un report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-104">This tutorial teaches you how to include a (KPI) in a report.</span></span> <span data-ttu-id="1c16d-105">In questo scenario l'indicatore KPI è il riepilogo delle vendite in base alle sottocategorie del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1c16d-105">In this scenario, the sales summary by product subcategories is the KPI.</span></span> <span data-ttu-id="1c16d-106">Lo stato corrente dell'indicatore KPI viene mostrato tramite colori, misuratori e indicatori.</span><span class="sxs-lookup"><span data-stu-id="1c16d-106">The current state of the KPI is shown by using colors, gauges, and indicators.</span></span>  
  
 <span data-ttu-id="1c16d-107">Nell'illustrazione seguente viene mostrato il report che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="1c16d-107">The following illustration shows the report that you will create.</span></span>  
  
 <span data-ttu-id="1c16d-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span><span class="sxs-lookup"><span data-stu-id="1c16d-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="1c16d-109">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="1c16d-109">What You Will Learn</span></span>  
 <span data-ttu-id="1c16d-110">In questa esercitazione verrà illustrato come aggiungere un indicatore KPI impostando il colore di sfondo delle celle della tabella in base al valore della cella, nonché come aggiungere e configurare un misuratore e un indicatore.</span><span class="sxs-lookup"><span data-stu-id="1c16d-110">In this tutorial, you will learn to add a KPI by setting the background color of table cells based on cell value and add and configure a gauge and an indicator.</span></span> <span data-ttu-id="1c16d-111">Verrà inoltre illustrato come scrivere l'espressione che consente di impostare il colore di sfondo delle celle della tabella.</span><span class="sxs-lookup"><span data-stu-id="1c16d-111">You also learn to write the expression that sets the background color of the table cells.</span></span>  
  
 <span data-ttu-id="1c16d-112">In questa esercitazione sono disponibili le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c16d-112">This tutorial contains the following procedures:</span></span>  
  
1.  [<span data-ttu-id="1c16d-113">Creare un report tabella e un set di dati dalla Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="1c16d-113">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Table)  
  
2.  [<span data-ttu-id="1c16d-114">Organizzare dati, scegliere il layout e lo stile dalla Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="1c16d-114">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="1c16d-115">Utilizzare i colori di sfondo per visualizzare un indicatore KPI</span><span class="sxs-lookup"><span data-stu-id="1c16d-115">Use Background Colors to Display a KPI</span></span>](#BackgroundColors)  
  
4.  [<span data-ttu-id="1c16d-116">Visualizzare un indicatore KPI tramite un misuratore</span><span class="sxs-lookup"><span data-stu-id="1c16d-116">Display a KPI by Using a Gauge</span></span>](#Gauge)  
  
5.  [<span data-ttu-id="1c16d-117">Visualizzare un indicatore KPI tramite un indicatore</span><span class="sxs-lookup"><span data-stu-id="1c16d-117">Display a KPI by Using an Indicator</span></span>](#Indicator)  
  
6.  [<span data-ttu-id="1c16d-118">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="1c16d-118">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="1c16d-119">Salva il report</span><span class="sxs-lookup"><span data-stu-id="1c16d-119">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="1c16d-120">In questa esercitazione, i passaggi della procedura guidata sono consolidati in due procedure: una per la creazione del set di dati e un'altra per la creazione di una tabella.</span><span class="sxs-lookup"><span data-stu-id="1c16d-120">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="1c16d-121">Per istruzioni dettagliate su come selezionare un server di report, scegliere un'origine dati, creare un set di dati ed eseguire la procedura guidata, vedere la prima esercitazione di questa serie: [Esercitazione: Creazione di un report tabella semplice &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1c16d-121">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="1c16d-122">Tempo previsto per il completamento di questa esercitazione: 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="1c16d-122">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c16d-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c16d-123">Requirements</span></span>  
 <span data-ttu-id="1c16d-124">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="1c16d-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Table"></a><span data-ttu-id="1c16d-125">1. creare un report tabella e un set di dati dalla creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="1c16d-125">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="1c16d-126">Nella finestra di dialogo **Introduzione** scegliere un'origine dati condivisa, creare un set di dati incorporato e visualizzare i dati in una tabella.</span><span class="sxs-lookup"><span data-stu-id="1c16d-126">From the **Getting Started** dialog box, choose a shared data source, create an embedded dataset, and display the data in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c16d-127">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="1c16d-127">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="1c16d-128">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="1c16d-128">This makes the query quite long.</span></span> <span data-ttu-id="1c16d-129">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="1c16d-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="1c16d-130">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="1c16d-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-table"></a><span data-ttu-id="1c16d-131">Per creare una nuova tabella</span><span class="sxs-lookup"><span data-stu-id="1c16d-131">To create a new table</span></span>  
  
1.  <span data-ttu-id="1c16d-132">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="1c16d-133">Verrà visualizzata la finestra di dialogo **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="1c16d-133">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c16d-134">Se la finestra di dialogo **Introduzione** non viene visualizzata, dal pulsante Generatore report fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-134">If the **Getting Started** dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="1c16d-135">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="1c16d-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="1c16d-136">Nel riquadro destro fare clic su **Creazione guidata tabella o matrice**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="1c16d-137">Nella pagina Scegliere un set di dati fare clic su **Crea un set di dati**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-137">On the Choose a dataset page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="1c16d-138">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="1c16d-139">Nella pagina **scegliere una connessione a un'origine dei dati** selezionare un'origine dati esistente o individuare il server di report e selezionare un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1c16d-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source.</span></span> <span data-ttu-id="1c16d-140">Se non vi è alcuna origine dati disponibile o non si dispone dell'accesso a un server di report, è possibile utilizzare un'origine dati incorporata.</span><span class="sxs-lookup"><span data-stu-id="1c16d-140">If there no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="1c16d-141">Per altre informazioni, vedere [Esercitazione: Creazione di un report tabella semplice &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1c16d-141">For more information, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="1c16d-142">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="1c16d-143">Nella pagina **Progetta query** fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="1c16d-144">Copiare e incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="1c16d-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
10. <span data-ttu-id="1c16d-145">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="1c16d-146">2. organizzare i dati, scegliere il layout e lo stile dalla creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="1c16d-146">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="1c16d-147">Utilizzare la procedura guidata per fornire una progettazione iniziale in cui visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="1c16d-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="1c16d-148">Il riquadro di anteprima nella procedura guidata consente di visualizzare il risultato del raggruppamento di dati prima di completare la progettazione della tabella o della matrice.</span><span class="sxs-lookup"><span data-stu-id="1c16d-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-choose-a-layout-and-a-style"></a><span data-ttu-id="1c16d-149">Per organizzare i dati in gruppi, scegliere un layout e uno stile</span><span class="sxs-lookup"><span data-stu-id="1c16d-149">To organize data into groups, choose a layout and a style</span></span>  
  
1.  <span data-ttu-id="1c16d-150">Nella pagina Disponi campi trascinare Product in **Valori**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-150">On the Arrange fields page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="1c16d-151">Trascinare Quantity in **Valori** e posizionarlo sotto Product.</span><span class="sxs-lookup"><span data-stu-id="1c16d-151">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="1c16d-152">Il campo Quantity viene riepilogato con la funzione Sum, ovvero la funzione predefinita per riepilogare i campi numerici.</span><span class="sxs-lookup"><span data-stu-id="1c16d-152">Quantity is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
3.  <span data-ttu-id="1c16d-153">Trascinare Sales in **Valori** e posizionarlo sotto Quantity.</span><span class="sxs-lookup"><span data-stu-id="1c16d-153">Drag Sales to **Values** and place below Quantity.</span></span>  
  
     <span data-ttu-id="1c16d-154">Nei passaggi 1, 2 e 3 sono specificati i dati da visualizzare nella tabella.</span><span class="sxs-lookup"><span data-stu-id="1c16d-154">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="1c16d-155">Trascinare SalesDate in **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-155">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="1c16d-156">Trascinare Subcategory in **Gruppi di righe** e posizionarlo sotto SalesDate.</span><span class="sxs-lookup"><span data-stu-id="1c16d-156">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="1c16d-157">I passaggi 4 e 5 consentono di organizzare i valori per i campi prima in base alla data, quindi in base a tutte le vendite per tale data.</span><span class="sxs-lookup"><span data-stu-id="1c16d-157">Steps 4 and 5 organize the values for the fields first by date, and then by all sales for that date.</span></span>  
  
6.  <span data-ttu-id="1c16d-158">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-158">Click **Next**.</span></span>  
  
     <span data-ttu-id="1c16d-159">Quando si esegue il report, nella tabella vengono visualizzati tutte le date, tutti gli ordini per ciascuna data e tutti i prodotti, le quantità e i totali di vendite per ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="1c16d-159">When you run the report, the table displays each date, all orders for each date, and all products, quantities, and sales totals for each order.</span></span>  
  
7.  <span data-ttu-id="1c16d-160">Nella pagina Scegliere il layout, in **Opzioni**, verificare che la casella **Mostra subtotali e totali complessivi** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="1c16d-160">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
8.  <span data-ttu-id="1c16d-161">Verificare che l'opzione **Bloccato, subtotale sotto** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="1c16d-161">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
9. <span data-ttu-id="1c16d-162">Deselezionare l'opzione **Espandi/comprimi gruppi**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-162">Clear the option **Expand/collapse groups**.</span></span>  
  
     <span data-ttu-id="1c16d-163">Nel report creato in questa esercitazione non viene utilizzata la funzionalità drill-down che consente all'utente di espandere una gerarchia di gruppo padre per visualizzare le righe del gruppo figlio e le righe di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="1c16d-163">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
10. <span data-ttu-id="1c16d-164">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-164">Click **Next**.</span></span>  
  
11. <span data-ttu-id="1c16d-165">Selezionare uno stile dal riquadro Stili della pagina Scegliere uno stile.</span><span class="sxs-lookup"><span data-stu-id="1c16d-165">On the Choose a Style page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="1c16d-166">Lo stile utilizzato nell'illustrazione per il record completato è Oceano.</span><span class="sxs-lookup"><span data-stu-id="1c16d-166">The illustration of the completed report shows the report using the Ocean style.</span></span>  
  
12. <span data-ttu-id="1c16d-167">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-167">Click **Finish**.</span></span>  
  
     <span data-ttu-id="1c16d-168">La tabella viene aggiunta all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1c16d-168">The table is added to the design surface.</span></span> <span data-ttu-id="1c16d-169">Nella tabella sono presenti cinque colonne e altrettante righe.</span><span class="sxs-lookup"><span data-stu-id="1c16d-169">The table has five columns and five rows.</span></span> <span data-ttu-id="1c16d-170">Nel riquadro Gruppi di righe sono visualizzati tre gruppi di righe: SalesDate, Subcategory e Details.</span><span class="sxs-lookup"><span data-stu-id="1c16d-170">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="1c16d-171">I dati dettaglio costituiscono tutti i dati recuperati dalla query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="1c16d-171">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
13. <span data-ttu-id="1c16d-172">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-172">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1c16d-173">Per ogni prodotto venduto in una data specifica, nella tabella vengono visualizzati il nome del prodotto, la quantità venduta e il totale delle vendite.</span><span class="sxs-lookup"><span data-stu-id="1c16d-173">For each product that is sold on a specific date, the table displays the product name, the quantity sold, and the sales total.</span></span> <span data-ttu-id="1c16d-174">I dati sono organizzati prima in base alla data delle vendite, quindi in base alla sottocategoria.</span><span class="sxs-lookup"><span data-stu-id="1c16d-174">The data is organized first by sales date and then by subcategory.</span></span>  
  
##  <a name="3-use-background-colors-to-display-a-kpi"></a><a name="BackgroundColors"></a><span data-ttu-id="1c16d-175">3. utilizzare i colori di sfondo per visualizzare un indicatore KPI</span><span class="sxs-lookup"><span data-stu-id="1c16d-175">3. Use Background Colors to Display a KPI</span></span>  
 <span data-ttu-id="1c16d-176">I colori di sfondo possono essere impostati su un'espressione valutata quando si esegue il report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-176">Background colors can be set to an expression that is evaluated when you run the report.</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-by-using-background-colors"></a><span data-ttu-id="1c16d-177">Per visualizzare lo stato attuale di un indicatore KPI utilizzando i colori di sfondo</span><span class="sxs-lookup"><span data-stu-id="1c16d-177">To display the present state of a KPI by using background colors</span></span>  
  
1.  <span data-ttu-id="1c16d-178">Nella tabella fare clic con il pulsante destro del mouse su due celle verso il basso dalla `[Sum(Sales)]` cella, ovvero la riga del subtotale in cui sono visualizzate le vendite per una sottocategoria, quindi fare clic su **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-178">In the table, right-click two cells down from the `[Sum(Sales)]` cell (the subtotal row that displays the sales for a subcategory), and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="1c16d-179">In **riempimento**fare clic sul pulsante **FX** accanto all'opzione **colore riempimento** e immettere l'espressione seguente nel campo **Imposta espressione per: BackgroundColor** :</span><span class="sxs-lookup"><span data-stu-id="1c16d-179">In **Fill**, click the **fx** button next to the **Fill color** option and enter the following expression in the **Set expression for: BackgroundColor** field:</span></span>  
  
 `=IIF(Sum(Fields!Sales.Value) >= 5000 ,"Lime", IIF(Sum(Fields!Sales.Value) < 2500, "Red","Yellow"))`  
  
 <span data-ttu-id="1c16d-180">Il colore di sfondo cambierà in verde, utilizzando la sfumatura di verde denominata "Verde brillante", per ogni cella contenente una somma aggregata per `[Sum(Sales)]` che può essere maggiore o uguale a 5000.</span><span class="sxs-lookup"><span data-stu-id="1c16d-180">This changes the background color to green, using the shade of green named "Lime", for each cell that contains an aggregated sum for `[Sum(Sales)]` that is greater than or equal to 5000.</span></span> <span data-ttu-id="1c16d-181">I valori di `[Sum(Sales)]` compresi tra 2500 e 5000 sono visualizzati in giallo,</span><span class="sxs-lookup"><span data-stu-id="1c16d-181">Values of `[Sum(Sales)]` between 2500 and 5000 are colored yellow.</span></span> <span data-ttu-id="1c16d-182">mentre quelli minori di 2500 in rosso.</span><span class="sxs-lookup"><span data-stu-id="1c16d-182">Values less than 2500 are colored red.</span></span>  
  
1.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="1c16d-183">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-183">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1c16d-184">Nella riga del subtotale in cui sono visualizzate le vendite per una sottocategoria, il colore di sfondo della cella è rosso, giallo o verde a seconda del valore della somma delle vendite.</span><span class="sxs-lookup"><span data-stu-id="1c16d-184">In the subtotal row that displays the sales for a subcategory, the background color of the cell is red, yellow, or green depending on value of the sales sum.</span></span>  
  
##  <a name="4-display-a-kpi-by-using-a-gauge"></a><a name="Gauge"></a><span data-ttu-id="1c16d-185">4. visualizzare un indicatore KPI tramite un misuratore</span><span class="sxs-lookup"><span data-stu-id="1c16d-185">4. Display a KPI by Using a Gauge</span></span>  
 <span data-ttu-id="1c16d-186">Un misuratore raffigura un singolo valore di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="1c16d-186">A gauge depicts a single value in a dataset.</span></span> <span data-ttu-id="1c16d-187">In questa esercitazione viene utilizzato un misuratore lineare orizzontale poiché la relativa forma e semplicità ne rende facile la lettura, anche quando è di piccole dimensioni e viene utilizzato all'interno di una cella della tabella.</span><span class="sxs-lookup"><span data-stu-id="1c16d-187">This tutorial uses a horizontal linear gauge because its shape and simplicity makes it easy to read, even in when it is a small size and used within a table cell.</span></span> <span data-ttu-id="1c16d-188">Per altre informazioni, vedere [Misuratori &#40;Generatore report e SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1c16d-188">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-a-gauge"></a><span data-ttu-id="1c16d-189">Per visualizzare lo stato attuale di un indicatore KPI utilizzando un misuratore</span><span class="sxs-lookup"><span data-stu-id="1c16d-189">To display the present state of a KPI using a gauge</span></span>  
  
1.  <span data-ttu-id="1c16d-190">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="1c16d-190">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="1c16d-191">Nella tabella fare clic con il pulsante destro del mouse sul gestore colonne per la cella modificata nella procedura precedente, scegliere **Inserisci colonna**, quindi fare clic su a **destra**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-191">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="1c16d-192">Alla tabella verrà aggiunta una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="1c16d-192">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="1c16d-193">Digitare **KPI** nell'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="1c16d-193">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="1c16d-194">Nel gruppo **aree dati** della scheda **Inserisci** fare clic su **misuratore**, quindi fare clic sull'area di progettazione all'esterno della tabella.</span><span class="sxs-lookup"><span data-stu-id="1c16d-194">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click the design surface outside the table.</span></span> <span data-ttu-id="1c16d-195">Verrà visualizzata la finestra di dialogo **Seleziona tipo di misuratore** .</span><span class="sxs-lookup"><span data-stu-id="1c16d-195">The **Select Gauge Type** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="1c16d-196">Fare clic su **lineare**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-196">Click **Linear**.</span></span> <span data-ttu-id="1c16d-197">Il primo tipo di misuratore lineare, **orizzontale**, è selezionato.</span><span class="sxs-lookup"><span data-stu-id="1c16d-197">The first linear gauge type, **Horizontal**, is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="1c16d-198">Nell'area di progettazione verrà aggiunto un misuratore.</span><span class="sxs-lookup"><span data-stu-id="1c16d-198">A gauge is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="1c16d-199">Dal riquadro dei dati del report trascinare Sales nel misuratore.</span><span class="sxs-lookup"><span data-stu-id="1c16d-199">From the Report Data pane, drag Sales to the gauge.</span></span> <span data-ttu-id="1c16d-200">Quando si trascina Sales nel misuratore, viene visualizzato il riquadro Dati misuratore.</span><span class="sxs-lookup"><span data-stu-id="1c16d-200">When you drag Sales across the gauge, the Gauge Data pane opens.</span></span>  
  
8.  <span data-ttu-id="1c16d-201">Rilasciare Sales nell'elenco **valori** .</span><span class="sxs-lookup"><span data-stu-id="1c16d-201">Drop Sales in the **Values** list.</span></span>  
  
     <span data-ttu-id="1c16d-202">Quando si rilascia il campo nel misuratore, il campo viene aggregato utilizzando la funzione Sum predefinita.</span><span class="sxs-lookup"><span data-stu-id="1c16d-202">When you drop the field onto the gauge, the field is aggregated by using the built-in Sum function.</span></span>  
  
9. <span data-ttu-id="1c16d-203">Fare clic con il pulsante destro del mouse sul misuratore e scegliere **Proprietà puntatore**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-203">Right-click the pointer in the gauge and click **Pointer Properties**.</span></span>  
  
10. <span data-ttu-id="1c16d-204">In **tipo di puntatore**selezionare **barra**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-204">In **Pointer Type**, select **Bar**.</span></span> <span data-ttu-id="1c16d-205">L'indicatore di misura si trasformerà da marcatore in una barra che risulterà più visibile in seguito all'aggiunta del misuratore alla tabella.</span><span class="sxs-lookup"><span data-stu-id="1c16d-205">This changes the pointer from a marker to a bar that will be more visible when the gauge is added to the table.</span></span>  
  
11. <span data-ttu-id="1c16d-206">Fare clic su **Riempimento puntatore**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-206">Click **Pointer Fill**.</span></span> <span data-ttu-id="1c16d-207">In **colore secondario** selezionare **giallo**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-207">In **Secondary Color,** pick **Yellow**.</span></span> <span data-ttu-id="1c16d-208">Il modello di riempimento sfumato cambierà da bianco in giallo.</span><span class="sxs-lookup"><span data-stu-id="1c16d-208">The gradient fill pattern will change from white to yellow.</span></span>  
  
12. <span data-ttu-id="1c16d-209">Fare clic con il pulsante destro del mouse sulla scala nel misuratore e selezionare **Proprietà scala**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-209">Right-click the scale in the gauge and click **Scale Properties**.</span></span>  
  
13. <span data-ttu-id="1c16d-210">Impostare l'opzione **Maximum** su 25000.</span><span class="sxs-lookup"><span data-stu-id="1c16d-210">Set the **Maximum** option to 25000.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c16d-211">Per calcolare dinamicamente il valore dell'opzione **Massimo** è possibile usare un'espressione invece di una costante, ad esempio 25000.</span><span class="sxs-lookup"><span data-stu-id="1c16d-211">Instead of a constant such as 25000, you can use an expression to dynamically calculate the value of the **Maximum** option.</span></span> <span data-ttu-id="1c16d-212">L'espressione utilizzerebbe in tal caso l'aggregazione della funzionalità di aggregazione, rendendola simile all'espressione `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span><span class="sxs-lookup"><span data-stu-id="1c16d-212">The expression would use the aggregate of aggregate feature and look similar to the expression `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span></span>  
  
14. <span data-ttu-id="1c16d-213">Trascinare il misuratore all'interno della tabella, nella terza cella della riga del subtotale in cui sono visualizzate le vendite per una sottocategoria della colonna inserita.</span><span class="sxs-lookup"><span data-stu-id="1c16d-213">Drag the gauge inside the table into the third cell in the subtotal row that displays the sales for a subcategory of the column that you inserted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c16d-214">Potrebbe essere necessario ridimensionare la colonna in modo che il misuratore lineare orizzontale rientri nella cella.</span><span class="sxs-lookup"><span data-stu-id="1c16d-214">You might have to resize the column so that the horizontal linear gauge fits into the cell.</span></span> <span data-ttu-id="1c16d-215">Per ridimensionare la colonna, fare clic sull'intestazione e utilizzare gli handle per ridimensionare le celle orizzontalmente e verticalmente.</span><span class="sxs-lookup"><span data-stu-id="1c16d-215">To resize the column, click a column header and use the handles to resize the cells horizontally and vertically.</span></span>  
  
15. <span data-ttu-id="1c16d-216">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-216">Click **Run** to preview the report.</span></span>  
  
     <span data-ttu-id="1c16d-217">La lunghezza orizzontale della barra nel misuratore cambia in base al valore dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="1c16d-217">The horizontal length of the bar in the gauge changes depending on the value of the KPI.</span></span>  
  
16. <span data-ttu-id="1c16d-218">(Facoltativo) Aggiungere un pin massimo per gestire l'overflow in modo che qualsiasi valore che supera il massimo della scala punti sempre al pin massimo:</span><span class="sxs-lookup"><span data-stu-id="1c16d-218">(Optional) Add a maximum pin to handle overflow so that any value over the scale maximum always points to the maximum pin:</span></span>  
  
    1.  <span data-ttu-id="1c16d-219">Aprire il riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1c16d-219">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="1c16d-220">Fare clic sulla scala.</span><span class="sxs-lookup"><span data-stu-id="1c16d-220">Click the scale.</span></span> <span data-ttu-id="1c16d-221">Le proprietà della scala lineare verranno visualizzate nel riquadro Proprietà.</span><span class="sxs-lookup"><span data-stu-id="1c16d-221">The properties for the linear scale are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="1c16d-222">Nella categoria **pin della scala** espandere il nodo **MaximumPin** .</span><span class="sxs-lookup"><span data-stu-id="1c16d-222">In the **Scale Pins** category, expand the **MaximumPin** node.</span></span>  
  
    4.  <span data-ttu-id="1c16d-223">Impostare la proprietà **Enable** su `True` .</span><span class="sxs-lookup"><span data-stu-id="1c16d-223">Set the **Enable** property to `True`.</span></span> <span data-ttu-id="1c16d-224">Verrà visualizzato un pin dopo il valore massimo della scala.</span><span class="sxs-lookup"><span data-stu-id="1c16d-224">A pin appears after the maximum value on the scale.</span></span>  
  
    5.  <span data-ttu-id="1c16d-225">Impostare **BorderColor** su `Lime` .</span><span class="sxs-lookup"><span data-stu-id="1c16d-225">Set **BorderColor** to `Lime`.</span></span>  
  
17. <span data-ttu-id="1c16d-226">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-display-a-kpi-by-using-an-indicator"></a><a name="Indicator"></a><span data-ttu-id="1c16d-227">5. visualizzare un indicatore KPI tramite un indicatore</span><span class="sxs-lookup"><span data-stu-id="1c16d-227">5. Display a KPI by Using an Indicator</span></span>  
 <span data-ttu-id="1c16d-228">Gli indicatori sono piccoli e semplici misuratori che consentono di visualizzare i valori dei dati in modo immediato.</span><span class="sxs-lookup"><span data-stu-id="1c16d-228">Indicators are small simple gauges that communicate data values at a glance.</span></span> <span data-ttu-id="1c16d-229">Grazie alle loro dimensioni e alla semplicità, gli indicatori vengono spesso utilizzati nelle tabelle e nelle matrici.</span><span class="sxs-lookup"><span data-stu-id="1c16d-229">Because of their size and simplicity, indicators are often used in tables and matrices.</span></span> <span data-ttu-id="1c16d-230">Per altre informazioni, vedere [Indicatori &#40;Generatore report e SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1c16d-230">For more information, see [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-an-indicator"></a><span data-ttu-id="1c16d-231">Per visualizzare lo stato attuale di un indicatore KPI utilizzando un indicatore</span><span class="sxs-lookup"><span data-stu-id="1c16d-231">To display the present state of a KPI using an indicator</span></span>  
  
1.  <span data-ttu-id="1c16d-232">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="1c16d-232">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="1c16d-233">Nella tabella fare clic con il pulsante destro del mouse sul gestore colonne per la cella modificata nella procedura precedente, scegliere **Inserisci colonna**, quindi fare clic su a **destra**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-233">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="1c16d-234">Alla tabella verrà aggiunta una nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="1c16d-234">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="1c16d-235">Digitare **KPI** nell'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="1c16d-235">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="1c16d-236">Fare clic sulla cella per il subtotale della sottocategoria.</span><span class="sxs-lookup"><span data-stu-id="1c16d-236">Click the cell for the subcategory subtotal.</span></span>  
  
5.  <span data-ttu-id="1c16d-237">Nel gruppo **aree dati** della scheda **Inserisci** fare doppio clic su **indicatore.**</span><span class="sxs-lookup"><span data-stu-id="1c16d-237">On the **Insert** tab, in the **Data Regions** group, double-click **Indicator.**</span></span>  
  
     <span data-ttu-id="1c16d-238">Verrà visualizzata la finestra di dialogo **Seleziona tipo indicatore** .</span><span class="sxs-lookup"><span data-stu-id="1c16d-238">The **Select Indicator Type** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="1c16d-239">Fare clic su **forme**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-239">Click **Shapes**.</span></span> <span data-ttu-id="1c16d-240">Viene selezionato il primo tipo di forma, **3 semafori (Non bordati)** .</span><span class="sxs-lookup"><span data-stu-id="1c16d-240">The first shape type, **3 Traffic Lights (Unrimmed),** is selected.</span></span>  
  
     <span data-ttu-id="1c16d-241">Nell'esercitazione verrà utilizzato questo indicatore.</span><span class="sxs-lookup"><span data-stu-id="1c16d-241">You will use this indicator in the tutorial.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="1c16d-242">L'indicatore verrà aggiunto all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1c16d-242">The indicator is added to the design surface.</span></span>  
  
8.  <span data-ttu-id="1c16d-243">Fare clic con il pulsante destro del mouse sull'indicatore e scegliere **Proprietà indicatore**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-243">Right-click the indicator and click **Indicator Properties**.</span></span>  
  
9. <span data-ttu-id="1c16d-244">Fare clic su **valori e Stati**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-244">Click **Values and States**.</span></span>  
  
10. <span data-ttu-id="1c16d-245">Nell'elenco a discesa valore selezionare **[Sum (Sales)]**, ma non modificare altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="1c16d-245">In the Value drop-down list, select **[Sum(Sales)]**, but do not change any other options.</span></span>  
  
     <span data-ttu-id="1c16d-246">Per impostazione predefinita, si verifica la sincronizzazione dei dati nell'area dati e il valore **Tablix1**, ovvero il nome dell'area dati della tabella nel report, viene visualizzato nella casella **Ambito sincronizzazione** .</span><span class="sxs-lookup"><span data-stu-id="1c16d-246">By default, data synchronization occurs across the data region and you see the value **Tablix1**, the name of the table data region in the report, in the **Synchronization scope** box.</span></span>  
  
     <span data-ttu-id="1c16d-247">In questo report, è possibile anche modificare l'ambito di un indicatore posizionato nella cella del subtotale della sottocategoria per eseguire la sincronizzazione nel campo SalesDate.</span><span class="sxs-lookup"><span data-stu-id="1c16d-247">In this report, you can also change the scope of an indicator placed in the cell of the subcategory subtotal to synchronize across the SalesDate field.</span></span>  
  
11. <span data-ttu-id="1c16d-248">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-248">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="1c16d-249">6. aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="1c16d-249">6. Add a Report Title</span></span>  
 <span data-ttu-id="1c16d-250">Nella parte superiore del report viene visualizzato il titolo del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-250">A report title appears at the top of the report.</span></span> <span data-ttu-id="1c16d-251">È possibile posizionare il titolo del report in un'apposita intestazione oppure, se ne è privo, in una casella di testo nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-251">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="1c16d-252">Sarà utilizzata la casella di testo che viene posizionata automaticamente nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-252">You will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="1c16d-253">Il testo può essere ulteriormente migliorato applicando stili di carattere, dimensioni e colori diversi alle frasi e ai singoli caratteri del testo.</span><span class="sxs-lookup"><span data-stu-id="1c16d-253">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="1c16d-254">Per altre informazioni, vedere [Formattare il testo in una casella di testo &#40;Generatore report e SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1c16d-254">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="1c16d-255">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="1c16d-255">To add a report title</span></span>  
  
1.  <span data-ttu-id="1c16d-256">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-256">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="1c16d-257">Digitare **KPI vendite prodotto**, quindi fare clic all'esterno della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="1c16d-257">Type **Product Sales KPI**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="1c16d-258">Facoltativamente, fare clic con il pulsante destro del mouse sulla casella di testo contenente **KPI vendite prodotto**, fare clic su **Proprietà casella di testo**, quindi nella scheda carattere selezionare gli stili, le dimensioni e i colori dei diversi tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="1c16d-258">Optionally, right-click the text box that contains **Product Sales KPI**, click **Text Box Properties**, and then on the Font tab select the different font styles, sizes and colors.</span></span>  
  
4.  <span data-ttu-id="1c16d-259">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-259">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="1c16d-260">7. salvare il report</span><span class="sxs-lookup"><span data-stu-id="1c16d-260">7. Save the Report</span></span>  
 <span data-ttu-id="1c16d-261">Salvare il report in un server di report o nel computer.</span><span class="sxs-lookup"><span data-stu-id="1c16d-261">Save the report to a report server or your computer.</span></span> <span data-ttu-id="1c16d-262">Se il report non viene salvato nel server di report, non saranno disponibili alcune funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , ad esempio le parti del report e i sottoreport.</span><span class="sxs-lookup"><span data-stu-id="1c16d-262">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="1c16d-263">Per salvare il report in un server di report</span><span class="sxs-lookup"><span data-stu-id="1c16d-263">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="1c16d-264">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-264">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="1c16d-265">Fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-265">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="1c16d-266">Selezionare o digitare il nome del server di report per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-266">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="1c16d-267">Verrà visualizzato il messaggio "Connessione al server di report".</span><span class="sxs-lookup"><span data-stu-id="1c16d-267">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="1c16d-268">Al termine della connessione, verrà visualizzato il contenuto della cartella di report specificata dall'amministratore del server di report come posizione predefinita per i report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-268">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="1c16d-269">In **Nome**sostituire il nome predefinito con **Product Sales KPI**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-269">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
5.  <span data-ttu-id="1c16d-270">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-270">Click **Save**.</span></span>  
  
 <span data-ttu-id="1c16d-271">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-271">The report is saved to the report server.</span></span> <span data-ttu-id="1c16d-272">Il nome del server di report al quale si è connessi verrà visualizzato sulla barra di stato nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="1c16d-272">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="1c16d-273">Per salvare il report nel computer</span><span class="sxs-lookup"><span data-stu-id="1c16d-273">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="1c16d-274">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-274">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="1c16d-275">Fare clic su **Desktop**, **Documenti**o **Risorse del computer**e selezionare la cartella in cui si vuole salvare il report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-275">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c16d-276">Se non si ha accesso a un server di report, fare clic su **Desktop**, **Documenti**o **Risorse del computer** e salvare il report nel computer.</span><span class="sxs-lookup"><span data-stu-id="1c16d-276">If you do not have access to a report server, click **Desktop**, **My Documents**, or **My computer** and save the report to your computer.</span></span>  
  
1.  <span data-ttu-id="1c16d-277">In **Nome**sostituire il nome predefinito con **Product Sales KPI**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-277">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
2.  <span data-ttu-id="1c16d-278">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1c16d-278">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1c16d-279">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1c16d-279">Next Steps</span></span>  
 <span data-ttu-id="1c16d-280">Questo passaggio conclude l'esercitazione relativa all'aggiunta di un indicatore KPI al report.</span><span class="sxs-lookup"><span data-stu-id="1c16d-280">You have successfully completed the Adding a KPI to Your Report tutorial.</span></span> <span data-ttu-id="1c16d-281">Per ulteriori informazioni, vedere indicatori dei misuratori (Generatore report) [&#40;Generatore report e SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1c16d-281">For more information, see Gauges (Report Builder) [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c16d-282">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c16d-282">See Also</span></span>  
 <span data-ttu-id="1c16d-283">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="1c16d-283">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="1c16d-284">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1c16d-284">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
