---
title: Trasformazione Pivot | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.pivottrans.f1
helpviewer_keywords:
- Pivot transformation
- normalized data [Integration Services]
- PivotUsage property
- datasets [Integration Services], normalized data
- less normalized data set [Integration Services]
ms.assetid: 55f5db6e-6777-435f-8a06-b68c129f8437
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43bdc5be709ea00d4be4601f52c38e96fe3f1ce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727091"
---
# <a name="pivot-transformation"></a><span data-ttu-id="bf351-102">Pivot - trasformazione</span><span class="sxs-lookup"><span data-stu-id="bf351-102">Pivot Transformation</span></span>
  <span data-ttu-id="bf351-103">La trasformazione Pivot consente di convertire un set di dati normalizzato in una versione meno normalizzata ma più compatta, trasformando i dati di input tramite Pivot in base a un valore di colonna.</span><span class="sxs-lookup"><span data-stu-id="bf351-103">The Pivot transformation makes a normalized data set into a less normalized but more compact version by pivoting the input data on a column value.</span></span> <span data-ttu-id="bf351-104">Un set di dati normalizzato di nome **Orders** che elenca nomi di clienti, prodotti e quantità vendute, ad esempio, include in genere più righe per ogni cliente che ha acquistato più prodotti, indicando su ogni riga i dettagli dell'ordine di un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="bf351-104">For example, a normalized **Orders** data set that lists customer name, product, and quantity purchased typically has multiple rows for any customer who purchased multiple products, with each row for that customer showing order details for a different product.</span></span> <span data-ttu-id="bf351-105">Trasformando il set di dati tramite Pivot in base alla colonna dei prodotti, la trasformazione Pivot può restituire in output un set di dati con una singola riga per cliente,</span><span class="sxs-lookup"><span data-stu-id="bf351-105">By pivoting the data set on the product column, the Pivot transformation can output a data set with a single row per customer.</span></span> <span data-ttu-id="bf351-106">nella quale sono elencati tutti gli acquisti effettuati dal cliente, utilizzando i nomi dei prodotti come nomi delle colonne e visualizzando le quantità come valori nelle colonne dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="bf351-106">That single row lists all the purchases by the customer, with the product names shown as column names, and the quantity shown as a value in the product column.</span></span> <span data-ttu-id="bf351-107">Poiché non tutti i clienti acquistano tutti i prodotti, molte colonne possono contenere valori Null.</span><span class="sxs-lookup"><span data-stu-id="bf351-107">Because not every customer purchases every product, many columns may contain null values.</span></span>  
  
 <span data-ttu-id="bf351-108">Quando si trasforma un set di dati tramite Pivot, le colonne di input svolgono ruoli diversi nel processo.</span><span class="sxs-lookup"><span data-stu-id="bf351-108">When a dataset is pivoted, input columns perform different roles in the pivoting process.</span></span> <span data-ttu-id="bf351-109">Una colonna può partecipare nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf351-109">A column can participate in the following ways:</span></span>  
  
-   <span data-ttu-id="bf351-110">La colonna viene passata all'output invariata.</span><span class="sxs-lookup"><span data-stu-id="bf351-110">The column is passed through unchanged to the output.</span></span> <span data-ttu-id="bf351-111">Poiché più righe di input possono convergere in una sola riga di output, la trasformazione copia solo il primo valore di input per la colonna.</span><span class="sxs-lookup"><span data-stu-id="bf351-111">Because many input rows can result only in one output row, the transformation copies only the first input value for the column.</span></span>  
  
-   <span data-ttu-id="bf351-112">La colonna viene utilizzata come chiave, o parte di una chiave, che identifica un set di record.</span><span class="sxs-lookup"><span data-stu-id="bf351-112">The column acts as the key or part of the key that identifies a set of records.</span></span>  
  
-   <span data-ttu-id="bf351-113">La colonna definisce il pivot.</span><span class="sxs-lookup"><span data-stu-id="bf351-113">The column defines the pivot.</span></span> <span data-ttu-id="bf351-114">I valori nella colonna vengono associati alle colonne del set di dati trasformato tramite Pivot.</span><span class="sxs-lookup"><span data-stu-id="bf351-114">The values in this column are associated with columns in the pivoted dataset.</span></span>  
  
