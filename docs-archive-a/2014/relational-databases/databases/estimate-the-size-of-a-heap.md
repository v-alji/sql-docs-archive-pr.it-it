---
title: Stimare le dimensioni di un heap | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- estimating heap size
- size [SQL Server], heap
- space [SQL Server], indexes
- heaps
ms.assetid: 81fd5ec9-ce0f-4c2c-8ba0-6c483cea6c75
author: stevestein
ms.author: sstein
ms.openlocfilehash: f32432d07a9731d849ceb793daf209cfc505b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637876"
---
# <a name="estimate-the-size-of-a-heap"></a><span data-ttu-id="c9e3e-102">Stima delle dimensioni di un heap</span><span class="sxs-lookup"><span data-stu-id="c9e3e-102">Estimate the Size of a Heap</span></span>
  <span data-ttu-id="c9e3e-103">I seguenti passaggi sono utilizzabili per valutare la quantità di spazio necessaria per l'archiviazione dei dati in un heap:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-103">You can use the following steps to estimate the amount of space that is required to store data in a heap:</span></span>  
  
1.  <span data-ttu-id="c9e3e-104">Specificare il numero di righe che verranno incluse nella tabella:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-104">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="c9e3e-105">***Num_Rows***  = numero di righe della tabella</span><span class="sxs-lookup"><span data-stu-id="c9e3e-105">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="c9e3e-106">Specificare il numero di colonne di lunghezza fissa e e variabile e calcolare lo spazio necessario per la loro archiviazione:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-106">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="c9e3e-107">Calcolare lo spazio occupato da ognuno di questi gruppi di colonne all'interno della riga di dati.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-107">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="c9e3e-108">Le dimensioni di una colonna dipendono dal tipo di dati e dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-108">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="c9e3e-109">***Num_Cols***  = numero totale di colonne (a lunghezza fissa e a lunghezza variabile)</span><span class="sxs-lookup"><span data-stu-id="c9e3e-109">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="c9e3e-110">***Fixed_Data_Size***  = dimensioni totali in byte di tutte le colonne a lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="c9e3e-110">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="c9e3e-111">***Num_Variable_Cols***  = numero di colonne a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="c9e3e-111">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="c9e3e-112">***Max_Var_Size***  = dimensioni massime totali in byte di tutte le colonne a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="c9e3e-112">***Max_Var_Size***  = maximum total byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="c9e3e-113">Parte della riga, nota come mappa di bit null, è riservata alla gestione del supporto dei valori Null in una colonna.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-113">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="c9e3e-114">Calcolarne le dimensioni:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-114">Calculate its size:</span></span>  
  
     <span data-ttu-id="c9e3e-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="c9e3e-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="c9e3e-116">Solo l'integrale di questa espressione dovrebbe essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-116">Only the integer part of this expression should be used.</span></span> <span data-ttu-id="c9e3e-117">Eliminare le parti restanti.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-117">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="c9e3e-118">Calcolare le dimensioni dei dati di lunghezza variabile:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-118">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="c9e3e-119">Se la tabella include colonne di lunghezza variabile, determinare la quantità di spazio utilizzata per l'archiviazione delle colonne nella riga:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-119">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="c9e3e-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="c9e3e-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="c9e3e-121">I byte aggiunti a ***Max_Var_Size*** servono a tenere traccia di ogni colonna a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-121">The bytes added to ***Max_Var_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="c9e3e-122">Questa formula si basa sul presupposto che tutte le colonne a lunghezza variabile siano piene al 100%.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-122">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="c9e3e-123">Se si prevede una percentuale inferiore di utilizzo dello spazio di archiviazione delle colonne a lunghezza variabile, è possibile modificare il valore di ***Max_Var_Size*** in base a tale percentuale per ottenere una stima più accurata delle dimensioni complessive della tabella.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-123">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9e3e-124">È possibile combinare colonne `varchar`, `nvarchar`, `varbinary` o `sql_variant` che fanno eccedere gli 8.060 byte per la larghezza totale definita della tabella.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-124">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="c9e3e-125">La lunghezza di ogni colonna deve comunque rientrare nel limite di 8.000 byte per una `varchar` `nvarchar,``varbinary` colonna, o `sql_variant` .</span><span class="sxs-lookup"><span data-stu-id="c9e3e-125">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `nvarchar,``varbinary`, or `sql_variant` column.</span></span> <span data-ttu-id="c9e3e-126">Le larghezze combinate di tali colonne possono tuttavia superare il limite di 8.060 byte in una tabella.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-126">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="c9e3e-127">Se non sono disponibili colonne di lunghezza variabile, impostare ***Variable_Data_Size*** su 0.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-127">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="c9e3e-128">Calcolare le dimensioni totali della riga:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-128">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="c9e3e-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="c9e3e-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="c9e3e-130">Il valore 4 nel formula è l'overhead dell'intestazione di riga della riga di dati.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-130">The value 4 in the formula is the row header overhead of the data row.</span></span>  
  
