---
title: 'Esercitazione: Formattazione di testo (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 67d8513e-8a70-464b-b87f-e91d010cfd82
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c96b500f8aa30b77c78f75ccd1342398fd44eb2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722432"
---
# <a name="tutorial-format-text-report-builder"></a><span data-ttu-id="76cc2-102">Esercitazione: Formattazione di testo (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="76cc2-102">Tutorial: Format Text (Report Builder)</span></span>
  <span data-ttu-id="76cc2-103">In questa esercitazione sarà possibile applicare una formattazione al testo in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="76cc2-103">In this tutorial, you can practice formatting text in various ways.</span></span> <span data-ttu-id="76cc2-104">Dopo avere impostato l'origine dati e il set di dati per il report vuoto, sarà possibile scegliere i passaggi che si desidera esplorare.</span><span class="sxs-lookup"><span data-stu-id="76cc2-104">After you set up the blank report with the data source and dataset, you can pick and choose the steps that you want to explore.</span></span>  
  
 <span data-ttu-id="76cc2-105">Nell'immagine seguente viene illustrato un report simile a quello che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="76cc2-105">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="76cc2-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span><span class="sxs-lookup"><span data-stu-id="76cc2-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span></span>  
  
 <span data-ttu-id="76cc2-107">In un passaggio si introdurrà intenzionalmente un errore, in modo da comprenderne gli effetti.</span><span class="sxs-lookup"><span data-stu-id="76cc2-107">In one step, you make a mistake on purpose so you can see why it is a mistake.</span></span> <span data-ttu-id="76cc2-108">Si correggerà quindi l'errore per ottenere il risultato desiderato.</span><span class="sxs-lookup"><span data-stu-id="76cc2-108">Then you correct the mistake to achieve the desired effect.</span></span>  
  
 <span data-ttu-id="76cc2-109">Una versione avanzata del report che verrà creato in questa esercitazione è disponibile come report di esempio di Generatore report di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76cc2-109">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="76cc2-110">Per ulteriori informazioni sul download di questo report di esempio e di altri, vedere [Generatore report report di esempio](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="76cc2-110">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="76cc2-111">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="76cc2-111">What You Will Learn</span></span>  
  
