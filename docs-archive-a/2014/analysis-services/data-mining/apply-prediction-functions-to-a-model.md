---
title: Applicare funzioni di stima a un modello | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Model Prediction [Analysis Services], selecting mining models
ms.assetid: cf9a97e2-c249-441b-af12-c977c1a91c44
author: minewiskan
ms.author: owend
ms.openlocfilehash: fde9de00adaa1712a9db6e18aabc6a83dd660efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624436"
---
# <a name="apply-prediction-functions-to-a-model"></a><span data-ttu-id="b17b2-102">Applicare le funzioni di stima a un modello</span><span class="sxs-lookup"><span data-stu-id="b17b2-102">Apply Prediction Functions to a Model</span></span>
  <span data-ttu-id="b17b2-103">Per creare una query di stima, è innanzitutto necessario selezionare il modello di data mining su cui basare la query.</span><span class="sxs-lookup"><span data-stu-id="b17b2-103">To create a prediction query, you must first select the mining model on which the query will be based.</span></span> <span data-ttu-id="b17b2-104">È possibile selezionare qualsiasi modello di data mining esistente nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="b17b2-104">You can select any mining model that exists in the current project.</span></span>  
  
 <span data-ttu-id="b17b2-105">Dopo avere selezionato un modello, aggiungere una *funzione di stima* alla query.</span><span class="sxs-lookup"><span data-stu-id="b17b2-105">After you have selected a model, add a *prediction function* to the query.</span></span> <span data-ttu-id="b17b2-106">Si tratta di un'importazione per comprendere che le funzioni di stima vengono utilizzate per molti scopi: Sì, è possibile stimare i valori, ma è anche possibile ottenere le statistiche correlate, nonché le informazioni utilizzate per generare la stima.</span><span class="sxs-lookup"><span data-stu-id="b17b2-106">It is import to understand that prediction functions are used for many purposes-yes, you can predict values, but you can also get related statistics, as well as information that was used in generating the prediction.</span></span> <span data-ttu-id="b17b2-107">Le funzioni di stima possono restituire i tipi seguenti di valori:</span><span class="sxs-lookup"><span data-stu-id="b17b2-107">Prediction functions can return the following types of values:</span></span>  
  
-   <span data-ttu-id="b17b2-108">Nome dell'attributo di stima e valore che viene stimato.</span><span class="sxs-lookup"><span data-stu-id="b17b2-108">The name of the predictable attribute, and the value that is predicted.</span></span>  
  
-   <span data-ttu-id="b17b2-109">Statistiche sulla distribuzione e varianza dei valori stimati.</span><span class="sxs-lookup"><span data-stu-id="b17b2-109">Statistics about the distribution and variance of the predicted values.</span></span>  
  
-   <span data-ttu-id="b17b2-110">Probabilità di un risultato specificato o di tutti i possibili risultati.</span><span class="sxs-lookup"><span data-stu-id="b17b2-110">The probability of a specified outcome, or of all possible outcomes.</span></span>  
  
-   <span data-ttu-id="b17b2-111">Punteggi superiori o inferiori o valori.</span><span class="sxs-lookup"><span data-stu-id="b17b2-111">The top or bottom scores or values.</span></span>  
  
-   <span data-ttu-id="b17b2-112">Valori associati a un nodo, un oggetto o un attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="b17b2-112">Values associated with a specified node, object, or attribute.</span></span>  
  
 <span data-ttu-id="b17b2-113">È disponibile un'ampia varietà di funzioni di stima che è possibile utilizzare, tuttavia è necessario scegliere la funzione che indica il tipo di modello creato.</span><span class="sxs-lookup"><span data-stu-id="b17b2-113">There is a wide variety of prediction functions that you can use, but you must choose the function that suits the type of model you created.</span></span> <span data-ttu-id="b17b2-114">In genere questa scelta dipende dall'algoritmo utilizzato per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="b17b2-114">Usually this choice depends on the algorithm used to create the model.</span></span>  
  
