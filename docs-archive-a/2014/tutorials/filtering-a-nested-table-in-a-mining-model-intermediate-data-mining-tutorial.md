---
title: Filtro di una tabella nidificata in un modello di data mining (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0a3ae0e5-897b-4898-a60d-5455eec3d305
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1e6ce2936a3c6763ea41999b2724c0fe8c79301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723239"
---
# <a name="filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="44964-102">Applicazione di filtri a una tabella nidificata in un modello di data mining (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="44964-102">Filtering a Nested Table in a Mining Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="44964-103">Dopo avere creato ed esplorato il modello, si decide che si desidera concentrarsi su un subset dei dati sui clienti.</span><span class="sxs-lookup"><span data-stu-id="44964-103">After you have created and explored the model, you decide that you want to focus on a subset of the customer data.</span></span> <span data-ttu-id="44964-104">Potrebbe ad esempio essere necessario analizzare solo gli acquisti relativi a uno specifico articolo o analizzare i dati demografici dei clienti che non hanno effettuato acquisti in un determinato periodo.</span><span class="sxs-lookup"><span data-stu-id="44964-104">For example, you might want to analyze only the baskets that contain a specific item, or to analyze the demographics of customers who have not purchased anything in a certain period.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="44964-105">consente di filtrare i dati utilizzati in un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="44964-105">provides the ability to filter the data that is used in a mining model.</span></span> <span data-ttu-id="44964-106">Questa funzionalità è utile perché non è necessario configurare una nuova vista origine dati per l'utilizzo di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="44964-106">This feature is useful because you do not need to set up a new data source view to use different data.</span></span> <span data-ttu-id="44964-107">Nell'esercitazione di base sul data mining è stato descritto come filtrare i dati da una tabella flat applicando condizioni alla tabella del case.</span><span class="sxs-lookup"><span data-stu-id="44964-107">In the Basic Data Mining Tutorial, you learned how to filter data from a flat table by applying conditions to the case table.</span></span> <span data-ttu-id="44964-108">In questa attività verrà creato un filtro che si applica a una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="44964-108">In this task, you create a filter that applies to a nested table.</span></span>  
  
## <a name="filters-on-nested-vs-case-tables"></a><span data-ttu-id="44964-109">Filtri su tabelle nidificate o tabelle del case</span><span class="sxs-lookup"><span data-stu-id="44964-109">Filters on Nested vs. Case Tables</span></span>  
 <span data-ttu-id="44964-110">Se la vista origine dati contiene una tabella del case e una tabella nidificata, come la vista origine dati utilizzata nel modello di associazione, è possibile applicare filtri in base ai valori nella tabella del case, alla presenza o assenza di un valore nella tabella nidificata o a una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="44964-110">If your data source view contains a case table and a nested table, like the data source view used in the Association model, you can filter on values from the case table, the presence or absence of a value in the nested table, or some combination of both.</span></span>  
  
 <span data-ttu-id="44964-111">In questa attività verrà innanzitutto creata una copia del modello di associazione, quindi si aggiungeranno gli attributi IncomeGroup e Region al nuovo modello correlato, in modo da applicare filtri in base a tali attributi nella tabella del case.</span><span class="sxs-lookup"><span data-stu-id="44964-111">In this task, you will first make a copy of the Association model and then add the IncomeGroup and Region attributes to the new related model, so that you can filter on those attributes in the case table.</span></span>  
  
#### <a name="to-create-and-modify-a-copy-of-the-association-model"></a><span data-ttu-id="44964-112">Per creare e modificare una copia del modello di associazione</span><span class="sxs-lookup"><span data-stu-id="44964-112">To create and modify a copy of the Association model</span></span>  
  
1.  <span data-ttu-id="44964-113">Nella scheda **modelli di data mining** di fare [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] clic con il pulsante destro del mouse sul `Association` modello e scegliere **nuovo modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="44964-113">In the **Mining Models** tab of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click the `Association` model, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="44964-114">Per **nome modello**, digitare `Association Filtered` .</span><span class="sxs-lookup"><span data-stu-id="44964-114">For **Model Name**, type `Association Filtered`.</span></span> <span data-ttu-id="44964-115">Per **Nome algoritmo**selezionare **Microsoft Association Rules**.</span><span class="sxs-lookup"><span data-stu-id="44964-115">For **Algorithm Name**, select **Microsoft Association Rules**.</span></span> <span data-ttu-id="44964-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44964-116">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="44964-117">Nella colonna per il modello Association Filtered fare clic sulla riga IncomeGroup e modificare il valore da **Ignore** a **input**.</span><span class="sxs-lookup"><span data-stu-id="44964-117">In the column for the Association Filtered model, click the IncomeGroup row and change the value from **Ignore** to **Input**.</span></span>  
  
 <span data-ttu-id="44964-118">Il passaggio successivo consiste nella creazione di un filtro sulla tabella del case nel nuovo modello di associazione.</span><span class="sxs-lookup"><span data-stu-id="44964-118">Next, you will create a filter on the case table in the new association model.</span></span> <span data-ttu-id="44964-119">Il filtro passerà al modello solo i clienti nell'area di destinazione o con il livello di reddito di destinazione.</span><span class="sxs-lookup"><span data-stu-id="44964-119">The filter will pass to the model only the customers in the target region or with the target income level.</span></span> <span data-ttu-id="44964-120">Si aggiungerà quindi un secondo set di condizioni di filtro per specificare che il modello utilizza solo i clienti i cui acquisti contengono almeno un articolo.</span><span class="sxs-lookup"><span data-stu-id="44964-120">Then, you will add a second set of filter conditions to specify that the model uses only customers whose shopping baskets contained at least one item.</span></span>  
  
#### <a name="to-add-a-filter-to-a-mining-model"></a><span data-ttu-id="44964-121">Per aggiungere un filtro a un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="44964-121">To add a filter to a mining model</span></span>  
  
1.  <span data-ttu-id="44964-122">Nella scheda **modelli di data mining** fare clic con il pulsante destro del mouse sull'associazione di modelli filtrata e selezionare **Imposta filtro modello**.</span><span class="sxs-lookup"><span data-stu-id="44964-122">In the **Mining Models** tab, right-click the model Association Filtered, and select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="44964-123">Nella finestra di dialogo **Filtro modello** fare clic sulla riga superiore nella griglia della casella di testo **Colonna struttura di data mining** .</span><span class="sxs-lookup"><span data-stu-id="44964-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
3.  <span data-ttu-id="44964-124">Nella casella di testo **colonna struttura di data mining** selezionare IncomeGroup.</span><span class="sxs-lookup"><span data-stu-id="44964-124">In the **Mining Structure Column** text box, select IncomeGroup.</span></span>  
  
     <span data-ttu-id="44964-125">L'icona a sinistra della casella di testo cambia per indicare che l'elemento selezionato è una colonna.</span><span class="sxs-lookup"><span data-stu-id="44964-125">The icon at the left side of the text box changes to indicate that the selected item is a column.</span></span>  
  
4.  <span data-ttu-id="44964-126">Fare clic sulla casella di testo **operatore** e selezionare l' **=** operatore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="44964-126">Click the **Operator** text box and select the **=** operator from the list.</span></span>  
  
5.  <span data-ttu-id="44964-127">Fare clic sulla casella di testo **valore** e digitare `High` nella casella.</span><span class="sxs-lookup"><span data-stu-id="44964-127">Click the **Value** text box, and type `High` in the box.</span></span>  
  
6.  <span data-ttu-id="44964-128">Fare clic sulla riga successiva nella griglia.</span><span class="sxs-lookup"><span data-stu-id="44964-128">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="44964-129">Fare clic sulla casella di testo **and/or** nella riga successiva della griglia e selezionare **o**.</span><span class="sxs-lookup"><span data-stu-id="44964-129">Click the **AND/OR** text box in the next row of the grid and select **OR**.</span></span>  
  
8.  <span data-ttu-id="44964-130">Nella casella di testo **colonna struttura di data mining** selezionare IncomeGroup.</span><span class="sxs-lookup"><span data-stu-id="44964-130">In the **Mining Structure Column** text box, select IncomeGroup.</span></span> <span data-ttu-id="44964-131">Nella casella di testo **valore** Digitare `Moderate` .</span><span class="sxs-lookup"><span data-stu-id="44964-131">In the **Value** text box, type `Moderate`.</span></span>  
  
     <span data-ttu-id="44964-132">La condizione di filtro creata viene aggiunta automaticamente alla casella di testo **espressione** e dovrebbe apparire come segue:</span><span class="sxs-lookup"><span data-stu-id="44964-132">The filter condition that you created is automatically added to the **Expression** text box, and should appears as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate'`  
  
9. <span data-ttu-id="44964-133">Fare clic sulla riga successiva nella griglia, lasciando l'operatore come predefinito, **e**.</span><span class="sxs-lookup"><span data-stu-id="44964-133">Click the next row in the grid, leaving the operator as the default, **AND**.</span></span>  
  
10. <span data-ttu-id="44964-134">Per **operator**, lasciare il valore predefinito, **Contains**.</span><span class="sxs-lookup"><span data-stu-id="44964-134">For **Operator**, leave the default value, **Contains**.</span></span> <span data-ttu-id="44964-135">Fare clic sulla casella di testo **valore** .</span><span class="sxs-lookup"><span data-stu-id="44964-135">Click the **Value** text box.</span></span>  
  
11. <span data-ttu-id="44964-136">Nella finestra di dialogo **filtro** , nella prima riga sotto **colonna struttura di data mining**Selezionare `Model` .</span><span class="sxs-lookup"><span data-stu-id="44964-136">In the **Filter** dialog box, in the first row under **Mining Structure Column**, select `Model`.</span></span>  
  
12. <span data-ttu-id="44964-137">Per **operator**selezionare **is not null**.</span><span class="sxs-lookup"><span data-stu-id="44964-137">For **Operator**, select **IS NOT NULL**.</span></span> <span data-ttu-id="44964-138">Lasciare vuota la casella di testo **valore** .</span><span class="sxs-lookup"><span data-stu-id="44964-138">Leave the **Value** text box blank.</span></span> <span data-ttu-id="44964-139">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44964-139">Click **OK**.</span></span>  
  
     <span data-ttu-id="44964-140">La condizione di filtro nella casella di testo **espressione** della finestra di dialogo **filtro modello** viene aggiornata automaticamente per includere la nuova condizione nella tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="44964-140">The filter condition in the **Expression** text box of the **Model Filter** dialog box is automatically updated to include the new condition on the nested table.</span></span> <span data-ttu-id="44964-141">L'espressione completa è la seguente:</span><span class="sxs-lookup"><span data-stu-id="44964-141">The completed expression is as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate' AND EXISTS SELECT * FROM [vAssocSeqLineItems] WHERE [Model] <> NULL).`  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)] ``  
  
#### <a name="to-enable-drillthrough-and-to-process-the-filtered-model"></a><span data-ttu-id="44964-142">Per abilitare il drill-through ed elaborare il modello filtrato</span><span class="sxs-lookup"><span data-stu-id="44964-142">To enable drillthrough and to process the filtered model</span></span>  
  
1.  <span data-ttu-id="44964-143">Nella scheda **modelli di data mining** fare clic con il pulsante destro del mouse sul `Association Filtered` modello e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="44964-143">In the **Mining Models** tab, right-click the `Association Filtered` model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="44964-144">Modificare la proprietà **AllowDrillThrough** in **true**.</span><span class="sxs-lookup"><span data-stu-id="44964-144">Change the **AllowDrillThrough** property to **True**.</span></span>  
  
3.  <span data-ttu-id="44964-145">Fare clic con il pulsante destro del mouse sul `Association Filtered` modello di data mining e scegliere **Elabora modello**.</span><span class="sxs-lookup"><span data-stu-id="44964-145">Right-click the `Association Filtered` mining model, and select **Process Model**.</span></span>  
  
4.  <span data-ttu-id="44964-146">Fare clic su **Sì** nel messaggio di errore per distribuire il nuovo modello nel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="44964-146">Click **Yes** in the error message to deploy the new model to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
5.  <span data-ttu-id="44964-147">Nella finestra di dialogo **Elabora struttura di data mining** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="44964-147">In the **Process Mining Structure** dialog box, click **Run**.</span></span>  
  
6.  <span data-ttu-id="44964-148">Al termine dell'elaborazione, fare clic su **Chiudi** per uscire dalla finestra di dialogo **stato** elaborazione, quindi fare di nuovo clic su **Chiudi** per chiudere la finestra di dialogo **Elabora struttura di data mining** .</span><span class="sxs-lookup"><span data-stu-id="44964-148">When processing is complete click **Close** to exit the **Process Progress** dialog box, and click **Close** again to exit the **Process Mining Structure** dialog box.</span></span>  
  
 <span data-ttu-id="44964-149">È possibile verificare tramite Microsoft Generic Content Tree Viewer e controllando il valore di NODE_SUPPORT che il modello filtrato contenga meno case del modello originale.</span><span class="sxs-lookup"><span data-stu-id="44964-149">You can verify by using the Microsoft Generic Content Tree viewer and looking at the value for NODE_SUPPORT that the filtered model contains fewer cases than the original model.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44964-150">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="44964-150">Remarks</span></span>  
 <span data-ttu-id="44964-151">Il filtro della tabella nidificata che è stato creato controlla solo la presenza di almeno una riga nella tabella nidificata, tuttavia è anche possibile creare condizioni di filtro che verifichino la presenza di prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="44964-151">The nested table filter that you just created checks only for the presence of at least one row in the nested table; however, you can also create filter conditions that check for the presence of specific products.</span></span>  <span data-ttu-id="44964-152">È ad esempio possibile creare il filtro seguente:</span><span class="sxs-lookup"><span data-stu-id="44964-152">For example, you could create the following filter:</span></span>  
  
```  
[IncomeGroup] = 'High' AND  
 EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] = 'Water Bottle' )   
