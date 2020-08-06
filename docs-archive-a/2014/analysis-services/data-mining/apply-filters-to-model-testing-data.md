---
title: Applicare filtri ai dati di test del modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input row filtering [SQL Server]
- filtering input rows [Analysis Services]
- Mining Accuracy Chart [Analysis Services], filtering input rows
ms.assetid: 9ccc9a23-5597-4b35-a05f-2fc8eb885147
author: minewiskan
ms.author: owend
ms.openlocfilehash: d1fd2b643ae4f7d831cab980ca45b7d43d8b58f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624437"
---
# <a name="apply-filters-to-model-testing-data"></a><span data-ttu-id="296d7-102">Applicare filtri ai dati di test del modello</span><span class="sxs-lookup"><span data-stu-id="296d7-102">Apply Filters to Model Testing Data</span></span>
  <span data-ttu-id="296d7-103">Quando si specifica un'origine dati esterna da usare per il test di un modello, è possibile applicare un filtro per limitare i dati di input.</span><span class="sxs-lookup"><span data-stu-id="296d7-103">When you specify an external data source to use in testing a model, you can optionally apply a filter to restrict the input data.</span></span> <span data-ttu-id="296d7-104">È ad esempio possibile testare il modello in modo specifico per le stime sui clienti in una determinata fascia di reddito.</span><span class="sxs-lookup"><span data-stu-id="296d7-104">For example, you might want to test the model specifically for predictions on customers in a certain income range.</span></span>  
  
 <span data-ttu-id="296d7-105">In uno scenario di mailing diretto di AdventureWorks, ad esempio, è possibile creare un'espressione di filtro come la seguente in ProspectiveBuyer, ovvero la tabella che contiene i dati di test, e limitare i test case in base alla fascia di reddito:</span><span class="sxs-lookup"><span data-stu-id="296d7-105">For example, in the AdventureWorks targeted mailing scenario, you can create a filter expression like the following one on ProspectiveBuyer, which is the table that contains the testing data, and restrict testing cases by income range:</span></span>  
  
 `[YearlyIncome] = '50000'`  
  
 <span data-ttu-id="296d7-106">Il comportamento dei filtri cambia a seconda che i filtri vengano applicati ai dati di training del modello o al set di dati di test:</span><span class="sxs-lookup"><span data-stu-id="296d7-106">The behavior of filters is slightly different, depending on whether you are filtering model training data or a testing data set:</span></span>  
  
-   <span data-ttu-id="296d7-107">Quando si definisce un filtro su un set di dati di test, si crea una clausola WHERE sui dati in ingresso.</span><span class="sxs-lookup"><span data-stu-id="296d7-107">When you define a filter on a testing data set, you create a WHERE clause on the incoming data.</span></span> <span data-ttu-id="296d7-108">Se si applica un filtro su un set di dati di input utilizzato per la valutazione di un modello, l'espressione di filtro viene convertita in un'istruzione Transact-SQL e applicata alla tabella di input durante la creazione del grafico.</span><span class="sxs-lookup"><span data-stu-id="296d7-108">If you are filtering an input data set used for evaluating a model, the filter expression is translated to a Transact-SQL statement and applied to the input table when the chart is created.</span></span> <span data-ttu-id="296d7-109">Di conseguenza, il numero di test case può essere sostanzialmente ridotto.</span><span class="sxs-lookup"><span data-stu-id="296d7-109">As a result, the number of test cases can be greatly reduced.</span></span>  
  