-   <span data-ttu-id="bf351-115">La colonna contiene valori che vengono inseriti nelle colonne create dalla trasformazione Pivot.</span><span class="sxs-lookup"><span data-stu-id="bf351-115">The column contains values that are placed in the columns that the pivot creates.</span></span>  
  
 <span data-ttu-id="bf351-116">Questa trasformazione include un input, un output regolare e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="bf351-116">This transformation has one input, one regular output, and one error output.</span></span>  
  
## <a name="sort-and-duplicate-rows"></a><span data-ttu-id="bf351-117">Ordinare e duplicare le righe</span><span class="sxs-lookup"><span data-stu-id="bf351-117">Sort and Duplicate Rows</span></span>  
 <span data-ttu-id="bf351-118">Per trasformare efficientemente i dati tramite Pivot, ovvero creare il minor numero di record possibile nel set di dati di output, i dati di input devono essere ordinati in base alla colonna pivot.</span><span class="sxs-lookup"><span data-stu-id="bf351-118">To pivot data efficiently, which means creating as few records in the output dataset as possible, the input data must be sorted on the pivot column.</span></span> <span data-ttu-id="bf351-119">Se i dati non sono ordinati, la trasformazione Pivot potrà generare più record per ogni valore nella chiave del set, che è la colonna che definisce l'appartenenza al set.</span><span class="sxs-lookup"><span data-stu-id="bf351-119">If the data is not sorted, the Pivot transformation might generate multiple records for each value in the set key, which is the column that defines set membership.</span></span> <span data-ttu-id="bf351-120">Se un set di dati viene trasformato tramite Pivot in base a una colonna **Name** , ad esempio, ma i nomi non sono ordinati, nel set di dati di output potranno essere incluse più righe per ogni cliente, perché viene eseguita un'operazione pivot ogni volta che cambia il valore in **Name** .</span><span class="sxs-lookup"><span data-stu-id="bf351-120">For example, if a dataset is pivoted on a **Name** column but the names are not sorted, the output dataset could have more than one row for each customer, because a pivot occurs every time that the value in **Name** changes.</span></span>  
  
 <span data-ttu-id="bf351-121">I dati di input potrebbero contenere righe duplicate, provocando l'errore della trasformazione Pivot.</span><span class="sxs-lookup"><span data-stu-id="bf351-121">The input data might contain duplicate rows, which will cause the Pivot transformation to fail.</span></span> <span data-ttu-id="bf351-122">Per righe duplicate si intendono righe che contengono gli stessi valori nelle colonne chiave del set e nelle colonne pivot.</span><span class="sxs-lookup"><span data-stu-id="bf351-122">"Duplicate rows" means rows that have the same values in the set key columns and the pivot columns.</span></span> <span data-ttu-id="bf351-123">Per evitare l'errore è possibile configurare la trasformazione in modo che le righe con esito negativo vengano reindirizzate a un output degli errori, oppure preaggregare i valori per assicurarsi che non siano presenti righe duplicate.</span><span class="sxs-lookup"><span data-stu-id="bf351-123">To avoid failure, you can either configure the transformation to redirect error rows to an error output or you can pre-aggregate values to ensure there are no duplicate rows.</span></span>  
  
