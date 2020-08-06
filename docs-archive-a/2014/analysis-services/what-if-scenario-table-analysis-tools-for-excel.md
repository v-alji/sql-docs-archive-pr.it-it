---
title: Scenario di simulazione (strumenti di analisi tabelle per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- what if scenario
- scenario analysis
ms.assetid: 4df5a5c5-1983-4009-a7c5-cd340649fd2f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4bb5c5e866c1320c297fb4f2760bca58623f6601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727148"
---
# <a name="what-if-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="ae966-102">Scenario di Analisi di simulazione (Strumenti di analisi tabelle per Excel)</span><span class="sxs-lookup"><span data-stu-id="ae966-102">What-If Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="ae966-103">![Pulsante di scenario di simulazione in Strumenti di analisi tabelle](media/tat-whatif.gif "Pulsante di scenario di simulazione in Strumenti di analisi tabelle")</span><span class="sxs-lookup"><span data-stu-id="ae966-103">![What If Scenario button in Table Analysis tools](media/tat-whatif.gif "What If Scenario button in Table Analysis tools")</span></span>

 <span data-ttu-id="ae966-104">Lo **strumento scenario di simulazione analizza i modelli** nei dati esistenti e quindi consente di valutare l'effetto delle modifiche apportate a una colonna sul valore di una colonna diversa.</span><span class="sxs-lookup"><span data-stu-id="ae966-104">The **What-If** scenario tool analyzes patterns in existing data, and then enables you to evaluate the effect that changes in one column would have on the value of a different column.</span></span>

 <span data-ttu-id="ae966-105">È ad esempio possibile esaminare l'effetto prodotto sulle vendite totali dall'aumento del prezzo di un articolo.</span><span class="sxs-lookup"><span data-stu-id="ae966-105">For example, you could explore the effect of raising the price of an item on its total sales.</span></span>

 <span data-ttu-id="ae966-106">Lo strumento consente di creare il numero desiderato di stime.</span><span class="sxs-lookup"><span data-stu-id="ae966-106">The tool is flexible about the number of predictions you can create.</span></span> <span data-ttu-id="ae966-107">Dopo aver completato l'analisi iniziale, è possibile effettuare una stima relativa alle modifiche per tutti i dati della tabella o immettere i valori di prova uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="ae966-107">After the initial analysis is complete, you can either predict changes for all the data in the table, or enter test values one at a time.</span></span>

## <a name="using-the-what-if-scenario-tool"></a><span data-ttu-id="ae966-108">Utilizzo dello strumento per scenari di Analisi di simulazione</span><span class="sxs-lookup"><span data-stu-id="ae966-108">Using the What-If Scenario Tool</span></span>

1.  <span data-ttu-id="ae966-109">Aprire una tabella di dati di Excel.</span><span class="sxs-lookup"><span data-stu-id="ae966-109">Open an Excel data table.</span></span>

2.  <span data-ttu-id="ae966-110">Fare clic su **scenari**, quindi **selezionare simulazione**.</span><span class="sxs-lookup"><span data-stu-id="ae966-110">Click **Scenarios**, and then select **What-If**.</span></span>

3.  <span data-ttu-id="ae966-111">Nella casella **scenario** selezionare la colonna che contiene il valore che si vuole modificare e specificare la modifica come valore specifico o come percentuale di modifica (aumentata o ridotta) sui valori correnti.</span><span class="sxs-lookup"><span data-stu-id="ae966-111">In the **Scenario** box, select the column that contains the value you will change, and specify the change either as a specific value or as a percentage of change (either increased or decreased) on the current values.</span></span>

4.  <span data-ttu-id="ae966-112">Nella casella **cosa accade a** specificare la colonna per la quale si desidera valutare l'effetto.</span><span class="sxs-lookup"><span data-stu-id="ae966-112">In the **What happens to** box, specify the column for which you want to assess the effect.</span></span>

5.  <span data-ttu-id="ae966-113">Facoltativamente, fare clic su **Scegli le colonne da utilizzare per l'analisi** per selezionare le colonne che potrebbero essere utili per eseguire la stima.</span><span class="sxs-lookup"><span data-stu-id="ae966-113">Optionally, click **Choose columns to be used for analysis** to select columns that are likely to be useful in making the prediction.</span></span> <span data-ttu-id="ae966-114">È inoltre possibile deselezionare le colonne poco utili per l'individuazione di modelli, ad esempio nomi o ID riga.</span><span class="sxs-lookup"><span data-stu-id="ae966-114">You can also deselect columns that are likely to be of little use in detecting patterns, such as row IDs or names.</span></span>

6.  <span data-ttu-id="ae966-115">Nella casella **specificare la riga o la tabella** scegliere se si desidera che l'effetto venga valutato solo per la riga attualmente selezionata o per il set completo di dati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ae966-115">In the **Specify row or table** box, choose whether you want the impact assessed for the currently selected row only, or for the complete set of data in the table.</span></span>

7.  <span data-ttu-id="ae966-116">Se si seleziona **questa riga**, lo strumento visualizzerà il risultato nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ae966-116">If you select **On this row**, the tool displays the result in the dialog box.</span></span> <span data-ttu-id="ae966-117">Fino a quando la finestra di dialogo rimane aperta, è possibile modificare le opzioni selezionate o testare altri scenari.</span><span class="sxs-lookup"><span data-stu-id="ae966-117">While the dialog box remains open, you can modify your selections to test other scenarios.</span></span>

8.  <span data-ttu-id="ae966-118">Se si seleziona **intera tabella**, lo strumento Visualizza un messaggio di stato nella finestra di dialogo e aggiunge due nuove colonne alla tabella dati originale.</span><span class="sxs-lookup"><span data-stu-id="ae966-118">If you select **Entire table**, the tool displays a status message in the dialog box, and adds two new columns to the original data table.</span></span> <span data-ttu-id="ae966-119">Fare clic su **Chiudi** per visualizzare i risultati completi nel foglio di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ae966-119">Click **Close** to view the complete results in the worksheet.</span></span>

### <a name="requirements"></a><span data-ttu-id="ae966-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae966-120">Requirements</span></span>
 <span data-ttu-id="ae966-121">Questo strumento utilizza l'algoritmo Microsoft Logistic Regression, che supporta la stima di valori numerici o discreti.</span><span class="sxs-lookup"><span data-stu-id="ae966-121">This tool uses the Microsoft Logistic Regression algorithm, which supports prediction of either numeric or discrete values.</span></span> <span data-ttu-id="ae966-122">Per ottenere risultati migliori, è tuttavia consigliabile attenersi alle procedure consigliate seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae966-122">However, to achieve the best results, we suggest the following best practices:</span></span>

-   <span data-ttu-id="ae966-123">Selezionare per l'analisi colonne contenenti informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="ae966-123">Select columns for analysis that contain useful information.</span></span>

-   <span data-ttu-id="ae966-124">Se si include un numero troppo limitato di colonne, potrebbe essere difficile ottenere un risultato.</span><span class="sxs-lookup"><span data-stu-id="ae966-124">If you include too few columns it may be difficult to obtain a result.</span></span>

-   <span data-ttu-id="ae966-125">Se si usa l'opzione **per il valore** , è necessario digitare un valore nella casella o selezionare un valore dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="ae966-125">If you use the **To value** option, you must type a value in the box or select a value from the list.</span></span>

-   <span data-ttu-id="ae966-126">Se si usa l'opzione **percentuale** , impostare la modifica come aumento o riduzione percentuale.</span><span class="sxs-lookup"><span data-stu-id="ae966-126">If you use the **Percentage** option, set the change as a percentage increase or decrease.</span></span> <span data-ttu-id="ae966-127">Il valore predefinito è 120%, ovvero un aumento del 20% rispetto al valore corrente.</span><span class="sxs-lookup"><span data-stu-id="ae966-127">The default is 120%, meaning a 20% increase over the current value.</span></span>

> [!NOTE]
>  <span data-ttu-id="ae966-128">Se non si imposta alcun valore, è possibile che venga visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="ae966-128">If you do not set a value, you might receive an error.</span></span>

## <a name="understanding-the-results-of-what-if-analysis"></a><span data-ttu-id="ae966-129">Informazioni sui risultati dell'analisi di simulazione</span><span class="sxs-lookup"><span data-stu-id="ae966-129">Understanding the Results of What-If Analysis</span></span>
 <span data-ttu-id="ae966-130">Quando si crea uno **scenario di** simulazione, lo strumento esegue tre operazioni:</span><span class="sxs-lookup"><span data-stu-id="ae966-130">When you create a **What-If** scenario, the tool does three things:</span></span>

-   <span data-ttu-id="ae966-131">Creazione di una struttura di data mining per l'archiviazione dei fatti principali relativi ai dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="ae966-131">Creates a data mining structure that stores key facts about the data in your table.</span></span>

-   <span data-ttu-id="ae966-132">Creazione di un modello di data mining per la regressione logistica basato sui dati.</span><span class="sxs-lookup"><span data-stu-id="ae966-132">Creates a logistic regression mining model based on the data.</span></span>

-   <span data-ttu-id="ae966-133">Creazione di una query di stima per ogni valore specificato.</span><span class="sxs-lookup"><span data-stu-id="ae966-133">Creates a prediction query for each of the values you specify.</span></span>

 <span data-ttu-id="ae966-134">È possibile restituire tutte le stime contemporaneamente specificando un' **intera tabella**.</span><span class="sxs-lookup"><span data-stu-id="ae966-134">You can output all the predictions at one time by specifying **Entire table**.</span></span> <span data-ttu-id="ae966-135">Verranno quindi create automaticamente due nuove colonne nella tabella dati originale.</span><span class="sxs-lookup"><span data-stu-id="ae966-135">The tool then creates two new columns in the original data table.</span></span>

 <span data-ttu-id="ae966-136">Nelle colonne che vengono aggiunte alla tabella sono contenuti due tipi di informazioni: il valore stimato prodotto dalla modifica e il relativo livello di confidenza.</span><span class="sxs-lookup"><span data-stu-id="ae966-136">The columns that are added to the table contain two types of information: the predicted value given the change, and its confidence.</span></span> <span data-ttu-id="ae966-137">Per confidenza si intende il grado di probabilità che la stima sia corretta.</span><span class="sxs-lookup"><span data-stu-id="ae966-137">Confidence means the probability that the prediction is correct.</span></span>

 <span data-ttu-id="ae966-138">È inoltre possibile immettere i valori di modifica uno alla volta nella finestra di dialogo e visualizzare le stime in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="ae966-138">You can also enter change values one by one in the dialog box, and view the predictions interactively.</span></span> <span data-ttu-id="ae966-139">Corrisponde alla creazione di una query di *stima singleton*.</span><span class="sxs-lookup"><span data-stu-id="ae966-139">This is the same as creating a *singleton prediction query*.</span></span> <span data-ttu-id="ae966-140">I risultati della query di stima vengono restituiti come output con le informazioni seguenti: avvenuta o mancata esecuzione della stima, valore stimato e livello di confidenza.</span><span class="sxs-lookup"><span data-stu-id="ae966-140">The results of the prediction query are output with the following information: the success or failure of prediction, the predicted value, and the confidence level.</span></span> <span data-ttu-id="ae966-141">Quest'ultimo viene indicato come una barra contenente una linea punteggiata.</span><span class="sxs-lookup"><span data-stu-id="ae966-141">The confidence level is shown as a bar that contains a dotted line.</span></span> <span data-ttu-id="ae966-142">Più è lunga la linea punteggiata, maggiore è il livello di confidenza del risultato.</span><span class="sxs-lookup"><span data-stu-id="ae966-142">The longer the dotted line, the higher the confidence in the result.</span></span>

 <span data-ttu-id="ae966-143">Se, ad esempio, si sta tentando di determinare l'effetto di un aumento della validità del cliente sulla volontà del cliente di acquistare e di aumentare l'età del cliente a 25, **lo strumento di analisi di simulazione** esegue una query sul modello di data mining e restituisce il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="ae966-143">For example, if you are trying to determine the effect of increasing the customer's age on the customer's willingness to buy, and increase the customer's age to 25, the **What-If** tool queries the data mining model and returns the following result:</span></span>

 <span data-ttu-id="ae966-144">**Soluzione trovata dall'analisi di simulazione per Purchases Bicycle.**</span><span class="sxs-lookup"><span data-stu-id="ae966-144">**What-If Analysis for Purchases Bicycle has found a solution.**</span></span>

 <span data-ttu-id="ae966-145">**'Purchases Bicycle' = yes**</span><span class="sxs-lookup"><span data-stu-id="ae966-145">**'Purchases Bicycle' = yes**</span></span>

 <span data-ttu-id="ae966-146">**Confidence: Fair**</span><span class="sxs-lookup"><span data-stu-id="ae966-146">**Confidence: Fair**</span></span>

 <span data-ttu-id="ae966-147">Poiché questo risultato è basato su una riga esistente della tabella dati, indica che, se tutti i dati relativi a un determinato cliente rimangono invariati eccetto l'età, che è stata aumentata a 25 anni, è probabile che il cliente acquisterà una bicicletta.</span><span class="sxs-lookup"><span data-stu-id="ae966-147">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's age was increased to 25, the customer would likely buy a bicycle.</span></span>

 <span data-ttu-id="ae966-148">La restituzione delle stime come output nella tabella dati originale consente di determinare con maggiore facilità se le stime sono utili.</span><span class="sxs-lookup"><span data-stu-id="ae966-148">Outputting the predictions to the original data table might make it easier to determine whether the predictions are useful.</span></span>

## <a name="related-tools"></a><span data-ttu-id="ae966-149">Strumenti correlati</span><span class="sxs-lookup"><span data-stu-id="ae966-149">Related Tools</span></span>
 <span data-ttu-id="ae966-150">Il Client di data mining per Excel, un componente aggiuntivo separato che offre funzionalità di data mining più avanzate, include procedure guidate per la creazione di modelli di data mining in grado di stimare il comportamento.</span><span class="sxs-lookup"><span data-stu-id="ae966-150">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="ae966-151">Per ulteriori informazioni, vedere [creazione di un modello di data mining](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="ae966-151">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="ae966-152">Per ulteriori informazioni sull'algoritmo **utilizzato dallo strumento scenario di** simulazione, vedere l'argomento "algoritmo di regressione logistica Microsoft" in documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae966-152">For more information about the algorithm used by the **What-If** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in SQL Server Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae966-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae966-153">See Also</span></span>
 [<span data-ttu-id="ae966-154">Strumenti di analisi tabelle per Excel</span><span class="sxs-lookup"><span data-stu-id="ae966-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


