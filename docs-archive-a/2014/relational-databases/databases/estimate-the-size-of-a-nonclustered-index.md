---
title: Stimare le dimensioni di un indice non cluster | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: c183b0e4-ef4c-4bfc-8575-5ac219c25b0a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 097c0e5568ba17b12f83d09e347eb3bf8b0bd7da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721480"
---
# <a name="estimate-the-size-of-a-nonclustered-index"></a><span data-ttu-id="23c0b-102">Stima delle dimensioni di un indice non cluster</span><span class="sxs-lookup"><span data-stu-id="23c0b-102">Estimate the Size of a Nonclustered Index</span></span>
  <span data-ttu-id="23c0b-103">Per stimare la quantità di spazio necessaria per archiviare un indice non cluster, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c0b-103">Follow these steps to estimate the amount of space that is required to store a nonclustered index:</span></span>  
  
1.  <span data-ttu-id="23c0b-104">Calcolare le variabili da utilizzare nei passaggi 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="23c0b-104">Calculate variables for use in steps 2 and 3.</span></span>  
  
2.  <span data-ttu-id="23c0b-105">Calcolare lo spazio utilizzato per l'archiviazione di informazioni sull'indice nel livello foglia dell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="23c0b-105">Calculate the space used to store index information in the leaf level of the nonclustered index.</span></span>  
  
3.  <span data-ttu-id="23c0b-106">Calcolare lo spazio utilizzato per l'archiviazione di informazioni sull'indice nei livelli non foglia dell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="23c0b-106">Calculate the space used to store index information in the non-leaf levels of the nonclustered index.</span></span>  
  
4.  <span data-ttu-id="23c0b-107">Sommare i valori calcolati.</span><span class="sxs-lookup"><span data-stu-id="23c0b-107">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-variables-for-use-in-steps-2-and-3"></a><span data-ttu-id="23c0b-108">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="23c0b-108">Step 1.</span></span> <span data-ttu-id="23c0b-109">Calcolare le variabili da utilizzare nei passaggi 2 e 3</span><span class="sxs-lookup"><span data-stu-id="23c0b-109">Calculate Variables for Use in Steps 2 and 3</span></span>  
 <span data-ttu-id="23c0b-110">Per calcolare le variabili utilizzate per stimare la quantità di spazio necessario per archiviare i livelli superiori dell'indice, è possibile effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c0b-110">You can use the following steps to calculate variables that are used to estimate the amount of space that is required to store the upper levels of the index.</span></span>  
  