##  <a name="options-in-the-pivot-dialog-box"></a><a name="options"></a> <span data-ttu-id="bf351-124">Opzioni della finestra di dialogo Pivot</span><span class="sxs-lookup"><span data-stu-id="bf351-124">Options in the Pivot Dialog Box</span></span>  
 <span data-ttu-id="bf351-125">L'operazione pivot può essere configurata impostando le opzioni nella finestra di dialogo **Pivot** .</span><span class="sxs-lookup"><span data-stu-id="bf351-125">You configure the pivot operation by setting the options in the **Pivot** dialog box.</span></span> <span data-ttu-id="bf351-126">Per aprire la finestra di dialogo **Pivot** , aggiungere la trasformazione Pivot al pacchetto in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]e quindi fare clic con il pulsante destro del mouse sul componente e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bf351-126">To open the **Pivot** dialog box, add the Pivot transformation to the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and then right-click the component and click **Edit**.</span></span>  
  
 <span data-ttu-id="bf351-127">L'elenco seguente descrive le opzioni nella finestra di dialogo **Pivot** .</span><span class="sxs-lookup"><span data-stu-id="bf351-127">The following list describes the options in the **Pivot** dialog box.</span></span>  
  
 <span data-ttu-id="bf351-128">**Chiave pivot**</span><span class="sxs-lookup"><span data-stu-id="bf351-128">**Pivot Key**</span></span>  
 <span data-ttu-id="bf351-129">Viene specificata la colonna da utilizzare per i valori nella riga superiore (riga di intestazione) della tabella.</span><span class="sxs-lookup"><span data-stu-id="bf351-129">Specifies the column to use for values across the top row (header row) of the table.</span></span>  
  
 <span data-ttu-id="bf351-130">**Chiave set**</span><span class="sxs-lookup"><span data-stu-id="bf351-130">**Set Key**</span></span>  
 <span data-ttu-id="bf351-131">Viene specificata la colonna da utilizzare per i valori nella colonna sinistra della tabella.</span><span class="sxs-lookup"><span data-stu-id="bf351-131">Specifies the column to use for values in the left column of the table.</span></span> <span data-ttu-id="bf351-132">È necessario ordinare la data di input in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="bf351-132">The input date must be sorted on this column.</span></span>  
  
 <span data-ttu-id="bf351-133">**Valore pivot**</span><span class="sxs-lookup"><span data-stu-id="bf351-133">**Pivot Value**</span></span>  
 <span data-ttu-id="bf351-134">Viene specificata la colonna da utilizzare per i valori della tabella diversi rispetto ai valori della riga di intestazione e della colonna sinistra.</span><span class="sxs-lookup"><span data-stu-id="bf351-134">Specifies the column to use for the table values, other than the values in the header row and the left column.</span></span>  
  
 <span data-ttu-id="bf351-135">**Ignora i valori delle chiavi pivot senza corrispondenza e segnalali dopo l'esecuzione del flusso di dati**</span><span class="sxs-lookup"><span data-stu-id="bf351-135">**Ignore un-matched Pivot Key values and report them after DataFlow execution**</span></span>  
 <span data-ttu-id="bf351-136">Selezionare questa opzione per configurare la trasformazione Pivot per ignorare le righe contenenti valori non riconosciuti nella colonna **Chiave pivot** e restituire tutti i valori di chiave pivot in un messaggio di log, quando viene eseguito il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="bf351-136">Select this option to configure the Pivot transformation to ignore rows containing unrecognized values in the **Pivot Key** column and to output all of the pivot key values to a log message, when the package is run.</span></span>  
  
 <span data-ttu-id="bf351-137">È anche possibile configurare la trasformazione per restituire i valori impostando la proprietà personalizzata `PassThroughUnmatchedPivotKeys` su `True`.</span><span class="sxs-lookup"><span data-stu-id="bf351-137">You can also configure the transformation to output the values by setting the `PassThroughUnmatchedPivotKeys` custom property to `True`.</span></span>  
  
 <span data-ttu-id="bf351-138">**Generare colonne di output pivot dai valori**</span><span class="sxs-lookup"><span data-stu-id="bf351-138">**Generate pivot output columns from values**</span></span>  
 <span data-ttu-id="bf351-139">Immettere i valori di chiave pivot in questa casella per consentire alla trasformazione Pivot di creare colonne di output per ogni valore.</span><span class="sxs-lookup"><span data-stu-id="bf351-139">Enter the pivot key values in this box to enable the Pivot transformation to create output columns for each value.</span></span> <span data-ttu-id="bf351-140">È possibile immettere i valori prima dell'esecuzione del pacchetto oppure effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="bf351-140">You can either enter the values prior to running the package, or do the following.</span></span>  
  
