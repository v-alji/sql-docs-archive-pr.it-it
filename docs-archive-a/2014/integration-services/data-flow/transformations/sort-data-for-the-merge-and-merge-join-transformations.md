---
title: Ordinare i dati per le trasformazioni Unione e Merge Join | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- sort attributes [Integration Services]
- output columns [Integration Services]
ms.assetid: 22ce3f5d-8a88-4423-92c2-60a8f82cd4fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bb4e91ad84c6baa52e1d7fb4b0104d835b7e4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712179"
---
# <a name="sort-data-for-the-merge-and-merge-join-transformations"></a><span data-ttu-id="3a38c-102">Ordinamento dei dati per le trasformazioni Unione e Merge Join</span><span class="sxs-lookup"><span data-stu-id="3a38c-102">Sort Data for the Merge and Merge Join Transformations</span></span>
  <span data-ttu-id="3a38c-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]le trasformazioni Unione e Merge Join richiedono dati di input ordinati.</span><span class="sxs-lookup"><span data-stu-id="3a38c-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the Merge and Merge Join transformations require sorted data for their inputs.</span></span> <span data-ttu-id="3a38c-104">I dati di input devono essere ordinati fisicamente ed è necessario impostare le opzioni di ordinamento sugli output e sulle colonne di output nell'origine o nella trasformazione a monte.</span><span class="sxs-lookup"><span data-stu-id="3a38c-104">The input data must be sorted physically, and sort options must be set on the outputs and the output columns in the source or in the upstream transformation.</span></span> <span data-ttu-id="3a38c-105">Se le opzioni di ordinamento indicano che i dati sono ordinati, mentre in realtà non lo sono, l'operazione di Unione o Merge join restituisce risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="3a38c-105">If the sort options indicate that the data is sorted, but the data is not actually sorted, the results of the merge or merge join operation are unpredictable.</span></span>  
  
## <a name="sorting-the-data"></a><span data-ttu-id="3a38c-106">Ordinamento dei dati</span><span class="sxs-lookup"><span data-stu-id="3a38c-106">Sorting the Data</span></span>  
 <span data-ttu-id="3a38c-107">È possibile ordinare i dati mediante uno dei seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="3a38c-107">You can sort this data by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="3a38c-108">Utilizzare nell'origine una clausola ORDER BY nell'istruzione utilizzata per caricare i dati.</span><span class="sxs-lookup"><span data-stu-id="3a38c-108">In the source, use an ORDER BY clause in the statement that is used to load the data.</span></span>  
  
-   <span data-ttu-id="3a38c-109">Inserire nel flusso di dati una trasformazione Ordinamento prima della trasformazione Unione o Merge join.</span><span class="sxs-lookup"><span data-stu-id="3a38c-109">In the data flow, insert a Sort transformation before the Merge or Merge Join transformation.</span></span>  
  
 <span data-ttu-id="3a38c-110">Se i dati sono di tipo stringa, le trasformazioni Unione e Merge join presuppongono che i valori stringa siano stati ordinati mediante le regole di confronto di Windows.</span><span class="sxs-lookup"><span data-stu-id="3a38c-110">If the data is string data, both the Merge and Merge Join transformations expect the string values to have been sorted by using Windows collation.</span></span> <span data-ttu-id="3a38c-111">Per fornire i valori stringa alle trasformazioni Unione e Merge join ordinate mediante le regole di confronto di Windows, utilizzare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3a38c-111">To provide string values to the Merge and Merge Join transformations that are sorted by using Windows collation, use the following procedure.</span></span>  
  
#### <a name="to-provide-string-values-that-are-sorted-by-using-windows-collation"></a><span data-ttu-id="3a38c-112">Per fornire valori stringa ordinati tramite regole di confronto di Windows</span><span class="sxs-lookup"><span data-stu-id="3a38c-112">To provide string values that are sorted by using Windows collation</span></span>  
  
-   <span data-ttu-id="3a38c-113">Utilizzare una trasformazione Ordinamento per ordinare i dati.</span><span class="sxs-lookup"><span data-stu-id="3a38c-113">Use a Sort transformation to sort the data.</span></span>  
  
     <span data-ttu-id="3a38c-114">La trasformazione Ordinamento utilizza le regole di confronto di Windows per ordinare i valori stringa.</span><span class="sxs-lookup"><span data-stu-id="3a38c-114">The Sort transformation uses Windows collation to sort string values.</span></span>  
  
     <span data-ttu-id="3a38c-115">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3a38c-115">-or-</span></span>  
  