6.  <span data-ttu-id="c9e3e-131">Calcolare il numero di righe per pagina (8096 byte liberi per pagina):</span><span class="sxs-lookup"><span data-stu-id="c9e3e-131">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="c9e3e-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="c9e3e-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="c9e3e-133">Poiché le righe non si estendono su più pagine, il numero di righe per pagina deve essere arrotondato alla riga completa più vicina.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-133">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="c9e3e-134">Il valore 2 nella formula è per la voce di riga nella matrice di slot della pagina.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-134">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
7.  <span data-ttu-id="c9e3e-135">Calcolare il numero di pagine necessario per archiviare tutte le righe:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-135">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="c9e3e-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span><span class="sxs-lookup"><span data-stu-id="c9e3e-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span></span>  
  
     <span data-ttu-id="c9e3e-137">Il numero di pagine stimato deve essere arrotondato alla pagina intera più vicina.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-137">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
8.  <span data-ttu-id="c9e3e-138">Infine, calcolare la quantità di spazio necessaria per archiviare i dati nell'heap (8192 byte totali per pagina):</span><span class="sxs-lookup"><span data-stu-id="c9e3e-138">Calculate the amount of space that is required to store the data in the heap (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="c9e3e-139">Dimensioni dell'heap (byte) = 8192 x ***Num_Pages***</span><span class="sxs-lookup"><span data-stu-id="c9e3e-139">Heap size (bytes) = 8192 x ***Num_Pages***</span></span>  
  
 <span data-ttu-id="c9e3e-140">Il calcolo non prende in considerazione i fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9e3e-140">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="c9e3e-141">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="c9e3e-141">Partitioning</span></span>  
  
     <span data-ttu-id="c9e3e-142">L'overhead dello spazio derivante dal partizionamento è minimo, ma difficile da calcolare.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-142">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="c9e3e-143">Non è fondamentale includerlo.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-143">It is not important to include.</span></span>  
  
-   <span data-ttu-id="c9e3e-144">Pagine di allocazione</span><span class="sxs-lookup"><span data-stu-id="c9e3e-144">Allocation pages</span></span>  
  
     <span data-ttu-id="c9e3e-145">Esiste almeno una pagina IAM utilizzata per tenere traccia delle pagine allocate su un heap, ma l'overhead dello spazio è minimo e non è presente alcun algoritmo per calcolare in modo deterministico l'esatto numero di pagine IAM che verranno utilizzate.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-145">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="c9e3e-146">Valori LOB</span><span class="sxs-lookup"><span data-stu-id="c9e3e-146">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="c9e3e-147">L'algoritmo per determinare esattamente la quantità di spazio utilizzata per archiviare i tipi di dati LOB `varchar(max)` ,,, `varbinary(max)` `nvarchar(max)` `text` , **ntextxml**e `image` i valori è complesso.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-147">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, **ntextxml**, and `image` values is complex.</span></span> <span data-ttu-id="c9e3e-148">È sufficiente aggiungere soltanto le dimensioni medie dei valori LOB previsti e aggiungerle alle dimensioni totali dell'heap.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-148">It is sufficient to just add the average size of the LOB values that are expected and add that to the total heap size.</span></span>  
  
-   <span data-ttu-id="c9e3e-149">Compressione</span><span class="sxs-lookup"><span data-stu-id="c9e3e-149">Compression</span></span>  
  
     <span data-ttu-id="c9e3e-150">Non è possibile pre-calcolare la dimensione di un heap compresso.</span><span class="sxs-lookup"><span data-stu-id="c9e3e-150">You cannot pre-calculate the size of a compressed heap.</span></span>  
  
-   <span data-ttu-id="c9e3e-151">Colonne di tipo sparse</span><span class="sxs-lookup"><span data-stu-id="c9e3e-151">Sparse columns</span></span>  
  
     <span data-ttu-id="c9e3e-152">Per informazioni sui requisiti di spazio delle colonne di tipo sparse, vedere [Utilizzo di colonne di tipo sparse](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="c9e3e-152">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e3e-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e3e-153">See Also</span></span>  
 <span data-ttu-id="c9e3e-154">[Heap &#40;tabelle senza indici cluster&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3e-154">[Heaps &#40;Tables without Clustered Indexes&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span></span>  
 <span data-ttu-id="c9e3e-155">[Descrizione di indici cluster e non cluster.](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3e-155">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="c9e3e-156">[Creare indici cluster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3e-156">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="c9e3e-157">[Creare indici non cluster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3e-157">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="c9e3e-158">[Stima delle dimensioni di una tabella](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3e-158">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="c9e3e-159">[Stima delle dimensioni di un indice cluster](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3e-159">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="c9e3e-160">[Stima delle dimensioni di un indice non cluster](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3e-160">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 [<span data-ttu-id="c9e3e-161">Stima delle dimensioni di un database</span><span class="sxs-lookup"><span data-stu-id="c9e3e-161">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
