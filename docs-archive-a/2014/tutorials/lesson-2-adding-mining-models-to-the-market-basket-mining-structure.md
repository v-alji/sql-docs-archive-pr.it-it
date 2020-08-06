---
title: 'Lezione 2: aggiunta di modelli di data mining alla struttura di data mining Market basket | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d96a7a7d-35d7-4b34-abb5-f0822c256253
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b9573d9359983e33cf23533787c26039572710ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717099"
---
# <a name="lesson-2-adding-mining-models-to-the-market-basket-mining-structure"></a><span data-ttu-id="04d31-102">Lezione 2: Aggiunta di modelli di data mining alla struttura di data mining Market Basket</span><span class="sxs-lookup"><span data-stu-id="04d31-102">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>
  <span data-ttu-id="04d31-103">In questa lezione vengono aggiunti due modelli di data mining alla struttura di data mining Market Basket creata nella [lezione 1: creazione della struttura di data mining Market basket](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="04d31-103">In this lesson, you will add two mining models to the Market Basket mining structure that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="04d31-104">Questi modelli di data mining consentiranno di creare stime.</span><span class="sxs-lookup"><span data-stu-id="04d31-104">These mining models will allow you to create predictions.</span></span>  
  
 <span data-ttu-id="04d31-105">Per prevedere i tipi di prodotti che i clienti tendono ad acquistare contemporaneamente, sarà possibile creare due modelli di data mining utilizzando l' [algoritmo Microsoft Association](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) e due valori diversi per il parametro *MINIMUM_PROBABILTY* .</span><span class="sxs-lookup"><span data-stu-id="04d31-105">To predict the types of products that customers tend to purchase at the same time, you will create two mining models using the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) and two different values for the *MINIMUM_PROBABILTY* parameter.</span></span>  
  
 <span data-ttu-id="04d31-106">*MINIMUM_PROBABILTY* è un [!INCLUDE[msCoName](../includes/msconame-md.md)] parametro dell'algoritmo di associazione che consente di determinare il numero di regole che un modello di data mining conterrà specificando la probabilità minima che una regola deve avere.</span><span class="sxs-lookup"><span data-stu-id="04d31-106">*MINIMUM_PROBABILTY* is a [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm parameter that helps to determine the number of rules that a mining model will contain by specifying the minimum probability that a rule must have.</span></span> <span data-ttu-id="04d31-107">Ad esempio, l'impostazione di questo valore su 0,4 specifica che una regola può essere generata solo se la combinazione di prodotti che la regola descrive ha una probabilità di realizzazione di almeno il 40%.</span><span class="sxs-lookup"><span data-stu-id="04d31-107">For example, setting this value to 0.4 specifies that a rule can be generated only if the combination of products that the rule describes has at least a forty percent probability of occurring.</span></span>  
  
 <span data-ttu-id="04d31-108">In una lezione successiva sarà possibile visualizzare l'effetto della modifica del parametro *MINIMUM_PROBABILTY* .</span><span class="sxs-lookup"><span data-stu-id="04d31-108">You will view the effect of changing the *MINIMUM_PROBABILTY* parameter in a later lesson.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="04d31-109">Istruzione ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="04d31-109">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="04d31-110">Per aggiungere un modello di data mining contenente una tabella nidificata a una struttura di data mining, è possibile utilizzare l'istruzione [ALTER mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="04d31-110">To add a mining model that contains a nested table to a mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="04d31-111">Il codice nell'istruzione può essere suddiviso nelle parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="04d31-111">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="04d31-112">Identificazione della struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="04d31-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="04d31-113">Denominazione del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="04d31-113">Naming the mining model</span></span>  
  
-   <span data-ttu-id="04d31-114">Definizione della colonna chiave</span><span class="sxs-lookup"><span data-stu-id="04d31-114">Defining the key column</span></span>  
  
-   <span data-ttu-id="04d31-115">Definizione della colonna di input e della colonna stimabile</span><span class="sxs-lookup"><span data-stu-id="04d31-115">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="04d31-116">Definizione delle colonne della tabella nidificata</span><span class="sxs-lookup"><span data-stu-id="04d31-116">Defining the nested table columns</span></span>  
  
-   <span data-ttu-id="04d31-117">Identificazione delle modifiche a livello di algoritmo e parametri</span><span class="sxs-lookup"><span data-stu-id="04d31-117">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="04d31-118">Gli elementi seguenti sono un esempio generico dell'istruzione `ALTER MINING STRUCTURE`, che consente di aggiungere un modello di data mining a una struttura che include colonne delle tabelle nidificate:</span><span class="sxs-lookup"><span data-stu-id="04d31-118">The following is a generic example of the `ALTER MINING STRUCTURE` statement that adds a mining model to a structure that includes nested table columns:</span></span>  
  
```  
ALTER MINING STRUCTURE [<Mining Structure Name>]  
ADD MINING MODEL [<Mining Model Name>]  
(  
    [<key column>],  
    <mining model column> <usage>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
) USING <algorithm>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="04d31-119">La prima riga del codice identifica la struttura di data mining esistente a cui verrà aggiunto il modello di data mining:</span><span class="sxs-lookup"><span data-stu-id="04d31-119">The first line of the code identifies the existing mining structure to which the mining model will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="04d31-120">La riga successiva del codice indica il nome del modello di data mining che verrà aggiunto alla struttura di data mining:</span><span class="sxs-lookup"><span data-stu-id="04d31-120">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="04d31-121">Per informazioni sulla denominazione di un oggetto in DMX (Data Mining Extensions), vedere [identificatori &#40;&#41;DMX ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="04d31-121">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="04d31-122">Le successive righe del codice definiscono le colonne della struttura di data mining che verranno utilizzate dal modello di data mining:</span><span class="sxs-lookup"><span data-stu-id="04d31-122">The next lines of the code define the columns in the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns> <usage>,  
```  
  
 <span data-ttu-id="04d31-123">È possibile utilizzare solo colonne che esistono già nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="04d31-123">You can only use columns that already exist in the mining structure.</span></span>  
  
 <span data-ttu-id="04d31-124">La prima colonna nell'elenco delle colonne del modello di data mining deve essere la colonna chiave nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="04d31-124">The first column in the list of mining model columns must be the key column in the mining structure.</span></span> <span data-ttu-id="04d31-125">Tuttavia, non è necessario digitare `KEY` dopo la colonna chiave per specificare l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="04d31-125">However, you do not have to type `KEY` after the key column to specify usage.</span></span> <span data-ttu-id="04d31-126">Ciò avviene perché la colonna è già stata definita come colonna chiave al momento della creazione della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="04d31-126">That is because you have already defined the column as a key when you created the mining structure.</span></span>  
  
 <span data-ttu-id="04d31-127">Le righe rimanenti specificano l'utilizzo delle colonne nel nuovo modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="04d31-127">The remaining lines specify the usage of the columns in the new mining model.</span></span> <span data-ttu-id="04d31-128">Per specificare che una colonna nel modello di data mining verrà utilizzata per la stima, è possibile utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="04d31-128">You can specify that a column in the mining model will be used for prediction by using the following syntax:</span></span>  
  
```  
<column name> PREDICT,  
```  
  
 <span data-ttu-id="04d31-129">Se non viene specificato l'utilizzo, non è necessario includere una colonna della struttura di data mining nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="04d31-129">If you do not specify usage, you do not have to include a data mining structure column in the list.</span></span> <span data-ttu-id="04d31-130">Tutte le colonne utilizzate dalla struttura di data mining di riferimento sono automaticamente disponibili per l'utilizzo da parte dei modelli di data mining basati su tale struttura.</span><span class="sxs-lookup"><span data-stu-id="04d31-130">All columns that are used by the referenced data mining structure are automatically available for use by the mining models that are based on that structure.</span></span> <span data-ttu-id="04d31-131">Tuttavia, il modello non utilizzerà le colonne per il training a meno che non venga specificato l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="04d31-131">However, the model will not use the columns for training unless you specify the usage.</span></span>  
  
 <span data-ttu-id="04d31-132">L'ultima riga del codice definisce l'algoritmo e i parametri dell'algoritmo che verranno utilizzati per generare il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="04d31-132">The last line in the code defines the algorithm and algorithm parameters that will be used to generate the mining model.</span></span>  
  
```  
) USING <algorithm>( <algorithm parameters> )  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="04d31-133">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="04d31-133">Lesson Tasks</span></span>  
 <span data-ttu-id="04d31-134">In questa lezione verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="04d31-134">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="04d31-135">Aggiunta di un modello di data mining di associazione alla struttura utilizzando il valore di probabilità predefinito</span><span class="sxs-lookup"><span data-stu-id="04d31-135">Add an association mining model to the structure using the default probability</span></span>  
  
-   <span data-ttu-id="04d31-136">Aggiunta di un modello di data mining di associazione alla struttura utilizzando un valore di probabilità modificato</span><span class="sxs-lookup"><span data-stu-id="04d31-136">Add an association mining model to the structure using a modified probability</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-using-the-default-minimum_probability"></a><span data-ttu-id="04d31-137">Aggiunta di un modello di data mining di associazione alla struttura utilizzando il valore predefinito di MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="04d31-137">Adding an Association Mining Model to the Structure Using the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="04d31-138">La prima attività consiste nell'aggiungere un nuovo modello di data mining alla struttura di data mining Market basket in base all' [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo di associazione usando il valore predefinito per *MINIMUM_PROBABILITY*.</span><span class="sxs-lookup"><span data-stu-id="04d31-138">The first task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm using the default value for *MINIMUM_PROBABILITY*.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="04d31-139">Per aggiungere un modello di data mining di associazione</span><span class="sxs-lookup"><span data-stu-id="04d31-139">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="04d31-140">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="04d31-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="04d31-141">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="04d31-141">Query Editor opens and contains a new, blank query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04d31-142">Per creare una query DMX su un database [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] specifico, fare clic con il pulsante destro del mouse sul database anziché sull'istanza.</span><span class="sxs-lookup"><span data-stu-id="04d31-142">To create a DMX query against a specific [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, right-click the database instead of the instance.</span></span>  
  
2.  <span data-ttu-id="04d31-143">Copiare l'esempio generico dell'istruzione `ALTER MINING STRUCTURE` nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="04d31-143">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="04d31-144">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04d31-144">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="04d31-145">con:</span><span class="sxs-lookup"><span data-stu-id="04d31-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
4.  <span data-ttu-id="04d31-146">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04d31-146">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="04d31-147">con:</span><span class="sxs-lookup"><span data-stu-id="04d31-147">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="04d31-148">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04d31-148">Replace the following:</span></span>  
  
    ```  
    [<key column>],  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="04d31-149">con:</span><span class="sxs-lookup"><span data-stu-id="04d31-149">with:</span></span>  
  
    ```  
    OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="04d31-150">In questo caso, la tabella `[Products]` è stata definita come colonna stimabile`.` Inoltre, la colonna `[Model]` è inclusa nell'elenco delle colonne della tabella nidificata, poiché è la colonna chiave della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="04d31-150">In this case, the `[Products]` table has been designated as the predictable column`.` Also, the `[Model]` column is included in the list of nested table columns because it is the key column of the nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04d31-151">Tenere presente che una chiave nidificata è diversa da una chiave del case.</span><span class="sxs-lookup"><span data-stu-id="04d31-151">Remember that a nested key is different from a case key.</span></span> <span data-ttu-id="04d31-152">Una chiave del case è un identificatore univoco del case, mentre la chiave nidificata è un attributo che si desidera modellare.</span><span class="sxs-lookup"><span data-stu-id="04d31-152">A case key is a unique identifier of the case, whereas the nested key is an attribute that you want to model.</span></span>  
  
6.  <span data-ttu-id="04d31-153">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04d31-153">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="04d31-154">con:</span><span class="sxs-lookup"><span data-stu-id="04d31-154">with:</span></span>  
  
    ```  
    Using Microsoft_Association_Rules  
    ```  
  
     <span data-ttu-id="04d31-155">L'istruzione risultante dovrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="04d31-155">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Default Association]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    Using Microsoft_Association_Rules  
    ```  
  
7.  <span data-ttu-id="04d31-156">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="04d31-156">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="04d31-157">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Default_Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="04d31-157">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Default_Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="04d31-158">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="04d31-158">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-changing-the-default-minimum_probability"></a><span data-ttu-id="04d31-159">Aggiunta di un modello di data mining di associazione alla struttura modificando il valore predefinito di MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="04d31-159">Adding an Association Mining Model to the Structure Changing the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="04d31-160">L'attività successiva consiste nell'aggiunta di un nuovo modello di data mining alla struttura di data mining Market Basket in base all'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Association modificando il valore predefinito di MINIMUM_PROBABILITY in 0,01.</span><span class="sxs-lookup"><span data-stu-id="04d31-160">The next task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm, and change the default value for MINIMUM_PROBABILITY to 0.01.</span></span> <span data-ttu-id="04d31-161">La modifica del parametro determinerà la creazione di ulteriori regole da parte dell'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Association.</span><span class="sxs-lookup"><span data-stu-id="04d31-161">Changing the parameter will cause the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm to create more rules.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="04d31-162">Per aggiungere un modello di data mining di associazione</span><span class="sxs-lookup"><span data-stu-id="04d31-162">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="04d31-163">In **Esplora oggetti**fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , scegliere **nuova query**, quindi fare clic su **DMX**.</span><span class="sxs-lookup"><span data-stu-id="04d31-163">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="04d31-164">Verrà avviato l'editor di query con una nuova query vuota.</span><span class="sxs-lookup"><span data-stu-id="04d31-164">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="04d31-165">Copiare l'esempio generico dell'istruzione `ALTER MINING STRUCTURE` nella query vuota.</span><span class="sxs-lookup"><span data-stu-id="04d31-165">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="04d31-166">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04d31-166">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="04d31-167">con:</span><span class="sxs-lookup"><span data-stu-id="04d31-167">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="04d31-168">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04d31-168">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="04d31-169">con:</span><span class="sxs-lookup"><span data-stu-id="04d31-169">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="04d31-170">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04d31-170">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="04d31-171">con:</span><span class="sxs-lookup"><span data-stu-id="04d31-171">with:</span></span>  
  
    ```  
    OrderNumber,  
    [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="04d31-172">In questo caso, la tabella `[Products]` è stata designata come colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="04d31-172">In this case, the `[Products]` table has been designated as the predictable column.</span></span> <span data-ttu-id="04d31-173">Anche la colonna `[MODEL]` è inclusa nell'elenco perché è la colonna chiave nella tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="04d31-173">Also, the `[MODEL]` column is included in the list because it is the key column in the nested table.</span></span>  
  
6.  <span data-ttu-id="04d31-174">Sostituire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="04d31-174">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="04d31-175">con:</span><span class="sxs-lookup"><span data-stu-id="04d31-175">with:</span></span>  
  
    ```  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
     <span data-ttu-id="04d31-176">L'istruzione risultante dovrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="04d31-176">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Modified Assocation]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
7.  <span data-ttu-id="04d31-177">Scegliere **Salva DMXQuery1. DMX con nome**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="04d31-177">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="04d31-178">Nella finestra di dialogo **Salva con** nome individuare la cartella appropriata e assegnare al file il nome `Modified Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="04d31-178">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="04d31-179">Sulla barra degli strumenti fare clic sul pulsante **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="04d31-179">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="04d31-180">Nella lezione successiva verranno elaborati la struttura di data mining Market Basket insieme ai relativi modelli di data mining associati.</span><span class="sxs-lookup"><span data-stu-id="04d31-180">In this next lesson you will process the Market Basket mining structure together with its associated mining models.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="04d31-181">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="04d31-181">Next Lesson</span></span>  
 [<span data-ttu-id="04d31-182">Lezione 3: Elaborazione della struttura di data mining Market Basket</span><span class="sxs-lookup"><span data-stu-id="04d31-182">Lesson 3: Processing the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-market-basket-mining-structure.md)  
  
  
