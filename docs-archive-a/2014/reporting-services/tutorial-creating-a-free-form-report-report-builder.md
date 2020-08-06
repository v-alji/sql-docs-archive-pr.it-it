---
title: 'Esercitazione: Creazione di un report in formato libero (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 87288b59-faf2-4b1d-a8e4-a7582baedf2f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 515b0d2566efa4e11216a28648338c7ec43f3950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722455"
---
# <a name="tutorial-creating-a-free-form-report-report-builder"></a><span data-ttu-id="b6b98-102">Esercitazione: Creazione di un report in formato libero (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="b6b98-102">Tutorial: Creating a Free Form Report (Report Builder)</span></span>
  <span data-ttu-id="b6b98-103">In questa esercitazione viene illustrato come creare un report in formato libero di SSRS che sia simile a una lettera tipo.</span><span class="sxs-lookup"><span data-stu-id="b6b98-103">This tutorial teaches you how to create an SSRS free form report that resembles a forms letter.</span></span> <span data-ttu-id="b6b98-104">È possibile disporre gli elementi dei report in modo da creare un form, con caselle di testo, immagini e altre aree dati.</span><span class="sxs-lookup"><span data-stu-id="b6b98-104">You can arrange report items to create a form with text boxes, images and other data regions.</span></span>

 <span data-ttu-id="b6b98-105">Il report creato in questa esercitazione si basa su dati di vendita di esempio inclusi nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="b6b98-105">The report you create in this tutorial is based on sample sales data that is included in the tutorial.</span></span> <span data-ttu-id="b6b98-106">Nel report le informazioni vengono raggruppate per territorio e vengono visualizzati il nome del responsabile vendite del territorio e informazioni dettagliate e riepilogative relative alle vendite.</span><span class="sxs-lookup"><span data-stu-id="b6b98-106">The report groups information by territory and displays the name of the sales manager for the territory as well as detailed and summary sales information.</span></span> <span data-ttu-id="b6b98-107">Come base per il report in formato libero si utilizzerà l'area dati elenco e si aggiungerà quindi un pannello decorativo con un'immagine, testo statico contenente dati, una tabella per la visualizzazione di informazioni dettagliate e facoltativamente grafici a torta e istogrammi per la visualizzazione di informazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="b6b98-107">You will use the list data region as the foundation for the free form report, and then add a decorative panel with an image, static text with data inserted, a table to show detailed information, and optionally, pie and column charts to display summary information.</span></span>

##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="b6b98-108">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="b6b98-108">What You Will Learn</span></span>
 <span data-ttu-id="b6b98-109">In questa esercitazione verranno illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6b98-109">In this tutorial, you will learn how to do the following:</span></span>

