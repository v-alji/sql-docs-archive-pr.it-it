---
title: 'Lezione 4: esplorazione dei modelli di data mining Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8de3c500-f881-42da-a096-b6c03300d58d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 709df371d840d4b24e420b4fcd08750fd31e8075
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627585"
---
# <a name="lesson-4-browsing-the-bike-buyer-mining-models"></a><span data-ttu-id="e82e5-102">Lezione 4: Esplorazione dei modelli di data mining Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="e82e5-102">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>
  <span data-ttu-id="e82e5-103">In questa lezione verrà utilizzata l'istruzione [Select (DMX)](/sql/dmx/select-dmx) per esplorare il contenuto dei modelli di data mining di clustering e di albero delle decisioni creati nella [lezione 2: aggiunta di modelli di data mining alla struttura di data mining predittiva](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="e82e5-103">In this lesson, you will use the [SELECT (DMX)](/sql/dmx/select-dmx) statement to explore the content in the decision tree and clustering mining models that you created in [Lesson 2: Adding Mining Models to the Predictive Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="e82e5-104">Le colonne contenute in un modello di data mining non sono quelle definite dalla struttura di data mining ma sono un set specifico di colonne che descrivono le tendenze e gli schemi individuati dall'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e82e5-104">The columns contained in a mining model are not the columns defined by the mining structure, but instead are a specific set of columns that describe the trends and patterns that are found by the algorithm.</span></span> <span data-ttu-id="e82e5-105">Queste colonne del modello di data mining sono descritte nel set di righe dello schema [DMSCHEMA_MINING_MODEL_CONTENT set di righe](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) .</span><span class="sxs-lookup"><span data-stu-id="e82e5-105">These mining model columns are described in the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) schema rowset.</span></span> <span data-ttu-id="e82e5-106">La colonna MODEL_NAME nel set di righe dello schema del contenuto, ad esempio, contiene il nome del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="e82e5-106">For example, the MODEL_NAME column in the content schema rowset contains the name of the mining model.</span></span> <span data-ttu-id="e82e5-107">Per un modello di data mining di clustering, la colonna NODE_CAPTION contiene il nome di ogni cluster e la colonna NODE_DESCRIPTION contiene una descrizione delle caratteristiche di ogni cluster.</span><span class="sxs-lookup"><span data-stu-id="e82e5-107">For a clustering mining model, the NODE_CAPTION column contains the name of each cluster, and the NODE_DESCRIPTION column contains a description of the characteristics of each cluster.</span></span> <span data-ttu-id="e82e5-108">È possibile esplorare queste colonne utilizzando l'oggetto SELECT FROM \<model> . Istruzione CONTENT in DMX.</span><span class="sxs-lookup"><span data-stu-id="e82e5-108">You can browse these columns by using the SELECT FROM \<model>.CONTENT statement in DMX.</span></span> <span data-ttu-id="e82e5-109">Questa istruzione consente anche di esplorare i dati utilizzati per creare il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="e82e5-109">You can also use this statement to explore the data that was used to create the mining model.</span></span> <span data-ttu-id="e82e5-110">Per utilizzare questa istruzione è necessario che sia abilitato il drill-through nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="e82e5-110">Drillthrough must be enabled on the mining structure in order to use this statement.</span></span> <span data-ttu-id="e82e5-111">Per ulteriori informazioni sull'istruzione, vedere [SELECT FROM &#60;model&#62;. CASI &#40;&#41;DMX ](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="e82e5-111">For more information about the statement, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
 <span data-ttu-id="e82e5-112">È inoltre possibile ottenere tutti gli stati di una colonna discreta utilizzando l'istruzione SELECT DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="e82e5-112">You can also return all the states of a discrete column by using the SELECT DISTINCT statement.</span></span> <span data-ttu-id="e82e5-113">Se ad esempio si esegue questa operazione su una colonna relativa al sesso, la query restituirà `male` e `female`.</span><span class="sxs-lookup"><span data-stu-id="e82e5-113">For example, if you perform this operation on a gender column, the query will return `male` and `female`.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="e82e5-114">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="e82e5-114">Lesson Tasks</span></span>  
 <span data-ttu-id="e82e5-115">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e82e5-115">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="e82e5-116">Esplorazione del contenuto dei modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="e82e5-116">Explore the content contained within the mining models</span></span>  
  
-   <span data-ttu-id="e82e5-117">Restituzione dei case dall'origine dei dati utilizzata per il training dei modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="e82e5-117">Return the cases from the source data that was used to train the mining models</span></span>  
  