-   <span data-ttu-id="3a38c-116">Utilizzare l'operatore CAST Transact-SQL per eseguire innanzitutto il cast dei valori `varchar` in valori `nvarchar`, quindi utilizzare la clausola ORDER BY Transact-SQL per ordinare i dati.</span><span class="sxs-lookup"><span data-stu-id="3a38c-116">Use the Transact-SQL CAST operator to first cast `varchar` values to `nvarchar` values, and then use the Transact-SQL ORDER BY clause to sort the data.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3a38c-117">Non è possibile utilizzare solo la clausola ORDER BY perché tale clausola utilizza le regole di confronto di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per ordinare i valori stringa.</span><span class="sxs-lookup"><span data-stu-id="3a38c-117">You cannot use the ORDER BY clause alone because the ORDER BY clause uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation to sort string values.</span></span> <span data-ttu-id="3a38c-118">L'uso delle regole di confronto di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] può restituire un ordinamento diverso rispetto alle regole di confronto di Windows, con risultati imprevisti nella trasformazione Unione o Merge join.</span><span class="sxs-lookup"><span data-stu-id="3a38c-118">The use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation might result in a different sort order than Windows collation, which can cause the Merge or Merge Join transformation to produce unexpected results.</span></span>  
  
## <a name="setting-sort-options-on-the-data"></a><span data-ttu-id="3a38c-119">Impostazione delle opzioni di ordinamento nei dati</span><span class="sxs-lookup"><span data-stu-id="3a38c-119">Setting Sort Options on the Data</span></span>  
 <span data-ttu-id="3a38c-120">È necessario impostare due importanti proprietà di ordinamento per l'origine o per la trasformazione a monte che fornisce i dati alle trasformazioni Unione e Merge join:</span><span class="sxs-lookup"><span data-stu-id="3a38c-120">There are two important sort properties that must be set for the source or upstream transformation that supplies data to the Merge and Merge Join transformations:</span></span>  
  
-   <span data-ttu-id="3a38c-121">La proprietà `IsSorted` dell'output che indica se i dati sono stati ordinati.</span><span class="sxs-lookup"><span data-stu-id="3a38c-121">The `IsSorted` property of the output that indicates whether the data has been sorted.</span></span> <span data-ttu-id="3a38c-122">Questa proprietà deve essere impostata su `True`.</span><span class="sxs-lookup"><span data-stu-id="3a38c-122">This property must be set to `True`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3a38c-123">L'impostazione del valore della proprietà `IsSorted` su `True` non determina l'ordinamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="3a38c-123">Setting the value of the `IsSorted` property to `True` does not sort the data.</span></span> <span data-ttu-id="3a38c-124">Questa proprietà fornisce solo un hint ai componenti a valle in relazione all'ordinamento precedente dei dati.</span><span class="sxs-lookup"><span data-stu-id="3a38c-124">This property only provides a hint to downstream components that the data has been previously sorted.</span></span>  
  
-   <span data-ttu-id="3a38c-125">La proprietà `SortKeyPosition` delle colonne di output che indica se una colonna è ordinata, l'ordinamento della colonna e la sequenza di ordinamento di più colonne.</span><span class="sxs-lookup"><span data-stu-id="3a38c-125">The `SortKeyPosition` property of output columns that indicates whether a column is sorted, the column's sort order, and the sequence in which multiple columns are sorted.</span></span> <span data-ttu-id="3a38c-126">Questa proprietà deve essere impostata per ogni colonna di dati ordinati.</span><span class="sxs-lookup"><span data-stu-id="3a38c-126">This property must be set for each column of sorted data.</span></span>  
  
 <span data-ttu-id="3a38c-127">Se si utilizza una trasformazione Ordinamento per ordinare i dati, entrambe le proprietà vengono impostate come richiesto dalla trasformazione Unione o Merge join,</span><span class="sxs-lookup"><span data-stu-id="3a38c-127">If you use a Sort transformation to sort the data, the Sort transformation sets both of these properties as required by the Merge or Merge Join transformation.</span></span> <span data-ttu-id="3a38c-128">ovvero, la trasformazione Ordinamento imposta la proprietà `IsSorted` dell'output su `True` e le proprietà `SortKeyPosition` delle colonne di output.</span><span class="sxs-lookup"><span data-stu-id="3a38c-128">That is, the Sort transformation sets the `IsSorted` property of its output to `True`, and sets the `SortKeyPosition` properties of its output columns.</span></span>  
  
 <span data-ttu-id="3a38c-129">Tuttavia, se non si utilizza una trasformazione Ordinamento per ordinare i dati, è necessario impostare manualmente queste proprietà di ordinamento nell'origine o nella trasformazione a monte.</span><span class="sxs-lookup"><span data-stu-id="3a38c-129">However, if you do not use a Sort transformation to sort the data, you must set these sort properties manually on the source or the upstream transformation.</span></span> <span data-ttu-id="3a38c-130">Per impostare manualmente le proprietà di ordinamento nell'origine o nella trasformazione a monte, utilizzare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="3a38c-130">To manually set the sort properties on the source or upstream transformation, use the following procedure.</span></span>  
  