1.  <span data-ttu-id="bf351-141">Selezionare l'opzione **Ignora i valori delle chiavi pivot senza corrispondenza e segnalali dopo l'esecuzione del flusso di dati** , quindi fare clic su **OK** nella finestra di dialogo **Pivot** per salvare le modifiche nella trasformazione Pivot.</span><span class="sxs-lookup"><span data-stu-id="bf351-141">Select the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then click **OK** in the **Pivot** dialog box to save the changes to the Pivot transformation.</span></span>  
  
2.  <span data-ttu-id="bf351-142">Eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="bf351-142">Run the package.</span></span>  
  
3.  <span data-ttu-id="bf351-143">Quando l'esecuzione del pacchetto viene completata correttamente, fare clic sulla scheda **Stato** e cercare il messaggio di log informativo della trasformazione Pivot contenente i valori di chiave pivot.</span><span class="sxs-lookup"><span data-stu-id="bf351-143">When the package succeeds, click the **Progress** tab and look for the information log message from the Pivot transformation that contains the pivot key values.</span></span>  
  
4.  <span data-ttu-id="bf351-144">Fare clic con il pulsante destro del mouse sul messaggio e scegliere **Copia testo messaggio**.</span><span class="sxs-lookup"><span data-stu-id="bf351-144">Right-click the message and click **Copy Message Text**.</span></span>  
  
5.  <span data-ttu-id="bf351-145">Fare clic su **Arresta debug** nel menu **Debug** per passare alla modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="bf351-145">Click **Stop Debugging** on the **Debug** menu to switch to the design mode.</span></span>  
  
6.  <span data-ttu-id="bf351-146">Fare clic con il pulsante destro del mouse sulla trasformazione Pivot e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bf351-146">Right-click the Pivot transformation, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="bf351-147">Deselezionare l'opzione **Ignora i valori delle chiavi pivot senza corrispondenza e segnalali dopo l'esecuzione del flusso di dati** , quindi incollare i valori di chiave pivot nella casella **Generare colonne di output pivot dai valori** usando il formato seguente.</span><span class="sxs-lookup"><span data-stu-id="bf351-147">Uncheck the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then paste the pivot key values in the **Generate pivot output columns from values** box using the following format.</span></span>  
  
     <span data-ttu-id="bf351-148">[valore1],[valore2],[valore3]</span><span class="sxs-lookup"><span data-stu-id="bf351-148">[value1],[value2],[value3]</span></span>  
  
 <span data-ttu-id="bf351-149">**Genera colonne**</span><span class="sxs-lookup"><span data-stu-id="bf351-149">**Generate Columns Now**</span></span>  
 <span data-ttu-id="bf351-150">Fare clic per creare una colonna di output per ogni valore di chiave pivot elencato nella casella **Generare colonne di output pivot dai valori** .</span><span class="sxs-lookup"><span data-stu-id="bf351-150">Click to create an output column for each pivot key value that is listed in the **Generate pivot output columns from values** box.</span></span>  
  
 <span data-ttu-id="bf351-151">Le colonne di output vengono visualizzate nella casella **Colonne di output trasformate tramite pivot esistenti** .</span><span class="sxs-lookup"><span data-stu-id="bf351-151">The output columns appear in the **Existing pivoted output columns** box.</span></span>  
  
 <span data-ttu-id="bf351-152">**Colonne di output trasformate tramite pivot esistenti**</span><span class="sxs-lookup"><span data-stu-id="bf351-152">**Existing pivoted output columns**</span></span>  
 <span data-ttu-id="bf351-153">Vengono elencate le colonne di output per i valori di chiave pivot</span><span class="sxs-lookup"><span data-stu-id="bf351-153">Lists the output columns for the pivot key values</span></span>  
  
 <span data-ttu-id="bf351-154">La tabella seguente mostra un set di dati prima della trasformazione dei dati tramite Pivot in base alla colonna **Year** .</span><span class="sxs-lookup"><span data-stu-id="bf351-154">The following table shows a data set before the data is pivoted on the **Year** column.</span></span>  
  
