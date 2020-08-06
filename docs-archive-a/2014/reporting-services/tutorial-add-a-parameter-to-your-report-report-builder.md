---
title: 'Esercitazione: Aggiungere un parametro al report (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eab34ec4-b3ad-4a76-95cc-07b2f75ee6d7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dff41066a2d505ab53b17a10fb3da9b6cb17130f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720964"
---
# <a name="tutorial-add-a-parameter-to-your-report-report-builder"></a><span data-ttu-id="af22c-102">Esercitazione: Aggiungere un parametro al report (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="af22c-102">Tutorial: Add a Parameter to Your Report (Report Builder)</span></span>
  <span data-ttu-id="af22c-103">Aggiungere un parametro al report per consentire agli utenti di filtrare i dati del report dall'origine dati o nel report.</span><span class="sxs-lookup"><span data-stu-id="af22c-103">Add a parameter to your report to let users filter report data from the data source or in the report.</span></span> <span data-ttu-id="af22c-104">I parametri di report vengono creati automaticamente per ogni parametro di query incluso in una query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="af22c-104">Report parameters are created automatically for each query parameter that you include in a dataset query.</span></span> <span data-ttu-id="af22c-105">Il tipo di dati determina il modo in cui il parametro viene presentato sulla barra degli strumenti della visualizzazione report.</span><span class="sxs-lookup"><span data-stu-id="af22c-105">The parameter data type determines how it appears on the report view toolbar.</span></span>  
  
 <span data-ttu-id="af22c-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span><span class="sxs-lookup"><span data-stu-id="af22c-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="af22c-107">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="af22c-107">What You Will Learn</span></span>  
 <span data-ttu-id="af22c-108">In questa esercitazione verranno illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="af22c-108">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="af22c-109">Creare un report matrice e un set di dati dalla Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="af22c-109">Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="af22c-110">Organizzare dati, scegliere il layout e lo stile dalla Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="af22c-110">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="af22c-111">Aggiungere un parametro di query per creare un parametro di report</span><span class="sxs-lookup"><span data-stu-id="af22c-111">Add a Query Parameter to Create a Report Parameter</span></span>](#Query)  
  
4.  [<span data-ttu-id="af22c-112">Modificare il tipo di dati e altre proprietà predefiniti per un parametro di report</span><span class="sxs-lookup"><span data-stu-id="af22c-112">Change Default Data Type and Other Properties for a Report Parameter</span></span>](#ChangeDefaultProperties)  
  
    1.  [<span data-ttu-id="af22c-113">Aggiungere un set di dati per fornire i valori disponibili e i nomi visualizzati</span><span class="sxs-lookup"><span data-stu-id="af22c-113">Add a Dataset to Provide Available Values and Display Names</span></span>](#AddDataset)  
  
    2.  [<span data-ttu-id="af22c-114">Specificare i valori disponibili per creare un elenco a discesa di valori</span><span class="sxs-lookup"><span data-stu-id="af22c-114">Specify Available Values to Create a Drop-List of Values</span></span>](#AvailableValues)  
  
    3.  [<span data-ttu-id="af22c-115">Specificare i valori predefiniti così che il report possa essere eseguito automaticamente</span><span class="sxs-lookup"><span data-stu-id="af22c-115">Specify Default Values so the Report Runs Automatically</span></span>](#DefaultValues)  
  
    4.  [<span data-ttu-id="af22c-116">Cercare un valore da un set di dati che disponga di coppie nome/valore</span><span class="sxs-lookup"><span data-stu-id="af22c-116">Look up a Value from a Dataset that has Name/Value Pairs</span></span>](#NameValue)  
  
5.  [<span data-ttu-id="af22c-117">Visualizzare il valore del parametro selezionato nel report</span><span class="sxs-lookup"><span data-stu-id="af22c-117">Display the Selected Parameter Value in the Report</span></span>](#Expression)  
  
6.  [<span data-ttu-id="af22c-118">Utilizzare il parametro del report in un filtro</span><span class="sxs-lookup"><span data-stu-id="af22c-118">Use the Report Parameter in a Filter</span></span>](#Filter)  
  
7.  [<span data-ttu-id="af22c-119">Modificare il parametro di report in modo che vengano accettati più valori</span><span class="sxs-lookup"><span data-stu-id="af22c-119">Change the Report Parameter to Accept Multiple Values</span></span>](#Multivalued)  
  
8.  [<span data-ttu-id="af22c-120">Aggiungere un parametro booleano per la visibilità condizionale</span><span class="sxs-lookup"><span data-stu-id="af22c-120">Add a Boolean Parameter for Conditional Visibility</span></span>](#Boolean)  
  
9. [<span data-ttu-id="af22c-121">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="af22c-121">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="af22c-122">Salva il report</span><span class="sxs-lookup"><span data-stu-id="af22c-122">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="af22c-123">In questa esercitazione, i passaggi per la procedura guidata sono consolidati in un'unica procedura.</span><span class="sxs-lookup"><span data-stu-id="af22c-123">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="af22c-124">Per istruzioni dettagliate su come selezionare un server di report, come scegliere un'origine dati e come creare un set di dati, vedere la prima esercitazione di questa serie: [Esercitazione: Creazione di un report tabella semplice &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="af22c-124">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="af22c-125">Tempo stimato per il completamento dell'esercitazione: 25 minuti.</span><span class="sxs-lookup"><span data-stu-id="af22c-125">Estimated time to complete this tutorial: 25 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af22c-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af22c-126">Requirements</span></span>  
 <span data-ttu-id="af22c-127">Per informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="af22c-127">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="af22c-128">1. creare un report matrice e un set di dati dalla creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="af22c-128">1. Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="af22c-129">Creare un report matrice, un'origine dati e un set di dati.</span><span class="sxs-lookup"><span data-stu-id="af22c-129">Create a matrix report, a data source, and a dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af22c-130">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="af22c-130">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="af22c-131">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="af22c-131">This makes the query quite long.</span></span> <span data-ttu-id="af22c-132">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="af22c-132">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="af22c-133">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="af22c-133">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix-report"></a><span data-ttu-id="af22c-134">Per creare un nuovo report matrice</span><span class="sxs-lookup"><span data-stu-id="af22c-134">To create a new matrix report</span></span>  
  
1.  <span data-ttu-id="af22c-135">Fare clic sul pulsante **Start**, scegliere **programmi**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Generatore report**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="af22c-135">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="af22c-136">Verrà visualizzata la finestra di dialogo **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="af22c-136">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="af22c-137">Se la finestra di dialogo **Introduzione** non viene visualizzata, dal pulsante **Generatore report** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="af22c-137">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="af22c-138">Nel riquadro sinistro verificare che sia selezionata l'opzione **report** .</span><span class="sxs-lookup"><span data-stu-id="af22c-138">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="af22c-139">Nel riquadro destro fare clic su **Creazione guidata tabella o matrice**.</span><span class="sxs-lookup"><span data-stu-id="af22c-139">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="af22c-140">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="af22c-140">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="af22c-141">Nella pagina **Scegliere un set di dati** fare clic su **Crea un set di dati**.</span><span class="sxs-lookup"><span data-stu-id="af22c-141">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
6.  <span data-ttu-id="af22c-142">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="af22c-142">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="af22c-143">Nella pagina **Scegliere una connessione a un'origine dei dati** selezionare un'origine dati che sia del tipo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="af22c-143">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="af22c-144">Selezionare un'origine dati dall'elenco o passare al server di report per selezionarne una.</span><span class="sxs-lookup"><span data-stu-id="af22c-144">Select a data source from the list or browse to the report server to select one.</span></span>  
  
8.  <span data-ttu-id="af22c-145">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="af22c-145">Click **Next**.</span></span>  
  
9. <span data-ttu-id="af22c-146">Nella pagina **Progetta query** fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="af22c-146">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
10. <span data-ttu-id="af22c-147">Incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="af22c-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    ;WITH CTE (StoreID, Subcategory, Quantity)   
    AS (  
    SELECT 200 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 2002 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Camcorders' AS Subcategory, 1954 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Accessories' AS Subcategory, 1895 AS Quantity  
    UNION SELECT  199 AS StoreID, 'Digital Cameras' AS Subcategory, 1849 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1579 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Camcorders' AS Subcategory, 1561 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital Cameras' AS Subcategory, 1553 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Accessories' AS Subcategory, 1534 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Accessories' AS Subcategory, 1755 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Camcorders' AS Subcategory, 1631 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1772 AS Quantity)  
    SELECT StoreID, Subcategory, Quantity  
    FROM CTE  
    ```  
  
     <span data-ttu-id="af22c-148">Questa query combina i risultati di diverse istruzioni SELECT di [!INCLUDE[tsql](../includes/tsql-md.md)] in un'espressione di tabella comune per specificare i valori basati sui dati semplificati del database di esempio Contoso.</span><span class="sxs-lookup"><span data-stu-id="af22c-148">This query combines the results of several [!INCLUDE[tsql](../includes/tsql-md.md)] SELECT statements inside a common table expression to specify values that are based on simplified data from the Contoso sample database.</span></span> <span data-ttu-id="af22c-149">I dati di vendita di Contoso rappresentano dati di vendita internazionali per i beni di consumo.</span><span class="sxs-lookup"><span data-stu-id="af22c-149">The Contoso sales data represents international sales data for consumer goods.</span></span> <span data-ttu-id="af22c-150">In questa esercitazione sono utilizzati dati di vendita relativi a fotocamere.</span><span class="sxs-lookup"><span data-stu-id="af22c-150">This tutorial uses sales data for cameras.</span></span> <span data-ttu-id="af22c-151">Le sottocategorie sono costituite da fotocamere digitali, fotocamere single lens reflex (SLR), cineprese e accessori.</span><span class="sxs-lookup"><span data-stu-id="af22c-151">The subcategories represent digital cameras, digital single lens reflex (SLR) cameras, camcorders, and accessories.</span></span>  
  
     <span data-ttu-id="af22c-152">Nella query sono specificati i nomi delle colonne che includono un identificatore del punto vendita, una sottocategoria di elementi di vendita e la quantità degli ordini vendita di tre punti vendita.</span><span class="sxs-lookup"><span data-stu-id="af22c-152">The query specifies column names that include a store identifier, a sales item subcategory, and the quantity ordered for sales orders from three stores.</span></span> <span data-ttu-id="af22c-153">In questa query, il nome del punto vendita non è parte del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="af22c-153">In this query, the store name is not part of the result set.</span></span> <span data-ttu-id="af22c-154">Più avanti in questa esercitazione, si cercherà il nome del punto vendita che corrisponde all'identificatore del punto vendita in un set di dati separato.</span><span class="sxs-lookup"><span data-stu-id="af22c-154">Later in this tutorial, you will look up the name of the store that corresponds to the store identifier from a separate dataset.</span></span>  
  
     <span data-ttu-id="af22c-155">Questa query non contiene parametri di query.</span><span class="sxs-lookup"><span data-stu-id="af22c-155">This query does not contain query parameters.</span></span> <span data-ttu-id="af22c-156">Verranno aggiunti più avanti in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="af22c-156">You will add query parameters later in this tutorial.</span></span>  
  
11. <span data-ttu-id="af22c-157">Sulla barra degli strumenti Progettazione query fare clic su **Esegui** (**!**).</span><span class="sxs-lookup"><span data-stu-id="af22c-157">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="af22c-158">Nel set di risultati vengono visualizzate 11 righe di dati che mostrano la quantità di articoli venduti per ogni sottocategoria in quattro punti vendita e sono incluse le colonne seguenti: StoreID, Subcategory, Quantity.</span><span class="sxs-lookup"><span data-stu-id="af22c-158">The result set displays 11 rows of data that show the quantity of items sold for each subcategory for four stores, and includes the following columns: StoreID, Subcategory, Quantity.</span></span>  
  
12. <span data-ttu-id="af22c-159">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="af22c-159">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="af22c-160">2. organizzare i dati, scegliere il layout e lo stile dalla creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="af22c-160">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="af22c-161">Utilizzare la procedura guidata per fornire una progettazione iniziale in cui visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="af22c-161">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="af22c-162">Il riquadro di anteprima nella procedura guidata consente di visualizzare il risultato del raggruppamento di dati prima di completare la progettazione della tabella o della matrice.</span><span class="sxs-lookup"><span data-stu-id="af22c-162">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="af22c-163">Per organizzare i dati in gruppi</span><span class="sxs-lookup"><span data-stu-id="af22c-163">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="af22c-164">Nella pagina **Disponi campi** trascinare Subcategory in **Gruppi di righe**.</span><span class="sxs-lookup"><span data-stu-id="af22c-164">On the **Arrange fields** page, drag Subcategory to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="af22c-165">Trascinare StoreID in **Gruppi di colonne**.</span><span class="sxs-lookup"><span data-stu-id="af22c-165">Drag StoreID to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="af22c-166">Trascinare Quantity in **Valori**.</span><span class="sxs-lookup"><span data-stu-id="af22c-166">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="af22c-167">Sono stati così organizzati i valori delle quantità vendute in righe raggruppate per sottocategorie.</span><span class="sxs-lookup"><span data-stu-id="af22c-167">You have organized the quantity sold values in rows grouped by subcategory.</span></span> <span data-ttu-id="af22c-168">Ogni punto vendita sarà rappresentato da una colonna.</span><span class="sxs-lookup"><span data-stu-id="af22c-168">There will be one column for each store.</span></span>  
  
4.  <span data-ttu-id="af22c-169">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="af22c-169">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="af22c-170">Nella pagina **scegliere un layout** , in **Opzioni**, verificare che sia selezionata l'opzione **Mostra subtotali e totali** complessivi.</span><span class="sxs-lookup"><span data-stu-id="af22c-170">On the **Choose a Layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="af22c-171">Quando si esegue il report, nell'ultima colonna verrà mostrata la quantità totale di ogni sottocategoria per tutti i punti vendita mentre nell'ultima riga verrà mostrata la quantità totale per tutte le sottocategorie per ogni punto vendita.</span><span class="sxs-lookup"><span data-stu-id="af22c-171">When you run the report, the last column will show the total quantity of each subcategory for all stores, and the last row will show the total quantity for all subcategories for each store.</span></span>  
  
6.  <span data-ttu-id="af22c-172">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="af22c-172">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="af22c-173">Nel riquadro Stili della pagina **scegliere uno stile** selezionare uno stile.</span><span class="sxs-lookup"><span data-stu-id="af22c-173">On the **Choose a Style** page, in the Styles pane, select a style.</span></span>  
  
8.  <span data-ttu-id="af22c-174">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="af22c-174">Click **Finish**.</span></span>  
  
     <span data-ttu-id="af22c-175">La matrice viene aggiunta all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="af22c-175">The matrix is added to the design surface.</span></span> <span data-ttu-id="af22c-176">Nella matrice sono visualizzate tre colonne e tre righe.</span><span class="sxs-lookup"><span data-stu-id="af22c-176">The matrix displays three columns and three rows.</span></span> <span data-ttu-id="af22c-177">Il contenuto delle celle nella prima riga è Sottocategoria, [StoreID] e Totale.</span><span class="sxs-lookup"><span data-stu-id="af22c-177">The contents of the cells in the first row are Subcategory, [StoreID], and Total.</span></span> <span data-ttu-id="af22c-178">Nelle celle della seconda riga sono visualizzate le espressioni che rappresentano la sottocategoria, la quantità di articoli venduti per ogni punto vendita e la quantità totale per ogni sottocategoria per tutti i punti vendita.</span><span class="sxs-lookup"><span data-stu-id="af22c-178">The contents of the cells in the second row contain expressions that represent the subcategory, the quantity of items sold for each store, and the total quantity for each subcategory for all stores.</span></span> <span data-ttu-id="af22c-179">Nelle celle della riga finale è visualizzato il totale complessivo per ogni punto vendita.</span><span class="sxs-lookup"><span data-stu-id="af22c-179">The cells in the final row display the grand total for each store.</span></span>  
  
9. <span data-ttu-id="af22c-180">Fare clic nella matrice, posizionare il puntatore sul bordo della prima colonna, fare clic sul quadratino di ridimensionamento ed espandere la larghezza della colonna.</span><span class="sxs-lookup"><span data-stu-id="af22c-180">Click in the matrix, hover over the edge of the first column, grab the handle, and expand the column width.</span></span>  
  
10. <span data-ttu-id="af22c-181">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-181">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="af22c-182">Il report verrà eseguito nel server di report, con il titolo e l'ora di elaborazione del report visualizzati.</span><span class="sxs-lookup"><span data-stu-id="af22c-182">The report runs on the report server and displays the title and the time the report processing occurred.</span></span>  
  
 <span data-ttu-id="af22c-183">In questo scenario, nelle intestazioni di colonna è visualizzato l'identificatore ma non il nome del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="af22c-183">In this scenario, the column headings display the store identifier but not the store name.</span></span> <span data-ttu-id="af22c-184">Più avanti in questa esercitazione, verrà aggiunta un'espressione per cercare il nome del punto vendita in un set di dati che contiene la coppia identificatore/nome del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="af22c-184">Later, you will add an expression to look up the store name in a dataset that contains store identifier/store name pairs.</span></span>  
  
##  <a name="3-add-a-query-parameter-to-create-a-report-parameter"></a><a name="Query"></a><span data-ttu-id="af22c-185">3. aggiungere un parametro di query per creare un parametro di report</span><span class="sxs-lookup"><span data-stu-id="af22c-185">3. Add a Query Parameter to Create a Report Parameter</span></span>  
 <span data-ttu-id="af22c-186">Quando si aggiunge un parametro di query a una query, in Generatore report viene creato automaticamente un parametro di report a valore singolo con proprietà predefinite per nome, messaggio di richiesta e tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="af22c-186">When you add a query parameter to a query, Report Builder automatically creates a single-valued report parameter with default properties for name, prompt, and data type.</span></span>  
  
#### <a name="to-add-a-query-parameter"></a><span data-ttu-id="af22c-187">Per aggiungere un parametro di query</span><span class="sxs-lookup"><span data-stu-id="af22c-187">To add a query parameter</span></span>  
  
1.  <span data-ttu-id="af22c-188">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="af22c-188">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="af22c-189">Nel riquadro Dati report espandere la cartella **Set di dati** , fare clic con il pulsante destro del mouse su **DataSet1**e quindi fare clic su **Query**.</span><span class="sxs-lookup"><span data-stu-id="af22c-189">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
3.  <span data-ttu-id="af22c-190">Aggiungere la [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clausola seguente come ultima riga della query:</span><span class="sxs-lookup"><span data-stu-id="af22c-190">Add the following [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause as the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID = (@StoreID)  
    ```  
  
     <span data-ttu-id="af22c-191">La `WHERE` clausola limita i dati recuperati all'identificatore del punto vendita specificato dal parametro di query *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="af22c-191">The `WHERE` clause limits the retrieved data to the store identifier that is specified by the query parameter *@StoreID*.</span></span>  
  
4.  <span data-ttu-id="af22c-192">Sulla barra degli strumenti Progettazione query fare clic su **Esegui** (**!**).</span><span class="sxs-lookup"><span data-stu-id="af22c-192">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="af22c-193">Viene aperta la finestra di dialogo **Definisci parametri query** nella quale viene richiesto un valore per il parametro di query *@StoreID*.</span><span class="sxs-lookup"><span data-stu-id="af22c-193">The **Define Query Parameters** dialog box opens and prompts for a value for the query parameter *@StoreID*.</span></span>  
  
5.  <span data-ttu-id="af22c-194">In **Valore parametro**digitare **200**.</span><span class="sxs-lookup"><span data-stu-id="af22c-194">In **Parameter Value**, type **200**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="af22c-195">Nel set di risultati vengono visualizzate le quantità vendute di accessori, cineprese e fotocamere SLR digitali per l'identificatore del punto vendita **200**.</span><span class="sxs-lookup"><span data-stu-id="af22c-195">The result set displays the quantities sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="af22c-196">Nel riquadro Dati report espandere la cartella **Parametri** .</span><span class="sxs-lookup"><span data-stu-id="af22c-196">In the Report Data pane, expand the **Parameters** folder.</span></span>  
  
 <span data-ttu-id="af22c-197">Si noti che è ora presente un parametro del report denominato *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="af22c-197">Notice that there is now a report parameter named *@StoreID*.</span></span> <span data-ttu-id="af22c-198">Per impostazione predefinita, il parametro ha il tipo di dati **Text**.</span><span class="sxs-lookup"><span data-stu-id="af22c-198">By default, the parameter has data type **Text**.</span></span> <span data-ttu-id="af22c-199">Poiché l'identificatore del punto vendita è un intero, nella procedura descritta di seguito il tipo di dati verrà modificato in Integer.</span><span class="sxs-lookup"><span data-stu-id="af22c-199">Because the store identifier is an integer, you will change the data type to Integer in the next procedure.</span></span>  
  
##  <a name="4-change-default-data-type-and-other-properties-for-a-report-parameter"></a><a name="ChangeDefaultProperties"></a><span data-ttu-id="af22c-200">4. modificare il tipo di dati predefinito e altre proprietà per un parametro di report</span><span class="sxs-lookup"><span data-stu-id="af22c-200">4. Change Default Data Type and Other Properties for a Report Parameter</span></span>  
 <span data-ttu-id="af22c-201">Dopo aver creato un parametro di report, è possibile impostare i valori predefiniti per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="af22c-201">After a report parameter is created, you can adjust the default values for properties.</span></span>  
  
#### <a name="to-change-the-default-data-type-for-a-report-parameter"></a><span data-ttu-id="af22c-202">Per modificare il tipo di dati predefinito per un parametro di report</span><span class="sxs-lookup"><span data-stu-id="af22c-202">To change the default data type for a report parameter</span></span>  
  
1.  <span data-ttu-id="af22c-203">Nel riquadro dei dati del report sotto il nodo **parametri** fare clic con il pulsante destro del mouse su *@StoreID* , quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="af22c-203">In the Report Data pane under the **Parameters** node, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="af22c-204">In messaggio di richiesta digitare **identificatore archivio?**</span><span class="sxs-lookup"><span data-stu-id="af22c-204">In Prompt, type **Store identifier?**</span></span> <span data-ttu-id="af22c-205">Questo testo viene visualizzato nella barra degli strumenti del visualizzatore di report quando si esegue il report.</span><span class="sxs-lookup"><span data-stu-id="af22c-205">This text appears on the report viewer toolbar when you run the report.</span></span>  
  
3.  <span data-ttu-id="af22c-206">In **Tipo di dati**selezionare **Integer**nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="af22c-206">In **Data type**, from the drop-down list, select **Integer**.</span></span>  
  
4.  <span data-ttu-id="af22c-207">Accettare i valori predefiniti rimanenti nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="af22c-207">Accept the remaining default values in the dialog box.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="af22c-208">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-208">Preview the report.</span></span> <span data-ttu-id="af22c-209">Il Visualizzatore di report Visualizza la richiesta di *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="af22c-209">The report viewer displays the prompt for *@StoreID*.</span></span>  
  
7.  <span data-ttu-id="af22c-210">Nella barra degli strumenti del visualizzatore di report, accanto a Store ID, digitare **200**e quindi fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="af22c-210">On the report viewer toolbar, next to Store ID, type **200**, and then click **View Report**.</span></span>  
  
##  <a name="4a-add-a-dataset-to-provide-available-values-and-display-names"></a><a name="AddDataset"></a><span data-ttu-id="af22c-211">4a.</span><span class="sxs-lookup"><span data-stu-id="af22c-211">4a.</span></span> <span data-ttu-id="af22c-212">Aggiungere un set di dati per fornire i valori disponibili e i nomi visualizzati</span><span class="sxs-lookup"><span data-stu-id="af22c-212">Add a Dataset to Provide Available Values and Display Names</span></span>  
 <span data-ttu-id="af22c-213">Per assicurarsi che un utente possa digitare solo valori validi per un parametro, è possibile creare un elenco a discesa di valori tra cui scegliere.</span><span class="sxs-lookup"><span data-stu-id="af22c-213">To ensure a user can type only valid values for a parameter, you can create a drop-down list of values to choose from.</span></span> <span data-ttu-id="af22c-214">I valori possono provenire da un set di dati o da un elenco che si specifica.</span><span class="sxs-lookup"><span data-stu-id="af22c-214">The values can come from a dataset or from a list that you specify.</span></span> <span data-ttu-id="af22c-215">I valori disponibili devono provenire da un set di dati che dispone di una query che non contiene un riferimento al parametro.</span><span class="sxs-lookup"><span data-stu-id="af22c-215">Available values must be supplied from a dataset that has a query that does not contain a reference to the parameter.</span></span>  
  
#### <a name="to-create-a-dataset-for-valid-values-for-a-parameter"></a><span data-ttu-id="af22c-216">Per creare un set di dati per i valori validi per un parametro</span><span class="sxs-lookup"><span data-stu-id="af22c-216">To create a dataset for valid values for a parameter</span></span>  
  
1.  <span data-ttu-id="af22c-217">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="af22c-217">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="af22c-218">Nel riquadro Dati report fare clic con il pulsante destro del mouse sula cartella **Datasets** e quindi fare clic su **Aggiungi set di dati**.</span><span class="sxs-lookup"><span data-stu-id="af22c-218">In the Report Data pane, right-click the **Datasets** folder, and then click **Add Dataset**.</span></span>  
  
3.  <span data-ttu-id="af22c-219">In **Nome**digitare **Punti vendita**.</span><span class="sxs-lookup"><span data-stu-id="af22c-219">In **Name**, type **Stores**.</span></span>  
  
4.  <span data-ttu-id="af22c-220">Selezionare l'opzione **Usa un set di dati incorporato nel report** .</span><span class="sxs-lookup"><span data-stu-id="af22c-220">Select the **Use a dataset embedded in my report** option.</span></span>  
  
5.  <span data-ttu-id="af22c-221">In **origine dati**scegliere dall'elenco a discesa l'origine dati creata nella prima procedura.</span><span class="sxs-lookup"><span data-stu-id="af22c-221">In **Data source**, from the drop-down list, choose the data source you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="af22c-222">In **Tipo di query**verificare che sia selezionata l'opzione **Testo** .</span><span class="sxs-lookup"><span data-stu-id="af22c-222">In **Query type**, verify that **Text** is selected.</span></span>  
  
7.  <span data-ttu-id="af22c-223">In **Query**incollare il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="af22c-223">In **Query**, paste the following text:</span></span>  
  
    ```  
    SELECT 200 AS StoreID, 'Contoso Catalog Store' as StoreName  
    UNION SELECT 199 AS StoreID, 'Contoso North America Online Store' as StoreName  
    UNION SELECT 307 AS StoreID, 'Contoso Asia Online Store' as StoreName  
    UNION SELECT 306 AS StoreID, 'Contoso Europe Online Store' as StoreName  
    ```  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="af22c-224">Nel riquadro Dati report sono visualizzati i campi StoreID e StoreName nel nodo del set di dati **Punti vendita** .</span><span class="sxs-lookup"><span data-stu-id="af22c-224">The Report Data pane displays the fields StoreID and StoreName under the **Stores** dataset node.</span></span>  
  
##  <a name="4b-specify-available-values-to-create-a-drop-down-list-of-values"></a><a name="AvailableValues"></a><span data-ttu-id="af22c-225">4B.</span><span class="sxs-lookup"><span data-stu-id="af22c-225">4b.</span></span> <span data-ttu-id="af22c-226">Specificare i valori disponibili per creare un elenco a discesa di valori</span><span class="sxs-lookup"><span data-stu-id="af22c-226">Specify Available Values to Create a Drop-down List of Values</span></span>  
 <span data-ttu-id="af22c-227">Dopo aver creato un set di dati per fornire i valori disponibili, è necessario modificare le proprietà del report per specificare quale set di dati e quale campo utilizzare per popolare l'elenco a discesa di valori validi nella barra degli strumenti del visualizzatore di report.</span><span class="sxs-lookup"><span data-stu-id="af22c-227">After you create a dataset to provide available values, you must change the report properties to specify which dataset and which field to use to populate the drop-down list of valid values on the reportviewer toolbar.</span></span>  
  
#### <a name="to-provide-available-values-for-a-parameter-from-a-dataset"></a><span data-ttu-id="af22c-228">Per fornire i valori disponibili per un parametro da un set di dati</span><span class="sxs-lookup"><span data-stu-id="af22c-228">To provide available values for a parameter from a dataset</span></span>  
  
1.  <span data-ttu-id="af22c-229">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sul parametro *@StoreID* , quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="af22c-229">In the Report Data pane, right-click the parameter *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="af22c-230">Fare clic su **Valori disponibili**e quindi su **Ottieni valori da una query**.</span><span class="sxs-lookup"><span data-stu-id="af22c-230">Click **Available Values**, and then click **Get values from a query**.</span></span>  
  
3.  <span data-ttu-id="af22c-231">In **Set di dati**fare clic su **Punti vendita**nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="af22c-231">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
4.  <span data-ttu-id="af22c-232">In **Campo valori**fare clic su StoreID nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="af22c-232">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
5.  <span data-ttu-id="af22c-233">In **Campo etichette**fare clic su StoreName nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="af22c-233">In **Label field**, from the drop-down list, click StoreName.</span></span> <span data-ttu-id="af22c-234">Il campo etichette consente di specificare il nome visualizzato per il valore.</span><span class="sxs-lookup"><span data-stu-id="af22c-234">The label field specifies the display name for the value.</span></span>  
  
6.  <span data-ttu-id="af22c-235">Fare clic su **General**.</span><span class="sxs-lookup"><span data-stu-id="af22c-235">Click **General**.</span></span>  
  
7.  <span data-ttu-id="af22c-236">In messaggio di richiesta digitare **Nome archivio?**</span><span class="sxs-lookup"><span data-stu-id="af22c-236">In Prompt, type **Store name?**</span></span>  
  
     <span data-ttu-id="af22c-237">L'utente selezionerà ora da un elenco di nomi di punti vendita anziché di identificatori.</span><span class="sxs-lookup"><span data-stu-id="af22c-237">The user will now select from a list of store names instead of store identifiers.</span></span> <span data-ttu-id="af22c-238">Si noti che il tipo di dati del parametro rimane **Integer** perché il parametro si basa sull'identificatore del punto vendita, non sul nome.</span><span class="sxs-lookup"><span data-stu-id="af22c-238">Note that the parameter data type remains **Integer** because the parameter is based on the store identifier, not the store name.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="af22c-239">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-239">Preview the report.</span></span>  
  
     <span data-ttu-id="af22c-240">Nella barra degli strumenti del Visualizzatore di report, la casella di testo del parametro è ora un elenco a discesa in cui è visualizzato **\<Select a Value>** .</span><span class="sxs-lookup"><span data-stu-id="af22c-240">In the report viewer toolbar, the parameter text box is now a drop-down list that displays **\<Select a Value>**.</span></span>  
  
10. <span data-ttu-id="af22c-241">Nell'elenco a discesa selezionare Contoso Catalog Store e quindi fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="af22c-241">From the drop-down list, select Contoso Catalog Store, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="af22c-242">Nel report viene visualizzata la quantità venduta di accessori, cineprese e fotocamere SLR digitali per l'identificatore del punto vendita **200**.</span><span class="sxs-lookup"><span data-stu-id="af22c-242">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4c-specify-default-values-so-the-report-runs-automatically"></a><a name="DefaultValues"></a><span data-ttu-id="af22c-243">4C.</span><span class="sxs-lookup"><span data-stu-id="af22c-243">4c.</span></span> <span data-ttu-id="af22c-244">Specificare i valori predefiniti così che il report possa essere eseguito automaticamente</span><span class="sxs-lookup"><span data-stu-id="af22c-244">Specify Default Values so the Report Runs Automatically</span></span>  
 <span data-ttu-id="af22c-245">È possibile specificare un valore predefinito per ciascun parametro in modo che il report venga eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="af22c-245">You can specify a default value for each parameter so the report runs automatically.</span></span>  
  
#### <a name="to-specify-a-default-value-from-a-dataset"></a><span data-ttu-id="af22c-246">Per specificare un valore predefinito da un set di dati</span><span class="sxs-lookup"><span data-stu-id="af22c-246">To specify a default value from a dataset</span></span>  
  
1.  <span data-ttu-id="af22c-247">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="af22c-247">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="af22c-248">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse su *@StoreID* , quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="af22c-248">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="af22c-249">Fare clic su **valori predefiniti**e quindi su **Ottieni valori da una query**.</span><span class="sxs-lookup"><span data-stu-id="af22c-249">Click **Default Values**, and then click **Get values from a query**.</span></span>  
  
4.  <span data-ttu-id="af22c-250">In **Set di dati**fare clic su **Punti vendita**nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="af22c-250">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
5.  <span data-ttu-id="af22c-251">In **Campo valori**fare clic su StoreID nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="af22c-251">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="af22c-252">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-252">Preview the report.</span></span>  
  
 <span data-ttu-id="af22c-253">Per *@StoreID* , nel Visualizzatore di report viene visualizzato il valore "Contoso America del Nord Online Store".</span><span class="sxs-lookup"><span data-stu-id="af22c-253">For *@StoreID*, the report viewer displays the value "Contoso North America Online Store".</span></span> <span data-ttu-id="af22c-254">Si tratta del primo valore del set di risultati per gli **archivi**del set di dati.</span><span class="sxs-lookup"><span data-stu-id="af22c-254">This is the first value from the result set for the dataset **Stores**.</span></span> <span data-ttu-id="af22c-255">Nel report viene visualizzata la quantità venduta di fotocamere digitali per l'identificatore del punto vendita **199**.</span><span class="sxs-lookup"><span data-stu-id="af22c-255">The report displays the quantity sold for Digital Cameras for store identifier **199**.</span></span>  
  
#### <a name="to-specify-a-custom-default-value"></a><span data-ttu-id="af22c-256">Per specificare un valore predefinito personalizzato</span><span class="sxs-lookup"><span data-stu-id="af22c-256">To specify a custom default value</span></span>  
  
1.  <span data-ttu-id="af22c-257">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="af22c-257">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="af22c-258">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse su *@StoreID* , quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="af22c-258">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="af22c-259">Fare clic su **valori predefiniti**, quindi fare clic su **Imposta valori**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="af22c-259">Click **Default Values**, and click **Specify values**, and then click **Add**.</span></span> <span data-ttu-id="af22c-260">Verrà aggiunta una nuova riga di valori.</span><span class="sxs-lookup"><span data-stu-id="af22c-260">A new value row is added.</span></span>  
  
4.  <span data-ttu-id="af22c-261">In **Valore**digitare **200**.</span><span class="sxs-lookup"><span data-stu-id="af22c-261">In **Value**, type **200**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="af22c-262">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-262">Preview the report.</span></span>  
  
 <span data-ttu-id="af22c-263">Per *@StoreID* , nel Visualizzatore di report viene visualizzato il valore "Contoso Catalog Store".</span><span class="sxs-lookup"><span data-stu-id="af22c-263">For *@StoreID*, the report viewer displays the value "Contoso Catalog Store".</span></span> <span data-ttu-id="af22c-264">Si tratta del nome visualizzato per l'identificatore del punto vendita **200**.</span><span class="sxs-lookup"><span data-stu-id="af22c-264">This is the display name for store identifier **200**.</span></span> <span data-ttu-id="af22c-265">Nel report viene visualizzata la quantità venduta di accessori, cineprese e fotocamere SLR digitali per l'identificatore del punto vendita **200**.</span><span class="sxs-lookup"><span data-stu-id="af22c-265">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4d-look-up-a-value-from-a-dataset-that-has-namevalue-pairs"></a><a name="NameValue"></a><span data-ttu-id="af22c-266">4D.</span><span class="sxs-lookup"><span data-stu-id="af22c-266">4d.</span></span> <span data-ttu-id="af22c-267">Cercare un valore da un set di dati che disponga di coppie nome/valore</span><span class="sxs-lookup"><span data-stu-id="af22c-267">Look up a Value from a Dataset that has Name/Value Pairs</span></span>  
 <span data-ttu-id="af22c-268">Un set di dati potrebbe contenere sia l'identificatore e che il campo del nome corrispondente.</span><span class="sxs-lookup"><span data-stu-id="af22c-268">A dataset might contain both the identifier and the corresponding name field.</span></span> <span data-ttu-id="af22c-269">Quando si dispone solo di un identificatore, è possibile cercare il nome corrispondente in un set di dati creato che include coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="af22c-269">When you only have an identifier, you can look up the corresponding name in a dataset that you created that includes name/value pairs.</span></span>  
  
#### <a name="to-look-up-a-value-from-a-dataset"></a><span data-ttu-id="af22c-270">Per cercare un valore in un set di dati</span><span class="sxs-lookup"><span data-stu-id="af22c-270">To look up a value from a dataset</span></span>  
  
1.  <span data-ttu-id="af22c-271">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="af22c-271">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="af22c-272">Nell'area di progettazione nella matrice nell'intestazione di colonna della prima riga fare clic con il pulsante destro del mouse su `[StoreID]` e fare clic su **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="af22c-272">On the design surface, in the matrix, in the first row column header, right-click `[StoreID]` and then click **Expression**.</span></span>  
  
3.  <span data-ttu-id="af22c-273">Nel riquadro dell'espressione, eliminare qualsiasi testo eccetto il segno `equals` (=) iniziale.</span><span class="sxs-lookup"><span data-stu-id="af22c-273">In the expression pane, delete all text except the beginning `equals` (=).</span></span>  
  
4.  <span data-ttu-id="af22c-274">In **Categoria**espandere **Funzioni comuni**e fare clic su **Varie**.</span><span class="sxs-lookup"><span data-stu-id="af22c-274">In **Category**, expand **Common Functions**, and click **Miscellaneous**.</span></span> <span data-ttu-id="af22c-275">Nel riquadro Elemento è visualizzato un set di funzioni.</span><span class="sxs-lookup"><span data-stu-id="af22c-275">The Item pane displays a set of functions.</span></span>  
  
5.  <span data-ttu-id="af22c-276">In Elemento fare doppio clic su **Ricerca**.</span><span class="sxs-lookup"><span data-stu-id="af22c-276">In Item, double-click **Lookup**.</span></span> <span data-ttu-id="af22c-277">Nel riquadro dell'espressione viene visualizzato `=Lookup(`.</span><span class="sxs-lookup"><span data-stu-id="af22c-277">The expression pane displays `=Lookup(`.</span></span> <span data-ttu-id="af22c-278">Nel riquadro Esempio viene visualizzato un esempio di sintassi di Lookup.</span><span class="sxs-lookup"><span data-stu-id="af22c-278">The Example pane displays an example of Lookup syntax.</span></span>  
  
6.  <span data-ttu-id="af22c-279">Digitare l'espressione seguente: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span><span class="sxs-lookup"><span data-stu-id="af22c-279">Type the following expression: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span></span>  
  
     <span data-ttu-id="af22c-280">La funzione di ricerca accetta il valore per StoreID, lo cerca nel set di dati "Punti vendita" e restituisce il valore StoreName.</span><span class="sxs-lookup"><span data-stu-id="af22c-280">The Lookup function takes the value for StoreID, looks it up in the "Stores" dataset, and returns the StoreName value.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="af22c-281">L'intestazione di colonna Store contiene il testo visualizzato per un'espressione complessa: **<\<Expr>>** .</span><span class="sxs-lookup"><span data-stu-id="af22c-281">The store column header contains the display text for a complex expression: **<\<Expr>>**.</span></span>  
  
8.  <span data-ttu-id="af22c-282">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-282">Preview the report.</span></span>  
  
 <span data-ttu-id="af22c-283">La casella di testo all'inizio di ogni pagina visualizza il nome del punto vendita anziché l'identificatore.</span><span class="sxs-lookup"><span data-stu-id="af22c-283">The text box at the top of each page displays the store name instead of the store identifier.</span></span>  
  
##  <a name="5-display-the-selected-parameter-value-in-the-report"></a><a name="Expression"></a><span data-ttu-id="af22c-284">5. visualizzare il valore del parametro selezionato nel report</span><span class="sxs-lookup"><span data-stu-id="af22c-284">5. Display the Selected Parameter Value in the Report</span></span>  
 <span data-ttu-id="af22c-285">Quando un utente ha delle domande su un report, è di aiuto sapere quali valori di parametri sono stati scelti.</span><span class="sxs-lookup"><span data-stu-id="af22c-285">When a user has questions about a report, it helps to know which parameter values they chose.</span></span> <span data-ttu-id="af22c-286">È possibile mantenere i valori selezionati dall'utente per ogni parametro nel report.</span><span class="sxs-lookup"><span data-stu-id="af22c-286">You can preserve user-selected values for each parameter in the report.</span></span> <span data-ttu-id="af22c-287">Un modo consiste nel visualizzare i parametri in una casella di testo nel piè di pagina della pagina.</span><span class="sxs-lookup"><span data-stu-id="af22c-287">One way is to display the parameters in a text box in the page footer.</span></span>  
  
#### <a name="to-display-the-selected-parameter-value-and-label-on-a-page-footer"></a><span data-ttu-id="af22c-288">Per visualizzare il valore del parametro selezionato e l'etichetta nel piè di pagina di una pagina</span><span class="sxs-lookup"><span data-stu-id="af22c-288">To display the selected parameter value and label on a page footer</span></span>  
  
1.  <span data-ttu-id="af22c-289">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="af22c-289">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="af22c-290">Fare clic con il pulsante destro del mouse sul piè di pagina, scegliere **Inserisci**, quindi fare clic su **casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="af22c-290">Right-click the page footer, point to **Insert**, and then click **Text Box**.</span></span> <span data-ttu-id="af22c-291">Trascinare la casella di testo accanto alla casella di testo con il timestamp.</span><span class="sxs-lookup"><span data-stu-id="af22c-291">Drag the text box next to the text box with the time stamp.</span></span> <span data-ttu-id="af22c-292">Fare clic sul quadratino di ridimensionamento laterale della casella di testo ed espanderla in larghezza.</span><span class="sxs-lookup"><span data-stu-id="af22c-292">Grab the side handle of the text box and expand the width.</span></span>  
  
3.  <span data-ttu-id="af22c-293">Trascinare il parametro dal riquadro dei dati del report nella *@StoreID* casella di testo.</span><span class="sxs-lookup"><span data-stu-id="af22c-293">From the Report Data pane, drag the parameter *@StoreID* to the text box.</span></span> <span data-ttu-id="af22c-294">Nella casella di testo viene visualizzato `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="af22c-294">The text box displays `[@StoreID]`.</span></span>  
  
4.  <span data-ttu-id="af22c-295">Per visualizzare l'etichetta del parametro, fare clic nella casella di testo finché il cursore di inserimento non viene visualizzato dopo l'espressione esistente, immettere uno spazio, quindi trascinare un'altra copia del parametro dal riquadro dei dati del report nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="af22c-295">To display the parameter label, click in the text box until the insert cursor appears after the existing expression, type a space, and then drag another copy of the parameter from the Report Data pane to the text box.</span></span> <span data-ttu-id="af22c-296">Nella casella di testo viene visualizzato `[@StoreID] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="af22c-296">The text box displays `[@StoreID] [@StoreID]`.</span></span>  
  
5.  <span data-ttu-id="af22c-297">Fare clic con il pulsante destro del mouse sulla prima espressione, quindi scegliere **espressione**.</span><span class="sxs-lookup"><span data-stu-id="af22c-297">Right-click the first expression and click **Expression**.</span></span> <span data-ttu-id="af22c-298">Verrà visualizzata la finestra di dialogo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="af22c-298">The **Expression** dialog box opens.</span></span> <span data-ttu-id="af22c-299">Sostituire il testo `Value` in base a `Label`.</span><span class="sxs-lookup"><span data-stu-id="af22c-299">Replace the text `Value` by `Label`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="af22c-300">Verrà visualizzato il testo: `[@StoreID.Label] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="af22c-300">The text displays: `[@StoreID.Label] [@StoreID]`.</span></span>  
  
7.  <span data-ttu-id="af22c-301">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-301">Preview the report.</span></span>  
  
##  <a name="6-use-the-report-parameter-in-a-filter"></a><a name="Filter"></a><span data-ttu-id="af22c-302">6. utilizzare il parametro del report in un filtro</span><span class="sxs-lookup"><span data-stu-id="af22c-302">6. Use the Report Parameter in a Filter</span></span>  
 <span data-ttu-id="af22c-303">I filtri consentono di controllare quali dati utilizzare in un report dopo averli recuperati da un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="af22c-303">Filters help control which data to use in a report after it is retrieved from an external data source.</span></span> <span data-ttu-id="af22c-304">Per aiutare un utente a controllare i dati che desidera vedere, è possibile includere il parametro del report in un filtro per la matrice.</span><span class="sxs-lookup"><span data-stu-id="af22c-304">To let a user help control the data they want to see, you can include the report parameter in a filter for the matrix.</span></span>  
  
#### <a name="to-specify-a-parameter-in-a-matrix-filter"></a><span data-ttu-id="af22c-305">Per specificare un parametro in un filtro della matrice</span><span class="sxs-lookup"><span data-stu-id="af22c-305">To specify a parameter in a matrix filter</span></span>  
  
1.  <span data-ttu-id="af22c-306">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="af22c-306">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="af22c-307">Fare clic con il pulsante destro del mouse sul quadratino di ridimensionamento dell'intestazione di una riga o colonna della matrice e quindi fare clic su **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="af22c-307">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="af22c-308">Fare clic su **Filtri**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="af22c-308">Click **Filters**, and then click **Add**.</span></span> <span data-ttu-id="af22c-309">Verrà visualizzata una nuova riga del filtro.</span><span class="sxs-lookup"><span data-stu-id="af22c-309">A new filter row appears.</span></span>  
  
4.  <span data-ttu-id="af22c-310">In **Espressione**selezionare il campo del set di dati StoreID nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="af22c-310">In **Expression**, from the drop-down list, select the dataset field StoreID.</span></span> <span data-ttu-id="af22c-311">I dati visualizzati sono di tipo **Integer**.</span><span class="sxs-lookup"><span data-stu-id="af22c-311">The data type displays **Integer**.</span></span> <span data-ttu-id="af22c-312">Se il valore dell'espressione è un campo del set di dati, il tipo di dati viene impostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="af22c-312">When the expression value is a dataset field, the data type is set automatically.</span></span>  
  
5.  <span data-ttu-id="af22c-313">In **operatore**verificare che `equals` sia selezionata l'opzione (=).</span><span class="sxs-lookup"><span data-stu-id="af22c-313">In **Operator**, verify that `equals` (=) is selected.</span></span>  
  
6.  <span data-ttu-id="af22c-314">In **Valore**digitare `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="af22c-314">In **Value**, type `[@StoreID]`.</span></span> <span data-ttu-id="af22c-315">`[@StoreID]` è la sintassi dell'espressione semplice che rappresenta `=Parameters!StoreID.Value`.</span><span class="sxs-lookup"><span data-stu-id="af22c-315">`[@StoreID]` is the simple expression syntax that represents `=Parameters!StoreID.Value`.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="af22c-316">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-316">Preview the report.</span></span>  
  
     <span data-ttu-id="af22c-317">La matrice visualizza dati solo per "Contoso Catalog Store".</span><span class="sxs-lookup"><span data-stu-id="af22c-317">The matrix displays data only for "Contoso Catalog Store".</span></span>  
  
9. <span data-ttu-id="af22c-318">Nella barra degli strumenti del visualizzatore di report, per **Nome punto vendita?** selezionare **Contoso Asia Online Store**e quindi fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="af22c-318">On the report viewer toolbar, for **Store name?**, select **Contoso Asia Online Store**, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="af22c-319">La matrice visualizza dati che corrispondono al punto vendita che è stato selezionato.</span><span class="sxs-lookup"><span data-stu-id="af22c-319">The matrix displays data that corresponds to the store that you selected.</span></span>  
  
##  <a name="7-change-the-report-parameter-to-accept-multiple-values"></a><a name="Multivalued"></a><span data-ttu-id="af22c-320">7. modificare il parametro del report per accettare più valori</span><span class="sxs-lookup"><span data-stu-id="af22c-320">7. Change the Report Parameter to Accept Multiple Values</span></span>  
 <span data-ttu-id="af22c-321">Per modificare un parametro da singolo a multivalore, è necessario modificare la query e tutte le espressioni che contengono un riferimento a quel parametro, inclusi i filtri.</span><span class="sxs-lookup"><span data-stu-id="af22c-321">To change a parameter from single to multivalued, you must change the query, and all expressions that contain a reference to the parameter, including filters.</span></span> <span data-ttu-id="af22c-322">Un parametro multivalore è una matrice di valori.</span><span class="sxs-lookup"><span data-stu-id="af22c-322">A multivalued parameter is an array of values.</span></span> <span data-ttu-id="af22c-323">In una query del set di dati, la sintassi della query deve verificare l'inclusione di un valore in un set di valori.</span><span class="sxs-lookup"><span data-stu-id="af22c-323">In a dataset query, query syntax must test for inclusion of one value in a set of values.</span></span> <span data-ttu-id="af22c-324">In un'espressione di report, la sintassi dell'espressione deve accedere a una matrice di valori anziché a un valore singolo.</span><span class="sxs-lookup"><span data-stu-id="af22c-324">In a report expression, expression syntax must access an array of values instead of an individual value.</span></span>  
  
#### <a name="to-change-a-parameter-from-single-to-multivalued"></a><span data-ttu-id="af22c-325">Per modificare un parametro da singolo a multivalore</span><span class="sxs-lookup"><span data-stu-id="af22c-325">To change a parameter from single to multivalued</span></span>  
  
1.  <span data-ttu-id="af22c-326">Passare alla Visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="af22c-326">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="af22c-327">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse su *@StoreID* , quindi scegliere **Proprietà parametri**.</span><span class="sxs-lookup"><span data-stu-id="af22c-327">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="af22c-328">Selezionare **Consenti più valori**.</span><span class="sxs-lookup"><span data-stu-id="af22c-328">Select **Allow multiple values**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="af22c-329">Nel riquadro Dati report espandere la cartella **Set di dati** , fare clic con il pulsante destro del mouse su **DataSet1**e quindi fare clic su **Query**.</span><span class="sxs-lookup"><span data-stu-id="af22c-329">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
6.  <span data-ttu-id="af22c-330">Modificare `equals` (=) in `IN` nella [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clausola nell'ultima riga della query:</span><span class="sxs-lookup"><span data-stu-id="af22c-330">Change `equals` (=) to `IN` in the [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause in the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID IN (@StoreID)  
    ```  
  
     <span data-ttu-id="af22c-331">L'operatore `IN` verifica un valore per l'inclusione in un set di valori.</span><span class="sxs-lookup"><span data-stu-id="af22c-331">The `IN` operator tests a value for inclusion in a set of values.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="af22c-332">Fare clic con il pulsante destro del mouse sul quadratino di ridimensionamento dell'intestazione di una riga o colonna della matrice e quindi fare clic su **Proprietà Tablix**.</span><span class="sxs-lookup"><span data-stu-id="af22c-332">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
9. <span data-ttu-id="af22c-333">Fare clic su **Filtri**.</span><span class="sxs-lookup"><span data-stu-id="af22c-333">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="af22c-334">In **Operatore**selezionare **In**.</span><span class="sxs-lookup"><span data-stu-id="af22c-334">In **Operator**, select **In**.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="af22c-335">Nella casella di testo in cui è visualizzato il parametro nel piè di pagina, eliminare qualsiasi testo.</span><span class="sxs-lookup"><span data-stu-id="af22c-335">In the text box that displays the parameter in the page footer, delete all text.</span></span>  
  
13. <span data-ttu-id="af22c-336">Fare clic con il pulsante destro del mouse sulla casella di testo e quindi fare clic su **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="af22c-336">Right-click the text box, and then click **Expression**.</span></span> <span data-ttu-id="af22c-337">Digitare l'espressione seguente: `=Join(Parameters!StoreID.Label, ", ")`</span><span class="sxs-lookup"><span data-stu-id="af22c-337">Type the following expression: `=Join(Parameters!StoreID.Label, ", ")`</span></span>  
  
     <span data-ttu-id="af22c-338">Questa espressione concatena tutti i nomi dei punti vendita che l'utente ha selezionato.</span><span class="sxs-lookup"><span data-stu-id="af22c-338">This expression concatenates all store names that the user selected.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
15. <span data-ttu-id="af22c-339">Fare clic nella casella di testo di fronte all'espressione appena creata, quindi digitare quanto segue: Valori del parametro selezionati:.</span><span class="sxs-lookup"><span data-stu-id="af22c-339">Click in the text box in front of the expression that you just created, and then type the following: Parameter Values Selected:.</span></span>  
  
16. <span data-ttu-id="af22c-340">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-340">Preview the report.</span></span>  
  
17. <span data-ttu-id="af22c-341">Fare clic sull'elenco a discesa accanto a Nome punto vendita?</span><span class="sxs-lookup"><span data-stu-id="af22c-341">Click the drop-down list next to Store Name?</span></span>  
  
     <span data-ttu-id="af22c-342">Ogni valore valido appare accanto a una casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="af22c-342">Each valid value appears next to a check box.</span></span>  
  
18. <span data-ttu-id="af22c-343">Fare clic su **Seleziona tutto**quindi fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="af22c-343">Click **Select All**, and then click **View Report**.</span></span>  
  
     <span data-ttu-id="af22c-344">Il report visualizza la quantità venduta per tutte le sottocategorie per tutti i punti vendita.</span><span class="sxs-lookup"><span data-stu-id="af22c-344">The report displays the quantity sold for all subcategories for all stores.</span></span>  
  
19. <span data-ttu-id="af22c-345">Dall'elenco a discesa fare clic su **Seleziona tutto** per cancellare l'elenco, fare clic su "Contoso Catalog Store" e "Contoso Asia Online Store" e quindi scegliere **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="af22c-345">From the drop-down list, click **Select All** to clear the list, click "Contoso Catalog Store" and "Contoso Asia Online Store", and then click **View Report**.</span></span>  
  
##  <a name="8-add-a-boolean-parameter-for-conditional-visibility"></a><a name="Boolean"></a><span data-ttu-id="af22c-346">8. aggiungere un parametro booleano per la visibilità condizionale</span><span class="sxs-lookup"><span data-stu-id="af22c-346">8. Add a Boolean Parameter for Conditional Visibility</span></span>  
  
#### <a name="to-add-a-boolean-parameter"></a><span data-ttu-id="af22c-347">Per aggiungere un parametro booleano</span><span class="sxs-lookup"><span data-stu-id="af22c-347">To add a boolean parameter</span></span>  
  
1.  <span data-ttu-id="af22c-348">Nell'area di progettazione nel riquadro Dati report fare clic con il pulsante destro del mouse su **Parametri**e fare clic su **Aggiungi parametro**.</span><span class="sxs-lookup"><span data-stu-id="af22c-348">On the design surface, in the Report Data pane, right-click **Parameters**, and click **Add Parameter**.</span></span>  
  
2.  <span data-ttu-id="af22c-349">Nella casella **Nome**digitare ShowSelections.</span><span class="sxs-lookup"><span data-stu-id="af22c-349">In **Name**, type ShowSelections.</span></span>  
  
3.  <span data-ttu-id="af22c-350">In **Messaggio di richiesta**digitare Mostra selezioni?</span><span class="sxs-lookup"><span data-stu-id="af22c-350">In **Prompt**, type Show selections?</span></span>  
  
4.  <span data-ttu-id="af22c-351">In **tipo di dati**, nell'elenco a discesa, fare clic su **Boolean**.</span><span class="sxs-lookup"><span data-stu-id="af22c-351">In **Data type**, from the drop-down list, click **Boolean**.</span></span>  
  
5.  <span data-ttu-id="af22c-352">Fare clic su **Valori predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="af22c-352">Click **Default Values**.</span></span>  
  
6.  <span data-ttu-id="af22c-353">Fare clic su **Imposta valori**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="af22c-353">Click **Specify value**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="af22c-354">In **Valore**digitare **False**.</span><span class="sxs-lookup"><span data-stu-id="af22c-354">In **Value**, type **False**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-set-visibility-based-on-a-boolean-parameter"></a><span data-ttu-id="af22c-355">Per impostare la visibilità in base a un parametro booleano</span><span class="sxs-lookup"><span data-stu-id="af22c-355">To set visibility based on a boolean parameter</span></span>  
  
1.  <span data-ttu-id="af22c-356">Nell'area di progettazione fare clic con il pulsante destro del mouse nella casella di testo nel piè di pagina che visualizza i valori del parametro e quindi fare clic su **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="af22c-356">On the design surface, right-click the text box in the page footer that displays the parameter values, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="af22c-357">Fare clic su **Visibilità**.</span><span class="sxs-lookup"><span data-stu-id="af22c-357">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="af22c-358">Selezionare l'opzione **Mostra o nascondi in base a un'espressione**e quindi fare clic sul pulsante di espressione **Fx**.</span><span class="sxs-lookup"><span data-stu-id="af22c-358">Select the option **Show or hide based on an expression**, and then click the expression button **Fx**.</span></span>  
  
4.  <span data-ttu-id="af22c-359">Digitare l'espressione seguente: `=Not Parameters!ShowSelections.Value`</span><span class="sxs-lookup"><span data-stu-id="af22c-359">Type the following expression: `=Not Parameters!ShowSelections.Value`</span></span>  
  
     <span data-ttu-id="af22c-360">L'opzione di visibilità della casella di testo viene controllata dalla proprietà Hidden.</span><span class="sxs-lookup"><span data-stu-id="af22c-360">The text box Visibility option is controlled by the property Hidden.</span></span> <span data-ttu-id="af22c-361">Applicare l'operatore `Not` in modo che quando viene selezionato il parametro, la proprietà Hidden è impostata su false e la casella di testo verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="af22c-361">Apply the `Not` operator so that when the parameter is selected, the Hidden property is false, and the text box will be displayed.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="af22c-362">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-362">Preview the report.</span></span>  
  
     <span data-ttu-id="af22c-363">Non è visualizzata la casella di testo nella quale vengono visualizzate le opzioni del parametro.</span><span class="sxs-lookup"><span data-stu-id="af22c-363">The text box that displays the parameter choices does not appear.</span></span>  
  
8.  <span data-ttu-id="af22c-364">Nella barra degli strumenti del Visualizzatore di report, accanto a **Mostra selezioni**, fare clic su `True` .</span><span class="sxs-lookup"><span data-stu-id="af22c-364">In the report viewer toolbar, next to **Show selections**, click `True`.</span></span>  
  
9. <span data-ttu-id="af22c-365">Visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="af22c-365">Preview the report.</span></span>  
  
 <span data-ttu-id="af22c-366">Nella casella di testo nel piè di pagina vengono visualizzati tutti i nomi di punti vendita selezionati.</span><span class="sxs-lookup"><span data-stu-id="af22c-366">The text box in the page footer displays all the store names that you selected.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="af22c-367">9. aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="af22c-367">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="af22c-368">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="af22c-368">To add a report title</span></span>  
  
1.  <span data-ttu-id="af22c-369">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="af22c-369">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="af22c-370">Digitare Vendite prodotto con parametri, quindi fare clic all'esterno della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="af22c-370">Type Parameterized Product Sales, and then click outside the text box.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="af22c-371">10. salvare il report</span><span class="sxs-lookup"><span data-stu-id="af22c-371">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="af22c-372">Per salvare il report in un server di report</span><span class="sxs-lookup"><span data-stu-id="af22c-372">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="af22c-373">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="af22c-373">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="af22c-374">Fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="af22c-374">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="af22c-375">Selezionare o digitare il nome del server di report per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="af22c-375">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="af22c-376">Viene visualizzato il messaggio **Connessione al server di report**.</span><span class="sxs-lookup"><span data-stu-id="af22c-376">The message **Connecting to report server appears**.</span></span> <span data-ttu-id="af22c-377">Al termine della connessione, verrà visualizzato il contenuto della cartella di report specificata dall'amministratore del server di report come posizione predefinita per i report.</span><span class="sxs-lookup"><span data-stu-id="af22c-377">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="af22c-378">In **Nome**sostituire il nome predefinito con Report delle vendite con parametri.</span><span class="sxs-lookup"><span data-stu-id="af22c-378">In **Name**, replace the default name with Parameterized Sales Report.</span></span>  
  
5.  <span data-ttu-id="af22c-379">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="af22c-379">Click **Save**.</span></span>  
  
 <span data-ttu-id="af22c-380">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="af22c-380">The report is saved to the report server.</span></span> <span data-ttu-id="af22c-381">Il server di report al quale si è connessi verrà visualizzato sulla barra di stato nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="af22c-381">The report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="af22c-382">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="af22c-382">Next Steps</span></span>  
 <span data-ttu-id="af22c-383">Questa operazione conclude la procedura dettagliata per l'aggiunta di un parametro al report.</span><span class="sxs-lookup"><span data-stu-id="af22c-383">This concludes the walkthrough for how to add a parameter to your report.</span></span> <span data-ttu-id="af22c-384">Per altre informazioni sui parametri, vedere [Parametri report &#40;Generatore report e Progettazione report&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="af22c-384">To learn more about parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af22c-385">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af22c-385">See Also</span></span>  
 <span data-ttu-id="af22c-386">[Esercitazioni &#40;Generatore report&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="af22c-386">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="af22c-387">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="af22c-387">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