-   <span data-ttu-id="296d7-110">Quando si applica un filtro su un modello di data mining, l'espressione di filtro creata viene convertita in un'istruzione DMX (Data Mining Extensions) e applicata al singolo modello.</span><span class="sxs-lookup"><span data-stu-id="296d7-110">When you apply a filter to a mining model, the filter expression that you create is translated to a Data Mining Extensions (DMX) statement, and applied to the individual model.</span></span> <span data-ttu-id="296d7-111">Di conseguenza, quando si applica un filtro a un modello, solo un subset dei dati originali viene utilizzato per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="296d7-111">Therefore, when you apply a filter to a model, only a subset of the original data is used to train the model.</span></span> <span data-ttu-id="296d7-112">Questo può essere causa di problemi se il modello di training viene filtrato con un set di criteri in modo che il modello venga ottimizzato in base a un determinato set di dati, e quindi testato con un altro set di criteri.</span><span class="sxs-lookup"><span data-stu-id="296d7-112">This can cause problems if you filter the training model with one set of criteria, so that the model is tuned to a certain set of data, and then test the model with another set of criteria.</span></span>  
  
-   <span data-ttu-id="296d7-113">Se durante la creazione della struttura è stato definito un set di dati di test, i case del modello usati per il training includono solo quelli presenti nel set di training della struttura di data mining **e** che soddisfano le condizioni del filtro.</span><span class="sxs-lookup"><span data-stu-id="296d7-113">If you defined a testing data set when you created the structure, the model cases used for training include only those cases that are in the mining structure training set **and** which meet the conditions of the filter.</span></span> <span data-ttu-id="296d7-114">Pertanto, quando si testa un modello e si seleziona l'opzione **Usa test case del modello di data mining**i test case includono solo i case presenti nel set di test della struttura di data mining che soddisfano le condizioni del filtro.</span><span class="sxs-lookup"><span data-stu-id="296d7-114">Thus, when you are testing a model and select the option **Use mining model test cases**, the testing cases will include only the cases that are in the mining structure test set and which meet the conditions of the filter.</span></span> <span data-ttu-id="296d7-115">Se, tuttavia, non è stato definito un set di dati di controllo, i case del modello utilizzati per il test includono tutti i case presenti nel set di dati che soddisfano le condizioni del filtro.</span><span class="sxs-lookup"><span data-stu-id="296d7-115">However, if you did not define a holdout data set, the model cases used for testing include all the cases in the data set that meet the filter conditions</span></span>  
  
-   <span data-ttu-id="296d7-116">Le condizioni del filtro che si applicano a un modello influiscono anche sulle query drill-through sui case del modello.</span><span class="sxs-lookup"><span data-stu-id="296d7-116">Filter conditions that you apply on a model also affect drillthrough queries on the model cases.</span></span>  
  
 <span data-ttu-id="296d7-117">In breve, quando si testano più modelli, anche se tutti i modelli sono basati sulla stessa struttura di data mining, è necessario tenere presente che i modelli utilizzano potenzialmente subset diversi di dati per il training e il test.</span><span class="sxs-lookup"><span data-stu-id="296d7-117">In summary, when you test multiple models, even if all the models are based on the same mining structure, you must be aware that the models potentially use different subsets of data for training and testing.</span></span> <span data-ttu-id="296d7-118">Questo può produrre gli effetti seguenti sui grafici di accuratezza:</span><span class="sxs-lookup"><span data-stu-id="296d7-118">This can have the following effects on accuracy charts:</span></span>  
  
-   <span data-ttu-id="296d7-119">Il numero totale di casi nei set di test può variare tra i modelli testati.</span><span class="sxs-lookup"><span data-stu-id="296d7-119">The total number of cases in the testing sets can vary among the models being tested.</span></span>  
  
-   <span data-ttu-id="296d7-120">Le percentuali per ogni modello potrebbero non allinearsi nel grafico se i modelli utilizzano subset diversi di dati di training o dati di test.</span><span class="sxs-lookup"><span data-stu-id="296d7-120">The percentages for each model may not align in the chart, if the models use different subsets of training data or testing data.</span></span>  
  
 <span data-ttu-id="296d7-121">Per determinare se un modello contiene un filtro predefinito che potrebbe influire sui risultati, è possibile cercare la proprietà **Filtro** nel riquadro **Proprietà** oppure eseguire una query sul modello tramite i set di righe dello schema di data mining.</span><span class="sxs-lookup"><span data-stu-id="296d7-121">To determine whether a model contains a predefined filter that might affect results, you can look for the **Filter** property in the **Property** pane, or you can query the model by using the data mining schema rowsets.</span></span> <span data-ttu-id="296d7-122">La query seguente, ad esempio, restituisce il testo del filtro per il modello specificato:</span><span class="sxs-lookup"><span data-stu-id="296d7-122">For example, the following query returns the filter text for the specified model:</span></span>  
  
 `SELECT [FILTER] FROM $system.DMSCHEMA_MINING_MODELS WHERE MODEL_NAME = 'name of model'`  
  
