---
title: Compilare da esempio (strumenti di analisi tabelle per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- fill from example
ms.assetid: dac57d8f-1c65-4878-8ea0-9c680df5e4fb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 69ff9f554c51240eb6f9151718d30677bfb57996
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715875"
---
# <a name="fill-from-example-table-analysis-tools-for-excel"></a><span data-ttu-id="16b70-102">Estendi da esempio (Strumenti di analisi tabelle per Excel)</span><span class="sxs-lookup"><span data-stu-id="16b70-102">Fill From Example (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="16b70-103">![Pulsante Estendi da esempio in Strumenti di analisi tabelle](media/tat-fillex.gif "Pulsante Estendi da esempio in Strumenti di analisi tabelle")</span><span class="sxs-lookup"><span data-stu-id="16b70-103">![Fill From Example button in Table Analysis Tools](media/tat-fillex.gif "Fill From Example button in Table Analysis Tools")</span></span>  
  
 <span data-ttu-id="16b70-104">Lo strumento **Compila da esempio** consente di compilare nuove colonne di dati in base ai valori esistenti.</span><span class="sxs-lookup"><span data-stu-id="16b70-104">The **Fill From Example** tool helps you build new columns of data based on existing values.</span></span>  
  
 <span data-ttu-id="16b70-105">Si supponga, ad esempio, che i dati contengano una colonna **importo acquisti** , una colonna **Orders Quantity** e una colonna **Customer Premier** basata su una formula che utilizza le altre colonne.</span><span class="sxs-lookup"><span data-stu-id="16b70-105">For example, suppose your data contains a **Purchase Amount** column, an **Orders Quantity** column, and a **Premier Customer** column that is based on some formula using the other columns.</span></span> <span data-ttu-id="16b70-106">Se nella colonna **Customer Premier** sono contenute molte righe vuote, è possibile utilizzare le colonne **purchase amount** e **Orders Quantity** come input per dedurre i valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="16b70-106">If the  **Premier Customer** column contains many blank rows, you could use the **Purchase Amount** and **Orders Quantity** columns as the inputs, to infer the missing values.</span></span> <span data-ttu-id="16b70-107">Lo strumento analizza modelli esistenti nei dati insieme agli esempi immessi e stima la categoria da assegnare a ogni cliente.</span><span class="sxs-lookup"><span data-stu-id="16b70-107">The tool analyzes existing patterns in the data together with the examples you entered, and predicts which category to assign to each customer.</span></span>  
  
 <span data-ttu-id="16b70-108">Se i risultati non sono soddisfacenti, è possibile migliorarli immettendo ulteriori esempi.</span><span class="sxs-lookup"><span data-stu-id="16b70-108">If you are not satisfied with the results, you can refine the results by providing more examples.</span></span>  
  
## <a name="using-the-fill-from-example-tool"></a><span data-ttu-id="16b70-109">Utilizzo dello strumento Estendi da esempio</span><span class="sxs-lookup"><span data-stu-id="16b70-109">Using the Fill From Example Tool</span></span>  
  
1.  <span data-ttu-id="16b70-110">Nella barra multifunzione **analizza** fare clic su **Compila da esempio**.</span><span class="sxs-lookup"><span data-stu-id="16b70-110">In the **Analyze** ribbon, click **Fill From Example**.</span></span>  
  
2.  <span data-ttu-id="16b70-111">Tramite lo strumento viene automaticamente selezionata la colonna da compilare in base all'analisi dei dati ed è possibile accettare o ignorare il suggerimento.</span><span class="sxs-lookup"><span data-stu-id="16b70-111">The tool will automatically pick a column to fill based on analysis of the data, and you can either accept or override this suggestion.</span></span>  
  
3.  <span data-ttu-id="16b70-112">Creare una colonna per i nuovi dati e digitare esempi dei valori che si desidera stimare.</span><span class="sxs-lookup"><span data-stu-id="16b70-112">Create a column for the new data, and type in examples of the data that you want to predict.</span></span> <span data-ttu-id="16b70-113">Verificare che sia presente almeno un esempio per ogni valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="16b70-113">Make sure that there is at least one example for every value that you want to predict.</span></span> <span data-ttu-id="16b70-114">Se si immettono i dati in una colonna esistente, selezionare la colonna con valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="16b70-114">If you are filling in data in an existing column, select the column that has missing values.</span></span>  
  
4.  <span data-ttu-id="16b70-115">Facoltativamente, fare clic su **Scegli colonne da utilizzare nell'analisi**.</span><span class="sxs-lookup"><span data-stu-id="16b70-115">Optionally, click **Choose columns to be used in analysis**.</span></span> <span data-ttu-id="16b70-116">Nella finestra di dialogo **Selezione colonne avanzate** specificare le colonne che più probabilmente saranno utili quando si compilano i dati mancanti.</span><span class="sxs-lookup"><span data-stu-id="16b70-116">In the **Advanced Columns Selection** dialog box, specify the columns that are most likely to be useful when filling in the missing data.</span></span>  
  
     <span data-ttu-id="16b70-117">Se, per esperienza, si sa che esiste un rapporto di causa-effetto tra una colonna e la colonna con valori mancanti, è possibile deselezionare le altre colonne per ottenere risultati migliori.</span><span class="sxs-lookup"><span data-stu-id="16b70-117">For example, if you know from experience that there is a causal effect between one column and the column that has missing values, you can deselect other columns to get better results.</span></span>  
  
     <span data-ttu-id="16b70-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="16b70-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="16b70-119">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="16b70-119">Click **Run**.</span></span>  
  
     <span data-ttu-id="16b70-120">Al termine dell'analisi, lo strumento crea un nuovo foglio di **disegno** che contiene i risultati dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="16b70-120">When analysis is complete, the tool creates a new **Patterns** worksheet that contains the results of analysis.</span></span> <span data-ttu-id="16b70-121">Nel report vengono elencate le regole, o fattori di influenza chiave, trovati e viene visualizzata la probabilità per ogni regola.</span><span class="sxs-lookup"><span data-stu-id="16b70-121">The report lists the rules, or key influencers, that were found, and shows the probability for each rule.</span></span>  
  
     <span data-ttu-id="16b70-122">Nella tabella dati originale viene aggiunta automaticamente una colonna contenente i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="16b70-122">The tool also automatically adds a column that contains the new values to the original data table.</span></span> <span data-ttu-id="16b70-123">È possibile esaminare tali valori e confrontarli con l'originale.</span><span class="sxs-lookup"><span data-stu-id="16b70-123">You can review the values and compare them against the original.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="16b70-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16b70-124">Requirements</span></span>  
 <span data-ttu-id="16b70-125">È possibile utilizzare lo strumento solo sui dati disponibili in colonne.</span><span class="sxs-lookup"><span data-stu-id="16b70-125">You can only work with data in columns.</span></span> <span data-ttu-id="16b70-126">Se la serie che si desidera completare è archiviata in una riga, è possibile utilizzare la funzionalità Incolla, Trasponi in Excel per convertire i dati nel formato a colonne.</span><span class="sxs-lookup"><span data-stu-id="16b70-126">If the series that you want to fill is stored in a row, you can use the Paste, Transpose function in Excel to change the data to a columnar format.</span></span>  
  
## <a name="understanding-the-pattern-report"></a><span data-ttu-id="16b70-127">Informazioni sul report dei modelli</span><span class="sxs-lookup"><span data-stu-id="16b70-127">Understanding the Pattern Report</span></span>  
 <span data-ttu-id="16b70-128">Quando si esegue lo strumento **Compila da esempio** , viene creato un report che fornisce ulteriori informazioni sui modelli rilevati.</span><span class="sxs-lookup"><span data-stu-id="16b70-128">When you run the **Fill From Example** tool, a report is created that provides more information about the patterns that were detected.</span></span> <span data-ttu-id="16b70-129">Questi modelli vengono utilizzati per estrapolare i nuovi valori dei dati.</span><span class="sxs-lookup"><span data-stu-id="16b70-129">These patterns are used for extrapolating new data values.</span></span>  
  
 <span data-ttu-id="16b70-130">Nel report dei modelli sono indicati i fattori di influenza chiave per ogni valore stimato.</span><span class="sxs-lookup"><span data-stu-id="16b70-130">The Pattern Report shows the key influencers for each value that was predicted.</span></span> <span data-ttu-id="16b70-131">Ogni fattore di influenza o regola viene descritto come combinazione di colonna, valore della colonna e impatto relativo della regola sulla stima.</span><span class="sxs-lookup"><span data-stu-id="16b70-131">Each influencer or rule is described as a combination of a column, the value in that column, and the relative impact of the rule on the prediction.</span></span>  
  
 <span data-ttu-id="16b70-132">Ad esempio, se è necessario completare un foglio di lavoro che indica la distanza di spedizione per gli ordini, è prevedibile da un punto di vista logico che la destinazione abbia un impatto significativo sul valore della distanza di spedizione.</span><span class="sxs-lookup"><span data-stu-id="16b70-132">For example, if you were trying to fill in a worksheet that shows the shipping distance for orders, you might logically expect the destination to have a strong impact on the value for shipping distance.</span></span> <span data-ttu-id="16b70-133">In questo caso, il report potrebbe contenere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="16b70-133">In this case, the report might contain the following row:</span></span>  
  
|<span data-ttu-id="16b70-134">Colonna</span><span class="sxs-lookup"><span data-stu-id="16b70-134">Column</span></span>|<span data-ttu-id="16b70-135">Valore</span><span class="sxs-lookup"><span data-stu-id="16b70-135">Value</span></span>|<span data-ttu-id="16b70-136">Predilige</span><span class="sxs-lookup"><span data-stu-id="16b70-136">Favors</span></span>|<span data-ttu-id="16b70-137">Impatto relativo</span><span class="sxs-lookup"><span data-stu-id="16b70-137">Relative Impact</span></span>|  
|------------|-----------|------------|---------------------|  
|<span data-ttu-id="16b70-138">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="16b70-138">StateProvinceCode</span></span>|<span data-ttu-id="16b70-139">AB</span><span class="sxs-lookup"><span data-stu-id="16b70-139">AB</span></span>|<span data-ttu-id="16b70-140">>500 chilometri</span><span class="sxs-lookup"><span data-stu-id="16b70-140">>500 kilometers</span></span>|<span data-ttu-id="16b70-141">80%</span><span class="sxs-lookup"><span data-stu-id="16b70-141">80%</span></span>|  
  
 <span data-ttu-id="16b70-142">Questo significa che il valore AB nella colonna **StateProvinceCode** stima fortemente una distanza di spedizione di >500 chilometri.</span><span class="sxs-lookup"><span data-stu-id="16b70-142">This means that the value AB in the **StateProvinceCode** column strongly predicts a shipping distance of >500 kilometers.</span></span>  
  
 <span data-ttu-id="16b70-143">Le stime sono in genere basate su modelli molto più complessi rispetto a questo esempio e il report potrebbe includere numerose righe di regole per ogni stima.</span><span class="sxs-lookup"><span data-stu-id="16b70-143">Typically, predictions are based on patterns that are far more complex than this example, and the report may contain many rows of rules for each prediction.</span></span> <span data-ttu-id="16b70-144">Per derivare il valore stimato vengono combinati gli effetti di tutte le regole.</span><span class="sxs-lookup"><span data-stu-id="16b70-144">The effect of all the rules are combined to derive the predicted value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16b70-145">L' **effetto relativo** viene visualizzato come una barra ombreggiata.</span><span class="sxs-lookup"><span data-stu-id="16b70-145">**Relative Impact** is shown as a shaded bar.</span></span> <span data-ttu-id="16b70-146">Più lunga è la barra, maggiore è la probabilità che la regola sia predittiva per il valore inserito.</span><span class="sxs-lookup"><span data-stu-id="16b70-146">The longer the bar, the greater the probability that this rule is predictive of the filled-in value.</span></span>  
  
 <span data-ttu-id="16b70-147">Lo strumento aggiunge anche una nuova colonna alla tabella dati originale, denominata \<column name> Extended.</span><span class="sxs-lookup"><span data-stu-id="16b70-147">The tool also adds a new column to the original data table, named \<column name> Extended.</span></span>  
  
 <span data-ttu-id="16b70-148">Se la colonna dei dati originale contiene un valore, tale valore viene copiato nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="16b70-148">If the original data column contained a value, that value is copied into the new column.</span></span> <span data-ttu-id="16b70-149">Se la colonna originale contiene una cella vuota, invece, la nuova colonna conterrà il valore stimato dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="16b70-149">However, if the original column contained a blank cell, the new column contains the value that was predicted by the wizard.</span></span>  
  
## <a name="related-tools-and-information"></a><span data-ttu-id="16b70-150">Strumenti e informazioni correlati</span><span class="sxs-lookup"><span data-stu-id="16b70-150">Related Tools and Information</span></span>  
 <span data-ttu-id="16b70-151">È inoltre possibile utilizzare la procedura guidata [esplorazione dati](explore-data-sql-server-data-mining-add-ins.md) , disponibile nel client di data mining per Excel, per esaminare la distribuzione dei valori in una colonna di Excel.</span><span class="sxs-lookup"><span data-stu-id="16b70-151">You can also use the [Explore Data](explore-data-sql-server-data-mining-add-ins.md) wizard, available in the Data Mining Client for Excel, to examine the distribution of values in an Excel column.</span></span> <span data-ttu-id="16b70-152">Per ulteriori informazioni, vedere [esplorazione e pulizia dei dati](exploring-and-cleaning-data.md).</span><span class="sxs-lookup"><span data-stu-id="16b70-152">For more information, see [Exploring and Cleaning Data](exploring-and-cleaning-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b70-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16b70-153">See Also</span></span>  
 [<span data-ttu-id="16b70-154">Strumenti di analisi tabelle per Excel</span><span class="sxs-lookup"><span data-stu-id="16b70-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
