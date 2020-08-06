---
title: 'Esercitazione: Aggiungere un grafico a barre al report (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6956ebd6-0217-4087-a4fa-5cc1c3804691
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01708ca548c40118daa03fac34d8a323d628b012
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627067"
---
# <a name="tutorial-add-a-bar-chart-to-your-report-report-builder"></a><span data-ttu-id="31971-102">Esercitazione: Aggiungere un grafico a barre al report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="31971-102">Tutorial: Add a Bar Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="31971-103">In un grafico a barre i dati delle categorie vengono visualizzati orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="31971-103">A bar chart displays category data horizontally.</span></span> <span data-ttu-id="31971-104">per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="31971-104">This can help to:</span></span>  
  
-   <span data-ttu-id="31971-105">Migliorare la leggibilità dei nomi di categoria lunghi.</span><span class="sxs-lookup"><span data-stu-id="31971-105">Improve readability of long category names.</span></span>  
  
-   <span data-ttu-id="31971-106">Migliorare la comprensibilità delle ore tracciate come valori.</span><span class="sxs-lookup"><span data-stu-id="31971-106">Improve understandability of times plotted as values.</span></span>  
  
-   <span data-ttu-id="31971-107">Confrontare il valore relativo di più serie.</span><span class="sxs-lookup"><span data-stu-id="31971-107">Compare the relative value of multiple series.</span></span>  
  
 <span data-ttu-id="31971-108">Nell'illustrazione seguente viene mostrato il grafico a barre che verrà creato, in ordine alfabetico, con le vendite dei primi cinque venditori per gli anni 2008 e 2009.</span><span class="sxs-lookup"><span data-stu-id="31971-108">The following illustration shows the bar chart that you will create, with sales for 2008 and 2009 for the top five salespeople, in alphabetical order.</span></span>  
  
 <span data-ttu-id="31971-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span><span class="sxs-lookup"><span data-stu-id="31971-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="31971-110">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="31971-110">What You Will Learn</span></span>  
 <span data-ttu-id="31971-111">In questa esercitazione verranno illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31971-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="31971-112">Creare un grafico da Creazione guidata grafico</span><span class="sxs-lookup"><span data-stu-id="31971-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="31971-113">Scegliere il tipo di grafico</span><span class="sxs-lookup"><span data-stu-id="31971-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="31971-114">Visualizzare i valori di tutte le categorie sull'asse verticale</span><span class="sxs-lookup"><span data-stu-id="31971-114">Display all Category Values on the Vertical Axis</span></span>](#AllValues)  
  
