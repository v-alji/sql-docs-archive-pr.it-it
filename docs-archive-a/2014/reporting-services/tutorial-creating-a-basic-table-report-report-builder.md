---
title: 'Esercitazione: Creazione di un report tabella semplice (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d9e30521-f8ae-4c45-89c3-d40727f622f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3587e2a53e2b09dd347a2733875eafd708b8a05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625962"
---
# <a name="tutorial-creating-a-basic-table-report-report-builder"></a><span data-ttu-id="34037-102">Esercitazione: Creazione di un report tabella semplice (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="34037-102">Tutorial: Creating a Basic Table Report (Report Builder)</span></span>
  <span data-ttu-id="34037-103">In questa esercitazione viene illustrato come creare un report tabella semplice basato sui dati di vendita di esempio.</span><span class="sxs-lookup"><span data-stu-id="34037-103">This tutorial teaches you to create a basic table report based on sample sales data.</span></span> <span data-ttu-id="34037-104">Nell'illustrazione seguente viene mostrato il report che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="34037-104">The following illustration shows the report you will create.</span></span>  
  
 <span data-ttu-id="34037-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="34037-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="34037-106">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="34037-106">What You Will Learn</span></span>  
 <span data-ttu-id="34037-107">In questa esercitazione verranno illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="34037-107">In this tutorial, you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="34037-108">Creare un nuovo report dal Riquadro attività iniziale</span><span class="sxs-lookup"><span data-stu-id="34037-108">Create a New Report from Getting Started</span></span>](#CreateTable)  
  
    1.  [<span data-ttu-id="34037-109">Specificare una connessione dati in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-109">Specify a Data Connection in the Table Wizard</span></span>](#DataConnection)  
  
    2.  [<span data-ttu-id="34037-110">Creare una query in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-110">Create a Query in the Table Wizard</span></span>](#Query)  
  
    3.  [<span data-ttu-id="34037-111">Organizzare dati in gruppi in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-111">Organize Data into Groups in the Table Wizard</span></span>](#Groups)  
  
    4.  [<span data-ttu-id="34037-112">Aggiungere le righe Subtotale e Totale in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-112">Add Subtotal and Total Rows in the Table Wizard</span></span>](#Subtotals)  
  
    5.  [<span data-ttu-id="34037-113">Scegliere uno stile in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-113">Choose a Style in the Table Wizard</span></span>](#Style)  
  
2.  [<span data-ttu-id="34037-114">Formattare i dati come valuta</span><span class="sxs-lookup"><span data-stu-id="34037-114">Format Data as Currency</span></span>](#FormatCurrency)  
  
3.  [<span data-ttu-id="34037-115">Formattare i dati come data</span><span class="sxs-lookup"><span data-stu-id="34037-115">Format Data as Date</span></span>](#FormatDate)  
  
4.  [<span data-ttu-id="34037-116">Modificare la larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="34037-116">Change Column Widths</span></span>](#Width)  
  
5.  [<span data-ttu-id="34037-117">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="34037-117">Add a Report Title</span></span>](#Title)  
  
6.  [<span data-ttu-id="34037-118">Salva il report</span><span class="sxs-lookup"><span data-stu-id="34037-118">Save the Report</span></span>](#Save)  
  
7.  [<span data-ttu-id="34037-119">Esportare il report</span><span class="sxs-lookup"><span data-stu-id="34037-119">Export the Report</span></span>](#Export)  
  
 <span data-ttu-id="34037-120">Il tempo stimato per il completare l'esercitazione è di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="34037-120">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34037-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34037-121">Requirements</span></span>  
 <span data-ttu-id="34037-122">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="34037-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-new-report-from-getting-started"></a><a name="CreateTable"></a><span data-ttu-id="34037-123">1. creare un nuovo report da Introduzione</span><span class="sxs-lookup"><span data-stu-id="34037-123">1. Create a New Report from Getting Started</span></span>  
 <span data-ttu-id="34037-124">Creare un report tabella dalla finestra di dialogo **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="34037-124">Create a table report from the **Getting Started** dialog box.</span></span> <span data-ttu-id="34037-125">Sono disponibili due modalità: progettazione report e progettazione del set di dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="34037-125">There are two modes: report design and shared dataset design.</span></span> <span data-ttu-id="34037-126">Nella modalità progettazione report si specificano i dati nel riquadro dei dati del report e il layout del report nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="34037-126">In report design mode, you specify data in the Report Data pane and the report layout on the design surface.</span></span> <span data-ttu-id="34037-127">Nella modalità progettazione del set di dati condivisa, si creano query del set di dati da condividere con altri.</span><span class="sxs-lookup"><span data-stu-id="34037-127">In shared dataset design mode, you create dataset queries to share with others.</span></span> <span data-ttu-id="34037-128">In questa esercitazione si utilizzerà modalità progettazione report.</span><span class="sxs-lookup"><span data-stu-id="34037-128">In this tutorial, you will be using report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="34037-129">Per creare un nuovo report</span><span class="sxs-lookup"><span data-stu-id="34037-129">To create a new report</span></span>  
  
1.  <span data-ttu-id="34037-130">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="34037-130">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="34037-131">Verrà visualizzata la finestra di dialogo **Attività iniziali**.</span><span class="sxs-lookup"><span data-stu-id="34037-131">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34037-132">Se la finestra di dialogo **Introduzione** non viene visualizzata, dal pulsante **Generatore report** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="34037-132">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="34037-133">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="34037-133">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="34037-134">Nel riquadro destro verificare che sia selezionata **Creazione guidata tabella o matrice** .</span><span class="sxs-lookup"><span data-stu-id="34037-134">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection-in-the-table-wizard"></a><a name="DataConnection"></a><span data-ttu-id="34037-135">1a.</span><span class="sxs-lookup"><span data-stu-id="34037-135">1a.</span></span> <span data-ttu-id="34037-136">Specificare una connessione dati in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-136">Specify a Data Connection in the Table Wizard</span></span>  
 <span data-ttu-id="34037-137">Una connessione dati contiene le informazioni necessarie per connettersi a un'origine dati esterna, ad esempio un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34037-137">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="34037-138">In genere, le informazioni di connessione e il tipo di credenziali da utilizzare vengono fornite dal proprietario dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="34037-138">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span> <span data-ttu-id="34037-139">Per specificare una connessione dati, è possibile utilizzare un'origine dati condivisa dal server di report o creare un'origine dati incorporata che sia utilizzata solo in questo report.</span><span class="sxs-lookup"><span data-stu-id="34037-139">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span>  
  
 <span data-ttu-id="34037-140">In questa esercitazione si utilizzerà un'origine dati incorporata.</span><span class="sxs-lookup"><span data-stu-id="34037-140">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="34037-141">Per altre informazioni sull'uso di un'origine dati condivisa, vedere [Modalità alternative di acquisizione di una connessione dati &#40;Generatore report&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="34037-141">To learn more about using a shared data sources, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="34037-142">Per creare un'origine dati incorporata</span><span class="sxs-lookup"><span data-stu-id="34037-142">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="34037-143">Nella pagina **Scegliere un set di dati** selezionare **Crea un set di dati**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="34037-143">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="34037-144">Verrà visualizzata la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="34037-144">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="34037-145">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="34037-145">Click **New**.</span></span> <span data-ttu-id="34037-146">Verrà visualizzata la finestra di dialogo **Proprietà origine dati** .</span><span class="sxs-lookup"><span data-stu-id="34037-146">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="34037-147">In **nome**digitare **vendite prodotto** un nome per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="34037-147">In **Name**, type **Product Sales** a name for the data source.</span></span>  
  
4.  <span data-ttu-id="34037-148">In **Select a connection type**(Seleziona un tipo di connessione), verificare che sia selezionato **Microsoft SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="34037-148">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
5.  <span data-ttu-id="34037-149">In **stringa di connessione**Digitare il testo seguente, dove *\<servername>* è il nome di un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="34037-149">In **Connection string**, type the following text, where *\<servername>* is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
    ```  
    Data Source=<servername>  
    ```  
  
     <span data-ttu-id="34037-150">Poiché verrà utilizzata una query che contiene i dati anziché recuperarli da un database, la stringa di connessione non include il nome del database.</span><span class="sxs-lookup"><span data-stu-id="34037-150">Because you will use a query that contains the data instead of retrieving the data from a database, the connection string does not include the database name.</span></span> <span data-ttu-id="34037-151">Per altre informazioni, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="34037-151">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
6.  <span data-ttu-id="34037-152">Fare clic su **Credenziali**.</span><span class="sxs-lookup"><span data-stu-id="34037-152">Click **Credentials**.</span></span> <span data-ttu-id="34037-153">Immettere le credenziali necessarie per accedere all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="34037-153">Enter the credentials that you need to access the external data source.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="34037-154">Verrà visualizzata di nuovo la pagina **Scegliere una connessione a un'origine dei dati** .</span><span class="sxs-lookup"><span data-stu-id="34037-154">You are back on the **Choose a connection to a data source** page.</span></span>  
  
8.  <span data-ttu-id="34037-155">Per verificare che la connessione all'origine dati avvenga correttamente, fare clic su **Test connessione**.</span><span class="sxs-lookup"><span data-stu-id="34037-155">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="34037-156">Verrà visualizzato il messaggio "Creazione connessione completata".</span><span class="sxs-lookup"><span data-stu-id="34037-156">The message "Connection created successfully" appears.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="34037-157">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="34037-157">Click **Next**.</span></span>  
  
##  <a name="1b-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="34037-158">1b.</span><span class="sxs-lookup"><span data-stu-id="34037-158">1b.</span></span> <span data-ttu-id="34037-159">Creare una query in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-159">Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="34037-160">In un report, è possibile utilizzare un set di dati condiviso che dispone di una query predefinita oppure è possibile creare un set di dati incorporato da utilizzare solo nel report.</span><span class="sxs-lookup"><span data-stu-id="34037-160">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="34037-161">In questa esercitazione si creerà un set di dati incorporato.</span><span class="sxs-lookup"><span data-stu-id="34037-161">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34037-162">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="34037-162">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="34037-163">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="34037-163">This makes the query quite long.</span></span> <span data-ttu-id="34037-164">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="34037-164">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="34037-165">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="34037-165">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="34037-166">Per creare una query</span><span class="sxs-lookup"><span data-stu-id="34037-166">To create a query</span></span>  
  
1.  <span data-ttu-id="34037-167">Nella pagina **Progetta query** si apre la finestra Progettazione query relazionale.</span><span class="sxs-lookup"><span data-stu-id="34037-167">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="34037-168">Per questa esercitazione si utilizzerà la finestra Progettazione query basata su testo.</span><span class="sxs-lookup"><span data-stu-id="34037-168">For this tutorial, you will use the text-based query designer.</span></span>  
  
     <span data-ttu-id="34037-169">Fare clic su **modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="34037-169">Click **Edit As Text**.</span></span> <span data-ttu-id="34037-170">Nella finestra Progettazione query basata su testo viene visualizzato il riquadro della query e il riquadro dei risultati.</span><span class="sxs-lookup"><span data-stu-id="34037-170">The text-based query designer displays a query pane and a results pane.</span></span>  
  
2.  <span data-ttu-id="34037-171">Nella casella [!INCLUDE[tsql](../includes/tsql-md.md)] Query **incollare la query** seguente.</span><span class="sxs-lookup"><span data-stu-id="34037-171">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(9924.60 AS money) AS Sales, 68 as Quantity  
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
  
3.  <span data-ttu-id="34037-172">Sulla barra degli strumenti Progettazione query fare clic su **Esegui** (**!**).</span><span class="sxs-lookup"><span data-stu-id="34037-172">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="34037-173">La query viene eseguita e viene visualizzato il set di risultati per il campi SalesDate, Subcategory, Product, Sales e Quantity.</span><span class="sxs-lookup"><span data-stu-id="34037-173">The query runs and displays the result set for the fields SalesDate, Subcategory, Product, Sales, and Quantity.</span></span>  
  
     <span data-ttu-id="34037-174">Nel set di risultati le intestazioni di colonna sono basate sui nomi nella query.</span><span class="sxs-lookup"><span data-stu-id="34037-174">In the result set, the column headings are based on the names in the query.</span></span> <span data-ttu-id="34037-175">Nel set di dati, le intestazioni di colonna diventano i nomi dei campi e vengono salvate nel report.</span><span class="sxs-lookup"><span data-stu-id="34037-175">In the dataset, the column headings become the field names, and are saved in the report.</span></span> <span data-ttu-id="34037-176">Al termine della procedura guidata, è possibile utilizzare il riquadro dei dati del report per esaminare la raccolta dei campi del set di dati.</span><span class="sxs-lookup"><span data-stu-id="34037-176">After you complete the wizard, you can use the Report Data pane to view the collection of dataset fields.</span></span>  
  
4.  <span data-ttu-id="34037-177">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="34037-177">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups-in-the-table-wizard"></a><a name="Groups"></a><span data-ttu-id="34037-178">1C.</span><span class="sxs-lookup"><span data-stu-id="34037-178">1c.</span></span> <span data-ttu-id="34037-179">Organizzare dati in gruppi in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-179">Organize Data into Groups in the Table Wizard</span></span>  
 <span data-ttu-id="34037-180">Quando si selezionano dei campi da raggruppare, si progetta una tabella con righe e colonne che visualizzano dati dettagliati e dati aggregati.</span><span class="sxs-lookup"><span data-stu-id="34037-180">When you select fields to group on, you design a table that has rows and columns that display detail data and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="34037-181">Per organizzare i dati in gruppi</span><span class="sxs-lookup"><span data-stu-id="34037-181">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="34037-182">Nella pagina **Disponi campi** trascinare Product in **valori**.</span><span class="sxs-lookup"><span data-stu-id="34037-182">On the **Arrange fields** page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="34037-183">Trascinare Quantity in **Valori** e posizionarlo sotto Product.</span><span class="sxs-lookup"><span data-stu-id="34037-183">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="34037-184">Quantity viene aggregata automaticamente dalla funzione Sum, l'aggregazione predefinita per i campi numerici.</span><span class="sxs-lookup"><span data-stu-id="34037-184">Quantity is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="34037-185">Il valore è [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="34037-185">The value is [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="34037-186">È possibile aprire l'elenco a discesa per visualizzare le altre funzioni di aggregazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="34037-186">You can open the drop-down list to view the other aggregate functions available.</span></span> <span data-ttu-id="34037-187">Non modificare la funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="34037-187">Do not change the aggregate function.</span></span>  
  
3.  <span data-ttu-id="34037-188">Trascinare Sales in **Valori** e posizionarlo sotto [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="34037-188">Drag Sales to **Values** and place below [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="34037-189">Il campo Sales viene aggregato mediante la funzione Sum.</span><span class="sxs-lookup"><span data-stu-id="34037-189">Sales is aggregated by the Sum function.</span></span> <span data-ttu-id="34037-190">Il valore è [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="34037-190">The value is [Sum(Sales)].</span></span>  
  
     <span data-ttu-id="34037-191">Nei passaggi 1, 2 e 3 sono specificati i dati da visualizzare nella tabella.</span><span class="sxs-lookup"><span data-stu-id="34037-191">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="34037-192">Trascinare SalesDate in **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="34037-192">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="34037-193">Trascinare Subcategory in **Gruppi di righe** e posizionarlo sotto SalesDate.</span><span class="sxs-lookup"><span data-stu-id="34037-193">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="34037-194">I passaggi 4 e 5 consentono di organizzare i valori per i campi prima in base alla data, quindi in base alla sottocategoria del prodotto per quella data.</span><span class="sxs-lookup"><span data-stu-id="34037-194">Steps 4 and 5 organize the values for the fields first by date, and then by product subcategory for that date.</span></span>  
  
6.  <span data-ttu-id="34037-195">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="34037-195">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotal-and-total-rows-in-the-table-wizard"></a><a name="Subtotals"></a><span data-ttu-id="34037-196">1D.</span><span class="sxs-lookup"><span data-stu-id="34037-196">1d.</span></span> <span data-ttu-id="34037-197">Aggiungere le righe Subtotale e Totale in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-197">Add Subtotal and Total Rows in the Table Wizard</span></span>  
 <span data-ttu-id="34037-198">Dopo avere creato dei gruppi, è possibile aggiungere e formattare delle righe nelle quali visualizzare valori di aggregazione per i campi.</span><span class="sxs-lookup"><span data-stu-id="34037-198">After you create groups, you can add and format rows on which to display aggregate values for the fields.</span></span> <span data-ttu-id="34037-199">È possibile scegliere se mostrare tutti i dati o lasciare che sia l'utente a espandere e comprimere in modo interattivo i dati raggruppati.</span><span class="sxs-lookup"><span data-stu-id="34037-199">You can choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="34037-200">Per aggiungere subtotali e totali</span><span class="sxs-lookup"><span data-stu-id="34037-200">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="34037-201">Nella pagina **scegliere il layout** , in **Opzioni**, verificare che sia selezionata l'opzione **Mostra subtotali e totali** complessivi.</span><span class="sxs-lookup"><span data-stu-id="34037-201">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
2.  <span data-ttu-id="34037-202">Verificare che l'opzione **Bloccato, subtotale sotto** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="34037-202">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
     <span data-ttu-id="34037-203">Nel riquadro di anteprima della creazione guidata viene visualizzata una tabella con cinque righe.</span><span class="sxs-lookup"><span data-stu-id="34037-203">The wizard Preview pane displays a table with five rows.</span></span> <span data-ttu-id="34037-204">Quando si esegue il report, ogni riga viene visualizzata nel seguente modo:</span><span class="sxs-lookup"><span data-stu-id="34037-204">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="34037-205">La prima riga si ripete una volta per la tabella per mostrare le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="34037-205">The first row will repeat once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="34037-206">La seconda riga si ripete una volta per ogni voce nell'ordine di vendita e contiene il nome di prodotto, la quantità dell'ordine e il totale della riga.</span><span class="sxs-lookup"><span data-stu-id="34037-206">The second row will repeat once for each line item in the sales order and display the product name, order quantity, and line total.</span></span>  
  
    3.  <span data-ttu-id="34037-207">La terza riga si ripete una volta per ogni ordine di vendita per visualizzare i subtotali di ciascun ordine.</span><span class="sxs-lookup"><span data-stu-id="34037-207">The third row will repeat once for each sales order to display subtotals per order.</span></span>  
  
    4.  <span data-ttu-id="34037-208">La quarta riga si ripete una volta per ogni data dell'ordine per visualizzare i subtotali di ciascun giorno.</span><span class="sxs-lookup"><span data-stu-id="34037-208">The fourth row will repeat once for each order date to display the subtotals per day.</span></span>  
  
    5.  <span data-ttu-id="34037-209">La quinta riga si ripete una volta per la tabella per visualizzare i totali complessivi.</span><span class="sxs-lookup"><span data-stu-id="34037-209">The fifth row will repeat once for the table to display the grand totals.</span></span>  
  
3.  <span data-ttu-id="34037-210">Deselezionare l'opzione **Espandi/comprimi gruppi**.</span><span class="sxs-lookup"><span data-stu-id="34037-210">Clear the option **Expand/collapse groups**.</span></span> <span data-ttu-id="34037-211">Nel report creato in questa esercitazione non viene utilizzata la funzionalità drill-down che consente all'utente di espandere una gerarchia di gruppo padre per visualizzare le righe del gruppo figlio e le righe di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="34037-211">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
4.  <span data-ttu-id="34037-212">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="34037-212">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style-in-the-table-wizard"></a><a name="Style"></a><span data-ttu-id="34037-213">1e.</span><span class="sxs-lookup"><span data-stu-id="34037-213">1e.</span></span> <span data-ttu-id="34037-214">Scegliere uno stile in Creazione guidata tabella</span><span class="sxs-lookup"><span data-stu-id="34037-214">Choose a Style in the Table Wizard</span></span>  
 <span data-ttu-id="34037-215">Uno stile specifica lo stile del carattere, il set di colori e uno stile del bordo.</span><span class="sxs-lookup"><span data-stu-id="34037-215">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-table-style"></a><span data-ttu-id="34037-216">Per specificare uno stile della tabella</span><span class="sxs-lookup"><span data-stu-id="34037-216">To specify a table style</span></span>  
  
1.  <span data-ttu-id="34037-217">Nella pagina **scegliere uno stile** , nel riquadro Stili, selezionare oceano.</span><span class="sxs-lookup"><span data-stu-id="34037-217">On the **Choose a Style** page, in the Styles pane, select Ocean.</span></span>  
  
     <span data-ttu-id="34037-218">Nel riquadro di anteprima viene visualizzato un esempio della tabella con lo stile selezionato.</span><span class="sxs-lookup"><span data-stu-id="34037-218">The Preview pane displays a sample of the table with that style.</span></span>  
  
2.  <span data-ttu-id="34037-219">Facoltativamente, fare clic sugli altri stili per vederli applicati all'esempio.</span><span class="sxs-lookup"><span data-stu-id="34037-219">Optionally, click the other styles to see the sample with them applied.</span></span>  
  
3.  <span data-ttu-id="34037-220">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="34037-220">Click **Finish**.</span></span>  
  
 <span data-ttu-id="34037-221">La tabella viene aggiunta all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="34037-221">The table is added to the design surface.</span></span> <span data-ttu-id="34037-222">La tabella dispone di 5 colonne e 5 righe.</span><span class="sxs-lookup"><span data-stu-id="34037-222">The table has 5 columns and 5 rows.</span></span> <span data-ttu-id="34037-223">Nel riquadro Gruppi di righe sono visualizzati tre gruppi di righe: SalesDate, Subcategory e Details.</span><span class="sxs-lookup"><span data-stu-id="34037-223">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="34037-224">I dati dettaglio costituiscono tutti i dati recuperati dalla query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="34037-224">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="34037-225">2. formattare i dati come valuta</span><span class="sxs-lookup"><span data-stu-id="34037-225">2. Format Data as Currency</span></span>  
 <span data-ttu-id="34037-226">Per impostazione predefinita, i dati di riepilogo del campo Sales riportano un numero generico.</span><span class="sxs-lookup"><span data-stu-id="34037-226">By default, the summary data for the Sales field displays a general number.</span></span> <span data-ttu-id="34037-227">È possibile formattare tale numero come valuta.</span><span class="sxs-lookup"><span data-stu-id="34037-227">Format it to display the number as currency.</span></span> <span data-ttu-id="34037-228">Attivare o disattivare **Stili segnaposto** per visualizzare caselle di testo formattate e testo segnaposto come valori di esempio.</span><span class="sxs-lookup"><span data-stu-id="34037-228">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="34037-229">Per formattare un campo di tipo valuta</span><span class="sxs-lookup"><span data-stu-id="34037-229">To format a currency field</span></span>  
  
1.  <span data-ttu-id="34037-230">Fare clic su **progettazione** per passare alla visualizzazione progettazione.</span><span class="sxs-lookup"><span data-stu-id="34037-230">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="34037-231">Fare clic sulla cella nella seconda riga (sotto la riga delle intestazioni di colonna) della colonna Sales e trascinare verso il basso per selezionare tutte le celle che contengono `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="34037-231">Click the cell in the second row (under the column headings row) in the Sales column and drag down to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="34037-232">Nel gruppo **Numero** della scheda **Home** fare clic sul pulsante **Valuta** .</span><span class="sxs-lookup"><span data-stu-id="34037-232">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="34037-233">Nelle celle i numeri vengono visualizzati nel formato di valuta.</span><span class="sxs-lookup"><span data-stu-id="34037-233">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="34037-234">Se la lingua delle impostazioni locali è Inglese (Stati Uniti), il testo di esempio predefinito sarà [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="34037-234">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="34037-235">Se non viene visualizzato un valore di valuta di esempio, fare clic su **Stili segnaposto** nel gruppo **numeri** , quindi fare clic su **valori di esempio**.</span><span class="sxs-lookup"><span data-stu-id="34037-235">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="34037-236">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="34037-236">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="34037-237">I valori di riepilogo per Sales vengono visualizzati come valuta.</span><span class="sxs-lookup"><span data-stu-id="34037-237">The summary values for Sales display as currency.</span></span>  
  
##  <a name="3-format-data-as-date"></a><a name="FormatDate"></a><span data-ttu-id="34037-238">3. formattare i dati come data</span><span class="sxs-lookup"><span data-stu-id="34037-238">3. Format Data as Date</span></span>  
 <span data-ttu-id="34037-239">Per impostazione predefinita, nel campo SalesDate vengono visualizzate sia la data che l'ora.</span><span class="sxs-lookup"><span data-stu-id="34037-239">By default, the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="34037-240">È possibile formattare tale campo in modo da visualizzare solo la data.</span><span class="sxs-lookup"><span data-stu-id="34037-240">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="34037-241">Per formattare un campo relativo alla data utilizzando il formato predefinito</span><span class="sxs-lookup"><span data-stu-id="34037-241">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="34037-242">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="34037-242">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="34037-243">Fare clic sulla cella contenente `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="34037-243">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="34037-244">Sulla barra multifunzione, nella scheda **Home** , nel gruppo **numero** , selezionare **Data**nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="34037-244">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="34037-245">Nella cella viene visualizzata la data di esempio **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="34037-245">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="34037-246">Se non viene visualizzata una data di esempio, fare clic su **Stili segnaposto** nel gruppo **Numeri** , quindi fare clic su **Valori di esempio**.</span><span class="sxs-lookup"><span data-stu-id="34037-246">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="34037-247">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="34037-247">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="34037-248">I valori SalesDate vengono visualizzati nel formato di data predefinito.</span><span class="sxs-lookup"><span data-stu-id="34037-248">The SalesDate values display in the default date format.</span></span>  
  
#### <a name="to-change-the-date-format-to-a-custom-format"></a><span data-ttu-id="34037-249">Per modificare il formato della data in un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="34037-249">To change the date format to a custom format</span></span>  
  
1.  <span data-ttu-id="34037-250">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="34037-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="34037-251">Fare clic sulla cella contenente `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="34037-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="34037-252">Nel gruppo **numero** della scheda **Home** fare clic sul pulsante di avvio della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="34037-252">On the **Home** tab, in the **Number** group, click the dialog box launcher.</span></span>  
  
     <span data-ttu-id="34037-253">Il pulsante di avvio è la piccola freccia visualizzata nell'angolo a destra del gruppo.</span><span class="sxs-lookup"><span data-stu-id="34037-253">The launcher is the small arrow in the right-hand corner of the group.</span></span> <span data-ttu-id="34037-254">Viene aperta la finestra di dialogo **Proprietà casella di testo** .</span><span class="sxs-lookup"><span data-stu-id="34037-254">The **Text Box Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="34037-255">Nel riquadro Categoria verificare che sia selezionata l'opzione **Data** .</span><span class="sxs-lookup"><span data-stu-id="34037-255">In the Category pane, verify that **Date** is selected.</span></span>  
  
5.  <span data-ttu-id="34037-256">Nel riquadro **Tipo** selezionare **31 gennaio 2000**.</span><span class="sxs-lookup"><span data-stu-id="34037-256">In the **Type** pane, select **January 31, 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="34037-257">Nella cella viene visualizzata la data di esempio **[31 gennaio 2000]**.</span><span class="sxs-lookup"><span data-stu-id="34037-257">The cell displays the example date **[January 31, 2000]**.</span></span>  
  
7.  <span data-ttu-id="34037-258">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="34037-258">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="34037-259">Il valore SalesDate viene visualizzato con il nome anziché il numero del mese.</span><span class="sxs-lookup"><span data-stu-id="34037-259">The SalesDate value displays with the name of the month instead of the number for the month.</span></span>  
  
##  <a name="4-change-column-widths"></a><a name="Width"></a><span data-ttu-id="34037-260">4. modificare la larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="34037-260">4. Change Column Widths</span></span>  
 <span data-ttu-id="34037-261">Per impostazione predefinita, in ogni cella della tabella è contenuta una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="34037-261">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="34037-262">Una casella di testo si espande verso il basso per adattarsi al testo digitato quando la pagina viene sottoposta al rendering.</span><span class="sxs-lookup"><span data-stu-id="34037-262">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="34037-263">Nel report visualizzabile, ogni riga si espande fino all'altezza della casella di testo visualizzabile più alta nella riga.</span><span class="sxs-lookup"><span data-stu-id="34037-263">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="34037-264">L'altezza della riga nell'area di progettazione non ha alcun effetto sull'altezza della riga nel report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="34037-264">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="34037-265">Per ridurre la quantità di spazio verticale di ciascuna riga, espandere la larghezza della colonna per adattare su un'unica riga il contenuto previsto delle caselle di testo nella colonna.</span><span class="sxs-lookup"><span data-stu-id="34037-265">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-table-columns"></a><span data-ttu-id="34037-266">Per modificare la larghezza delle colonne della tabella</span><span class="sxs-lookup"><span data-stu-id="34037-266">To change the width of table columns</span></span>  
  
1.  <span data-ttu-id="34037-267">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="34037-267">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="34037-268">Fare clic nella tabella in modo che vengano visualizzati gli handle di colonna e riga sopra e accanto alla tabella.</span><span class="sxs-lookup"><span data-stu-id="34037-268">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="34037-269">Le barre grigie lungo la parte superiore e laterale della tabella sono gli handle di riga e di colonna.</span><span class="sxs-lookup"><span data-stu-id="34037-269">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="34037-270">Posizionare il puntatore del mouse sulla riga tra gli handle di colonna in modo che il cursore assuma la forma di una doppia freccia.</span><span class="sxs-lookup"><span data-stu-id="34037-270">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="34037-271">Trascinare le colonne fino a ottenere le dimensioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="34037-271">Drag the columns to the size you want.</span></span> <span data-ttu-id="34037-272">Espandere, ad esempio, la colonna Prodotto in modo da visualizzare il nome di prodotto su una riga.</span><span class="sxs-lookup"><span data-stu-id="34037-272">For example, expand the column for Product so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="34037-273">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="34037-273">Click **Run** to preview your report.</span></span>  
  
##  <a name="5-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="34037-274">5. aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="34037-274">5. Add a Report Title</span></span>  
 <span data-ttu-id="34037-275">Nella parte superiore del report viene visualizzato il titolo del report.</span><span class="sxs-lookup"><span data-stu-id="34037-275">A report title appears at the top of the report.</span></span> <span data-ttu-id="34037-276">È possibile posizionare il titolo del report in un'apposita intestazione oppure, se ne è privo, in una casella di testo nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="34037-276">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="34037-277">In questa esercitazione sarà utilizzata la casella di testo che viene posizionata automaticamente nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="34037-277">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="34037-278">Il testo può essere ulteriormente migliorato applicando stili di carattere, dimensioni e colori diversi alle frasi e ai singoli caratteri del testo.</span><span class="sxs-lookup"><span data-stu-id="34037-278">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="34037-279">Per altre informazioni, vedere [Formattare il testo in una casella di testo &#40;Generatore report e SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34037-279">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="34037-280">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="34037-280">To add a report title</span></span>  
  
1.  <span data-ttu-id="34037-281">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="34037-281">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="34037-282">Digitare **Vendite prodotto**, quindi fare clic all'esterno della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="34037-282">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="34037-283">Fare clic con il pulsante destro del mouse sulla casella di testo che contiene **Vendite prodotto** , quindi fare clic su **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="34037-283">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="34037-284">Nella finestra di dialogo **Proprietà casella di testo** fare clic su **Carattere**.</span><span class="sxs-lookup"><span data-stu-id="34037-284">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="34037-285">Nell'elenco **Dimensione** selezionare **18pt**.</span><span class="sxs-lookup"><span data-stu-id="34037-285">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="34037-286">Nell'elenco **Colore** selezionare **Blu fiordaliso**.</span><span class="sxs-lookup"><span data-stu-id="34037-286">In the **Color** list, select **Cornflower Blue**.</span></span>  
  
7.  <span data-ttu-id="34037-287">Selezionare **Grassetto**.</span><span class="sxs-lookup"><span data-stu-id="34037-287">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report"></a><a name="Save"></a><span data-ttu-id="34037-288">6. salvare il report</span><span class="sxs-lookup"><span data-stu-id="34037-288">6. Save the Report</span></span>  
 <span data-ttu-id="34037-289">Salvare il report in un server di report o nel computer.</span><span class="sxs-lookup"><span data-stu-id="34037-289">Save the report to a report server or your computer.</span></span> <span data-ttu-id="34037-290">Se il report non viene salvato nel server di report, non saranno disponibili alcune funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , ad esempio le parti del report e i sottoreport.</span><span class="sxs-lookup"><span data-stu-id="34037-290">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="34037-291">Per salvare il report in un server di report</span><span class="sxs-lookup"><span data-stu-id="34037-291">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="34037-292">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="34037-292">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="34037-293">Fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="34037-293">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="34037-294">Selezionare o digitare il nome del server di report per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="34037-294">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="34037-295">Verrà visualizzato il messaggio "Connessione al server di report".</span><span class="sxs-lookup"><span data-stu-id="34037-295">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="34037-296">Al termine della connessione, verrà visualizzato il contenuto della cartella di report specificata dall'amministratore del server di report come posizione predefinita per i report.</span><span class="sxs-lookup"><span data-stu-id="34037-296">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="34037-297">In **Nome**sostituire il nome predefinito con **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="34037-297">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="34037-298">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="34037-298">Click **Save**.</span></span>  
  
 <span data-ttu-id="34037-299">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="34037-299">The report is saved to the report server.</span></span> <span data-ttu-id="34037-300">Il nome del server di report al quale si è connessi verrà visualizzato sulla barra di stato nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="34037-300">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="34037-301">Per salvare il report nel computer</span><span class="sxs-lookup"><span data-stu-id="34037-301">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="34037-302">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="34037-302">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="34037-303">Fare clic su **Desktop**, **Documenti**o **Risorse del computer**e selezionare la cartella in cui si vuole salvare il report.</span><span class="sxs-lookup"><span data-stu-id="34037-303">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="34037-304">In **Nome**sostituire il nome predefinito con **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="34037-304">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="34037-305">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="34037-305">Click **Save**.</span></span>  
  
##  <a name="7-export-the-report"></a><a name="Export"></a><span data-ttu-id="34037-306">7. esportare il report</span><span class="sxs-lookup"><span data-stu-id="34037-306">7. Export the Report</span></span>  
 <span data-ttu-id="34037-307">I report possono essere esportati in formati differenti quali Microsoft Excel e CSV.</span><span class="sxs-lookup"><span data-stu-id="34037-307">Reports can be exported to different formats such Microsoft Excel and comma separated value (CSV).</span></span> <span data-ttu-id="34037-308">Per ulteriori informazioni, vedere [esportazione di report &#40;Generatore report e SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34037-308">For more information, see [Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="34037-309">In questa esercitazione, si esporterà il report in Excel e si imposterà una proprietà nel report per fornire un nome personalizzato per la scheda della cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="34037-309">In this tutorial, you will export the report to Excel and set a property on the report to provide a custom name for the workbook tab.</span></span>  
  
#### <a name="to-specify-the-workbook-tab-name"></a><span data-ttu-id="34037-310">Per specificare il nome della scheda della cartella di lavoro</span><span class="sxs-lookup"><span data-stu-id="34037-310">To specify the workbook tab name</span></span>  
  
1.  <span data-ttu-id="34037-311">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="34037-311">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="34037-312">Fare clic in un punto qualsiasi all'esterno del report.</span><span class="sxs-lookup"><span data-stu-id="34037-312">Click anywhere outside the report.</span></span>  
  
3.  <span data-ttu-id="34037-313">. Nel riquadro Proprietà individuare la proprietà InitialPageName e digitare **vendite prodotto Excel**.</span><span class="sxs-lookup"><span data-stu-id="34037-313">.In the Properties pane, locate the InitialPageName property and type **Product Sales Excel**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34037-314">Se il riquadro proprietà non è visibile, fare clic sulla scheda Visualizza sulla barra multifunzione, quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="34037-314">If the Properties pane is not visible, click the View tab on the ribbon, and then click **Properties**.</span></span>  
  
#### <a name="to-export-a-report-to-excel"></a><span data-ttu-id="34037-315">Per esportare un report in Excel</span><span class="sxs-lookup"><span data-stu-id="34037-315">To export a report to Excel</span></span>  
  
1.  <span data-ttu-id="34037-316">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="34037-316">Click **Run** to preview the report.</span></span>  
  
2.  <span data-ttu-id="34037-317">. Sulla barra multifunzione fare clic su **Esporta**, quindi su **Excel**.</span><span class="sxs-lookup"><span data-stu-id="34037-317">.On the ribbon, click **Export**, and then click **Excel**.</span></span>  
  
     <span data-ttu-id="34037-318">Verrà aperta la finestra di dialogo **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="34037-318">The **Save As** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="34037-319">Passare alla cartella **documenti** .</span><span class="sxs-lookup"><span data-stu-id="34037-319">Browse to the **Documents** folder.</span></span>  
  
4.  <span data-ttu-id="34037-320">Nella casella di testo **nome file** digitare **vendite prodotto Excel**.</span><span class="sxs-lookup"><span data-stu-id="34037-320">In the **File name** text box, type **Product Sales Excel**.</span></span>  
  
5.  <span data-ttu-id="34037-321">Verificare che il tipo di file sia **cartella di lavoro di Excel**.</span><span class="sxs-lookup"><span data-stu-id="34037-321">Verify that the file type is **Excel Workbook**.</span></span>  
  
6.  <span data-ttu-id="34037-322">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="34037-322">Click **Save**.</span></span>  
  
#### <a name="to-view-the-report-in-excel"></a><span data-ttu-id="34037-323">Per visualizzare il report in Excel</span><span class="sxs-lookup"><span data-stu-id="34037-323">To view the report in Excel</span></span>  
  
1.  <span data-ttu-id="34037-324">Aprire la cartella **documenti** e fare doppio clic su **vendite prodotto Excel.xlsx**.</span><span class="sxs-lookup"><span data-stu-id="34037-324">Open the **Documents** folder and double click **Product Sales Excel.xlsx**.</span></span>  
  
2.  <span data-ttu-id="34037-325">Verificare che il nome della scheda della cartella di lavoro sia **Vendite prodotto Excel**.</span><span class="sxs-lookup"><span data-stu-id="34037-325">Verify that the name of the workbook tab is **Product Sales Excel**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="34037-326">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="34037-326">Next Steps</span></span>  
 <span data-ttu-id="34037-327">La procedura dettagliata per la creazione di un report tabella semplice è terminata.</span><span class="sxs-lookup"><span data-stu-id="34037-327">This concludes the walkthrough for how to create a basic table report.</span></span> <span data-ttu-id="34037-328">Per altre informazioni sulle tabelle, vedere [Tabelle, matrici ed elenchi &#40;Generatore report e SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="34037-328">For more information about tables, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34037-329">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34037-329">See Also</span></span>  
 <span data-ttu-id="34037-330">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="34037-330">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="34037-331">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="34037-331">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
