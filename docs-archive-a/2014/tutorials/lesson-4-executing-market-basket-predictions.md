---
title: 'Lezione 4: esecuzione di stime Market basket | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b3238f1b-ea04-4253-ade2-838a806b62fe
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 3b49fc242eb8b2242269c5af33cc094937bbe0de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627580"
---
# <a name="lesson-4-executing-market-basket-predictions"></a><span data-ttu-id="1b866-102">Lezione 4: Esecuzione delle stime relative a Market Basket</span><span class="sxs-lookup"><span data-stu-id="1b866-102">Lesson 4: Executing Market Basket Predictions</span></span>
  <span data-ttu-id="1b866-103">In questa lezione verrà utilizzata l' `SELECT` istruzione DMX per creare stime basate sui modelli di associazione creati nella [lezione 2: aggiunta di modelli di data mining alla struttura di data mining Market basket](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="1b866-103">In this lesson, you will use the DMX `SELECT` statement to create predictions based on the association models you created in [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="1b866-104">Una query della stima viene creata utilizzando l'istruzione DMX `SELECT` e aggiungendo una clausola `PREDICTION JOIN`</span><span class="sxs-lookup"><span data-stu-id="1b866-104">A prediction query is created by using the DMX `SELECT` statement and adding a `PREDICTION JOIN` clause.</span></span> <span data-ttu-id="1b866-105">Per ulteriori informazioni sulla sintassi di un prediction join, vedere [SELECT FROM &#60;model&#62; prediction join &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span><span class="sxs-lookup"><span data-stu-id="1b866-105">For more information about the syntax of a prediction join, see [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span></span>  
  
 <span data-ttu-id="1b866-106">Il modulo **Select from \<model> PREDICTION JOIN** dell' `SELECT` istruzione contiene tre parti:</span><span class="sxs-lookup"><span data-stu-id="1b866-106">The **SELECT FROM \<model> PREDICTION JOIN** form of the `SELECT` statement contains three parts:</span></span>  
  
-   <span data-ttu-id="1b866-107">Un elenco di colonne e funzioni di stima del modello di data mining restituite nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="1b866-107">A list of the mining model columns and prediction functions that are returned in the result set.</span></span> <span data-ttu-id="1b866-108">Può includere anche le colonne di input dall'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="1b866-108">This list can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="1b866-109">Una query di origine che definisce i dati utilizzati per la creazione di una stima,</span><span class="sxs-lookup"><span data-stu-id="1b866-109">A source query that defines the data that is being used to create a prediction.</span></span> <span data-ttu-id="1b866-110">Ad esempio, se si stanno creando più stime in un batch, la query di origine è in grado di recuperare un elenco dei clienti.</span><span class="sxs-lookup"><span data-stu-id="1b866-110">For example, if you are creating many predictions in a batch, the source query could retrieve a list of customers.</span></span>  
  
-   <span data-ttu-id="1b866-111">Un mapping tra le colonne del modello di data mining e i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="1b866-111">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="1b866-112">Se i nomi delle colonne corrispondono, è possibile utilizzare la sintassi `NATURAL PREDICTION JOIN` e omettere i mapping delle colonne.</span><span class="sxs-lookup"><span data-stu-id="1b866-112">If the columns names match, you can use the `NATURAL PREDICTION JOIN` syntax and omit the column mappings.</span></span>  
  
 <span data-ttu-id="1b866-113">Per migliorare la query, è possibile utilizzare le funzioni di stima</span><span class="sxs-lookup"><span data-stu-id="1b866-113">You can enhance the query by using prediction functions.</span></span> <span data-ttu-id="1b866-114">che forniscono informazioni aggiuntive, quali la probabilità che una stima sia confermata dai fatti o supporto per una stima nel set di dati di training.</span><span class="sxs-lookup"><span data-stu-id="1b866-114">Prediction functions provide additional information, such as the probability of a prediction occurring, or the support for a prediction in the training dataset.</span></span> <span data-ttu-id="1b866-115">Per ulteriori informazioni sulle funzioni di stima, vedere [funzioni &#40;&#41;DMX ](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="1b866-115">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="1b866-116">È inoltre possibile utilizzare il generatore delle query di stima in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per creare query di stima.</span><span class="sxs-lookup"><span data-stu-id="1b866-116">You can also use the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create prediction queries.</span></span>  
  
## <a name="singleton-prediction-join-statement"></a><span data-ttu-id="1b866-117">Istruzione PREDICTION JOIN singleton</span><span class="sxs-lookup"><span data-stu-id="1b866-117">Singleton PREDICTION JOIN Statement</span></span>  
 <span data-ttu-id="1b866-118">Il primo passaggio consiste nel creare una query singleton utilizzando la sintassi **Select from \<model> PREDICTION JOIN** e specificando come input un singolo set di valori.</span><span class="sxs-lookup"><span data-stu-id="1b866-118">The first step is to create a singleton query, by using the **SELECT FROM \<model> PREDICTION JOIN** syntax and supplying a single set of values as input.</span></span> <span data-ttu-id="1b866-119">Di seguito è riportato un esempio generico dell'istruzione singleton:</span><span class="sxs-lookup"><span data-stu-id="1b866-119">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list>  
    FROM [<mining model>]   
[NATURAL] PREDICTION JOIN  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
AS [<input alias>]  
```  
  
 <span data-ttu-id="1b866-120">La prima riga del codice definisce le colonne del modello di data mining restituite dalla query e specifica il nome del modello di data mining utilizzato per generare la stima:</span><span class="sxs-lookup"><span data-stu-id="1b866-120">The first line of the code defines the columns from the mining model that the query returns, and specifies the name of the mining model used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>]   
```  
  
 <span data-ttu-id="1b866-121">La riga successiva del codice indica l'operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="1b866-121">The next line of the code indicates the operation to perform.</span></span> <span data-ttu-id="1b866-122">Perché si specificheranno valori per ognuna delle colonne e si digiteranno i nomi delle colonne in modo che corrispondano al modello, è possibile utilizzare la sintassi `NATURAL PREDICTION JOIN`.</span><span class="sxs-lookup"><span data-stu-id="1b866-122">Because you will specify values for each of the columns and type the column names exactly so as to match the model, you can use the `NATURAL PREDICTION JOIN` syntax.</span></span> <span data-ttu-id="1b866-123">Tuttavia, se i nomi della colonna sono diversi, è necessario specificare i mapping tra le colonne nel modello e le colonne nei nuovi dati aggiungendo una clausola `ON`.</span><span class="sxs-lookup"><span data-stu-id="1b866-123">However, if the column names were different, you would have to specify mappings between the columns in the model and the columns in the new data by adding an `ON` clause.</span></span>  
  
```  
[NATURAL] PREDICTION JOIN  
```  
  
 <span data-ttu-id="1b866-124">Le righe successive del codice definiscono i prodotti presenti nel carrello acquisti che verranno utilizzati per stimare i prodotti aggiuntivi che un cliente aggiungerà:</span><span class="sxs-lookup"><span data-stu-id="1b866-124">The next lines of the code define the products in the shopping cart that will be used to predict additional products that a customer will add:</span></span>  
  
```  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="1b866-125">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="1b866-125">Lesson Tasks</span></span>  
 <span data-ttu-id="1b866-126">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b866-126">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="1b866-127">Creazione di una query che stima quali altri articoli è probabile che vengano acquistati da un cliente, sulla base degli articoli già inseriti nel carrello acquisti.</span><span class="sxs-lookup"><span data-stu-id="1b866-127">Create a query that predicts what other items a customer will likely purchase, based on items already existing in their shopping cart.</span></span> <span data-ttu-id="1b866-128">Questa query verrà creata utilizzando il modello di data mining con il *MINIMUM_PROBABILITY*predefinito.</span><span class="sxs-lookup"><span data-stu-id="1b866-128">You will create this query by using the mining model with the default *MINIMUM_PROBABILITY*.</span></span>  
  
-   <span data-ttu-id="1b866-129">Creazione di una query che stima quali altri articoli è probabile che vengano acquistati da un cliente, sulla base degli articoli già inseriti nel carrello acquisti.</span><span class="sxs-lookup"><span data-stu-id="1b866-129">Create a query that predicts what other items a customer will likely purchase based on items already existing in their shopping cart.</span></span> <span data-ttu-id="1b866-130">Questa query si basa su un modello diverso, in cui *MINIMUM_PROBABILITY* è stato impostato su 0,01.</span><span class="sxs-lookup"><span data-stu-id="1b866-130">This query is based on a different model, in which *MINIMUM_PROBABILITY* has been set to 0.01.</span></span> <span data-ttu-id="1b866-131">Poiché il valore predefinito per *MINIMUM_PROBABILITY* nei modelli di associazione è 0,3, la query su questo modello deve restituire più elementi possibili rispetto alla query sul modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="1b866-131">Because the default value for *MINIMUM_PROBABILITY* in association models is 0.3, the query on this model should return more possible items than the query on the default model.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-the-default-minimum_probability"></a><span data-ttu-id="1b866-132">Creazione di una stima utilizzando un modello con il valore predefinito per MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="1b866-132">Create a Prediction by Using a Model with the Default MINIMUM_PROBABILITY</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="1b866-133">Per creare una query di associazione</span><span class="sxs-lookup"><span data-stu-id="1b866-133">To create an association query</span></span>  
  
1.  <span data-ttu-id="1b866-134">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX** per aprire l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="1b866-134">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="1b866-135">Copiare l'esempio generico dell'istruzione `PREDICTION JOIN` nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="1b866-135">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="1b866-136">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1b866-136">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="1b866-137">con:</span><span class="sxs-lookup"><span data-stu-id="1b866-137">with:</span></span>  
  
    ```  
    PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
     <span data-ttu-id="1b866-138">È sufficiente includere il nome di colonna [Products], ma utilizzando la funzione [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) , è possibile limitare il numero di prodotti restituiti dall'algoritmo a tre.</span><span class="sxs-lookup"><span data-stu-id="1b866-138">You could just include the column name [Products], but by using the [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) function, you can limit the number of products that are returned by the algorithm to three.</span></span> <span data-ttu-id="1b866-139">È inoltre possibile utilizzare `INCLUDE_STATISTICS`, che restituisce il supporto, la probabilità e il valore della probabilità adattato per ciascun prodotto.</span><span class="sxs-lookup"><span data-stu-id="1b866-139">You can also use `INCLUDE_STATISTICS`, which returns the support, probability, and adjusted probability for each product.</span></span> <span data-ttu-id="1b866-140">Queste statistiche consentono di valutare l'accuratezza della stima.</span><span class="sxs-lookup"><span data-stu-id="1b866-140">These statistics help you rate the accuracy of the prediction.</span></span>  
  
4.  <span data-ttu-id="1b866-141">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1b866-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="1b866-142">con:</span><span class="sxs-lookup"><span data-stu-id="1b866-142">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="1b866-143">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1b866-143">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="1b866-144">con:</span><span class="sxs-lookup"><span data-stu-id="1b866-144">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="1b866-145">Questa istruzione utilizza l'istruzione `UNION` per specificare tre prodotti che devono essere inclusi nel carrello acquisti insieme ai prodotti stimati.</span><span class="sxs-lookup"><span data-stu-id="1b866-145">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="1b866-146">La colonna Model nell'istruzione `SELECT` corrisponde alla colonna del modello presente nella tabella dei prodotti nidificata.</span><span class="sxs-lookup"><span data-stu-id="1b866-146">The Model column in the `SELECT` statement corresponds to the model column that is contained in the nested products table.</span></span>  
  
     <span data-ttu-id="1b866-147">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="1b866-147">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Default Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="1b866-148">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="1b866-148">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="1b866-149">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="1b866-149">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="1b866-150">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="1b866-150">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="1b866-151">La query restituisce una tabella che contiene tre prodotti: HL Mountain Tire, Fender Set – Mountain e ML Mountain Tire.</span><span class="sxs-lookup"><span data-stu-id="1b866-151">The query returns a table that contains three products: HL Mountain Tire, Fender Set - Mountain, and ML Mountain Tire.</span></span> <span data-ttu-id="1b866-152">Nella tabella vengono elencati questi prodotti restituiti in ordine di probabilità.</span><span class="sxs-lookup"><span data-stu-id="1b866-152">The table lists these returned products in order of probability.</span></span> <span data-ttu-id="1b866-153">Il prodotto restituito con la maggiore probabilità di essere incluso nello stesso carrello acquisti dei tre prodotti specificati nella query viene visualizzato all'inizio della tabella.</span><span class="sxs-lookup"><span data-stu-id="1b866-153">The returned product that is most likely to be included in the same shopping cart as the three products specified in the query appears at the top of the table.</span></span> <span data-ttu-id="1b866-154">I due prodotti che seguono sono quelli con la seconda maggiore probabilità di essere inclusi nel carrello acquisti.</span><span class="sxs-lookup"><span data-stu-id="1b866-154">The two products that follow are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="1b866-155">La tabella contiene anche le statistiche che descrivono l'accuratezza della stima.</span><span class="sxs-lookup"><span data-stu-id="1b866-155">The table also contains statistics describing the accuracy of the prediction.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-a-minimum_probability-of-001"></a><span data-ttu-id="1b866-156">Creazione di una stima utilizzando un modello con il valore 0,01 per MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="1b866-156">Create a Prediction by Using a Model with a MINIMUM_PROBABILITY of 0.01</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="1b866-157">Per creare una query di associazione</span><span class="sxs-lookup"><span data-stu-id="1b866-157">To create an association query</span></span>  
  
1.  <span data-ttu-id="1b866-158">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX** per aprire l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="1b866-158">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="1b866-159">Copiare l'esempio generico dell'istruzione `PREDICTION JOIN` nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="1b866-159">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="1b866-160">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1b866-160">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="1b866-161">con:</span><span class="sxs-lookup"><span data-stu-id="1b866-161">with:</span></span>  
  
    ```  
    PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
4.  <span data-ttu-id="1b866-162">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1b866-162">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="1b866-163">con:</span><span class="sxs-lookup"><span data-stu-id="1b866-163">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="1b866-164">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1b866-164">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="1b866-165">con:</span><span class="sxs-lookup"><span data-stu-id="1b866-165">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="1b866-166">Questa istruzione utilizza l'istruzione `UNION` per specificare tre prodotti che devono essere inclusi nel carrello acquisti insieme ai prodotti stimati.</span><span class="sxs-lookup"><span data-stu-id="1b866-166">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="1b866-167">La colonna `[Model]` nell'istruzione `SELECT` corrisponde alla colonna della tabella dei prodotti nidificata.</span><span class="sxs-lookup"><span data-stu-id="1b866-167">The `[Model]` column in the `SELECT` statement corresponds to the column in the nested products table.</span></span>  
  
     <span data-ttu-id="1b866-168">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="1b866-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Modified Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="1b866-169">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="1b866-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="1b866-170">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Modified Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="1b866-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="1b866-171">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="1b866-171">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="1b866-172">La query restituisce una tabella che contiene tre prodotti: HL Mountain Tire, Water Bottle e Fender Set – Mountain.</span><span class="sxs-lookup"><span data-stu-id="1b866-172">The query returns a table that contains three products: HL Mountain Tire, Water Bottle, and Fender Set - Mountain.</span></span> <span data-ttu-id="1b866-173">Nella tabella vengono elencati questi prodotti in ordine di probabilità.</span><span class="sxs-lookup"><span data-stu-id="1b866-173">The table lists these products in order of probability.</span></span> <span data-ttu-id="1b866-174">Il prodotto visualizzato nella parte superiore della tabella è il prodotto con la maggiore probabilità di essere incluso nello stesso carrello acquisti dei tre prodotti specificati nella query.</span><span class="sxs-lookup"><span data-stu-id="1b866-174">The product that appears at the top of the table is the product that is most likely to be included in the same shopping cart as the three products specified in the query.</span></span> <span data-ttu-id="1b866-175">I due prodotti rimanenti sono quelli con la seconda maggiore probabilità di essere inclusi nel carrello acquisti.</span><span class="sxs-lookup"><span data-stu-id="1b866-175">The remaining products are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="1b866-176">La tabella contiene anche le statistiche che descrivono l'accuratezza della stima.</span><span class="sxs-lookup"><span data-stu-id="1b866-176">The table also contains statistics that describe the accuracy of the prediction.</span></span>  
  
     <span data-ttu-id="1b866-177">Nei risultati di questa query è possibile osservare che il valore del parametro *MINIMUM_PROBABILITY* influiscono sui risultati restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="1b866-177">You can see from the results of this query that the value of the *MINIMUM_PROBABILITY* parameter affects the results returned by the query.</span></span>  
  
 <span data-ttu-id="1b866-178">Questo passaggio conclude l'esercitazione Market Basket.</span><span class="sxs-lookup"><span data-stu-id="1b866-178">This is the last step in the Market Basket tutorial.</span></span> <span data-ttu-id="1b866-179">A questo punto si dispone di un set di modelli da utilizzare per stimare i prodotti che i clienti potrebbero acquistare contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1b866-179">You now have a set of models that you can use to predict the products that customers might purchase at the same time.</span></span>  
  
 <span data-ttu-id="1b866-180">Per informazioni su come usare DMX in un altro scenario predittivo, vedere [esercitazione DMX Bike Buyer](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="1b866-180">To learn how to use DMX in another predictive scenario, see [Bike Buyer DMX Tutorial](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b866-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b866-181">See Also</span></span>  
 <span data-ttu-id="1b866-182">[Esempi di query sul modello di associazione](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="1b866-182">[Association Model Query Examples](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span></span>  
 [<span data-ttu-id="1b866-183">Interfacce di query di data mining</span><span class="sxs-lookup"><span data-stu-id="1b866-183">Data Mining Query Interfaces</span></span>](../../2014/analysis-services/data-mining/data-mining-query-tools.md)  
  
  
