---
title: Dimensioni di tabelle e righe per le tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b0a248a4-4488-4cc8-89fc-46906a8c24a1
author: rothja
ms.author: jroth
ms.openlocfilehash: 74cc40b7d1f2d0132d79d1e9ae15c2321ac9b74a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725728"
---
# <a name="table-and-row-size-in-memory-optimized-tables"></a><span data-ttu-id="246e5-102">Dimensioni di tabelle e righe per le tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="246e5-102">Table and Row Size in Memory-Optimized Tables</span></span>
  <span data-ttu-id="246e5-103">Una tabella ottimizzata per la memoria è costituita da una raccolta di righe e di indici contenenti i puntatori alle righe.</span><span class="sxs-lookup"><span data-stu-id="246e5-103">A memory-optimized table consists of a collection of rows and indexes that contain pointers to rows.</span></span> <span data-ttu-id="246e5-104">In una tabella ottimizzata per la memoria, le righe non possono essere più lunghe di 8.060 byte.</span><span class="sxs-lookup"><span data-stu-id="246e5-104">In a memory-optimized table, rows cannot be longer than 8,060 bytes.</span></span> <span data-ttu-id="246e5-105">Comprendere le dimensioni di una tabella ottimizzata per la memoria è importante per capire se il computer dispone di una quantità di memoria sufficiente.</span><span class="sxs-lookup"><span data-stu-id="246e5-105">Understanding the size of a memory-optimized table will help you understand if your computer has enough memory.</span></span>  
  
 <span data-ttu-id="246e5-106">Esistono due motivi per calcolare le dimensioni di righe e tabelle:</span><span class="sxs-lookup"><span data-stu-id="246e5-106">There are two reasons for computing table and row size:</span></span>  
  
-   <span data-ttu-id="246e5-107">Quanta memoria viene utilizzata da una tabella?</span><span class="sxs-lookup"><span data-stu-id="246e5-107">How much memory does a table use?</span></span>  
  
    -   <span data-ttu-id="246e5-108">La quantità di memoria utilizzata dalla tabella non può essere calcolata esattamente.</span><span class="sxs-lookup"><span data-stu-id="246e5-108">The amount of memory used by the table cannot be calculated exactly.</span></span> <span data-ttu-id="246e5-109">Molti fattori influiscono su tale quantità,</span><span class="sxs-lookup"><span data-stu-id="246e5-109">Many factors affect the amount of memory used.</span></span> <span data-ttu-id="246e5-110">ad esempio l'allocazione della memoria basata sul paging, la località, la memorizzazione nella cache e il riempimento.</span><span class="sxs-lookup"><span data-stu-id="246e5-110">Factors such as page-based memory allocation, locality, caching, and padding.</span></span> <span data-ttu-id="246e5-111">Un altro fattore può essere la presenza di più versioni delle righe a cui sono associate transazioni attive o che sono in attesa di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="246e5-111">Also, multiple versions of rows that either have active transactions associated or that are waiting for garbage collection.</span></span>  
  
    -   <span data-ttu-id="246e5-112">Le dimensioni minime richieste per i dati e gli indici nella tabella si ottengono con il calcolo di [table size] descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="246e5-112">The minimum size required for the data and indexes in the table is given by the calculation for [table size], discussed below.</span></span>  
  
    -   <span data-ttu-id="246e5-113">Il calcolo dell'utilizzo della memoria è nella migliore delle ipotesi un'approssimazione ed è consigliabile includere la pianificazione della capacità nei piani di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="246e5-113">Calculating memory use is at best an approximation and you are advised to include capacity planning in your deployment plans.</span></span>  
  
-   <span data-ttu-id="246e5-114">Quali sono le dimensioni dei dati di una riga? Tali dimensioni rientrano nel limite di 8.060 byte?</span><span class="sxs-lookup"><span data-stu-id="246e5-114">The data size of a row, and does it fit in the 8,060 byte row size limitation?</span></span> <span data-ttu-id="246e5-115">Per rispondere a queste domande, utilizzare il calcolo di [row body size] descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="246e5-115">To answer these questions, use the computation for [row body size], discussed below.</span></span>  
  
 <span data-ttu-id="246e5-116">Nella figura seguente viene illustrata una tabella con indici e righe, che a loro volta contengono intestazioni e corpi di riga:</span><span class="sxs-lookup"><span data-stu-id="246e5-116">The following figure illustrates a table with indexes and rows, which in turn have row headers and bodies:</span></span>  
  
 <span data-ttu-id="246e5-117">![Tabella con ottimizzazione per la memoria.](../../database-engine/media/hekaton-guide-1.gif "Tabella con ottimizzazione per la memoria.")</span><span class="sxs-lookup"><span data-stu-id="246e5-117">![Memory optimized table.](../../database-engine/media/hekaton-guide-1.gif "Memory optimized table.")</span></span>  
<span data-ttu-id="246e5-118">Tabella con ottimizzazione per la memoria, costituita da indici e righe.</span><span class="sxs-lookup"><span data-stu-id="246e5-118">Memory-optimized table, consisting of indexes and rows.</span></span>  
  
 <span data-ttu-id="246e5-119">Le dimensioni in memoria di una tabella, in byte, vengono calcolate come segue:</span><span class="sxs-lookup"><span data-stu-id="246e5-119">The in-memory size of a table, in bytes, is computed as follows:</span></span>  
  
