---
title: 'Lezione 5: esecuzione di query di stima | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0037bd2f-aa2d-464b-bf86-b0210f0438b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a5f4d6dd79f62541e207df688349f694680e2421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719074"
---
# <a name="lesson-5-executing-prediction-queries"></a><span data-ttu-id="3f043-102">Lezione 5: Esecuzione di query di stima</span><span class="sxs-lookup"><span data-stu-id="3f043-102">Lesson 5: Executing Prediction Queries</span></span>
  <span data-ttu-id="3f043-103">In questa lezione verrà utilizzato il formato [ \<model> DMX (Select from prediction join)](/sql/dmx/select-from-model-cases-dmx) dell'istruzione SELECT per creare due tipi diversi di stime in base al modello di albero delle decisioni creato nella [lezione 2: aggiunta di modelli di data mining alla struttura di data mining Association](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="3f043-103">In this lesson, you will use the [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement to create two different types of predictions based on the decision tree model you created in [Lesson 2: Adding Mining Models to the Association Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="3f043-104">Di seguito è riportata la definizione di questi tipi di stima.</span><span class="sxs-lookup"><span data-stu-id="3f043-104">These prediction types are defined below.</span></span>  
  
 <span data-ttu-id="3f043-105">Query singleton</span><span class="sxs-lookup"><span data-stu-id="3f043-105">Singleton Query</span></span>  
 <span data-ttu-id="3f043-106">Utilizzare una query singleton per fornire valori ad hoc in caso di esecuzione di stime.</span><span class="sxs-lookup"><span data-stu-id="3f043-106">Use a singleton query to provide ad hoc values when making predictions.</span></span> <span data-ttu-id="3f043-107">È ad esempio possibile determinare se un cliente sia il probabile acquirente di una bicicletta passando alla query input come la distanza dal luogo di lavoro, il prefisso telefonico o il numero di figli del cliente.</span><span class="sxs-lookup"><span data-stu-id="3f043-107">For example, you can determine whether a single customer is likely to be a bike buyer, by passing inputs to the query such as the commute distance, the area code, or the number of children of the customer.</span></span> <span data-ttu-id="3f043-108">La query singleton restituisce un valore che indica con quale probabilità il cliente acquisterà una bicicletta in base agli input forniti.</span><span class="sxs-lookup"><span data-stu-id="3f043-108">The singleton query returns a value that indicates how likely the person is to purchase a bicycle based on those inputs.</span></span>  
  
 <span data-ttu-id="3f043-109">Query batch</span><span class="sxs-lookup"><span data-stu-id="3f043-109">Batch Query</span></span>  
 <span data-ttu-id="3f043-110">Una query batch consente di determinare quali clienti, all'interno di una tabella di potenziali clienti, è probabile che acquistino una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="3f043-110">Use a batch query to determine who in a table of potential customers is likely to purchase a bicycle.</span></span> <span data-ttu-id="3f043-111">Ad esempio, se il reparto marketing fornisce un elenco di clienti con i relativi attributi, è possibile utilizzare una stima batch per stabilire quali di essi è probabile che acquistino una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="3f043-111">For example, if your marketing department provides you with a list of customers and customer attributes, then you can use a batch prediction to determine who from the table is likely to purchase a bicycle.</span></span>  
  
 <span data-ttu-id="3f043-112">Il modulo [Select from \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) dell'istruzione SELECT contiene tre parti:</span><span class="sxs-lookup"><span data-stu-id="3f043-112">The [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement contains three parts:</span></span>  
  
-   <span data-ttu-id="3f043-113">Un elenco di funzioni di stima e di colonne del modello di data mining restituite nei risultati.</span><span class="sxs-lookup"><span data-stu-id="3f043-113">A list of the mining model columns and prediction functions that are returned in the results.</span></span> <span data-ttu-id="3f043-114">I risultati possono anche includere le colonne di input provenienti dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3f043-114">The results can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="3f043-115">La query di origine che definisce i dati utilizzati per la creazione di una stima,</span><span class="sxs-lookup"><span data-stu-id="3f043-115">The source query defining the data that is being used to create a prediction.</span></span> <span data-ttu-id="3f043-116">ad esempio un elenco di clienti in una query batch.</span><span class="sxs-lookup"><span data-stu-id="3f043-116">For example, in a batch query this could be a list of customers.</span></span>  
  
