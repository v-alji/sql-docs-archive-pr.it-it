---
title: 'Lezione 2: aggiunta di modelli di data mining alla struttura di data mining Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 03fe44c5-6452-4ed0-95f6-9682670c0f52
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: de65fb7a85154f607cd8f266faec4621cdc41476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717106"
---
# <a name="lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure"></a><span data-ttu-id="78f18-102">Lezione 2: Aggiunta di modelli di data mining alla struttura di data mining Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="78f18-102">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="78f18-103">In questa lezione vengono aggiunti due modelli di data mining alla struttura di data mining Bike Buyer creata nella [lezione 1: creazione della struttura di data mining Bike Buyer](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="78f18-103">In this lesson, you will add two mining models to the Bike Buyer mining structure that you created [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span></span> <span data-ttu-id="78f18-104">Uno di questi modelli consentirà di esplorare i dati e l'altro di creare stime.</span><span class="sxs-lookup"><span data-stu-id="78f18-104">These mining models will allow you to explore the data using one model, and to create predictions using another.</span></span>  
  
 <span data-ttu-id="78f18-105">Per esplorare il modo in cui i clienti potenziali possono essere classificati in base alle relative caratteristiche, verrà creato un modello di data mining basato sull' [algoritmo Microsoft Clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="78f18-105">To explore how potential customers can be categorized by their characteristics, you will create a mining model based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span> <span data-ttu-id="78f18-106">In una lezione successiva verrà esaminato il modo in cui questo algoritmo individua cluster di clienti che condividono caratteristiche simili.</span><span class="sxs-lookup"><span data-stu-id="78f18-106">In a later lesson, you will explore how this algorithm finds clusters of customers who share similar characteristics.</span></span> <span data-ttu-id="78f18-107">È possibile riscontrare, ad esempio, che determinati clienti tendono a vivere nelle stesse aree, a usare la bicicletta per recarsi al lavoro e ad avere una formazione scolastica analoga.</span><span class="sxs-lookup"><span data-stu-id="78f18-107">For example, you might find that certain customers tend to live close to each other, commute by bicycle, and have similar education backgrounds.</span></span> <span data-ttu-id="78f18-108">Questi cluster possono essere utilizzati per comprendere più a fondo la correlazione tra vari clienti e queste informazioni possono essere utilizzate come base per una strategia di marketing rivolta a un particolare segmento di clientela.</span><span class="sxs-lookup"><span data-stu-id="78f18-108">You can use these clusters to better understand how different customers are related, and to use the information to create a marketing strategy that targets specific customers.</span></span>  
  
 <span data-ttu-id="78f18-109">Per prevedere se è probabile che un potenziale cliente acquisti una bicicletta, si creerà un modello di data mining basato sull' [algoritmo Microsoft Decision Trees](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="78f18-109">To predict whether a potential customer is likely to buy a bicycle, you will create a mining model based on the [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="78f18-110">Questo algoritmo esamina le informazioni associate a ogni potenziale cliente e individua le caratteristiche utili per stimare se acquisterà una bicicletta,</span><span class="sxs-lookup"><span data-stu-id="78f18-110">This algorithm looks through the information that is associated with each potential customer, and finds characteristics that are useful in predicting if they will buy a bicycle.</span></span> <span data-ttu-id="78f18-111">quindi confronta i valori delle caratteristiche dei precedenti acquirenti di biciclette con quelli dei nuovi potenziali clienti per stabilire se è probabile che questi ultimi acquistino una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="78f18-111">It then compares the values of the characteristics of previous bike buyers against new potential customers to determine whether the new potential customers are likely to buy a bicycle.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="78f18-112">Istruzione ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="78f18-112">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="78f18-113">Per aggiungere un modello di data mining alla struttura di data mining, è possibile utilizzare l'istruzione [ALTER mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="78f18-113">In order to add a mining model to the mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="78f18-114">Il codice nell'istruzione può essere suddiviso nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="78f18-114">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="78f18-115">Identificazione della struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="78f18-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="78f18-116">Denominazione del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="78f18-116">Naming the mining model</span></span>  
  
-   <span data-ttu-id="78f18-117">Definizione della colonna chiave</span><span class="sxs-lookup"><span data-stu-id="78f18-117">Defining the key column</span></span>  
  
-   <span data-ttu-id="78f18-118">Definizione della colonna di input e della colonna stimabile</span><span class="sxs-lookup"><span data-stu-id="78f18-118">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="78f18-119">Identificazione delle modifiche a livello di algoritmo e parametri</span><span class="sxs-lookup"><span data-stu-id="78f18-119">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="78f18-120">Di seguito è riportato un esempio generico dell'istruzione ALTER MINING MODEL:</span><span class="sxs-lookup"><span data-stu-id="78f18-120">The following is a generic example of the ALTER MINING MODEL statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
(  
    [<key column>],  
    <mining model columns>,  
) USING <algorithm name>( <algorithm parameters> )  
WITH FILTER (<expression>)  
```  
  
 <span data-ttu-id="78f18-121">La prima riga del codice identifica la struttura di data mining esistente a cui verranno aggiunti i modelli di data mining:</span><span class="sxs-lookup"><span data-stu-id="78f18-121">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="78f18-122">La riga successiva del codice indica il nome del modello di data mining che verrà aggiunto alla struttura di data mining:</span><span class="sxs-lookup"><span data-stu-id="78f18-122">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="78f18-123">Per informazioni sulla denominazione di un oggetto in DMX, vedere [identificatori &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="78f18-123">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="78f18-124">Le successive righe del codice definiscono le colonne della struttura di data mining che verranno utilizzate dal modello di data mining:</span><span class="sxs-lookup"><span data-stu-id="78f18-124">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns>  
```  
  
 <span data-ttu-id="78f18-125">È possibile utilizzare solo colonne già esistenti nella struttura di data mining e la prima colonna nell'elenco deve essere la colonna chiave dalla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="78f18-125">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="78f18-126">La riga successiva del codice definisce l'algoritmo di data mining che genera il modello di data mining e i parametri che è possibile impostare nell'algoritmo:</span><span class="sxs-lookup"><span data-stu-id="78f18-126">The next line of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm:</span></span>  
  
```  
) USING <algorithm name>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="78f18-127">Per ulteriori informazioni sui parametri dell'algoritmo che è possibile modificare, vedere algoritmo [Microsoft Decision Trees](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) e [algoritmo Microsoft Clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="78f18-127">For more information about the algorithm parameters that you can adjust, see [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) and [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span>  
  
 <span data-ttu-id="78f18-128">Per specificare che una colonna nel modello di data mining deve essere utilizzata per la stima, è possibile utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="78f18-128">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
 <span data-ttu-id="78f18-129">L'ultima riga del codice, che è facoltativa, definisce un filtro che viene applicato durante il training e il test del modello.</span><span class="sxs-lookup"><span data-stu-id="78f18-129">The final line of the code, which is optional, defines a filter that is applied when training and testing the model.</span></span> <span data-ttu-id="78f18-130">Per ulteriori informazioni sull'applicazione di filtri ai modelli di data mining, vedere [filtri per i modelli di data mining &#40;Analysis Services-&#41;di data mining ](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="78f18-130">For more information about how to apply filters to mining models, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="78f18-131">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="78f18-131">Lesson Tasks</span></span>  
 <span data-ttu-id="78f18-132">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="78f18-132">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="78f18-133">Aggiunta di un modello di data mining dell'albero delle decisioni alla struttura Bike Buyer mediante l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees</span><span class="sxs-lookup"><span data-stu-id="78f18-133">Add a decision tree mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm</span></span>  
  
-   <span data-ttu-id="78f18-134">Aggiunta di un modello di data mining di clustering alla struttura Bike Buyer mediante l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering</span><span class="sxs-lookup"><span data-stu-id="78f18-134">Add a clustering mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm</span></span>  
  
-   <span data-ttu-id="78f18-135">Poiché si desidera visualizzare i risultati per tutti i casi, non verrà ancora aggiunto un filtro ai modelli.</span><span class="sxs-lookup"><span data-stu-id="78f18-135">Because you want to see results for all cases, you will not yet add a filter to either model.</span></span>  
  
## <a name="adding-a-decision-tree-mining-model-to-the-structure"></a><span data-ttu-id="78f18-136">Aggiunta di un modello di data mining dell'albero delle decisioni alla struttura</span><span class="sxs-lookup"><span data-stu-id="78f18-136">Adding a Decision Tree Mining Model to the Structure</span></span>  
 <span data-ttu-id="78f18-137">Il primo passaggio consiste nell'aggiunta di un modello di data mining basato sull'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="78f18-137">The first step is to add a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
#### <a name="to-add-a-decision-tree-mining-model"></a><span data-ttu-id="78f18-138">Per aggiungere un modello di data mining dell'albero delle decisioni</span><span class="sxs-lookup"><span data-stu-id="78f18-138">To add a decision tree mining model</span></span>  
  
1.  <span data-ttu-id="78f18-139">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX** per aprire l'editor di query e una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="78f18-139">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="78f18-140">Copiare l'esempio generico dell'istruzione ALTER MINING STRUCTURE nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="78f18-140">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="78f18-141">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78f18-141">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="78f18-142">con:</span><span class="sxs-lookup"><span data-stu-id="78f18-142">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="78f18-143">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78f18-143">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="78f18-144">con:</span><span class="sxs-lookup"><span data-stu-id="78f18-144">with:</span></span>  
  
    ```  
    Decision Tree  
    ```  
  
5.  <span data-ttu-id="78f18-145">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78f18-145">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    ```  
  
     <span data-ttu-id="78f18-146">con:</span><span class="sxs-lookup"><span data-stu-id="78f18-146">with:</span></span>  
  
    ```  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ```  
  
     <span data-ttu-id="78f18-147">In questo caso, la colonna `[Bike Buyer]` è stata designata come colonna PREDICT.</span><span class="sxs-lookup"><span data-stu-id="78f18-147">In this case, the `[Bike Buyer]` column has been designated as the PREDICT column.</span></span>  
  
6.  <span data-ttu-id="78f18-148">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78f18-148">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )   
    ```  
  
     <span data-ttu-id="78f18-149">con:</span><span class="sxs-lookup"><span data-stu-id="78f18-149">with:</span></span>  
  
    ```  
    Using Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="78f18-150">L'istruzione WITH DRILLTHROUGH consente di esplorare i case utilizzati per compilare il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="78f18-150">The WITH DRILLTHROUGH statement allows you to explore the cases that were used to build the mining model.</span></span>  
  
     <span data-ttu-id="78f18-151">L'istruzione risultante dovrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="78f18-151">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Decision Tree]  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ) USING Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
7.  <span data-ttu-id="78f18-152">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="78f18-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="78f18-153">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `DT_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="78f18-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `DT_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="78f18-154">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="78f18-154">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-a-clustering-mining-model-to-the-structure"></a><span data-ttu-id="78f18-155">Aggiunta di un modello di data mining di clustering alla struttura</span><span class="sxs-lookup"><span data-stu-id="78f18-155">Adding a Clustering Mining Model to the Structure</span></span>  
 <span data-ttu-id="78f18-156">A questo punto è possibile aggiungere un modello di data mining alla struttura Bike Buyer mediante l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering.</span><span class="sxs-lookup"><span data-stu-id="78f18-156">You can now add a mining model to the Bike Buyer mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span> <span data-ttu-id="78f18-157">Dato che il modello di data mining di clustering utilizzerà tutte le colonne definite nella struttura di data mining, è possibile utilizzare una procedura abbreviata per aggiungere il modello alla struttura omettendo la definizione delle colonne di data mining.</span><span class="sxs-lookup"><span data-stu-id="78f18-157">Because the clustering mining model will use all the columns defined in the mining structure, you can use a shortcut to add the model to the structure by omitting the definition of the mining columns.</span></span>  
  
#### <a name="to-add-a-clustering-mining-model"></a><span data-ttu-id="78f18-158">Per aggiungere un modello di data mining di clustering</span><span class="sxs-lookup"><span data-stu-id="78f18-158">To add a Clustering mining model</span></span>  
  
1.  <span data-ttu-id="78f18-159">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX** per aprire l'editor di query e una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="78f18-159">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor opens and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="78f18-160">Copiare l'esempio generico dell'istruzione ALTER MINING STRUCTURE nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="78f18-160">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="78f18-161">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78f18-161">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="78f18-162">con:</span><span class="sxs-lookup"><span data-stu-id="78f18-162">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="78f18-163">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78f18-163">Replace the following:</span></span>  
  
    ```  
    <mining model>   
    ```  
  
     <span data-ttu-id="78f18-164">con:</span><span class="sxs-lookup"><span data-stu-id="78f18-164">with:</span></span>  
  
    ```  
    Clustering Model  
    ```  
  
5.  <span data-ttu-id="78f18-165">Eliminare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78f18-165">Delete the following:</span></span>  
  
    ```  
    (  
        [<key column>],  
        <mining model columns>,  
    )  
    ```  
  
6.  <span data-ttu-id="78f18-166">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="78f18-166">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="78f18-167">con:</span><span class="sxs-lookup"><span data-stu-id="78f18-167">with:</span></span>  
  
    ```  
    USING Microsoft_Clustering  
    ```  
  
     <span data-ttu-id="78f18-168">L'istruzione completa dovrebbe risultare analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="78f18-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Clustering]  
    USING Microsoft_Clustering   
    ```  
  
7.  <span data-ttu-id="78f18-169">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="78f18-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="78f18-170">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Clustering_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="78f18-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Clustering_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="78f18-171">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="78f18-171">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="78f18-172">Nella lezione successiva verranno elaborati i modelli e la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="78f18-172">In the next lesson, you will process the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="78f18-173">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="78f18-173">Next Lesson</span></span>  
 [<span data-ttu-id="78f18-174">Lezione 3: Elaborazione della struttura di data mining Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="78f18-174">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-bike-buyer-mining-structure.md)  
  
  
