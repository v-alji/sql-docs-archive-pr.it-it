---
title: Stimare le dimensioni di un indice cluster | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- disk space [SQL Server], indexes
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- space [SQL Server], indexes
- clustered indexes, table size
- nonclustered indexes [SQL Server], table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: 2b5137f8-98ad-46b5-9aae-4c980259bf8d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d224c5ae55cc5ec7690ca0962cbc2130bac22e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725871"
---
# <a name="estimate-the-size-of-a-clustered-index"></a><span data-ttu-id="e9010-102">Stima delle dimensioni di un indice cluster</span><span class="sxs-lookup"><span data-stu-id="e9010-102">Estimate the Size of a Clustered Index</span></span>
  <span data-ttu-id="e9010-103">Per stimare la quantità di spazio necessaria per l'archiviazione dati in un indice cluster, è possibile utilizzare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e9010-103">You can use the following steps to estimate the amount of space that is required to store data in a clustered index:</span></span>  
  
1.  <span data-ttu-id="e9010-104">Calcolare lo spazio utilizzato per archiviare dati nel livello foglia dell'indice cluster.</span><span class="sxs-lookup"><span data-stu-id="e9010-104">Calculate the space used to store data in the leaf level of the clustered index.</span></span>  
  
2.  <span data-ttu-id="e9010-105">Calcolare lo spazio utilizzato per archiviare le informazioni sugli indici per l'indice cluster.</span><span class="sxs-lookup"><span data-stu-id="e9010-105">Calculate the space used to store index information for the clustered index.</span></span>  
  
3.  <span data-ttu-id="e9010-106">Sommare i valori calcolati.</span><span class="sxs-lookup"><span data-stu-id="e9010-106">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-the-space-used-to-store-data-in-the-leaf-level"></a><span data-ttu-id="e9010-107">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="e9010-107">Step 1.</span></span> <span data-ttu-id="e9010-108">Calcolare lo spazio utilizzato per l'archiviazione di dati nel livello foglia</span><span class="sxs-lookup"><span data-stu-id="e9010-108">Calculate the Space Used to Store Data in the Leaf Level</span></span>  
  
1.  <span data-ttu-id="e9010-109">Specificare il numero di righe che verranno incluse nella tabella:</span><span class="sxs-lookup"><span data-stu-id="e9010-109">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="e9010-110">***Num_Rows***  = numero di righe della tabella</span><span class="sxs-lookup"><span data-stu-id="e9010-110">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="e9010-111">Specificare il numero di colonne di lunghezza fissa e e variabile e calcolare lo spazio necessario per la loro archiviazione:</span><span class="sxs-lookup"><span data-stu-id="e9010-111">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="e9010-112">Calcolare lo spazio occupato da ognuno di questi gruppi di colonne all'interno della riga di dati.</span><span class="sxs-lookup"><span data-stu-id="e9010-112">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="e9010-113">Le dimensioni di una colonna dipendono dal tipo di dati e dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="e9010-113">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="e9010-114">***Num_Cols***  = numero totale di colonne (a lunghezza fissa e a lunghezza variabile)</span><span class="sxs-lookup"><span data-stu-id="e9010-114">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="e9010-115">***Fixed_Data_Size***  = dimensioni totali in byte di tutte le colonne a lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="e9010-115">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="e9010-116">***Num_Variable_Cols***  = numero di colonne a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="e9010-116">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="e9010-117">***Max_Var_Size***  = dimensioni massime in byte di tutte le colonne a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="e9010-117">***Max_Var_Size***  = maximum byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="e9010-118">Se l'indice cluster è non univoco, considerare la colonna *uniqueifier* :</span><span class="sxs-lookup"><span data-stu-id="e9010-118">If the clustered index is nonunique, account for the *uniqueifier* column:</span></span>  
  
     <span data-ttu-id="e9010-119">La colonna uniqueifier è una colonna a lunghezza variabile che ammette valori Null.</span><span class="sxs-lookup"><span data-stu-id="e9010-119">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="e9010-120">Sarà una colonna non Null da 4 byte nelle righe che includono valori chiave non univoci.</span><span class="sxs-lookup"><span data-stu-id="e9010-120">It will be nonnull and 4 bytes in size in rows that have nonunique key values.</span></span> <span data-ttu-id="e9010-121">Questo valore fa parte della chiave di indice ed è necessario per garantire che ogni riga includa un valore di chiave univoco.</span><span class="sxs-lookup"><span data-stu-id="e9010-121">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="e9010-122">***Num_Cols***  = ***Num_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e9010-122">***Num_Cols***  = ***Num_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e9010-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e9010-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e9010-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="e9010-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span></span>  
  
     <span data-ttu-id="e9010-125">In queste modifiche si presuppone che tutti i valori siano non univoci.</span><span class="sxs-lookup"><span data-stu-id="e9010-125">These modifications assume that all values will be nonunique.</span></span>  
  