4.  [<span data-ttu-id="31971-115">Modificare la visualizzazione dei nomi sull'asse verticale</span><span class="sxs-lookup"><span data-stu-id="31971-115">Modify the Display of Names on the Vertical Axis</span></span>](#Sort)  
  
5.  [<span data-ttu-id="31971-116">Spostare la legenda</span><span class="sxs-lookup"><span data-stu-id="31971-116">Move the Legend</span></span>](#Legend)  
  
6.  [<span data-ttu-id="31971-117">Spostare il titolo del grafico</span><span class="sxs-lookup"><span data-stu-id="31971-117">Move the Chart Title</span></span>](#ChartTitle)  
  
7.  [<span data-ttu-id="31971-118">Formattare l'asse orizzontale e assegnare un'etichetta</span><span class="sxs-lookup"><span data-stu-id="31971-118">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
8.  [<span data-ttu-id="31971-119">Aggiungere un filtro per visualizzare i primi cinque valori</span><span class="sxs-lookup"><span data-stu-id="31971-119">Add a Filter to Display the Top Five Values</span></span>](#Filter)  
  
9. [<span data-ttu-id="31971-120">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="31971-120">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="31971-121">Salva il report</span><span class="sxs-lookup"><span data-stu-id="31971-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="31971-122">In questa esercitazione, i passaggi per la procedura guidata sono consolidati in un'unica procedura.</span><span class="sxs-lookup"><span data-stu-id="31971-122">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="31971-123">Per istruzioni dettagliate su come selezionare un server di report, creare un set di dati e scegliere un'origine dati, vedere la prima esercitazione di questa serie: [Esercitazione: Creazione di un report di tabelle semplici &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="31971-123">For step-by-step instructions about how to browse to a report server, create a dataset, and choose a data source, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="31971-124">Tempo previsto per il completamento di questa esercitazione: 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="31971-124">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31971-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31971-125">Requirements</span></span>  
 <span data-ttu-id="31971-126">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="31971-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="31971-127">1. creare un report grafico da Creazione guidata grafico</span><span class="sxs-lookup"><span data-stu-id="31971-127">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="31971-128">Nella finestra di dialogo **Introduzione** creare un set di dati incorporato, scegliere un'origine dati condivisa e creare un grafico a barre utilizzando la creazione guidata grafico.</span><span class="sxs-lookup"><span data-stu-id="31971-128">From the **Getting Started** dialog box, create an embedded dataset, choose a shared data source, and create a bar chart by using the Chart Wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31971-129">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="31971-129">In this tutorial, the query contains the data values so that it does not need an external data source.</span></span> <span data-ttu-id="31971-130">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="31971-130">This makes the query quite long.</span></span> <span data-ttu-id="31971-131">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="31971-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="31971-132">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="31971-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="31971-133">Per creare un nuovo report grafico</span><span class="sxs-lookup"><span data-stu-id="31971-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="31971-134">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="31971-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="31971-135">Verrà visualizzata la finestra di dialogo **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="31971-135">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31971-136">Se la finestra di dialogo **Introduzione** non viene visualizzata, fare clic sul pulsante Generatore report, quindi fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="31971-136">If the **Getting Started** dialog box does not appear, click the Report Builder button, and then click **New**.</span></span>  
  
2.  <span data-ttu-id="31971-137">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="31971-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="31971-138">Nel riquadro di destra fare clic su **Creazione guidata grafico**.</span><span class="sxs-lookup"><span data-stu-id="31971-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="31971-139">Nella pagina **Scegliere un set di dati** fare clic su **Crea un set di dati**e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="31971-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="31971-140">Nella pagina **Scegliere una connessione a un'origine dati** selezionare un'origine dati esistente o individuare il server di report, quindi selezionare un'origine dati e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="31971-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="31971-141">Potrebbe essere necessario immettere un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="31971-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31971-142">L'origine dati scelta non ha importanza purché si disponga delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="31971-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="31971-143">Non verranno recuperati dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="31971-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="31971-144">Per altre informazioni, vedere [Modalità alternative di acquisizione di una connessione dati &#40;Generatore report&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="31971-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="31971-145">Nella pagina **Progetta query** fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="31971-145">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="31971-146">Incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="31971-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Luis' as FirstName, 'Alverca' as LastName, CAST(170000.00 AS money) AS SalesYear2009, CAST(150000. AS money) AS SalesYear2008  
    UNION SELECT 'Jeffrey' as FirstName, 'Zeng' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(190000. AS money) AS SalesYear2008  
    UNION SELECT 'Houman' as FirstName, 'Pournasseh' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Robin' as FirstName, 'Wood' as LastName, CAST(75000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'Daniela' as FirstName, 'Guaita' as LastName,  CAST(170000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'John' as FirstName, 'Yokim' as LastName, CAST(160000. AS money) AS SalesYear2009, CAST(195000. AS money) AS SalesYear2008  
    UNION SELECT 'Delphine' as FirstName, 'Ribaute' as LastName, CAST(180000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Robert' as FirstName, 'Hernady' as LastName, CAST(140000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Tanja' as FirstName, 'Plate' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(160000. AS money) AS SalesYear2008  
    UNION SELECT 'David' as FirstName, 'Bradley' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Michal' as FirstName, 'Jaworski' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(220000. AS money) AS SalesYear2008  
    UNION SELECT 'Chris' as FirstName, 'Ashton' as LastName, CAST(195000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Pongsiri' as FirstName, 'Hirunyanitiwatna' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(215000. AS money) AS SalesYear2008  
    UNION SELECT 'Brian' as FirstName, 'Burke' as LastName, CAST(187000. AS money) AS SalesYear2009, CAST(207000. AS money) AS SalesYear2008  
    ```  
  
8.  <span data-ttu-id="31971-147">(Facoltativo) Fare clic sul pulsante Esegui (**!**) per visualizzare i dati su cui si baserà il grafico.</span><span class="sxs-lookup"><span data-stu-id="31971-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="31971-148">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="31971-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="31971-149">2. scegliere il tipo di grafico</span><span class="sxs-lookup"><span data-stu-id="31971-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="31971-150">È possibile scegliere tra diversi tipi di grafico predefiniti.</span><span class="sxs-lookup"><span data-stu-id="31971-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="31971-151">Per aggiungere un istogramma</span><span class="sxs-lookup"><span data-stu-id="31971-151">To add a column chart</span></span>  
  
1.  <span data-ttu-id="31971-152">L'istogramma è il tipo di grafico predefinito nella pagina **Scegliere un tipo di grafico** .</span><span class="sxs-lookup"><span data-stu-id="31971-152">On the **Choose a chart type** page, the column chart is the default chart type.</span></span>  
  
2.  <span data-ttu-id="31971-153">Fare clic su **Barre**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="31971-153">Click **Bar**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="31971-154">Nella pagina **Disponi campi del grafico** sono presenti quattro campi nel riquadro **campi disponibili** : FirstName, LastName, SalesYear2009 e SalesYear2008.</span><span class="sxs-lookup"><span data-stu-id="31971-154">On the **Arrange chart fields** page, there are four fields in the **Available fields** pane: FirstName, LastName, SalesYear2009, and SalesYear2008.</span></span>  
  
3.  <span data-ttu-id="31971-155">Trascinare LastName nel riquadro Categorie.</span><span class="sxs-lookup"><span data-stu-id="31971-155">Drag LastName to the Categories pane.</span></span>  
  
4.  <span data-ttu-id="31971-156">Trascinare SalesYear2009 nel riquadro Valori.</span><span class="sxs-lookup"><span data-stu-id="31971-156">Drag SalesYear2009 to the Values pane.</span></span> <span data-ttu-id="31971-157">SalesYear2009 rappresenta l'importo delle vendite di ogni venditore per l'anno 2009.</span><span class="sxs-lookup"><span data-stu-id="31971-157">SalesYear2009 represents the sales amount for each salesperson for the year 2009.</span></span> <span data-ttu-id="31971-158">Nel riquadro Valori viene visualizzato `[Sum(SalesYear2009)]` perché nel grafico viene mostrata l'aggregazione per ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="31971-158">The Values pane displays `[Sum(SalesYear2009)]` because the chart displays the aggregate for each product.</span></span>  
  
5.  <span data-ttu-id="31971-159">Trascinare SalesYear2008 nel riquadro Valori sotto SalesYear2009.</span><span class="sxs-lookup"><span data-stu-id="31971-159">Drag SalesYear2008 to the Values pane under SalesYear2009.</span></span> <span data-ttu-id="31971-160">SalesYear2008 rappresenta l'importo delle vendite di ogni venditore per l'anno 2008.</span><span class="sxs-lookup"><span data-stu-id="31971-160">SalesYear2008 represents the sales amount for each salesperson for the year 2008.</span></span>  
  
6.  <span data-ttu-id="31971-161">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="31971-161">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="31971-162">Nel riquadro Stili della pagina **scegliere uno stile** selezionare uno stile.</span><span class="sxs-lookup"><span data-stu-id="31971-162">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="31971-163">Uno stile specifica lo stile del carattere, il set di colori e uno stile del bordo.</span><span class="sxs-lookup"><span data-stu-id="31971-163">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="31971-164">Quando si seleziona uno stile, nel riquadro di anteprima viene visualizzato un esempio del grafico con lo stile selezionato.</span><span class="sxs-lookup"><span data-stu-id="31971-164">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
8.  <span data-ttu-id="31971-165">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="31971-165">Click **Finish**.</span></span>  
  
     <span data-ttu-id="31971-166">Il grafico verrà aggiunto all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="31971-166">The chart is added to the design surface.</span></span>  
  
9. <span data-ttu-id="31971-167">Fare clic sul grafico per visualizzarne gli handle.</span><span class="sxs-lookup"><span data-stu-id="31971-167">Click the chart to display the chart handles.</span></span> <span data-ttu-id="31971-168">Trascinare l'angolo inferiore destro del grafico per ingrandirlo.</span><span class="sxs-lookup"><span data-stu-id="31971-168">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span>  
  
10. <span data-ttu-id="31971-169">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="31971-170">Nel report viene visualizzato il grafico a barre relativo alle vendite di ogni venditore per gli anni 2008 e 2009.</span><span class="sxs-lookup"><span data-stu-id="31971-170">The report displays the bar chart for sales for each sales person for the years 2008 and 2009.</span></span> <span data-ttu-id="31971-171">La lunghezza della barra corrisponde al totale delle vendite.</span><span class="sxs-lookup"><span data-stu-id="31971-171">The length of the bar corresponds to the sales total.</span></span>  
  
##  <a name="3-modify-the-display-of-names-on-the-vertical-axis"></a><a name="AllValues"></a><span data-ttu-id="31971-172">3. modificare la visualizzazione dei nomi sull'asse verticale</span><span class="sxs-lookup"><span data-stu-id="31971-172">3. Modify the Display of Names on the Vertical Axis</span></span>  
 <span data-ttu-id="31971-173">Per impostazione predefinita sull'asse verticale vengono visualizzati solo alcuni valori.</span><span class="sxs-lookup"><span data-stu-id="31971-173">By default, only some of the values on the vertical axis appear.</span></span> <span data-ttu-id="31971-174">È possibile modificare il grafico per visualizzare tutte le categorie.</span><span class="sxs-lookup"><span data-stu-id="31971-174">You can change the chart to display all categories.</span></span>  
  
#### <a name="to-display-all-sales-persons-along-the-category-axis-of-a-bar-chart"></a><span data-ttu-id="31971-175">Per visualizzare tutti i venditori lungo l'asse delle categorie di un grafico a barre</span><span class="sxs-lookup"><span data-stu-id="31971-175">To display all sales persons along the category axis of a bar chart</span></span>  
  
1.  <span data-ttu-id="31971-176">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="31971-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="31971-177">Fare clic con il pulsante destro del mouse sull'asse verticale, quindi scegliere **Proprietà asse verticale**.</span><span class="sxs-lookup"><span data-stu-id="31971-177">Right-click the vertical axis, and then click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="31971-178">Nella casella **Intervallo**di **Intervallo asse** digitare **1**.</span><span class="sxs-lookup"><span data-stu-id="31971-178">Under **Axis range and interval**, in the **Interval** box, type **1**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="31971-179">Fare clic con il pulsante destro del mouse sul **titolo dell'asse** verticale e deselezionare la casella di controllo **Mostra titolo asse** .</span><span class="sxs-lookup"><span data-stu-id="31971-179">Right-click the vertical **Axis Title** and clear the **Show Axis Title** check box.</span></span>  
  
6.  <span data-ttu-id="31971-180">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-180">Click **Run** to preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31971-181">Se i nomi dei venditori sull'asse verticale non sono leggibili, è possibile aumentare l'altezza del grafico o modificare le opzioni di formattazione per le etichette dell'asse.</span><span class="sxs-lookup"><span data-stu-id="31971-181">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
###  <a name="display-last-name-and-first-name-on-vertical-axis"></a><a name="CategoryExpression"></a><span data-ttu-id="31971-182">Visualizzare cognome e nome sull'asse verticale</span><span class="sxs-lookup"><span data-stu-id="31971-182">Display Last Name and First Name on Vertical Axis</span></span>  
 <span data-ttu-id="31971-183">È possibile modificare l'espressione delle categorie per includere il cognome seguito dal nome di ogni venditore.</span><span class="sxs-lookup"><span data-stu-id="31971-183">You can change the category expression to include last name followed by first name of each sales person.</span></span>  
  
##### <a name="to-change-the-category-expression"></a><span data-ttu-id="31971-184">Per modificare l'espressione delle categorie</span><span class="sxs-lookup"><span data-stu-id="31971-184">To change the category expression</span></span>  
  
1.  <span data-ttu-id="31971-185">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="31971-185">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="31971-186">Fare doppio clic sul grafico per visualizzare il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="31971-186">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="31971-187">Nell'area **Gruppi di categorie** fare clic con il pulsante destro del mouse sul campo [LastName] e scegliere **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="31971-187">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="31971-188">In Etichetta fare clic sul pulsante espressione (Fx).</span><span class="sxs-lookup"><span data-stu-id="31971-188">In Label, click the expression (Fx) button.</span></span>  
  
5.  <span data-ttu-id="31971-189">Digitare l'espressione seguente: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="31971-189">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
     <span data-ttu-id="31971-190">Questa espressione determina la concatenazione di cognome, virgola e nome.</span><span class="sxs-lookup"><span data-stu-id="31971-190">This expression concatenates the last name, a comma, and the first name.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="31971-191">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-191">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="31971-192">Se i nomi non vengono visualizzati quando si esegue il report, è possibile aggiornare i dati manualmente.</span><span class="sxs-lookup"><span data-stu-id="31971-192">If the first names do not appear when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="31971-193">Mentre si è ancora in modalità anteprima, fare clic su **Aggiorna** nel gruppo **Navigazione** della scheda **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="31971-193">While still in preview mode, on the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31971-194">Se i nomi dei venditori sull'asse verticale non sono leggibili, è possibile aumentare l'altezza del grafico o modificare le opzioni di formattazione per le etichette dell'asse.</span><span class="sxs-lookup"><span data-stu-id="31971-194">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
##  <a name="4-change-the-sort-order-for-names-on-the-vertical-axis"></a><a name="Sort"></a><span data-ttu-id="31971-195">4. modificare l'ordinamento dei nomi sull'asse verticale</span><span class="sxs-lookup"><span data-stu-id="31971-195">4. Change the Sort Order for Names on the Vertical Axis</span></span>  
 <span data-ttu-id="31971-196">Quando si ordinano i dati in un grafico si modifica l'ordine dei valori sull'asse delle categorie.</span><span class="sxs-lookup"><span data-stu-id="31971-196">When you sort the data on a chart, you are changing the order of values on the category axis.</span></span>  
  
#### <a name="to-sort-the-names-in-alphabetical-order-on-the-bar-chart"></a><span data-ttu-id="31971-197">Per ordinare i nomi in ordine alfabetico sul grafico a barre</span><span class="sxs-lookup"><span data-stu-id="31971-197">To sort the names in alphabetical order on the bar chart</span></span>  
  
1.  <span data-ttu-id="31971-198">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="31971-198">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="31971-199">Fare doppio clic sul grafico per visualizzare il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="31971-199">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="31971-200">Nell'area **Gruppi di categorie** fare clic con il pulsante destro del mouse sul campo [LastName] e scegliere **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="31971-200">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="31971-201">Fare clic su **Ordinamento**.</span><span class="sxs-lookup"><span data-stu-id="31971-201">Click **Sorting**.</span></span> <span data-ttu-id="31971-202">Nella pagina **Modificare le opzioni di ordinamento** viene visualizzato un elenco di espressioni di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="31971-202">The **Change sorting options** page displays a list of sort expressions.</span></span> <span data-ttu-id="31971-203">Per impostazione predefinita, l'elenco dispone di un'unica espressione di ordinamento che equivale all'espressione originale di raggruppamento delle categorie.</span><span class="sxs-lookup"><span data-stu-id="31971-203">By default, this list has one sort expression that is the same as the original category group expression.</span></span>  
  
5.  <span data-ttu-id="31971-204">In Ordina per fare clic sul pulsante espressione (**FX**).</span><span class="sxs-lookup"><span data-stu-id="31971-204">In Sort by, click the expression (**Fx**) button.</span></span>  
  
6.  <span data-ttu-id="31971-205">Digitare l'espressione seguente: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="31971-205">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
7.  <span data-ttu-id="31971-206">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="31971-206">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="31971-207">Tornare alla pagina **Proprietà gruppo categorie** nell'elenco a discesa **ordine** Selezionare **da Z a a**. Questa operazione consente di selezionare l'ordine alfabetico inverso in modo che i nomi vengano visualizzati in ordine dall'alto verso il basso.</span><span class="sxs-lookup"><span data-stu-id="31971-207">Back on the **Category Group Properties** page, in the **Order** drop-down list, select **Z to A**. This selects reverse alphabetical order so that the names appear in order from top to bottom.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="31971-208">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-208">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="31971-209">I nomi sull'asse orizzontale vengono ordinati in ordine inverso, con **partendo Alerca fino** nella parte superiore e **Zeng** nella parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="31971-209">The names on the horizontal axis are sorted in reverse order, with **Alerca** at the top and **Zeng** at the bottom.</span></span>  
  
##  <a name="5-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="31971-210">5. spostare la legenda</span><span class="sxs-lookup"><span data-stu-id="31971-210">5. Move the Legend</span></span>  
 <span data-ttu-id="31971-211">Per migliorare la leggibilità dei valori del grafico, è possibile spostare la legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="31971-211">To improve the readability of the chart values, you might want to move the chart legend.</span></span> <span data-ttu-id="31971-212">In un grafico a barre in cui le barre sono visualizzate orizzontalmente, è ad esempio possibile modificare la posizione della legenda in modo che si trovi al di sopra o al di sotto dell'area del grafico.</span><span class="sxs-lookup"><span data-stu-id="31971-212">For example, in a bar chart where bars are shown horizontally, you can change the position of the legend so that it is above or below the chart area.</span></span> <span data-ttu-id="31971-213">In questo modo lo spazio orizzontale disponibile per le barre risulterà maggiore.</span><span class="sxs-lookup"><span data-stu-id="31971-213">This gives more horizontal space to the bars.</span></span>  
  
#### <a name="to-display-the-legend-below-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="31971-214">Per visualizzare la legenda al di sotto dell'area del grafico di un grafico a barre</span><span class="sxs-lookup"><span data-stu-id="31971-214">To display the legend below the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="31971-215">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="31971-215">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="31971-216">Fare clic con il pulsante destro del mouse sulla legenda nel grafico.</span><span class="sxs-lookup"><span data-stu-id="31971-216">Right-click the legend on the chart.</span></span>  
  
3.  <span data-ttu-id="31971-217">Selezionare **Proprietà legenda**.</span><span class="sxs-lookup"><span data-stu-id="31971-217">Select **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="31971-218">In **Posizione legenda**selezionare un'altra posizione,</span><span class="sxs-lookup"><span data-stu-id="31971-218">For **Legend position**, select a different position.</span></span> <span data-ttu-id="31971-219">ad esempio la posizione centrale inferiore.</span><span class="sxs-lookup"><span data-stu-id="31971-219">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="31971-220">Quando la legenda viene posizionata alla fine o all'inizio di un grafico, il relativo layout viene modificato da verticale in orizzontale.</span><span class="sxs-lookup"><span data-stu-id="31971-220">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="31971-221">È possibile selezionare un altro layout nell'elenco a discesa **Layout** .</span><span class="sxs-lookup"><span data-stu-id="31971-221">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="31971-222">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-222">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="31971-223">6. titolo del grafico</span><span class="sxs-lookup"><span data-stu-id="31971-223">6. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="31971-224">Per modificare il titolo di un grafico a barre al di sopra dell'area del grafico</span><span class="sxs-lookup"><span data-stu-id="31971-224">To change the chart title above the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="31971-225">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="31971-225">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="31971-226">Selezionare le parole **titolo grafico** nella parte superiore del grafico, quindi digitare il testo seguente: **vendite per 2008 e 2009**.</span><span class="sxs-lookup"><span data-stu-id="31971-226">Select the words **Chart Title** at the top of the chart, and then type the following text: **Sales for 2008 and 2009**.</span></span>  
  
3.  <span data-ttu-id="31971-227">Fare clic in un punto qualsiasi all'esterno del testo.</span><span class="sxs-lookup"><span data-stu-id="31971-227">Click anywhere outside the text.</span></span>  
  
4.  <span data-ttu-id="31971-228">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-228">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="31971-229">7. formattare l'asse orizzontale e assegnare un'etichetta</span><span class="sxs-lookup"><span data-stu-id="31971-229">7. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="31971-230">Per impostazione predefinita, sull'asse orizzontale vengono visualizzati valori in un formato generale che viene ridimensionato automaticamente in base alle dimensioni del grafico.</span><span class="sxs-lookup"><span data-stu-id="31971-230">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-the-numbers-on-the-horizontal-axis"></a><span data-ttu-id="31971-231">Per formattare i numeri sull'asse orizzontale</span><span class="sxs-lookup"><span data-stu-id="31971-231">To format the numbers on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="31971-232">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="31971-232">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="31971-233">Fare clic sull'asse orizzontale lungo il bordo inferiore del grafico per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="31971-233">Click the horizontal axis along the bottom of the chart to select it.</span></span>  
  
     <span data-ttu-id="31971-234">Sulla barra multifunzione, nel gruppo **numero** della scheda **Home** fare clic sul pulsante **valuta** .</span><span class="sxs-lookup"><span data-stu-id="31971-234">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="31971-235">Le etichette dell'asse orizzontale vengono convertite nel formato valuta.</span><span class="sxs-lookup"><span data-stu-id="31971-235">The horizontal axis labels change to currency.</span></span>  
  
3.  <span data-ttu-id="31971-236">(Facoltativo) Rimuovere le cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="31971-236">(Optional) Remove the decimal digits.</span></span> <span data-ttu-id="31971-237">Fare clic due volte sul pulsante **Diminuisci decimali** accanto al pulsante **Valuta** .</span><span class="sxs-lookup"><span data-stu-id="31971-237">Near the **Currency** button, click the **Decrease Decimal** button twice.</span></span>  
  
4.  <span data-ttu-id="31971-238">Fare clic con il pulsante destro del mouse sull'asse orizzontale e scegliere **Proprietà asse orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="31971-238">Right-click the horizontal axis, and click **Horizontal Axis Properties**.</span></span>  
  
5.  <span data-ttu-id="31971-239">Nella scheda **numero** selezionare **Mostra valori in migliaia.**</span><span class="sxs-lookup"><span data-stu-id="31971-239">On the **Number** tab, select **Show values in Thousands.**</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="31971-240">Fare clic con il pulsante destro del mouse su **titolo asse** e scegliere **Proprietà titolo asse**.</span><span class="sxs-lookup"><span data-stu-id="31971-240">Right-click **Axis Title** and click **Axis Title Properties**.</span></span>  
  
8.  <span data-ttu-id="31971-241">Nella casella di **testo titolo** digitare **vendite in migliaia** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="31971-241">In the **Title text** box, type **Sales in thousands** and click **OK**.</span></span>  
  
9. <span data-ttu-id="31971-242">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-242">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="31971-243">Nel report l'importo delle vendite viene visualizzato sull'asse orizzontale come valuta in migliaia senza cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="31971-243">The report displays the sales amount on the horizontal axis as currency in thousands, and has no decimal digits.</span></span>  
  
##  <a name="8-add-a-filter-to-display-the-top-five-values"></a><a name="Filter"></a><span data-ttu-id="31971-244">8. aggiungere un filtro per visualizzare i primi cinque valori</span><span class="sxs-lookup"><span data-stu-id="31971-244">8. Add a Filter to Display the Top Five Values</span></span>  
 <span data-ttu-id="31971-245">È possibile aggiungere un filtro al grafico per specificare quali dati del set di dati includere o escludere.</span><span class="sxs-lookup"><span data-stu-id="31971-245">You can add a filter to the chart to specify which data from the dataset to include or exclude in the chart.</span></span>  
  
#### <a name="to-add-a-filter-and-display-the-top-five-values"></a><span data-ttu-id="31971-246">Per aggiungere un filtro e visualizzare i primi cinque valori</span><span class="sxs-lookup"><span data-stu-id="31971-246">To add a filter and display the top five values</span></span>  
  
1.  <span data-ttu-id="31971-247">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="31971-247">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="31971-248">Fare doppio clic sul grafico per visualizzare il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="31971-248">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="31971-249">Nell'area **Gruppi di categorie** fare clic con il pulsante destro del mouse sul campo [LastName] e scegliere **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="31971-249">In the **Category Groups** area, right-click the [LastName] field, and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="31971-250">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="31971-250">Click **Filters**.</span></span> <span data-ttu-id="31971-251">Nella pagina **Modificare i filtri** può essere visualizzato un elenco di espressioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="31971-251">The **Change filters** page can display a list of filter expressions.</span></span> <span data-ttu-id="31971-252">Per impostazione predefinita, tale elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="31971-252">By default, this list is empty.</span></span>  
  
5.  <span data-ttu-id="31971-253">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="31971-253">Click **Add**.</span></span> <span data-ttu-id="31971-254">Verrà visualizzato un nuovo filtro vuoto.</span><span class="sxs-lookup"><span data-stu-id="31971-254">A new blank filter appears.</span></span>  
  
6.  <span data-ttu-id="31971-255">In **espressione**Digitare **[Sum (SalesYear2009)]**.</span><span class="sxs-lookup"><span data-stu-id="31971-255">In **Expression**, type **[Sum(SalesYear2009)]**.</span></span> <span data-ttu-id="31971-256">Viene creata l'espressione sottostante `=Sum(Fields!SalesYear2009.Value)`, che può essere visualizzata facendo clic sul pulsante **fx** .</span><span class="sxs-lookup"><span data-stu-id="31971-256">This creates the underlying expression `=Sum(Fields!SalesYear2009.Value)`, which you can see if you click the **fx** button.</span></span>  
  
7.  <span data-ttu-id="31971-257">Verificare che il tipo di dati sia **Text**.</span><span class="sxs-lookup"><span data-stu-id="31971-257">Verify that the data type is **Text**.</span></span>  
  
8.  <span data-ttu-id="31971-258">In **Operatore**selezionare **Top N** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="31971-258">In **Operator**, select **Top N** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="31971-259">In **Valore**digitare l'espressione seguente: **=5**</span><span class="sxs-lookup"><span data-stu-id="31971-259">In **Value**, type the following expression: **=5**</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="31971-260">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-260">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="31971-261">Se i risultati non vengono filtrati quando si esegue il report, sarà possibile aggiornare i dati manualmente.</span><span class="sxs-lookup"><span data-stu-id="31971-261">If the results are not filtered when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="31971-262">Nella scheda **Esegui** del gruppo **Navigazione** fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="31971-262">On the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
 <span data-ttu-id="31971-263">Nel grafico verranno visualizzati i primi cinque nomi di venditori in base ai dati relativi alle vendite del 2009.</span><span class="sxs-lookup"><span data-stu-id="31971-263">The chart shows the top five salesperson names from the 2009 sales data.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="31971-264">9. aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="31971-264">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="31971-265">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="31971-265">To add a report title</span></span>  
  
1.  <span data-ttu-id="31971-266">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="31971-266">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="31971-267">Digitare **grafico a barre-Vendite**, premere INVIO, quindi digitare **primi cinque venditori per 2009**, in modo da ottenere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="31971-267">Type **Sales Bar Chart**, press ENTER, and then type **Top Five Sellers for 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="31971-268">**Grafico a barre - Vendite**</span><span class="sxs-lookup"><span data-stu-id="31971-268">**Sales Bar Chart**</span></span>  
  
     <span data-ttu-id="31971-269">**Primi cinque venditori per il 2009**</span><span class="sxs-lookup"><span data-stu-id="31971-269">**Top Five Sellers for 2009**</span></span>  
  
3.  <span data-ttu-id="31971-270">Selezionare **Grafico a barre - Vendite**e fare clic sul pulsante **Grassetto** .</span><span class="sxs-lookup"><span data-stu-id="31971-270">Select **Sales Bar Chart**, and click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="31971-271">Selezionare i **primi cinque venditori per 2009**e nella sezione **carattere** della scheda **Home** impostare le dimensioni del carattere su **10**.</span><span class="sxs-lookup"><span data-stu-id="31971-271">Select **Top Five Sellers for 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="31971-272">(Facoltativo) Per contenere le due righe del testo potrebbe essere necessario aumentare l'altezza della casella di testo Titolo.</span><span class="sxs-lookup"><span data-stu-id="31971-272">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="31971-273">Il titolo verrà visualizzato nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="31971-273">This title will appear at the top of the report.</span></span> <span data-ttu-id="31971-274">Quando non è definita un'intestazione di pagina, gli elementi nella parte superiore del corpo del report equivalgono a un'intestazione di report.</span><span class="sxs-lookup"><span data-stu-id="31971-274">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="31971-275">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="31971-275">Click **Run** to preview the report.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="31971-276">10. salvare il report</span><span class="sxs-lookup"><span data-stu-id="31971-276">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="31971-277">Per salvare il report</span><span class="sxs-lookup"><span data-stu-id="31971-277">To save the report</span></span>  
  
1.  <span data-ttu-id="31971-278">Passare alla visualizzazione di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="31971-278">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="31971-279">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="31971-279">From the **Report Builder** button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="31971-280">In **Nome**digitare **Grafico a barre - Vendite**.</span><span class="sxs-lookup"><span data-stu-id="31971-280">In **Name**, type **Sales Bar Chart**.</span></span>  
  
4.  <span data-ttu-id="31971-281">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="31971-281">Click **Save**.</span></span>  
  
 <span data-ttu-id="31971-282">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="31971-282">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="31971-283">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="31971-283">Next Steps</span></span>  
 <span data-ttu-id="31971-284">Questo passaggio conclude l'esercitazione relativa all'aggiunta di un grafico a barre al report.</span><span class="sxs-lookup"><span data-stu-id="31971-284">You have successfully completed the Adding a Bar Chart to Your Report tutorial.</span></span> <span data-ttu-id="31971-285">Per altre informazioni sui grafici, vedere [Grafici &#40;Generatore report e SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) e [Grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="31971-285">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31971-286">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31971-286">See Also</span></span>  
 <span data-ttu-id="31971-287">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="31971-287">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="31971-288">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="31971-288">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
