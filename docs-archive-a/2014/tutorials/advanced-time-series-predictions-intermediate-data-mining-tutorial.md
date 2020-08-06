---
title: Stime avanzate basate su serie temporali (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b614ebdb-07ca-44af-a0ff-893364bd4b71
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 70ebf856ba0782cbf44969aba30602818015582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720538"
---
# <a name="advanced-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="f8051-102">Stime avanzate basate su serie temporali (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="f8051-102">Advanced Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="f8051-103">Dall'esplorazione del modello di previsione è emerso che, benché le vendite nella maggior parte delle aree geografiche seguano uno schema analogo, alcune aree e alcuni modelli, ad esempio il modello M200 nell'area del Pacifico, mostrano tendenze molto diverse.</span><span class="sxs-lookup"><span data-stu-id="f8051-103">You saw from exploring the forecasting model that although sales in most of the regions follow a similar pattern, some regions and some models, such as the M200 model in the Pacific region, exhibit very different trends.</span></span> <span data-ttu-id="f8051-104">Questo risultato non è sorprendente, in quanto è noto che differenze tra le diverse aree sono comuni e possono essere causate da numerosi fattori, tra cui promozioni marketing, produzione di report imprecisi o eventi geopolitici.</span><span class="sxs-lookup"><span data-stu-id="f8051-104">This does not surprise you, as you know that differences among regions are common and can be caused by many factors, including marketing promotions, inaccurate reporting, or geopolitical events.</span></span>  
  
 <span data-ttu-id="f8051-105">Gli utenti richiedono tuttavia un modello che possa essere applicato a livello mondiale.</span><span class="sxs-lookup"><span data-stu-id="f8051-105">However, your users are asking for a model that can be applied worldwide.</span></span> <span data-ttu-id="f8051-106">Per ridurre quindi l'influenza di questi singoli fattori sulle proiezioni, si decide di compilare un modello basato su misure aggregate di vendite mondiali.</span><span class="sxs-lookup"><span data-stu-id="f8051-106">Therefore, to minimize the effect of individual factors on projections, you decide to build a model that is based on aggregated measures of worldwide sales.</span></span> <span data-ttu-id="f8051-107">Sarà quindi possibile utilizzare questo modello per eseguire stime per le singole aree.</span><span class="sxs-lookup"><span data-stu-id="f8051-107">You can then use this model to make predictions for each individual region.</span></span>  
  
 <span data-ttu-id="f8051-108">In questa attività si compileranno tutte le origini dati necessarie per eseguire le attività di stima avanzate.</span><span class="sxs-lookup"><span data-stu-id="f8051-108">In this task, you will build all the data sources that you need to perform the advanced prediction tasks.</span></span> <span data-ttu-id="f8051-109">Verranno create due viste origine dati da utilizzare come input per la query di stima e una vista origine dati da utilizzare per la compilazione del nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="f8051-109">You will create two data source views for use as inputs to the prediction query, and one data source view to use in building a new model.</span></span>  
  
 <span data-ttu-id="f8051-110">**Passaggi**</span><span class="sxs-lookup"><span data-stu-id="f8051-110">**Steps**</span></span>  
  
1.  [<span data-ttu-id="f8051-111">Preparare i dati di vendita estesi (per la stima)</span><span class="sxs-lookup"><span data-stu-id="f8051-111">Prepare the extended sales data (for prediction)</span></span>](#bkmk_newExtendData)  
  
2.  [<span data-ttu-id="f8051-112">Preparare i dati aggregati (per la compilazione del modello)</span><span class="sxs-lookup"><span data-stu-id="f8051-112">Prepare the aggregated data (for building the model)</span></span>](#bkmk_newReplaceData)  
  
3.  [<span data-ttu-id="f8051-113">Preparare i dati della serie (per la stima incrociata)</span><span class="sxs-lookup"><span data-stu-id="f8051-113">Prepare the series data (for cross-prediction)</span></span>](#bkmk_CrossData2)  
  
4.  [<span data-ttu-id="f8051-114">Eseguire la stima utilizzando EXTEND</span><span class="sxs-lookup"><span data-stu-id="f8051-114">Predict using EXTEND</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
5.  [<span data-ttu-id="f8051-115">Creare il modello di stima incrociata</span><span class="sxs-lookup"><span data-stu-id="f8051-115">Create the cross-prediction model</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
6.  [<span data-ttu-id="f8051-116">Eseguire la stima utilizzando REPLACE</span><span class="sxs-lookup"><span data-stu-id="f8051-116">Predict using REPLACE</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
7.  [<span data-ttu-id="f8051-117">Rivedere le nuove stime</span><span class="sxs-lookup"><span data-stu-id="f8051-117">Review the new predictions</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
##  <a name="creating-the-new-extended-sales-data"></a><a name="bkmk_newExtendData"></a><span data-ttu-id="f8051-118">Creazione dei nuovi dati di vendita estesi</span><span class="sxs-lookup"><span data-stu-id="f8051-118">Creating the New Extended Sales Data</span></span>  
 <span data-ttu-id="f8051-119">Per aggiornare i dati di vendita, sarà necessario ottenere le cifre di vendita più recenti.</span><span class="sxs-lookup"><span data-stu-id="f8051-119">To update your sales data, you will need to get the latest sales figures.</span></span> <span data-ttu-id="f8051-120">Sono di particolare interesse solo i dati dalla regione del Pacifico, dove è stata avviata una promozione di vendite regionali per richiamare l'attenzione sui nuovi punti vendita e generare consapevolezza dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="f8051-120">Of particular interest are the data just in from the Pacific region, which launched a regional sales promotion to call attention to the new stores and raise awareness of their products.</span></span>  
  
 <span data-ttu-id="f8051-121">Per questo scenario si presuppone che i dati siano stati importati da una cartella di lavoro di Excel che contiene solo tre mesi di nuovi dati per un paio di aree.</span><span class="sxs-lookup"><span data-stu-id="f8051-121">For this scenario, we'll assume that the data has been imported from an Excel workbook that contains just three months of new data for a couple of regions.</span></span> <span data-ttu-id="f8051-122">Si creerà una tabella per i dati utilizzando uno script Transact-SQL e quindi si definirà una vista origine dati da utilizzare per la stima.</span><span class="sxs-lookup"><span data-stu-id="f8051-122">You'll create a table for the data using a Transact-SQL script, and then define a data source view to use for prediction.</span></span>  
  
#### <a name="create-the-table-with-new-sales-data"></a><span data-ttu-id="f8051-123">Creare la tabella con i nuovi dati di vendita</span><span class="sxs-lookup"><span data-stu-id="f8051-123">Create the table with new sales data</span></span>  
  
1.  <span data-ttu-id="f8051-124">In una finestra di query Transact-SQL eseguire l'istruzione seguente per aggiungere i dati di vendita al database AdventureWorksDW o a qualsiasi altro database.</span><span class="sxs-lookup"><span data-stu-id="f8051-124">In a Transact-SQL query window, execute the following statement to add the sales data to the AdventureWorksDW database (or any other database).</span></span>  
  
    ```  
    USE [database name];  
    GO  
    IF OBJECT_ID ([dbo].[NewSalesData]) IS NOT NULL   
        DROP TABLE [dbo].[NewSalesData];  
    GO  
    CREATE TABLE [dbo].[NewSalesData]([Series] [nvarchar](255) NULL,  
    [NewDate] [datetime] NULL,  
    [NewQty] [float] NULL,  
    [NewAmount] [money] NULL) ON [PRIMARY]  
  
    GO  
    ```  
  
2.  <span data-ttu-id="f8051-125">Inserire i nuovi valori utilizzando lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="f8051-125">Insert the new values using the following script.</span></span>  
  
    ```  
    INSERT INTO [NewSalesData]  
    (Series,NewDate,NewQty,NewAmount)  
    VALUES('T1000 Pacific', '7/25/08', 55, '$130,170.22'),  
    ('T1000 Pacific', '8/25/08', 50, '$114,435.36 '),  
    ('T1000 Pacific', '9/25/08', 50, '$117,296.24 '),  
    ('T1000 Europe', '7/25/08', 37, '$88,210.00 '),  
    ('T1000 Europe', '8/25/08', 41, '$97,746.00 '),  
    ('T1000 Europe', '9/25/08', 37, '$88,210.00 '),  
    ('T1000 North America', '7/25/08', 69, '$164,500.00 '),  
    ('T1000 North America', '8/25/08', 66, '$157,348.00 '),  
    ('T1000 North America', '9/25/08', 58, '$138,276.00 '),  
    ('M200 Pacific', '7/25/08', 65, '$149,824.35'),  
    ('M200 Pacific', '8/25/08', 54,  '$124,619.46'),  
    ('M200 Pacific', '9/25/08', 61, '$141,143.39'),  
    ('M200 Europe', '7/25/08', 75, '$173,026.00'),  
    ('M200 Europe', '8/25/08', 76, '$175,212.00'),  
    ('M200 Europe', '9/25/08', 84, '$193,731.00'),  
    ('M200 North America', '7/25/08', 94, '$216,916.00'),  
    ('M200 North America', '8/25/08', 94, '$216,891.00'),  
    ('M200 North America', '9/25/08', 91,'$209,943.00');  
    ```  
  
    > [!WARNING]  
    >  <span data-ttu-id="f8051-126">Le virgolette vengono utilizzate con i valori di valuta per evitare problemi con il separatore virgola e il simbolo di valuta.</span><span class="sxs-lookup"><span data-stu-id="f8051-126">The quotation marks are used with the currency values to prevent problems with the comma separator and the currency symbol.</span></span> <span data-ttu-id="f8051-127">È inoltre possibile passare i valori della valuta in questo formato: `130170.22`</span><span class="sxs-lookup"><span data-stu-id="f8051-127">You could also pass in the currency values in this format: `130170.22`</span></span>  
    >   
    >  <span data-ttu-id="f8051-128">Si noti che le date utilizzate nel database di esempio sono state modificate per questa versione.</span><span class="sxs-lookup"><span data-stu-id="f8051-128">Note that the dates used in the sample database have changed for this release.</span></span> <span data-ttu-id="f8051-129">Se si utilizza una versione di AdventureWorks precedente, potrebbe essere necessario modificare le date inserite in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="f8051-129">If you are using an earlier edition of AdventureWorks, you might need to adjust the inserted dates accordingly.</span></span>  
  
###  <a name="create-a-data-source-view-using-the-new-sales-data"></a><a name="bkmk_newReplaceData"></a><span data-ttu-id="f8051-130">Creare una vista origine dati utilizzando i nuovi dati di vendita</span><span class="sxs-lookup"><span data-stu-id="f8051-130">Create a data source view using the new sales data</span></span>  
  
1.  <span data-ttu-id="f8051-131">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **viste origine dati**, quindi scegliere **nuova vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="f8051-131">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="f8051-132">Nella Creazione guidata vista origine dati effettuare le selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8051-132">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="f8051-133">**Origine dati**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8051-133">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="f8051-134">**Selezione tabelle e viste**: selezionare la tabella appena creata, NewSalesData.</span><span class="sxs-lookup"><span data-stu-id="f8051-134">**Select Tables and Views**: Select the table that you just created, NewSalesData.</span></span>  
  
3.  <span data-ttu-id="f8051-135">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f8051-135">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="f8051-136">Nell'area di progettazione della vista origine dati fare clic con il pulsante destro del mouse su NewSalesData, quindi scegliere **Esplora dati** per verificare i dati.</span><span class="sxs-lookup"><span data-stu-id="f8051-136">In the Data Source View design surface, right-click NewSalesData, and then select **Explore Data** to verify the data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="f8051-137">Si utilizzeranno solo questi dati per la stima, pertanto non si importa se i dati sono incompleti.</span><span class="sxs-lookup"><span data-stu-id="f8051-137">You will use this data for prediction only, so it does not matter that the data is incomplete.</span></span>  
  
##  <a name="creating-the-data-for-the-cross-prediction-model"></a><a name="bkmk_CrossData2"></a><span data-ttu-id="f8051-138">Creazione dei dati per il modello di stima incrociata</span><span class="sxs-lookup"><span data-stu-id="f8051-138">Creating the Data for the Cross-Prediction Model</span></span>  
 <span data-ttu-id="f8051-139">I dati utilizzati nel modello di previsione originale sono già raggruppati approssimativamente dalla vista vTimeSeries in cui diversi modelli di bicicletta sono stati compressi in un numero di categorie inferiore e i risultati di singoli paesi sono stati uniti in aree.</span><span class="sxs-lookup"><span data-stu-id="f8051-139">The data that was used in the original forecasting model was already grouped somewhat by the view vTimeSeries, which collapsed several bike models into a smaller number of categories, and merged results from individual countries into regions.</span></span> <span data-ttu-id="f8051-140">Per creare un modello che possa essere utilizzato per le proiezioni mondiali, si creeranno direttamente alcune semplici aggregazioni aggiuntive nella finestra di progettazione Vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="f8051-140">To create a model that can be used for world-wide projections, you will create some additional simple aggregations directly in the Data Source View Designer.</span></span> <span data-ttu-id="f8051-141">La nuova vista origine dati contiene solo una somma e una media delle vendite di tutti i prodotti per tutte le aree.</span><span class="sxs-lookup"><span data-stu-id="f8051-141">The new data source view will contain just a sum and an average of the sales of all products for all regions.</span></span>  
  
 <span data-ttu-id="f8051-142">Dopo avere creato l'origine dati per il modello, è necessario creare una nuova vista origine dati da utilizzare per la stima.</span><span class="sxs-lookup"><span data-stu-id="f8051-142">After you have created the data source used for the model, you must create a new data source view to use for prediction.</span></span> <span data-ttu-id="f8051-143">Se si desidera ad esempio stimare le vendite per l'Europa utilizzando il nuovo modello mondiale, è necessario inserire i dati solo per l'area Europa.</span><span class="sxs-lookup"><span data-stu-id="f8051-143">For example, if you want to predict sales for Europe using the new worldwide model, you must feed in data for the Europe region only.</span></span> <span data-ttu-id="f8051-144">Si configurerà quindi una nuova vista origine dati che filtra i dati originali e si modificherà la condizione di filtro per ogni set di query di stima.</span><span class="sxs-lookup"><span data-stu-id="f8051-144">So you will set up a new data source view that filters the original data, and change the filter condition for each set of prediction queries.</span></span>  
  
#### <a name="to-create-the-model-data-using-a-custom-data-source-view"></a><span data-ttu-id="f8051-145">Per creare i dati del modello utilizzando una vista origine dati personalizzata</span><span class="sxs-lookup"><span data-stu-id="f8051-145">To create the model data using a custom data source view</span></span>  
  
1.  <span data-ttu-id="f8051-146">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **viste origine dati**, quindi scegliere **nuova vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="f8051-146">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="f8051-147">Nella pagina di benvenuto della procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8051-147">On the welcome page of the wizard, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f8051-148">Nella pagina **Selezionare un'origine dati** selezionare [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)], quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8051-148">On the **Select Data Source** page, select [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f8051-149">Nella pagina **selezionare tabelle e viste**, non aggiungere alcuna tabella. fare semplicemente clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f8051-149">In the page, **Select Tables and Views**, do not add any tables-just click **Next**.</span></span>  
  
5.  <span data-ttu-id="f8051-150">Nella pagina **Completamento procedura guidata**Digitare il nome `AllRegions` e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="f8051-150">On the page, **Completing the Wizard**, type the name `AllRegions`, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="f8051-151">Fare quindi clic con il pulsante destro del mouse sull'area di progettazione della vista origine dati vuota, quindi scegliere **nuova query denominata**.</span><span class="sxs-lookup"><span data-stu-id="f8051-151">Next, right-click the blank data source view design surface, and then select **New Named Query**.</span></span>  
  
7.  <span data-ttu-id="f8051-152">Nella finestra di dialogo **Crea query denominata** , per **nome**, digitare `AllRegions` e per **Descrizione**digitare **somma e media delle vendite per tutti i modelli e le aree**.</span><span class="sxs-lookup"><span data-stu-id="f8051-152">In the **Create Named Query** dialog box, for **Name**, type `AllRegions`, and for **Description**, type **Sum and average of sales for all models and regions**.</span></span>  
  
8.  <span data-ttu-id="f8051-153">Nel riquadro Testo SQL digitare l'istruzione seguente, quindi scegliere OK:</span><span class="sxs-lookup"><span data-stu-id="f8051-153">In the SQL text pane, type the following statement and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate,   
    SUM([Quantity]) as SumQty, AVG([Quantity]) as AvgQty,  
    SUM([Amount]) AS SumAmt, AVG([Amount]) AS AvgAmt,  
    'All Regions' as [Region]  
    FROM dbo.vTimeSeries   
    GROUP BY ReportingDate  
    ```  
  
9. <span data-ttu-id="f8051-154">Fare clic con il pulsante destro del mouse sulla `AllRegions` tabella, quindi scegliere **Esplora dati**.</span><span class="sxs-lookup"><span data-stu-id="f8051-154">Right-click the `AllRegions` table, and then select **Explore Data**.</span></span>  
  
###  <a name="to-create-the-series-data-for-cross-prediction"></a><a name="bkmk_CrossData"></a><span data-ttu-id="f8051-155">Per creare i dati della serie per la stima incrociata</span><span class="sxs-lookup"><span data-stu-id="f8051-155">To create the series data for cross-prediction</span></span>  
  
1.  <span data-ttu-id="f8051-156">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **viste origine dati**, quindi scegliere **nuova vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="f8051-156">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="f8051-157">Nella Creazione guidata vista origine dati effettuare le selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8051-157">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="f8051-158">**Origine dati**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8051-158">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="f8051-159">**Selezione tabelle e viste**: non selezionare alcuna tabella</span><span class="sxs-lookup"><span data-stu-id="f8051-159">**Select Tables and Views**: Do not select any tables</span></span>  
  
     <span data-ttu-id="f8051-160">**Nome**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="f8051-160">**Name**: `T1000 Pacific Region`</span></span>  
  
3.  <span data-ttu-id="f8051-161">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f8051-161">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="f8051-162">Fare clic con il pulsante destro del mouse sull'area di progettazione vuota per **T1000 Pacific Region. DSV**, quindi scegliere **nuova query denominata**.</span><span class="sxs-lookup"><span data-stu-id="f8051-162">Right-click the empty design surface for **T1000 Pacific Region.dsv**, and then select **New Named Query**.</span></span>  
  
     <span data-ttu-id="f8051-163">Verrà visualizzata la finestra di dialogo **Crea query denominata** .</span><span class="sxs-lookup"><span data-stu-id="f8051-163">The **Create Named Query** dialog box appears.</span></span> <span data-ttu-id="f8051-164">Digitare nuovamente il nome e aggiungere la descrizione seguente:</span><span class="sxs-lookup"><span data-stu-id="f8051-164">Retype the name, and then add the following description:</span></span>  
  
     <span data-ttu-id="f8051-165">**Nome**: `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="f8051-165">**Name**: `T1000 Pacific Region`</span></span>  
  
     <span data-ttu-id="f8051-166">**Descrizione**: **filtrare `vTimeSeries` per area e modello**</span><span class="sxs-lookup"><span data-stu-id="f8051-166">**Description**: **Filter`vTimeSeries`by region and model**</span></span>  
  
5.  <span data-ttu-id="f8051-167">Nel riquadro Testo digitare la query seguente, quindi scegliere OK:</span><span class="sxs-lookup"><span data-stu-id="f8051-167">In the text pane, type the following query, and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate, ModelRegion, Quantity, Amount  
    FROM dbo.vTimeSeries  
    WHERE (ModelRegion = N'T1000 Pacific')  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8051-168">Poiché è necessario creare stime separatamente per ogni serie, è possibile copiare il testo della query e salvarlo in un file di testo, in modo da poterlo riutilizzare per l'altra serie di dati.</span><span class="sxs-lookup"><span data-stu-id="f8051-168">Since you will need to create predictions for each series separately, you might want to copy the query text and save it to a text file so that you can re-use it for the other data series.</span></span>  
  
6.  <span data-ttu-id="f8051-169">Nell'area di progettazione della vista origine dati fare clic con il pulsante destro del mouse su T1000 Pacific, quindi scegliere **Esplora dati** per verificare che i dati vengano filtrati correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8051-169">In the Data Source View design surface, right-click T1000 Pacific, and then select **Explore Data** to verify that the data is filtered correctly.</span></span>  
  
     <span data-ttu-id="f8051-170">Si utilizzeranno questi dati come input del modello in caso di creazione di query di stima incrociata.</span><span class="sxs-lookup"><span data-stu-id="f8051-170">You will use this data as the input to the model when creating cross-prediction queries.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f8051-171">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="f8051-171">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f8051-172">Stime basate su serie temporali che utilizzano dati aggiornati &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f8051-172">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="f8051-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8051-173">See Also</span></span>  
 <span data-ttu-id="f8051-174">[Algoritmo Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="f8051-174">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 <span data-ttu-id="f8051-175">[Riferimento tecnico per l'algoritmo Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f8051-175">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="f8051-176">Viste origine dati in modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="f8051-176">Data Source Views in Multidimensional Models</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models)  
  
  
