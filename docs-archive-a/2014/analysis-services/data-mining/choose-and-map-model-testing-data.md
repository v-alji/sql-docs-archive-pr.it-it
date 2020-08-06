---
title: Scegliere ed eseguire il mapping dei dati di test del modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining accuracy charts
- Mining Accuracy Chart [Analysis Services], column mappings
- input column mapping [Analysis Services]
- mapping input columns [Analysis Services]
ms.assetid: be0d9f20-40c3-4dac-81da-281cfe724126
author: minewiskan
ms.author: owend
ms.openlocfilehash: 84f1d01c40070069d610bb028ab003223c5afbcd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627551"
---
# <a name="choose-and-map-model-testing-data"></a><span data-ttu-id="36293-102">Scegliere ed eseguire il mapping dei dati di test del modello</span><span class="sxs-lookup"><span data-stu-id="36293-102">Choose and Map Model Testing Data</span></span>
  <span data-ttu-id="36293-103">Per creare un grafico di accuratezza in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], è necessario scegliere i dati che verranno utilizzati per il test del modello ed eseguire il mapping dei dati al modello.</span><span class="sxs-lookup"><span data-stu-id="36293-103">To create an accuracy chart in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must choose the data that will be used to test the model, and map the data to the model.</span></span>  
  
 <span data-ttu-id="36293-104">Per impostazione predefinita, in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] verranno utilizzati i dati di test del modello di data mining, a condizione che sia stato creato un set di dati di controllo al momento della compilazione della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="36293-104">By default, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will use the mining model testing data, provided that you created a holdout data set when you built the mining structure.</span></span> <span data-ttu-id="36293-105">La creazione di un set di test di controllo rappresenta il modo più semplice per testare i modelli basati sulla stessa struttura di data mining perché i nomi delle colonne e i tipi di dati corrisponderanno sempre al modello e si può essere ragionevolmente certi che la distribuzione dei dati sia simile.</span><span class="sxs-lookup"><span data-stu-id="36293-105">Creating a holdout test set is the easiest way to test models that are based on the same mining structure, because the column names and data types will always match the model, and you can be reasonably assured that the distribution of the data is similar.</span></span> <span data-ttu-id="36293-106">Nella finestra di progettazione verranno inoltre create automaticamente le relazioni tra le colonne di input e le colonne del modello.</span><span class="sxs-lookup"><span data-stu-id="36293-106">Also, the designer will automatically create the relationships between the input and model columns.</span></span>  
  
 <span data-ttu-id="36293-107">In alternativa, è possibile specificare un'origine esterna dei dati.</span><span class="sxs-lookup"><span data-stu-id="36293-107">Alternatively, you can specify an external source of data.</span></span> <span data-ttu-id="36293-108">Per i dati esterni, esistono alcuni requisiti aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="36293-108">For external data, there are some additional requirements:</span></span>  
  
-   <span data-ttu-id="36293-109">Il set di dati esterno deve essere definito come vista origine dati in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36293-109">The external data set must be defined as a data source view in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="36293-110">Il set di dati esterno deve contenere almeno una colonna di cui sia possibile eseguire il mapping alla colonna stimabile del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="36293-110">The external data set must at least contain one column that can be mapped to the predictable column in the mining model.</span></span> <span data-ttu-id="36293-111">È possibile scegliere di ignorare alcune colonne.</span><span class="sxs-lookup"><span data-stu-id="36293-111">You can choose to ignore some columns.</span></span>  
  
-   <span data-ttu-id="36293-112">Non è possibile aggiungere nuove colonne o eseguire il mapping di colonne in una vista origine dati diversa.</span><span class="sxs-lookup"><span data-stu-id="36293-112">You cannot add new columns or map columns in a different data source view.</span></span> <span data-ttu-id="36293-113">La vista origine dati selezionata deve contenere tutte le colonne necessarie per la query di stima.</span><span class="sxs-lookup"><span data-stu-id="36293-113">The data source view that you select must contain all the columns that you need for the prediction query.</span></span>  
  
-   <span data-ttu-id="36293-114">Se i nomi delle colonne esterne corrispondono esattamente a quelli nel modello, il mapping verrà eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="36293-114">If the external column names exactly match those in the model, the designer will map them for you.</span></span> <span data-ttu-id="36293-115">Se i mapping non sono corretti, è possibile modificarli o eliminare e creare nuovi mapping per colonne esistenti.</span><span class="sxs-lookup"><span data-stu-id="36293-115">If the mappings are wrong, you can change them, or delete and create new mappings for existing columns.</span></span>  
  