#### <a name="to-manually-set-sort-attributes-on-a-source-or-transformation-component"></a><span data-ttu-id="3a38c-131">Per impostare manualmente gli attributi di ordinamento in un componente dell'origine o della trasformazione</span><span class="sxs-lookup"><span data-stu-id="3a38c-131">To manually set sort attributes on a source or transformation component</span></span>  
  
1.  <span data-ttu-id="3a38c-132">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="3a38c-132">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3a38c-133">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="3a38c-133">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3a38c-134">Nella scheda **Flusso di dati** individuare l'origine o la trasformazione a monte appropriata o trascinarla dalla **Casella degli strumenti** nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3a38c-134">On the **Data Flow** tab, locate the appropriate source or upstream transformation, or drag it from the **Toolbox** to the design surface.</span></span>  
  
4.  <span data-ttu-id="3a38c-135">Fare clic sul componente con il pulsante destro del mouse e scegliere **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="3a38c-135">Right-click the component and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="3a38c-136">Fare clic sulla scheda **Proprietà input e output** .</span><span class="sxs-lookup"><span data-stu-id="3a38c-136">Click the **Input and Output Properties** tab.</span></span>  
  
6.  <span data-ttu-id="3a38c-137">Fare clic su \*\* \<component name> output\*\*e impostare la `IsSorted` proprietà su `True` .</span><span class="sxs-lookup"><span data-stu-id="3a38c-137">Click **\<component name> Output**, and set the `IsSorted` property to `True`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3a38c-138">Se si imposta manualmente la proprietà `IsSorted` dell'output su `True` e se i dati non sono ordinati, alcuni dati potrebbero essere mancanti o danneggiati nella trasformazione Unione o Merge Join quando si esegue il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3a38c-138">If you manually set the `IsSorted` property of the output to `True` and the data is not sorted, there might be missing data or bad data comparisons in the downstream Merge or Merge Join transformation when you run the package.</span></span>  
  
7.  <span data-ttu-id="3a38c-139">Espandere **Colonne di output**.</span><span class="sxs-lookup"><span data-stu-id="3a38c-139">Expand **Output Columns**.</span></span>  
  
