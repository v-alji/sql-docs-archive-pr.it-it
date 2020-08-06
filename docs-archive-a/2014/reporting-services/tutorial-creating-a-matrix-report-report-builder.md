---
title: 'Esercitazione: Creazione di un report tabella semplice (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9ee19c2e-2a8c-4bb0-9274-04a5812c2e96
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3df32098d9e6400931ba2a88b2ffd22d6e015a62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722443"
---
# <a name="tutorial-creating-a-matrix-report-report-builder"></a><span data-ttu-id="8129e-102">Esercitazione: Creazione di un report matrice (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="8129e-102">Tutorial: Creating a Matrix Report (Report Builder)</span></span>
  <span data-ttu-id="8129e-103">In questa esercitazione viene illustrato come creare un report matrice semplice basato su dati di vendita di esempio.</span><span class="sxs-lookup"><span data-stu-id="8129e-103">This tutorial teaches you how to create a basic matrix report based on sample sales data.</span></span> <span data-ttu-id="8129e-104">La matrice presenta gruppi di righe e di colonne annidati, nonché un gruppo di colonne adiacente.</span><span class="sxs-lookup"><span data-stu-id="8129e-104">The matrix has nested row and column groups and an adjacent column group.</span></span> <span data-ttu-id="8129e-105">Verrà inoltre illustrato come formattare le colonne e ruotare il testo.</span><span class="sxs-lookup"><span data-stu-id="8129e-105">You will also learn how to format columns and rotate text.</span></span> <span data-ttu-id="8129e-106">Nell'immagine seguente viene illustrato un report simile a quello che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="8129e-106">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="8129e-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="8129e-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span></span>  
  
 <span data-ttu-id="8129e-108">Una versione avanzata del report che verrà creato in questa esercitazione è disponibile come report di esempio di Generatore report di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8129e-108">An enhanced version of the report you will create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="8129e-109">Per ulteriori informazioni sul download di questo report di esempio e di altri, vedere [Generatore report report di esempio](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="8129e-109">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="8129e-110">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="8129e-110">What You Will Learn</span></span>  
 <span data-ttu-id="8129e-111">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="8129e-111">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="8129e-112">Creare un report matrice e un set di dati tramite la Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="8129e-112">Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>](#CreateMatrix)  
  
2.  [<span data-ttu-id="8129e-113">Organizzare i dati e scegliere il layout e lo stile tramite la Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="8129e-113">Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>](#Groups)  
  
3.  [<span data-ttu-id="8129e-114">Formattare i dati</span><span class="sxs-lookup"><span data-stu-id="8129e-114">Format Data</span></span>](#FormatData)  
  
4.  [<span data-ttu-id="8129e-115">Aggiungere un gruppo di colonne adiacente</span><span class="sxs-lookup"><span data-stu-id="8129e-115">Add Adjacent Column Group</span></span>](#AdjacentGroup)  
  
5.  [<span data-ttu-id="8129e-116">Modificare la larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="8129e-116">Change Column Widths</span></span>](#Width)  
  
6.  [<span data-ttu-id="8129e-117">Unire le celle della matrice</span><span class="sxs-lookup"><span data-stu-id="8129e-117">Merge Matrix Cells</span></span>](#MergeCells)  
  
7.  [<span data-ttu-id="8129e-118">Aggiungere un'intestazione e un titolo al report</span><span class="sxs-lookup"><span data-stu-id="8129e-118">Add a Report Header and Report Title</span></span>](#HeaderTitle)  
  
8.  [<span data-ttu-id="8129e-119">Salva il report</span><span class="sxs-lookup"><span data-stu-id="8129e-119">Save the Report</span></span>](#Save)  
  
### <a name="other-optional-step"></a><span data-ttu-id="8129e-120">Altro passaggio facoltativo</span><span class="sxs-lookup"><span data-stu-id="8129e-120">Other Optional Step</span></span>  
  
1.  [<span data-ttu-id="8129e-121">Ruotare la casella di testo di 270 gradi</span><span class="sxs-lookup"><span data-stu-id="8129e-121">Rotate Text Box 270 Degrees</span></span>](#RotateTextBox)  
  
 <span data-ttu-id="8129e-122">Il tempo stimato per il completare l'esercitazione è di 20 minuti.</span><span class="sxs-lookup"><span data-stu-id="8129e-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8129e-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8129e-123">Requirements</span></span>  
 <span data-ttu-id="8129e-124">Per altre informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="8129e-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-new-table-or-matrix-wizard"></a><a name="CreateMatrix"></a><span data-ttu-id="8129e-125">1. creare un report matrice e un set di dati dalla creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="8129e-125">1. Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="8129e-126">Nella finestra di dialogo **Introduzione** in Generatore report scegliere un'origine dati condivisa, creare un set di dati incorporato e visualizzare i dati in una matrice.</span><span class="sxs-lookup"><span data-stu-id="8129e-126">From the **Getting Started** dialog box in Report Builder, choose a shared data source, create an embedded dataset, and then display the data in a matrix.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8129e-127">Per evitare di dover disporre di un'origine dati esterna, nella query di questa esercitazione sono già inclusi i valori dei dati.</span><span class="sxs-lookup"><span data-stu-id="8129e-127">In this tutorial, the query already contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="8129e-128">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="8129e-128">This makes the query quite long.</span></span> <span data-ttu-id="8129e-129">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="8129e-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="8129e-130">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="8129e-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix"></a><span data-ttu-id="8129e-131">Per creare una nuova matrice</span><span class="sxs-lookup"><span data-stu-id="8129e-131">To create a new matrix</span></span>  
  
1.  <span data-ttu-id="8129e-132">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="8129e-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8129e-133">Verrà visualizzata la finestra di dialogo **Riquadro attività iniziale** .</span><span class="sxs-lookup"><span data-stu-id="8129e-133">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="8129e-134">In caso contrario, fare clic sul pulsante Generatore report, quindi su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8129e-134">If it doesn't, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="8129e-135">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="8129e-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="8129e-136">Nel riquadro destro fare clic su **Creazione guidata tabella o matrice**.</span><span class="sxs-lookup"><span data-stu-id="8129e-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="8129e-137">Nella pagina **Scegliere un set di dati** fare clic su **Crea un set di dati**.</span><span class="sxs-lookup"><span data-stu-id="8129e-137">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="8129e-138">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8129e-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="8129e-139">Nella pagina **scegliere una connessione a un'origine dei dati** selezionare un'origine dati esistente o individuare il server di report, quindi selezionare un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8129e-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server, and then select a data source.</span></span> <span data-ttu-id="8129e-140">Se non è disponibile un'origine dati o non si dispone dell'accesso a un server di report, sarà possibile utilizzare un'origine dati incorporata.</span><span class="sxs-lookup"><span data-stu-id="8129e-140">If no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="8129e-141">Per ulteriori informazioni sulla creazione di un'origine dati incorporata, vedere [esercitazione: creazione di un report tabella semplice &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="8129e-141">For more information about creating an embedded data source, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="8129e-142">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8129e-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="8129e-143">Nella pagina **Progetta query** fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="8129e-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="8129e-144">Copiare e incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="8129e-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity  
    ```  
  
10. <span data-ttu-id="8129e-145">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8129e-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-and-choose-layout-and-style-from-the-new-table-or-matrix-wizard"></a><a name="Groups"></a><span data-ttu-id="8129e-146">2. organizzare i dati e scegliere il layout e lo stile dalla procedura guidata nuova tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="8129e-146">2. Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="8129e-147">Utilizzare la procedura guidata per fornire una progettazione iniziale in cui visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="8129e-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="8129e-148">Il riquadro di anteprima nella procedura guidata consente di visualizzare il risultato del raggruppamento di dati prima di completare la progettazione della matrice.</span><span class="sxs-lookup"><span data-stu-id="8129e-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-and-choose-a-layout-and-style"></a><span data-ttu-id="8129e-149">Per organizzare i dati in gruppi e scegliere un layout e uno stile</span><span class="sxs-lookup"><span data-stu-id="8129e-149">To organize data into groups and choose a layout and style</span></span>  
  
1.  <span data-ttu-id="8129e-150">Nella pagina **Disponi campi** trascinare Territory da **Campi disponibili** in **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="8129e-150">On the **Arrange fields** page, drag Territory from **Available fields** to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="8129e-151">Trascinare SalesDate in **Gruppi di righe** e posizionarlo sotto Territory.</span><span class="sxs-lookup"><span data-stu-id="8129e-151">Drag SalesDate to **Row groups** and place it below Territory.</span></span>  
  
     <span data-ttu-id="8129e-152">L'ordine in cui i campi vengono elencati in **Gruppi di righe** consente di definire la gerarchia di gruppi.</span><span class="sxs-lookup"><span data-stu-id="8129e-152">The order in which fields are listed in **Row groups** defines the group hierarchy.</span></span> <span data-ttu-id="8129e-153">I passaggi 1 e 2 consentono di organizzare i valori dei campi prima in base al territorio, quindi in base alle date di vendita.</span><span class="sxs-lookup"><span data-stu-id="8129e-153">Steps 1 and 2 organize the values of the fields first by territory, and then by sales date.</span></span>  
  
3.  <span data-ttu-id="8129e-154">Trascinare Subcategory in **Gruppi di colonne**.</span><span class="sxs-lookup"><span data-stu-id="8129e-154">Drag Subcategory to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="8129e-155">Trascinare Product in **gruppi di colonne,** quindi posizionarlo sotto Subcategory.</span><span class="sxs-lookup"><span data-stu-id="8129e-155">Drag Product to **Column groups,** and then place below Subcategory.</span></span>  
  
     <span data-ttu-id="8129e-156">L'ordine in cui i campi vengono elencati in **gruppi di colonne** definisce la gerarchia di gruppi.</span><span class="sxs-lookup"><span data-stu-id="8129e-156">The order in which fields are listed in **Column groups** defines the group hierarchy.</span></span>  
  
     <span data-ttu-id="8129e-157">I passaggi 3 e 4 consentono di organizzare i valori per i campi prima in base alla sottocategoria, quindi in base al prodotto.</span><span class="sxs-lookup"><span data-stu-id="8129e-157">Steps 3 and 4 organize the values for the fields first by subcategory, and then by product.</span></span>  
  
5.  <span data-ttu-id="8129e-158">Trascinare Sales in **Valori**.</span><span class="sxs-lookup"><span data-stu-id="8129e-158">Drag Sales to **Values**.</span></span>  
  
     <span data-ttu-id="8129e-159">Le vendite vengono riepilogate con la funzione Sum, ovvero la funzione predefinita per il riepilogo di campi numerici.</span><span class="sxs-lookup"><span data-stu-id="8129e-159">Sales is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
6.  <span data-ttu-id="8129e-160">Trascinare Quantity in **Valori**.</span><span class="sxs-lookup"><span data-stu-id="8129e-160">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="8129e-161">La quantità viene riepilogata con la funzione Sum.</span><span class="sxs-lookup"><span data-stu-id="8129e-161">Quantity is summarized with the Sum function.</span></span>  
  
     <span data-ttu-id="8129e-162">I passaggi 5 e 6 consentono di specificare i dati da visualizzare nella celle di dati della matrice.</span><span class="sxs-lookup"><span data-stu-id="8129e-162">Steps 5 and 6 specify the data to display in the matrix data cells.</span></span>  
  
7.  <span data-ttu-id="8129e-163">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8129e-163">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="8129e-164">Nella pagina Scegliere il layout, in **Opzioni**, verificare che la casella **Mostra subtotali e totali complessivi** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8129e-164">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
9. <span data-ttu-id="8129e-165">Verificare che l'opzione **Bloccato, subtotale sotto** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8129e-165">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
10. <span data-ttu-id="8129e-166">Verificare che l'opzione **Espandi/comprimi gruppi** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8129e-166">Verify the option **Expand/collapse groups** is selected.</span></span>  
  
11. <span data-ttu-id="8129e-167">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8129e-167">Click **Next**.</span></span>  
  
12. <span data-ttu-id="8129e-168">Nel riquadro Stili della pagina Scegliere uno stile selezionare **Ardesia**.</span><span class="sxs-lookup"><span data-stu-id="8129e-168">On the Choose a Style page, in the Styles pane, select **Slate**.</span></span>  
  
13. <span data-ttu-id="8129e-169">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8129e-169">Click **Finish**.</span></span>  
  
     <span data-ttu-id="8129e-170">La matrice viene aggiunta all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8129e-170">The matrix is added to the design surface.</span></span> <span data-ttu-id="8129e-171">Nel riquadro Gruppi di righe vengono visualizzati due gruppi di righe, ovvero Territory e SalesDate.</span><span class="sxs-lookup"><span data-stu-id="8129e-171">The Row Groups pane shows two row groups: Territory and SalesDate.</span></span> <span data-ttu-id="8129e-172">Nel riquadro Gruppi di colonne vengono visualizzati due gruppi di colonne, ovvero Subcategory e Product.</span><span class="sxs-lookup"><span data-stu-id="8129e-172">The Column Groups pane shows two column groups: Subcategory and Product.</span></span> <span data-ttu-id="8129e-173">I dati dettaglio costituiscono tutti i dati recuperati dalla query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="8129e-173">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
14. <span data-ttu-id="8129e-174">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-174">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="8129e-175">Per ogni prodotto venduto in una data specifica, nella matrice viene visualizzata la sottocategoria alla quale appartiene il prodotto, nonché il territorio delle vendite.</span><span class="sxs-lookup"><span data-stu-id="8129e-175">For each product that is sold on a specific date, the matrix shows the subcategory to which the product belongs and the territory of the sales.</span></span>  
  
##  <a name="3-format-data"></a><a name="FormatData"></a><span data-ttu-id="8129e-176">3. formattare i dati</span><span class="sxs-lookup"><span data-stu-id="8129e-176">3. Format Data</span></span>  
 <span data-ttu-id="8129e-177">Per impostazione predefinita, i dati riepilogativi per il campo Sales vengono visualizzati come numero generico e nel campo SalesDate vengono visualizzate le informazioni di data e ora.</span><span class="sxs-lookup"><span data-stu-id="8129e-177">By default, the summary data for the Sales field displays a general number and the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="8129e-178">Formattare il campo Sales in modo che il numero venga visualizzato come valuta e formattare il campo SalesDate in modo che venga visualizzata solo la data.</span><span class="sxs-lookup"><span data-stu-id="8129e-178">Format the Sales field to display the number as currency and the SalesDate field to display only the date.</span></span> <span data-ttu-id="8129e-179">Attivare o disattivare **Stili segnaposto** per visualizzare caselle di testo formattate e testo segnaposto come valori di esempio.</span><span class="sxs-lookup"><span data-stu-id="8129e-179">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-fields"></a><span data-ttu-id="8129e-180">Per formattare i campi</span><span class="sxs-lookup"><span data-stu-id="8129e-180">To format fields</span></span>  
  
1.  <span data-ttu-id="8129e-181">Fare clic su **progettazione** per passare alla visualizzazione progettazione.</span><span class="sxs-lookup"><span data-stu-id="8129e-181">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="8129e-182">Premere CTRL e selezionare le nove celle contenenti `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="8129e-182">Press the Ctrl key, and then select the nine cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="8129e-183">Nel gruppo **Numero** della scheda **Home** fare clic su **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="8129e-183">On the **Home** tab, in the **Number** group, click **Currency**.</span></span> <span data-ttu-id="8129e-184">I numeri nelle celle verranno visualizzati nel formato di valuta.</span><span class="sxs-lookup"><span data-stu-id="8129e-184">The cells changeto show the formatted currency.</span></span>  
  
     <span data-ttu-id="8129e-185">Se la lingua delle impostazioni locali è Inglese (Stati Uniti), il testo di esempio predefinito sarà [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="8129e-185">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="8129e-186">Se non viene visualizzato un valore di valuta di esempio, fare clic su **Stili segnaposto** nel gruppo **numeri** , quindi fare clic su **valori di esempio**.</span><span class="sxs-lookup"><span data-stu-id="8129e-186">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="8129e-187">Fare clic sulla cella contenente `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="8129e-187">Click the cell that contains `[SalesDate]`.</span></span>  
  
5.  <span data-ttu-id="8129e-188">Nel gruppo **numero** selezionare **Data**nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="8129e-188">In the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="8129e-189">Nella cella viene visualizzata la data di esempio **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="8129e-189">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="8129e-190">Se non viene visualizzata una data di esempio, fare clic su **Stili segnaposto** nel gruppo **Numeri** , quindi fare clic su **Valori di esempio**.</span><span class="sxs-lookup"><span data-stu-id="8129e-190">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
6.  <span data-ttu-id="8129e-191">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-191">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="8129e-192">I valori di data verranno visualizzati solo come date mentre i valori delle vendite verranno visualizzati come valuta.</span><span class="sxs-lookup"><span data-stu-id="8129e-192">The date values display only dates and the sales values display as currency.</span></span>  
  
##  <a name="4-add-adjacent-column-group"></a><a name="AdjacentGroup"></a><span data-ttu-id="8129e-193">4. aggiungere un gruppo di colonne adiacente</span><span class="sxs-lookup"><span data-stu-id="8129e-193">4. Add Adjacent Column Group</span></span>  
 <span data-ttu-id="8129e-194">È possibile annidare gruppi di righe e colonne nelle relazioni padre-figlio oppure gruppi di righe e colonne adiacenti nelle relazioni di pari livello.</span><span class="sxs-lookup"><span data-stu-id="8129e-194">You can nest row and column groups in parent child relationships or adjacent in sibling relationships.</span></span>  
  
 <span data-ttu-id="8129e-195">Aggiungere un gruppo di colonne adiacente al gruppo di colonne Subcategory, copiare le celle per popolare il nuovo gruppo di colonne, quindi utilizzare un'espressione per creare il valore dell'intestazione del gruppo di colonne.</span><span class="sxs-lookup"><span data-stu-id="8129e-195">Add a column group that is adjacent to the Subcategory column group, copy cells to populate the new column group, and then use an expression to create the value of the column group header.</span></span>  
  
#### <a name="to-add-an-adjacent-column-group"></a><span data-ttu-id="8129e-196">Per aggiungere un gruppo di colonne adiacente</span><span class="sxs-lookup"><span data-stu-id="8129e-196">To add an adjacent column group</span></span>  
  
1.  <span data-ttu-id="8129e-197">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="8129e-197">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="8129e-198">Fare clic con il pulsante destro del mouse sulla cella contenente `[Subcategory]`, scegliere **Aggiungi gruppo**, quindi fare clic su **Adiacente a destra**.</span><span class="sxs-lookup"><span data-stu-id="8129e-198">Right-click the cell that contains `[Subcategory]`, point to **Add Group**, and then click **Adjacent Right**.</span></span>  
  
     <span data-ttu-id="8129e-199">Verrà visualizzata la finestra di dialogo **Gruppo Tablix** .</span><span class="sxs-lookup"><span data-stu-id="8129e-199">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="8129e-200">Nell'elenco **Raggruppa per** selezionare SalesDate, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8129e-200">In the **Group By** list, select SalesDate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8129e-201">Un nuovo gruppo di colonne verrà aggiunto a sinistra del gruppo di colonne Subcategory.</span><span class="sxs-lookup"><span data-stu-id="8129e-201">A new column group is added to the left of the Subcategory column group.</span></span>  
  
4.  <span data-ttu-id="8129e-202">Fare clic con il pulsante destro del mouse sulla cella del nuovo gruppo di colonne contenente `[SalesDate],` quindi scegliere **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="8129e-202">Right-click the cell in the new column group that contains `[SalesDate],` and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="8129e-203">Copiare l'espressione seguente nella casella dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="8129e-203">Copy the following expression to expression box.</span></span>  
  
    ```  
    =WeekdayName(DatePart("w",Fields!SalesDate.Value))  
    ```  
  
     <span data-ttu-id="8129e-204">Questa espressione consente di estrarre il nome del giorno della settimana dalla data in cui è stata realizzata la vendita.</span><span class="sxs-lookup"><span data-stu-id="8129e-204">This expression extracts the weekday name from the sales date.</span></span> <span data-ttu-id="8129e-205">Per altre informazioni, vedere [Espressioni &#40;Generatore report e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8129e-205">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="8129e-206">Fare clic con il pulsante destro del mouse sul gruppo di colonne Subcategory contenente Total, quindi scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="8129e-206">Right-click the cell in the Subcategory column group that contains Total, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="8129e-207">Fare clic con il pulsante destro del mouse sulla cella posta immediatamente sotto a quella contenente l'espressione creata nel passaggio 5 e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="8129e-207">Right-click the cell immediately below the cell that contains the expression you created in step 5 and click **Paste**.</span></span>  
  
8.  <span data-ttu-id="8129e-208">Premere CTRL.</span><span class="sxs-lookup"><span data-stu-id="8129e-208">Press the Ctrl key.</span></span>  
  
9. <span data-ttu-id="8129e-209">Nel gruppo Subcategory fare clic sull'intestazione di colonna Sales e sulle tre celle sottostanti, fare clic con il pulsante destro del mouse, quindi scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="8129e-209">In the Subcategory group, click the Sales column header and the three cells below it, right-click, and then click **Copy**.</span></span>  
  
10. <span data-ttu-id="8129e-210">Incollare le quattro celle nelle quattro celle vuote del nuovo gruppo di colonne.</span><span class="sxs-lookup"><span data-stu-id="8129e-210">Paste the four cells into the four empty cells in the new column group.</span></span>  
  
11. <span data-ttu-id="8129e-211">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-211">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="8129e-212">Nel report sono incluse due colonne denominate Monday e Tuesday.</span><span class="sxs-lookup"><span data-stu-id="8129e-212">The report includes columns named Monday and Tuesday.</span></span> <span data-ttu-id="8129e-213">Il set di dati contiene i dati solo per questi due giorni.</span><span class="sxs-lookup"><span data-stu-id="8129e-213">The dataset contains only data for these two days.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8129e-214">Diversamente, nel report sarebbero state incluse le colonne per gli altri giorni della settimana.</span><span class="sxs-lookup"><span data-stu-id="8129e-214">If the data included other days, the report would include columns for them as well.</span></span> <span data-ttu-id="8129e-215">Ogni colonna presenta l'intestazione di colonna, `Sales` e i totali delle vendite per territorio.</span><span class="sxs-lookup"><span data-stu-id="8129e-215">Each column has the column header, `Sales`, and sales totals by territory.</span></span>  
  
##  <a name="5-change-column-widths"></a><a name="Width"></a><span data-ttu-id="8129e-216">5. modificare la larghezza delle colonne</span><span class="sxs-lookup"><span data-stu-id="8129e-216">5. Change Column Widths</span></span>  
 <span data-ttu-id="8129e-217">Al momento dell'esecuzione, un report contenente una matrice si espande in genere orizzontalmente e verticalmente.</span><span class="sxs-lookup"><span data-stu-id="8129e-217">A report that includes a matrix typically expands horizontally as well as vertically when it runs.</span></span> <span data-ttu-id="8129e-218">Il controllo di espansione orizzontale è particolarmente importante quando si intende esportare il report in un formato quale Microsoft Word o Adobe PDF utilizzato per i report stampati.</span><span class="sxs-lookup"><span data-stu-id="8129e-218">Controlling horizontal expansion is particularly important if you plan to export the report to formats such as Microsoft Word or Adobe PDF that are used for printed reports.</span></span> <span data-ttu-id="8129e-219">Se il report si espande orizzontalmente su più pagine, sarà difficile interpretare il report stampato.</span><span class="sxs-lookup"><span data-stu-id="8129e-219">If the report expands horizontally across multiple pages, the printed report is difficult to understand.</span></span> <span data-ttu-id="8129e-220">Per contenere l'espansione orizzontale, è possibile ridimensionare le colonne alla larghezza minima necessaria per visualizzare i dati su una sola riga.</span><span class="sxs-lookup"><span data-stu-id="8129e-220">To minimize horizontal expansion, you can resize columns to be only the width necessary to display the data without wrapping.</span></span> <span data-ttu-id="8129e-221">È inoltre possibile rinominare le colonne in modo che i relativi titoli si adattino alla larghezza necessaria per visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="8129e-221">You can also rename columns so that their titles fit the width needed to display the data.</span></span>  
  
#### <a name="to-rename-and-resize-the-columns"></a><span data-ttu-id="8129e-222">Per rinominare e ridimensionare le colonne</span><span class="sxs-lookup"><span data-stu-id="8129e-222">To rename and resize the columns</span></span>  
  
1.  <span data-ttu-id="8129e-223">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="8129e-223">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="8129e-224">Selezionare il testo nella colonna Quantity all'estrema sinistra, quindi digitare **QTA**.</span><span class="sxs-lookup"><span data-stu-id="8129e-224">Select the text in the furthest Quantity column to the left, and then type **QTY**.</span></span>  
  
     <span data-ttu-id="8129e-225">Il titolo della colonna corrisponderà a QTA.</span><span class="sxs-lookup"><span data-stu-id="8129e-225">The column title is now QTY.</span></span>  
  
3.  <span data-ttu-id="8129e-226">Ripetere il passaggio 2 per le altre colonne denominate Quantity,</span><span class="sxs-lookup"><span data-stu-id="8129e-226">Repeat step 2 for the other columns named Quantity.</span></span> <span data-ttu-id="8129e-227">ovvero due delle colonne presenti.</span><span class="sxs-lookup"><span data-stu-id="8129e-227">There are two of them.</span></span>  
  
4.  <span data-ttu-id="8129e-228">Fare clic nella matrice in modo che vengano visualizzati gli handle di riga e di colonna sopra e accanto alla matrice.</span><span class="sxs-lookup"><span data-stu-id="8129e-228">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
     <span data-ttu-id="8129e-229">Le barre grigie lungo la parte superiore e laterale della tabella sono gli handle di riga e di colonna.</span><span class="sxs-lookup"><span data-stu-id="8129e-229">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
5.  <span data-ttu-id="8129e-230">Per ridimensionare la colonna della quantità all'estrema destra, posizionare il puntatore del mouse sulla riga posta tra gli handle di colonna in modo che il cursore assuma la forma di una doppia freccia.</span><span class="sxs-lookup"><span data-stu-id="8129e-230">To resize the furthest QTY column to the left, point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="8129e-231">Trascinare la colonna verso sinistra fino a quando non raggiunge una larghezza di 1 centimetro circa.</span><span class="sxs-lookup"><span data-stu-id="8129e-231">Drag the column towards the left until it is 1/2 inch wide.</span></span>  
  
     <span data-ttu-id="8129e-232">Una larghezza di colonna di circa 1 centimetro è ideale per visualizzare la quantità.</span><span class="sxs-lookup"><span data-stu-id="8129e-232">A column width of 1/2 inch is adequate to display the quantity.</span></span>  
  
6.  <span data-ttu-id="8129e-233">Ripetere il passaggio 5 per le altre colonne denominate QTA.</span><span class="sxs-lookup"><span data-stu-id="8129e-233">Repeat step 5 for the other columns named QTY.</span></span>  
  
7.  <span data-ttu-id="8129e-234">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-234">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="8129e-235">Le colonne del report contenenti le quantità risulteranno ora denominate QTA e saranno più strette.</span><span class="sxs-lookup"><span data-stu-id="8129e-235">The columns in the report that contains quantities are now named QTY and the columns are narrower.</span></span>  
  
##  <a name="6-merge-matrix-cells"></a><a name="MergeCells"></a><span data-ttu-id="8129e-236">6. unire le celle della matrice</span><span class="sxs-lookup"><span data-stu-id="8129e-236">6. Merge Matrix Cells</span></span>  
 <span data-ttu-id="8129e-237">L'area dell'angolo si trova in corrispondenza dell'angolo superiore sinistro della matrice.</span><span class="sxs-lookup"><span data-stu-id="8129e-237">The corner area is in the upper left corner of the matrix.</span></span> <span data-ttu-id="8129e-238">Il numero di celle nell'area dell'angolo varia a seconda del numero di righe e di gruppi di colonne presenti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="8129e-238">Depending on the number of row and column groups in the matrix, the number of cells in the corner area varies.</span></span> <span data-ttu-id="8129e-239">La matrice creata in questa esercitazione dispone di quattro celle nell'area dell'angolo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8129e-239">The matrix, built in this tutorial, has four cells in its corner area.</span></span> <span data-ttu-id="8129e-240">Le celle vengono disposte in due righe e due colonne, in modo da riflettere il livello delle gerarchie di gruppo di righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="8129e-240">The cells are arranged in two rows and two columns, reflecting the depth of row and column group hierarchies.</span></span> <span data-ttu-id="8129e-241">Le quattro celle non vengono utilizzate in questo report e verranno unite in un'unica cella.</span><span class="sxs-lookup"><span data-stu-id="8129e-241">The four cells are not used in this report and you will merge them into one.</span></span>  
  
#### <a name="to-merge-matrix-cells"></a><span data-ttu-id="8129e-242">Per unire le celle della matrice</span><span class="sxs-lookup"><span data-stu-id="8129e-242">To merge matrix cells</span></span>  
  
1.  <span data-ttu-id="8129e-243">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="8129e-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="8129e-244">Fare clic nella matrice in modo che vengano visualizzati gli handle di riga e di colonna sopra e accanto alla matrice.</span><span class="sxs-lookup"><span data-stu-id="8129e-244">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
3.  <span data-ttu-id="8129e-245">Premere CTRL e selezionare quindi le quattro celle d'angolo.</span><span class="sxs-lookup"><span data-stu-id="8129e-245">Press the Ctrl key, and then select the four corner cells.</span></span>  
  
4.  <span data-ttu-id="8129e-246">Fare clic con il pulsante destro del mouse sulle celle, quindi scegliere **Unisci celle**.</span><span class="sxs-lookup"><span data-stu-id="8129e-246">Right-click the cells and then click **Merge Cells**.</span></span>  
  
5.  <span data-ttu-id="8129e-247">Fare clic con il pulsante destro del mouse sulla cella d'angolo, quindi scegliere **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="8129e-247">Right-click the corner cell, and then click **Text Box Properties**.</span></span>  
  
6.  <span data-ttu-id="8129e-248">Fare clic sulla scheda **Riempimento** .</span><span class="sxs-lookup"><span data-stu-id="8129e-248">Click the **Fill** tab.</span></span>  
  
7.  <span data-ttu-id="8129e-249">Fare clic sul pulsante (***FX***) per **colore riempimento**.</span><span class="sxs-lookup"><span data-stu-id="8129e-249">Click the (***fx***) button for **Fill color**.</span></span>  
  
8.  <span data-ttu-id="8129e-250">Copiare e incollare l'espressione seguente nella casella dell'espressione:</span><span class="sxs-lookup"><span data-stu-id="8129e-250">Copy and paste the following expression in the expression box.</span></span>  
  
    ```  
    #96a4b2  
    ```  
  
     <span data-ttu-id="8129e-251">Si tratta del valore esadecimale RGB per un colore blu grigio utilizzato nello stile Ardesia.</span><span class="sxs-lookup"><span data-stu-id="8129e-251">This is the RGB hex value for a gray blue color used in the Slate style.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="8129e-252">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-252">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="8129e-253">La matrice nell'angolo superiore è costituita da un'unica cella e ha lo stesso colore delle celle del gruppo di righe e del gruppo di colonne.</span><span class="sxs-lookup"><span data-stu-id="8129e-253">The upper corner matrix is a single cell and has the same color as the row group and column group cells.</span></span>  
  
##  <a name="7-add-a-report-header-and-report-title"></a><a name="HeaderTitle"></a><span data-ttu-id="8129e-254">7. aggiungere un'intestazione e un titolo al report</span><span class="sxs-lookup"><span data-stu-id="8129e-254">7. Add a Report Header and Report Title</span></span>  
 <span data-ttu-id="8129e-255">Nella parte superiore del report viene visualizzato il titolo del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-255">A report title appears at the top of the report.</span></span> <span data-ttu-id="8129e-256">È possibile posizionare il titolo del report in un'apposita intestazione oppure, se ne è privo, in una casella di testo nella parte superiore del corpo del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-256">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="8129e-257">In questa esercitazione verrà rimossa la casella di testo nella parte superiore del report e verrà aggiunto un titolo all'intestazione.</span><span class="sxs-lookup"><span data-stu-id="8129e-257">In this tutorial, you will remove the text box at the top of the report and add a title to the header.</span></span>  
  
#### <a name="to-add-a-report-header-and-report-title"></a><span data-ttu-id="8129e-258">Per aggiungere un'intestazione e un titolo al report</span><span class="sxs-lookup"><span data-stu-id="8129e-258">To add a report header and report title</span></span>  
  
1.  <span data-ttu-id="8129e-259">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="8129e-259">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="8129e-260">Fare clic sulla casella di testo nella parte superiore del corpo del report che contiene **clic per aggiungere il titolo**, quindi premere il tasto CANC.</span><span class="sxs-lookup"><span data-stu-id="8129e-260">Click the text box at the top of the report body that contains **Click to add title**, and then press the Delete key.</span></span>  
  
3.  <span data-ttu-id="8129e-261">Nella scheda **Inserisci** della barra multifunzione fare clic su **intestazione** e quindi su **Aggiungi intestazione**.</span><span class="sxs-lookup"><span data-stu-id="8129e-261">On the **Insert** tab of the ribbon, click **Header** and then click **Add Header**.</span></span>  
  
     <span data-ttu-id="8129e-262">Nella parte superiore del corpo del report verrà aggiunta un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="8129e-262">A header is added to the top of the report body.</span></span>  
  
4.  <span data-ttu-id="8129e-263">Nella scheda **Inserisci** fare clic su **Casella di testo**, quindi trascinare una casella di testo nell'intestazione del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-263">On the **Insert** tab, click **Text Box**, and then drag a text box inside the report header.</span></span> <span data-ttu-id="8129e-264">Assegnare alla casella di testo una lunghezza di circa 15 centimetri e un'altezza di circa 2 centimetri e posizionarla nella parte sinistra dell'intestazione del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-264">Make the text box about 6 inches long and 3/4 inch tall and place it on the left side of the report header.</span></span>  
  
5.  <span data-ttu-id="8129e-265">Nella casella di testo digitare **Vendite per territorio, sottocategoria e giorno**.</span><span class="sxs-lookup"><span data-stu-id="8129e-265">In the text box, type **Sales by Territory, Subcategory, and Day**.</span></span>  
  
6.  <span data-ttu-id="8129e-266">Selezionare il testo digitato, fare clic con il pulsante destro del mouse e quindi scegliere **Proprietà testo**.</span><span class="sxs-lookup"><span data-stu-id="8129e-266">Select the text you typed, right-click, and then click **Text Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8129e-267">Per applicare contemporaneamente la formattazione, è necessario che i caratteri siano contigui.</span><span class="sxs-lookup"><span data-stu-id="8129e-267">To format characters at the same time, they must be contiguous.</span></span>  
  
7.  <span data-ttu-id="8129e-268">Nella finestra di dialogo **Proprietà testo** fare clic su **tipo di carattere**.</span><span class="sxs-lookup"><span data-stu-id="8129e-268">In the **Text Properties** dialog box, click **Font**.</span></span>  
  
8.  <span data-ttu-id="8129e-269">Nell'elenco **tipo di carattere** selezionare **Times New Roman**; in **dimensioni** selezionare **24 PT**, in **colore** selezionare **marrone**e in **stile** selezionare **corsivo**.</span><span class="sxs-lookup"><span data-stu-id="8129e-269">In the **Font** list, select **Times New Roman**; in **Size** select **24 pt**, in **Color** select **Maroon**, and in **Style** select **Italic**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="8129e-270">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-270">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="8129e-271">Nel report visualizzato è incluso il titolo di un report nella relativa intestazione.</span><span class="sxs-lookup"><span data-stu-id="8129e-271">The report includes a report title in the report header.</span></span>  
  
##  <a name="8-save-the-report"></a><a name="Save"></a><span data-ttu-id="8129e-272">8. salvare il report</span><span class="sxs-lookup"><span data-stu-id="8129e-272">8. Save the Report</span></span>  
 <span data-ttu-id="8129e-273">È possibile salvare i report in un server di report, in una raccolta di SharePoint o nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="8129e-273">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="8129e-274">In questa esercitazione il report verrà salvato in un server di report.</span><span class="sxs-lookup"><span data-stu-id="8129e-274">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="8129e-275">Se non si dispone dell'accesso a un server di report, sarà possibile salvare il report nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="8129e-275">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="8129e-276">Per salvare il report in un server di report</span><span class="sxs-lookup"><span data-stu-id="8129e-276">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="8129e-277">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="8129e-277">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="8129e-278">Fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="8129e-278">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="8129e-279">Selezionare o digitare il nome del server di report per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="8129e-279">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="8129e-280">Verrà visualizzato il messaggio "Connessione al server di report".</span><span class="sxs-lookup"><span data-stu-id="8129e-280">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="8129e-281">Al termine della connessione, verrà visualizzato il contenuto della cartella di report specificata dall'amministratore del server di report come posizione predefinita per i report.</span><span class="sxs-lookup"><span data-stu-id="8129e-281">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="8129e-282">In **Nome**sostituire il nome predefinito con **VenditePerTerritorioSottocategoria**.</span><span class="sxs-lookup"><span data-stu-id="8129e-282">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
5.  <span data-ttu-id="8129e-283">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8129e-283">Click **Save**.</span></span>  
  
 <span data-ttu-id="8129e-284">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="8129e-284">The report is saved to the report server.</span></span> <span data-ttu-id="8129e-285">Il nome del server di report al quale si è connessi verrà visualizzato sulla barra di stato nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="8129e-285">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="8129e-286">Per salvare il report nel computer</span><span class="sxs-lookup"><span data-stu-id="8129e-286">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="8129e-287">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="8129e-287">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="8129e-288">Fare clic su **Desktop**, **Documenti**o **Risorse del computer**, quindi selezionare la cartella in cui si desidera salvare il report.</span><span class="sxs-lookup"><span data-stu-id="8129e-288">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="8129e-289">In **Nome**sostituire il nome predefinito con **VenditePerTerritorioSottocategoria**.</span><span class="sxs-lookup"><span data-stu-id="8129e-289">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
4.  <span data-ttu-id="8129e-290">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8129e-290">Click **Save**.</span></span>  
  
##  <a name="9-optional-rotate-text-box-270-degrees"></a><a name="RotateTextBox"></a><span data-ttu-id="8129e-291">9. (facoltativo) ruotare la casella di testo 270 gradi</span><span class="sxs-lookup"><span data-stu-id="8129e-291">9. (Optional) Rotate Text Box 270 Degrees</span></span>  
 <span data-ttu-id="8129e-292">Al momento dell'esecuzione, un report con matrici può espandersi orizzontalmente e verticalmente.</span><span class="sxs-lookup"><span data-stu-id="8129e-292">A report with matrices can expand horizontally and vertically when it runs.</span></span> <span data-ttu-id="8129e-293">La rotazione verticale, o di 270 gradi, delle caselle di testo consente di risparmiare spazio orizzontale.</span><span class="sxs-lookup"><span data-stu-id="8129e-293">By rotating text boxes vertically, or 270 degrees, you can save horizontal space.</span></span> <span data-ttu-id="8129e-294">Il report visualizzabile risulterà quindi più stretto e nel caso venga esportato in un formato quale Microsoft Word si adatterà con maggiore facilità alle dimensioni della pagina stampata.</span><span class="sxs-lookup"><span data-stu-id="8129e-294">The rendered report is then narrower and if exported to a format such as Microsoft Word, will be more likely to fit on a printed page.</span></span>  
  
 <span data-ttu-id="8129e-295">Il testo in una casella di testo può inoltre essere visualizzato in senso orizzontale e verticale (dall'alto in basso).</span><span class="sxs-lookup"><span data-stu-id="8129e-295">A text box can also display text as horizontal, vertical (top to bottom).</span></span> <span data-ttu-id="8129e-296">Per altre informazioni, vedere [Caselle di testo &#40;Generatore report e SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8129e-296">For more information, see [Text Boxes &#40;Report Builder and SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-rotate-text-box-270-degrees"></a><span data-ttu-id="8129e-297">Per ruotare una casella di testo di 270 gradi</span><span class="sxs-lookup"><span data-stu-id="8129e-297">To rotate text box 270 degrees</span></span>  
  
1.  <span data-ttu-id="8129e-298">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="8129e-298">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="8129e-299">Fare clic sulla cella contenente `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="8129e-299">Click the cell that contains `[Territory].`</span></span>  
  
3.  <span data-ttu-id="8129e-300">Nel riquadro Proprietà individuare la proprietà WritingMode e nell'elenco a discesa selezionare **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="8129e-300">In the Properties pane, locate the WritingMode property and in its drop-down list, select **Rotate270**.</span></span>  
  
     <span data-ttu-id="8129e-301">Se il riquadro Proprietà non viene visualizzato, fare clic sulla scheda **Visualizza** e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8129e-301">If the Properties pane is not open, click the **View** tab of the ribbon, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="8129e-302">Verificare che la proprietà CanGrow sia impostata su `True` .</span><span class="sxs-lookup"><span data-stu-id="8129e-302">Verify that the CanGrow property is set to `True`.</span></span>  
  
5.  <span data-ttu-id="8129e-303">Ridimensionare la colonna Territory assegnandole una larghezza di circa 1 centimetro ed eliminare il titolo della colonna.</span><span class="sxs-lookup"><span data-stu-id="8129e-303">Resize the Territory column to be 1/2 inch wide and delete the column title.</span></span>  
  
6.  <span data-ttu-id="8129e-304">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="8129e-304">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="8129e-305">Il nome dell'area risulterà scritto in senso verticale, dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="8129e-305">The territory name is written vertically, bottom to top.</span></span> <span data-ttu-id="8129e-306">L'altezza del gruppo di righe Territory dipenderà dalla lunghezza del nome del territorio.</span><span class="sxs-lookup"><span data-stu-id="8129e-306">The height of the Territory row group varies by the length of the territory name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8129e-307">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8129e-307">Next Steps</span></span>  
 <span data-ttu-id="8129e-308">L'esercitazione sulla creazione di un report matrice è terminata.</span><span class="sxs-lookup"><span data-stu-id="8129e-308">This concludes the tutorial for how to create a matrix report.</span></span> <span data-ttu-id="8129e-309">Per ulteriori informazioni sulle matrici, vedere [tabelle, matrici ed elenchi &#40;Generatore report e ssrs&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [matrici &#40;Generatore report e SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [aree dell'area dati tablix &#40;Generatore report e SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)e [celle, righe e colonne dell'area dati Tablix &#40;Generatore report&#41; e SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="8129e-309">For more information about matrices, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Matrices &#40;Report Builder and SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8129e-310">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8129e-310">See Also</span></span>  
 <span data-ttu-id="8129e-311">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="8129e-311">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="8129e-312">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8129e-312">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