-   <span data-ttu-id="b17b2-115">Per un elenco delle funzioni di stima supportate per quasi tutti i tipi di modello, vedere [Funzioni di stima generali &#40;DMX&#41;](/sql/dmx/general-prediction-functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="b17b2-115">For a list of the prediction functions that are supported for almost all model types, see [General Prediction Functions &#40;DMX&#41;](/sql/dmx/general-prediction-functions-dmx).</span></span>  
  
-   <span data-ttu-id="b17b2-116">I singoli algoritmi supportano inoltre una varietà di funzioni specializzate.</span><span class="sxs-lookup"><span data-stu-id="b17b2-116">Additionally, individual algorithms support a variety of specialized functions.</span></span> <span data-ttu-id="b17b2-117">Ad esempio, se si crea un modello di data mining basato sull'algoritmo Microsoft Clustering, è possibile utilizzare funzioni di stima specializzate per trovare informazioni sui cluster, ad esempio la distanza da un valore di dati al centro del cluster.</span><span class="sxs-lookup"><span data-stu-id="b17b2-117">For example, if you create a mining model based on the Microsoft Clustering algorithm, you can use specialized prediction functions to find information about the clusters, such as the distance from a data value to the cluster centroid.</span></span>  
  
     <span data-ttu-id="b17b2-118">Per alcuni esempi di come eseguire una query su un tipo specifico di modello di data mining, vedere l'argomento di riferimento sugli algoritmi in [Algoritmi di data mining &#40;Analysis Services - Data mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="b17b2-118">For examples of how to query a specific type of mining model, see the algorithm reference topic, in [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="choose-a-mining-model-to-use-for-prediction"></a><span data-ttu-id="b17b2-119">Scegliere un modello di data mining da utilizzare per la stima</span><span class="sxs-lookup"><span data-stu-id="b17b2-119">Choose a mining model to use for prediction</span></span>  
  
1.  <span data-ttu-id="b17b2-120">Da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic con il pulsante destro del mouse sul modello e scegliere **Compila query di stima**.</span><span class="sxs-lookup"><span data-stu-id="b17b2-120">From [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the model, and select **Build Prediction Query**.</span></span>  
  
     <span data-ttu-id="b17b2-121">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b17b2-121">--OR --</span></span>  
  
     <span data-ttu-id="b17b2-122">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare clic sulla scheda **Stima modello di data mining**e quindi scegliere **Seleziona modello** nella tabella  **Modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="b17b2-122">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the tab, **Mining Model Prediction**, and then click **Select Model** in the  **Mining Model** table.</span></span>  
  
2.  <span data-ttu-id="b17b2-123">Nella finestra di dialogo **Seleziona modello di data mining** selezionare un modello di data mining e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b17b2-123">In the **Select Mining Model** dialog box, select a mining model, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b17b2-124">È possibile scegliere qualsiasi modello all'interno del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] corrente.</span><span class="sxs-lookup"><span data-stu-id="b17b2-124">You can choose any model within the current [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="b17b2-125">Per creare una query utilizzando un modello in un database diverso, è necessario aprire una nuova finestra Query nel contesto di quel database oppure aprire il file della soluzione che contiene tale modello.</span><span class="sxs-lookup"><span data-stu-id="b17b2-125">To create a query using a model in a different database, you must either open a new query window in the context of that database, or open the solution file that contains that model.</span></span>  
  
### <a name="add-prediction-functions-to-a-query"></a><span data-ttu-id="b17b2-126">Aggiungere funzioni di stima a una query</span><span class="sxs-lookup"><span data-stu-id="b17b2-126">Add prediction functions to a query</span></span>  
  
1.  <span data-ttu-id="b17b2-127">In **Generatore delle query di stima**configurare i dati di input usati per la stima, specificando i valori nella finestra di dialogo **Input query singleton** o eseguendo il mapping del modello a un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="b17b2-127">In the **Prediction Query Builder**, configure the input data used for prediction, either by providing values in the **Singleton Query Input** dialog box, or by mapping the model to an external data source.</span></span>  
  
     <span data-ttu-id="b17b2-128">Per altre informazioni, vedere [Scegliere ed eseguire il mapping di dati di input per una query di stima](choose-and-map-input-data-for-a-prediction-query.md).</span><span class="sxs-lookup"><span data-stu-id="b17b2-128">For more information, see [Choose and Map Input Data for a Prediction Query](choose-and-map-input-data-for-a-prediction-query.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="b17b2-129">Non è necessario fornire input per generare stime.</span><span class="sxs-lookup"><span data-stu-id="b17b2-129">It is not required that you provide inputs to generate predictions.</span></span> <span data-ttu-id="b17b2-130">In assenza di input, l'algoritmo restituisce in genere il valore stimato più probabile attraverso tutti i possibili input.</span><span class="sxs-lookup"><span data-stu-id="b17b2-130">When there is no input, the algorithm will typically return the mostly likely predicted value across all possible inputs.</span></span>  
  
2.  <span data-ttu-id="b17b2-131">Fare clic sulla colonna **Origine** e scegliere un valore nell'elenco:</span><span class="sxs-lookup"><span data-stu-id="b17b2-131">Click the **Source** column, and choose a value from the list:</span></span>  
  
    |||  
    |-|-|  
    |**\<model name>**|<span data-ttu-id="b17b2-132">Selezionare questa opzione per includere i valori del modello di data mining nell'output.</span><span class="sxs-lookup"><span data-stu-id="b17b2-132">Select this option to include values from the mining model in the output.</span></span> <span data-ttu-id="b17b2-133">È possibile aggiungere unicamente colonne stimabili.</span><span class="sxs-lookup"><span data-stu-id="b17b2-133">You can only add predictable columns.</span></span><br /><br /> <span data-ttu-id="b17b2-134">Quando si aggiunge una colonna dal modello, il risultato restituito è l'elenco non distinto di valori in quella colonna.</span><span class="sxs-lookup"><span data-stu-id="b17b2-134">When you add a column from the model, the result returned is the non-distinct list of values in that column.</span></span><br /><br /> <span data-ttu-id="b17b2-135">Le colonne che si aggiungono tramite questa opzione sono incluse nella parte SELECT dell'istruzione DMX risultante.</span><span class="sxs-lookup"><span data-stu-id="b17b2-135">The columns that you add with this option are included in the SELECT portion of the resulting DMX statement.</span></span>|  
    |<span data-ttu-id="b17b2-136">**Prediction Function**</span><span class="sxs-lookup"><span data-stu-id="b17b2-136">**Prediction Function**</span></span>|<span data-ttu-id="b17b2-137">Selezionare questa opzione per esplorare un elenco di funzioni di stima.</span><span class="sxs-lookup"><span data-stu-id="b17b2-137">Select this option to browse a list of prediction functions.</span></span><br /><br /> <span data-ttu-id="b17b2-138">I valori o le funzioni selezionate vengono aggiunte alla parte SELECT dell'istruzione DMX risultante.</span><span class="sxs-lookup"><span data-stu-id="b17b2-138">The values or functions you select are added to the SELECT portion of the resulting DMX statement.</span></span><br /><br /> <span data-ttu-id="b17b2-139">L'elenco di funzioni di stima non è filtrato o vincolato dal tipo di modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="b17b2-139">The list of prediction functions is not filtered or constrained by the type of model you have selected.</span></span> <span data-ttu-id="b17b2-140">Pertanto, se non si sa con sicurezza se la funzione è supportata per il tipo di modello corrente, è possibile aggiungerla all'elenco e assicurarsi che non si verifichi alcun errore.</span><span class="sxs-lookup"><span data-stu-id="b17b2-140">Therefore, if you have any doubt about whether the function is supported for the current model type, you can just add the function to the list and see if there is an error.</span></span><br /><br /> <span data-ttu-id="b17b2-141">Gli elementi dell'elenco preceduti da $ (AdjustedProbability $) rappresentano le colonne della tabella nidificata che viene restituita quando si utilizza la funzione, `PredictHistogram`.</span><span class="sxs-lookup"><span data-stu-id="b17b2-141">List items that are preceded by $ (such as $AdjustedProbability) represent columns from the nested table that is output when you use the function, `PredictHistogram`.</span></span> <span data-ttu-id="b17b2-142">Si tratta di collegamenti che è possibile utilizzare per restituire una singola colonna e non una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="b17b2-142">These are shortcuts that you can use to return a single column and not a nested table.</span></span>|  
    |<span data-ttu-id="b17b2-143">**Espressione personalizzata**</span><span class="sxs-lookup"><span data-stu-id="b17b2-143">**Custom Expression**</span></span>|<span data-ttu-id="b17b2-144">Selezionare questa opzione per digitare un'espressione personalizzata e quindi assegnare un alias all'output.</span><span class="sxs-lookup"><span data-stu-id="b17b2-144">Select this option to type a custom expression and then assign an alias to the output.</span></span><br /><br /> <span data-ttu-id="b17b2-145">L'espressione personalizzata viene aggiunta alla parte SELECT della query di stima DMX risultante.</span><span class="sxs-lookup"><span data-stu-id="b17b2-145">The custom expression is added to the SELECT portion of the resulting DMX prediction query.</span></span><br /><br /> <span data-ttu-id="b17b2-146">Questa opzione è utile se si desidera aggiungere del testo per l'output con ogni riga, per chiamare funzioni VB o stored procedure personalizzate.</span><span class="sxs-lookup"><span data-stu-id="b17b2-146">This option is useful if you want to add text for output with each row, to call VB functions, or to call custom stored procedures.</span></span><br /><br /> <span data-ttu-id="b17b2-147">Per informazioni sull'uso di funzioni VBA e di Excel da DMX, vedere [Funzioni VBA in MDX e DAX](/sql/mdx/vba-functions-in-mdx-and-dax).</span><span class="sxs-lookup"><span data-stu-id="b17b2-147">For information about using VBA and Excel functions from DMX, see [VBA functions in MDX and DAX](/sql/mdx/vba-functions-in-mdx-and-dax).</span></span>|  
  
3.  <span data-ttu-id="b17b2-148">Dopo avere aggiunto ogni funzione o espressione, passare alla vista DMX per vedere come la funzione viene aggiunta all'interno dell'istruzione DMX.</span><span class="sxs-lookup"><span data-stu-id="b17b2-148">After adding each function or expression, switch to DMX view to see how the function is added within the DMX statement.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="b17b2-149">Il Generatore delle query di stima non convalida l'istruzione DMX finché non si fa clic su **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="b17b2-149">The Prediction Query Builder does not validate the DMX until you click **Results**.</span></span> <span data-ttu-id="b17b2-150">Spesso, l'espressione che viene prodotta dal generatore di query non è una DMX valida.</span><span class="sxs-lookup"><span data-stu-id="b17b2-150">Often, you will find that the expression that is produced by the query builder is not valid DMX.</span></span> <span data-ttu-id="b17b2-151">Le cause tipiche sono una colonna che non è correlata alla colonna stimabile o il tentativo di stimare una colonna in una tabella nidificata che richiede un'istruzione sub-SELECT.</span><span class="sxs-lookup"><span data-stu-id="b17b2-151">Typical causes are referencing a column that is not related to the predictable column, or trying to predict a column in a nested table, which requires a sub-SELECT statement.</span></span> <span data-ttu-id="b17b2-152">A questo punto, è possibile passare a vista DMX e continuare a modificare l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b17b2-152">At this point, you can switch to DMX view and continue editing the statement.</span></span>  
  
### <a name="example-create-a-query-on-a-clustering-model"></a><span data-ttu-id="b17b2-153">Esempio: creare una query in un modello di clustering</span><span class="sxs-lookup"><span data-stu-id="b17b2-153">Example: Create a query on a clustering model</span></span>  
  
1.  <span data-ttu-id="b17b2-154">Se non è disponibile un modello di clustering per la generazione di questa query di esempio, creare il modello [TM_Clustering] facendo riferimento a [Esercitazione di base sul data mining](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b17b2-154">If you do not have a clustering model available for building this sample query, create the model, [TM_Clustering], using the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span>  
  
2.  <span data-ttu-id="b17b2-155">Da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic con il pulsante destro del mouse sul modello [TM_Clustering] e scegliere **Compila query di stima**.</span><span class="sxs-lookup"><span data-stu-id="b17b2-155">From [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the model, [TM_Clustering], and select **Build Prediction Query**.</span></span>  
  
3.  <span data-ttu-id="b17b2-156">Scegliere **Query singleton** dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="b17b2-156">From the **Mining Model** menu, select **Singleton Query**.</span></span>  
  
4.  <span data-ttu-id="b17b2-157">Nella finestra di dialogo **Input query singleton** impostare i valori seguenti come input:</span><span class="sxs-lookup"><span data-stu-id="b17b2-157">In the **Singleton Query Input** dialog box, set the following values as inputs:</span></span>  
  
    -   <span data-ttu-id="b17b2-158">Gender = M</span><span class="sxs-lookup"><span data-stu-id="b17b2-158">Gender = M</span></span>  
  
    -   <span data-ttu-id="b17b2-159">Commute Distance = 5-10 miles</span><span class="sxs-lookup"><span data-stu-id="b17b2-159">Commute Distance = 5-10 miles</span></span>  
  
5.  <span data-ttu-id="b17b2-160">Nella griglia della query per **Origine**selezionare il modello di data mining TM_Clustering e aggiungere la colonna [Bike Buyer].</span><span class="sxs-lookup"><span data-stu-id="b17b2-160">In the query grid, for **Source**, select TM_Clustering mining model, and add the column, [Bike Buyer].</span></span>  
  
6.  <span data-ttu-id="b17b2-161">Per **origine**, selezionare **funzione di stima**e aggiungere la funzione, `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="b17b2-161">For **Source**, select **Prediction Function**, and add the function, `Cluster`.</span></span>  
  
7.  <span data-ttu-id="b17b2-162">Per **origine**selezionare **funzione di stima**, aggiungere la funzione, `PredictSupport` e trascinare la colonna del modello [Bike Buyer] nella casella **criteri/argomento** .</span><span class="sxs-lookup"><span data-stu-id="b17b2-162">For **Source**, select **Prediction Function**, add the function, `PredictSupport`, and drag the model column [Bike Buyer] into the **Criteria/Argument** box.</span></span> <span data-ttu-id="b17b2-163">Digitare **Supporto** nella colonna **Alias** .</span><span class="sxs-lookup"><span data-stu-id="b17b2-163">Type **Support** in the **Alias** column.</span></span>  
  
     <span data-ttu-id="b17b2-164">Copiare l'espressione che rappresenta la funzione di stima e il riferimento alla colonna dalla casella **Criteri/Argomento** .</span><span class="sxs-lookup"><span data-stu-id="b17b2-164">Copy the expression representing the prediction function and column reference from the **Criteria/Argument** box.</span></span>  
  
8.  <span data-ttu-id="b17b2-165">Per **Origine**selezionare **Espressione personalizzata**, digitare un alias e quindi fare riferimento alla funzione CEILING di Excel usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b17b2-165">For **Source**, select **Custom Expression**, type an alias, and then reference the Excel CEILING function by using the following syntax:</span></span>  
  
    ```  
    Excel![CEILING](<arguments) as <return type>  
    ```  
  
     <span data-ttu-id="b17b2-166">Incollare il riferimento alla colonna come argomento alla funzione.</span><span class="sxs-lookup"><span data-stu-id="b17b2-166">Paste the column reference in as the argument to the function.</span></span>  
  
     <span data-ttu-id="b17b2-167">Ad esempio, l'espressione seguente restituisce il valore CEILING del valore di supporto:</span><span class="sxs-lookup"><span data-stu-id="b17b2-167">For example, the following expression returns the CEILING of the support value:</span></span>  
  
    ```  
    EXCEL!CEILING(PredictSupport([TM_Clustering].[Bike Buyer]),2)  
    ```  
  
     <span data-ttu-id="b17b2-168">Digitare CEILING nella colonna **Alias** .</span><span class="sxs-lookup"><span data-stu-id="b17b2-168">Type CEILING in the **Alias** column.</span></span>  
  
9. <span data-ttu-id="b17b2-169">Fare clic su **Passa alla visualizzazione del testo della query** per esaminare l'istruzione DMX generata e quindi fare clic su **Passa alla visualizzazione dei risultati della query** per visualizzare l'output delle colonne restituito dalla query di stima.</span><span class="sxs-lookup"><span data-stu-id="b17b2-169">Click **Switch to query text view** to review the DMX statement that was generated, and then click **Switch to query result view** to see the columns output by the prediction query.</span></span>  
  
     <span data-ttu-id="b17b2-170">Nella tabella seguente vengono illustrati i risultati previsti:</span><span class="sxs-lookup"><span data-stu-id="b17b2-170">The following table shows the expected results:</span></span>  
  
    |<span data-ttu-id="b17b2-171">Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="b17b2-171">Bike Buyer</span></span>|<span data-ttu-id="b17b2-172">$Cluster</span><span class="sxs-lookup"><span data-stu-id="b17b2-172">$Cluster</span></span>|<span data-ttu-id="b17b2-173">SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b17b2-173">SUPPORT</span></span>|<span data-ttu-id="b17b2-174">CEILING</span><span class="sxs-lookup"><span data-stu-id="b17b2-174">CEILING</span></span>|  
    |----------------|--------------|-------------|-------------|  
    |<span data-ttu-id="b17b2-175">0</span><span class="sxs-lookup"><span data-stu-id="b17b2-175">0</span></span>|<span data-ttu-id="b17b2-176">Cluster 8</span><span class="sxs-lookup"><span data-stu-id="b17b2-176">Cluster 8</span></span>|<span data-ttu-id="b17b2-177">954</span><span class="sxs-lookup"><span data-stu-id="b17b2-177">954</span></span>|<span data-ttu-id="b17b2-178">953.948638926372</span><span class="sxs-lookup"><span data-stu-id="b17b2-178">953.948638926372</span></span>|  
  
 <span data-ttu-id="b17b2-179">Se si desidera aggiungere altre clausole altrove nell'istruzione, ad esempio se si desidera aggiungere una clausola WHERE, non è possibile aggiungerla utilizzando la griglia; per prima cosa, è necessario passare alla visualizzazione DMX.</span><span class="sxs-lookup"><span data-stu-id="b17b2-179">If you want to add other clauses elsewhere in the statement-for example, if you want to add a WHERE clause-you cannot add it by using the grid; you must switch to DMX view first.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17b2-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b17b2-180">See Also</span></span>  
 [<span data-ttu-id="b17b2-181">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="b17b2-181">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