-   <span data-ttu-id="3f043-117">Un mapping tra le colonne del modello di data mining e i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="3f043-117">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="3f043-118">Se i nomi corrispondono, è possibile utilizzare la sintassi NATURAL e tralasciare i mapping delle colonne.</span><span class="sxs-lookup"><span data-stu-id="3f043-118">If these names match, then you can use NATURAL syntax and leave out the column mappings.</span></span>  
  
 <span data-ttu-id="3f043-119">Per migliorare ulteriormente la query, è possibile utilizzare le funzioni di stima</span><span class="sxs-lookup"><span data-stu-id="3f043-119">You can further enhance the query by using prediction functions.</span></span> <span data-ttu-id="3f043-120">che forniscono informazioni aggiuntive, quali la probabilità che una stima sia confermata dai fatti, e supporto per la stima nel set di dati di training.</span><span class="sxs-lookup"><span data-stu-id="3f043-120">Prediction functions provide additional information, such as the probability of a prediction occurring, and provide support for the prediction in the training dataset.</span></span> <span data-ttu-id="3f043-121">Per ulteriori informazioni sulle funzioni di stima, vedere [funzioni &#40;&#41;DMX ](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="3f043-121">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="3f043-122">Le stime in questa esercitazione sono basate sulla tabella ProspectiveBuyer nel database di esempio [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f043-122">The predictions in this tutorial are based on the ProspectiveBuyer table in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database.</span></span> <span data-ttu-id="3f043-123">La tabella ProspectiveBuyer contiene un elenco di potenziali clienti con le relative caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="3f043-123">The ProspectiveBuyer table contains a list of potential customers and their associated characteristics.</span></span> <span data-ttu-id="3f043-124">I clienti in questa tabella sono indipendenti dai clienti utilizzati per creare il modello di data mining dell'albero delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="3f043-124">The customers in this table are independent of the customers that were used to create the decision tree mining model.</span></span>  
  
 <span data-ttu-id="3f043-125">È inoltre possibile creare stime utilizzando il generatore delle query di stima in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f043-125">You can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="3f043-126">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="3f043-126">Lesson Tasks</span></span>  
 <span data-ttu-id="3f043-127">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f043-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="3f043-128">Creazione di una query singleton per determinare la probabilità che un particolare cliente acquisti una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="3f043-128">Create a singleton query to determine whether a specific customer is likely to purchase a bicycle.</span></span>  
  
-   <span data-ttu-id="3f043-129">Creazione di una query batch per determinare quali clienti, all'interno di una tabella di clienti, è probabile che acquistino una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="3f043-129">Create a batch query to determine which customers, listed in a table of customers, are likely to purchase a bicycle.</span></span>  
  
## <a name="singleton-query"></a><span data-ttu-id="3f043-130">Query singleton</span><span class="sxs-lookup"><span data-stu-id="3f043-130">Singleton Query</span></span>  
 <span data-ttu-id="3f043-131">Il primo passaggio consiste nell'utilizzare il [modello SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in una query di stima singleton.</span><span class="sxs-lookup"><span data-stu-id="3f043-131">The first step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a singleton prediction query.</span></span> <span data-ttu-id="3f043-132">Di seguito è riportato un esempio generico dell'istruzione singleton:</span><span class="sxs-lookup"><span data-stu-id="3f043-132">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
```  
  
 <span data-ttu-id="3f043-133">La prima riga del codice definisce le colonne del modello di data mining restituite dalla query e specifica il modello di data mining utilizzato per generare la stima:</span><span class="sxs-lookup"><span data-stu-id="3f043-133">The first line of the code defines the columns from the mining model that the query should return, and specifies the mining model that is used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
```  
  
 <span data-ttu-id="3f043-134">Le successive righe del codice definiscono le caratteristiche del cliente utilizzate per creare una stima:</span><span class="sxs-lookup"><span data-stu-id="3f043-134">The next lines of the code define the characteristics of the customer that you use to create a prediction:</span></span>  
  
```  
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="3f043-135">Se si specifica NATURAL PREDICTION JOIN, il server ricercherà la corrispondenza tra ogni colonna del modello e una colonna dell'input, in base ai nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="3f043-135">If you specify NATURAL PREDICTION JOIN, the server matches each column from the model to a column from the input, based on column names.</span></span> <span data-ttu-id="3f043-136">Se i nomi di colonna non corrispondono, le colonne vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="3f043-136">If column names do not match, the columns are ignored.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query"></a><span data-ttu-id="3f043-137">Per creare una query di stima singleton</span><span class="sxs-lookup"><span data-stu-id="3f043-137">To create a singleton prediction query</span></span>  
  
1.  <span data-ttu-id="3f043-138">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="3f043-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="3f043-139">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="3f043-139">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="3f043-140">Copiare l'esempio generico dell'istruzione singleton nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="3f043-140">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="3f043-141">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3f043-141">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="3f043-142">con:</span><span class="sxs-lookup"><span data-stu-id="3f043-142">with:</span></span>  
  
    ```  
    [Bike Buyer] AS Buyer, PredictHistogram([Bike Buyer]) AS Statistics  
    ```  
  
     <span data-ttu-id="3f043-143">L'istruzione AS viene utilizzata per creare un alias delle colonne restituite dalla query.</span><span class="sxs-lookup"><span data-stu-id="3f043-143">The AS statement is used to alias columns returned by the query.</span></span> <span data-ttu-id="3f043-144">La funzione [PredictHistogram](/sql/dmx/predicthistogram-dmx) restituisce statistiche sulla stima, incluse la probabilità e il supporto.</span><span class="sxs-lookup"><span data-stu-id="3f043-144">The [PredictHistogram](/sql/dmx/predicthistogram-dmx) function returns statistics about the prediction, including the probability and the support.</span></span> <span data-ttu-id="3f043-145">Per ulteriori informazioni sulle funzioni che possono essere utilizzate in un'istruzione di stima, vedere [funzioni &#40;&#41;DMX ](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="3f043-145">For more information about the functions that can be used in a prediction statement, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
4.  <span data-ttu-id="3f043-146">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3f043-146">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="3f043-147">con:</span><span class="sxs-lookup"><span data-stu-id="3f043-147">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="3f043-148">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3f043-148">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column name>], ...)  AS t  
    ```  
  
     <span data-ttu-id="3f043-149">con:</span><span class="sxs-lookup"><span data-stu-id="3f043-149">with:</span></span>  
  
    ```  
    (SELECT 35 AS [Age],  
      '5-10 Miles' AS [Commute Distance],  
      '1' AS [House Owner Flag],  
      2 AS [Number Cars Owned],  
      2 AS [Total Children]) AS t  
    ```  
  
     <span data-ttu-id="3f043-150">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="3f043-150">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
       [Bike Buyer] AS Buyer,  
       PredictHistogram([Bike Buyer]) AS Statistics  
    FROM  
       [Decision Tree]  
    NATURAL PREDICTION JOIN  
    (SELECT 35 AS [Age],  
       '5-10 Miles' AS [Commute Distance],  
       '1' AS [House Owner Flag],  
       2 AS [Number Cars Owned],  
       2 AS [Total Children]) AS t  
    ```  
  
6.  <span data-ttu-id="3f043-151">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="3f043-151">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="3f043-152">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Singleton_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="3f043-152">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_Query.dmx`.</span></span>  
  
8.  <span data-ttu-id="3f043-153">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="3f043-153">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="3f043-154">La query restituisce una stima sulla probabilità che un cliente con le caratteristiche specificate acquisti una bicicletta, nonché le statistiche relative a tale stima.</span><span class="sxs-lookup"><span data-stu-id="3f043-154">The query returns a prediction about whether a customer with the specified characteristics will purchase a bicycle, as well as statistics about that prediction.</span></span>  
  
## <a name="batch-query"></a><span data-ttu-id="3f043-155">Query batch</span><span class="sxs-lookup"><span data-stu-id="3f043-155">Batch Query</span></span>  
 <span data-ttu-id="3f043-156">Il passaggio successivo consiste nell'utilizzare il [modello SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in una query di stima batch.</span><span class="sxs-lookup"><span data-stu-id="3f043-156">The next step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a batch prediction query.</span></span> <span data-ttu-id="3f043-157">Di seguito è riportato un esempio generico di istruzione batch:</span><span class="sxs-lookup"><span data-stu-id="3f043-157">The following is a generic example of a batch statement:</span></span>  
  
```  
SELECT TOP <number> <select list>   
FROM [<mining model name>]  
PREDICTION JOIN  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
ON <on clause, mapping,>  
WHERE <where clause, boolean expression,>  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="3f043-158">Come nella query singleton, le prime due righe del codice definiscono le colonne del modello di data mining restituite dalla query, nonché il nome del modello di data mining utilizzato per generare la stima.</span><span class="sxs-lookup"><span data-stu-id="3f043-158">As in the singleton query, the first two lines of the code define the columns from mining model that the query returns, as well as the name of the mining model that is used to generate the prediction.</span></span> <span data-ttu-id="3f043-159">Nell' \<number> istruzione Top viene specificato che la query restituirà solo il numero o i risultati specificati da \<number> .</span><span class="sxs-lookup"><span data-stu-id="3f043-159">The TOP \<number> statement specifies that the query will only return the number or the results specified by \<number>.</span></span>  
  
 <span data-ttu-id="3f043-160">Le successive righe del codice definiscono i dati di origine su cui si basano le stime:</span><span class="sxs-lookup"><span data-stu-id="3f043-160">The next lines of the code define the source data that the predictions are based on:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
```  
  
 <span data-ttu-id="3f043-161">Sebbene siano disponibili diverse opzioni per il recupero dei dati di origine, in questa esercitazione si utilizzerà OPENQUERY.</span><span class="sxs-lookup"><span data-stu-id="3f043-161">You have several options for the method of retrieving the source data, but in this tutorial, you will use OPENQUERY.</span></span> <span data-ttu-id="3f043-162">Per altre informazioni sulle opzioni disponibili, vedere [&#60;query sui dati di origine&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="3f043-162">For more information about the options available, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
 <span data-ttu-id="3f043-163">La riga successiva definisce il mapping tra le colonne di origine nel modello di data mining e le colonne nei dati di origine:</span><span class="sxs-lookup"><span data-stu-id="3f043-163">The next line defines the mapping between the source columns in the mining model and the columns in the source data:</span></span>  
  
```  
ON <column mappings>  
```  
  
 <span data-ttu-id="3f043-164">La clausola WHERE filtra i risultati restituiti dalla query di stima:</span><span class="sxs-lookup"><span data-stu-id="3f043-164">The WHERE clause filters the results returned by the prediction query:</span></span>  
  
```  
WHERE <where clause, boolean expression,>  
```  
  
 <span data-ttu-id="3f043-165">L'ultima riga (facoltativa) del codice specifica la colonna in base alla quale verranno ordinati i risultati:</span><span class="sxs-lookup"><span data-stu-id="3f043-165">The last and optional line of the code specifies the column that the results will be ordered by:</span></span>  
  
```  
ORDER BY <expression> [DESC|ASC]  
```  
  
 <span data-ttu-id="3f043-166">Utilizzare ORDER BY in combinazione con l' \<number> istruzione top, per filtrare i risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="3f043-166">Use ORDER BY in combination with the TOP \<number> statement, to filter the results that are returned.</span></span> <span data-ttu-id="3f043-167">In questa stima, ad esempio, verranno restituiti i primi dieci acquirenti di biciclette, ordinati in base alla probabilità che la stima si riveli corretta.</span><span class="sxs-lookup"><span data-stu-id="3f043-167">For example, in this prediction you will return the top ten bike buyers, ordered by the probability of the prediction being correct.</span></span> <span data-ttu-id="3f043-168">È possibile utilizzare la sintassi [DESC|ASC] per controllare l'ordine di visualizzazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="3f043-168">You can use [DESC|ASC] syntax to control the order in which the results are displayed.</span></span>  
  
#### <a name="to-create-a-batch-prediction-query"></a><span data-ttu-id="3f043-169">Per creare una query di stima batch</span><span class="sxs-lookup"><span data-stu-id="3f043-169">To create a batch prediction query</span></span>  
  
1.  <span data-ttu-id="3f043-170">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="3f043-170">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="3f043-171">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="3f043-171">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="3f043-172">Copiare l'esempio generico di istruzione batch nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="3f043-172">Copy the generic example of the batch statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="3f043-173">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3f043-173">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="3f043-174">con:</span><span class="sxs-lookup"><span data-stu-id="3f043-174">with:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    ```  
  
     <span data-ttu-id="3f043-175">La clausola TOP 10 specifica che la query restituirà solo i primi dieci risultati.</span><span class="sxs-lookup"><span data-stu-id="3f043-175">The TOP 10 clause specifies that only the top ten results will be returned by the query.</span></span> <span data-ttu-id="3f043-176">L'istruzione ORDER BY nella query consente di ordinare i risultati in base alla probabilità che la stima si riveli corretta. Verranno quindi restituiti solo i dieci risultati con un grado di probabilità maggiore.</span><span class="sxs-lookup"><span data-stu-id="3f043-176">The ORDER BY statement in this query orders the results by the probability of the prediction being correct, so only the ten most likely results will be returned.</span></span>  
  
4.  <span data-ttu-id="3f043-177">Sostituire il segnaposto seguente:</span><span class="sxs-lookup"><span data-stu-id="3f043-177">Replace the following placeholder:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="3f043-178">Con il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="3f043-178">With the name of the model:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="3f043-179">Sostituire l'istruzione generica OPENQUERY seguente:</span><span class="sxs-lookup"><span data-stu-id="3f043-179">Replace the following generic OPENQUERY statement:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="3f043-180">Con un'istruzione che faccia riferimento al data warehouse Adventureworks corrente, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3f043-180">With a statement that references the current Adventureworks data warehouse, such as:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2014],  
      'SELECT  
        [LastName],  
        [FirstName],  
        [MaritalStatus],  
        [Gender],  
        [YearlyIncome],  
        [TotalChildren],  
        [NumberChildrenAtHome],  
        [Education],  
        [Occupation],  
        [HouseOwnerFlag],  
        [NumberCarsOwned]  
      FROM  
        [dbo].[ProspectiveBuyer]  
      ') AS t  
    ```  
  
6.  <span data-ttu-id="3f043-181">Sostituire la sintassi generica seguente:</span><span class="sxs-lookup"><span data-stu-id="3f043-181">Replace the following generic syntax:</span></span>  
  
    ```  
    <ON clause, mapping,>   
    WHERE <where clause, boolean expression,>  
    ORDER BY <expression>  
    ```  
  
     <span data-ttu-id="3f043-182">Con i mapping delle colonne necessari per questo modello e per il set di dati di input:</span><span class="sxs-lookup"><span data-stu-id="3f043-182">With the column mappings needed for this model and input data set:</span></span>  
  
    ```  
    [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
     <span data-ttu-id="3f043-183">Specificare `DESC` per fare in modo che l'elenco dei risultati inizi dalla probabilità più alta.</span><span class="sxs-lookup"><span data-stu-id="3f043-183">Specify `DESC` in order to list the results with the highest probability first.</span></span>  
  
     <span data-ttu-id="3f043-184">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="3f043-184">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    FROM  
      [Decision Tree]  
    PREDICTION JOIN  
      OPENQUERY([Adventure Works DW 2014],  
        'SELECT  
          [LastName],  
          [FirstName],  
          [MaritalStatus],  
          [Gender],  
          [YearlyIncome],  
          [TotalChildren],  
          [NumberChildrenAtHome],  
          [Education],  
          [Occupation],  
          [HouseOwnerFlag],  
          [NumberCarsOwned]  
        FROM  
          [dbo].[ProspectiveBuyer]  
        ') AS t  
    ON  
      [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
7.  <span data-ttu-id="3f043-185">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="3f043-185">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="3f043-186">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Batch_Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="3f043-186">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Batch_Prediction.dmx`.</span></span>  
  
9. <span data-ttu-id="3f043-187">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="3f043-187">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="3f043-188">La query restituisce una tabella con i nomi dei clienti, una stima relativa all'acquisto di una bicicletta da parte di ogni cliente e la probabilità che la stima si riveli corretta.</span><span class="sxs-lookup"><span data-stu-id="3f043-188">The query returns a table containing customer names, a prediction of whether each customer will purchase a bicycle, and the probability of the prediction.</span></span>  
  
 <span data-ttu-id="3f043-189">Si conclude così l'esercitazione Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="3f043-189">This is the last step in the Bike Buyer tutorial.</span></span> <span data-ttu-id="3f043-190">A questo punto si dispone di un set di modelli di data mining che è possibile utilizzare per valutare le analogie tra i propri clienti e stimare se i potenziali clienti acquisteranno una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="3f043-190">You now have a set of mining models that you can use to explore similarities between you customers and predict whether potential customers will purchase a bicycle.</span></span>  
  
 <span data-ttu-id="3f043-191">Per informazioni sull'utilizzo di DMX in uno scenario Market basket, vedere l' [esercitazione su Market basket DMX](../../2014/tutorials/market-basket-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="3f043-191">To learn how to use DMX in a Market Basket scenario, see [Market Basket DMX Tutorial](../../2014/tutorials/market-basket-dmx-tutorial.md).</span></span>  
  
  