4.  <span data-ttu-id="e9010-126">Parte della riga, nota come mappa di bit null, è riservata alla gestione del supporto dei valori Null in una colonna.</span><span class="sxs-lookup"><span data-stu-id="e9010-126">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="e9010-127">Calcolarne le dimensioni:</span><span class="sxs-lookup"><span data-stu-id="e9010-127">Calculate its size:</span></span>  
  
     <span data-ttu-id="e9010-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="e9010-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="e9010-129">Utilizzare solo la parte intera del risultato dell'espressione indicata in precedenza, eliminando eventuali residui.</span><span class="sxs-lookup"><span data-stu-id="e9010-129">Only the integer part of the previous expression should be used; discard any remainder.</span></span>  
  
5.  <span data-ttu-id="e9010-130">Calcolare le dimensioni dei dati di lunghezza variabile:</span><span class="sxs-lookup"><span data-stu-id="e9010-130">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="e9010-131">Se la tabella include colonne di lunghezza variabile, determinare la quantità di spazio utilizzata per l'archiviazione delle colonne nella riga:</span><span class="sxs-lookup"><span data-stu-id="e9010-131">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="e9010-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="e9010-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="e9010-133">I byte aggiunti a ***Max_Var_Size*** servono a tenere traccia di ogni colonna variabile.</span><span class="sxs-lookup"><span data-stu-id="e9010-133">The bytes added to ***Max_Var_Size*** are for tracking each variable column.</span></span> <span data-ttu-id="e9010-134">Questa formula si basa sul presupposto che tutte le colonne a lunghezza variabile siano piene al 100%.</span><span class="sxs-lookup"><span data-stu-id="e9010-134">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="e9010-135">Se si prevede una percentuale inferiore di utilizzo dello spazio di archiviazione delle colonne a lunghezza variabile, è possibile modificare il valore di ***Max_Var_Size*** in base a tale percentuale per ottenere una stima più accurata delle dimensioni complessive della tabella.</span><span class="sxs-lookup"><span data-stu-id="e9010-135">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e9010-136">È possibile combinare colonne `varchar`, `nvarchar`, `varbinary` o `sql_variant` che fanno eccedere gli 8.060 byte per la larghezza totale definita della tabella.</span><span class="sxs-lookup"><span data-stu-id="e9010-136">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="e9010-137">La lunghezza di ogni colonna deve essere compresa nel limite di 8.000 byte per una colonna `varchar`, `varbinary` o `sql_variant` e di 4.000 byte per le colonne `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="e9010-137">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="e9010-138">Le larghezze combinate di tali colonne possono tuttavia superare il limite di 8.060 byte in una tabella.</span><span class="sxs-lookup"><span data-stu-id="e9010-138">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="e9010-139">Se non sono disponibili colonne di lunghezza variabile, impostare ***Variable_Data_Size*** su 0.</span><span class="sxs-lookup"><span data-stu-id="e9010-139">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="e9010-140">Calcolare le dimensioni totali della riga:</span><span class="sxs-lookup"><span data-stu-id="e9010-140">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="e9010-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="e9010-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="e9010-142">Il valore 4 rappresenta l'overhead dell'intestazione di riga di una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="e9010-142">The value 4 is the row header overhead of a data row.</span></span>  
  
