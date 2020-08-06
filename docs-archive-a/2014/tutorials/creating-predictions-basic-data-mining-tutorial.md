---
title: Creazione di stime (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a8410ed2-bb98-4d51-a9eb-b239be1201c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 456aec6c6b9d0d1a5d0ee1d9949507a37577130c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711204"
---
# <a name="creating-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="0e36d-102">Creazione di stime (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="0e36d-102">Creating Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="0e36d-103">Una volta verificata l'accuratezza dei modelli di data mining e si è deciso di ottenere risultati soddisfacenti, è possibile generare stime utilizzando la Generatore di query di stima nella scheda **Stima modello** di data mining di progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="0e36d-103">After you have tested the accuracy of your mining models and decided that you are satisfied with the results, you can then generate predictions by using the Prediction Query Builder on the **Mining Model Prediction** tab in the Data Mining Designer.</span></span>  
  
 <span data-ttu-id="0e36d-104">Nel generatore delle query di stima sono disponibili tre viste.</span><span class="sxs-lookup"><span data-stu-id="0e36d-104">The Prediction Query Builder has three views.</span></span> <span data-ttu-id="0e36d-105">Con le visualizzazioni **progettazione** e **query** , è possibile compilare ed esaminare la query.</span><span class="sxs-lookup"><span data-stu-id="0e36d-105">With the **Design** and **Query** views, you can build and examine your query.</span></span> <span data-ttu-id="0e36d-106">È quindi possibile eseguire la query e **visualizzare i risultati nella visualizzazione risultati** .</span><span class="sxs-lookup"><span data-stu-id="0e36d-106">You can then run the query and view the results in the **Result** view.</span></span>  
  
 <span data-ttu-id="0e36d-107">Tutte le query di stima utilizzano DMX, ovvero la forma abbreviata per il linguaggio Data Mining Extensions (DMX).</span><span class="sxs-lookup"><span data-stu-id="0e36d-107">All prediction queries use DMX, which is short for the Data Mining Extensions (DMX) language.</span></span> <span data-ttu-id="0e36d-108">La sintassi di DMX è simile a quella di T-SQL e viene utilizzata specificamente per le query sugli oggetti di data mining.</span><span class="sxs-lookup"><span data-stu-id="0e36d-108">DMX has syntax like that of T-SQL but is used for queries against data mining objects.</span></span> <span data-ttu-id="0e36d-109">Sebbene la sintassi DMX non sia complicata, l'utilizzo di un generatore di query come questo o quello nel [SQL Server componenti aggiuntivi Data mining per Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), rende molto più semplice selezionare gli input e le espressioni di compilazione, pertanto è consigliabile apprendere le nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="0e36d-109">Although DMX syntax is not complicated, using a query builder like this one, or the one in the [SQL Server Data Mining Add-Ins for Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), makes it much easier to select inputs and build expressions, so we highly recommend that you learn the basics.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="0e36d-110">Creazione della query</span><span class="sxs-lookup"><span data-stu-id="0e36d-110">Creating the Query</span></span>  
 <span data-ttu-id="0e36d-111">Il primo passaggio per creare una query di stima consiste nel selezionare un modello di data mining e una tabella di input.</span><span class="sxs-lookup"><span data-stu-id="0e36d-111">The first step in creating a prediction query is to select a mining model and input table.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="0e36d-112">Per selezionare un modello e una tabella di input</span><span class="sxs-lookup"><span data-stu-id="0e36d-112">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="0e36d-113">Nella scheda **Stima modello** di data mining di progettazione modelli di data mining fare clic su **Seleziona modello**nella casella **modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="0e36d-113">On the **Mining Model Prediction** tab of Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="0e36d-114">Nella finestra di dialogo **Seleziona modello di data mining** spostarsi nell'albero fino alla struttura **Targeted Mailing** , espandere la struttura, selezionare `TM_Decision_Tree` , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-114">In the **Select Mining Model** dialog box, navigate through the tree to the **Targeted Mailing** structure, expand the structure, select `TM_Decision_Tree`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0e36d-115">Nella casella **Seleziona tabella/** e di input fare clic su **Seleziona tabella del case**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-115">In the **Select Input Table(s)** box, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="0e36d-116">Nella finestra di dialogo **Seleziona tabella** selezionare la vista origine dati nell'elenco **origine dati** [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e36d-116">In the **Select Table** dialog box, in the **Data Source** list, select the data source view [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
5.  <span data-ttu-id="0e36d-117">In **nome tabella/vista**selezionare la tabella **ProspectiveBuyer (dbo)** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-117">In **Table/View Name**, select the **ProspectiveBuyer (dbo)** table, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0e36d-118">La `ProspectiveBuyer` tabella è molto simile alla tabella del case **vTargetMail** .</span><span class="sxs-lookup"><span data-stu-id="0e36d-118">The `ProspectiveBuyer` table most closely resembles the **vTargetMail** case table.</span></span>  
  
## <a name="mapping-the-columns"></a><span data-ttu-id="0e36d-119">Mapping delle colonne</span><span class="sxs-lookup"><span data-stu-id="0e36d-119">Mapping the Columns</span></span>  
 <span data-ttu-id="0e36d-120">Dopo aver selezionato la tabella di input, il generatore delle query di stima crea un mapping predefinito tra il modello di data mining e la tabella di input in base ai nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="0e36d-120">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="0e36d-121">Almeno una colonna della struttura deve corrispondere a una colonna dei dati esterni.</span><span class="sxs-lookup"><span data-stu-id="0e36d-121">At least one column from the structure must match a column in the external data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0e36d-122">I dati utilizzati per determinare l'accuratezza dei modelli devono contenere una colonna della quale è possibile eseguire il mapping alla colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="0e36d-122">The data that you use to determine the accuracy of the models must contain a column that can be mapped to the predictable column.</span></span> <span data-ttu-id="0e36d-123">Se tale colonna non esiste, è possibile crearne una con valori vuoti, ma deve contenere lo stesso tipo di dati della colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="0e36d-123">If such a column does not exist, you can create one with empty values, but it must have the same data type as the predictable column.</span></span>  
  
#### <a name="to-map-the-inputs-to-the-model"></a><span data-ttu-id="0e36d-124">Per eseguire il mapping degli input al modello</span><span class="sxs-lookup"><span data-stu-id="0e36d-124">To map the inputs to the model</span></span>  
  
1.  <span data-ttu-id="0e36d-125">Fare clic con il pulsante destro del mouse sulle linee che connettono la finestra **modello di data mining** alla finestra **Seleziona tabella di input** e scegliere **modifica connessioni**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-125">Right-click the lines connecting the **Mining Model** window to the **Select Input Table** window, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="0e36d-126">Si noti che non su tutte le colonne viene eseguito il mapping.</span><span class="sxs-lookup"><span data-stu-id="0e36d-126">Notice that not every column is mapped.</span></span> <span data-ttu-id="0e36d-127">Si aggiungeranno i mapping per diverse **colonne della tabella**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-127">We will add mappings for several **Table Columns**.</span></span> <span data-ttu-id="0e36d-128">Verrà inoltre generata una nuova colonna per la data di nascita in base alla colonna della data corrente in modo da ottenere una maggiore corrispondenza tra le colonne.</span><span class="sxs-lookup"><span data-stu-id="0e36d-128">We will also generate a new birth date column based on the current date column, so that the columns match better.</span></span>  
  
2.  <span data-ttu-id="0e36d-129">In **colonna tabella**fare clic sulla `Bike Buyer` cella e selezionare ProspectiveBuyer. Unknown nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0e36d-129">Under **Table Column**, click the `Bike Buyer` cell and select ProspectiveBuyer.Unknown from the dropdown.</span></span>  
  
     <span data-ttu-id="0e36d-130">Verrà eseguito il mapping della colonna stimabile [Bike Buyer] a una colonna della tabella di input.</span><span class="sxs-lookup"><span data-stu-id="0e36d-130">This maps the predictable column, [Bike Buyer], to an input table column.</span></span>  
  
3.  <span data-ttu-id="0e36d-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-131">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="0e36d-132">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sulla vista origine dati **mailing** diretto e scegliere **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-132">In **Solution Explorer**, right-click the **Targeted Mailing** data source view and select **View Designer**.</span></span>  
  
5.  <span data-ttu-id="0e36d-133">Fare clic con il pulsante destro del mouse sulla tabella ProspectiveBuyer e scegliere **nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-133">Right-click the table, ProspectiveBuyer, and select **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="0e36d-134">Nella finestra di dialogo **Crea calcolo denominato** Digitare per **nome colonna** `calcAge` .</span><span class="sxs-lookup"><span data-stu-id="0e36d-134">In the **Create Named Calculation** dialog box, for **Column name**, type `calcAge`.</span></span>  
  
7.  <span data-ttu-id="0e36d-135">Per **Descrizione**digitare **Calculate Age in base alla data di nascita**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-135">For **Description**, type **Calculate age based on birthdate**.</span></span>  
  
8.  <span data-ttu-id="0e36d-136">Nella casella **espressione** Digitare, `DATEDIFF(YYYY,[BirthDate],getdate())` quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-136">In the **Expression** box, type `DATEDIFF(YYYY,[BirthDate],getdate())` and then click **OK**.</span></span>  
  
     <span data-ttu-id="0e36d-137">Poiché la tabella di input non dispone di una colonna **Age** corrispondente a quella del modello, è possibile utilizzare questa espressione per calcolare l'età del cliente dalla colonna Data di nascita nella tabella di input.</span><span class="sxs-lookup"><span data-stu-id="0e36d-137">Because the input table has no **Age** column corresponding to the one in the model, you can use this expression to calculate customer age from the BirthDate column in the input table.</span></span> <span data-ttu-id="0e36d-138">Poiché **Age** è stato identificato come la colonna più influente per la stima dell'acquisto di biciclette, deve esistere sia nel modello che nella tabella di input.</span><span class="sxs-lookup"><span data-stu-id="0e36d-138">Since **Age** was identified as the most influential column for predicting bike buying, it must exist in both the model and in the input table.</span></span>  
  
9. <span data-ttu-id="0e36d-139">In Progettazione modelli di data mining selezionare la scheda **Stima modello di data mining** e riaprire la finestra **modifica connessioni** .</span><span class="sxs-lookup"><span data-stu-id="0e36d-139">In Data Mining Designer, select the **Mining Model Prediction** tab and re-open the **Modify Connections** window.</span></span>  
  
10. <span data-ttu-id="0e36d-140">In **colonna tabella**fare clic sulla cella **età** e selezionare ProspectiveBuyer. calci nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0e36d-140">Under **Table Column**, click the **Age** cell and select ProspectiveBuyer.calcAge from the dropdown.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="0e36d-141">Se la colonna non viene visualizzata nell'elenco, potrebbe essere necessario aggiornare la definizione della vista origine dati caricata nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0e36d-141">If you do not see the column in the list, you might have to refresh the definition of the data source view that is loaded in the designer.</span></span> <span data-ttu-id="0e36d-142">A tale scopo, scegliere **Salva tutto**dal menu **file** , quindi chiudere e riaprire il progetto nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0e36d-142">To do this, from the **File** menu, select **Save all**, and then close and re-open the project in the designer.</span></span>  
  
11. <span data-ttu-id="0e36d-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-143">Click **OK**.</span></span>  
  
## <a name="designing-the-prediction-query"></a><span data-ttu-id="0e36d-144">Progettazione della query di stima</span><span class="sxs-lookup"><span data-stu-id="0e36d-144">Designing the Prediction Query</span></span>  
  
1.  <span data-ttu-id="0e36d-145">Il primo pulsante della barra degli strumenti della scheda **Stima modello di data mining** è **passa alla visualizzazione progettazione/passa a visualizzazione risultati/passa al pulsante visualizzazione query** .</span><span class="sxs-lookup"><span data-stu-id="0e36d-145">The first button on the toolbar of the **Mining Model Prediction** tab is the **Switch to design view / Switch to result view / Switch to query view** button.</span></span> <span data-ttu-id="0e36d-146">Fare clic sulla freccia verso il basso in questo pulsante e selezionare **progetta**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-146">Click the down arrow on this button, and select **Design**.</span></span>  
  
2.  <span data-ttu-id="0e36d-147">Nella griglia della scheda **Stima modello di data mining** fare clic sulla cella nella prima riga vuota della colonna **origine** , quindi selezionare **funzione di stima**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-147">In the grid on the **Mining Model Prediction** tab, click the cell in the first empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
3.  <span data-ttu-id="0e36d-148">Nella riga **funzione di stima** fare clic su nella colonna **campo** `PredictProbability` .</span><span class="sxs-lookup"><span data-stu-id="0e36d-148">In the **Prediction Function** row, in the **Field** column, select `PredictProbability`.</span></span>  
  
     <span data-ttu-id="0e36d-149">Nella colonna **alias** della stessa riga digitare **probabilità di risultato**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-149">In the **Alias** column of the same row, type **Probability of result**.</span></span>  
  
4.  <span data-ttu-id="0e36d-150">Dalla finestra **modello di data mining** precedente, selezionare e trascinare [Bike Buyer] nella cella **criteri/argomento** .</span><span class="sxs-lookup"><span data-stu-id="0e36d-150">From the **Mining Model** window above, select and drag [Bike Buyer] into the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="0e36d-151">Quando si lascia andare, [TM_Decision_Tree]. [Bike Buyer] viene visualizzato nella cella **criteri/argomento** .</span><span class="sxs-lookup"><span data-stu-id="0e36d-151">When you let go, [TM_Decision_Tree].[Bike Buyer] appears in the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="0e36d-152">In questo modo viene specificata la colonna di destinazione per la funzione `PredictProbability`.</span><span class="sxs-lookup"><span data-stu-id="0e36d-152">This specifies the target column for the `PredictProbability` function.</span></span> <span data-ttu-id="0e36d-153">Per ulteriori informazioni sulle funzioni, vedere [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="0e36d-153">For more information about functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
5.  <span data-ttu-id="0e36d-154">Fare clic sulla riga vuota successiva nella colonna **origine** , quindi selezionare **TM_Decision_Tree** modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="0e36d-154">Click the next empty row in the **Source** column, and then select **TM_Decision_Tree** mining model.</span></span>  
  
6.  <span data-ttu-id="0e36d-155">Nella `TM_Decision_Tree` riga della colonna **campo** Selezionare `Bike Buyer` .</span><span class="sxs-lookup"><span data-stu-id="0e36d-155">In the `TM_Decision_Tree` row, in the **Field** column, select `Bike Buyer`.</span></span>  
  
7.  <span data-ttu-id="0e36d-156">Nella `TM_Decision_Tree` riga, nella colonna **criteri/argomento** , digitare `=1` .</span><span class="sxs-lookup"><span data-stu-id="0e36d-156">In the `TM_Decision_Tree` row, in the **Criteria/Argument** column, type `=1`.</span></span>  
  
8.  <span data-ttu-id="0e36d-157">Fare clic sulla riga vuota successiva nella colonna **origine** , quindi selezionare la **tabella ProspectiveBuyer**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-157">Click the next empty row in the **Source** column, and then select **ProspectiveBuyer table**.</span></span>  
  
9. <span data-ttu-id="0e36d-158">Nella `ProspectiveBuyer` riga della colonna **campo** Selezionare **ProspectiveBuyerKey**.</span><span class="sxs-lookup"><span data-stu-id="0e36d-158">In the `ProspectiveBuyer` row, in the **Field** column, select **ProspectiveBuyerKey**.</span></span>  
  
     <span data-ttu-id="0e36d-159">Verrà aggiunto un identificatore univoco alla query di stima che consente di identificare la probabilità di acquisto di una bicicletta da parte dei singoli clienti.</span><span class="sxs-lookup"><span data-stu-id="0e36d-159">This adds the unique identifier to the prediction query so that you can identify who is and who is not likely to buy a bicycle.</span></span>  
  
10. <span data-ttu-id="0e36d-160">Aggiungere altre cinque righe alla griglia.</span><span class="sxs-lookup"><span data-stu-id="0e36d-160">Add five more rows to the grid.</span></span> <span data-ttu-id="0e36d-161">Per ogni riga selezionare **ProspectiveBuyer Table** come **origine** , quindi aggiungere le colonne seguenti nelle celle del **campo** :</span><span class="sxs-lookup"><span data-stu-id="0e36d-161">For each row, select **ProspectiveBuyer table** as the **Source** and then add the following columns in the **Field** cells:</span></span>  
  
    -   <span data-ttu-id="0e36d-162">calcAge</span><span class="sxs-lookup"><span data-stu-id="0e36d-162">calcAge</span></span>  
  
    -   <span data-ttu-id="0e36d-163">LastName</span><span class="sxs-lookup"><span data-stu-id="0e36d-163">LastName</span></span>  
  
    -   <span data-ttu-id="0e36d-164">FirstName</span><span class="sxs-lookup"><span data-stu-id="0e36d-164">FirstName</span></span>  
  
    -   <span data-ttu-id="0e36d-165">AddressLine1</span><span class="sxs-lookup"><span data-stu-id="0e36d-165">AddressLine1</span></span>  
  
    -   <span data-ttu-id="0e36d-166">AddressLine2</span><span class="sxs-lookup"><span data-stu-id="0e36d-166">AddressLine2</span></span>  
  
 <span data-ttu-id="0e36d-167">Eseguire infine la query e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0e36d-167">Finally, run the query and browse the results.</span></span>  
  
 <span data-ttu-id="0e36d-168">Il **Generatore di query di stima** include anche i controlli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e36d-168">The **Prediction Query Builder** also includes these controls:</span></span>  
  
-   <span data-ttu-id="0e36d-169">Casella di controllo **Mostra**</span><span class="sxs-lookup"><span data-stu-id="0e36d-169">**Show** check box</span></span>  
  
     <span data-ttu-id="0e36d-170">Consente di rimuovere le clausole dalla query senza doverle eliminare dalla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0e36d-170">Lets you remove clauses from the query without having to delete them from the designer.</span></span> <span data-ttu-id="0e36d-171">Questa operazione può risultare utile quando si utilizzano query complesse e si desidera mantenere la sintassi senza dover copiare e incollare il codice DMX nella finestra.</span><span class="sxs-lookup"><span data-stu-id="0e36d-171">This can be useful when you are working with complex queries and want to preserve syntax without having to copy and paste DMX into the window.</span></span>  
  
-   <span data-ttu-id="0e36d-172">**Gruppo**</span><span class="sxs-lookup"><span data-stu-id="0e36d-172">**Group**</span></span>  
  
     <span data-ttu-id="0e36d-173">Inserisce una parentesi (sinistra) di apertura all'inizio della riga selezionata o inserisce una parentesi (destra) di chiusura alla fine della riga corrente.</span><span class="sxs-lookup"><span data-stu-id="0e36d-173">Inserts an opening (left) parentheses at the beginning of the selected line, or inserts a closing (right) parenthesis at the end of the current line.</span></span>  
  
-   <span data-ttu-id="0e36d-174">**E/O**</span><span class="sxs-lookup"><span data-stu-id="0e36d-174">**AND/OR**</span></span>  
  
     <span data-ttu-id="0e36d-175">Inserisce l'operatore `AND` o l'operatore `OR` immediatamente dopo la funzione o la colonna corrente.</span><span class="sxs-lookup"><span data-stu-id="0e36d-175">Inserts the  `AND` operator or the `OR` operator immediately after the current function or column.</span></span>  
  
#### <a name="to-run-the-query-and-view-results"></a><span data-ttu-id="0e36d-176">Per eseguire la query e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="0e36d-176">To run the query and view results</span></span>  
  
1.  <span data-ttu-id="0e36d-177">Nella scheda **Stima modello di data mining** selezionare il pulsante **risultato** .</span><span class="sxs-lookup"><span data-stu-id="0e36d-177">In the **Mining Model Prediction** tab, select the **Result** button.</span></span>  
  
2.  <span data-ttu-id="0e36d-178">Dopo l'esecuzione della query e la visualizzazione dei risultati, è possibile rivedere i risultati.</span><span class="sxs-lookup"><span data-stu-id="0e36d-178">After the query runs and the results are displayed, you can review the results.</span></span>  
  
     <span data-ttu-id="0e36d-179">Nella scheda **Stima modello di data mining** vengono visualizzate le informazioni di contatto per i potenziali clienti che probabilmente sono acquirenti di biciclette.</span><span class="sxs-lookup"><span data-stu-id="0e36d-179">The **Mining Model Prediction** tab displays contact information for potential customers who are likely to be bike buyers.</span></span> <span data-ttu-id="0e36d-180">La colonna **probabilità della colonna risultati** indica la probabilità che la stima sia corretta.</span><span class="sxs-lookup"><span data-stu-id="0e36d-180">The **Probability of result** column indicates the probability of the prediction being correct.</span></span> <span data-ttu-id="0e36d-181">È possibile utilizzare questi risultati per determinare quali tra i clienti potenziali sono da considerare come potenziali destinatari di messaggi promozionali.</span><span class="sxs-lookup"><span data-stu-id="0e36d-181">You can use these results to determine which potential customers to target for the mailing.</span></span>  
  
3.  <span data-ttu-id="0e36d-182">A questo punto, è possibile salvare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0e36d-182">At this point, you can save the results.</span></span> <span data-ttu-id="0e36d-183">Sono disponibili tre opzioni:</span><span class="sxs-lookup"><span data-stu-id="0e36d-183">You have three options:</span></span>  
  
    -   <span data-ttu-id="0e36d-184">Fare clic con il pulsante destro del mouse su una riga di dati nei risultati e selezionare **copia** per salvare solo quel valore (e l'intestazione di colonna) negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="0e36d-184">Right-click a row of data in the results, and select **Copy** to save just that value (and the column heading) to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="0e36d-185">Fare clic con il pulsante destro del mouse su una riga nei risultati e selezionare **copia tutto** per copiare negli Appunti l'intero set di risultati, incluse le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="0e36d-185">Right-click any row in the results, and select **Copy All** to copy the entire result set, including column headings, to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="0e36d-186">Fare clic su **Salva risultati query** per salvare i risultati direttamente in un database, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0e36d-186">Click **Save query result** to save the results directly to a database as follows:</span></span>  
  
        1.  <span data-ttu-id="0e36d-187">Nella finestra di dialogo **Salva risultati query di data mining** selezionare un'origine dati o definire una nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e36d-187">In the **Save Data Mining Query Result** dialog box, select a data source, or define a new data source.</span></span>  
  
        2.  <span data-ttu-id="0e36d-188">Digitare un nome per la tabella in cui saranno contenuti i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="0e36d-188">Type a name for the table that will contain the query results.</span></span>  
  
        3.  <span data-ttu-id="0e36d-189">Utilizzare l'opzione **Aggiungi a DSV**per creare la tabella e aggiungerla a una vista origine dati esistente.</span><span class="sxs-lookup"><span data-stu-id="0e36d-189">Use the option, **Add to DSV**, to create the table and add it to an existing data source view.</span></span> <span data-ttu-id="0e36d-190">Questa opzione è utile se si desidera utilizzare tutte le tabelle correlate per un modello, ad esempio i dati di training, i dati di origine della stima e i risultati della query, nella stessa vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="0e36d-190">This is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source view.</span></span>  
  
        4.  <span data-ttu-id="0e36d-191">Utilizzare l'opzione, **Sovrascrivi se esistente**, per aggiornare una tabella esistente con i risultati più recenti.</span><span class="sxs-lookup"><span data-stu-id="0e36d-191">Use the option, **Overwrite if exists**, to update an existing table with the latest results.</span></span>  
  
             <span data-ttu-id="0e36d-192">È necessario utilizzare l'opzione per sovrascrivere la tabella se sono state aggiunte tutte le colonne alla query di stima, modificati i nomi o i tipi di dati di tutte le colonne nella query di stima o se sono state eseguite tutte le istruzioni ALTER sulla tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0e36d-192">You must use the option to overwrite the table if you have added any columns to the prediction query, changed the names or data types of any columns in the prediction query, or if you have run any ALTER statements on the destination table.</span></span>  
  
             <span data-ttu-id="0e36d-193">Inoltre, se più colonne hanno lo stesso nome (ad esempio, l' **espressione**del nome di colonna predefinito), è necessario creare un alias per le colonne con nomi duplicati. in caso di errore, verrà generato un errore quando la finestra di progettazione tenterà di salvare i risultati in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e36d-193">Also, if multiple columns have the same name (for example, the default column name **Expression**) you must create an alias for the columns with duplicate names, or an error will be raised when the designer tries to save the results to SQL Server.</span></span> <span data-ttu-id="0e36d-194">Il motivo è che SQL Server non consente più colonne con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="0e36d-194">The reason is that SQL Server does not allow multiple columns to have the same name.</span></span>  
  
             <span data-ttu-id="0e36d-195">Per ulteriori informazioni, vedere la [finestra di dialogo Salva risultati query di Data Mining &#40;visualizzazione Stima modello di data mining&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span><span class="sxs-lookup"><span data-stu-id="0e36d-195">For more information, see [Save Data Mining Query Result Dialog Box &#40;Mining Model Prediction View&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0e36d-196">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="0e36d-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0e36d-197">Utilizzo del drill-through sui dati della struttura &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="0e36d-197">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e36d-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e36d-198">See Also</span></span>  
 [<span data-ttu-id="0e36d-199">Creare una query di stima utilizzando Generatore query di stima</span><span class="sxs-lookup"><span data-stu-id="0e36d-199">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
