---
title: Rilevare le categorie (strumenti di analisi tabelle per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- clustering [data mining]
- mining model, decision tree
- category detection
ms.assetid: 3c7e9ebb-d0c9-498e-a9ba-cc13eaa43520
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4874c85d7e4ab65716741e8ae9433406dfb08b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722016"
---
# <a name="detect-categories-table-analysis-tools-for-excel"></a><span data-ttu-id="b5a5f-102">Rileva categorie (Strumenti di analisi tabelle per Excel)</span><span class="sxs-lookup"><span data-stu-id="b5a5f-102">Detect Categories (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="b5a5f-103">![Pulsante Rileva categorie sulla barra multifunzione](media/tat-detectcat.gif "Pulsante Rileva categorie sulla barra multifunzione")</span><span class="sxs-lookup"><span data-stu-id="b5a5f-103">![Detect Categories button in ribbon](media/tat-detectcat.gif "Detect Categories button in ribbon")</span></span>

 <span data-ttu-id="b5a5f-104">Lo strumento **Rileva categorie** consente di trovare automaticamente le righe in una tabella con caratteristiche simili.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-104">The **Detect Categories** tool automatically finds rows in a table that have similar characteristics.</span></span>

 <span data-ttu-id="b5a5f-105">Al termine dell'esecuzione dello strumento, viene creato un report in cui sono elencate tutte le categorie trovate, insieme alle relative caratteristiche distintive.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-105">When the tool finishes, it creates a report that lists the categories it found, together with their distinguishing characteristics.</span></span> <span data-ttu-id="b5a5f-106">Per impostazione predefinita, nella tabella dati contenente la categoria proposta viene aggiunta una nuova colonna per ogni riga di dati.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-106">By default, it adds a new column to the data table that contains the proposed category for each row of your data.</span></span> <span data-ttu-id="b5a5f-107">È quindi possibile esaminare le categorie e rinominarle.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-107">You can then review the categories and rename them.</span></span>

## <a name="using-the-detect-categories-tool"></a><span data-ttu-id="b5a5f-108">Utilizzo dello strumento Rileva categorie</span><span class="sxs-lookup"><span data-stu-id="b5a5f-108">Using the Detect Categories Tool</span></span>

1.  <span data-ttu-id="b5a5f-109">Aprire una tabella di Excel.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-109">Open an Excel table.</span></span>

2.  <span data-ttu-id="b5a5f-110">Fare clic su **Rileva categorie**.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-110">Click **Detect Categories**.</span></span>

3.  <span data-ttu-id="b5a5f-111">Specificare le colonne da utilizzare nell'analisi.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-111">Specify the columns to use in analysis.</span></span> <span data-ttu-id="b5a5f-112">È possibile deselezionare le colonne contenenti valori distinti, ad esempio nomi o ID di record, poiché non sono utili per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-112">You can deselect columns that have distinct values, such as personal names or record IDs, because these columns might not be useful for analysis.</span></span>

4.  <span data-ttu-id="b5a5f-113">È possibile specificare il numero massimo di categorie da creare.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-113">Optionally, specify the maximum number of categories to create.</span></span> <span data-ttu-id="b5a5f-114">Per impostazione predefinita, vengono create automaticamente tutte le categorie trovate dallo strumento.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-114">By default, the tool automatically creates as many categories as it finds.</span></span>

5.  <span data-ttu-id="b5a5f-115">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-115">Click **Run**.</span></span>

6.  <span data-ttu-id="b5a5f-116">Tramite lo strumento viene creato un nuovo foglio di lavoro, denominato Report categorie, contenente l'elenco delle categorie e le relative caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-116">The tool creates a new worksheet, named Categories Report, which contains the list of categories and their characteristics.</span></span>

 <span data-ttu-id="b5a5f-117">Per ulteriori informazioni su come specificare le opzioni per lo strumento, vedere [finestra di dialogo Rileva categorie (strumenti di analisi tabelle per Excel)](detect-categories-table-analysis-tools-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b5a5f-117">For more information about how to specify options for the tool, see [Detect Categories Dialog Box (Table Analysis Tools for Excel)](detect-categories-table-analysis-tools-for-excel.md).</span></span>

## <a name="understanding-the-categories-report"></a><span data-ttu-id="b5a5f-118">Informazioni su Report categorie</span><span class="sxs-lookup"><span data-stu-id="b5a5f-118">Understanding the Categories Report</span></span>
 <span data-ttu-id="b5a5f-119">Il **report categorie** contiene due tabelle, le caratteristiche **elenco** categorie e **categoria**e un grafico **Profili categoria** .</span><span class="sxs-lookup"><span data-stu-id="b5a5f-119">The **Categories Report** contains two tables, **Category List** and **Category Characteristics**, and a **Category Profiles** chart.</span></span>

### <a name="category-list"></a><span data-ttu-id="b5a5f-120">Elenco di categorie</span><span class="sxs-lookup"><span data-stu-id="b5a5f-120">Category List</span></span>
 <span data-ttu-id="b5a5f-121">Nella prima tabella sono elencate le categorie trovate.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-121">The first table lists the categories that were found.</span></span> <span data-ttu-id="b5a5f-122">La colonna **conteggio** righe indica il numero di righe di dati assegnate a ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-122">The **Row Count** column indicates how many rows of data were assigned to each category.</span></span>

 <span data-ttu-id="b5a5f-123">Il modello crea nomi temporanei per ogni categoria, ma è possibile rinominare le categorie come si desidera.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-123">The model creates temporary names for each category, but you can rename the categories as you like.</span></span> <span data-ttu-id="b5a5f-124">Nell'esempio seguente, ad esempio, la prima categoria è stata rinominata **low income**, perché questo è l'attributo principale del cluster.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-124">For example, in the following example, the first category has been renamed **Low Income**, because that was the top attribute of the cluster.</span></span>

 <span data-ttu-id="b5a5f-125">![Report creato dallo strumento Rileva categorie](media/dm13-tat-detectcat-report1.gif "Report creato dallo strumento Rileva categorie")</span><span class="sxs-lookup"><span data-stu-id="b5a5f-125">![report created by Detect Categories tool](media/dm13-tat-detectcat-report1.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="b5a5f-126">Non appena si digita la nuova etichetta, la modifica viene propagata a tutti gli altri grafici e all'elenco di categorie aggiunto nel foglio di lavoro dati di origine.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-126">As soon as you type the new label, the change is propagated to all the other charts as well as to the category list added in the source data worksheet.</span></span>

### <a name="category-characteristics"></a><span data-ttu-id="b5a5f-127">Caratteristiche categoria</span><span class="sxs-lookup"><span data-stu-id="b5a5f-127">Category Characteristics</span></span>
 <span data-ttu-id="b5a5f-128">La seconda tabella, **categoria caratteristiche**, Mostra i dettagli relativi alla composizione di ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-128">The second table, **Category Characteristics**, shows details about the makeup of each category.</span></span> <span data-ttu-id="b5a5f-129">Fare clic sul pulsante **filtro** nella parte superiore della colonna **categoria** per visualizzare lo stato attivo su una o solo alcune categorie.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-129">Click the **Filter** button at the top of the **Category** column to see focus on one or just a few categories.</span></span>

 <span data-ttu-id="b5a5f-130">![Report creato dallo strumento Rileva categorie](media/dm13-tat-detectcat-report2.gif "Report creato dallo strumento Rileva categorie")</span><span class="sxs-lookup"><span data-stu-id="b5a5f-130">![report created by Detect Categories tool](media/dm13-tat-detectcat-report2.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="b5a5f-131">L'ombreggiatura nella colonna relativa all' **importanza relativa**indica l'importanza della combinazione di attributo e valore come fattore di distinzione.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-131">The shading in the column, **Relative Importance**, indicates how important that combination of attribute and value is as a distinguishing factor.</span></span> <span data-ttu-id="b5a5f-132">Più è lunga la barra, più è probabile che l'attributo sia fortemente rappresentativo della categoria.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-132">The longer the bar, the more likely it is that this attribute is strongly representative of this category.</span></span>

### <a name="categories-profile-chart"></a><span data-ttu-id="b5a5f-133">Grafico Profili categoria</span><span class="sxs-lookup"><span data-stu-id="b5a5f-133">Categories Profile Chart</span></span>
 <span data-ttu-id="b5a5f-134">Il grafico finale nel foglio di calcolo del **report Categories** , **Profili categoria**, è un **grafico pivot** interattivo che è possibile utilizzare per ridisporre e nascondere i campi, filtrare i valori e personalizzare l'aspetto del grafico.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-134">The final chart in the **Categories Report** worksheet, **Category Profiles**, is an interactive **Pivot Chart** that you can use to rearrange and hide fields, filter on values, and customize the chart's appearance.</span></span>

 <span data-ttu-id="b5a5f-135">In Excel 2013 sono ora disponibili gli **stili dei grafici** e i controlli **degli elementi del grafico** direttamente nell'area di progettazione che semplificano il miglioramento della progettazione del grafico.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-135">Excel 2013 now provides **Chart Styles** and **Chart Elements** controls right in the design surface that make it easy to improve the chart design.</span></span>

 <span data-ttu-id="b5a5f-136">![Report creato dallo strumento Rileva categorie](media/dm13-tat-detectcat-report3.gif "Report creato dallo strumento Rileva categorie")</span><span class="sxs-lookup"><span data-stu-id="b5a5f-136">![report created by Detect Categories tool](media/dm13-tat-detectcat-report3.gif "report created by Detect Categories tool")</span></span>

## <a name="requirements"></a><span data-ttu-id="b5a5f-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5a5f-137">Requirements</span></span>
 <span data-ttu-id="b5a5f-138">Lo strumento **Rileva categorie** non prevede requisiti per la quantità o il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-138">The **Detect Categories** tool has no requirements for the amount or type of data.</span></span>

> [!NOTE]
>  <span data-ttu-id="b5a5f-139">Quando si utilizza lo strumento **Rileva categorie** , viene creata una nuova colonna, Category, nella tabella dati originale.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-139">When you use the **Detect Categories** tool, it creates a new column, Category, in the original data table.</span></span> <span data-ttu-id="b5a5f-140">Se si lascia questa colonna nella tabella dati e quindi si eseguono successivamente operazioni di data mining, è possibile che i risultati vengano falsati dalla presenza di tale colonna.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-140">If you leave this column in the data table and then perform subsequent data mining operations, the presence of this column could influence your results.</span></span> <span data-ttu-id="b5a5f-141">Per evitare questo problema, è consigliabile creare una copia della tabella dati senza la colonna Categoria prima di utilizzare altri strumenti di data mining.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-141">To ensure that this does not affect other operations, you should make a copy of the data table without the Category column before using other data mining tools.</span></span>

## <a name="related-tools"></a><span data-ttu-id="b5a5f-142">Strumenti correlati</span><span class="sxs-lookup"><span data-stu-id="b5a5f-142">Related Tools</span></span>
 <span data-ttu-id="b5a5f-143">Quando lo strumento **Rileva categorie** analizza i dati, crea una struttura data mining e data mining modello usando l' [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Clustering.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-143">When the **Detect Categories** tool analyzes your data, it creates a data mining structure and data mining model by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span>

 <span data-ttu-id="b5a5f-144">Dopo aver creato un modello di data mining utilizzando lo strumento **Analizza fattori di influenza chiave** , è possibile utilizzare il client di data mining per Excel per esplorare il modello ed esplorare le relazioni in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-144">After you have created a data mining model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client for Excel to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="b5a5f-145">Il Client di data mining per Excel è un componente aggiuntivo separato in cui sono disponibili funzionalità di data mining più avanzate.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-145">The Data Mining Client for Excel is a separate add-in that provides more advanced data mining functionality.</span></span> <span data-ttu-id="b5a5f-146">Per informazioni, vedere [esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data Mining&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="b5a5f-146">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>

 <span data-ttu-id="b5a5f-147">Per ulteriori informazioni sull'utilizzo delle funzionalità di modellazione dei dati nel client di data mining per Excel, vedere [creazione di un modello di data mining](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="b5a5f-147">For more information about using the data modeling capabilities in the Data Mining Client for Excel, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="b5a5f-148">Per ulteriori informazioni sull'algoritmo utilizzato dallo strumento **Rileva categorie** , vedere l'argomento "algoritmo Microsoft Clustering" nella [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] documentazione online di.</span><span class="sxs-lookup"><span data-stu-id="b5a5f-148">For more information about the algorithm used by the **Detect Categories** tool, see the topic "Microsoft Clustering Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5a5f-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5a5f-149">See Also</span></span>
 [<span data-ttu-id="b5a5f-150">Strumenti di analisi tabelle per Excel</span><span class="sxs-lookup"><span data-stu-id="b5a5f-150">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


