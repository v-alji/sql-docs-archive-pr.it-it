---
title: Scenario di ricerca obiettivo (strumenti di analisi tabelle per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- scenario analysis
- goal seek scenario
ms.assetid: efe50306-cf7c-46b3-9cc4-e7f0b6968b0c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b3b4df4f78a2d3652b1dac3c566e66507b523ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626966"
---
# <a name="goal-seek-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="e8898-102">Ricerca obiettivo (Strumenti di analisi tabelle per Excel)</span><span class="sxs-lookup"><span data-stu-id="e8898-102">Goal Seek Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="e8898-103">![Pulsante Ricerca obiettivo in Strumenti di analisi tabelle](media/tat-goalseek.gif "Pulsante Ricerca obiettivo in Strumenti di analisi tabelle")</span><span class="sxs-lookup"><span data-stu-id="e8898-103">![Goal Seek button in Table Analysis tools](media/tat-goalseek.gif "Goal Seek button in Table Analysis tools")</span></span>  
  
 <span data-ttu-id="e8898-104">Lo strumento per lo scenario di **Ricerca obiettivo** è complementare allo strumento [What If](what-if-scenario-table-analysis-tools-for-excel.md) scenario.</span><span class="sxs-lookup"><span data-stu-id="e8898-104">The **Goal Seek** scenario tool is complementary to the [What If](what-if-scenario-table-analysis-tools-for-excel.md) scenario tool.</span></span> <span data-ttu-id="e8898-105">Lo **strumento di** simulazione indica l'effetto di apportare una modifica, mentre lo strumento **Ricerca obiettivo** indica i fattori sottostanti che devono essere modificati per ottenere un risultato desiderato.</span><span class="sxs-lookup"><span data-stu-id="e8898-105">The **What-If** tool tells you the impact of making a change, whereas the **Goal Seek** tool tells you the underlying factors that must change to achieve a desired result.</span></span>  
  
 <span data-ttu-id="e8898-106">Si immagini, ad esempio, che l'obiettivo sia quello di aumentare la soddisfazione dei clienti.</span><span class="sxs-lookup"><span data-stu-id="e8898-106">For example, let's say your goal is to increase customer satisfaction.</span></span> <span data-ttu-id="e8898-107">È possibile utilizzare l'analisi **Ricerca obiettivo** per determinare quali fattori potrebbero aumentare la soddisfazione dei clienti e decidere se tali modifiche sono convenienti.</span><span class="sxs-lookup"><span data-stu-id="e8898-107">You can use **Goal Seek** analysis to determine which factors would be most likely to increase customer satisfaction, and decide whether those changes are cost-effective.</span></span>  
  
 <span data-ttu-id="e8898-108">Al termine dell'analisi, tramite lo strumento vengono create due nuove colonne nella tabella dati di origine.</span><span class="sxs-lookup"><span data-stu-id="e8898-108">When the tool finishes its analysis, it creates two new columns in the source data table.</span></span> <span data-ttu-id="e8898-109">Queste colonne indicano la *probabilità* che il risultato di destinazione possa essere ottenuto e la modifica consigliata, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="e8898-109">These columns show the *likelihood* that the targeted outcome can be achieved, and the recommended change, if any.</span></span>  
  
 <span data-ttu-id="e8898-110">Lo strumento consente di analizzare un set di dati e di eseguire stime per l'intero set. Altrimenti, è possibile creare l'analisi, quindi testare uno scenario alla volta.</span><span class="sxs-lookup"><span data-stu-id="e8898-110">The tool can analyze a set of data and make predictions for the entire set, or you can create the analysis and then test scenarios one at a time.</span></span>  
  
## <a name="using-the-goal-seek-scenario-tool"></a><span data-ttu-id="e8898-111">Utilizzo dello strumento per l'analisi di scenari Ricerca obiettivo</span><span class="sxs-lookup"><span data-stu-id="e8898-111">Using the Goal Seek Scenario Tool</span></span>  
  
1.  <span data-ttu-id="e8898-112">Aprire una tabella di Excel.</span><span class="sxs-lookup"><span data-stu-id="e8898-112">Open an Excel table.</span></span>  
  
2.  <span data-ttu-id="e8898-113">Fare clic su **scenari**e selezionare **Ricerca obiettivo**.</span><span class="sxs-lookup"><span data-stu-id="e8898-113">Click **Scenarios**, and select **Goal Seek**.</span></span>  
  
3.  <span data-ttu-id="e8898-114">Nella finestra di dialogo **analisi dello scenario: ricerca obiettivo** selezionare la colonna che contiene il valore di destinazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="e8898-114">In the **Scenario Analysis: Goal Seek** dialog box, select the column that contains the target value from the list.</span></span>  
  
4.  <span data-ttu-id="e8898-115">Specificare il valore che si desidera raggiungere.</span><span class="sxs-lookup"><span data-stu-id="e8898-115">Specify the value that you want to achieve.</span></span>  
  
     <span data-ttu-id="e8898-116">Se l'obiettivo della colonna contiene valori numerici continui, è anche possibile specificare la riduzione o l'aumento desiderato per il valore.</span><span class="sxs-lookup"><span data-stu-id="e8898-116">If the column goal contains continuous numeric values, you can also specify a desired increase or decrease in the value.</span></span> <span data-ttu-id="e8898-117">È ad esempio possibile scegliere **Sales** come colonna e specificare che la destinazione è un aumento del 120%.</span><span class="sxs-lookup"><span data-stu-id="e8898-117">For example, you might choose **Sales** as the column and specify that the target is an increase of 120%.</span></span>  
  
     <span data-ttu-id="e8898-118">In alternativa, è possibile specificare l'obiettivo come intervallo di valori, digitando un limite inferiore e uno superiore.</span><span class="sxs-lookup"><span data-stu-id="e8898-118">Or, you can specify the goal as a range of values, by typing a lower and upper limit.</span></span>  
  
5.  <span data-ttu-id="e8898-119">Specificare la colonna contenente i valori che verranno modificati.</span><span class="sxs-lookup"><span data-stu-id="e8898-119">Specify the column that contains the values you will change.</span></span> <span data-ttu-id="e8898-120">In altre parole, scegliere la colonna che verrà modificata per produrre il risultato desiderato.</span><span class="sxs-lookup"><span data-stu-id="e8898-120">In other words, pick the column that will be manipulated to produce the desired result.</span></span>  
  
6.  <span data-ttu-id="e8898-121">Facoltativamente, fare clic su **Scegli le colonne da utilizzare per l'analisi**e selezionare le colonne contenenti informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="e8898-121">Optionally, click **Choose columns to be used for analysis**, and select columns that contain useful information.</span></span> <span data-ttu-id="e8898-122">Deselezionare le colonne che non contribuiscono all'analisi.</span><span class="sxs-lookup"><span data-stu-id="e8898-122">Deselect columns that will not contribute to the analysis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8898-123">Non deselezionare le colonne che verranno utilizzate per l'obiettivo o per la modifica.</span><span class="sxs-lookup"><span data-stu-id="e8898-123">Do not deselect columns that you will use for either the goal or the change.</span></span> <span data-ttu-id="e8898-124">Queste colonne sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="e8898-124">These columns are required.</span></span>  
  
7.  <span data-ttu-id="e8898-125">Specificare se si desidera eseguire le stime per l'intera tabella o solo per la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e8898-125">Specify whether you want to make predictions for the entire table, or for only the selected row.</span></span>  
  
8.  <span data-ttu-id="e8898-126">Se è stata selezionata l'opzione **intera tabella** , lo strumento aggiunge le stime alla tabella di origine in due nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="e8898-126">If you selected the **Entire table** option, the tool adds the predictions to the source table in two new columns.</span></span>  
  
9. <span data-ttu-id="e8898-127">Se è stata selezionata l'opzione **in questa riga**, i risultati dell'analisi vengono restituiti alla finestra di dialogo per la revisione.</span><span class="sxs-lookup"><span data-stu-id="e8898-127">If you selected the option **On this row**, the results of analysis are output to the dialog box for review.</span></span> <span data-ttu-id="e8898-128">La finestra di dialogo rimane aperta in modo che sia possibile continuare a provare diversi valori e obiettivi.</span><span class="sxs-lookup"><span data-stu-id="e8898-128">The dialog box stays open so that you can continue trying out different values and goals.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="e8898-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8898-129">Requirements</span></span>  
 <span data-ttu-id="e8898-130">Questo strumento utilizza l'algoritmo Microsoft Logistic Regression, che consente di elaborare valori numerici o discreti.</span><span class="sxs-lookup"><span data-stu-id="e8898-130">This tool uses the Microsoft Logistic Regression algorithm, which can process either numeric or discrete values.</span></span>  
  
 <span data-ttu-id="e8898-131">È possibile eseguire la stima più volte selezionando colonne diverse, ma ogni combinazione di obiettivo e modifica deve essere calcolata separatamente.</span><span class="sxs-lookup"><span data-stu-id="e8898-131">You can run the prediction multiple times, and select different columns later, but each combination of a goal and a change must be calculated separately.</span></span>  
  
 <span data-ttu-id="e8898-132">È possibile ottenere risultati migliori se per l'analisi si selezionano colonne contenenti informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="e8898-132">You can achieve better results if you select columns for analysis that contain useful information.</span></span> <span data-ttu-id="e8898-133">Se tuttavia si include un numero di colonne troppo limitato, potrebbe essere difficile ottenere un risultato.</span><span class="sxs-lookup"><span data-stu-id="e8898-133">However, if you include too few columns, it might be difficult to obtain a result.</span></span>  
  
 <span data-ttu-id="e8898-134">Quando si crea una stima alla volta, assicurarsi di selezionare una riga che non contenga già il risultato desiderato. In caso contrario, potrebbe verificarsi un errore.</span><span class="sxs-lookup"><span data-stu-id="e8898-134">When you create predictions one at a time, be sure to select a row that does not already contain the desired result, or you may get an error.</span></span> <span data-ttu-id="e8898-135">In altre parole, se lo scopo della ricerca dell'obiettivo è quello di determinare i fattori che incoraggiano l'acquisto di biciclette, è necessario includere solo i clienti che non hanno acquistato una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="e8898-135">In other words, if the purpose of goal seeking is to determine factors that encourage bike purchases, you should only include customers who did not purchase a bike.</span></span>  
  
## <a name="understanding-the-results-of-goal-seek-analysis"></a><span data-ttu-id="e8898-136">Informazioni sui risultati di un'analisi Ricerca obiettivo</span><span class="sxs-lookup"><span data-stu-id="e8898-136">Understanding the Results of Goal Seek Analysis</span></span>  
 <span data-ttu-id="e8898-137">Quando si crea uno scenario per la ricerca di un obiettivo, tramite lo strumento vengono eseguite tre operazioni:</span><span class="sxs-lookup"><span data-stu-id="e8898-137">When you create a goal seeking scenario, the tool does three things:</span></span>  
  
-   <span data-ttu-id="e8898-138">Creazione di una struttura di data mining per l'archiviazione dei fatti principali relativi ai dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="e8898-138">Creates a data mining structure that stores key facts about the data in your table.</span></span>  
  
-   <span data-ttu-id="e8898-139">Creazione di un modello di data mining per la regressione logistica basato sui dati.</span><span class="sxs-lookup"><span data-stu-id="e8898-139">Creates a logistic regression mining model based on the data.</span></span>  
  
-   <span data-ttu-id="e8898-140">Creazione di una stima per ogni valore specificato.</span><span class="sxs-lookup"><span data-stu-id="e8898-140">Creates a prediction for each value that you specify.</span></span>  
  
 <span data-ttu-id="e8898-141">Se si testano gli scenari di ricerca dell'obiettivo uno alla volta, è possibile visualizzare i risultati in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="e8898-141">If you test goal-seeking scenarios one at a time, you can view the results interactively.</span></span> <span data-ttu-id="e8898-142">Corrisponde alla creazione di una query di *stima singleton*.</span><span class="sxs-lookup"><span data-stu-id="e8898-142">This is the same as creating a *singleton prediction query*.</span></span>  
  
 <span data-ttu-id="e8898-143">Lo strumento segnala nel riquadro dei **risultati** della finestra di dialogo se la ricerca di uno scenario che raggiunge l'obiettivo desiderato è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e8898-143">The tool reports in the **Results** pane of the dialog box whether it was successful in finding a scenario that achieves the desired goal.</span></span> <span data-ttu-id="e8898-144">Se è stata individuata una soluzione appropriata, viene inoltre indicata la modifica necessaria.</span><span class="sxs-lookup"><span data-stu-id="e8898-144">If a successful solution was found, the tool also generates a recommendation that tells you the required change.</span></span> <span data-ttu-id="e8898-145">Ad esempio, lo strumento **Ricerca obiettivo** potrebbe indicare che la distanza di commutazione deve essere inferiore a 5 km.</span><span class="sxs-lookup"><span data-stu-id="e8898-145">For example, the **Goal Seek** tool might tell you that the commuting distance should be less than 5 miles.</span></span>  
  
 <span data-ttu-id="e8898-146">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="e8898-146">Example results:</span></span>  
  
 <span data-ttu-id="e8898-147">**Soluzione trovata per la ricerca dell'obiettivo Interest in Buying.**</span><span class="sxs-lookup"><span data-stu-id="e8898-147">**Goal Seeking for Interest in Buying has found a solution.**</span></span>  
  
 <span data-ttu-id="e8898-148">**Risultato migliore ottenuto con la modifica di 'Commute distance' in '2-5 miles'.**</span><span class="sxs-lookup"><span data-stu-id="e8898-148">**Closest match obtained by changing 'Commute distance' to '2-5 miles'.**</span></span>  
  
 <span data-ttu-id="e8898-149">Poiché il risultato è basato su una riga esistente nella tabella dati, significa che per un particolare cliente l'acquisto di una bicicletta sarebbe più probabile se tutti gli altri dati rimanessero invariati, ma la distanza dal lavoro del cliente venisse ridotta a 2-5 miglia.</span><span class="sxs-lookup"><span data-stu-id="e8898-149">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's commute was reduced to 2-5 miles, the customer would be somewhat more likely buy a bicycle.</span></span>  
  
 <span data-ttu-id="e8898-150">Se si creano stime di ricerca obiettivo per tutte le righe nella tabella di Excel specificando l' **intera tabella**, theTool crea due nuove colonne nella tabella dati originale.</span><span class="sxs-lookup"><span data-stu-id="e8898-150">If you create goal-seeking predictions for all the rows in the Excel table by specifying **Entire table**, thetool creates two new columns in the original data table.</span></span> <span data-ttu-id="e8898-151">La prima colonna aggiunta alla tabella contiene un segno di spunta all'interno di un cerchio verde, per indicare che l'obiettivo può essere raggiunto, oppure un segno X all'interno di un cerchio rosso, per indicare che non è possibile apportare modifiche che permettano di raggiungere l'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="e8898-151">The first column that is added to the table contains either a check mark in a green circle, to indicate that the goal can be met, or an X mark in a red circle, to indicate that no changes can be made that will enable the goal.</span></span>  
  
 <span data-ttu-id="e8898-152">La seconda colonna contiene la modifica consigliata.</span><span class="sxs-lookup"><span data-stu-id="e8898-152">The second column contains the recommended change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8898-153">Il livello di confidenza dell'indicazione e la relativa efficacia sono predeterminati dall'algoritmo e non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="e8898-153">The confidence level for the recommendation and its success are predetermined by the algorithm and cannot be changed.</span></span>  
  
## <a name="related-tools"></a><span data-ttu-id="e8898-154">Strumenti correlati</span><span class="sxs-lookup"><span data-stu-id="e8898-154">Related Tools</span></span>  
 <span data-ttu-id="e8898-155">Il Client di data mining per Excel, un componente aggiuntivo separato che offre funzionalità di data mining più avanzate, include procedure guidate per la creazione di modelli di data mining in grado di stimare il comportamento.</span><span class="sxs-lookup"><span data-stu-id="e8898-155">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="e8898-156">Per ulteriori informazioni, vedere [creazione di un modello di data mining](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="e8898-156">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
 <span data-ttu-id="e8898-157">Per ulteriori informazioni sull'algoritmo utilizzato dallo strumento per lo scenario di **Ricerca obiettivo** , vedere l'argomento "algoritmo di regressione logistica Microsoft" nella [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] documentazione online di.</span><span class="sxs-lookup"><span data-stu-id="e8898-157">For more information about the algorithm used by the **Goal Seek** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8898-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8898-158">See Also</span></span>  
 [<span data-ttu-id="e8898-159">Strumenti di analisi tabelle per Excel</span><span class="sxs-lookup"><span data-stu-id="e8898-159">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