8.  <span data-ttu-id="3a38c-140">Fare clic sulla colonna che si desidera indicare come ordinata e impostarne la proprietà `SortKeyPosition` su un valore intero diverso da zero attenendosi alle linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a38c-140">Click the column that you want to indicate is sorted and set its `SortKeyPosition` property to a nonzero integer value by following these guidelines:</span></span>  
  
    -   <span data-ttu-id="3a38c-141">Il valore intero deve rappresentare una sequenza numerica che inizia con 1 e che ha incrementi di 1.</span><span class="sxs-lookup"><span data-stu-id="3a38c-141">The integer value must represent a numeric sequence, starting with 1 and incremented by 1.</span></span>  
  
    -   <span data-ttu-id="3a38c-142">Un valore intero positivo indica un ordinamento crescente.</span><span class="sxs-lookup"><span data-stu-id="3a38c-142">A positive integer value indicates an ascending sort order.</span></span>  
  
    -   <span data-ttu-id="3a38c-143">Un valore intero negativo indica un ordinamento decrescente.</span><span class="sxs-lookup"><span data-stu-id="3a38c-143">A negative integer value indicates a descending sort order.</span></span> <span data-ttu-id="3a38c-144">Se impostato su un numero negativo, il valore assoluto del numero determina la posizione della colonna nella sequenza di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="3a38c-144">(If set to a negative number, the absolute value of the number determines the column's position in the sort sequence.)</span></span>  
  
    -   <span data-ttu-id="3a38c-145">Il valore predefinito 0 indica che la colonna non è ordinata.</span><span class="sxs-lookup"><span data-stu-id="3a38c-145">The default value of 0 indicates that the column is not sorted.</span></span> <span data-ttu-id="3a38c-146">Lasciare il valore 0 per colonne di output che non vengono incluse nell'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="3a38c-146">Leave the value of 0 for output columns that do not participate in the sort.</span></span>  
  
     <span data-ttu-id="3a38c-147">Come esempio per l'impostazione della proprietà `SortKeyPosition`, considerare l'istruzione Transact-SQL seguente che carica i dati in un'origine:</span><span class="sxs-lookup"><span data-stu-id="3a38c-147">As an example of how to set the `SortKeyPosition` property, consider the following Transact-SQL statement that loads data in a source:</span></span>  
  
     `SELECT * FROM MyTable ORDER BY ColumnA, ColumnB DESC, ColumnC`  
  
     <span data-ttu-id="3a38c-148">Per questa istruzione, impostare la proprietà `SortKeyPosition` per ogni colonna come segue:</span><span class="sxs-lookup"><span data-stu-id="3a38c-148">For this statement, you would set the `SortKeyPosition` property for each column as follows:</span></span>  
  
    -   <span data-ttu-id="3a38c-149">Impostare la proprietà `SortKeyPosition` di ColumnA su 1.</span><span class="sxs-lookup"><span data-stu-id="3a38c-149">Set the `SortKeyPosition` property of ColumnA to 1.</span></span> <span data-ttu-id="3a38c-150">In questo modo viene indicato che ColumnA è la prima colonna da ordinare e che l'ordinamento deve essere crescente.</span><span class="sxs-lookup"><span data-stu-id="3a38c-150">This indicates that ColumnA is the first column to be sorted and is sorted in ascending order.</span></span>  
  
    -   <span data-ttu-id="3a38c-151">Impostare la proprietà `SortKeyPosition` di ColumnB su -2.</span><span class="sxs-lookup"><span data-stu-id="3a38c-151">Set the `SortKeyPosition` property of ColumnB to -2.</span></span> <span data-ttu-id="3a38c-152">In questo modo viene indicato che ColumnB è la seconda colonna da ordinare e che l'ordinamento deve essere decrescente.</span><span class="sxs-lookup"><span data-stu-id="3a38c-152">This indicates that ColumnB is the second column to be sorted and is sorted in descending order</span></span>  
  
    -   <span data-ttu-id="3a38c-153">Impostare la proprietà `SortKeyPosition` di ColumnC su 3.</span><span class="sxs-lookup"><span data-stu-id="3a38c-153">Set the `SortKeyPosition` property of ColumnC to 3.</span></span> <span data-ttu-id="3a38c-154">In questo modo viene indicato che ColumnC è la terza colonna da ordinare e che l'ordinamento deve essere crescente.</span><span class="sxs-lookup"><span data-stu-id="3a38c-154">This indicates that ColumnC is the third column to be sorted and is sorted in ascending order.</span></span>  
  
9. <span data-ttu-id="3a38c-155">Ripetere il passaggio 8 per ogni colonna ordinata.</span><span class="sxs-lookup"><span data-stu-id="3a38c-155">Repeat step 8 for each sorted column.</span></span>  
  
10. <span data-ttu-id="3a38c-156">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a38c-156">Click **OK**.</span></span>  
  
11. <span data-ttu-id="3a38c-157">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="3a38c-157">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a38c-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a38c-158">See Also</span></span>  
 <span data-ttu-id="3a38c-159">[Trasformazione Unione](merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="3a38c-159">[Merge Transformation](merge-transformation.md) </span></span>  
 <span data-ttu-id="3a38c-160">[Trasformazione Merge join](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="3a38c-160">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="3a38c-161">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="3a38c-161">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="3a38c-162">[Percorsi in Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="3a38c-162">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="3a38c-163">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="3a38c-163">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
