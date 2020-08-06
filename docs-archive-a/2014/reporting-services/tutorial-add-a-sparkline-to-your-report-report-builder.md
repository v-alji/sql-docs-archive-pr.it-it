---
title: 'Esercitazione: Aggiunta di un grafico sparkline al report (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 18c90a36-48bf-4805-a960-2d1e8f00c2dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1bf83810b6c743b977e399864ce2edd514f572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720957"
---
# <a name="tutorial-add-a-sparkline-to-your-report-report-builder"></a><span data-ttu-id="94dd4-102">Esercitazione: Aggiungere un grafico sparkline al report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="94dd4-102">Tutorial: Add a Sparkline to Your Report (Report Builder)</span></span>
  <span data-ttu-id="94dd4-103">In questa esercitazione si creerà un report tabella semplice basato su dati di vendita di esempio, quindi si aggiungerà un grafico sparkline a una cella della tabella.</span><span class="sxs-lookup"><span data-stu-id="94dd4-103">In this tutorial, you create a basic table report based on sample sales data, and then add a sparkline chart to a cell in the table.</span></span>  
  
 <span data-ttu-id="94dd4-104">Una versione avanzata del report che verrà creato in questa esercitazione è disponibile come report di esempio di Generatore report di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94dd4-104">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="94dd4-105">Per ulteriori informazioni sul download di questo report di esempio e di altri, vedere [Generatore report report di esempio](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="94dd4-105">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span> <span data-ttu-id="94dd4-106">Nell'immagine seguente viene illustrato il report di esempio simile a quello che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="94dd4-106">The following illustration shows the sample report similar to the one that you will create.</span></span>  
  
 <span data-ttu-id="94dd4-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span><span class="sxs-lookup"><span data-stu-id="94dd4-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span></span>  
  
 <span data-ttu-id="94dd4-108">Il video [procedura: creare un sparkline in una tabella (video Generatore report)](https://technet.microsoft.com/bi/ff871942.aspx) illustra come creare un report simile con i grafici sparkline.</span><span class="sxs-lookup"><span data-stu-id="94dd4-108">The video [How to: Create a Sparkline in a Table (Report Builder Video)](https://technet.microsoft.com/bi/ff871942.aspx) illustrates how to create a similar report with sparklines.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="94dd4-109">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="94dd4-109">What You Will Learn</span></span>  
 <span data-ttu-id="94dd4-110">In questa esercitazione verranno illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="94dd4-110">In this tutorial, you will learn how to do the following:</span></span>  
  
 1. [<span data-ttu-id="94dd4-111">Creare un report con una tabella</span><span class="sxs-lookup"><span data-stu-id="94dd4-111">Create a Report with a Table</span></span>](#CreateTable)  
  
 2. [<span data-ttu-id="94dd4-112">Creare una query in Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="94dd4-112">Create a Query in the Table or Matrix Wizard</span></span>](#Query)  
  
 3. [<span data-ttu-id="94dd4-113">Aggiungere un grafico sparkline alla tabella</span><span class="sxs-lookup"><span data-stu-id="94dd4-113">Add a Sparkline to the Table</span></span>](#Sparkline)  
  
 4. [<span data-ttu-id="94dd4-114">Allineare i grafici sparkline verticalmente e orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="94dd4-114">Align the Sparklines Vertically and Horizontally</span></span>](#AlignSparklines)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="94dd4-115">Altri passaggi facoltativi</span><span class="sxs-lookup"><span data-stu-id="94dd4-115">Other Optional Steps</span></span>  
 5. [<span data-ttu-id="94dd4-116">Formattare i dati come valuta</span><span class="sxs-lookup"><span data-stu-id="94dd4-116">Format Data as Currency</span></span>](#FormatCurrency)  
  
 6. [<span data-ttu-id="94dd4-117">Formattare i dati come date</span><span class="sxs-lookup"><span data-stu-id="94dd4-117">Format Data as Dates</span></span>](#FormatDates)  
  
 7. [<span data-ttu-id="94dd4-118">Modificare la larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="94dd4-118">Change Column Widths</span></span>](#Width)  
  
 8. [<span data-ttu-id="94dd4-119">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="94dd4-119">Add a Report Title</span></span>](#Title)  
  
 9. [<span data-ttu-id="94dd4-120">Salva il report</span><span class="sxs-lookup"><span data-stu-id="94dd4-120">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="94dd4-121">Tempo previsto per il completamento di questa esercitazione: 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="94dd4-121">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94dd4-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94dd4-122">Requirements</span></span>  
 <span data-ttu-id="94dd4-123">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="94dd4-123">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-report-with-a-table"></a><a name="CreateTable"></a><span data-ttu-id="94dd4-124">1. creare un report con una tabella</span><span class="sxs-lookup"><span data-stu-id="94dd4-124">1. Create a Report with a Table</span></span>  
  
#### <a name="to-create-a-report"></a><span data-ttu-id="94dd4-125">Per creare un report</span><span class="sxs-lookup"><span data-stu-id="94dd4-125">To create a report</span></span>  
  
1.  <span data-ttu-id="94dd4-126">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-126">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="94dd4-127">Verrà visualizzata la finestra di dialogo **Attività iniziali**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-127">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94dd4-128">Se la finestra di dialogo **Introduzione** non viene visualizzata, dal pulsante **Generatore report** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-128">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="94dd4-129">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="94dd4-129">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="94dd4-130">Nel riquadro destro fare clic su **Creazione guidata tabella o matrice**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-130">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="94dd4-131">Nella pagina **Scegliere un set di dati** selezionare **Crea un set di dati**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-131">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="94dd4-132">Verrà visualizzata la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="94dd4-132">The **Choose a connection to a data source** page opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94dd4-133">Per questa esercitazione non sono necessari dati specifici. È sufficiente una connessione a un database di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94dd4-133">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="94dd4-134">Se in **Connessioni a origini dati**è già disponibile una connessione all'origine dati, sarà possibile selezionarla e andare al passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="94dd4-134">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to step 10.</span></span> <span data-ttu-id="94dd4-135">Per altre informazioni, vedere [Modalità alternative di acquisizione di una connessione dati &#40;Generatore report&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="94dd4-135">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  <span data-ttu-id="94dd4-136">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-136">Click **New**.</span></span> <span data-ttu-id="94dd4-137">Verrà visualizzata la finestra di dialogo **Proprietà origine dati** .</span><span class="sxs-lookup"><span data-stu-id="94dd4-137">The **Data Source Properties** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="94dd4-138">In **Nome**digitare **Vendite prodotto**come nome per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="94dd4-138">In **Name**, type **Product Sales**, a name for the data source.</span></span>  
  
7.  <span data-ttu-id="94dd4-139">In **Select a connection type**(Seleziona un tipo di connessione), verificare che sia selezionato **Microsoft SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="94dd4-139">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
8.  <span data-ttu-id="94dd4-140">In **Stringa di connessione**digitare il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="94dd4-140">In **Connection string**, type the following text:</span></span>  
  
     <span data-ttu-id="94dd4-141">**Origine dati =\<servername>**</span><span class="sxs-lookup"><span data-stu-id="94dd4-141">**Data Source=\<servername>**</span></span>  
  
     <span data-ttu-id="94dd4-142">L'espressione \<servername>, ad esempio Report001, indica un computer in cui è installata un'istanza del motore di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="94dd4-142">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="94dd4-143">Poiché i dati del report non vengono estratti da un database di SQL Server, non è necessario includere il nome di un database.</span><span class="sxs-lookup"><span data-stu-id="94dd4-143">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="94dd4-144">Per analizzare la query viene utilizzato il database predefinito nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="94dd4-144">The default database on the specified server is used to parse the query.</span></span>  
  
9. <span data-ttu-id="94dd4-145">Fare clic su **Credenziali**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-145">Click **Credentials**.</span></span> <span data-ttu-id="94dd4-146">Immettere le credenziali necessarie per accedere all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="94dd4-146">Enter the credentials that you need to access the external data source.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="94dd4-147">Verrà visualizzata di nuovo la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="94dd4-147">You are back on the **Choose a connection to a data source** page.</span></span>  
  
11. <span data-ttu-id="94dd4-148">Per verificare che la connessione all'origine dati avvenga correttamente, fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-148">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="94dd4-149">Verrà visualizzato il messaggio "Creazione connessione completata".</span><span class="sxs-lookup"><span data-stu-id="94dd4-149">The message "Connection created successfully" appears.</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="94dd4-150">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-150">Click **Next**.</span></span>  
  
##  <a name="2-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="94dd4-151">2. creare una query in creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="94dd4-151">2. Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="94dd4-152">In un report, è possibile utilizzare un set di dati condiviso che dispone di una query predefinita oppure è possibile creare un set di dati incorporato da utilizzare solo nel report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-152">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="94dd4-153">In questa esercitazione si creerà un set di dati incorporato.</span><span class="sxs-lookup"><span data-stu-id="94dd4-153">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94dd4-154">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="94dd4-154">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="94dd4-155">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="94dd4-155">This makes the query quite long.</span></span> <span data-ttu-id="94dd4-156">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="94dd4-156">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="94dd4-157">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="94dd4-157">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="94dd4-158">Per creare una query</span><span class="sxs-lookup"><span data-stu-id="94dd4-158">To create a query</span></span>  
  
1.  <span data-ttu-id="94dd4-159">Nella pagina **Progetta query** si apre la finestra Progettazione query relazionale.</span><span class="sxs-lookup"><span data-stu-id="94dd4-159">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="94dd4-160">Per questa esercitazione si utilizzerà la finestra Progettazione query basata su testo.</span><span class="sxs-lookup"><span data-stu-id="94dd4-160">For this tutorial, you will use the text-based query designer.</span></span>  
  
2.  <span data-ttu-id="94dd4-161">Fare clic su **modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-161">Click **Edit As Text**.</span></span> <span data-ttu-id="94dd4-162">Nella finestra Progettazione query basata su testo viene visualizzato il riquadro della query e il riquadro dei risultati.</span><span class="sxs-lookup"><span data-stu-id="94dd4-162">The text-based query designer displays a query pane and a results pane.</span></span>  
  
3.  <span data-ttu-id="94dd4-163">Nella casella [!INCLUDE[tsql](../includes/tsql-md.md)] Query **incollare la query** seguente.</span><span class="sxs-lookup"><span data-stu-id="94dd4-163">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Budget Movie-Maker' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Slim Digital' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,'Accessories' as Subcategory,    
       'Budget Movie-Maker' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2010-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Carrying Case' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
4.  <span data-ttu-id="94dd4-164">Sulla barra degli strumenti di Progettazione query fare clic su Esegui (**!**).</span><span class="sxs-lookup"><span data-stu-id="94dd4-164">On the query designer toolbar, click Run  (**!**).</span></span>  
  
     <span data-ttu-id="94dd4-165">La query viene eseguita e viene visualizzato il set di risultati per il campi **SalesDate**, **Subcategory**, **Product**, **Sales**e **Quantity**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-165">The query runs and displays the result set for the fields **SalesDate**, **Subcategory**, **Product**, **Sales**, and **Quantity**.</span></span>  
  
5.  <span data-ttu-id="94dd4-166">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-166">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="94dd4-167">Nella pagina **Disponi campi** trascinare **Sales** in **Valori**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-167">On the **Arrange fields** page, drag **Sales** to **Values**.</span></span>  
  
     <span data-ttu-id="94dd4-168">Il campo**Sales** viene aggregato mediante la funzione Sum.</span><span class="sxs-lookup"><span data-stu-id="94dd4-168">**Sales** is aggregated by the Sum function.</span></span> <span data-ttu-id="94dd4-169">Il valore è [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="94dd4-169">The value is [Sum(Sales)].</span></span>  
  
7.  <span data-ttu-id="94dd4-170">Trascinare **Product** in **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-170">Drag **Product** to **Row groups**.</span></span>  
  
8.  <span data-ttu-id="94dd4-171">Trascinare **SalesDate** in **Gruppi di colonne**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-171">Drag **SalesDate** to **Column groups**.</span></span>  
  
9. <span data-ttu-id="94dd4-172">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-172">Click **Next**.</span></span>  
  
10. <span data-ttu-id="94dd4-173">Nella pagina **scegliere il layout** , in **Opzioni**, verificare che sia selezionata l'opzione **Mostra subtotali e totali** complessivi.</span><span class="sxs-lookup"><span data-stu-id="94dd4-173">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="94dd4-174">Nel riquadro di anteprima della creazione guidata verrà visualizzata una tabella con tre righe.</span><span class="sxs-lookup"><span data-stu-id="94dd4-174">The wizard Preview pane displays a table with three rows.</span></span> <span data-ttu-id="94dd4-175">Quando si esegue il report, ogni riga viene visualizzata nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="94dd4-175">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="94dd4-176">La prima riga verrà visualizzata una sola volta per la tabella per mostrare le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="94dd4-176">The first row will appear once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="94dd4-177">La seconda riga verrà ripetuta una volta per ogni prodotto e conterrà il nome del prodotto, il totale per giorno e il totale della riga.</span><span class="sxs-lookup"><span data-stu-id="94dd4-177">The second row will repeat once for each product and display the product name, total per day, and line total.</span></span>  
  
    3.  <span data-ttu-id="94dd4-178">La terza riga verrà visualizzata una sola volta per la tabella per visualizzare i totali complessivi.</span><span class="sxs-lookup"><span data-stu-id="94dd4-178">The third row will appear once for the table to display the grand totals.</span></span>  
  
11. <span data-ttu-id="94dd4-179">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-179">Click **Next**.</span></span>  
  
12. <span data-ttu-id="94dd4-180">Nel riquadro **Stili** della pagina **Scegliere uno stile** selezionare **Ardesia**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-180">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>  
  
     <span data-ttu-id="94dd4-181">Nel riquadro di anteprima viene visualizzato un esempio della tabella con lo stile selezionato.</span><span class="sxs-lookup"><span data-stu-id="94dd4-181">The Preview pane displays a sample of the table with that style.</span></span>  
  
13. <span data-ttu-id="94dd4-182">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-182">Click **Finish**.</span></span>  
  
14. <span data-ttu-id="94dd4-183">La tabella viene aggiunta all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="94dd4-183">The table is added to the design surface.</span></span> <span data-ttu-id="94dd4-184">Nella tabella sono presenti tre colonne e altrettante righe.</span><span class="sxs-lookup"><span data-stu-id="94dd4-184">The table has three columns and three rows.</span></span>  
  
     <span data-ttu-id="94dd4-185">Osservare il riquadro di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="94dd4-185">Look in the Grouping pane.</span></span> <span data-ttu-id="94dd4-186">Se il riquadro Raggruppamento non è visualizzato, scegliere **Raggruppamento** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-186">If you can't see the Grouping pane, on the **View** menu, click **Grouping**.</span></span> <span data-ttu-id="94dd4-187">Nel riquadro Gruppi di righe viene visualizzato un gruppo di righe, ovvero **Product**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-187">The Row Groups pane shows one row group: **Product**.</span></span> <span data-ttu-id="94dd4-188">Nel riquadro Gruppi di colonne viene visualizzato un gruppo di colonne, ovvero **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-188">The Column Groups pane shows one column group: **SalesDate**.</span></span> <span data-ttu-id="94dd4-189">I dati dettaglio costituiscono tutti i dati recuperati dalla query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="94dd4-189">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
15. <span data-ttu-id="94dd4-190">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-190">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-add-a-sparkline"></a><a name="Sparkline"></a><span data-ttu-id="94dd4-191">3. aggiungere un sparkline</span><span class="sxs-lookup"><span data-stu-id="94dd4-191">3. Add a Sparkline</span></span>  
  
#### <a name="to-add-a-sparkline-chart-to-a-table"></a><span data-ttu-id="94dd4-192">Per aggiungere un grafico sparkline a una tabella</span><span class="sxs-lookup"><span data-stu-id="94dd4-192">To add a sparkline chart to a table</span></span>  
  
1.  <span data-ttu-id="94dd4-193">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="94dd4-193">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="94dd4-194">Selezionare la colonna Total nella tabella.</span><span class="sxs-lookup"><span data-stu-id="94dd4-194">Select the Total column in your table.</span></span>  
  
3.  <span data-ttu-id="94dd4-195">Fare clic con il pulsante destro del mouse, scegliere **Inserisci colonna**e fare clic su **A sinistra**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-195">Right-click, point to **Insert Column**, and then click **Left**.</span></span>  
  
4.  <span data-ttu-id="94dd4-196">Nella nuova colonna, fare clic con il pulsante destro del mouse sulla riga [Product], scegliere la scheda **Inserisci** barra multifunzione e quindi fare clic su **sparkline**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-196">In the new column, right-click in the [Product] row, point to the **Insert** ribbon tab, and then click **Sparkline**.</span></span>  
  
5.  <span data-ttu-id="94dd4-197">Verificare che sia selezionato il primo sparkline nella riga della **colonna** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-197">Make sure the first sparkline in the **Column** row is selected and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="94dd4-198">Fare clic sul grafico sparkline per visualizzare il riquadro Dati grafico.</span><span class="sxs-lookup"><span data-stu-id="94dd4-198">Click the sparkline to show the Chart Data pane.</span></span>  
  
7.  <span data-ttu-id="94dd4-199">Fare clic sul segno più (+) nella casella valori, quindi fare clic su **vendite**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-199">Click the plus (+) sign in the Values box, and then click **Sales**.</span></span>  
  
     <span data-ttu-id="94dd4-200">I valori nel campo **Sales** corrispondono ora ai valori per il grafico sparkline.</span><span class="sxs-lookup"><span data-stu-id="94dd4-200">The values in the **Sales** field are now the values for the sparkline.</span></span>  
  
8.  <span data-ttu-id="94dd4-201">Fare clic sul segno più (+) nella casella gruppi di categorie e quindi fare clic su **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-201">Click the plus (+) sign in the Category Groups box, and then click **SalesDate**.</span></span>  
  
9. <span data-ttu-id="94dd4-202">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-202">Click **Run** to preview your report.</span></span>  
  
     <span data-ttu-id="94dd4-203">Si noti che sono presenti grafici sparkline in ogni riga della tabella, che tuttavia non sono corretti.</span><span class="sxs-lookup"><span data-stu-id="94dd4-203">Note that there are sparkline charts in each row of the table, but they're not correct.</span></span> <span data-ttu-id="94dd4-204">Le barre nei grafici non sono allineate l'una all'altra.</span><span class="sxs-lookup"><span data-stu-id="94dd4-204">The bars in the charts don't line up with each other.</span></span> <span data-ttu-id="94dd4-205">Nella seconda riga di dati sono presenti solo quattro barre; pertanto le barre risultano più ampie di quelle nella prima riga, che ne contiene sei.</span><span class="sxs-lookup"><span data-stu-id="94dd4-205">There are only four bars in the second row of data, so the bars are wider than the bars in the first row, which has six.</span></span> <span data-ttu-id="94dd4-206">Non è possibile confrontare i valori di ogni prodotto per giorno.</span><span class="sxs-lookup"><span data-stu-id="94dd4-206">You can't compare values for each product per day.</span></span> <span data-ttu-id="94dd4-207">È necessario che le barre siano allineate.</span><span class="sxs-lookup"><span data-stu-id="94dd4-207">They need to line up with each other.</span></span>  
  
     <span data-ttu-id="94dd4-208">Per ogni riga si noti inoltre che la barra più alta per la riga specifica corrisponde all'altezza della riga stessa.</span><span class="sxs-lookup"><span data-stu-id="94dd4-208">Also note that for each row, the tallest bar for that row is the height of the row.</span></span> <span data-ttu-id="94dd4-209">Anche questo è fuorviante perché i valori più grandi per ogni riga non sono uguali: il valore più grande per il produttore del budget è $10.400, ma il valore più grande per Slim Digital è $26.576-più del doppio delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="94dd4-209">This is misleading, too, because the largest values for each row are not equal: the largest value for Budget Movie-Maker is $10,400, but the largest value for Slim Digital is $26,576-more than twice as large.</span></span> <span data-ttu-id="94dd4-210">Inoltre, le barre più grandi in quelle due righe hanno all'incirca la stessa altezza.</span><span class="sxs-lookup"><span data-stu-id="94dd4-210">And yet the largest bars in those two rows are about the same height.</span></span> <span data-ttu-id="94dd4-211">L'altezza deve inoltre essere ridimensionata conformemente agli altri grafici sparkline.</span><span class="sxs-lookup"><span data-stu-id="94dd4-211">That also needs to be made to scale with the other sparklines.</span></span>  
  
     <span data-ttu-id="94dd4-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span><span class="sxs-lookup"><span data-stu-id="94dd4-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span></span>  
  
##  <a name="4-align-the-sparklines-vertically-and-horizontally"></a><a name="AlignSparklines"></a><span data-ttu-id="94dd4-213">4. allineare i grafici sparkline verticalmente e orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="94dd4-213">4. Align the Sparklines Vertically and Horizontally</span></span>  
 <span data-ttu-id="94dd4-214">I grafici sparkline sono difficili da leggere quando non utilizzano tutte le stesse misurazioni.</span><span class="sxs-lookup"><span data-stu-id="94dd4-214">The sparklines are hard to read when they don't all use the same measurements.</span></span> <span data-ttu-id="94dd4-215">È necessario che vi sia corrispondenza tra gli assi orizzontale e verticale di ognuno.</span><span class="sxs-lookup"><span data-stu-id="94dd4-215">Both the horizontal and vertical axes for each need to match the rest.</span></span>  
  
#### <a name="to-set-alignment-for-the-sparklines-in-the-table"></a><span data-ttu-id="94dd4-216">Per impostare l'allineamento per i grafici sparkline nella tabella</span><span class="sxs-lookup"><span data-stu-id="94dd4-216">To set alignment for the sparklines in the table</span></span>  
  
1.  <span data-ttu-id="94dd4-217">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="94dd4-217">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="94dd4-218">Fare clic con il pulsante destro del mouse sul grafico sparkline e scegliere **Proprietà asse verticale**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-218">Right-click the sparkline and click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="94dd4-219">Selezionare la casella di controllo **Allinea assi in** .</span><span class="sxs-lookup"><span data-stu-id="94dd4-219">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="94dd4-220">Nell'elenco viene visualizzato Tablix1.</span><span class="sxs-lookup"><span data-stu-id="94dd4-220">Tablix1 is showing in the list.</span></span> <span data-ttu-id="94dd4-221">Questa è l'unica opzione</span><span class="sxs-lookup"><span data-stu-id="94dd4-221">That is the only option.</span></span> <span data-ttu-id="94dd4-222">e consente di impostare l'altezza delle barre in ogni grafico sparkline rispetto alle altre.</span><span class="sxs-lookup"><span data-stu-id="94dd4-222">This sets the height of the bars in each sparkline relative to the others.</span></span>  
  
4.  <span data-ttu-id="94dd4-223">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="94dd4-224">Fare clic con il pulsante destro del mouse sul grafico sparkline e scegliere **Proprietà asse orizzontatale**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-224">Right-click the sparkline and click **Horizontal Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="94dd4-225">Selezionare la casella di controllo **Allinea assi in** .</span><span class="sxs-lookup"><span data-stu-id="94dd4-225">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="94dd4-226">Nell'elenco viene visualizzato Tablix1.</span><span class="sxs-lookup"><span data-stu-id="94dd4-226">Tablix1 is showing in the list.</span></span> <span data-ttu-id="94dd4-227">Questa è l'unica opzione</span><span class="sxs-lookup"><span data-stu-id="94dd4-227">That is the only option.</span></span> <span data-ttu-id="94dd4-228">e consente di impostare la larghezza delle barre in ogni grafico sparkline rispetto alle altre.</span><span class="sxs-lookup"><span data-stu-id="94dd4-228">This sets the width of the bars in each sparkline relative to the others.</span></span> <span data-ttu-id="94dd4-229">Se sono presenti grafici sparkline con un numero inferiore di barre, in tali grafici saranno contenuti spazi vuoti per i dati mancanti.</span><span class="sxs-lookup"><span data-stu-id="94dd4-229">If some sparklines have fewer bars than others, then those sparklines will have blank spaces for the missing data.</span></span>  
  
7.  <span data-ttu-id="94dd4-230">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-230">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="94dd4-231">Fare clic su **Esegui** per visualizzare l'anteprima del nuovo report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-231">Click **Run** to preview your report again.</span></span>  
  
 <span data-ttu-id="94dd4-232">Si noti che tutte le barre risultano ora allineate con le barre nelle altre righe.</span><span class="sxs-lookup"><span data-stu-id="94dd4-232">Note that all the bars are now aligned with the bars in the other rows.</span></span>  
  
##  <a name="5-optional-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="94dd4-233">5. (facoltativo) formattare i dati come valuta</span><span class="sxs-lookup"><span data-stu-id="94dd4-233">5. (Optional) Format Data as Currency</span></span>  
 <span data-ttu-id="94dd4-234">Per impostazione predefinita, i dati di riepilogo per il campo **Sales** visualizzano un numero generico.</span><span class="sxs-lookup"><span data-stu-id="94dd4-234">By default, the summary data for the **Sales** field displays a general number.</span></span> <span data-ttu-id="94dd4-235">È possibile formattare tale numero come valuta.</span><span class="sxs-lookup"><span data-stu-id="94dd4-235">Format it to display the number as currency.</span></span> <span data-ttu-id="94dd4-236">Attivare o disattivare **Stili segnaposto** per visualizzare caselle di testo formattate e testo segnaposto come valori di esempio.</span><span class="sxs-lookup"><span data-stu-id="94dd4-236">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="94dd4-237">Per formattare un campo di tipo valuta</span><span class="sxs-lookup"><span data-stu-id="94dd4-237">To format a currency field</span></span>  
  
1.  <span data-ttu-id="94dd4-238">Fare clic su **progettazione** per passare alla visualizzazione progettazione.</span><span class="sxs-lookup"><span data-stu-id="94dd4-238">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="94dd4-239">Fare clic sulla cella nella seconda riga (sotto la riga delle intestazioni di colonna) nella colonna **SalesDate** e trascinare per selezionare tutte le celle che contengono `[Sum(Sales)]` .</span><span class="sxs-lookup"><span data-stu-id="94dd4-239">Click the cell in the second row (under the column headings row) in the **SalesDate** column and drag to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="94dd4-240">Nel gruppo **Numero** della scheda **Home** fare clic sul pulsante **Valuta** .</span><span class="sxs-lookup"><span data-stu-id="94dd4-240">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="94dd4-241">Nelle celle i numeri vengono visualizzati nel formato di valuta.</span><span class="sxs-lookup"><span data-stu-id="94dd4-241">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="94dd4-242">Se la lingua delle impostazioni locali è Inglese (Stati Uniti), il testo di esempio predefinito sarà [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="94dd4-242">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="94dd4-243">Se non viene visualizzato un valore di valuta di esempio, fare clic su **Stili segnaposto** nel gruppo **numeri** , quindi fare clic su **valori di esempio**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-243">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="94dd4-244">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-244">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="94dd4-245">I valori di riepilogo per **Sales** vengono visualizzati come valuta.</span><span class="sxs-lookup"><span data-stu-id="94dd4-245">The summary values for **Sales** display as currency.</span></span>  
  
##  <a name="6-optional-format-data-as-dates"></a><a name="FormatDates"></a><span data-ttu-id="94dd4-246">6. (facoltativo) formattare i dati come date</span><span class="sxs-lookup"><span data-stu-id="94dd4-246">6. (Optional) Format Data as Dates</span></span>  
 <span data-ttu-id="94dd4-247">Per impostazione predefinita, il campo **SalesDate** Visualizza le informazioni su data e ora.</span><span class="sxs-lookup"><span data-stu-id="94dd4-247">By default, the **SalesDate** field displays both date and time information.</span></span> <span data-ttu-id="94dd4-248">È possibile formattare tale campo in modo da visualizzare solo la data.</span><span class="sxs-lookup"><span data-stu-id="94dd4-248">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="94dd4-249">Per formattare un campo relativo alla data utilizzando il formato predefinito</span><span class="sxs-lookup"><span data-stu-id="94dd4-249">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="94dd4-250">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="94dd4-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="94dd4-251">Fare clic sulla cella contenente `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="94dd4-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="94dd4-252">Sulla barra multifunzione, nella scheda **Home** , nel gruppo **numero** , selezionare **Data**nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="94dd4-252">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="94dd4-253">Nella cella viene visualizzata la data di esempio **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-253">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="94dd4-254">Se non viene visualizzata una data di esempio, fare clic su **Stili segnaposto** nel gruppo **Numeri** , quindi fare clic su **Valori di esempio**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-254">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="94dd4-255">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-255">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="94dd4-256">I valori **SalesDate** vengono visualizzati nel formato di data predefinito.</span><span class="sxs-lookup"><span data-stu-id="94dd4-256">The **SalesDate** values display in the default date format.</span></span>  
  
##  <a name="7-optional-change-column-widths"></a><a name="Width"></a><span data-ttu-id="94dd4-257">7. (facoltativo) modificare la larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="94dd4-257">7. (Optional) Change Column Widths</span></span>  
 <span data-ttu-id="94dd4-258">Per impostazione predefinita, in ogni cella della tabella è contenuta una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="94dd4-258">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="94dd4-259">Una casella di testo si espande verso il basso per adattarsi al testo digitato quando la pagina viene sottoposta al rendering.</span><span class="sxs-lookup"><span data-stu-id="94dd4-259">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="94dd4-260">Nel report visualizzabile, ogni riga si espande fino all'altezza della casella di testo visualizzabile più alta nella riga.</span><span class="sxs-lookup"><span data-stu-id="94dd4-260">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="94dd4-261">L'altezza della riga nell'area di progettazione non ha alcun effetto sull'altezza della riga nel report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="94dd4-261">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="94dd4-262">Per ridurre la quantità di spazio verticale di ciascuna riga, espandere la larghezza della colonna per adattare su un'unica riga il contenuto previsto delle caselle di testo nella colonna.</span><span class="sxs-lookup"><span data-stu-id="94dd4-262">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-columns"></a><span data-ttu-id="94dd4-263">Per modificare la larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="94dd4-263">To change the width of columns</span></span>  
  
1.  <span data-ttu-id="94dd4-264">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="94dd4-264">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="94dd4-265">Fare clic nella tabella in modo che vengano visualizzati gli handle di colonna e riga sopra e accanto alla tabella.</span><span class="sxs-lookup"><span data-stu-id="94dd4-265">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="94dd4-266">Le barre grigie lungo la parte superiore e laterale della tabella sono gli handle di riga e di colonna.</span><span class="sxs-lookup"><span data-stu-id="94dd4-266">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="94dd4-267">Posizionare il puntatore del mouse sulla riga tra gli handle di colonna in modo che il cursore assuma la forma di una doppia freccia.</span><span class="sxs-lookup"><span data-stu-id="94dd4-267">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="94dd4-268">Trascinare le colonne fino a ottenere le dimensioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="94dd4-268">Drag the columns to the size you want.</span></span> <span data-ttu-id="94dd4-269">Espandere, ad esempio, la colonna **Product** in modo da visualizzare il nome del prodotto su una riga.</span><span class="sxs-lookup"><span data-stu-id="94dd4-269">For example, expand the column for **Product** so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="94dd4-270">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-270">Click **Run** to preview your report.</span></span>  
  
##  <a name="8-optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="94dd4-271">8. (facoltativo) aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="94dd4-271">8. (Optional) Add a Report Title</span></span>  
 <span data-ttu-id="94dd4-272">Nella parte superiore del report viene visualizzato il titolo del report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-272">A report title appears at the top of the report.</span></span> <span data-ttu-id="94dd4-273">È possibile posizionare il titolo del report in un'apposita intestazione oppure, se ne è privo, in una casella di testo nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-273">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="94dd4-274">In questa esercitazione sarà utilizzata la casella di testo che viene posizionata automaticamente nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-274">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="94dd4-275">Il testo può essere ulteriormente migliorato applicando stili di carattere, dimensioni e colori diversi alle frasi e ai singoli caratteri del testo.</span><span class="sxs-lookup"><span data-stu-id="94dd4-275">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="94dd4-276">Per altre informazioni, vedere [Formattare il testo in una casella di testo &#40;Generatore report e SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="94dd4-276">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="94dd4-277">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="94dd4-277">To add a report title</span></span>  
  
1.  <span data-ttu-id="94dd4-278">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-278">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="94dd4-279">Digitare **Vendite prodotto**, quindi fare clic all'esterno della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="94dd4-279">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="94dd4-280">Fare clic con il pulsante destro del mouse sulla casella di testo che contiene **Vendite prodotto** , quindi fare clic su **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-280">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="94dd4-281">Nella finestra di dialogo **Proprietà casella di testo** fare clic su **Carattere**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-281">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="94dd4-282">Nell'elenco **Dimensione** selezionare **18pt**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-282">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="94dd4-283">Nell'elenco **colore** selezionare **Bordeaux**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-283">In the **Color** list, select **Maroon**.</span></span>  
  
7.  <span data-ttu-id="94dd4-284">Selezionare **Grassetto**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-284">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="94dd4-285">9. salvare il report</span><span class="sxs-lookup"><span data-stu-id="94dd4-285">9. Save the Report</span></span>  
 <span data-ttu-id="94dd4-286">Salvare il report in un server di report o nel computer.</span><span class="sxs-lookup"><span data-stu-id="94dd4-286">Save the report to a report server or your computer.</span></span> <span data-ttu-id="94dd4-287">Se il report non viene salvato nel server di report, non saranno disponibili alcune funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , ad esempio le parti del report e i sottoreport.</span><span class="sxs-lookup"><span data-stu-id="94dd4-287">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="94dd4-288">Per salvare il report in un server di report</span><span class="sxs-lookup"><span data-stu-id="94dd4-288">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="94dd4-289">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-289">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="94dd4-290">Fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-290">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="94dd4-291">Selezionare o digitare il nome del server di report per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-291">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="94dd4-292">Verrà visualizzato il messaggio "Connessione al server di report".</span><span class="sxs-lookup"><span data-stu-id="94dd4-292">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="94dd4-293">Al termine della connessione, verrà visualizzato il contenuto della cartella di report specificata dall'amministratore del server di report come posizione predefinita per i report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-293">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="94dd4-294">In **Nome**sostituire il nome predefinito con **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-294">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="94dd4-295">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-295">Click **Save**.</span></span>  
  
 <span data-ttu-id="94dd4-296">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-296">The report is saved to the report server.</span></span> <span data-ttu-id="94dd4-297">Il nome del server di report al quale si è connessi verrà visualizzato sulla barra di stato nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="94dd4-297">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="94dd4-298">Per salvare il report nel computer</span><span class="sxs-lookup"><span data-stu-id="94dd4-298">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="94dd4-299">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-299">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="94dd4-300">Fare clic su **Desktop**, **Documenti**o **Risorse del computer**e selezionare la cartella in cui si vuole salvare il report.</span><span class="sxs-lookup"><span data-stu-id="94dd4-300">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="94dd4-301">In **Nome**sostituire il nome predefinito con **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-301">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="94dd4-302">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94dd4-302">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="94dd4-303">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="94dd4-303">Next Steps</span></span>  
 <span data-ttu-id="94dd4-304">L'esercitazione sulla creazione di un report tabella con grafici sparkline è terminata.</span><span class="sxs-lookup"><span data-stu-id="94dd4-304">This concludes the tutorial for creating a table report with sparkline charts.</span></span> <span data-ttu-id="94dd4-305">Per altre informazioni, vedere [Grafici sparkline e barre dei dati &#40;Generatore report e SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="94dd4-305">For more information about sparklines, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94dd4-306">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94dd4-306">See Also</span></span>  
 <span data-ttu-id="94dd4-307">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="94dd4-307">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="94dd4-308">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="94dd4-308">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