-   <span data-ttu-id="36293-116">Se si utilizza un'origine dati esterna, è possibile applicare i filtri per limitare i dati di test a un subset attinente di case.</span><span class="sxs-lookup"><span data-stu-id="36293-116">If you use an external data source, you can apply filters to restrict the testing data to a relevant subset of cases.</span></span>  
  
-   <span data-ttu-id="36293-117">Anche quando si utilizza il set di test di controllo, è necessario ricordare che i filtri possono creare differenze tra i dati di test associati a una struttura di data mining e i test case del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="36293-117">Even when you use the holdout test set, you should be aware that filters can cause differences between the testing data associated with a mining structure and the mining model test cases.</span></span>  
  
 <span data-ttu-id="36293-118">In questo argomento viene illustrato come scegliere ed eseguire il mapping dei dati di test:</span><span class="sxs-lookup"><span data-stu-id="36293-118">This topic describes how to choose and map the testing data:</span></span>  
  
 [<span data-ttu-id="36293-119">Selezionare le tabelle di input per testare l'accuratezza di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="36293-119">Select input tables to test the accuracy of a mining model</span></span>](#bkmk_SelectInputs)  
  
 [<span data-ttu-id="36293-120">Eseguire il mapping delle colonne del modello alle colonne nei dati di test</span><span class="sxs-lookup"><span data-stu-id="36293-120">Map model columns to the columns in the testing data</span></span>](#bkmk_MapColumns)  
  
 [<span data-ttu-id="36293-121">Modificare il mapping delle colonne nei dati di test al modello</span><span class="sxs-lookup"><span data-stu-id="36293-121">Change the way that columns in the testing data are mapped to the model</span></span>](#bkmk_ChangeMappings)  
  
##  <a name="to-select-input-tables-to-test-the-accuracy-of-a-mining-model"></a><a name="bkmk_SelectInputs"></a> <span data-ttu-id="36293-122">Per selezionare le tabelle di input per testare l'accuratezza di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="36293-122">To select input tables to test the accuracy of a mining model</span></span>  
  
1.  <span data-ttu-id="36293-123">Nella Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare doppio clic sulla struttura di data mining che contiene i modelli di cui tracciare il grafico.</span><span class="sxs-lookup"><span data-stu-id="36293-123">In Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="36293-124">Selezionare la scheda **Grafico di accuratezza modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="36293-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="36293-125">Nella scheda **Selezione input** della vista **Grafico accuratezza modello di data mining** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36293-125">On the **Input Selection Tab** of the **Mining Accuracy Chart** view, select one of the following options:</span></span>  
  
     <span data-ttu-id="36293-126">**Utilizza test case del modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="36293-126">**Use mining model test cases**</span></span>  
  
     <span data-ttu-id="36293-127">**Utilizza test case della struttura di data mining**</span><span class="sxs-lookup"><span data-stu-id="36293-127">**Use mining structure test cases**</span></span>  
  
     <span data-ttu-id="36293-128">**Specifica un set di dati diverso**</span><span class="sxs-lookup"><span data-stu-id="36293-128">**Specify a different data set**</span></span>  
  
4.  <span data-ttu-id="36293-129">Se è stato selezionato **Specifica un set di dati diverso**, è possibile fare clic facoltativamente su **Apri editor filtri** per creare condizioni di filtro nei set di dati di input.</span><span class="sxs-lookup"><span data-stu-id="36293-129">If you selected **Specify a different data set**, optionally click **Open Filter Editor** to create filter conditions on the input data set.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="36293-130">Fare clic sulla scheda **Grafico di accuratezza** o **Matrice di classificazione** per compilare automaticamente il grafico utilizzando i dati di test specificati.</span><span class="sxs-lookup"><span data-stu-id="36293-130">Click the **Lift Chart** tab or the **Classification Matrix** tab to automatically build the chart by using the testing data you specified.</span></span>  
  
##  <a name="to-map-model-columns-to-the-columns-in-the-testing-data"></a><a name="bkmk_MapColumns"></a> <span data-ttu-id="36293-131">Per eseguire il mapping delle colonne del modello alle colonne nei dati di test</span><span class="sxs-lookup"><span data-stu-id="36293-131">To map model columns to the columns in the testing data</span></span>  
  
1.  <span data-ttu-id="36293-132">Fare doppio clic sulla struttura di data mining contenente i modelli per i quali creare il grafico per aprire la struttura e i modelli in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="36293-132">Double-click the mining structure that contains the models you want to chart, to open the structure and models in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="36293-133">Selezionare la scheda **Grafico di accuratezza modello di data mining** , quindi selezionare la scheda **Selezione input** .</span><span class="sxs-lookup"><span data-stu-id="36293-133">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="36293-134">Nell'area **Seleziona set di dati da utilizzare per il grafico di accuratezza** della scheda **Selezione input**selezionare l'opzione **Specifica un set di dati diverso**.</span><span class="sxs-lookup"><span data-stu-id="36293-134">In the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="36293-135">Fare clic sul pulsante Sfoglia **(...)** per aprire una finestra di dialogo e compilare la definizione del set di dati esterno.</span><span class="sxs-lookup"><span data-stu-id="36293-135">Click the browse button **(...)** to open a dialog box and build the definition of the external data set.</span></span>  
  
5.  <span data-ttu-id="36293-136">Nella finestra di dialogo **Seleziona struttura di data mining** selezionare la struttura di data mining contenente i modelli che si desidera utilizzare e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="36293-136">In the **Select Mining Structure** dialog box, select the mining structure that contains the models you want to work with, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="36293-137">Nella tabella **Seleziona tabelle di input** della scheda **Grafico accuratezza modello di data mining** fare clic su **Seleziona tabella del case** per aprire la finestra di dialogo **Seleziona tabella** .</span><span class="sxs-lookup"><span data-stu-id="36293-137">On the **Select Input Table(s)** table of the **Mining Accuracy Chart** tab, click **Select Case Table** to open the **Select Table** dialog box.</span></span>  
  
7.  <span data-ttu-id="36293-138">Nella finestra di dialogo **Seleziona tabella** selezionare un'origine dati nell'elenco **Origine dati** .</span><span class="sxs-lookup"><span data-stu-id="36293-138">In the **Select Table** dialog box, select a data source from the **Data Source** list.</span></span> <span data-ttu-id="36293-139">Scegliere una tabella contenente i dati che si desidera utilizzare nella query di stima per determinare l'accuratezza dei modelli.</span><span class="sxs-lookup"><span data-stu-id="36293-139">Choose a table that contains the data that you want to use in the prediction queries to determine the accuracy of the models.</span></span>  
  
8.  <span data-ttu-id="36293-140">Nella casella **Nome tabella/vista** selezionare la tabella contenente i dati che si desidera usare per testare i modelli.</span><span class="sxs-lookup"><span data-stu-id="36293-140">In the **Table/View Name** box, select the table that contains the data that you want to use to test the models.</span></span>  
  
9. <span data-ttu-id="36293-141">Modificare i mapping, se necessario.</span><span class="sxs-lookup"><span data-stu-id="36293-141">Edit the mappings, if necessary.</span></span> <span data-ttu-id="36293-142">Verrà automaticamente eseguito il mapping tra le colonne della struttura di data mining e le colonne con lo stesso nome incluse nella tabella di input.</span><span class="sxs-lookup"><span data-stu-id="36293-142">Columns in the mining structure are automatically mapped to the columns with the same name in the input table.</span></span> <span data-ttu-id="36293-143">Per creare mapping manualmente, fare clic su una colonna nella tabella **Seleziona tabelle di input** e trascinarla sulla colonna corrispondente nella tabella **Struttura di data mining** .</span><span class="sxs-lookup"><span data-stu-id="36293-143">To manually create mappings, click a column in the **Select Input Table(s)** table and drag it onto the corresponding column in the **Mining Structure** table.</span></span> <span data-ttu-id="36293-144">Per eliminare un mapping, fare clic sulla linea che collega la colonna contenuta nella tabella **Struttura di data mining** alla colonna contenuta nella tabella **Seleziona tabelle di input** , quindi premere CANC.</span><span class="sxs-lookup"><span data-stu-id="36293-144">To delete a mapping, click the line that links the column in the **Mining Structure** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="to-modify-the-way-input-data-is-mapped-to-the-model"></a><a name="bkmk_ChangeMappings"></a><span data-ttu-id="36293-145">Per modificare la modalità di mapping dei dati di input al modello</span><span class="sxs-lookup"><span data-stu-id="36293-145">To modify the way input data is mapped to the model</span></span>  
  
1.  <span data-ttu-id="36293-146">In Progettazione modelli di data mining fare doppio clic sulla struttura che contiene i modelli di cui tracciare il grafico.</span><span class="sxs-lookup"><span data-stu-id="36293-146">In Data Mining Designer, double-click the structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="36293-147">Selezionare la scheda **Grafico di accuratezza modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="36293-147">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="36293-148">Fare clic sulla scheda **Selezione input** .</span><span class="sxs-lookup"><span data-stu-id="36293-148">Click the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="36293-149">In **Seleziona set di dati da utilizzare per il grafico di accuratezza**selezionare l'opzione **specifica un set di dati diverso**.</span><span class="sxs-lookup"><span data-stu-id="36293-149">In **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
5.  <span data-ttu-id="36293-150">Fare clic sul pulsante Sfoglia **(...)** per aprire una finestra di dialogo e compilare la definizione dell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="36293-150">Click the browse button **(...)** to open a dialog box and build the definition of the external data source.</span></span>  
  
6.  <span data-ttu-id="36293-151">Nella finestra di dialogo **Specifica mapping colonne** fare clic su **Seleziona tabella del case**.</span><span class="sxs-lookup"><span data-stu-id="36293-151">In the **Specify Column Mapping** dialog box, click **Select Case Table**.</span></span>  
  
7.  <span data-ttu-id="36293-152">Nella finestra di dialogo Seleziona tabella selezionare una vista origine dati nell'elenco, quindi la tabella che contiene i dati del case.</span><span class="sxs-lookup"><span data-stu-id="36293-152">In the Select Table dialog box, Select a data source view from the list, and select the table that contains the case data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="36293-153">Se le tabelle necessarie non sono disponibili, chiudere la finestra di dialogo e creare una nuova vista origine dati contenente la tabella.</span><span class="sxs-lookup"><span data-stu-id="36293-153">If the tables you need are not available, close the dialog box and create a new data source view that contains the table.</span></span> <span data-ttu-id="36293-154">Per informazioni su come creare una vista origine dati, vedere [Definizione di una vista origine dati &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="36293-154">For information about how to create a data source view, see [Defining a Data Source View &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span></span>  
  
9. <span data-ttu-id="36293-155">Se il modello di data mining contiene una tabella nidificata, fare clic su **Seleziona tabella nidificata**, quindi selezionare la tabella nidificata nell'elenco di tabelle nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="36293-155">If the mining model contains a nested table, click **Select Nested Table**, and select the nested table from the list of tables in the data source view.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="36293-156">Selezionare la linea join del mapping che si desidera modificare, quindi fare clic su **Modifica connessioni**.</span><span class="sxs-lookup"><span data-stu-id="36293-156">Select the join line of the mapping you want to modify, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="36293-157">Verrà visualizzata la finestra di dialogo **Modifica mapping** .</span><span class="sxs-lookup"><span data-stu-id="36293-157">The **Modify Mapping** dialog box opens.</span></span> <span data-ttu-id="36293-158">In questa finestra di dialogo è presente una tabella all'interno della quale la sezione **Colonna struttura di data mining** consente di visualizzare l'elenco delle colonne incluse nella struttura di data mining selezionata, mentre la sezione **Colonna tabella** consente di visualizzare le colonne delle tabelle di input sulle quali viene eseguito il mapping alle colonne della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="36293-158">In the table in this dialog box, **Mining Structure Column** lists each column that the selected mining structure contains, and **Table Column** lists the columns from input tables that are mapped to columns in the mining structure.</span></span>  
  
11. <span data-ttu-id="36293-159">In **Colonna tabella**selezionare la riga corrispondente alla riga inclusa in **Colonna struttura di data mining** per cui si desidera modificare una relazione.</span><span class="sxs-lookup"><span data-stu-id="36293-159">Under **Table Column**, select the row that corresponds to the row under **Mining Structure Column** for which you want to modify a relationship.</span></span> <span data-ttu-id="36293-160">Selezionare una nuova colonna nell'elenco oppure selezionare la voce vuota dell'elenco per eliminare la colonna.</span><span class="sxs-lookup"><span data-stu-id="36293-160">Select a new column from the list, or select the blank entry from the list to delete the column.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="36293-161">I nuovi mapping delle colonna verranno visualizzati nella finestra di dialogo **Specifica mapping colonne** .</span><span class="sxs-lookup"><span data-stu-id="36293-161">The new column mappings are displayed in the **Specify Column Mapping** dialog box.</span></span> <span data-ttu-id="36293-162">È possibile rimuovere un mapping selezionando la linea tra le colonne e premendo CANC.</span><span class="sxs-lookup"><span data-stu-id="36293-162">You can remove a mapping by selecting the line between the columns and pressing the DELETE key.</span></span> <span data-ttu-id="36293-163">È possibile creare una nuova connessione selezionando una colonna nella tabella **Struttura di data mining** , quindi trascinandola nella colonna corrispondente della tabella **Seleziona tabelle di input** .</span><span class="sxs-lookup"><span data-stu-id="36293-163">You can create a new connection by selecting a column in the **Mining Structure** table and dragging it to the corresponding column in the **SelectInput Table(s)** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36293-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36293-164">See Also</span></span>  
 [<span data-ttu-id="36293-165">Attività e procedure di test e convalida &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="36293-165">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
  