> [!WARNING]  
>  <span data-ttu-id="296d7-123">Se si desidera rimuovere il filtro da un modello di data mining esistente o modificare le condizioni del filtro, è necessario rielaborare il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="296d7-123">If you want to remove the filter from an existing mining model, or change the filter conditions, you must reprocess the mining model.</span></span>  
  
 <span data-ttu-id="296d7-124">Per altre informazioni sui tipi di filtri che è possibile applicare e sulle modalità di valutazione delle espressioni di filtro, vedere [Sintassi ed esempi di filtri dei modelli &#40;Analysis Services – Data mining&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="296d7-124">For more information about the kinds of filters you can apply, and how filter expressions are evaluated, see [Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span></span>  
  
### <a name="create-a-filter-on-external-testing-data"></a><span data-ttu-id="296d7-125">Creare un filtro sui dati di test esterni</span><span class="sxs-lookup"><span data-stu-id="296d7-125">Create a filter on external testing data</span></span>  
  
1.  <span data-ttu-id="296d7-126">Fare doppio clic sulla struttura di data mining che contiene il modello che si desidera testare per aprire Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="296d7-126">Double-click the mining structure that contains the model you want to test, to open Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="296d7-127">Selezionare la scheda **Grafico di accuratezza modello di data mining** , quindi selezionare la scheda **Selezione input** .</span><span class="sxs-lookup"><span data-stu-id="296d7-127">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="296d7-128">Nell'area **Seleziona set di dati da usare per il grafico di accuratezza** della scheda **Selezione input**selezionare l'opzione **Specifica un set di dati diverso**.</span><span class="sxs-lookup"><span data-stu-id="296d7-128">On the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="296d7-129">Fare clic sul pulsante Sfoglia **(...)** per aprire una finestra di dialogo e scegliere il set di dati esterno.</span><span class="sxs-lookup"><span data-stu-id="296d7-129">Click the browse button **(...)** to open a dialog box and choose the external data set.</span></span>  
  
5.  <span data-ttu-id="296d7-130">Scegliere la tabella del case e aggiungere, se necessario, una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="296d7-130">Choose the case table, and add a nested table if necessary.</span></span> <span data-ttu-id="296d7-131">Se necessario, eseguire il mapping delle colonne del modello alle colonne del set di dati esterno.</span><span class="sxs-lookup"><span data-stu-id="296d7-131">Map columns in the model to columns in the external data set as necessary.</span></span> <span data-ttu-id="296d7-132">Chiudere la finestra di dialogo **Specifica mapping colonne** per salvare la definizione della tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="296d7-132">Close the **Specify Column Mapping** dialog box to save the source table definition.</span></span>  
  
6.  <span data-ttu-id="296d7-133">Fare clic su **Apri editor filtri** per definire un filtro per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="296d7-133">Click **Open Filter Editor** to define a filter for the data set.</span></span>  
  
     <span data-ttu-id="296d7-134">Verrà visualizzata la finestra di dialogo **Filtro dei set di dati** .</span><span class="sxs-lookup"><span data-stu-id="296d7-134">The **Data Set Filter** dialog box opens.</span></span> <span data-ttu-id="296d7-135">Se la struttura contiene una tabella nidificata, è possibile creare un filtro in due parti.</span><span class="sxs-lookup"><span data-stu-id="296d7-135">If the structure contains a nested table, you can create a filter in two parts.</span></span> <span data-ttu-id="296d7-136">Per prima cosa, impostare le condizioni sulla tabella del case usando la finestra di dialogo **Filtro dei set di dati** , quindi impostare le condizioni sulle righe annidate usando la finestra di dialogo **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="296d7-136">First, set conditions on the case table by using the **Data Set Filter** dialog box, and then set conditions on the nested rows by using the **Filter** dialog box.</span></span>  
  
7.  <span data-ttu-id="296d7-137">Nella finestra di dialogo **Filtro dei set di dati** fare clic sulla riga superiore della griglia, in **Colonna struttura di data mining**, quindi selezionare una tabella o una colonna dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="296d7-137">In the **Data Set Filter** dialog box, click the top row in the grid, under **Mining Structure Column**, and select a table or column from the list.</span></span>  
  
     <span data-ttu-id="296d7-138">Se la vista origine dati contiene più tabelle o una tabella nidificata, è necessario selezionare prima il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="296d7-138">If the data source view contains multiple tables, or a nested table, you must first select the table name.</span></span> <span data-ttu-id="296d7-139">In caso contrario, è possibile selezionare le colonne direttamente dalla tabella del case.</span><span class="sxs-lookup"><span data-stu-id="296d7-139">Otherwise, you can select columns from the case table directly.</span></span>  
  
     <span data-ttu-id="296d7-140">Aggiungere una nuova riga per ogni colonna che si desidera filtrare.</span><span class="sxs-lookup"><span data-stu-id="296d7-140">Add a new row for each column that you want to filter.</span></span>  
  
8.  <span data-ttu-id="296d7-141">Usare le colonne **Operator**e **Value** per definire il modo in cui la colonna viene filtrata.</span><span class="sxs-lookup"><span data-stu-id="296d7-141">Use **Operator**, and **Value** columns to define how the column is filtered.</span></span>  
  
     <span data-ttu-id="296d7-142">**Note** Digitare i valori senza usare le virgolette.</span><span class="sxs-lookup"><span data-stu-id="296d7-142">**Note** Type values without using quotation marks.</span></span>  
  
9. <span data-ttu-id="296d7-143">Fare clic sulla casella di testo **And/Or** e selezionare un operatore logico per definire la modalità di combinazione di più condizioni.</span><span class="sxs-lookup"><span data-stu-id="296d7-143">Click the **And/Or** text box and select a logical operator to define how multiple conditions are combine.</span></span>  
  
10. <span data-ttu-id="296d7-144">Facoltativamente, fare clic sul pulsante Sfoglia **(...)** a destra della casella di testo **valore** per aprire la finestra di dialogo **filtro** e impostare le condizioni nella tabella nidificata o nelle singole colonne della tabella del case.</span><span class="sxs-lookup"><span data-stu-id="296d7-144">Optionally, click the browse button **(...)** at the right of the **Value** text box to open the **Filter** dialog box and set conditions on the nested table or on the individual case table columns.</span></span>  
  
11. <span data-ttu-id="296d7-145">Verificare la correttezza delle condizioni di filtro completate visualizzando il testo nel riquadro **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="296d7-145">Verify that the completed filter conditions are correct by viewing the text in the **Expression** pane.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="296d7-146">La condizione di filtro viene applicata all'origine dati quando si crea il grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="296d7-146">The filter condition is applied to the data source when you create the accuracy chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="296d7-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="296d7-147">See Also</span></span>  
 <span data-ttu-id="296d7-148">[Scegliere ed eseguire il mapping dei dati di test del modello](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="296d7-148">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 <span data-ttu-id="296d7-149">[Utilizzo di dati di tabelle nidificate come input per un grafico di accuratezza](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span><span class="sxs-lookup"><span data-stu-id="296d7-149">[Using Nested Table Data as an Input for an Accuracy Chart](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span></span>  
 [<span data-ttu-id="296d7-150">Scegliere un tipo di grafico di accuratezza e impostare le opzioni del grafico</span><span class="sxs-lookup"><span data-stu-id="296d7-150">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