|<span data-ttu-id="bf351-155">Year</span><span class="sxs-lookup"><span data-stu-id="bf351-155">Year</span></span>|<span data-ttu-id="bf351-156">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bf351-156">Product Name</span></span>|<span data-ttu-id="bf351-157">Totale</span><span class="sxs-lookup"><span data-stu-id="bf351-157">Total</span></span>|  
|----------|------------------|-----------|  
|<span data-ttu-id="bf351-158">2004</span><span class="sxs-lookup"><span data-stu-id="bf351-158">2004</span></span>|<span data-ttu-id="bf351-159">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="bf351-159">HL Mountain Tire</span></span>|<span data-ttu-id="bf351-160">1504884.15</span><span class="sxs-lookup"><span data-stu-id="bf351-160">1504884.15</span></span>|  
|<span data-ttu-id="bf351-161">2003</span><span class="sxs-lookup"><span data-stu-id="bf351-161">2003</span></span>|<span data-ttu-id="bf351-162">Road Tire Tube</span><span class="sxs-lookup"><span data-stu-id="bf351-162">Road Tire Tube</span></span>|<span data-ttu-id="bf351-163">35920.50</span><span class="sxs-lookup"><span data-stu-id="bf351-163">35920.50</span></span>|  
|<span data-ttu-id="bf351-164">2004</span><span class="sxs-lookup"><span data-stu-id="bf351-164">2004</span></span>|<span data-ttu-id="bf351-165">Water Bottle - 30 oz.</span><span class="sxs-lookup"><span data-stu-id="bf351-165">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="bf351-166">2805.00</span><span class="sxs-lookup"><span data-stu-id="bf351-166">2805.00</span></span>|  
|<span data-ttu-id="bf351-167">2002</span><span class="sxs-lookup"><span data-stu-id="bf351-167">2002</span></span>|<span data-ttu-id="bf351-168">Touring Tire</span><span class="sxs-lookup"><span data-stu-id="bf351-168">Touring Tire</span></span>|<span data-ttu-id="bf351-169">62364.225</span><span class="sxs-lookup"><span data-stu-id="bf351-169">62364.225</span></span>|  
  
 <span data-ttu-id="bf351-170">La tabella seguente mostra un set di dati dopo la trasformazione dei dati tramite Pivot in base alla colonna **Year** .</span><span class="sxs-lookup"><span data-stu-id="bf351-170">The following table shows a data set after the data has been pivoted on the **Year** column.</span></span>  
  