1.  <span data-ttu-id="23c0b-111">Specificare il numero di righe che verranno incluse nella tabella:</span><span class="sxs-lookup"><span data-stu-id="23c0b-111">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="23c0b-112">***Num_Rows***  = numero di righe della tabella</span><span class="sxs-lookup"><span data-stu-id="23c0b-112">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="23c0b-113">Specificare il numero di colonne a lunghezza fissa e a lunghezza variabile incluse nella chiave dell'indice e calcolare lo spazio necessario per archiviarle:</span><span class="sxs-lookup"><span data-stu-id="23c0b-113">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="23c0b-114">Le colonne chiave di un indice possono includere colonne a lunghezza fissa e a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="23c0b-114">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="23c0b-115">Per stimare le dimensioni delle righe di indice di livello interno, calcolare lo spazio occupato da ognuno di questi gruppi di colonne all'interno della riga di indice.</span><span class="sxs-lookup"><span data-stu-id="23c0b-115">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="23c0b-116">Le dimensioni di una colonna dipendono dal tipo di dati e dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="23c0b-116">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="23c0b-117">***Num_Key_Cols***  = numero totale di colonne chiave (a lunghezza fissa e a lunghezza variabile)</span><span class="sxs-lookup"><span data-stu-id="23c0b-117">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="23c0b-118">***Fixed_Key_Size***  = dimensioni totali in byte di tutte le colonne chiave a lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="23c0b-118">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="23c0b-119">***Num_Variable_Key_Cols***  = numero di colonne chiave a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="23c0b-119">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="23c0b-120">***Max_Var_Key_Size***  = dimensioni massime in byte di tutte le colonne chiave a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="23c0b-120">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
3.  <span data-ttu-id="23c0b-121">Considerare anche l'indicatore di posizione delle righe di dati, necessario se l'indice non è univoco:</span><span class="sxs-lookup"><span data-stu-id="23c0b-121">Account for the data row locator that is required if the index is nonunique:</span></span>  
  
     <span data-ttu-id="23c0b-122">Se l'indice non cluster non è univoco, l'indicatore di posizione delle righe di dati viene combinato con la chiave dell'indice non cluster in modo da ottenere un valore di chiave univoco per ciascuna riga.</span><span class="sxs-lookup"><span data-stu-id="23c0b-122">If the nonclustered index is nonunique, the data row locator is combined with the nonclustered index key to produce a unique key value for every row.</span></span>  
  
     <span data-ttu-id="23c0b-123">Se l'indice non cluster è su un heap, l'indicatore di posizione delle righe di dati corrisponde al RID dell'heap,</span><span class="sxs-lookup"><span data-stu-id="23c0b-123">If the nonclustered index is over a heap, the data row locator is the heap RID.</span></span> <span data-ttu-id="23c0b-124">le cui dimensioni sono pari a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="23c0b-124">This is a size of 8 bytes.</span></span>  
  
     <span data-ttu-id="23c0b-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="23c0b-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="23c0b-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="23c0b-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="23c0b-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="23c0b-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span></span>  
  
     <span data-ttu-id="23c0b-128">Se l'indice non cluster è su un indice cluster, l'indicatore di posizione delle righe di dati corrisponde alla chiave di clustering.</span><span class="sxs-lookup"><span data-stu-id="23c0b-128">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="23c0b-129">Le colonne da combinare con la chiave dell'indice non cluster sono le colonne della chiave di clustering non incluse già nel set di colonne chiave dell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="23c0b-129">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="23c0b-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + numero di colonne chiave di clustering non nel set di colonne chiave di indice non cluster (+ 1 se l'indice cluster è non univoco)</span><span class="sxs-lookup"><span data-stu-id="23c0b-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="23c0b-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + dimensioni totali in byte delle colonne chiave di clustering a lunghezza fissa non nel set di colonne chiave di indice non cluster</span><span class="sxs-lookup"><span data-stu-id="23c0b-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="23c0b-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + numero di colonne chiave di clustering a lunghezza variabile non nel set di colonne chiave di indice non cluster (+ 1 se l'indice cluster è non univoco)</span><span class="sxs-lookup"><span data-stu-id="23c0b-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="23c0b-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + dimensioni massime in byte delle colonne chiave di clustering a lunghezza variabile non nel set di colonne chiave di indice non cluster (+ 4 se l'indice cluster è non univoco)</span><span class="sxs-lookup"><span data-stu-id="23c0b-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