```  
[table size] = [size of index 1] + ... + [size of index n] + ([row size] * [row count])  
```  
  
 <span data-ttu-id="246e5-120">Le dimensioni di un indice hash vengono fissate al momento della creazione della tabella e dipendono dal numero effettivo di bucket.</span><span class="sxs-lookup"><span data-stu-id="246e5-120">The size of a hash index is fixed at table creation time and depends on the actual bucket count.</span></span> <span data-ttu-id="246e5-121">Il valore di bucket_count specificato con la specifica dell'indice viene arrotondato per eccesso alla più vicina potenza di 2 per ottenere il valore [actual bucket count].</span><span class="sxs-lookup"><span data-stu-id="246e5-121">The bucket_count specified with the index specification is rounded up to the nearest power of 2 to obtain the [actual bucket count].</span></span> <span data-ttu-id="246e5-122">Ad esempio, se il valore di bucket_count specificato è 100.000, il valore di [actual bucket count] per l'indice è 131.072.</span><span class="sxs-lookup"><span data-stu-id="246e5-122">For example, if the specified bucket_count is 100000, the [actual bucket count] for the index is 131072.</span></span>  
  
```  
[hash index size] = 8 * [actual bucket count]  
```  
  
 <span data-ttu-id="246e5-123">Le dimensioni delle righe vengono calcolate aggiungendo l'intestazione e il corpo:</span><span class="sxs-lookup"><span data-stu-id="246e5-123">The row size is computed by adding the header and the body:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices]  