```  
  
 <span data-ttu-id="44964-153">Questa istruzione indica che i clienti della tabella del case devono essere limitati a quelli che hanno acquistato una bottiglia d'acqua (Water Bottle).</span><span class="sxs-lookup"><span data-stu-id="44964-153">This statement means that you are restricting the customers from the case table to only those who have purchased a water bottle.</span></span> <span data-ttu-id="44964-154">Tuttavia, poiché il numero di attributi della tabella nidificata è potenzialmente illimitato, in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] non viene fornito un elenco di valori possibili da cui effettuare una selezione.</span><span class="sxs-lookup"><span data-stu-id="44964-154">However, because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="44964-155">È invece necessario digitare il valore esatto.</span><span class="sxs-lookup"><span data-stu-id="44964-155">Instead, you must type the exact value.</span></span>  
  
 <span data-ttu-id="44964-156">È possibile fare clic su **modifica query** per modificare manualmente l'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="44964-156">You can click **Edit Query** to manually change the filter expression.</span></span> <span data-ttu-id="44964-157">Se tuttavia si modifica manualmente una parte di un'espressione di filtro, la griglia verrà disabilitata e da allora in poi sarà necessario utilizzare l'espressione di filtro solo in modalità di modifica di testo.</span><span class="sxs-lookup"><span data-stu-id="44964-157">However, if you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="44964-158">Per ripristinare la modalità di modifica della griglia, è necessario cancellare l'espressione di filtro e ricominciare.</span><span class="sxs-lookup"><span data-stu-id="44964-158">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="44964-159">Non è possibile utilizzare l'operatore LIKE nel filtro di una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="44964-159">You cannot use the LIKE operator in a nested table filter.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="44964-160">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="44964-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="44964-161">Stima delle associazioni &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="44964-161">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="44964-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44964-162">See Also</span></span>  
 <span data-ttu-id="44964-163">[Sintassi del filtro del modello ed esempi &#40;Analysis Services-&#41;di data mining](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="44964-163">[Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="44964-164">Filtri per i modelli di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="44964-164">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