7.  <span data-ttu-id="e9010-143">Calcolare il numero di righe per pagina (8096 byte liberi per pagina):</span><span class="sxs-lookup"><span data-stu-id="e9010-143">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="e9010-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e9010-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e9010-145">Poiché le righe non si estendono su più pagine, il numero di righe per pagina deve essere arrotondato alla riga completa più vicina.</span><span class="sxs-lookup"><span data-stu-id="e9010-145">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e9010-146">Il valore 2 nella formula è per la voce di riga nella matrice di slot della pagina.</span><span class="sxs-lookup"><span data-stu-id="e9010-146">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
8.  <span data-ttu-id="e9010-147">Calcolare il numero di righe libere riservate per pagina, in base al [fattore di riempimento](../indexes/specify-fill-factor-for-an-index.md) specificato:</span><span class="sxs-lookup"><span data-stu-id="e9010-147">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="e9010-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e9010-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e9010-149">Il fattore di riempimento utilizzato nel calcolo è un valore intero, non una percentuale.</span><span class="sxs-lookup"><span data-stu-id="e9010-149">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="e9010-150">Poiché le righe non si estendono su più pagine, il numero di righe per pagina deve essere arrotondato alla riga completa più vicina.</span><span class="sxs-lookup"><span data-stu-id="e9010-150">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e9010-151">Aumentando il fattore di riempimento, in ciascuna pagina verrà archiviata una quantità maggiore di dati e il numero di pagine diminuirà.</span><span class="sxs-lookup"><span data-stu-id="e9010-151">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="e9010-152">Il valore 2 nella formula è per la voce di riga nella matrice di slot della pagina.</span><span class="sxs-lookup"><span data-stu-id="e9010-152">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
9. <span data-ttu-id="e9010-153">Calcolare il numero di pagine necessario per archiviare tutte le righe:</span><span class="sxs-lookup"><span data-stu-id="e9010-153">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="e9010-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="e9010-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="e9010-155">Il numero di pagine stimato deve essere arrotondato alla pagina intera più vicina.</span><span class="sxs-lookup"><span data-stu-id="e9010-155">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
10. <span data-ttu-id="e9010-156">Calcolare la quantità di spazio necessaria per l'archiviazione dei dati nel livello foglia (8192 byte totali per pagina):</span><span class="sxs-lookup"><span data-stu-id="e9010-156">Calculate the amount of space that is required to store the data in the leaf level (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="e9010-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="e9010-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information"></a><span data-ttu-id="e9010-158">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="e9010-158">Step 2.</span></span> <span data-ttu-id="e9010-159">Calcolare lo spazio utilizzato per l'archiviazione di informazioni sull'indice</span><span class="sxs-lookup"><span data-stu-id="e9010-159">Calculate the Space Used to Store Index Information</span></span>  
 <span data-ttu-id="e9010-160">Per stimare la quantità di spazio necessario per archiviare i livelli superiori dell'indice, è possibile utilizzare la seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="e9010-160">You can use the following steps to estimate the amount of space that is required to store the upper levels of the index:</span></span>  
  
1.  <span data-ttu-id="e9010-161">Specificare il numero di colonne a lunghezza fissa e a lunghezza variabile incluse nella chiave dell'indice e calcolare lo spazio necessario per archiviarle:</span><span class="sxs-lookup"><span data-stu-id="e9010-161">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="e9010-162">Le colonne chiave di un indice possono includere colonne a lunghezza fissa e a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="e9010-162">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="e9010-163">Per stimare le dimensioni delle righe di indice di livello interno, calcolare lo spazio occupato da ognuno di questi gruppi di colonne all'interno della riga di indice.</span><span class="sxs-lookup"><span data-stu-id="e9010-163">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="e9010-164">Le dimensioni di una colonna dipendono dal tipo di dati e dalla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="e9010-164">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="e9010-165">***Num_Key_Cols***  = numero totale di colonne chiave (a lunghezza fissa e a lunghezza variabile)</span><span class="sxs-lookup"><span data-stu-id="e9010-165">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="e9010-166">***Fixed_Key_Size***  = dimensioni totali in byte di tutte le colonne chiave a lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="e9010-166">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="e9010-167">***Num_Variable_Key_Cols***  = numero di colonne chiave a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="e9010-167">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="e9010-168">***Max_Var_Key_Size***  = dimensioni massime in byte di tutte le colonne chiave a lunghezza variabile</span><span class="sxs-lookup"><span data-stu-id="e9010-168">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
2.  <span data-ttu-id="e9010-169">Considerare le eventuali colonne uniqueifier necessarie se l'indice è non univoco:</span><span class="sxs-lookup"><span data-stu-id="e9010-169">Account for any uniqueifier needed if the index is nonunique:</span></span>  
  
     <span data-ttu-id="e9010-170">La colonna uniqueifier è una colonna a lunghezza variabile che ammette valori Null.</span><span class="sxs-lookup"><span data-stu-id="e9010-170">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="e9010-171">Sarà una colonna non Null da 4 byte nelle righe che includono valori chiave di indice non univoci.</span><span class="sxs-lookup"><span data-stu-id="e9010-171">It will be nonnull and 4 bytes in size in rows that have nonunique index key values.</span></span> <span data-ttu-id="e9010-172">Questo valore fa parte della chiave di indice ed è necessario per garantire che ogni riga includa un valore di chiave univoco.</span><span class="sxs-lookup"><span data-stu-id="e9010-172">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="e9010-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e9010-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e9010-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="e9010-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="e9010-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="e9010-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span></span>  
  
     <span data-ttu-id="e9010-176">In queste modifiche si presuppone che tutti i valori siano non univoci.</span><span class="sxs-lookup"><span data-stu-id="e9010-176">These modifications assume that all values will be nonunique.</span></span>  
  