### <a name="set-up-the-report"></a><span data-ttu-id="76cc2-112">Impostazione del report</span><span class="sxs-lookup"><span data-stu-id="76cc2-112">Set Up the Report</span></span>  
 1. [<span data-ttu-id="76cc2-113">Creare un report vuoto con un'origine dati e un set di dati</span><span class="sxs-lookup"><span data-stu-id="76cc2-113">Create a Blank Report with a Data Source and Dataset</span></span>](#CreateReport)  
  
 2. [<span data-ttu-id="76cc2-114">Aggiungere un campo all'area di progettazione del report (introducendo un errore e quindi correggendolo)</span><span class="sxs-lookup"><span data-stu-id="76cc2-114">Add a Field to the Report Design Surface (Incorrectly, then Correctly)</span></span>](#AddField)  
  
 3. [<span data-ttu-id="76cc2-115">Aggiungere una tabella al report Area di progettazione</span><span class="sxs-lookup"><span data-stu-id="76cc2-115">Add a Table to the Report Design Surface</span></span>](#AddTable)  
  
### <a name="pick-and-choose"></a><span data-ttu-id="76cc2-116">Effettuare una scelta</span><span class="sxs-lookup"><span data-stu-id="76cc2-116">Pick and Choose</span></span>  
 [<span data-ttu-id="76cc2-117">Aggiungere un collegamento ipertestuale al report</span><span class="sxs-lookup"><span data-stu-id="76cc2-117">Add a Hyperlink to the Report</span></span>](#AddHyperlink)  
  
 [<span data-ttu-id="76cc2-118">Ruotare il testo nel report</span><span class="sxs-lookup"><span data-stu-id="76cc2-118">Rotate Text in the Report</span></span>](#RotateText)  
  
 [<span data-ttu-id="76cc2-119">Visualizzazione del testo con formattazione HTML</span><span class="sxs-lookup"><span data-stu-id="76cc2-119">Displaying Text with HTML Formatting</span></span>](#FormatHTML)  
  
 [<span data-ttu-id="76cc2-120">Formattare la valuta</span><span class="sxs-lookup"><span data-stu-id="76cc2-120">Format Currency</span></span>](#FormatCurrency)  
  
 [<span data-ttu-id="76cc2-121">Salva il report</span><span class="sxs-lookup"><span data-stu-id="76cc2-121">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="76cc2-122">Il tempo stimato per il completare l'esercitazione è di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="76cc2-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76cc2-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="76cc2-123">Requirements</span></span>  
 <span data-ttu-id="76cc2-124">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="76cc2-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="create-a-blank-report-with-a-data-source-and-dataset"></a><a name="CreateReport"></a><span data-ttu-id="76cc2-125">Creare un report vuoto con un'origine dati e un set di dati</span><span class="sxs-lookup"><span data-stu-id="76cc2-125">Create a Blank Report with a Data Source and Dataset</span></span>  
  
#### <a name="to-create-a-blank-report"></a><span data-ttu-id="76cc2-126">Per creare un report vuoto</span><span class="sxs-lookup"><span data-stu-id="76cc2-126">To create a blank report</span></span>  
  
1.  <span data-ttu-id="76cc2-127">Fare clic sul pulsante **Start**, scegliere **programmi**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Generatore report**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-127">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76cc2-128">Verrà visualizzata la finestra di dialogo **Riquadro attività iniziale** .</span><span class="sxs-lookup"><span data-stu-id="76cc2-128">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="76cc2-129">In caso contrario, fare clic sul pulsante Generatore report, quindi su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-129">If it does not, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="76cc2-130">Nel riquadro sinistro della finestra di dialogo **Riquadro attività iniziale** verificare che l'opzione **Nuovo report** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="76cc2-130">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="76cc2-131">Nel riquadro destro fare clic su **Report vuoto**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-131">In the right pane, click **Blank Report**.</span></span>  
  
#### <a name="to-create-a-data-source"></a><span data-ttu-id="76cc2-132">Per creare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="76cc2-132">To create a data source</span></span>  
  
1.  <span data-ttu-id="76cc2-133">Nel riquadro dei dati del report fare clic su **nuovo**e quindi su **origine dati**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-133">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="76cc2-134">Nella casella **Nome** digitare: **TextDataSource**</span><span class="sxs-lookup"><span data-stu-id="76cc2-134">In the **Name** box, type: **TextDataSource**</span></span>  
  
3.  <span data-ttu-id="76cc2-135">Fare clic su **Usa una connessione incorporata nel report**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-135">Click **Use a connection embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="76cc2-136">Verificare che il tipo di connessione sia Microsoft SQL Server, quindi nella casella **stringa di connessione** digitare: \*\*Data Source = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="76cc2-136">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76cc2-137">L'espressione \<servername>, ad esempio Report001, indica un computer in cui è installata un'istanza del motore di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="76cc2-137">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="76cc2-138">Per questa esercitazione non sono necessari dati specifici. È sufficiente una connessione a un database di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76cc2-138">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="76cc2-139">Se in **Connessioni a origini dati**è già disponibile una connessione, è possibile selezionarla e passare alla procedura successiva, ovvero "Per creare un set di dati".</span><span class="sxs-lookup"><span data-stu-id="76cc2-139">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to the next procedure, "To create a dataset."</span></span> <span data-ttu-id="76cc2-140">Per altre informazioni, vedere [Modalità alternative di acquisizione di una connessione dati &#40;Generatore report&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="76cc2-140">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-create-a-dataset"></a><span data-ttu-id="76cc2-141">Per creare un set di dati</span><span class="sxs-lookup"><span data-stu-id="76cc2-141">To create a dataset</span></span>  
  
1.  <span data-ttu-id="76cc2-142">Nel riquadro dei dati del report fare clic su **Nuovo**, quindi su **Set di dati**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-142">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>  
  
2.  <span data-ttu-id="76cc2-143">Verificare che l'origine dati sia **TextDataSource**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-143">Verify that the data source is **TextDataSource**.</span></span>  
  
3.  <span data-ttu-id="76cc2-144">Nella casella **Nome** digitare: **TextDataset**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-144">In the **Name** box, type: **TextDataset.**</span></span>  
  
4.  <span data-ttu-id="76cc2-145">Verificare che il tipo di query **Testo** sia selezionato, quindi fare clic su **Progettazione query**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-145">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>  
  
5.  <span data-ttu-id="76cc2-146">Fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-146">Click **Edit as Text**.</span></span>  
  
6.  <span data-ttu-id="76cc2-147">Incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="76cc2-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    ```  
  
7.  <span data-ttu-id="76cc2-148">Scegliere Esegui (**!**) per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="76cc2-148">Click Run (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="76cc2-149">I risultati della query corrispondono ai dati disponibili per la visualizzazione nel report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-149">The query results are the data available to display in your report.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="add-a-field-to-the-report-design-surface"></a><a name="AddField"></a><span data-ttu-id="76cc2-150">Aggiungere un campo al report Area di progettazione</span><span class="sxs-lookup"><span data-stu-id="76cc2-150">Add a Field to the Report Design Surface</span></span>  
 <span data-ttu-id="76cc2-151">Se si desidera visualizzare un campo del set di dati in un report, è probabile che si scelga innanzitutto di trascinarlo direttamente nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="76cc2-151">If you want a field from your dataset to appear in a report, your first impulse may be to drag it directly to the design surface.</span></span> <span data-ttu-id="76cc2-152">In questo esercizio viene indicato perché questo modo di procedere non è corretto e quale operazione è invece necessario eseguire.</span><span class="sxs-lookup"><span data-stu-id="76cc2-152">This exercise points out why that doesn't work and what to do instead.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-wrong-result"></a><span data-ttu-id="76cc2-153">Per aggiungere un campo al report (e ottenere il risultato sbagliato)</span><span class="sxs-lookup"><span data-stu-id="76cc2-153">To add a field to the report (and get the wrong result)</span></span>  
  
1.  <span data-ttu-id="76cc2-154">Trascinare il campo **FullName** dal riquadro Dati report nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="76cc2-154">Drag the **FullName** field from the Report Data pane to the design surface.</span></span>  
  
     <span data-ttu-id="76cc2-155">Generatore report crea una casella di testo contenente un'espressione rappresentata da \<Expr>.</span><span class="sxs-lookup"><span data-stu-id="76cc2-155">Report Builder creates a text box with an expression in it, represented as \<Expr>.</span></span>  
  
2.  <span data-ttu-id="76cc2-156">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-156">Click **Run**.</span></span>  
  
     <span data-ttu-id="76cc2-157">Si noti che è presente un solo record, **Fernando Ross**, che è in ordine alfabetico il primo record nella query.</span><span class="sxs-lookup"><span data-stu-id="76cc2-157">Note that there is just one record, **Fernando Ross**, which is alphabetically the first record in the query.</span></span> <span data-ttu-id="76cc2-158">Il campo non viene ripetuto per visualizzare gli altri record di tale campo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-158">The field does not repeat to show the other records in that field.</span></span>  
  
3.  <span data-ttu-id="76cc2-159">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="76cc2-159">Click **Design** to return to design view.</span></span>  
  
4.  <span data-ttu-id="76cc2-160">Selezionare l'espressione \<Expr> nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-160">Select the expression \<Expr> in the text box.</span></span>  
  
5.  <span data-ttu-id="76cc2-161">Nel riquadro Proprietà della proprietà **Value** verrà visualizzato quanto segue (se il riquadro Proprietà non è visualizzato, selezionare **Proprietà** nella scheda **Visualizza**):</span><span class="sxs-lookup"><span data-stu-id="76cc2-161">In the Properties pane, for the **Value** property, you see the following (if you don't see the Properties pane, on the **View** tab, check **Properties**):</span></span>  
  
    ```  
    =First(Fields!FullName.Value, "TextDataSet")  
    ```  
  
     <span data-ttu-id="76cc2-162">La funzione `First` è progettata per recuperare solo il primo valore in un campo, così come è avvenuto.</span><span class="sxs-lookup"><span data-stu-id="76cc2-162">The `First` function is designed to retrieve only the first value in a field, and that is what it has done.</span></span>  
  
     <span data-ttu-id="76cc2-163">Il trascinamento del campo direttamente nell'area di progettazione ha determinato la creazione di una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-163">Dragging the field directly to the design surface created a text box.</span></span> <span data-ttu-id="76cc2-164">Le caselle di testo non sono di per sé aree dati e pertanto non consentono di visualizzare i dati di un set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-164">Text boxes by themselves are not data regions, so they do not display data from a report dataset.</span></span> <span data-ttu-id="76cc2-165">Le caselle di testo incluse in aree dati, ad esempio tabelle, matrici ed elenchi, consentono invece di visualizzare dati.</span><span class="sxs-lookup"><span data-stu-id="76cc2-165">Text boxes in data regions, such as tables, matrices, and lists, do display data.</span></span>  
  
6.  <span data-ttu-id="76cc2-166">Selezionare la casella di testo (se l'espressione è stata selezionata, premere ESC per selezionare la casella di testo), quindi premere CANC.</span><span class="sxs-lookup"><span data-stu-id="76cc2-166">Select the text box (if you have the expression selected, press ESC to select the text box), and press the DELETE key.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-right-result"></a><span data-ttu-id="76cc2-167">Per aggiungere un campo al report (e ottenere il risultato corretto)</span><span class="sxs-lookup"><span data-stu-id="76cc2-167">To add a field to the report (and get the right result)</span></span>  
  
1.  <span data-ttu-id="76cc2-168">Fare clic su **Elenco** nell'area **Aree dati** della scheda **Inserisci**sulla barra multifunzione .</span><span class="sxs-lookup"><span data-stu-id="76cc2-168">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List**.</span></span> <span data-ttu-id="76cc2-169">Fare clic nell'area di progettazione, quindi trascinare il mouse per creare una casella di circa 2 pollici (5 centimetri) di larghezza e 1 pollice (2,5 centimetri) di altezza.</span><span class="sxs-lookup"><span data-stu-id="76cc2-169">Click the design surface, and then drag to create a box that about two inches wide and one inch tall.</span></span>  
  
2.  <span data-ttu-id="76cc2-170">Trascinare il campo **FullName** dal riquadro Dati report nella casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-170">Drag the **FullName** field from the Report Data pane to the list box.</span></span>  
  
     <span data-ttu-id="76cc2-171">Questa volta Generatore report crea una casella di testo contenente l'espressione `[FullName]` .</span><span class="sxs-lookup"><span data-stu-id="76cc2-171">This time Report Builder creates a text box with the expression `[FullName]` in it.</span></span>  
  
3.  <span data-ttu-id="76cc2-172">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-172">Click **Run**.</span></span>  
  
     <span data-ttu-id="76cc2-173">Si noti che in questo caso le casella viene ripetuta per visualizzare tutti i record nella query.</span><span class="sxs-lookup"><span data-stu-id="76cc2-173">Note that this time the box repeats to show all the records in the query.</span></span>  
  
4.  <span data-ttu-id="76cc2-174">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="76cc2-174">Click **Design** to return to design view.</span></span>  
  
5.  <span data-ttu-id="76cc2-175">Selezionare l'espressione nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-175">Select the expression in the text box.</span></span>  
  
6.  <span data-ttu-id="76cc2-176">Nel riquadro Proprietà della proprietà **Value** verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="76cc2-176">In the Properties pane, for the **Value** property, you see the following:</span></span>  
  
    ```  
    =Fields!FullName.Value  
    ```  
  
     <span data-ttu-id="76cc2-177">Il trascinamento della casella di testo nell'area dati dell'elenco determina la visualizzazione dei dati inclusi nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="76cc2-177">By dragging the text box to the list data region, you display the data that is in the dataset.</span></span>  
  
7.  <span data-ttu-id="76cc2-178">Selezionare la casella di riepilogo e premere CANC.</span><span class="sxs-lookup"><span data-stu-id="76cc2-178">Select the list box and press the DELETE key.</span></span>  
  
##  <a name="add-a-table-to-the-report-design-surface"></a><a name="AddTable"></a><span data-ttu-id="76cc2-179">Aggiungere una tabella al report Area di progettazione</span><span class="sxs-lookup"><span data-stu-id="76cc2-179">Add a Table to the Report Design Surface</span></span>  
 <span data-ttu-id="76cc2-180">Creare questa tabella in modo da disporre di un elemento in cui inserire i collegamenti ipertestuali e il testo ruotato.</span><span class="sxs-lookup"><span data-stu-id="76cc2-180">Create this table so that you'll have a place to put hyperlinks and rotated text.</span></span>  
  
#### <a name="to-add-a-table-to-the-report"></a><span data-ttu-id="76cc2-181">Per aggiungere una tabella al report</span><span class="sxs-lookup"><span data-stu-id="76cc2-181">To add a table to the report</span></span>  
  
1.  <span data-ttu-id="76cc2-182">Scegliere **tabella**dal menu **Inserisci** , quindi fare clic su **creazione guidata tabella**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-182">On the **Insert** menu, click **Table**, and then click **Table Wizard**.</span></span>  
  
2.  <span data-ttu-id="76cc2-183">Nella pagina **scegliere un set di dati** della creazione guidata tabella o matrice fare clic **su Scegli un set di dati esistente in questo report o un set di dati condiviso**, quindi fare clic su **TextDataset (in questo report)**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-183">On the **Choose a dataset** page of the New Table or Matrix wizard, click **Choose an existing dataset in this report or a shared dataset**, and click **TextDataset (in this Report)**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="76cc2-184">Nella pagina **Disponi campi** trascinare i campi **Territory**, **linkText**e **Product** in gruppi di **righe**, trascinare il campo **Sales** in **valori**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-184">On the **Arrange fields** page, drag the **Territory**, **LinkText**, and **Product** fields to **Row groups**, drag the **Sales** field to **Values**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="76cc2-185">Nella pagina **scegliere il layout** deselezionare la casella di controllo **Espandi/Comprimi gruppi** , in modo che sia possibile visualizzare l'intera tabella, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-185">On the **Choose the layout** page, clear the **Expand/collapse groups** check box so you can see the whole table, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="76cc2-186">Nella pagina **scegliere uno stile** fare clic su **Slate**, quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-186">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="76cc2-187">Trascinare la tabella in modo da posizionarla sotto il blocco del titolo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-187">Drag the table so it is below the title block.</span></span>  
  
7.  <span data-ttu-id="76cc2-188">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-188">Click **Run**.</span></span>  
  
     <span data-ttu-id="76cc2-189">La tabella ha un aspetto corretto, ma dispone di due righe dei totali.</span><span class="sxs-lookup"><span data-stu-id="76cc2-189">The table looks OK, but it has two Total rows.</span></span> <span data-ttu-id="76cc2-190">Per il campo **linkText** non è necessaria una riga del totale.</span><span class="sxs-lookup"><span data-stu-id="76cc2-190">The **LinkText** field doesn't need a Total row.</span></span>  
  
8.  <span data-ttu-id="76cc2-191">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="76cc2-191">Click **Design** to return to design view.</span></span>  
  
9. <span data-ttu-id="76cc2-192">Fare clic con il pulsante destro del mouse sulla casella di testo che contiene `[LinkText]` e scegliere **Suddividi celle**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-192">Right-click the text box that contains `[LinkText]`, and click **Split Cells**.</span></span>  
  
10. <span data-ttu-id="76cc2-193">Selezionare la cella vuota sotto la `[LinkText]` cella, quindi tenere premuto il tasto MAIUSC e selezionare le due celle a destra: la cella **Total** nella colonna **Product** e la `[Sum(Sales)]` cella nella colonna **Sales** .</span><span class="sxs-lookup"><span data-stu-id="76cc2-193">Select the empty cell below the `[LinkText]` cell, and then hold down the SHIFT key and select the two cells to its right: the **Total** cell in the **Product** column and the `[Sum(Sales)]` cell in the **Sales** column.</span></span>  
  
11. <span data-ttu-id="76cc2-194">Con queste tre celle selezionate, fare clic con il pulsante destro del mouse su una di queste celle e scegliere **Elimina riga**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-194">With those three cells selected, right-click one of those cells and click **Delete Row**.</span></span>  
  
12. <span data-ttu-id="76cc2-195">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-195">Click **Run**.</span></span>  
  
##  <a name="add-a-hyperlink-to-the-report"></a><a name="AddHyperlink"></a><span data-ttu-id="76cc2-196">Aggiungere un collegamento ipertestuale al report</span><span class="sxs-lookup"><span data-stu-id="76cc2-196">Add a Hyperlink to the Report</span></span>  
 <span data-ttu-id="76cc2-197">In questa sezione si aggiungerà un collegamento ipertestuale al testo incluso nella tabella creata nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="76cc2-197">In this section, you add a hyperlink to text in the table from the previous section.</span></span>  
  
#### <a name="to-add-a-hyperlink-to-the-report"></a><span data-ttu-id="76cc2-198">Per aggiungere un collegamento ipertestuale al report</span><span class="sxs-lookup"><span data-stu-id="76cc2-198">To add a hyperlink to the report</span></span>  
  
1.  <span data-ttu-id="76cc2-199">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="76cc2-199">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="76cc2-200">Fare clic con il pulsante destro del mouse sulla cella contenente `[LinkText]`, quindi scegliere **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-200">Right-click in the cell containing `[LinkText]`, and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="76cc2-201">Nella casella **Proprietà casella di testo** fare clic su **azione**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-201">In the **Text Box Properties** box, click **Action**.</span></span>  
  
4.  <span data-ttu-id="76cc2-202">Fare clic su **Vai a URL**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-202">Click **Go to URL**.</span></span>  
  
5.  <span data-ttu-id="76cc2-203">Nella casella **Seleziona URL** fare clic su **[URL]**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-203">In the **Select URL** box, click **[URL]**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="76cc2-204">Si noti che il testo non presenta alcuna differenza.</span><span class="sxs-lookup"><span data-stu-id="76cc2-204">Note that the text does not look any different.</span></span> <span data-ttu-id="76cc2-205">È necessario renderlo simile al testo di un collegamento.</span><span class="sxs-lookup"><span data-stu-id="76cc2-205">You need to make it look like link text.</span></span>  
  
7.  <span data-ttu-id="76cc2-206">Selezionare `[LinkText]`.</span><span class="sxs-lookup"><span data-stu-id="76cc2-206">Select `[LinkText]`.</span></span>  
  
8.  <span data-ttu-id="76cc2-207">Nella sezione **carattere** della scheda **Home** fare clic sul pulsante **sottolineatura** , quindi fare clic sulla freccia a discesa accanto al pulsante **colore** e quindi su **blu**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-207">In the **Font** section of the **Home** tab, click the **Underline** button, and then click the drop-down arrow next to the **Color** button, and click **Blue**.</span></span>  
  
9. <span data-ttu-id="76cc2-208">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-208">Click **Run**.</span></span>  
  
     <span data-ttu-id="76cc2-209">L'aspetto del testo è ora simile a quello di un collegamento.</span><span class="sxs-lookup"><span data-stu-id="76cc2-209">The text now looks like a link.</span></span>  
  
10. <span data-ttu-id="76cc2-210">Fare clic su un collegamento.</span><span class="sxs-lookup"><span data-stu-id="76cc2-210">Click a link.</span></span> <span data-ttu-id="76cc2-211">Se il computer è connesso a Internet, in una finestra del browser verrà aperto un argomento della Guida di Generatore report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-211">If the computer is connected to the Internet, a browser will open to a Report Builder Help topic.</span></span>  
  
##  <a name="rotate-text-in-the-report"></a><a name="RotateText"></a><span data-ttu-id="76cc2-212">Ruotare il testo nel report</span><span class="sxs-lookup"><span data-stu-id="76cc2-212">Rotate Text in the Report</span></span>  
 <span data-ttu-id="76cc2-213">In questa sezione si ruoterà parte del testo incluso nella tabella creata nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="76cc2-213">In this section, you rotate some of the text in the table from the previous sections.</span></span>  
  
#### <a name="to-rotate-text"></a><span data-ttu-id="76cc2-214">Per ruotare il testo</span><span class="sxs-lookup"><span data-stu-id="76cc2-214">To rotate text</span></span>  
  
1.  <span data-ttu-id="76cc2-215">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="76cc2-215">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="76cc2-216">Fare clic nella cella che contiene `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="76cc2-216">Click in the cell containing `[Territory].`</span></span>  
  
3.  <span data-ttu-id="76cc2-217">Nella scheda **Home** della sezione **Carattere** fare clic sul pulsante **Grassetto** .</span><span class="sxs-lookup"><span data-stu-id="76cc2-217">On the **Home** tab in the **Font** section, click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="76cc2-218">Se il riquadro Proprietà non è visualizzato, selezionare la casella di controllo **Proprietà** nella scheda **Vista** .</span><span class="sxs-lookup"><span data-stu-id="76cc2-218">If the Properties pane is not open, on the **View** tab, select the **Properties** check box.</span></span>  
  
5.  <span data-ttu-id="76cc2-219">Individuare la proprietà WritingMode nel riquadro proprietà.</span><span class="sxs-lookup"><span data-stu-id="76cc2-219">Locate the WritingMode property in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76cc2-220">Se le proprietà nel riquadro Proprietà sono organizzate in categorie, WritingMode si trova nella categoria **Localizzazione** .</span><span class="sxs-lookup"><span data-stu-id="76cc2-220">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span> <span data-ttu-id="76cc2-221">Assicurarsi di aver selezionato la cella e non il testo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-221">Be sure you have selected the cell and not the text.</span></span> <span data-ttu-id="76cc2-222">WritingMode è una proprietà della casella di testo, non del testo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-222">WritingMode is a property of the text box, not of the text.</span></span>  
  
6.  <span data-ttu-id="76cc2-223">Nella casella di riepilogo fare clic su **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-223">In the list box, click **Rotate270**.</span></span>  
  
7.  <span data-ttu-id="76cc2-224">Nella sezione **paragrafo** della scheda **Home** fare clic sui pulsanti **centrale** e **centrale** per individuare il testo al centro della cella sia verticalmente che orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="76cc2-224">On the **Home** tab in the **Paragraph** section, click the **Middle** and **Center** buttons to locate the text in the center of the cell both vertically and horizontally.</span></span>  
  
8.  <span data-ttu-id="76cc2-225">Fare clic su Esegui (**!**).</span><span class="sxs-lookup"><span data-stu-id="76cc2-225">Click Run (**!**).</span></span>  
  
 <span data-ttu-id="76cc2-226">Il testo incluso nella cella `[Territory]` scorre ora verticalmente dal basso verso l'alto delle celle.</span><span class="sxs-lookup"><span data-stu-id="76cc2-226">Now the text in the `[Territory]` cell runs vertically from the bottom to the top of the cells.</span></span>  
  
##  <a name="displaying-text-with-html-formatting"></a><a name="FormatHTML"></a><span data-ttu-id="76cc2-227">Visualizzazione del testo con formattazione HTML</span><span class="sxs-lookup"><span data-stu-id="76cc2-227">Displaying Text with HTML Formatting</span></span>  
  
#### <a name="to-display-text-formatted-as-html"></a><span data-ttu-id="76cc2-228">Per visualizzare testo formattato come HTML</span><span class="sxs-lookup"><span data-stu-id="76cc2-228">To display text formatted as HTML</span></span>  
  
1.  <span data-ttu-id="76cc2-229">Fare clic su **progettazione** per passare alla visualizzazione progettazione.</span><span class="sxs-lookup"><span data-stu-id="76cc2-229">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="76cc2-230">Nella scheda **Inserisci** fare clic su **Casella di testo**, quindi nell'area di progettazione fare clic e trascinare il mouse per creare, sotto la tabella, una casella di testo di circa 10 centimetri di larghezza e 8 centimetri di altezza.</span><span class="sxs-lookup"><span data-stu-id="76cc2-230">On the **Insert** tab, click **Text Box**, and then on the design surface, click and drag to create a text box under the table, about four inches wide and three inches tall.</span></span>  
  
3.  <span data-ttu-id="76cc2-231">Copiare questo testo e incollarlo nella casella di testo:</span><span class="sxs-lookup"><span data-stu-id="76cc2-231">Copy this text and paste it into the text box:</span></span>  
  
    ```  
    <h4>Limitations of cascading style sheet attributes</h4>  
          <p>Only a basic set of <b>cascading style sheet (CSS)</b> attributes are defined:</p>  
          <ul><li>  
              text-align, text-indent  
            </li><li>  
              font-family, font-size  
            </li><li>  
              color  
            </li><li>  
              padding, padding-bottom, padding-top, padding-right, padding-left  
            </li><li>  
              font-weight  
            </li></ul>  
    ```  
  
4.  <span data-ttu-id="76cc2-232">Selezionare tutto il testo presente nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="76cc2-232">Select all of the text in the text box.</span></span>  
  
     <span data-ttu-id="76cc2-233">Poiché questa è una proprietà del testo e non della casella di testo, in una casella di testo è possibile avere una combinazione di testo normale e di testo in cui vengono utilizzati tag HTML come stili.</span><span class="sxs-lookup"><span data-stu-id="76cc2-233">This is a property of the text, not the text box, so in one text box you could have a mixture of plain text and text that uses HTML tags as styles.</span></span>  
  
5.  <span data-ttu-id="76cc2-234">Fare clic con il pulsante destro del mouse su tutto il testo selezionato, quindi scegliere **Proprietà testo**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-234">Right-click all of the selected text and click **Text Properties**.</span></span>  
  
6.  <span data-ttu-id="76cc2-235">In **tipo di markup**della pagina **generale** fare clic su **HTML-interpreta i tag HTML come stili**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-235">On the **General** page, under **Markup type**, click **HTML - Interpret HTML tags as styles**.</span></span>  
  
7.  <span data-ttu-id="76cc2-236">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-236">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="76cc2-237">Fare clic su Esegui (**!**) per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-237">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="76cc2-238">Il testo nella casella di testo viene visualizzato come un'intestazione, un paragrafo e un elenco puntato.</span><span class="sxs-lookup"><span data-stu-id="76cc2-238">The text in the text box is displayed as a heading, paragraph, and bulleted list.</span></span>  
  
##  <a name="format-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="76cc2-239">Formattare la valuta</span><span class="sxs-lookup"><span data-stu-id="76cc2-239">Format Currency</span></span>  
  
#### <a name="to-format-numbers-as-currency"></a><span data-ttu-id="76cc2-240">Per formattare i numeri come valuta</span><span class="sxs-lookup"><span data-stu-id="76cc2-240">To format numbers as currency</span></span>  
  
1.  <span data-ttu-id="76cc2-241">Fare clic su **progettazione** per passare alla visualizzazione progettazione.</span><span class="sxs-lookup"><span data-stu-id="76cc2-241">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="76cc2-242">Fare clic sulla cella prima cella tabella contenente `[Sum(Sales)]`, tenere premuto MAIUSC e fare clic sull'ultima cella della tabella contenente `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="76cc2-242">Click the top table cell that contains `[Sum(Sales)]`, hold down the SHIFT key, and click the bottom table cell that contains `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="76cc2-243">Nel gruppo **Numero** della scheda **Home** fare clic sul pulsante **Valuta** .</span><span class="sxs-lookup"><span data-stu-id="76cc2-243">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>  
  
4.  <span data-ttu-id="76cc2-244">Opzionale Nel gruppo **numero** della scheda **Home** fare clic sul pulsante **Stili segnaposto** e fare clic su **valori di esempio** per vedere come verranno formattati i numeri.</span><span class="sxs-lookup"><span data-stu-id="76cc2-244">(Optional) On the **Home** tab, in the **Number** group, click the **Placeholder Styles** button and click **Sample Values** to see how the numbers will be formatted.</span></span>  
  
5.  <span data-ttu-id="76cc2-245">(Facoltativo) Nel gruppo **Numero** della scheda **Home** fare clic due volte sul pulsante **Diminuisci decimali** per visualizzare le cifre in dollari senza centesimi.</span><span class="sxs-lookup"><span data-stu-id="76cc2-245">(Optional) On the **Home** tab, in the **Number** group, click the **Decrease Decimals** button twice to display dollar figures with no cents.</span></span>  
  
6.  <span data-ttu-id="76cc2-246">Fare clic su Esegui (**!**) per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-246">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="76cc2-247">Nel report verranno visualizzati i dati formattati che rendono più facile la lettura.</span><span class="sxs-lookup"><span data-stu-id="76cc2-247">The report now displays formatted data and is easier to read.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="76cc2-248">Salva il report</span><span class="sxs-lookup"><span data-stu-id="76cc2-248">Save the Report</span></span>  
 <span data-ttu-id="76cc2-249">È possibile salvare i report in un server di report, in una raccolta di SharePoint o nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="76cc2-249">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="76cc2-250">In questa esercitazione il report verrà salvato in un server di report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-250">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="76cc2-251">Se non si dispone dell'accesso a un server di report, sarà possibile salvare il report nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="76cc2-251">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="76cc2-252">Per salvare il report in un server di report</span><span class="sxs-lookup"><span data-stu-id="76cc2-252">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="76cc2-253">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-253">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="76cc2-254">Fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-254">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="76cc2-255">Selezionare o digitare il nome del server di report per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-255">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="76cc2-256">Verrà visualizzato il messaggio "Connessione al server di report".</span><span class="sxs-lookup"><span data-stu-id="76cc2-256">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="76cc2-257">Al termine della connessione, verrà visualizzato il contenuto della cartella di report specificata dall'amministratore del server di report come posizione predefinita per i report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-257">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="76cc2-258">In **Nome**sostituire il nome predefinito con un nome a scelta.</span><span class="sxs-lookup"><span data-stu-id="76cc2-258">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
5.  <span data-ttu-id="76cc2-259">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-259">Click **Save**.</span></span>  
  
 <span data-ttu-id="76cc2-260">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-260">The report is saved to the report server.</span></span> <span data-ttu-id="76cc2-261">Il nome del server di report al quale si è connessi verrà visualizzato sulla barra di stato nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="76cc2-261">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="76cc2-262">Per salvare il report nel computer</span><span class="sxs-lookup"><span data-stu-id="76cc2-262">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="76cc2-263">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-263">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="76cc2-264">Fare clic su **Desktop**, **Documenti**o **Risorse del computer**, quindi selezionare la cartella in cui si desidera salvare il report.</span><span class="sxs-lookup"><span data-stu-id="76cc2-264">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="76cc2-265">In **Nome**sostituire il nome predefinito con un nome a scelta.</span><span class="sxs-lookup"><span data-stu-id="76cc2-265">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
4.  <span data-ttu-id="76cc2-266">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="76cc2-266">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="76cc2-267">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="76cc2-267">Next Steps</span></span>  
 <span data-ttu-id="76cc2-268">Sono disponibili diversi modi per formattare il testo in Generatore report [esercitazione: creazione di un report in formato libero &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contiene altri esempi.</span><span class="sxs-lookup"><span data-stu-id="76cc2-268">There are many ways to format text in Report Builder [Tutorial: Creating a Free Form Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contains more examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76cc2-269">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76cc2-269">See Also</span></span>  
 <span data-ttu-id="76cc2-270">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="76cc2-270">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="76cc2-271">[Formattazione degli elementi del report &#40;Generatore report e SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76cc2-271">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="76cc2-272">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="76cc2-272">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