-   <span data-ttu-id="e82e5-118">Esplorazione dei vari stati disponibili per una determinata colonna discreta</span><span class="sxs-lookup"><span data-stu-id="e82e5-118">Explore the different states available for a specific discrete column</span></span>  
  
## <a name="returning-the-content-of-a-mining-model"></a><span data-ttu-id="e82e5-119">Restituzione del contenuto di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="e82e5-119">Returning the Content of a Mining Model</span></span>  
 <span data-ttu-id="e82e5-120">In questa lezione si utilizzerà il [modello di &#60;di selezione da&#62;. CONTENT &#40;istruzione DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) per restituire il contenuto del modello di clustering.</span><span class="sxs-lookup"><span data-stu-id="e82e5-120">In this lesson, you use the [SELECT FROM &#60;model&#62;.CONTENT &#40;DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) statement to return the contents of the clustering model.</span></span>  
  
 <span data-ttu-id="e82e5-121">Di seguito è riportato un esempio generico di SELECT FROM \<model> . Istruzione CONTENT:</span><span class="sxs-lookup"><span data-stu-id="e82e5-121">The following is a generic example of the SELECT FROM \<model>.CONTENT statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CONTENT  
WHERE <where clause>  
```  
  
 <span data-ttu-id="e82e5-122">La prima riga del codice definisce le colonne da restituire dal contenuto del modello di data mining, nonché il modello di data mining a cui sono associate:</span><span class="sxs-lookup"><span data-stu-id="e82e5-122">The first line of the code defines the columns to return from the mining model content, and the mining model they are associated with:</span></span>  
  
```  
SELECT <select list> FROM [<mining model].CONTENT  
```  
  
 <span data-ttu-id="e82e5-123">La clausola .CONTENT accanto al nome del modello di data mining specifica che il contenuto restituito proviene dal modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="e82e5-123">The .CONTENT clause next to the name of the mining model specifies that you are returning content from the mining model.</span></span> <span data-ttu-id="e82e5-124">Per ulteriori informazioni sulle colonne contenute nel modello di data mining, vedere [DMSCHEMA_MINING_MODEL_CONTENT set di righe](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="e82e5-124">For more information about the columns contained in the mining model, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
 <span data-ttu-id="e82e5-125">È possibile utilizzare facoltativamente la riga finale del codice per filtrare i risultati restituiti dall'istruzione:</span><span class="sxs-lookup"><span data-stu-id="e82e5-125">You can optionally use the final line of the code to filter the results returned by the statement:</span></span>  
  
```  
WHERE <where clause>  
```  
  
 <span data-ttu-id="e82e5-126">Se ad esempio si desidera limitare i risultati della query ai soli cluster contenenti un numero elevato di case, è possibile aggiungere all'istruzione SELECT la clausola WHERE seguente:</span><span class="sxs-lookup"><span data-stu-id="e82e5-126">For example, if you want to restrict the results of the query to only the clusters that contain a high number of cases, you can add the following WHERE clause to the SELECT statement:</span></span>  
  
```  
WHERE NODE_SUPPORT > 100  
```  
  
 <span data-ttu-id="e82e5-127">Per ulteriori informazioni sull'utilizzo dell'istruzione WHERE, vedere [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="e82e5-127">For more information about using the WHERE statement, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-content-of-the-clustering-mining-model"></a><span data-ttu-id="e82e5-128">Per ottenere la restituzione del contenuto del modello di data mining di clustering</span><span class="sxs-lookup"><span data-stu-id="e82e5-128">To return the content of the clustering mining model</span></span>  
  
1.  <span data-ttu-id="e82e5-129">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="e82e5-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="e82e5-130">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="e82e5-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="e82e5-131">Copiare l'esempio generico di SELECT FROM \<model> . Istruzione CONTENT nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="e82e5-131">Copy the generic example of the SELECT FROM \<model>.CONTENT statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="e82e5-132">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e82e5-132">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="e82e5-133">con:</span><span class="sxs-lookup"><span data-stu-id="e82e5-133">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="e82e5-134">È inoltre possibile sostituire \* con un elenco di tutte le colonne contenute nel set di [righe DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="e82e5-134">You can also replace \* with a list of any of the columns contained within the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
4.  <span data-ttu-id="e82e5-135">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e82e5-135">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="e82e5-136">con:</span><span class="sxs-lookup"><span data-stu-id="e82e5-136">with:</span></span>  
  
    ```  
    [Clustering]  
    ```  
  
     <span data-ttu-id="e82e5-137">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e82e5-137">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT * FROM [Clustering].CONTENT  
    ```  
  
5.  <span data-ttu-id="e82e5-138">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="e82e5-138">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="e82e5-139">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `SELECT_CONTENT.dmx` .</span><span class="sxs-lookup"><span data-stu-id="e82e5-139">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_CONTENT.dmx`.</span></span>  
  
7.  <span data-ttu-id="e82e5-140">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="e82e5-140">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="e82e5-141">La query restituisce il contenuto del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="e82e5-141">The query returns the content of the mining model.</span></span>  
  
## <a name="use-drillthrough"></a><span data-ttu-id="e82e5-142">Utilizzo del drill-through</span><span class="sxs-lookup"><span data-stu-id="e82e5-142">Use Drillthrough</span></span>  
 <span data-ttu-id="e82e5-143">Il passaggio successivo consiste nell'utilizzo dell'istruzione di drill-through per ottenere un campionamento dei case utilizzati per il training del modello di data mining dell'albero delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="e82e5-143">The next step is to use the drillthrough statement to return a sampling of the cases that were used to train the decision tree mining model.</span></span> <span data-ttu-id="e82e5-144">In questa lezione si utilizzerà il [modello di &#60;di selezione da&#62;. Case &#40;istruzione DMX&#41;](/sql/dmx/select-from-model-content-dmx) per restituire il contenuto del modello di albero delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="e82e5-144">In this lesson, you use the [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) statement to return the contents of the decision tree model.</span></span>  
  
 <span data-ttu-id="e82e5-145">Di seguito è riportato un esempio generico di SELECT FROM \<model> . Istruzione CASEs:</span><span class="sxs-lookup"><span data-stu-id="e82e5-145">The following is a generic example of the SELECT FROM \<model>.CASES statement:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model>].CASES  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="e82e5-146">La prima riga del codice definisce le colonne da restituire dall'origine dei dati, nonché il modello di data mining in cui sono contenute:</span><span class="sxs-lookup"><span data-stu-id="e82e5-146">The first line of the code defines the columns to return from the source data, and the mining model they are contained within:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CASES  
```  
  
 <span data-ttu-id="e82e5-147">La clausola .CASES specifica l'esecuzione di una query drill-through.</span><span class="sxs-lookup"><span data-stu-id="e82e5-147">The .CASES clause specifies that you are performing a drillthrough query.</span></span> <span data-ttu-id="e82e5-148">Per utilizzare il drill-through è necessario che venga attivato durante la creazione del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="e82e5-148">In order to use drillthrough you must enable drillthrough when you create the mining model.</span></span>  
  
 <span data-ttu-id="e82e5-149">L'ultima riga del codice è facoltativa e specifica il nodo nel modello di data mining da cui si desidera ottenere i case:</span><span class="sxs-lookup"><span data-stu-id="e82e5-149">The final line of the code is optional and specifies the node in the mining model that you are requesting cases from:</span></span>  
  
```  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="e82e5-150">Per ulteriori informazioni sull'utilizzo dell'istruzione WHERE con IsInNode, vedere [SELECT FROM &#60;model&#62;. CASI &#40;&#41;DMX ](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="e82e5-150">For more information about using the WHERE statement with IsInNode, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
#### <a name="to-return-the-cases-that-were-used-to-train-the-mining-model"></a><span data-ttu-id="e82e5-151">Per ottenere la restituzione dei case utilizzati per il training del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="e82e5-151">To return the cases that were used to train the mining model</span></span>  
  
1.  <span data-ttu-id="e82e5-152">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="e82e5-152">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="e82e5-153">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="e82e5-153">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="e82e5-154">Copiare l'esempio generico di SELECT FROM \<model> . Istruzione CASEs nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="e82e5-154">Copy the generic example of the SELECT FROM \<model>.CASES statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="e82e5-155">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e82e5-155">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="e82e5-156">con:</span><span class="sxs-lookup"><span data-stu-id="e82e5-156">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="e82e5-157">È inoltre possibile sostituire \* con un elenco di colonne contenute nell'origine dei dati, ad esempio [Bike Buyer]</span><span class="sxs-lookup"><span data-stu-id="e82e5-157">You can also replace \* with a list of any of the columns contained within the source data (such as [Bike Buyer]).</span></span>  
  
4.  <span data-ttu-id="e82e5-158">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e82e5-158">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="e82e5-159">con:</span><span class="sxs-lookup"><span data-stu-id="e82e5-159">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="e82e5-160">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e82e5-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT *   
    FROM [Decision Tree].CASES  
    ```  
  
5.  <span data-ttu-id="e82e5-161">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="e82e5-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="e82e5-162">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `SELECT_DRILLTHROUGH.dmx` .</span><span class="sxs-lookup"><span data-stu-id="e82e5-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DRILLTHROUGH.dmx`.</span></span>  
  
7.  <span data-ttu-id="e82e5-163">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="e82e5-163">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="e82e5-164">La query restituisce i dati di origine utilizzati per il training del modello di data mining dell'albero delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="e82e5-164">The query returns the source data that was used to train the decision tree mining model.</span></span>  
  
## <a name="return-the-states-of-a-discrete-mining-model-column"></a><span data-ttu-id="e82e5-165">Restituzione degli stati di una colonna discreta del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="e82e5-165">Return the States of a Discrete Mining Model Column</span></span>  
 <span data-ttu-id="e82e5-166">Il passaggio successivo consiste nell'utilizzo dell'istruzione SELECT DISTINCT per ottenere i vari stati possibili nella colonna specificata del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="e82e5-166">The next step is to use the SELECT DISTINCT statement to return the different possible states in the specified mining model column.</span></span>  
  
 <span data-ttu-id="e82e5-167">Di seguito è riportato un esempio generico dell'istruzione SELECT DISTINCT:</span><span class="sxs-lookup"><span data-stu-id="e82e5-167">The following is a generic example of the SELECT DISTINCT statement:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
FROM [<mining model>]  
```  
  
 <span data-ttu-id="e82e5-168">La prima riga del codice definisce le colonne del modello di data mining per cui vengono restituiti gli stati:</span><span class="sxs-lookup"><span data-stu-id="e82e5-168">The first line of the code defines the mining model columns for which the states are returned:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
```  
  
 <span data-ttu-id="e82e5-169">È necessario includere DISTINCT affinché vengano restituiti tutti gli stati della colonna.</span><span class="sxs-lookup"><span data-stu-id="e82e5-169">You must include DISTINCT in order to return all of the states of the column.</span></span> <span data-ttu-id="e82e5-170">Se si esclude DISTINCT, l'istruzione completa diventa una forma abbreviata di una stima e restituisce lo stato più probabile della colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="e82e5-170">If you exclude DISTINCT, then the full statement becomes a shortcut for a prediction and returns the most likely state of the specified column.</span></span> <span data-ttu-id="e82e5-171">Per altre informazioni, vedere [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="e82e5-171">For more information, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-states-of-a-discrete-column"></a><span data-ttu-id="e82e5-172">Per ottenere la restituzione degli stati di una colonna discreta</span><span class="sxs-lookup"><span data-stu-id="e82e5-172">To return the states of a discrete column</span></span>  
  
1.  <span data-ttu-id="e82e5-173">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="e82e5-173">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="e82e5-174">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="e82e5-174">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="e82e5-175">Copiare l'esempio generico dell'istruzione SELECT DISTINCT nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="e82e5-175">Copy the generic example of the SELECT Distinct statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="e82e5-176">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e82e5-176">Replace the following:</span></span>  
  
    ```  
    [<column,name>   
    ```  
  
     <span data-ttu-id="e82e5-177">con:</span><span class="sxs-lookup"><span data-stu-id="e82e5-177">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="e82e5-178">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e82e5-178">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="e82e5-179">con:</span><span class="sxs-lookup"><span data-stu-id="e82e5-179">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="e82e5-180">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e82e5-180">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT DISTINCT [Bike Buyer]   
    FROM [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="e82e5-181">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="e82e5-181">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="e82e5-182">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `SELECT_DISCRETE.dmx` .</span><span class="sxs-lookup"><span data-stu-id="e82e5-182">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DISCRETE.dmx`.</span></span>  
  
7.  <span data-ttu-id="e82e5-183">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="e82e5-183">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="e82e5-184">La query restituisce gli stati possibili della colonna Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="e82e5-184">The query returns the possible states of the Bike Buyer column.</span></span>  
  
 <span data-ttu-id="e82e5-185">Nella lezione successiva verrà utilizzato il modello di data mining dell'albero delle decisioni per stimare se i clienti potenziali diventeranno acquirenti di biciclette.</span><span class="sxs-lookup"><span data-stu-id="e82e5-185">In the next lesson, you will predict whether potential customers will be bike buyers by using the decision tree mining model.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="e82e5-186">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="e82e5-186">Next Lesson</span></span>  
 [<span data-ttu-id="e82e5-187">Lezione 5: Esecuzione di query di stima</span><span class="sxs-lookup"><span data-stu-id="e82e5-187">Lesson 5: Executing Prediction Queries</span></span>](../../2014/tutorials/lesson-5-executing-prediction-queries.md)  
  
  