3.  <span data-ttu-id="e9010-177">Calcolare le dimensioni della mappa di bit Null:</span><span class="sxs-lookup"><span data-stu-id="e9010-177">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="e9010-178">Se nella chiave di indice sono incluse colonne che ammettono valori Null, una parte della riga di indice viene riservata per la mappa di bit Null.</span><span class="sxs-lookup"><span data-stu-id="e9010-178">If there are nullable columns in the index key, part of the index row is reserved for the null bitmap.</span></span> <span data-ttu-id="e9010-179">Calcolarne le dimensioni:</span><span class="sxs-lookup"><span data-stu-id="e9010-179">Calculate its size:</span></span>  
  
     <span data-ttu-id="e9010-180">***Index_Null_Bitmap***  = 2 + ((numero di colonne nella riga di indice + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="e9010-180">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="e9010-181">Deve essere utilizzata solo la parte Integer dell'espressione precedente.</span><span class="sxs-lookup"><span data-stu-id="e9010-181">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="e9010-182">Eliminare le parti restanti.</span><span class="sxs-lookup"><span data-stu-id="e9010-182">Discard any remainder.</span></span>  
  
     <span data-ttu-id="e9010-183">Se invece non sono disponibili colonne chiave che ammettono i valori Null, impostare ***Index_Null_Bitmap*** su 0.</span><span class="sxs-lookup"><span data-stu-id="e9010-183">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
4.  <span data-ttu-id="e9010-184">Calcolare le dimensioni dei dati di lunghezza variabile:</span><span class="sxs-lookup"><span data-stu-id="e9010-184">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="e9010-185">Se l'indice include colonne a lunghezza variabile, determinare la quantità di spazio utilizzata per l'archiviazione delle colonne nella riga di indice:</span><span class="sxs-lookup"><span data-stu-id="e9010-185">If there are variable-length columns in the index, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="e9010-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="e9010-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="e9010-187">I byte aggiunti a ***Max_Var_Key_Size*** servono a tenere traccia di ogni colonna a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="e9010-187">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="e9010-188">Questa formula si basa sul presupposto che tutte le colonne a lunghezza variabile siano piene al 100%.</span><span class="sxs-lookup"><span data-stu-id="e9010-188">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="e9010-189">Se si prevede una percentuale inferiore di utilizzo dello spazio di archiviazione delle colonne a lunghezza variabile, è possibile modificare il valore di ***Max_Var_Key_Size*** in base a tale percentuale per ottenere una stima più accurata delle dimensioni complessive della tabella.</span><span class="sxs-lookup"><span data-stu-id="e9010-189">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="e9010-190">Se non sono disponibili colonne a lunghezza variabile, impostare ***Variable_Key_Size*** su 0.</span><span class="sxs-lookup"><span data-stu-id="e9010-190">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="e9010-191">Calcolare le dimensioni della riga di indice:</span><span class="sxs-lookup"><span data-stu-id="e9010-191">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="e9010-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (per l'overhead dell'intestazione di una riga di indice) + 6 (per il puntatore ID della pagina figlio)</span><span class="sxs-lookup"><span data-stu-id="e9010-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="e9010-193">Calcolare il numero di righe di indice per pagina (8096 byte liberi per pagina):</span><span class="sxs-lookup"><span data-stu-id="e9010-193">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="e9010-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="e9010-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="e9010-195">Poiché le righe di indice non si estendono su più pagine, il numero di righe di indice per pagina deve essere arrotondato alla riga completa più vicina.</span><span class="sxs-lookup"><span data-stu-id="e9010-195">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="e9010-196">Il numero 2 nella formula si riferisce alla voce della riga nella matrice di slot della pagina.</span><span class="sxs-lookup"><span data-stu-id="e9010-196">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="e9010-197">Calcolare il numero di livelli nell'indice:</span><span class="sxs-lookup"><span data-stu-id="e9010-197">Calculate the number of levels in the index:</span></span>  
  
     <span data-ttu-id="e9010-198">***Non-leaf_Levels*** = 1 + Index_Rows_Per_Page di log (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="e9010-198">***Non-leaf_Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="e9010-199">Arrotondare questo valore per eccesso al numero intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="e9010-199">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="e9010-200">Nel valore non è incluso il livello foglia dell'indice cluster.</span><span class="sxs-lookup"><span data-stu-id="e9010-200">This value does not include the leaf level of the clustered index.</span></span>  
  
8.  <span data-ttu-id="e9010-201">Calcolare il numero di pagine non foglia dell'indice:</span><span class="sxs-lookup"><span data-stu-id="e9010-201">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="e9010-202">***Num_Index_Pages =*** livello ∑ ***(Num_Leaf_Pages/(***<sup>livello</sup>Index_Rows_Per_Page ***))***</span><span class="sxs-lookup"><span data-stu-id="e9010-202">***Num_Index_Pages =*** ∑Level ***(Num_Leaf_Pages / (Index_Rows_Per_Page***<sup>Level</sup>***))***</span></span>  
  
     <span data-ttu-id="e9010-203">dove 1 <= Level <= ***Non-leaf_Levels***</span><span class="sxs-lookup"><span data-stu-id="e9010-203">where 1 <= Level <= ***Non-leaf_Levels***</span></span>  
  
     <span data-ttu-id="e9010-204">Arrotondare ogni addendo al numero intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="e9010-204">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="e9010-205">Per un esempio semplice, considerare un indice in cui ***Num_Leaf_Pages*** = 1000 e ***Index_Rows_Per_Page*** = 25.</span><span class="sxs-lookup"><span data-stu-id="e9010-205">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="e9010-206">Nel primo livello dell'indice sopra il livello foglia vengono archiviate 1000 righe di indice, ovvero una riga di indice per pagina foglia, ed è possibile inserire 25 righe di indice per pagina.</span><span class="sxs-lookup"><span data-stu-id="e9010-206">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="e9010-207">Per archiviare le 1000 righe di indice, sono quindi necessarie 40 pagine.</span><span class="sxs-lookup"><span data-stu-id="e9010-207">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="e9010-208">Nel livello successivo dell'indice devono invece essere archiviate 40 righe,</span><span class="sxs-lookup"><span data-stu-id="e9010-208">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="e9010-209">pertanto sono necessarie 2 pagine.</span><span class="sxs-lookup"><span data-stu-id="e9010-209">This means it requires 2 pages.</span></span> <span data-ttu-id="e9010-210">Nel livello finale dell'indice devono essere archiviate 2 righe,</span><span class="sxs-lookup"><span data-stu-id="e9010-210">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="e9010-211">pertanto è necessaria una sola pagina.</span><span class="sxs-lookup"><span data-stu-id="e9010-211">This means it requires 1 page.</span></span> <span data-ttu-id="e9010-212">Si ottengono quindi 43 pagine di indice non foglia.</span><span class="sxs-lookup"><span data-stu-id="e9010-212">This gives 43 non-leaf index pages.</span></span> <span data-ttu-id="e9010-213">Se nella formula precedente si utilizzano questi numeri, il risultato sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="e9010-213">When these numbers are used in the previous formulas, the outcome is as follows:</span></span>  
  
     <span data-ttu-id="e9010-214">***Non-leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="e9010-214">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="e9010-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, ovvero il numero di pagine descritte nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="e9010-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
9. <span data-ttu-id="e9010-216">Calcolare le dimensioni dell'indice (8192 byte totali per pagina):</span><span class="sxs-lookup"><span data-stu-id="e9010-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="e9010-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="e9010-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-3-total-the-calculated-values"></a><span data-ttu-id="e9010-218">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e9010-218">Step 3.</span></span> <span data-ttu-id="e9010-219">Sommare i valori calcolati</span><span class="sxs-lookup"><span data-stu-id="e9010-219">Total the Calculated Values</span></span>  
 <span data-ttu-id="e9010-220">Sommare i valori ottenuti nei due passaggi precedenti:</span><span class="sxs-lookup"><span data-stu-id="e9010-220">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="e9010-221">Dimensioni indice cluster (byte) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="e9010-221">Clustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="e9010-222">Il calcolo non prende in considerazione i fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9010-222">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="e9010-223">Partizionamento</span><span class="sxs-lookup"><span data-stu-id="e9010-223">Partitioning</span></span>  
  
     <span data-ttu-id="e9010-224">L'overhead dello spazio derivante dal partizionamento è minimo, ma difficile da calcolare.</span><span class="sxs-lookup"><span data-stu-id="e9010-224">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="e9010-225">Non è fondamentale includerlo.</span><span class="sxs-lookup"><span data-stu-id="e9010-225">It is not important to include.</span></span>  
  
-   <span data-ttu-id="e9010-226">Pagine di allocazione</span><span class="sxs-lookup"><span data-stu-id="e9010-226">Allocation pages</span></span>  
  
     <span data-ttu-id="e9010-227">Esiste almeno una pagina IAM utilizzata per tenere traccia delle pagine allocate su un heap, ma l'overhead dello spazio è minimo e non è presente alcun algoritmo per calcolare in modo deterministico l'esatto numero di pagine IAM che verranno utilizzate.</span><span class="sxs-lookup"><span data-stu-id="e9010-227">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="e9010-228">Valori LOB</span><span class="sxs-lookup"><span data-stu-id="e9010-228">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="e9010-229">L'algoritmo per determinare con esattezza la quantità di spazio utilizzata per archiviare i tipi di dati LOB `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` e `image` è complesso.</span><span class="sxs-lookup"><span data-stu-id="e9010-229">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="e9010-230">È sufficiente aggiungere le dimensioni medie dei valori LOB previste, moltiplicare per ***Num_Rows***e quindi aggiungere il valore ottenuto alle dimensioni totali dell'indice cluster.</span><span class="sxs-lookup"><span data-stu-id="e9010-230">It is sufficient to just add the average size of the LOB values that are expected, multiply by ***Num_Rows***, and add that to the total clustered index size.</span></span>  
  
-   <span data-ttu-id="e9010-231">Compressione</span><span class="sxs-lookup"><span data-stu-id="e9010-231">Compression</span></span>  
  
     <span data-ttu-id="e9010-232">Non è possibile pre-calcolare la dimensione di un indice compresso.</span><span class="sxs-lookup"><span data-stu-id="e9010-232">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="e9010-233">Colonne di tipo sparse</span><span class="sxs-lookup"><span data-stu-id="e9010-233">Sparse columns</span></span>  
  
     <span data-ttu-id="e9010-234">Per informazioni sui requisiti di spazio delle colonne di tipo sparse, vedere [Utilizzo di colonne di tipo sparse](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e9010-234">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9010-235">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9010-235">See Also</span></span>  
 <span data-ttu-id="e9010-236">[Descrizione di indici cluster e non cluster.](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="e9010-236">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="e9010-237">[Stima delle dimensioni di una tabella](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="e9010-237">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="e9010-238">[Creare indici cluster](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="e9010-238">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="e9010-239">[Creare indici non cluster](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="e9010-239">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="e9010-240">[Stima delle dimensioni di un indice non cluster](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="e9010-240">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 <span data-ttu-id="e9010-241">[Stima delle dimensioni di un heap](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="e9010-241">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="e9010-242">Stima delle dimensioni di un database</span><span class="sxs-lookup"><span data-stu-id="e9010-242">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