||<span data-ttu-id="bf351-171">2002</span><span class="sxs-lookup"><span data-stu-id="bf351-171">2002</span></span>|<span data-ttu-id="bf351-172">2003</span><span class="sxs-lookup"><span data-stu-id="bf351-172">2003</span></span>|<span data-ttu-id="bf351-173">2004</span><span class="sxs-lookup"><span data-stu-id="bf351-173">2004</span></span>|  
|-|----------|----------|----------|  
|<span data-ttu-id="bf351-174">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="bf351-174">HL Mountain Tire</span></span>|<span data-ttu-id="bf351-175">141164.10</span><span class="sxs-lookup"><span data-stu-id="bf351-175">141164.10</span></span>|<span data-ttu-id="bf351-176">446297.775</span><span class="sxs-lookup"><span data-stu-id="bf351-176">446297.775</span></span>|<span data-ttu-id="bf351-177">1504884.15</span><span class="sxs-lookup"><span data-stu-id="bf351-177">1504884.15</span></span>|  
|<span data-ttu-id="bf351-178">Road Tire Tube</span><span class="sxs-lookup"><span data-stu-id="bf351-178">Road Tire Tube</span></span>|<span data-ttu-id="bf351-179">3592.05</span><span class="sxs-lookup"><span data-stu-id="bf351-179">3592.05</span></span>|<span data-ttu-id="bf351-180">35920.50</span><span class="sxs-lookup"><span data-stu-id="bf351-180">35920.50</span></span>|<span data-ttu-id="bf351-181">89801.25</span><span class="sxs-lookup"><span data-stu-id="bf351-181">89801.25</span></span>|  
|<span data-ttu-id="bf351-182">Water Bottle - 30 oz.</span><span class="sxs-lookup"><span data-stu-id="bf351-182">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="bf351-183">*NULL*</span><span class="sxs-lookup"><span data-stu-id="bf351-183">*NULL*</span></span>|<span data-ttu-id="bf351-184">*NULL*</span><span class="sxs-lookup"><span data-stu-id="bf351-184">*NULL*</span></span>|<span data-ttu-id="bf351-185">2805.00</span><span class="sxs-lookup"><span data-stu-id="bf351-185">2805.00</span></span>|  
|<span data-ttu-id="bf351-186">Touring Tire</span><span class="sxs-lookup"><span data-stu-id="bf351-186">Touring Tire</span></span>|<span data-ttu-id="bf351-187">62364.225</span><span class="sxs-lookup"><span data-stu-id="bf351-187">62364.225</span></span>|<span data-ttu-id="bf351-188">375051.60</span><span class="sxs-lookup"><span data-stu-id="bf351-188">375051.60</span></span>|<span data-ttu-id="bf351-189">1041810.00</span><span class="sxs-lookup"><span data-stu-id="bf351-189">1041810.00</span></span>|  
  
 <span data-ttu-id="bf351-190">Per trasformare i dati tramite Pivot in base alla colonna **Year** , come mostrato in precedenza, vengono impostate le opzioni seguenti nella finestra di dialogo **Pivot** .</span><span class="sxs-lookup"><span data-stu-id="bf351-190">To pivot the data on the **Year** column, as shown above, the following options are set in the **Pivot** dialog box.</span></span>  
  
-   <span data-ttu-id="bf351-191">Selezione di Year nella casella di riepilogo **Chiave pivot** .</span><span class="sxs-lookup"><span data-stu-id="bf351-191">Year is selected in the **Pivot Key** list box.</span></span>  
  
-   <span data-ttu-id="bf351-192">Selezione di Product Name nella casella di riepilogo **Chiave set** .</span><span class="sxs-lookup"><span data-stu-id="bf351-192">Product Name is selected in the **Set Key** list box.</span></span>  
  
-   <span data-ttu-id="bf351-193">Selezione di Total nella casella di riepilogo **Valore pivot** .</span><span class="sxs-lookup"><span data-stu-id="bf351-193">Total is selected in the **Pivot Value** list box.</span></span>  
  
-   <span data-ttu-id="bf351-194">Immissione dei valori seguenti nella casella **Generare colonne di output pivot dai valori** .</span><span class="sxs-lookup"><span data-stu-id="bf351-194">The following values are entered in the **Generate pivot output columns from values** box.</span></span>  
  
     <span data-ttu-id="bf351-195">[2002],[2003],[2004]</span><span class="sxs-lookup"><span data-stu-id="bf351-195">[2002],[2003],[2004]</span></span>  
  
## <a name="configuration-of-the-pivot-transformation"></a><span data-ttu-id="bf351-196">Configurazione della trasformazione Pivot</span><span class="sxs-lookup"><span data-stu-id="bf351-196">Configuration of the Pivot Transformation</span></span>  
 <span data-ttu-id="bf351-197">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="bf351-197">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="bf351-198">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf351-198">For more information about the properties that you can set in the **Advanced Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="bf351-199">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="bf351-199">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="bf351-200">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="bf351-200">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-content"></a><span data-ttu-id="bf351-201">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="bf351-201">Related Content</span></span>  
 <span data-ttu-id="bf351-202">Per informazioni su come impostare le proprietà del componente, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="bf351-202">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf351-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf351-203">See Also</span></span>  
 <span data-ttu-id="bf351-204">[Trasformazione UnPivot](pivot-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="bf351-204">[Unpivot Transformation](pivot-transformation.md) </span></span>  
 <span data-ttu-id="bf351-205">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="bf351-205">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="bf351-206">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="bf351-206">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