-   [<span data-ttu-id="b6b98-110">Creare un report vuoto, un'origine dati e un set di dati</span><span class="sxs-lookup"><span data-stu-id="b6b98-110">Create a Blank Report, Data Source, and Dataset</span></span>](#BlankReport)

-   [<span data-ttu-id="b6b98-111">Aggiungere e configurare un elenco</span><span class="sxs-lookup"><span data-stu-id="b6b98-111">Add and Configure a List</span></span>](#List)

-   [<span data-ttu-id="b6b98-112">Aggiungere elementi grafici</span><span class="sxs-lookup"><span data-stu-id="b6b98-112">Add Graphics</span></span>](#Graphics)

-   [<span data-ttu-id="b6b98-113">Aggiungere testo in formato libero</span><span class="sxs-lookup"><span data-stu-id="b6b98-113">Add Free Form Text</span></span>](#Text)

-   [<span data-ttu-id="b6b98-114">Aggiungere una tabella per la visualizzazione di dettagli</span><span class="sxs-lookup"><span data-stu-id="b6b98-114">Add a Table to Show Details</span></span>](#Table)

-   [<span data-ttu-id="b6b98-115">Formattare i dati</span><span class="sxs-lookup"><span data-stu-id="b6b98-115">Format Data</span></span>](#Format)

-   [<span data-ttu-id="b6b98-116">Salva il report</span><span class="sxs-lookup"><span data-stu-id="b6b98-116">Save the Report</span></span>](#Save)

### <a name="other-optional-steps"></a><span data-ttu-id="b6b98-117">Altri passaggi facoltativi</span><span class="sxs-lookup"><span data-stu-id="b6b98-117">Other Optional Steps</span></span>

-   [<span data-ttu-id="b6b98-118">Aggiungere una linea per separare le aree del report</span><span class="sxs-lookup"><span data-stu-id="b6b98-118">Add a Line to Separate Areas of Report</span></span>](#Line)

-   [<span data-ttu-id="b6b98-119">Aggiungere una visualizzazione dei dati di riepilogo</span><span class="sxs-lookup"><span data-stu-id="b6b98-119">Add Summary Data Visualization</span></span>](#Visualization)

 <span data-ttu-id="b6b98-120">Il tempo stimato per il completare l'esercitazione è di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="b6b98-120">Estimated time to complete this tutorial: 20 minutes.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6b98-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6b98-121">Requirements</span></span>
 <span data-ttu-id="b6b98-122">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="b6b98-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>

##  <a name="1-create-a-blank-report-data-source-and-dataset"></a><a name="BlankReport"></a><span data-ttu-id="b6b98-123">1. creare un report vuoto, un'origine dati e un set di dati</span><span class="sxs-lookup"><span data-stu-id="b6b98-123">1. Create a Blank Report, Data Source, and Dataset</span></span>

> [!NOTE]
>  <span data-ttu-id="b6b98-124">Per evitare che nel report sia necessaria un'origine dati esterna, nella query di questa esercitazione sono inclusi i valori dei dati.</span><span class="sxs-lookup"><span data-stu-id="b6b98-124">In this tutorial, the query contains the data values so that the report does not need an external data source.</span></span> <span data-ttu-id="b6b98-125">L'uso di questo tipo di dati interni è molto utile ai fini dell'apprendimento, ma tale approccio rende la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="b6b98-125">The use of this type of internal data is great for learning purposes, but the approach makes the query long.</span></span> <span data-ttu-id="b6b98-126">.</span><span class="sxs-lookup"><span data-stu-id="b6b98-126">.</span></span>

#### <a name="to-create-a-blank-report"></a><span data-ttu-id="b6b98-127">Per creare un report vuoto</span><span class="sxs-lookup"><span data-stu-id="b6b98-127">To create a blank report</span></span>

1.  <span data-ttu-id="b6b98-128">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-128">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b6b98-129">Verrà visualizzata la finestra di dialogo **Riquadro attività iniziale** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-129">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="b6b98-130">In caso contrario, fare clic sul pulsante Generatore report, quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-130">If it does not, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="b6b98-131">Nel riquadro sinistro della finestra di dialogo **Riquadro attività iniziale** verificare che l'opzione **Nuovo report** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="b6b98-131">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>

3.  <span data-ttu-id="b6b98-132">Nel riquadro destro fare clic su **Report vuoto**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-132">In the right pane, click **Blank Report**.</span></span>

#### <a name="to-create-a-new-data-source"></a><span data-ttu-id="b6b98-133">Per creare una nuova origine dati</span><span class="sxs-lookup"><span data-stu-id="b6b98-133">To create a new data source</span></span>

1.  <span data-ttu-id="b6b98-134">Nel riquadro dei dati del report fare clic su **nuovo**e quindi su **origine dati**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-134">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>

2.  <span data-ttu-id="b6b98-135">Nella `Name` casella digitare: **ListDataSource**</span><span class="sxs-lookup"><span data-stu-id="b6b98-135">In the `Name` box, type: **ListDataSource**</span></span>

3.  <span data-ttu-id="b6b98-136">Fare clic su **Usa una connessione incorporata nel report**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-136">Click **Use a connection embedded in my report**.</span></span>

4.  <span data-ttu-id="b6b98-137">Verificare che il tipo di connessione sia Microsoft SQL Server, quindi nella casella **stringa di connessione** digitare: \*\*Data Source = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="b6b98-137">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>

     <span data-ttu-id="b6b98-138">\<servername>, ad esempio Report001, specifica un computer in cui è installata un'istanza del SQL Server motore di database.</span><span class="sxs-lookup"><span data-stu-id="b6b98-138">\<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="b6b98-139">Poiché i dati del report non vengono estratti da un database di SQL Server, non è necessario includere il nome di un database.</span><span class="sxs-lookup"><span data-stu-id="b6b98-139">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="b6b98-140">Per analizzare la query viene utilizzato il database predefinito nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="b6b98-140">The default database on the specified server is used to parse the query.</span></span>

5.  <span data-ttu-id="b6b98-141">Fare clic su **Credenziali**, quindi immettere le credenziali necessarie per la connessione all'istanza del motore di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6b98-141">Click **Credentials**, and enter the credentials needed to connect to the instance of the SQL Server Database Engine.</span></span>

6.  <span data-ttu-id="b6b98-142">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-142">Click **OK**.</span></span>

#### <a name="to-create-a-new-dataset"></a><span data-ttu-id="b6b98-143">Per creare un nuovo set di dati</span><span class="sxs-lookup"><span data-stu-id="b6b98-143">To create a new dataset</span></span>

1.  <span data-ttu-id="b6b98-144">Nel riquadro dei dati del report fare clic su **Nuovo**, quindi su **Set di dati**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-144">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>

2.  <span data-ttu-id="b6b98-145">Nella `Name` casella digitare: **ListDataset.**</span><span class="sxs-lookup"><span data-stu-id="b6b98-145">In the `Name` box, type: **ListDataset.**</span></span>

3.  <span data-ttu-id="b6b98-146">Fare clic su **Utilizzare un set di dati incorporato nel report**, quindi verificare che l'origine dati sia **ListDataSource**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-146">Click **Use a dataset embedded in my report**, and verify that the data source is **ListDataSource**.</span></span>

4.  <span data-ttu-id="b6b98-147">Verificare che il tipo di query **Testo** sia selezionato, quindi fare clic su **Progettazione query**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-147">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>

5.  <span data-ttu-id="b6b98-148">Fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-148">Click **Edit as Text**.</span></span>

6.  <span data-ttu-id="b6b98-149">Copiare e incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="b6b98-149">Copy and paste the following query into the query pane:</span></span>

    ```
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity
    ```

7.  <span data-ttu-id="b6b98-150">Fare clic su Esegui per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="b6b98-150">Click Run icon to run the query.</span></span>

     <span data-ttu-id="b6b98-151">I risultati della query corrispondono ai dati disponibili per la visualizzazione nel report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-151">The query results are the data available to display in your report.</span></span>

     <span data-ttu-id="b6b98-152">![Progettazione query](../../2014/tutorials/media/tutorial-querydesigner.png "Progettazione query")</span><span class="sxs-lookup"><span data-stu-id="b6b98-152">![Query Designer](../../2014/tutorials/media/tutorial-querydesigner.png "Query Designer")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="2-add-and-configure-a-list"></a><a name="List"></a><span data-ttu-id="b6b98-153">2. aggiungere e configurare un elenco</span><span class="sxs-lookup"><span data-stu-id="b6b98-153">2. Add and Configure a List</span></span>
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="b6b98-154">fornisce tre modelli di area dati, ovvero tabella, matrice ed elenco.</span><span class="sxs-lookup"><span data-stu-id="b6b98-154">provides three data region templates: table, matrix, and list.</span></span> <span data-ttu-id="b6b98-155">Questi modelli sono tutti basati su un area dati Tablix.</span><span class="sxs-lookup"><span data-stu-id="b6b98-155">These templates are all based on a tablix data region.</span></span>

 <span data-ttu-id="b6b98-156">In questa esercitazione si userà un elenco per visualizzare le informazioni sulle vendite per i territori di vendita in un report simile a un notiziario.</span><span class="sxs-lookup"><span data-stu-id="b6b98-156">In this tutorial, you will use a list to display the sales information for sales territories in a report that resembles a newsletter.</span></span> <span data-ttu-id="b6b98-157">Le informazioni vengono raggruppate per territorio.</span><span class="sxs-lookup"><span data-stu-id="b6b98-157">The information is grouped by territory.</span></span> <span data-ttu-id="b6b98-158">Si aggiungerà un nuovo gruppo di righe per il raggruppamento dei dati per territorio e si eliminerà quindi il gruppo di righe Dettagli incorporato.</span><span class="sxs-lookup"><span data-stu-id="b6b98-158">You will add a new row group that groups data by territory, and then delete the built-in Details row group.</span></span> <span data-ttu-id="b6b98-159">Il modello di elenco è ideale per la creazione di report in formato libero.</span><span class="sxs-lookup"><span data-stu-id="b6b98-159">The list template is ideal for creating free form reports.</span></span> <span data-ttu-id="b6b98-160">Per ulteriori informazioni, vedere la pagina relativa agli [elenchi &#40;Generatore report e SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b6b98-160">For more information, see [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="b6b98-161">Questo report utilizza il formato carta Letter (21,7 X 27,9 cm) e margini di 2,54 cm.</span><span class="sxs-lookup"><span data-stu-id="b6b98-161">This report uses the paper size Letter (8.5 X11) and 1 inch margins.</span></span> <span data-ttu-id="b6b98-162">Una pagina del report più alta di 9 pollici (23 centimetri) o più larga di 6 1/2 (16,5) centimetri potrebbe determinare la generazione di pagine vuote.</span><span class="sxs-lookup"><span data-stu-id="b6b98-162">A report page taller than 9 inches or wider than 6 1/2 inches might generate blank pages.</span></span>

#### <a name="to-add-a-list"></a><span data-ttu-id="b6b98-163">Per aggiungere un elenco</span><span class="sxs-lookup"><span data-stu-id="b6b98-163">To add a list</span></span>

1.  <span data-ttu-id="b6b98-164">Nell'area **Aree dati** della scheda **Inserisci** della barra multifunzione fare clic su **Elenco** , quindi trascinare l'elenco nel corpo del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-164">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List** and then drag the list inside the report body.</span></span> <span data-ttu-id="b6b98-165">Assegnare all'elenco un'altezza di 7 pollici (18 centimetri) e una larghezza di 6,25 pollici (16 centimetri).</span><span class="sxs-lookup"><span data-stu-id="b6b98-165">Make the list 7 inches tall and 6.25 inches wide.</span></span>

2.  <span data-ttu-id="b6b98-166">Fare clic nell'elenco, fare clic con il pulsante destro del mouse sulla parte superiore dell'elenco, quindi scegliere **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-166">Click inside the list, right-click the top of the list, and then click **Tablix Properties**.</span></span>

     <span data-ttu-id="b6b98-167">![Aggiunta di un elenco](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Aggiunta di un elenco")</span><span class="sxs-lookup"><span data-stu-id="b6b98-167">![Adding list](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Adding list")</span></span>

3.  <span data-ttu-id="b6b98-168">Nell'elenco a discesa **Nome set di dati** selezionare **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-168">In the **Dataset name** drop-down list, select **ListDataset**.</span></span>

4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

5.  <span data-ttu-id="b6b98-169">Fare clic con il pulsante destro del mouse nell'elenco, quindi scegliere **Proprietà rettangolo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-169">Right-click inside the list, and then click **Rectangle Properties**.</span></span>

     <span data-ttu-id="b6b98-170">![Comando Proprietà rettangolo](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Comando Proprietà rettangolo")</span><span class="sxs-lookup"><span data-stu-id="b6b98-170">![Rectangle Properties command](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Rectangle Properties command")</span></span>

6.  <span data-ttu-id="b6b98-171">Nella scheda **Generale** selezionare la casella di controllo **Aggiungi un'interruzione di pagina dopo** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-171">On the **General** tab, select the **Add a page break after** checkbox.</span></span>

7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-new-row-group-and-to-delete-the-details-group"></a><span data-ttu-id="b6b98-172">Per aggiungere un nuovo gruppo di righe ed eliminare il gruppo Dettagli</span><span class="sxs-lookup"><span data-stu-id="b6b98-172">To add a new row group and to delete the Details group</span></span>

1.  <span data-ttu-id="b6b98-173">Nel riquadro Gruppi di righe fare clic con il pulsante destro del mouse sul gruppo Dettagli, scegliere **Aggiungi gruppo**, quindi fare clic su **Gruppo padre**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-173">In the Row Groups pane, right-click the Details group, point to **Add Group**, and then click **Parent Group**.</span></span>

     <span data-ttu-id="b6b98-174">![Comando Gruppo padre](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Comando Gruppo padre")</span><span class="sxs-lookup"><span data-stu-id="b6b98-174">![Parent Group command](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Parent Group command")</span></span>

2.  <span data-ttu-id="b6b98-175">Nell'elenco a discesa selezionare `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="b6b98-175">In the drop-down list, select `[Territory].`</span></span>

3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="b6b98-176">All'elenco verrà aggiunta una colonna.</span><span class="sxs-lookup"><span data-stu-id="b6b98-176">A column is added to the list.</span></span> <span data-ttu-id="b6b98-177">La colonna contiene la cella `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="b6b98-177">The column contains the cell `[Territory].`</span></span>

4.  <span data-ttu-id="b6b98-178">Fare clic con il pulsante destro del mouse sulla colonna Territory, quindi scegliere **Elimina colonne**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-178">Right-click the Territory column in the list, and then click **Delete Columns**.</span></span>

     <span data-ttu-id="b6b98-179">![Elimina colonne](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Elimina colonne")</span><span class="sxs-lookup"><span data-stu-id="b6b98-179">![Delete columns](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Delete columns")</span></span>

5.  <span data-ttu-id="b6b98-180">Fare clic su **Elimina solo colonne**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-180">Click **Delete Columns only**.</span></span>

     <span data-ttu-id="b6b98-181">![Finestra di dialogo Elimina colonne](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Finestra di dialogo Elimina colonne")</span><span class="sxs-lookup"><span data-stu-id="b6b98-181">![Delete Columns dialog box](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Delete Columns dialog box")</span></span>

6.  <span data-ttu-id="b6b98-182">Nel riquadro Gruppi di righe fare clic con il pulsante destro del mouse sul gruppo **Dettagli** , quindi scegliere **Elimina gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-182">In the Row Groups pane, right-click the **Details** group, and then click **Delete Group**.</span></span>

     <span data-ttu-id="b6b98-183">![Elimina gruppo dettagli](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Elimina gruppo dettagli")</span><span class="sxs-lookup"><span data-stu-id="b6b98-183">![Delete Details Group](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Delete Details Group")</span></span>

7.  <span data-ttu-id="b6b98-184">Fare clic su **Elimina solo gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-184">Click **Delete Group only**.</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="3-add-graphics"></a><a name="Graphics"></a><span data-ttu-id="b6b98-185">3. aggiungere elementi grafici</span><span class="sxs-lookup"><span data-stu-id="b6b98-185">3. Add Graphics</span></span>
 <span data-ttu-id="b6b98-186">Uno dei vantaggi offerti da un'area dati elenco consiste nella possibilità di aggiungere elementi del report, quali rettangoli e caselle di testo, in qualsiasi posizione, anziché essere limitati a un layout tabulare.</span><span class="sxs-lookup"><span data-stu-id="b6b98-186">One of the advantages of using a list data region is that you can add report items such as rectangles and text boxes anywhere, instead of being limited to a tabular layout.</span></span> <span data-ttu-id="b6b98-187">L'aggiunta di un elemento grafico, ad esempio un rettangolo colorato, conferirà al report un aspetto più gradevole.</span><span class="sxs-lookup"><span data-stu-id="b6b98-187">You will enhance the appearance of the report by adding a graphic (a rectangle filled with a color).</span></span>

#### <a name="to-add-graphic-elements-to-the-report"></a><span data-ttu-id="b6b98-188">Per aggiungere elementi grafici al report</span><span class="sxs-lookup"><span data-stu-id="b6b98-188">To add graphic elements to the report</span></span>

1.  <span data-ttu-id="b6b98-189">Nella scheda **Inserisci** della barra multifunzione fare clic su **rettangolo**, quindi trascinare un rettangolo nell'angolo superiore sinistro dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b6b98-189">On the **Insert** tab of the ribbon, click **Rectangle**,and then drag a rectangle to the upper left corner of the list.</span></span> <span data-ttu-id="b6b98-190">Assegnare al rettangolo un'altezza di 7 pollici (18 centimetri) e una larghezza di 1 pollice (2,5 centimetri).</span><span class="sxs-lookup"><span data-stu-id="b6b98-190">Make the rectangle 7 inches tall and 1 inch wide.</span></span>

2.  <span data-ttu-id="b6b98-191">Fare clic con il pulsante destro del mouse sul rettangolo, quindi scegliere **Proprietà rettangolo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-191">Right-click the rectangle, and then click **Rectangle Properties**.</span></span>

3.  <span data-ttu-id="b6b98-192">Fare clic sulla scheda **Riempimento** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-192">Click the **Fill** tab.</span></span>

4.  <span data-ttu-id="b6b98-193">Nell'elenco a discesa **Colore riempimento** fare clic su **Altri colori**, quindi selezionare il colore **GrigioScuro** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-193">In the **Fill color** drop-down list, click **More Colors**, and then select the **DarkGray** color.</span></span>

     <span data-ttu-id="b6b98-194">![Seleziona colore di riempimento](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Seleziona colore di riempimento")</span><span class="sxs-lookup"><span data-stu-id="b6b98-194">![Select fill color](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Select fill color")</span></span>

5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

6.  <span data-ttu-id="b6b98-195">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-195">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b6b98-196">Nella parte sinistra del report è ora presente un elemento grafico verticale costituito da un rettangolo di colore grigio scuro.</span><span class="sxs-lookup"><span data-stu-id="b6b98-196">The left side of the report now has vertical graphic that consists of a dark gray rectangle.</span></span>

##  <a name="4-add-free-form-text"></a><a name="Text"></a><span data-ttu-id="b6b98-197">4. aggiungere testo in formato libero</span><span class="sxs-lookup"><span data-stu-id="b6b98-197">4. Add Free Form Text</span></span>
 <span data-ttu-id="b6b98-198">Una casella di testo contiene testo statico ripetuto in ogni pagina del report, nonché campi dati.</span><span class="sxs-lookup"><span data-stu-id="b6b98-198">A text box contains static text that is repeated on each report page as well as data fields.</span></span>

#### <a name="to-add-text-to-the-report"></a><span data-ttu-id="b6b98-199">Per aggiungere testo al report</span><span class="sxs-lookup"><span data-stu-id="b6b98-199">To add text to the report</span></span>

1.  <span data-ttu-id="b6b98-200">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="b6b98-200">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="b6b98-201">Nella scheda **Inserisci** della barra multifunzione fare clic su **Casella di testo**, quindi trascinare una casella di testo nell'angolo superiore sinistro dell'elenco all'interno del rettangolo aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b6b98-201">On the **Insert** tab of the ribbon, click **Text Box**, and then drag a text box to the upper left corner of the list, but inside of the rectangle you added previously.</span></span> <span data-ttu-id="b6b98-202">Assegnare alla casella di testo un'altezza di 3 pollici (8 centimetri) e una larghezza di 5 pollici (13 centimetri).</span><span class="sxs-lookup"><span data-stu-id="b6b98-202">Make the text box about 3 inches tall and 5 inches wide.</span></span>

3.  <span data-ttu-id="b6b98-203">Posizionare il cursore nella parte superiore della casella di testo, quindi digitare: **Notiziario per** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-203">Place the cursor in the upper part of the text box, and then type: **Newsletter for** .</span></span>

     <span data-ttu-id="b6b98-204">![Aggiungi testo di intestazione newsletter](../../2014/tutorials/media/tutorial-newsletterfor.png "Aggiungi testo di intestazione newsletter")</span><span class="sxs-lookup"><span data-stu-id="b6b98-204">![Add newsletter heading text](../../2014/tutorials/media/tutorial-newsletterfor.png "Add newsletter heading text")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b6b98-205">Assicurarsi di includere lo spazio aggiuntivo dopo la parola "per".</span><span class="sxs-lookup"><span data-stu-id="b6b98-205">Be sure to include the extra space after the word "for".</span></span> <span data-ttu-id="b6b98-206">Lo spazio consente di separare il testo dal campo che si aggiungerà nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="b6b98-206">The space separates the text and the field that you will add in the next step.</span></span>

4.  <span data-ttu-id="b6b98-207">Trascinare il campo Territory nella casella di testo e posizionarlo dopo il testo digitato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="b6b98-207">Drag the Territory field to the text box and place it after the text you typed in step 3.</span></span>

     <span data-ttu-id="b6b98-208">![Aggiungi campo Territorial](../../2014/tutorials/media/tutorial-addterritorialfield.png "Aggiungi campo Territorial")</span><span class="sxs-lookup"><span data-stu-id="b6b98-208">![Add Territorial field](../../2014/tutorials/media/tutorial-addterritorialfield.png "Add Territorial field")</span></span>

5.  <span data-ttu-id="b6b98-209">Selezionare tutto il testo, fare clic con il pulsante destro del mouse su di esso, quindi scegliere **Proprietà testo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-209">Select all text, right-click, and then click **Text Properties**.</span></span>

6.  <span data-ttu-id="b6b98-210">Fare clic sulla scheda **Tipo di carattere** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-210">Click the **Font** tab.</span></span>

7.  <span data-ttu-id="b6b98-211">Nell'elenco **Tipo di carattere** selezionare **Times New Roman**, in **Dimensioni** selezionare **20 pt**e in **Colore** selezionare **Rosso**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-211">In the **Font** list, select **Times New Roman**; in **Size** select **20 pt**, in **Color** select **Red**.</span></span>

     <span data-ttu-id="b6b98-212">![Proprietà testo](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Proprietà testo")</span><span class="sxs-lookup"><span data-stu-id="b6b98-212">![Text Properties](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Text Properties")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

9. <span data-ttu-id="b6b98-213">Posizionare il cursore sotto il testo digitato nel passaggio 3 e digitare: **Salve** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-213">Place the cursor below the text you typed in step 3 and type: **Hello** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b6b98-214">Assicurarsi di includere lo spazio aggiuntivo dopo la parola "Salve".</span><span class="sxs-lookup"><span data-stu-id="b6b98-214">Be sure to include the extra space after the word "Hello".</span></span> <span data-ttu-id="b6b98-215">Lo spazio consente di separare il testo dal campo che si aggiungerà nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="b6b98-215">The space separates the text and the field that you will add in the next step.</span></span>

10. <span data-ttu-id="b6b98-216">Trascinare il campo FullName nella casella di testo e posizionarlo dopo il testo digitato nel passaggio 9, quindi digitare una virgola (,).</span><span class="sxs-lookup"><span data-stu-id="b6b98-216">Drag the FullName field to the text box and place it after the text you typed in step 9, and then type a comma (,).</span></span>

     <span data-ttu-id="b6b98-217">![Aggiungi campo Nome completo](../../2014/tutorials/media/tutorial-addfullnamefield.png "Aggiungi campo Nome completo")</span><span class="sxs-lookup"><span data-stu-id="b6b98-217">![Add Full Name field](../../2014/tutorials/media/tutorial-addfullnamefield.png "Add Full Name field")</span></span>

11. <span data-ttu-id="b6b98-218">Selezionare il testo aggiunto nei passaggi 9 e 10, fare clic con il pulsante destro del mouse su di esso, quindi scegliere **Proprietà testo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-218">Select the text you added in steps 9 and 10, right-click, and then click **Text Properties**.</span></span>

12. <span data-ttu-id="b6b98-219">Fare clic sulla scheda **Tipo di carattere** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-219">Click the **Font** tab.</span></span>

13. <span data-ttu-id="b6b98-220">Nell'elenco **Tipo di carattere** selezionare **Times New Roman**, in **Dimensioni** selezionare **16 pt**e in **Colore** selezionare **Nero** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-220">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Black** color.</span></span>

14. [!INCLUDE[clickOK](../includes/clickok-md.md)]

15. <span data-ttu-id="b6b98-221">Posizionare il cursore sotto il testo aggiunto nei passaggi da 9 a 13, quindi copiare e incollare il testo fittizio seguente:</span><span class="sxs-lookup"><span data-stu-id="b6b98-221">Place the cursor below the text you added in steps 9 through 13, and then copy and paste the following "greeked" text:</span></span>

    ```
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin sed dolor in ipsum pulvinar egestas. Sed sed lacus at leo ornare ultricies. Vivamus velit risus, euismod nec sodales gravida, gravida in dui. Etiam ullamcorper elit vitae justo fermentum ut ullamcorper augue sodales. Ut placerat, nisl quis feugiat adipiscing, nibh est aliquet est, mollis faucibus mauris lectus quis arcu. In mollis tincidunt lacinia. In vitae erat ut lorem tincidunt luctus. Curabitur et magna nunc, sit amet adipiscing nisi. Nulla rhoncus elementum orci nec tincidunt. Aliquam imperdiet cursus erat vel tincidunt. Donec et neque ac urna rutrum sodales. In id purus et nisl dignissim dapibus. Sed rhoncus metus at felis feugiat eu tempor dolor vehicula. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam faucibus consectetur diam eu pellentesque. 
    Nulla facilisi. Proin ligula enim, porta ut tincidunt id, adipiscing sit amet eros. Ut purus sem, bibendum et vulputate sit amet, facilisis eget magna. Sed aliquam erat non erat eleifend hendrerit. Ut a ligula est, sit amet eleifend enim. Ut et nisl enim, sit amet adipiscing augue. Vivamus eu arcu ac libero posuere elementum. Integer condimentum bibendum venenatis. Integer odio tellus, feugiat in pellentesque semper, interdum nec sem. Sed cursus euismod sem, ut elementum sapien placerat vel. 
    ```

16. <span data-ttu-id="b6b98-222">Selezionare il testo aggiunto nel passaggio 15, fare clic con il pulsante destro del mouse su di esso, quindi scegliere **Proprietà testo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-222">Select the text you added in steps 15, right-click, and then click **Text Properties**.</span></span>

17. <span data-ttu-id="b6b98-223">Fare clic sulla scheda **Tipo di carattere** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-223">Click the **Font** tab.</span></span>

18. <span data-ttu-id="b6b98-224">Nell'elenco **Tipo di carattere** selezionare **Arial**, in **Dimensioni** selezionare **10 pt**e in **Colore** selezionare **Nero**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-224">In the **Font** list, select **Arial**; in **Size** select **10 pt**, in **Color** select **Black**.</span></span>

19. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="b6b98-225">![Aggiungi testo newsletter](../../2014/tutorials/media/tutorial-newslettertext.png "Aggiungi testo newsletter")</span><span class="sxs-lookup"><span data-stu-id="b6b98-225">![Add newsletter text](../../2014/tutorials/media/tutorial-newslettertext.png "Add newsletter text")</span></span>

20. <span data-ttu-id="b6b98-226">Posizionare il cursore sotto il testo incollato nel passaggio 15, quindi digitare: **Congratulazioni per le vendite totali di** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-226">Place the cursor below the text you pasted in step 15, and then type: **Congratulations on your total sales of** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b6b98-227">Assicurarsi di includere lo spazio aggiuntivo dopo la parola "di".</span><span class="sxs-lookup"><span data-stu-id="b6b98-227">Be sure to include the extra space after the word "of".</span></span> <span data-ttu-id="b6b98-228">Lo spazio consente di separare il testo dal campo che si aggiungerà nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="b6b98-228">The space separates the text and the field that you will add in the next step.</span></span>

21. <span data-ttu-id="b6b98-229">Trascinare il campo Sales nella casella di testo, posizionarlo dopo il testo digitato nel passaggio 20, quindi digitare un punto esclamativo (!).</span><span class="sxs-lookup"><span data-stu-id="b6b98-229">Drag the Sales field to the text box, place it after the text you typed in step 20, and then type an exclamation mark (!).</span></span>

22. <span data-ttu-id="b6b98-230">Evidenziare il campo Sales, fare clic con il pulsante destro del mouse sul campo, quindi scegliere **espressione**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-230">Highlight the Sales field, right-click the field, and then click **Expression**.</span></span>

23. <span data-ttu-id="b6b98-231">Nella casella dell'espressione modificare l'espressione per includere la funzione Sum nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b6b98-231">In the expression box, change the expression to include the Sum function as follows:</span></span>

    ```
    =Sum(Fields!Sales.value)
    ```

24. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="b6b98-232">![Aggiungi un'espressione al campo Sales](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Aggiungi un'espressione al campo Sales")</span><span class="sxs-lookup"><span data-stu-id="b6b98-232">![Add an expression to sales field](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Add an expression to sales field")</span></span>

25. <span data-ttu-id="b6b98-233">Selezionare il testo aggiunto nei passaggi da 20 a 23, fare clic con il pulsante destro del mouse su di esso, quindi scegliere **Proprietà testo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-233">Select the text you added in steps 20 through 23, right-click, and then click **Text Properties**.</span></span>

26. <span data-ttu-id="b6b98-234">Fare clic sulla scheda **Tipo di carattere** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-234">Click the **Font** tab.</span></span>

27. <span data-ttu-id="b6b98-235">Nell'elenco **Tipo di carattere** selezionare **Times New Roman**, in **Dimensioni** selezionare **16 pt**e in **Colore** selezionare **Rosso**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-235">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Red**.</span></span>

28. [!INCLUDE[clickOK](../includes/clickok-md.md)]

29. <span data-ttu-id="b6b98-236">Selezionare `[Sum(Sales)]` e nel gruppo **Numero** della scheda **Home** fare clic sul pulsante **Valuta** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-236">Select `[Sum(Sales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="b6b98-237">![Aggiungi simbolo di valuta](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Aggiungi simbolo di valuta")</span><span class="sxs-lookup"><span data-stu-id="b6b98-237">![Add currency symbol](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Add currency symbol")</span></span>

30. <span data-ttu-id="b6b98-238">Fare clic con il pulsante destro del mouse sulla casella di testo contenente il testo "Fare clic per aggiungere il titolo", quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-238">Right-click the text box with the "Click to add title" text, and then click **Delete**.</span></span>

31. <span data-ttu-id="b6b98-239">Selezionare la casella di riepilogo e spostarla nella parte superiore della pagina utilizzando i tasti di direzione.</span><span class="sxs-lookup"><span data-stu-id="b6b98-239">Select the list box and using the arrow keys, move it to the top of the page.</span></span>

32. <span data-ttu-id="b6b98-240">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-240">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b6b98-241">Nel report viene visualizzato il testo statico e in ogni pagina del report sono inclusi i dati relativi a un territorio.</span><span class="sxs-lookup"><span data-stu-id="b6b98-241">The report displays static text and each report page includes data that pertains to a territory.</span></span> <span data-ttu-id="b6b98-242">Le vendite vengono formattate come valuta.</span><span class="sxs-lookup"><span data-stu-id="b6b98-242">Sales are formatted as currency.</span></span>

 <span data-ttu-id="b6b98-243">![Anteprima della newsletter](../../2014/tutorials/media/tutorial-newsletters.png "Anteprima della newsletter")</span><span class="sxs-lookup"><span data-stu-id="b6b98-243">![Preview of Newsletter](../../2014/tutorials/media/tutorial-newsletters.png "Preview of Newsletter")</span></span>

##  <a name="5-add-a-table-to-show-sales-details"></a><a name="Table"></a><span data-ttu-id="b6b98-244">5. aggiungere una tabella per visualizzare i dettagli delle vendite</span><span class="sxs-lookup"><span data-stu-id="b6b98-244">5. Add a Table to Show Sales Details</span></span>
 <span data-ttu-id="b6b98-245">Utilizzare la procedura guidata Nuova tabella o matrice per aggiungere una tabella al report in formato libero.</span><span class="sxs-lookup"><span data-stu-id="b6b98-245">Use the New Table and Matrix Wizard to add a table to the free form report.</span></span> <span data-ttu-id="b6b98-246">Dopo avere completato la procedura guidata, si aggiungerà manualmente una riga per i totali.</span><span class="sxs-lookup"><span data-stu-id="b6b98-246">After you complete the wizard, you will manually add a row for totals.</span></span>

#### <a name="to-add-a-table"></a><span data-ttu-id="b6b98-247">Per aggiungere una tabella</span><span class="sxs-lookup"><span data-stu-id="b6b98-247">To add a table</span></span>

1.  <span data-ttu-id="b6b98-248">Nell'area **Aree dati** della scheda **Inserisci** della barra multifunzione fare clic su **Tabella**, quindi su **Creazione guidata tabella**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-248">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **Table**, and then click **Table Wizard**.</span></span>

2.  <span data-ttu-id="b6b98-249">Nella pagina Scegliere un set di dati fare clic su **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-249">On the Choose a dataset page, click **ListDataset**.</span></span>

3.  <span data-ttu-id="b6b98-250">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-250">Click **Next**.</span></span>

4.  <span data-ttu-id="b6b98-251">Nella pagina **Disponi campi** trascinare il campo Product da **Campi disponibili** a **Valori**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-251">On the **Arrange fields** page, drag the Product field from **Available fields** to **Values.**</span></span>

5.  <span data-ttu-id="b6b98-252">Ripetere il passaggio 4 per SalesDate, Quantity e Sales.</span><span class="sxs-lookup"><span data-stu-id="b6b98-252">Repeat step 4, for SalesDate, Quantity, and Sales.</span></span> <span data-ttu-id="b6b98-253">Posizionare SalesDate sotto Product, Quantity sotto SalesDate e Sales sotto SalesDate.</span><span class="sxs-lookup"><span data-stu-id="b6b98-253">Place SalesDate below Product, Quantity below SalesDate, and Sales below SalesDate.</span></span>

6.  <span data-ttu-id="b6b98-254">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-254">Click **Next**.</span></span>

7.  <span data-ttu-id="b6b98-255">Nella pagina **Scegliere il layout** visualizzare il layout della tabella.</span><span class="sxs-lookup"><span data-stu-id="b6b98-255">On the **Choose the layout** page, view the layout of the table.</span></span>

     <span data-ttu-id="b6b98-256">La tabella è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="b6b98-256">The table is very simple.</span></span> <span data-ttu-id="b6b98-257">È costituita da cinque colonne e non presenta gruppi di righe o colonne.</span><span class="sxs-lookup"><span data-stu-id="b6b98-257">It consists of five columns and has no row or column groups.</span></span> <span data-ttu-id="b6b98-258">Poiché non dispone di gruppi, le opzioni di layout correlate ai gruppi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="b6b98-258">Because it has no groups, the layout options related to groups, are not available.</span></span> <span data-ttu-id="b6b98-259">Più avanti nell'esercitazione si aggiornerà manualmente la tabella per includere un totale.</span><span class="sxs-lookup"><span data-stu-id="b6b98-259">You will manually update the table to include a total later in the tutorial.</span></span>

8.  <span data-ttu-id="b6b98-260">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-260">Click **Next**.</span></span>

9. <span data-ttu-id="b6b98-261">Nel riquadro **Stili** della pagina **Scegliere uno stile** selezionare **Ardesia**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-261">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

10. <span data-ttu-id="b6b98-262">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-262">Click **Finish**.</span></span>

11. <span data-ttu-id="b6b98-263">Trascinare la tabella sotto la casella di testo aggiunta nella lezione 4.</span><span class="sxs-lookup"><span data-stu-id="b6b98-263">Drag the table to below the text box that you added in lesson 4.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b6b98-264">Verificare che la tabella sia posizionata all'interno dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b6b98-264">Make sure the table is inside the list.</span></span>

12. <span data-ttu-id="b6b98-265">Dopo avere confermato che la tabella è selezionata, nel riquadro Gruppo di righe fare clic con il pulsante destro del mouse su Dettagli, scegliere **Aggiungi totale**, quindi fare clic su **Dopo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-265">Confirmed that the table is selected, then in the Row Group pane right-click Details, point to **Add Total**, and then click **After**.</span></span>

     <span data-ttu-id="b6b98-266">![Aggiungi totale report](../../2014/tutorials/media/tutorial-addtotal.png "Aggiungi totale report")</span><span class="sxs-lookup"><span data-stu-id="b6b98-266">![Add report total](../../2014/tutorials/media/tutorial-addtotal.png "Add report total")</span></span>

13. <span data-ttu-id="b6b98-267">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-267">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b6b98-268">Nel report verrà visualizzata una tabella con i dettagli e i totali delle vendite.</span><span class="sxs-lookup"><span data-stu-id="b6b98-268">The report displays a table with sales details and totals.</span></span>

 <span data-ttu-id="b6b98-269">![Totali vendite nel report](../../2014/tutorials/media/tutorial-reportsalestotals.png "Totali vendite nel report")</span><span class="sxs-lookup"><span data-stu-id="b6b98-269">![Sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals.png "Sales totals in report")</span></span>

##  <a name="6-format-data"></a><a name="Format"></a><span data-ttu-id="b6b98-270">6. formattare i dati</span><span class="sxs-lookup"><span data-stu-id="b6b98-270">6. Format Data</span></span>
 <span data-ttu-id="b6b98-271">Formattare solo i dati numerici come valuta e le date come giorno e ora.</span><span class="sxs-lookup"><span data-stu-id="b6b98-271">Format numeric data as currency and dates as day and time only.</span></span>

#### <a name="to-format-fields-table"></a><span data-ttu-id="b6b98-272">Per formattare la tabella dei campi</span><span class="sxs-lookup"><span data-stu-id="b6b98-272">To format fields table</span></span>

1.  <span data-ttu-id="b6b98-273">Fare clic su **progettazione** per passare alla visualizzazione progettazione.</span><span class="sxs-lookup"><span data-stu-id="b6b98-273">Click **Design** to switch to design view.</span></span>

2.  <span data-ttu-id="b6b98-274">Fare clic sulle celle della tabella contenenti `[Sum(SalesSales)]` e nel gruppo **Numero** della scheda **Home** fare clic sul pulsante **Valuta** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-274">Click the table cells that contain `[Sum(SalesSales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="b6b98-275">![Aggiungi simbolo di valuta a vendite totali](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Aggiungi simbolo di valuta a vendite totali")</span><span class="sxs-lookup"><span data-stu-id="b6b98-275">![Add currency symbol to sum sales](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Add currency symbol to sum sales")</span></span>

3.  <span data-ttu-id="b6b98-276">Fare clic sulle celle contenenti `[SalesDate]` e nell'elenco a discesa del gruppo **Numero** selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-276">Click the cell that contains `[SalesDate]` and in the **Number** group, from the drop-down list, select **Date**.</span></span>

4.  <span data-ttu-id="b6b98-277">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-277">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b6b98-278">Nel report verranno visualizzati i dati formattati che rendono più facile la lettura.</span><span class="sxs-lookup"><span data-stu-id="b6b98-278">The report now displays formatted data and is easier to read.</span></span>

 <span data-ttu-id="b6b98-279">![Formatta totali vendite nel report](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Formatta totali vendite nel report")</span><span class="sxs-lookup"><span data-stu-id="b6b98-279">![Format sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Format sales totals in report")</span></span>

##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="b6b98-280">7. salvare il report</span><span class="sxs-lookup"><span data-stu-id="b6b98-280">7. Save the Report</span></span>
 <span data-ttu-id="b6b98-281">È possibile salvare i report in un server di report, in una raccolta di SharePoint o nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b6b98-281">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="b6b98-282">È anche possibile esportare il report in diversi formati, ad esempio Word e PDF, eseguendo il report e scegliendo il formato dal menu **Esporta** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-282">You can also export the report to a variety of formats such as Word and PDF, by running the report and selecting the format from the **Export** menu.</span></span>

 <span data-ttu-id="b6b98-283">In questa esercitazione il report verrà salvato in un server di report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-283">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="b6b98-284">Se non si dispone dell'accesso a un server di report, sarà possibile salvare il report nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b6b98-284">If you do not have access to a report server, save the report to your computer.</span></span>

#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="b6b98-285">Per salvare il report in un server di report</span><span class="sxs-lookup"><span data-stu-id="b6b98-285">To save the report on a report server</span></span>

1.  <span data-ttu-id="b6b98-286">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-286">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="b6b98-287">Fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-287">Click **Recent Sites and Servers**.</span></span>

3.  <span data-ttu-id="b6b98-288">Selezionare o digitare il nome del server di report per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-288">Select or type the name of the report server where you have permission to save reports.</span></span>

     <span data-ttu-id="b6b98-289">Verrà visualizzato il messaggio "Connessione al server di report".</span><span class="sxs-lookup"><span data-stu-id="b6b98-289">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="b6b98-290">Al termine della connessione, verrà visualizzato il contenuto della cartella di report specificata dall'amministratore del server di report come posizione predefinita per i report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-290">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>

4.  <span data-ttu-id="b6b98-291">In `Name` sostituire il nome predefinito con **InformazioniVenditePerTerritorio**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-291">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

5.  <span data-ttu-id="b6b98-292">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-292">Click **Save**.</span></span>

 <span data-ttu-id="b6b98-293">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-293">The report is saved to the report server.</span></span> <span data-ttu-id="b6b98-294">Il nome del server di report al quale si è connessi verrà visualizzato sulla barra di stato nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="b6b98-294">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>

#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="b6b98-295">Per salvare il report nel computer</span><span class="sxs-lookup"><span data-stu-id="b6b98-295">To save the report on your computer</span></span>

1.  <span data-ttu-id="b6b98-296">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-296">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="b6b98-297">Fare clic su **Desktop**, **Documenti**o **Risorse del computer**, quindi selezionare la cartella in cui si desidera salvare il report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-297">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>

3.  <span data-ttu-id="b6b98-298">In `Name` sostituire il nome predefinito con **InformazioniVenditePerTerritorio**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-298">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

4.  <span data-ttu-id="b6b98-299">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-299">Click **Save**.</span></span>

##  <a name="8-optional-add-a-line-to-separate-areas-of-the-report"></a><a name="Line"></a><span data-ttu-id="b6b98-300">8. (facoltativo) aggiungere una linea per separare le aree del report</span><span class="sxs-lookup"><span data-stu-id="b6b98-300">8. (Optional) Add a Line to Separate Areas of the Report</span></span>
 <span data-ttu-id="b6b98-301">Aggiungere una linea per separare l'area editoriale da quella dei dettagli del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-301">Add a line to separate the editorial and details areas of the report.</span></span>

#### <a name="to-add-a-line"></a><span data-ttu-id="b6b98-302">Per aggiungere una linea</span><span class="sxs-lookup"><span data-stu-id="b6b98-302">To add a line</span></span>

1.  <span data-ttu-id="b6b98-303">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="b6b98-303">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="b6b98-304">Nell'area **Elementi del report** della scheda **Inserisci** della barra multifunzione fare clic su **Linea**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-304">On the **Insert** tab of the ribbon, in the **Report Items** area, click **Line.**</span></span>

3.  <span data-ttu-id="b6b98-305">Disegnare una linea sotto la casella di testo in formato libero aggiunta nella lezione 4.</span><span class="sxs-lookup"><span data-stu-id="b6b98-305">Draw a line below the free form text box you added in lesson 4.</span></span>

4.  <span data-ttu-id="b6b98-306">Fare clic sulla linea.</span><span class="sxs-lookup"><span data-stu-id="b6b98-306">Click the line.</span></span>

5.  <span data-ttu-id="b6b98-307">Fare clic sulla scheda **Home** .</span><span class="sxs-lookup"><span data-stu-id="b6b98-307">Click the **Home** tab.</span></span>

6.  <span data-ttu-id="b6b98-308">Nell'area **Bordo** selezionare **4 1/2** pt per la larghezza e **Rosso**per il colore.</span><span class="sxs-lookup"><span data-stu-id="b6b98-308">In the **Border** area, for width select **4 1/2** pt and for color, for color select **Red**.</span></span>

     <span data-ttu-id="b6b98-309">![Aggiungi riga al report](../../2014/tutorials/media/tutorial-reportwithline.png "Aggiungi riga al report")</span><span class="sxs-lookup"><span data-stu-id="b6b98-309">![Add line to report](../../2014/tutorials/media/tutorial-reportwithline.png "Add line to report")</span></span>

##  <a name="9-optional-add-summary-data-visualization"></a><a name="Visualization"></a><span data-ttu-id="b6b98-310">9. (facoltativo) aggiungere la visualizzazione dei dati di riepilogo</span><span class="sxs-lookup"><span data-stu-id="b6b98-310">9. (Optional) Add Summary Data Visualization</span></span>
 <span data-ttu-id="b6b98-311">I rettangoli consentono di controllare la modalità di rendering del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-311">Rectangles help you control how the report renders.</span></span> <span data-ttu-id="b6b98-312">Posizionare un grafico a torta e un istogramma all'interno di un rettangolo per essere certi che il rendering del report venga eseguito nel modo desiderato.</span><span class="sxs-lookup"><span data-stu-id="b6b98-312">Place a pie and column chart inside a rectangle to ensure that the report renders the way you want.</span></span>

#### <a name="to-add-a-rectangle"></a><span data-ttu-id="b6b98-313">Per aggiungere un rettangolo</span><span class="sxs-lookup"><span data-stu-id="b6b98-313">To add a rectangle</span></span>

1.  <span data-ttu-id="b6b98-314">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="b6b98-314">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="b6b98-315">Nell'area **Elementi del report** della scheda **Inserisci** della barra multifunzione fare clic su **Rettangolo**, quindi trascinare il rettangolo nell'elenco, a destra della tabella.</span><span class="sxs-lookup"><span data-stu-id="b6b98-315">On the **Insert** tab of the ribbon, in the **Report Items** area click **Rectangle**, and then drag the rectangle inside the list, to the right of the table.</span></span> <span data-ttu-id="b6b98-316">Assegnare al rettangolo una larghezza di 2 pollici (5 centimetri) e un'altezza di 4 pollici (10 centimetri).</span><span class="sxs-lookup"><span data-stu-id="b6b98-316">Make the rectangle 2 inches wide and 4 inches tall.</span></span>

3.  <span data-ttu-id="b6b98-317">Allineare le parti superiori del rettangolo e della tabella.</span><span class="sxs-lookup"><span data-stu-id="b6b98-317">Align the tops of the rectangle and the table.</span></span>

#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="b6b98-318">Per aggiungere un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="b6b98-318">To add a pie chart</span></span>

1.  <span data-ttu-id="b6b98-319">In **Visualizzazioni dati** nella scheda **Inserisci** della barra multifunzione fare clic su **Grafico** , quindi su **Creazione guidata grafico**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-319">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="b6b98-320">Nella pagina Scegliere un set di dati fare clic su **ListDataset**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-320">On the Choose a dataset page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="b6b98-321">Fare clic su **Torta**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-321">Click **Pie**, and then click **Next**.</span></span>

4.  <span data-ttu-id="b6b98-322">Nella pagina Disponi campi del grafico trascinare Product in **Categorie**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-322">On the arrange chart fields page, drag Product to **Categories**.</span></span>

5.  <span data-ttu-id="b6b98-323">Trascinare Quantity in **valori**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-323">Drag Quantity to **Values**, and then click **Next**.</span></span>

6.  <span data-ttu-id="b6b98-324">Nel riquadro **Stili** della pagina **Scegliere uno stile** selezionare **Ardesia**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-324">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="b6b98-325">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-325">Click **Finish**.</span></span>

8.  <span data-ttu-id="b6b98-326">Ridimensionare il grafico visualizzato nell'angolo superiore sinistro del report in modo che abbia un'altezza di 1 1/2 pollici (4 centimetri) e una larghezza di 2 pollici (5 centimetri).</span><span class="sxs-lookup"><span data-stu-id="b6b98-326">Resize the chart that appears in the upper left corner of the report, to be 1 1/2 inches tall and 2 inches wide.</span></span>

9. <span data-ttu-id="b6b98-327">Trascinare il grafico all'interno del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b6b98-327">Drag the chart inside the rectangle.</span></span>

     <span data-ttu-id="b6b98-328">![Aggiungi grafico a torta](../../2014/tutorials/media/tutorial-addpiechart.png "Aggiungi grafico a torta")</span><span class="sxs-lookup"><span data-stu-id="b6b98-328">![Add pie chart](../../2014/tutorials/media/tutorial-addpiechart.png "Add pie chart")</span></span>

10. <span data-ttu-id="b6b98-329">Fare clic con il pulsante destro del mouse sul titolo del grafico, quindi scegliere **Proprietà titolo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-329">Right-click the chart title, and then click **Title Properties**.</span></span>

11. <span data-ttu-id="b6b98-330">In Testo del titolo nella finestra di dialogo **Proprietà titolo grafico** digitare: **le Quantità di prodotto vendute**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-330">In the **Chart Title Properties** dialog box, in Title text, type: **Product Quantities Sold**.</span></span>

12. <span data-ttu-id="b6b98-331">Fare clic sulla scheda **Tipo di carattere** , quindi nell'elenco **Dimensioni** fare clic su **10pt**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-331">Click the **Font** tab, and in the **Size** list, click **10pt**.</span></span>

13. [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-column-chart"></a><span data-ttu-id="b6b98-332">Per aggiungere un istogramma</span><span class="sxs-lookup"><span data-stu-id="b6b98-332">To add a column chart</span></span>

1.  <span data-ttu-id="b6b98-333">In **Visualizzazioni dati** nella scheda **Inserisci** della barra multifunzione fare clic su **Grafico** , quindi su **Creazione guidata grafico**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-333">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="b6b98-334">Nella pagina **Scegliere un set di dati** fare clic su **ListDataset**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-334">On the **Choose a dataset** page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="b6b98-335">Fare clic su **Colonna**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-335">Click **Column**, and then click **Next**.</span></span>

4.  <span data-ttu-id="b6b98-336">Nella pagina Disponi campi del grafico trascinare il campo Product in **categorie**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-336">On the arrange chart fields page, drag the Product field to **Categories**.</span></span>

5.  <span data-ttu-id="b6b98-337">Trascinare Sales in **Valori** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-337">Drag Sales to **Values,** and then click **Next**.</span></span>

     <span data-ttu-id="b6b98-338">I valori vengono visualizzati sull'asse verticale.</span><span class="sxs-lookup"><span data-stu-id="b6b98-338">Values display on the vertical axis.</span></span>

6.  <span data-ttu-id="b6b98-339">Nel riquadro **Stili** della pagina **Scegliere uno stile** selezionare **Ardesia**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-339">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="b6b98-340">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-340">Click **Finish**.</span></span>

     <span data-ttu-id="b6b98-341">Un istogramma verrà aggiunto all'angolo superiore sinistro del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-341">A column chart is added to the upper left corner of the report.</span></span>

8.  <span data-ttu-id="b6b98-342">Ridimensionare il grafico in modo che abbia una larghezza e un'altezza di 2 pollici (5 centimetri).</span><span class="sxs-lookup"><span data-stu-id="b6b98-342">Resize the chart to be 2 inches wide and 2 inches tall.</span></span>

9. <span data-ttu-id="b6b98-343">Trascinare il grafico all'interno del rettangolo sotto il grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="b6b98-343">Drag the chart inside the rectangle, below the pie chart.</span></span>

     <span data-ttu-id="b6b98-344">![Aggiungere un istogramma](../../2014/tutorials/media/tutorial-addcolumnchart.png "Aggiungere un istogramma")</span><span class="sxs-lookup"><span data-stu-id="b6b98-344">![Add column chart](../../2014/tutorials/media/tutorial-addcolumnchart.png "Add column chart")</span></span>

10. <span data-ttu-id="b6b98-345">Fare clic con il pulsante destro del mouse sul titolo del grafico, quindi scegliere **Proprietà titolo**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-345">Right-click the chart title and then click **Title Properties**.</span></span>

11. <span data-ttu-id="b6b98-346">In Testo del titolo nella finestra di dialogo **Proprietà titolo grafico** digitare: **le Vendite prodotto**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-346">In the **Chart Title Properties** dialog box, in Title text, type: **Product Sales**.</span></span>

12. <span data-ttu-id="b6b98-347">Fare clic sulla scheda **Tipo di carattere** , quindi nell'elenco **Dimensioni** fare clic suk **10pt**e infine fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-347">Click the **Font** tab, and in the **Size** list click **10pt**, and then click **OK**.</span></span>

13. <span data-ttu-id="b6b98-348">Nell'istogramma fare clic con il pulsante destro del mouse sull'asse verticale, quindi deselezionare **Mostra titolo asse**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-348">In the column chart, right click the vertical axis, and then deselect **Show Axis Title**.</span></span>

14. <span data-ttu-id="b6b98-349">Ripetere il passaggio 13 per l'asse orizzontale.</span><span class="sxs-lookup"><span data-stu-id="b6b98-349">Repeat step 13 for the horizontal axis.</span></span>

15. <span data-ttu-id="b6b98-350">Fare clic con il pulsante destro del mouse sulla legenda, quindi scegliere **Elimina legenda**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-350">Right click the legend, and then click **Delete Legend**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b6b98-351">La rimozione dei titoli degli assi e della legenda rende il grafico più leggibile quando è di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b6b98-351">Removing axis titles and the legend makes the chart more readable when it is a small size.</span></span>

 <span data-ttu-id="b6b98-352">![Modifica titoli del grafico e rimuovi titolo dell'asse](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Modifica titoli del grafico e rimuovi titolo dell'asse")</span><span class="sxs-lookup"><span data-stu-id="b6b98-352">![Change chart titles and remove axis title](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Change chart titles and remove axis title")</span></span>

#### <a name="to-verify-the-charts-are-inside-the-rectangle"></a><span data-ttu-id="b6b98-353">Per verificare che i grafici siano all'interno del rettangolo</span><span class="sxs-lookup"><span data-stu-id="b6b98-353">To verify the charts are inside the rectangle</span></span>

1.  <span data-ttu-id="b6b98-354">Fare clic sul rettangolo aggiunto in precedenza nel corso della lezione.</span><span class="sxs-lookup"><span data-stu-id="b6b98-354">Click the rectangle you added earlier in this lesson.</span></span>

     <span data-ttu-id="b6b98-355">La proprietà `Name` nel riquadro Proprietà indica il nome del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b6b98-355">In the Properties pane, the `Name` property displays the name of the rectangle.</span></span>

     <span data-ttu-id="b6b98-356">![Nome del rettangolo](../../2014/tutorials/media/tutorial-rectanglename.png "Nome del rettangolo")</span><span class="sxs-lookup"><span data-stu-id="b6b98-356">![Name of rectangle](../../2014/tutorials/media/tutorial-rectanglename.png "Name of rectangle")</span></span>

2.  <span data-ttu-id="b6b98-357">Fare clic sul grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="b6b98-357">Click the pie chart.</span></span>

3.  <span data-ttu-id="b6b98-358">Nel riquadro **Proprietà** verificare che la `Parent` proprietà contenga il nome del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b6b98-358">In the **Properties** pane, verify that the `Parent` property contains the name of the rectangle.</span></span>

     <span data-ttu-id="b6b98-359">![Proprietà padre per il grafico a torta](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Proprietà padre per il grafico a torta")</span><span class="sxs-lookup"><span data-stu-id="b6b98-359">![Parent property for pie chart](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Parent property for pie chart")</span></span>

4.  <span data-ttu-id="b6b98-360">Fare clic sull'istogramma e ripetere i passaggi 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="b6b98-360">Click the column chart and repeat steps 2 and 3.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b6b98-361">Se non si trovano all'interno del rettangolo, i grafici non verranno visualizzati insieme nel report visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="b6b98-361">If the charts are not inside the rectangle, the rendered report does not display the charts together.</span></span>

#### <a name="to-make-the-charts-the-same-size"></a><span data-ttu-id="b6b98-362">Per assegnare ai grafici le stesse dimensioni</span><span class="sxs-lookup"><span data-stu-id="b6b98-362">To make the charts the same size</span></span>

1.  <span data-ttu-id="b6b98-363">Fare clic sul grafico a torta, premere CTRL, quindi fare clic sull'istogramma.</span><span class="sxs-lookup"><span data-stu-id="b6b98-363">Click the pie chart, press the Ctrl key, and then click the column chart.</span></span>

2.  <span data-ttu-id="b6b98-364">Con entrambi i grafici selezionati, fare clic con il pulsante destro del mouse, scegliere **Layout**, quindi fare clic su **Assegna stessa larghezza**.</span><span class="sxs-lookup"><span data-stu-id="b6b98-364">With both charts selected, right-click, point to **Layout**, and then click **Make Same Width**.</span></span>

     <span data-ttu-id="b6b98-365">![Assegna ai grafici la stessa larghezza](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Assegna ai grafici la stessa larghezza")</span><span class="sxs-lookup"><span data-stu-id="b6b98-365">![Make chart widths the same](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Make chart widths the same")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b6b98-366">Il primo elemento selezionato determina la larghezza di tutti gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="b6b98-366">The item you click first determines the width of all the selected items.</span></span>

3.  <span data-ttu-id="b6b98-367">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="b6b98-367">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="b6b98-368">Nel report verranno visualizzati i dati di vendita riepilogativi in diagrammi a torta e istogrammi.</span><span class="sxs-lookup"><span data-stu-id="b6b98-368">The report now displays summary sales data in pie and column charts.</span></span>

 <span data-ttu-id="b6b98-369">![Esercitazione su SSRS, report in formato libero](../../2014/tutorials/media/tutorial-reportfinal.png "Esercitazione su SSRS, report in formato libero")</span><span class="sxs-lookup"><span data-stu-id="b6b98-369">![SSRS tutorial, free form report](../../2014/tutorials/media/tutorial-reportfinal.png "SSRS tutorial, free form report")</span></span>

## <a name="more-information"></a><span data-ttu-id="b6b98-370">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b6b98-370">More Information</span></span>
 <span data-ttu-id="b6b98-371">Per ulteriori informazioni sugli elenchi, vedere [tabelle, matrici ed elenchi &#40;Generatore report e ssrs&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [elenchi &#40;Generatore report e SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [aree dell'area dati tablix &#40;Generatore report e SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)e [celle, righe e colonne dell'area dati Tablix &#40;Generatore report&#41; e SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b6b98-371">For more information about lists, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="b6b98-372">Per altre informazioni sulla progettazione delle query, vedere [Finestre di progettazione query &#40;Generatore report&#41;](../../2014/reporting-services/query-designers-report-builder.md) e [Interfaccia utente di Progettazione query basata su testo &#40;Generatore report&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b6b98-372">For more information about query designers, see [Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) and [Text-based Query Designer User Interface &#40;Report Builder&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6b98-373">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6b98-373">See Also</span></span>
 <span data-ttu-id="b6b98-374">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) [Generatore report in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="b6b98-374">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span></span>