4.  <span data-ttu-id="23c0b-134">È possibile riservare parte della riga, nota come mappa di bit Null, per la gestione del supporto dei valori Null della colonna.</span><span class="sxs-lookup"><span data-stu-id="23c0b-134">Part of the row, known as the null bitmap, may be reserved to manage column nullability.</span></span> <span data-ttu-id="23c0b-135">Calcolarne le dimensioni:</span><span class="sxs-lookup"><span data-stu-id="23c0b-135">Calculate its size:</span></span>  
  
     <span data-ttu-id="23c0b-136">Se sono presenti colonne che ammettono i valori Null nella chiave dell'indice, incluse le eventuali colonne chiave di clustering necessarie descritte al passaggio 1.3, parte della riga di indice viene riservata alla mappa di bit Null.</span><span class="sxs-lookup"><span data-stu-id="23c0b-136">If there are nullable columns in the index key, including any necessary clustering key columns as described in Step 1.3, part of the index row is reserved for the null bitmap.</span></span>  
  
     <span data-ttu-id="23c0b-137">***Index_Null_Bitmap***  = 2 + ((numero di colonne nella riga di indice + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="23c0b-137">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="23c0b-138">Deve essere utilizzata solo la parte Integer dell'espressione precedente.</span><span class="sxs-lookup"><span data-stu-id="23c0b-138">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="23c0b-139">Eliminare le parti restanti.</span><span class="sxs-lookup"><span data-stu-id="23c0b-139">Discard any remainder.</span></span>  
  
     <span data-ttu-id="23c0b-140">Se invece non sono disponibili colonne chiave che ammettono i valori Null, impostare ***Index_Null_Bitmap*** su 0.</span><span class="sxs-lookup"><span data-stu-id="23c0b-140">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
5.  <span data-ttu-id="23c0b-141">Calcolare le dimensioni dei dati a lunghezza variabile:</span><span class="sxs-lookup"><span data-stu-id="23c0b-141">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="23c0b-142">Se sono presenti colonne a lunghezza variabile nella chiave dell'indice, incluse eventuali colonne chiave dell'indice cluster necessarie, determinare lo spazio utilizzato per archiviare le colonne all'interno della riga di indice:</span><span class="sxs-lookup"><span data-stu-id="23c0b-142">If there are variable-length columns in the index key, including any necessary clustered index key columns, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="23c0b-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="23c0b-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="23c0b-144">I byte aggiunti a ***Max_Var_Key_Size*** servono a tenere traccia di ogni colonna variabile. Questa formula si basa sul presupposto che tutte le colonne a lunghezza variabile siano piene al 100%.</span><span class="sxs-lookup"><span data-stu-id="23c0b-144">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="23c0b-145">Se si prevede una percentuale inferiore di utilizzo dello spazio di archiviazione delle colonne a lunghezza variabile, è possibile modificare il valore di ***Max_Var_Key_Size*** in base a tale percentuale per ottenere una stima più accurata delle dimensioni complessive della tabella.</span><span class="sxs-lookup"><span data-stu-id="23c0b-145">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="23c0b-146">Se non sono disponibili colonne a lunghezza variabile, impostare ***Variable_Key_Size*** su 0.</span><span class="sxs-lookup"><span data-stu-id="23c0b-146">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="23c0b-147">Calcolare le dimensioni della riga di indice:</span><span class="sxs-lookup"><span data-stu-id="23c0b-147">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="23c0b-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (per l'overhead dell'intestazione di una riga di indice) + 6 (per il puntatore ID della pagina figlio)</span><span class="sxs-lookup"><span data-stu-id="23c0b-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
7.  <span data-ttu-id="23c0b-149">Calcolare il numero di righe di indice per pagina (8096 byte liberi per pagina):</span><span class="sxs-lookup"><span data-stu-id="23c0b-149">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="23c0b-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="23c0b-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="23c0b-151">Poiché le righe di indice non si estendono su più pagine, il numero di righe di indice per pagina deve essere arrotondato alla riga completa più vicina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-151">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="23c0b-152">Il numero 2 nella formula si riferisce alla voce della riga nella matrice di slot della pagina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-152">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information-in-the-leaf-level"></a><span data-ttu-id="23c0b-153">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="23c0b-153">Step 2.</span></span> <span data-ttu-id="23c0b-154">Calcolare lo spazio utilizzato per l'archiviazione di informazioni sull'indice nel livello foglia</span><span class="sxs-lookup"><span data-stu-id="23c0b-154">Calculate the Space Used to Store Index Information in the Leaf Level</span></span>  
 <span data-ttu-id="23c0b-155">Per stimare la quantità di spazio necessaria per archiviare il livello foglia dell'indice, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="23c0b-155">You can use the following steps to estimate the amount of space that is required to store the leaf level of the index.</span></span> <span data-ttu-id="23c0b-156">Per completare questo passaggio, sono necessari i valori preservati al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="23c0b-156">You will need the values preserved from Step 1 to complete this step.</span></span>  
  
1.  <span data-ttu-id="23c0b-157">Specificare il numero di colonne a lunghezza fissa e a lunghezza variabile incluse a livello foglia e calcolare lo spazio necessario per archiviarle:</span><span class="sxs-lookup"><span data-stu-id="23c0b-157">Specify the number of fixed-length and variable-length columns at the leaf level and calculate the space that is required for their storage:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23c0b-158">È possibile estendere un indice non cluster includendo colonne non chiave oltre alle colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="23c0b-158">You can extend a nonclustered index by including nonkey columns in addition to the index key columns.</span></span> <span data-ttu-id="23c0b-159">Tali colonne aggiuntive vengono archiviate solo al livello foglia dell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="23c0b-159">These additional columns are only stored at the leaf level of the nonclustered index.</span></span> <span data-ttu-id="23c0b-160">Per altre informazioni, vedere [Creare indici con colonne incluse](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="23c0b-160">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23c0b-161">È possibile combinare colonne `varchar`, `nvarchar`, `varbinary` o `sql_variant` che fanno eccedere gli 8.060 byte per la larghezza totale definita della tabella.</span><span class="sxs-lookup"><span data-stu-id="23c0b-161">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="23c0b-162">La lunghezza di ogni colonna deve essere compresa nel limite di 8.000 byte per una colonna `varchar`, `varbinary` o `sql_variant` e di 4.000 byte per le colonne `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="23c0b-162">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="23c0b-163">Le larghezze combinate di tali colonne possono tuttavia superare il limite di 8.060 byte in una tabella.</span><span class="sxs-lookup"><span data-stu-id="23c0b-163">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span> <span data-ttu-id="23c0b-164">Lo stesso vale inoltre per le righe foglia dell'indice non cluster che presentano colonne incluse.</span><span class="sxs-lookup"><span data-stu-id="23c0b-164">This also applies to nonclustered index leaf rows that have included columns.</span></span>  
  
     <span data-ttu-id="23c0b-165">Se l'indice non cluster non dispone di colonne incluse, utilizzare i valori del passaggio 1, incluse le eventuali modifiche determinate al passaggio 1.3:</span><span class="sxs-lookup"><span data-stu-id="23c0b-165">If the nonclustered index does not have any included columns, use the values from Step 1, including any modifications determined in Step 1.3:</span></span>  
  
     <span data-ttu-id="23c0b-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="23c0b-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span></span>  
  
     <span data-ttu-id="23c0b-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="23c0b-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span></span>  
  
     <span data-ttu-id="23c0b-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="23c0b-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span></span>  
  
     <span data-ttu-id="23c0b-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="23c0b-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="23c0b-170">Se l'indice non cluster dispone di colonne incluse, aggiungere i valori appropriati a quelli del passaggio 1, incluse le eventuali modifiche del passaggio 1.3.</span><span class="sxs-lookup"><span data-stu-id="23c0b-170">If the nonclustered index does have included columns, add the appropriate values to the values from Step 1, including any modifications in Step 1.3.</span></span> <span data-ttu-id="23c0b-171">Le dimensioni di una colonna dipendono dal tipo di dati e dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="23c0b-171">The size of a column depends on the data type and length specification.</span></span> <span data-ttu-id="23c0b-172">Per altre informazioni, vedere [Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="23c0b-172">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
     <span data-ttu-id="23c0b-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + numero di colonne incluse</span><span class="sxs-lookup"><span data-stu-id="23c0b-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + number of included columns</span></span>  
  
     <span data-ttu-id="23c0b-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + dimensioni massime in byte di tutte le colonne incluse a lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="23c0b-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length included columns</span></span>  
  
     <span data-ttu-id="23c0b-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length included columns</span><span class="sxs-lookup"><span data-stu-id="23c0b-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length included columns</span></span>  
  
     <span data-ttu-id="23c0b-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + dimensioni massime in byte di tutte le colonne incluse a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="23c0b-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length included columns</span></span>  
  
2.  <span data-ttu-id="23c0b-177">Considerare l'indicatore di posizione delle righe di dati:</span><span class="sxs-lookup"><span data-stu-id="23c0b-177">Account for the data row locator:</span></span>  
  
     <span data-ttu-id="23c0b-178">Se l'indice non cluster non è univoco, l'overhead per l'indicatore di posizione delle righe di dati è già stato considerato al passaggio 1.3 e non sono richieste modifiche ulteriori.</span><span class="sxs-lookup"><span data-stu-id="23c0b-178">If the nonclustered index is nonunique, the overhead for the data row locator has already been considered in Step 1.3 and no additional modifications are required.</span></span> <span data-ttu-id="23c0b-179">Procedere con il passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="23c0b-179">Go to the next step.</span></span>  
  
     <span data-ttu-id="23c0b-180">Se l'indice non cluster è univoco, è necessario considerare l'indicatore di posizione delle righe di dati per tutte le righe al livello foglia.</span><span class="sxs-lookup"><span data-stu-id="23c0b-180">If the nonclustered index is unique, the data row locator must be accounted for in all rows at the leaf level.</span></span>  
  
     <span data-ttu-id="23c0b-181">Se l'indice non cluster è su un heap, l'indicatore di posizione delle righe di dati corrisponde al RID dell'heap, ovvero a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="23c0b-181">If the nonclustered index is over a heap, the data row locator is the heap RID (size 8 bytes).</span></span>  
  
     <span data-ttu-id="23c0b-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="23c0b-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="23c0b-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="23c0b-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="23c0b-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="23c0b-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span></span>  
  
     <span data-ttu-id="23c0b-185">Se l'indice non cluster è su un indice cluster, l'indicatore di posizione delle righe di dati corrisponde alla chiave di clustering.</span><span class="sxs-lookup"><span data-stu-id="23c0b-185">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="23c0b-186">Le colonne da combinare con la chiave dell'indice non cluster sono le colonne della chiave di clustering non incluse già nel set di colonne chiave dell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="23c0b-186">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="23c0b-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + numero di colonne chiave di clustering non nel set di colonne chiave di indice non cluster (+ 1 se l'indice cluster è non univoco)</span><span class="sxs-lookup"><span data-stu-id="23c0b-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="23c0b-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + numero di colonne chiave di clustering a lunghezza fissa non nel set di colonne chiave di indice non cluster</span><span class="sxs-lookup"><span data-stu-id="23c0b-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + number of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="23c0b-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + numero di colonne chiave di clustering a lunghezza variabile non nel set di colonne chiave di indice non cluster (+ 1 se l'indice cluster è non univoco)</span><span class="sxs-lookup"><span data-stu-id="23c0b-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="23c0b-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + dimensione in byte delle colonne chiave di clustering a lunghezza variabile non nel set di colonne chiave di indice non cluster (+ 4 se l'indice cluster è non univoco)</span><span class="sxs-lookup"><span data-stu-id="23c0b-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + size in bytes of the variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
3.  <span data-ttu-id="23c0b-191">Calcolare le dimensioni della mappa di bit Null:</span><span class="sxs-lookup"><span data-stu-id="23c0b-191">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="23c0b-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="23c0b-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="23c0b-193">Deve essere utilizzata solo la parte Integer dell'espressione precedente.</span><span class="sxs-lookup"><span data-stu-id="23c0b-193">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="23c0b-194">Eliminare le parti restanti.</span><span class="sxs-lookup"><span data-stu-id="23c0b-194">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="23c0b-195">Calcolare le dimensioni dei dati a lunghezza variabile:</span><span class="sxs-lookup"><span data-stu-id="23c0b-195">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="23c0b-196">Se sono presenti colonne a lunghezza variabile nella chiave dell'indice, incluse eventuali colonne chiave di clustering necessarie descritte al passaggio 2.2, determinare lo spazio utilizzato per archiviare le colonne all'interno della riga di indice:</span><span class="sxs-lookup"><span data-stu-id="23c0b-196">If there are variable-length columns in the index key, including any necessary clustering key columns as described previously in Step 2.2, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="23c0b-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span><span class="sxs-lookup"><span data-stu-id="23c0b-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span></span>  
  
     <span data-ttu-id="23c0b-198">I byte aggiunti a ***Max_Var_Key_Size*** servono a tenere traccia di ogni colonna variabile. Questa formula si basa sul presupposto che tutte le colonne a lunghezza variabile siano piene al 100%.</span><span class="sxs-lookup"><span data-stu-id="23c0b-198">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="23c0b-199">Se si prevede una percentuale inferiore di utilizzo dello spazio di archiviazione delle colonne di lunghezza variabile, è possibile modificare il valore ***Max_Var_Leaf_Size*** in base a tale percentuale per ottenere una stima più precisa delle dimensioni complessive della tabella.</span><span class="sxs-lookup"><span data-stu-id="23c0b-199">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Leaf_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="23c0b-200">Se non sono disponibili colonne a lunghezza variabile, impostare ***Variable_Leaf_Size*** su 0.</span><span class="sxs-lookup"><span data-stu-id="23c0b-200">If there are no variable-length columns, set ***Variable_Leaf_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="23c0b-201">Calcolare le dimensioni della riga di indice:</span><span class="sxs-lookup"><span data-stu-id="23c0b-201">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="23c0b-202">***Leaf_Row_Size***   =  ***Fixed_Leaf_Size***  +  ***Variable_Leaf_Size***  +  ***Leaf_Null_Bitmap*** + 1 (per l'overhead dell'intestazione di riga di una riga di indice) + 6 (per il puntatore ID della pagina figlio)</span><span class="sxs-lookup"><span data-stu-id="23c0b-202">***Leaf_Row_Size***  = ***Fixed_Leaf_Size*** + ***Variable_Leaf_Size*** + ***Leaf_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="23c0b-203">Calcolare il numero di righe di indice per pagina (8096 byte liberi per pagina):</span><span class="sxs-lookup"><span data-stu-id="23c0b-203">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="23c0b-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="23c0b-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="23c0b-205">Poiché le righe di indice non si estendono su più pagine, il numero di righe di indice per pagina deve essere arrotondato alla riga completa più vicina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-205">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="23c0b-206">Il numero 2 nella formula si riferisce alla voce della riga nella matrice di slot della pagina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-206">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="23c0b-207">Calcolare il numero di righe libere riservate per pagina, in base al [fattore di riempimento](../indexes/specify-fill-factor-for-an-index.md) specificato:</span><span class="sxs-lookup"><span data-stu-id="23c0b-207">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="23c0b-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="23c0b-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="23c0b-209">Il fattore di riempimento utilizzato nel calcolo è un valore intero, non una percentuale.</span><span class="sxs-lookup"><span data-stu-id="23c0b-209">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="23c0b-210">Poiché le righe non si estendono su più pagine, il numero di righe per pagina deve essere arrotondato alla riga completa più vicina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-210">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="23c0b-211">Aumentando il fattore di riempimento, in ciascuna pagina verrà archiviata una quantità maggiore di dati e il numero di pagine diminuirà.</span><span class="sxs-lookup"><span data-stu-id="23c0b-211">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="23c0b-212">Il numero 2 nella formula si riferisce alla voce della riga nella matrice di slot della pagina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-212">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
8.  <span data-ttu-id="23c0b-213">Calcolare il numero di pagine necessario per archiviare tutte le righe:</span><span class="sxs-lookup"><span data-stu-id="23c0b-213">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="23c0b-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="23c0b-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="23c0b-215">Il numero di pagine stimato deve essere arrotondato alla pagina intera più vicina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-215">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
9. <span data-ttu-id="23c0b-216">Calcolare le dimensioni dell'indice (8192 byte totali per pagina):</span><span class="sxs-lookup"><span data-stu-id="23c0b-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="23c0b-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="23c0b-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-3-calculate-the-space-used-to-store-index-information-in-the-non-leaf-levels"></a><span data-ttu-id="23c0b-218">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="23c0b-218">Step 3.</span></span> <span data-ttu-id="23c0b-219">Calcolare lo spazio utilizzato per l'archiviazione di informazioni sull'indice nei livelli non foglia</span><span class="sxs-lookup"><span data-stu-id="23c0b-219">Calculate the Space Used to Store Index Information in the Non-leaf Levels</span></span>  
 <span data-ttu-id="23c0b-220">Per stimare la quantità di spazio necessaria per archiviare i livelli intermedio e radice dell'indice, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c0b-220">Follow these steps to estimate the amount of space that is required to store the intermediate and root levels of the index.</span></span> <span data-ttu-id="23c0b-221">Per completare questo passaggio, sono necessari i valori preservati ai passaggi 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="23c0b-221">You will need the values preserved from steps 2 and 3 to complete this step.</span></span>  
  
1.  <span data-ttu-id="23c0b-222">Calcolare il numero di livelli non foglia dell'indice:</span><span class="sxs-lookup"><span data-stu-id="23c0b-222">Calculate the number of non-leaf levels in the index:</span></span>  
  
     <span data-ttu-id="23c0b-223">***Livelli non foglia*** = 1 + Index_Rows_Per_Page di log (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="23c0b-223">***Non-leaf Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="23c0b-224">Arrotondare questo valore per eccesso al numero intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="23c0b-224">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="23c0b-225">Nel valore non è incluso il livello foglia dell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="23c0b-225">This value does not include the leaf level of the nonclustered index.</span></span>  
  
2.  <span data-ttu-id="23c0b-226">Calcolare il numero di pagine non foglia dell'indice:</span><span class="sxs-lookup"><span data-stu-id="23c0b-226">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="23c0b-227">***Num_Index_Pages*** = livello di ∑ (<sup>livello</sup>di***Num_Leaf_Pages/Index_Rows_Per_Page***) dove 1 <= livello <= ***livelli***</span><span class="sxs-lookup"><span data-stu-id="23c0b-227">***Num_Index_Pages***  = ∑Level (***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>Level</sup>)where 1 <= Level <= ***Levels***</span></span>  
  
     <span data-ttu-id="23c0b-228">Arrotondare ogni addendo al numero intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="23c0b-228">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="23c0b-229">Per un esempio semplice, considerare un indice in cui ***Num_Leaf_Pages*** = 1000 e ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="23c0b-229">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="23c0b-230">Nel primo livello dell'indice sopra il livello foglia vengono archiviate 1000 righe di indice, ovvero una riga di indice per pagina foglia, ed è possibile inserire 25 righe di indice per pagina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-230">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="23c0b-231">Per archiviare le 1000 righe di indice, sono quindi necessarie 40 pagine.</span><span class="sxs-lookup"><span data-stu-id="23c0b-231">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="23c0b-232">Nel livello successivo dell'indice devono invece essere archiviate 40 righe,</span><span class="sxs-lookup"><span data-stu-id="23c0b-232">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="23c0b-233">pertanto sono necessarie 2 pagine.</span><span class="sxs-lookup"><span data-stu-id="23c0b-233">This means that it requires 2 pages.</span></span> <span data-ttu-id="23c0b-234">Nel livello finale dell'indice devono essere archiviate 2 righe,</span><span class="sxs-lookup"><span data-stu-id="23c0b-234">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="23c0b-235">pertanto è necessaria una sola pagina.</span><span class="sxs-lookup"><span data-stu-id="23c0b-235">This means that it requires 1 page.</span></span> <span data-ttu-id="23c0b-236">Si ottengono quindi 43 pagine di indice non foglia.</span><span class="sxs-lookup"><span data-stu-id="23c0b-236">This yields 43 non-leaf index pages.</span></span> <span data-ttu-id="23c0b-237">Se nella formula precedente si utilizzano questi numeri, il risultato sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="23c0b-237">When these numbers are used in the previous formulas, the result is as follows:</span></span>  
  
     <span data-ttu-id="23c0b-238">***Non-leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="23c0b-238">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="23c0b-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, ovvero il numero di pagine descritte nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="23c0b-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
3.  <span data-ttu-id="23c0b-240">Calcolare le dimensioni dell'indice (8192 byte totali per pagina):</span><span class="sxs-lookup"><span data-stu-id="23c0b-240">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="23c0b-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="23c0b-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-4-total-the-calculated-values"></a><span data-ttu-id="23c0b-242">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="23c0b-242">Step 4.</span></span> <span data-ttu-id="23c0b-243">Sommare i valori calcolati</span><span class="sxs-lookup"><span data-stu-id="23c0b-243">Total the Calculated Values</span></span>  
 <span data-ttu-id="23c0b-244">Sommare i valori ottenuti nei due passaggi precedenti:</span><span class="sxs-lookup"><span data-stu-id="23c0b-244">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="23c0b-245">Dimensioni indice non cluster (byte) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="23c0b-245">Nonclustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="23c0b-246">Il calcolo non prende in considerazione i fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c0b-246">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="23c0b-247">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="23c0b-247">Partitioning</span></span>  
  
     <span data-ttu-id="23c0b-248">L'overhead dello spazio derivante dal partizionamento è minimo, ma difficile da calcolare.</span><span class="sxs-lookup"><span data-stu-id="23c0b-248">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="23c0b-249">Non è fondamentale includerlo.</span><span class="sxs-lookup"><span data-stu-id="23c0b-249">It is not important to include.</span></span>  
  
-   <span data-ttu-id="23c0b-250">Pagine di allocazione</span><span class="sxs-lookup"><span data-stu-id="23c0b-250">Allocation pages</span></span>  
  
     <span data-ttu-id="23c0b-251">Esiste almeno una pagina IAM utilizzata per tenere traccia delle pagine allocate su un heap, ma l'overhead dello spazio è minimo e non è presente alcun algoritmo per calcolare in modo deterministico l'esatto numero di pagine IAM che verranno utilizzate.</span><span class="sxs-lookup"><span data-stu-id="23c0b-251">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="23c0b-252">Valori LOB</span><span class="sxs-lookup"><span data-stu-id="23c0b-252">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="23c0b-253">L'algoritmo per determinare con esattezza la quantità di spazio utilizzata per archiviare i tipi di dati LOB `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` e `image` è complesso.</span><span class="sxs-lookup"><span data-stu-id="23c0b-253">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="23c0b-254">È comunque sufficiente aggiungere le dimensioni medie dei valori LOB previsti, moltiplicarle per ***Num_Rows***e aggiungere il prodotto alle dimensioni totali dell'indice non cluster.</span><span class="sxs-lookup"><span data-stu-id="23c0b-254">It is sufficient to just add the average size of the LOB values expected, multiply by ***Num_Rows***, and add that to the total nonclustered index size.</span></span>  
  
-   <span data-ttu-id="23c0b-255">Compressione</span><span class="sxs-lookup"><span data-stu-id="23c0b-255">Compression</span></span>  
  
     <span data-ttu-id="23c0b-256">Non è possibile pre-calcolare la dimensione di un indice compresso.</span><span class="sxs-lookup"><span data-stu-id="23c0b-256">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="23c0b-257">Colonne di tipo sparse</span><span class="sxs-lookup"><span data-stu-id="23c0b-257">Sparse columns</span></span>  
  
     <span data-ttu-id="23c0b-258">Per informazioni sui requisiti di spazio delle colonne di tipo sparse, vedere [Utilizzo di colonne di tipo sparse](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="23c0b-258">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c0b-259">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23c0b-259">See Also</span></span>  
 <span data-ttu-id="23c0b-260">[Descrizione di indici cluster e non cluster.](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="23c0b-260">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="23c0b-261">[Creare indici non cluster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="23c0b-261">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="23c0b-262">[Creare indici cluster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="23c0b-262">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="23c0b-263">[Stima delle dimensioni di una tabella](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="23c0b-263">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="23c0b-264">[Stima delle dimensioni di un indice cluster](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="23c0b-264">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="23c0b-265">[Stima delle dimensioni di un heap](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="23c0b-265">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="23c0b-266">Stima delle dimensioni di un database</span><span class="sxs-lookup"><span data-stu-id="23c0b-266">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