```  
  
 <span data-ttu-id="246e5-124">**Dimensioni del corpo delle righe**</span><span class="sxs-lookup"><span data-stu-id="246e5-124">**Row body size**</span></span>  
  
 <span data-ttu-id="246e5-125">Il calcolo di [row body size] viene descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="246e5-125">The calculation of [row body size] is discussed in the following table.</span></span>  
  
 <span data-ttu-id="246e5-126">Le dimensioni del corpo delle righe possono essere considerate da due punti di vista diversi, le dimensioni calcolate e le dimensioni effettive, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="246e5-126">There are two different computations for row body size: computed size and the actual size:</span></span>  
  
-   <span data-ttu-id="246e5-127">Le dimensioni calcolate, indicate con [computed row body size], vengono utilizzate per determinare se il limite di dimensione di 8.060 byte viene superato.</span><span class="sxs-lookup"><span data-stu-id="246e5-127">The computed size, denoted with [computed row body size], is used to determine if the row size limitation of 8,060 bytes is exceeded.</span></span>  
  
-   <span data-ttu-id="246e5-128">Le dimensioni effettive, indicate con [actual row body size], rappresentano le dimensioni di archiviazione effettive del corpo delle righe in memoria e nei file del checkpoint.</span><span class="sxs-lookup"><span data-stu-id="246e5-128">The actual size, denoted with [actual row body size], is the actual storage size of the row body in memory and in the checkpoint files.</span></span>  
  
 <span data-ttu-id="246e5-129">Entrambi i valori di [computed row body size] e [actual row body size] vengono calcolati in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="246e5-129">Both [computed row body size] and [actual row body size] are calculated similarly.</span></span> <span data-ttu-id="246e5-130">L'unica differenza è il calcolo delle dimensioni delle colonne (n)varchar(i) e varbinary(i), come evidenziato nella parte inferiore della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="246e5-130">The only difference is the calculation of the size of (n)varchar(i) and varbinary(i) columns, as reflected at the bottom of the following table.</span></span> <span data-ttu-id="246e5-131">Per le dimensioni calcolate del corpo delle righe viene usata la dimensione dichiarata *i* come dimensione della colonna, mentre per le dimensioni effettive del corpo delle righe viene usata la dimensione effettiva dei dati.</span><span class="sxs-lookup"><span data-stu-id="246e5-131">The computed row body size uses the declared size *i* as the size of the column, while the actual row body size uses the actual size of the data.</span></span>  
  
 <span data-ttu-id="246e5-132">Nella tabella seguente viene descritto il calcolo delle dimensioni del corpo delle righe, fornito come [actual row body size] = SUM ([size of shallow types) + 2 + 2 \* [number of deep type columns].</span><span class="sxs-lookup"><span data-stu-id="246e5-132">The following table describes the calculation of the row body size, given as [actual row body size] = SUM([size of shallow types]) + 2 + 2 \* [number of deep type columns].</span></span>  
  
|<span data-ttu-id="246e5-133">Sezione</span><span class="sxs-lookup"><span data-stu-id="246e5-133">Section</span></span>|<span data-ttu-id="246e5-134">Dimensione</span><span class="sxs-lookup"><span data-stu-id="246e5-134">Size</span></span>|<span data-ttu-id="246e5-135">Commenti</span><span class="sxs-lookup"><span data-stu-id="246e5-135">Comments</span></span>|  
|-------------|----------|--------------|  
|<span data-ttu-id="246e5-136">Colonne di tipo superficiale</span><span class="sxs-lookup"><span data-stu-id="246e5-136">Shallow type columns</span></span>|<span data-ttu-id="246e5-137">SUM([size of shallow types])</span><span class="sxs-lookup"><span data-stu-id="246e5-137">SUM([size of shallow types])</span></span><br /><br /> <span data-ttu-id="246e5-138">**Le dimensioni dei singoli tipi sono le seguenti:**</span><span class="sxs-lookup"><span data-stu-id="246e5-138">**Size of the individual types is as follows:**</span></span><br /><br /> <span data-ttu-id="246e5-139">Bit &#124; 1</span><span class="sxs-lookup"><span data-stu-id="246e5-139">Bit &#124; 1</span></span><br /><br /> <span data-ttu-id="246e5-140">Tinyint &#124; 1</span><span class="sxs-lookup"><span data-stu-id="246e5-140">Tinyint &#124; 1</span></span><br /><br /> <span data-ttu-id="246e5-141">Smallint &#124; 2</span><span class="sxs-lookup"><span data-stu-id="246e5-141">Smallint &#124; 2</span></span><br /><br /> <span data-ttu-id="246e5-142">Int &#124; 4</span><span class="sxs-lookup"><span data-stu-id="246e5-142">Int &#124; 4</span></span><br /><br /> <span data-ttu-id="246e5-143">Real &#124; 4</span><span class="sxs-lookup"><span data-stu-id="246e5-143">Real &#124; 4</span></span><br /><br /> <span data-ttu-id="246e5-144">Smalldatetime &#124; 4</span><span class="sxs-lookup"><span data-stu-id="246e5-144">Smalldatetime &#124; 4</span></span><br /><br /> <span data-ttu-id="246e5-145">Smallmoney &#124; 4</span><span class="sxs-lookup"><span data-stu-id="246e5-145">Smallmoney &#124; 4</span></span><br /><br /> <span data-ttu-id="246e5-146">Bigint &#124; 8</span><span class="sxs-lookup"><span data-stu-id="246e5-146">Bigint &#124; 8</span></span><br /><br /> <span data-ttu-id="246e5-147">Datetime &#124; 8</span><span class="sxs-lookup"><span data-stu-id="246e5-147">Datetime &#124; 8</span></span><br /><br /> <span data-ttu-id="246e5-148">Datetime2 &#124; 8</span><span class="sxs-lookup"><span data-stu-id="246e5-148">Datetime2 &#124; 8</span></span><br /><br /> <span data-ttu-id="246e5-149">Float 8</span><span class="sxs-lookup"><span data-stu-id="246e5-149">Float 8</span></span><br /><br /> <span data-ttu-id="246e5-150">Money 8</span><span class="sxs-lookup"><span data-stu-id="246e5-150">Money 8</span></span><br /><br /> <span data-ttu-id="246e5-151">Numeric (precisione <= 18) &#124; 8</span><span class="sxs-lookup"><span data-stu-id="246e5-151">Numeric (precision <=18) &#124; 8</span></span><br /><br /> <span data-ttu-id="246e5-152">Time &#124; 8</span><span class="sxs-lookup"><span data-stu-id="246e5-152">Time &#124; 8</span></span><br /><br /> <span data-ttu-id="246e5-153">Numeric (precisione>18) &#124; 16</span><span class="sxs-lookup"><span data-stu-id="246e5-153">Numeric(precision>18) &#124; 16</span></span><br /><br /> <span data-ttu-id="246e5-154">Uniqueidentifier &#124; 16</span><span class="sxs-lookup"><span data-stu-id="246e5-154">Uniqueidentifier &#124; 16</span></span>||  
|<span data-ttu-id="246e5-155">Riempimento delle colonne superficiali</span><span class="sxs-lookup"><span data-stu-id="246e5-155">Shallow column padding</span></span>|<span data-ttu-id="246e5-156">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="246e5-156">Possible values are:</span></span><br /><br /> <span data-ttu-id="246e5-157">1 se esistono colonne di tipo approfondito e le dimensioni totali dei dati delle colonne superficiali sono un numero dispari.</span><span class="sxs-lookup"><span data-stu-id="246e5-157">1 if there are deep type columns and the total data size of the shallow columns is as odd number.</span></span><br /><br /> <span data-ttu-id="246e5-158">In caso contrario, 0</span><span class="sxs-lookup"><span data-stu-id="246e5-158">0 otherwise</span></span>|<span data-ttu-id="246e5-159">I tipi approfonditi sono i tipi (var)binary e (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="246e5-159">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="246e5-160">Matrice di offset delle colonne di tipo approfondito</span><span class="sxs-lookup"><span data-stu-id="246e5-160">Offset array for deep type columns</span></span>|<span data-ttu-id="246e5-161">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="246e5-161">Possible values are:</span></span><br /><br /> <span data-ttu-id="246e5-162">0 se non sono disponibili colonne di tipo approfondito</span><span class="sxs-lookup"><span data-stu-id="246e5-162">0 if there are no deep type columns</span></span><br /><br /> <span data-ttu-id="246e5-163">2 + 2 \* [number of deep type columns] in caso contrario</span><span class="sxs-lookup"><span data-stu-id="246e5-163">2 + 2 \* [number of deep type columns] otherwise</span></span>|<span data-ttu-id="246e5-164">I tipi approfonditi sono i tipi (var)binary e (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="246e5-164">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="246e5-165">Matrice NULL</span><span class="sxs-lookup"><span data-stu-id="246e5-165">NULL array</span></span>|<span data-ttu-id="246e5-166">[number of nullable columns] / 8, arrotondato per eccesso ai byte completi.</span><span class="sxs-lookup"><span data-stu-id="246e5-166">[number of nullable columns] / 8, rounded up to full bytes.</span></span>|<span data-ttu-id="246e5-167">La matrice dispone di un bit per ogni colonna che ammette i valori Null.</span><span class="sxs-lookup"><span data-stu-id="246e5-167">The array has one bit per nullable column.</span></span> <span data-ttu-id="246e5-168">Il valore viene arrotondato per eccesso ai byte completi.</span><span class="sxs-lookup"><span data-stu-id="246e5-168">This is rounded up to full bytes.</span></span>|  
|<span data-ttu-id="246e5-169">Riempimento della matrice NULL</span><span class="sxs-lookup"><span data-stu-id="246e5-169">NULL array padding</span></span>|<span data-ttu-id="246e5-170">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="246e5-170">Possible values are:</span></span><br /><br /> <span data-ttu-id="246e5-171">1 se esistono colonne di tipo approfondito e le dimensioni della matrice NULL sono un numero dispari di byte.</span><span class="sxs-lookup"><span data-stu-id="246e5-171">1 if there are deep type columns and the size of the NULL array is an odd number of bytes.</span></span><br /><br /> <span data-ttu-id="246e5-172">In caso contrario, 0</span><span class="sxs-lookup"><span data-stu-id="246e5-172">0 otherwise</span></span>|<span data-ttu-id="246e5-173">I tipi approfonditi sono i tipi (var)binary e (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="246e5-173">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="246e5-174">Riempimento</span><span class="sxs-lookup"><span data-stu-id="246e5-174">Padding</span></span>|<span data-ttu-id="246e5-175">Se non sono disponibili colonne di tipo approfondito: 0</span><span class="sxs-lookup"><span data-stu-id="246e5-175">If there are no deep type columns: 0</span></span><br /><br /> <span data-ttu-id="246e5-176">Se sono disponibili colonne di tipo approfondito, vengono aggiunti 0-7 byte di riempimento, in base al maggiore allineamento richiesto da una colonna superficiale.</span><span class="sxs-lookup"><span data-stu-id="246e5-176">If there are deep type columns, 0-7 bytes of padding is added, based on the largest alignment required by a shallow column.</span></span> <span data-ttu-id="246e5-177">Ogni colonna superficiale richiede un allineamento uguale alle sue dimensioni, come descritto in precedenza, ad eccezione delle colonne GUID che richiedono l'allineamento di 1 byte (non 16) e delle colonne numeriche che richiedono sempre l'allineamento di 8 byte (mai 16).</span><span class="sxs-lookup"><span data-stu-id="246e5-177">Each shallow column requires alignment equal to its size as documented above, except that GUID columns need alignment of 1 byte (not 16) and numeric columns always need alignment of 8 bytes (never 16).</span></span> <span data-ttu-id="246e5-178">Viene utilizzato il requisito di maggiore allineamento tra tutte le colonne superficiali e vengono aggiunti 0-7 byte di riempimento in modo tale che le dimensioni totali fino a questo punto (senza le colonne di tipo approfondito) siano un multiplo dell'allineamento richiesto.</span><span class="sxs-lookup"><span data-stu-id="246e5-178">The largest alignment requirement among all shallow columns is used, and 0-7 bytes of padding is added in such a way that the total size so far (without the deep type columns) is a multiple of the required alignment.</span></span>|<span data-ttu-id="246e5-179">I tipi approfonditi sono i tipi (var)binary e (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="246e5-179">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="246e5-180">Colonne di tipo approfondito a lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="246e5-180">Fixed-length deep type columns</span></span>|<span data-ttu-id="246e5-181">SUM([size of fixed length deep type columns])</span><span class="sxs-lookup"><span data-stu-id="246e5-181">SUM([size of fixed length deep type columns])</span></span><br /><br /> <span data-ttu-id="246e5-182">Le dimensioni di ogni colonna sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="246e5-182">The size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="246e5-183">i per char(i) e binary(i).</span><span class="sxs-lookup"><span data-stu-id="246e5-183">i for char(i) and binary(i).</span></span><br /><br /> <span data-ttu-id="246e5-184">2 \* i per nchar(i)</span><span class="sxs-lookup"><span data-stu-id="246e5-184">2 \* i for nchar(i)</span></span>|<span data-ttu-id="246e5-185">Le colonne di tipo approfondito a lunghezza fissa sono le colonne di tipo char(i), nchar(i) o binary(i).</span><span class="sxs-lookup"><span data-stu-id="246e5-185">Fixed-length deep type columns are columns of type char(i), nchar(i), or binary(i).</span></span>|  
|<span data-ttu-id="246e5-186">Colonne di tipo approfondito a lunghezza variabile [computed size]</span><span class="sxs-lookup"><span data-stu-id="246e5-186">Variable length deep type columns [computed size]</span></span>|<span data-ttu-id="246e5-187">SUM([computed size of variable length deep type columns])</span><span class="sxs-lookup"><span data-stu-id="246e5-187">SUM([computed size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="246e5-188">Le dimensioni calcolate di ogni colonna sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="246e5-188">The computed size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="246e5-189">i per varchar(i) e varbinary(i)</span><span class="sxs-lookup"><span data-stu-id="246e5-189">i for varchar(i) and varbinary(i)</span></span><br /><br /> <span data-ttu-id="246e5-190">2 \* i per nvarchar(i)</span><span class="sxs-lookup"><span data-stu-id="246e5-190">2 \* i for nvarchar(i)</span></span>|<span data-ttu-id="246e5-191">Questa riga si riferiva solo a [computed row body size].</span><span class="sxs-lookup"><span data-stu-id="246e5-191">This row only applied to [computed row body size].</span></span><br /><br /> <span data-ttu-id="246e5-192">Le colonne di tipo approfondito a lunghezza variabile sono le colonne di tipo varchar(i), nvarchar(i) o varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="246e5-192">Variable-length deep type columns are columns of type varchar(i), nvarchar(i), or varbinary(i).</span></span> <span data-ttu-id="246e5-193">Le dimensioni calcolate sono determinate dalla lunghezza massima (i) della colonna.</span><span class="sxs-lookup"><span data-stu-id="246e5-193">The computed size is determined by the max length (i) of the column.</span></span>|  
|<span data-ttu-id="246e5-194">Colonne di tipo approfondito a lunghezza variabile [actual size]</span><span class="sxs-lookup"><span data-stu-id="246e5-194">Variable length deep type columns [actual size]</span></span>|<span data-ttu-id="246e5-195">SUM([actual size of variable length deep type columns])</span><span class="sxs-lookup"><span data-stu-id="246e5-195">SUM([actual size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="246e5-196">Le dimensioni effettive di ogni colonna sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="246e5-196">The actual size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="246e5-197">n, dove n è il numero di caratteri archiviato nella colonna, per varchar(i).</span><span class="sxs-lookup"><span data-stu-id="246e5-197">n, where n is the number of characters stored in the column, for varchar(i).</span></span><br /><br /> <span data-ttu-id="246e5-198">2 \* n, dove n è il numero di caratteri archiviato nella colonna, per nvarchar(i).</span><span class="sxs-lookup"><span data-stu-id="246e5-198">2 \* n, where n is the number of characters stored in the column, for nvarchar(i).</span></span><br /><br /> <span data-ttu-id="246e5-199">n, dove n è il numero di byte archiviato nella colonna, per varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="246e5-199">n, where n is the number of bytes stored in the column, for varbinary(i).</span></span>|<span data-ttu-id="246e5-200">Questa riga si riferiva solo a [actual row body size].</span><span class="sxs-lookup"><span data-stu-id="246e5-200">This row only applied to [actual row body size].</span></span><br /><br /> <span data-ttu-id="246e5-201">Le dimensioni effettive sono determinate dai dati archiviati nelle colonne della riga.</span><span class="sxs-lookup"><span data-stu-id="246e5-201">The actual size is determined by the data stored in the columns in the row.</span></span>|  
  
##  <a name="row-structure"></a><a name="bkmk_RowStructure"></a><span data-ttu-id="246e5-202">Struttura di righe</span><span class="sxs-lookup"><span data-stu-id="246e5-202">Row Structure</span></span>  
 <span data-ttu-id="246e5-203">Le righe di una tabella ottimizzata per la memoria includono i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="246e5-203">The rows in a memory-optimized table have the following components:</span></span>  
  
-   <span data-ttu-id="246e5-204">L'intestazione di riga contiene il timestamp necessario per implementare il controllo delle versioni delle righe.</span><span class="sxs-lookup"><span data-stu-id="246e5-204">The row header contains the timestamp necessary to implement row versioning.</span></span> <span data-ttu-id="246e5-205">L'intestazione di riga contiene inoltre il puntatore dell'indice per implementare il concatenamento di righe nei bucket di hash (descritti in precedenza).</span><span class="sxs-lookup"><span data-stu-id="246e5-205">The row header also contains the index pointer to implement the row chaining in the hash buckets (described above).</span></span>  
  
-   <span data-ttu-id="246e5-206">Il corpo della riga contiene i dati effettivi della colonna, che includono le informazioni ausiliarie come la matrice Null per le colonne che ammettono i valori Null e la matrice di offset per i tipi di dati a lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="246e5-206">The row body contains the actual column data, which includes some auxiliary information like the null array for nullable columns and the offset array for variable-length data types.</span></span>  
  
 <span data-ttu-id="246e5-207">Nella figura seguente viene illustrata la struttura di righe per una tabella con due indici:</span><span class="sxs-lookup"><span data-stu-id="246e5-207">The following figure illustrates the row structure for a table that has two indexes:</span></span>  
  
 <span data-ttu-id="246e5-208">![Struttura di righe per una tabella con due indici.](../../database-engine/media/hekaton-tables-4.gif "Struttura di righe per una tabella con due indici.")</span><span class="sxs-lookup"><span data-stu-id="246e5-208">![Row structure for a table that has two indexes.](../../database-engine/media/hekaton-tables-4.gif "Row structure for a table that has two indexes.")</span></span>  
  
 <span data-ttu-id="246e5-209">I timestamp di inizio e fine indicano il periodo in cui è valida una versione di riga specifica.</span><span class="sxs-lookup"><span data-stu-id="246e5-209">The begin and end timestamps indicate the period in which a particular row version is valid.</span></span> <span data-ttu-id="246e5-210">Le transazioni che iniziano in questo intervallo possono rilevare questa versione di riga.</span><span class="sxs-lookup"><span data-stu-id="246e5-210">Transactions that start in this interval can see this row version.</span></span> <span data-ttu-id="246e5-211">Per altri dettagli, vedere [Transactions in Memory-Optimized Tables](memory-optimized-tables.md) (Transazioni in tabelle con ottimizzazione per la memoria).</span><span class="sxs-lookup"><span data-stu-id="246e5-211">For more details see [Transactions in Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="246e5-212">I puntatori dell'indice puntano alla riga successiva della catena che appartiene al bucket di hash.</span><span class="sxs-lookup"><span data-stu-id="246e5-212">The index pointers point to the next row in the chain belonging to the hash bucket.</span></span> <span data-ttu-id="246e5-213">Nella figura seguente viene illustrata la struttura di una tabella con due colonne (nome, città) e con due indici, uno per il nome della colonna e uno per la città.</span><span class="sxs-lookup"><span data-stu-id="246e5-213">The following figure illustrates the structure of a table with two columns (name, city), and with two indexes, one on the column name, and one on the column city.</span></span>  
  
 <span data-ttu-id="246e5-214">![Struttura di una tabella con due colonne e indici.](../../database-engine/media/hekaton-tables-5.gif "Struttura di una tabella con due colonne e indici.")</span><span class="sxs-lookup"><span data-stu-id="246e5-214">![Structure of a table with two columns and indexes.](../../database-engine/media/hekaton-tables-5.gif "Structure of a table with two columns and indexes.")</span></span>  
  
 <span data-ttu-id="246e5-215">Nella figura, per i nomi John e Jane viene eseguito l'hashing al primo bucket.</span><span class="sxs-lookup"><span data-stu-id="246e5-215">In this figure, the names John and Jane are hashed to the first bucket.</span></span> <span data-ttu-id="246e5-216">Per Susan viene eseguito l'hashing al secondo bucket.</span><span class="sxs-lookup"><span data-stu-id="246e5-216">Susan is hashed to the second bucket.</span></span> <span data-ttu-id="246e5-217">Per le città Pechino e Bogotà viene eseguito l'hashing al primo bucket.</span><span class="sxs-lookup"><span data-stu-id="246e5-217">The cities Beijing and Bogota are hashed to the first bucket.</span></span> <span data-ttu-id="246e5-218">Per Parigi e Praga viene eseguito l'hashing al secondo bucket.</span><span class="sxs-lookup"><span data-stu-id="246e5-218">Paris and Prague are hashed to the second bucket.</span></span>  
  
 <span data-ttu-id="246e5-219">Le catene per l'indice hash sul nome sono pertanto le seguenti:</span><span class="sxs-lookup"><span data-stu-id="246e5-219">Thus, the chains for the hash index on name are as follows:</span></span>  
  
-   <span data-ttu-id="246e5-220">Primo bucket: (John, Pechino); (John, Parigi); (Jane, Praga)</span><span class="sxs-lookup"><span data-stu-id="246e5-220">First bucket: (John, Beijing); (John, Paris); (Jane, Prague)</span></span>  
  
-   <span data-ttu-id="246e5-221">Secondo bucket: (Susan, Bogotà)</span><span class="sxs-lookup"><span data-stu-id="246e5-221">Second bucket: (Susan, Bogota)</span></span>  
  
 <span data-ttu-id="246e5-222">Le catene per l'indice sulla città sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="246e5-222">The chains for the index on city are as follows:</span></span>  
  
-   <span data-ttu-id="246e5-223">Primo bucket: (John, Pechino), (Susan, Bogotà)</span><span class="sxs-lookup"><span data-stu-id="246e5-223">First bucket: (John, Beijing), (Susan, Bogota)</span></span>  
  
-   <span data-ttu-id="246e5-224">Secondo bucket: (John, Parigi), (Jane, Praga)</span><span class="sxs-lookup"><span data-stu-id="246e5-224">Second bucket: (John, Paris), (Jane, Prague)</span></span>  
  
 <span data-ttu-id="246e5-225">Un timestamp di fine &#x221e; (Infinity) indica che si tratta della versione attualmente valida della riga.</span><span class="sxs-lookup"><span data-stu-id="246e5-225">An end timestamp &#x221e; (infinity) indicates that this is the currently valid version of the row.</span></span> <span data-ttu-id="246e5-226">La riga non è stata aggiornata o eliminata dopo la scrittura di questa versione di riga.</span><span class="sxs-lookup"><span data-stu-id="246e5-226">The row has not been updated or deleted since this row version was written.</span></span>  
  
 <span data-ttu-id="246e5-227">Per un'ora maggiore di 200, la tabella contiene le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="246e5-227">For a time greater than 200, the table contains the following rows:</span></span>  
  
|<span data-ttu-id="246e5-228">Nome</span><span class="sxs-lookup"><span data-stu-id="246e5-228">Name</span></span>|<span data-ttu-id="246e5-229">city</span><span class="sxs-lookup"><span data-stu-id="246e5-229">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="246e5-230">John</span><span class="sxs-lookup"><span data-stu-id="246e5-230">John</span></span>|<span data-ttu-id="246e5-231">Pechino</span><span class="sxs-lookup"><span data-stu-id="246e5-231">Beijing</span></span>|  
|<span data-ttu-id="246e5-232">Jane</span><span class="sxs-lookup"><span data-stu-id="246e5-232">Jane</span></span>|<span data-ttu-id="246e5-233">Praga</span><span class="sxs-lookup"><span data-stu-id="246e5-233">Prague</span></span>|  
  
 <span data-ttu-id="246e5-234">Tuttavia, le eventuali transazioni attive con un'ora di inizio 100 rileveranno la seguente versione della tabella:</span><span class="sxs-lookup"><span data-stu-id="246e5-234">However, any active transaction with begin time 100 will see the following version of the table:</span></span>  
  
|<span data-ttu-id="246e5-235">Nome</span><span class="sxs-lookup"><span data-stu-id="246e5-235">Name</span></span>|<span data-ttu-id="246e5-236">city</span><span class="sxs-lookup"><span data-stu-id="246e5-236">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="246e5-237">John</span><span class="sxs-lookup"><span data-stu-id="246e5-237">John</span></span>|<span data-ttu-id="246e5-238">Parigi</span><span class="sxs-lookup"><span data-stu-id="246e5-238">Paris</span></span>|  
|<span data-ttu-id="246e5-239">Jane</span><span class="sxs-lookup"><span data-stu-id="246e5-239">Jane</span></span>|<span data-ttu-id="246e5-240">Praga</span><span class="sxs-lookup"><span data-stu-id="246e5-240">Prague</span></span>|  
|<span data-ttu-id="246e5-241">Susan</span><span class="sxs-lookup"><span data-stu-id="246e5-241">Susan</span></span>|<span data-ttu-id="246e5-242">Bogotà</span><span class="sxs-lookup"><span data-stu-id="246e5-242">Bogata</span></span>|  
  
##  <a name="example-table-and-row-size-computation"></a><a name="bkmk_ExampleComputation"></a> <span data-ttu-id="246e5-243">Esempio: calcolo delle dimensioni della tabella e delle righe</span><span class="sxs-lookup"><span data-stu-id="246e5-243">Example: Table and Row Size Computation</span></span>  
 <span data-ttu-id="246e5-244">Per gli indici hash il numero effettivo di bucket viene arrotondato alla più vicina potenza di 2.</span><span class="sxs-lookup"><span data-stu-id="246e5-244">For hash indexes, the actual bucket count is rounded up to the nearest power of 2.</span></span> <span data-ttu-id="246e5-245">Ad esempio, se il valore di bucket_count specificato è 100.000, il numero effettivo di bucket per l'indice è 131.072.</span><span class="sxs-lookup"><span data-stu-id="246e5-245">For example, if the specified bucket_count is 100000, the actual bucket count for the index is 131072.</span></span>  
  
 <span data-ttu-id="246e5-246">Si consideri una tabella Orders con la definizione seguente:</span><span class="sxs-lookup"><span data-stu-id="246e5-246">Consider an Orders table with the following definition:</span></span>  
  
```sql  
CREATE TABLE dbo.Orders (  
     OrderID int NOT NULL   
           PRIMARY KEY NONCLUSTERED,  
     CustomerID int NOT NULL   
           INDEX IX_CustomerID HASH WITH (BUCKET_COUNT=10000),  
     OrderDate datetime NOT NULL,  
     OrderDescription nvarchar(1000)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
```  
  
 <span data-ttu-id="246e5-247">Si noti che questa tabella include un indice hash e un indice non cluster (chiave primaria).</span><span class="sxs-lookup"><span data-stu-id="246e5-247">Notice that this table has one hash index and a nonclustered index (the primary key).</span></span> <span data-ttu-id="246e5-248">Dispone inoltre di tre colonne a lunghezza fissa e una colonna a lunghezza variabile; una delle colonne ammette i valori Null (OrderDescription).</span><span class="sxs-lookup"><span data-stu-id="246e5-248">It also has three fixed-length columns and one variable-length column, with one of the columns being NULLable (OrderDescription).</span></span> <span data-ttu-id="246e5-249">Si supponga che la tabella Orders contenga 8379 righe e che la lunghezza media dei valori nella colonna OrderDescription sia di 78 caratteri.</span><span class="sxs-lookup"><span data-stu-id="246e5-249">Let's assume the Orders table has 8379 rows, and the average length of the values in the OrderDescription column is 78 characters.</span></span>  
  
 <span data-ttu-id="246e5-250">Per determinare le dimensioni della tabella, è innanzitutto necessario determinare le dimensioni degli indici.</span><span class="sxs-lookup"><span data-stu-id="246e5-250">To determine the table size, first determine the size of the indexes.</span></span> <span data-ttu-id="246e5-251">Il valore di bucket_count per entrambi gli indici è specificato come 10.000.</span><span class="sxs-lookup"><span data-stu-id="246e5-251">The bucket_count for both indexes is specified as 10000.</span></span> <span data-ttu-id="246e5-252">Questo valore viene arrotondato per eccesso alla potenza di 2 più vicina: 16384.</span><span class="sxs-lookup"><span data-stu-id="246e5-252">This is rounded up to the nearest power of 2: 16384.</span></span> <span data-ttu-id="246e5-253">Pertanto, le dimensioni totali degli indici della tabella Orders sono:</span><span class="sxs-lookup"><span data-stu-id="246e5-253">Therefore, the total size of the indexes for the Orders table is:</span></span>  
  
```  
8 * 16384 = 131072 bytes  
```  
  
 <span data-ttu-id="246e5-254">Il valore restante corrisponde alle dimensioni dei dati della tabella, ovvero:</span><span class="sxs-lookup"><span data-stu-id="246e5-254">What remains is the table data size, which is,</span></span>  
  
```  
[row size] * [row count] = [row size] * 8379  
```  
  
 <span data-ttu-id="246e5-255">(La tabella di esempio contiene 8.379 righe). A questo punto:</span><span class="sxs-lookup"><span data-stu-id="246e5-255">(The example table has 8379 rows.) Now, we have:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices] = 24 + 8 * 1 = 32 bytes  
```  
  
 <span data-ttu-id="246e5-256">Si calcoli quindi [actual row body size]:</span><span class="sxs-lookup"><span data-stu-id="246e5-256">Next, let's calculate [actual row body size]:</span></span>  
  
-   <span data-ttu-id="246e5-257">Colonne di tipo superficiale:</span><span class="sxs-lookup"><span data-stu-id="246e5-257">Shallow type columns:</span></span>  
  
    ```  
    SUM([size of shallow types]) = 4 [int] + 4 [int] + 8 [datetime] = 16  
    ```  
  
-   <span data-ttu-id="246e5-258">Il riempimento delle colonne superficiali è 0, in quanto le dimensioni totali delle colonne superficiali sono un numero pari.</span><span class="sxs-lookup"><span data-stu-id="246e5-258">Shallow column padding is 0, as the total shallow column size is even.</span></span>  
  
-   <span data-ttu-id="246e5-259">Matrice di offset delle colonne di tipo approfondito:</span><span class="sxs-lookup"><span data-stu-id="246e5-259">Offset array for deep type columns:</span></span>  
  
    ```  
    2 + 2 * [number of deep type columns] = 2 + 2 * 1 = 4  
    ```  
  
-   <span data-ttu-id="246e5-260">Matrice NULL = 1</span><span class="sxs-lookup"><span data-stu-id="246e5-260">NULL array = 1</span></span>  
  
-   <span data-ttu-id="246e5-261">Riempimento matrice NULL = 1, in quanto le dimensioni della matrice NULL sono un numero dispari ed è presente una colonna di tipo approfondito.</span><span class="sxs-lookup"><span data-stu-id="246e5-261">NULL array padding = 1, as the NULL array size is odd and there is a deep type column.</span></span>  
  
-   <span data-ttu-id="246e5-262">Riempimento</span><span class="sxs-lookup"><span data-stu-id="246e5-262">Padding</span></span>  
  
    -   <span data-ttu-id="246e5-263">8 è il requisito di allineamento maggiore.</span><span class="sxs-lookup"><span data-stu-id="246e5-263">8 is the largest alignment requirement.</span></span>  
  
    -   <span data-ttu-id="246e5-264">Fino a questo punto le dimensioni corrispondono a 16 + 0 + 4 + 1 + 1 = 22.</span><span class="sxs-lookup"><span data-stu-id="246e5-264">Size so far is 16 + 0 + 4 + 1 + 1 = 22.</span></span>  
  
    -   <span data-ttu-id="246e5-265">Il multiplo più vicino di 8 è 24.</span><span class="sxs-lookup"><span data-stu-id="246e5-265">Nearest multiple of 8 is 24.</span></span>  
  
    -   <span data-ttu-id="246e5-266">Il riempimento totale è 24 - 22 = 2 byte.</span><span class="sxs-lookup"><span data-stu-id="246e5-266">Total padding is 24 - 22 = 2 bytes.</span></span>  
  
-   <span data-ttu-id="246e5-267">Non sono presenti colonne di tipo approfondito a lunghezza fissa (colonne di tipo approfondito a lunghezza fissa: 0.).</span><span class="sxs-lookup"><span data-stu-id="246e5-267">There are no fixed-length deep type columns (Fixed-length deep type columns: 0.).</span></span>  
  
-   <span data-ttu-id="246e5-268">Le dimensioni effettive della colonna di tipo approfondito sono 2 \* 78 = 156.</span><span class="sxs-lookup"><span data-stu-id="246e5-268">The actual size of deep type column is 2 \* 78 = 156.</span></span> <span data-ttu-id="246e5-269">La sola colonna di tipo approfondito OrderDescription è di tipo nvarchar.</span><span class="sxs-lookup"><span data-stu-id="246e5-269">The single deep type column OrderDescription has type nvarchar.</span></span>  
  
```  
[actual row body size] = 24 + 156 = 180 bytes  
```  
  
 <span data-ttu-id="246e5-270">Per completare il calcolo:</span><span class="sxs-lookup"><span data-stu-id="246e5-270">To complete the calculation:</span></span>  
  
```  
[row size] = 32 + 180 = 212 bytes  
[table size] = 8 * 16384 + 212 * 8379 = 131072 + 1776348 = 1907420  
```  
  
 <span data-ttu-id="246e5-271">Le dimensioni totali in memoria della tabella sono quindi 2 MB circa.</span><span class="sxs-lookup"><span data-stu-id="246e5-271">Total table size in memory is thus approximately 2 megabytes.</span></span> <span data-ttu-id="246e5-272">Questo calcolo non tiene conto del potenziale overhead sostenuto dall'allocazione di memoria nonché dell'eventuale controllo delle versioni delle righe richiesto per le transazioni che accedono a questa tabella.</span><span class="sxs-lookup"><span data-stu-id="246e5-272">This does not account for potential overhead incurred by memory allocation as well as any row versioning required for the transactions accessing this table.</span></span>  
  
 <span data-ttu-id="246e5-273">L'effettiva memoria allocata e utilizzata dalla tabella e dai relativi indici può essere ottenuta tramite la query seguente:</span><span class="sxs-lookup"><span data-stu-id="246e5-273">The actual memory allocated for and used by this table and its indexes can be obtained through the following query:</span></span>  
  
```sql  
select * from sys.dm_db_xtp_table_memory_stats  
where object_id = object_id('dbo.Orders')  
```  
  
## <a name="see-also"></a><span data-ttu-id="246e5-274">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="246e5-274">See Also</span></span>  
 [<span data-ttu-id="246e5-275">Tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="246e5-275">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
