---
title: Usare set di colonne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- sparse columns, column sets
- column sets
ms.assetid: a4f9de95-dc8f-4ad8-b957-137e32bfa500
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cb496137c3986b78a55862e434c153d354a42ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637719"
---
# <a name="use-column-sets"></a><span data-ttu-id="cdee1-102">Utilizzare set di colonne</span><span class="sxs-lookup"><span data-stu-id="cdee1-102">Use Column Sets</span></span>
  <span data-ttu-id="cdee1-103">Nelle tabelle che utilizzano colonne di tipo sparse è possibile definire un set di colonne per restituire tutte le colonne di tipo sparse della tabella.</span><span class="sxs-lookup"><span data-stu-id="cdee1-103">Tables that use sparse columns can designate a column set to return all sparse columns in the table.</span></span> <span data-ttu-id="cdee1-104">Un set di colonne è una rappresentazione XML non tipizzata che combina tutte le colonne di tipo sparse di una tabella in un output strutturato.</span><span class="sxs-lookup"><span data-stu-id="cdee1-104">A column set is an untyped XML representation that combines all the sparse columns of a table into a structured output.</span></span> <span data-ttu-id="cdee1-105">Un set di colonne è analogo a una colonna calcolata poiché non è archiviato fisicamente nella tabella,</span><span class="sxs-lookup"><span data-stu-id="cdee1-105">A column set is like a calculated column in that the column set is not physically stored in the table.</span></span> <span data-ttu-id="cdee1-106">ma differisce da una colonna calcolata poiché è direttamente aggiornabile.</span><span class="sxs-lookup"><span data-stu-id="cdee1-106">A column set differs from a calculated column in that the column set is directly updatable.</span></span>  
  
 <span data-ttu-id="cdee1-107">È necessario utilizzare i set di colonne quando il numero di colonne di una tabella è elevato e l'esecuzione di operazioni sulle singole colonne risulta eccessivamente complessa.</span><span class="sxs-lookup"><span data-stu-id="cdee1-107">You should consider using column sets when the number of columns in a table is large, and operating on them individually is cumbersome.</span></span> <span data-ttu-id="cdee1-108">Potrebbe essere possibile ottenere un miglioramento delle prestazioni relative alle applicazioni in caso di selezione e inserimento dei dati utilizzando set di colonne in tabelle in cui il numero di colonne è elevato.</span><span class="sxs-lookup"><span data-stu-id="cdee1-108">Applications might see some performance improvement when they select and insert data by using column sets on tables that have lots of columns.</span></span> <span data-ttu-id="cdee1-109">Le prestazioni relative ai set di colonne, tuttavia, possono risultare ridotte quando nelle colonne della tabella sono definiti molti indici,</span><span class="sxs-lookup"><span data-stu-id="cdee1-109">However, the performance of column sets can be reduced when many indexes are defined on the columns in the table.</span></span> <span data-ttu-id="cdee1-110">poiché la quantità di memoria necessaria per un piano di esecuzione aumenta.</span><span class="sxs-lookup"><span data-stu-id="cdee1-110">This is because the amount of memory that is required for an execution plan increases.</span></span>  
  
 <span data-ttu-id="cdee1-111">Per definire un set di colonne, usare le parole chiave *<nome_set_colonne>* FOR ALL_SPARSE_COLUMNS nelle istruzioni [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) o [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cdee1-111">To define a column set, use the *<column_set_name>* FOR ALL_SPARSE_COLUMNS keywords in the[CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) or [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) statements.</span></span>  
  
## <a name="guidelines-for-using-column-sets"></a><span data-ttu-id="cdee1-112">Linee guida per l'utilizzo di set di colonne</span><span class="sxs-lookup"><span data-stu-id="cdee1-112">Guidelines for Using Column Sets</span></span>  
 <span data-ttu-id="cdee1-113">Quando si utilizzano set di colonne, tenere presente le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdee1-113">When you use column sets, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="cdee1-114">Le colonne di tipo sparse e un set di colonne possono essere aggiunti come parte della stessa istruzione.</span><span class="sxs-lookup"><span data-stu-id="cdee1-114">Sparse columns and a column set can be added as part of the same statement.</span></span>  
  
-   <span data-ttu-id="cdee1-115">Il set di colonne non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="cdee1-115">The column set cannot be changed.</span></span> <span data-ttu-id="cdee1-116">Per modificare un set di colonne, è necessario eliminarlo e crearlo nuovamente.</span><span class="sxs-lookup"><span data-stu-id="cdee1-116">To change a column set, you must delete and re-create the column set.</span></span>  
  
-   <span data-ttu-id="cdee1-117">Un set di colonne non può essere aggiunto a una tabella in cui sono già contenute colonne di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="cdee1-117">A column set cannot be added to a table if that table already contains sparse columns.</span></span>  
  
-   <span data-ttu-id="cdee1-118">Un set di colonne può essere aggiunto a una tabella in cui non è contenuta alcuna colonna di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="cdee1-118">A column set can be added to a table that does not include any sparse columns.</span></span> <span data-ttu-id="cdee1-119">Se le colonne di tipo sparse vengono aggiunte alla tabella in un secondo momento, verranno visualizzate nel set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-119">If sparse columns are later added to the table, they will appear in the column set.</span></span>  
  
-   <span data-ttu-id="cdee1-120">Per ogni tabella è consentito un unico set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-120">Only one column set is allowed per table.</span></span>  
  
-   <span data-ttu-id="cdee1-121">Un set di colonne è facoltativo e non è necessario per utilizzare colonne di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="cdee1-121">A column set is optional and is not required to use sparse columns.</span></span>  
  
-   <span data-ttu-id="cdee1-122">Non è possibile definire vincoli o valori predefiniti in un set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-122">Constraints or default values cannot be defined on a column set.</span></span>  
  
-   <span data-ttu-id="cdee1-123">Nelle colonne calcolate non possono essere contenute colonne di un set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-123">Computed columns cannot contain column set columns.</span></span>  
  
-   <span data-ttu-id="cdee1-124">Le query distribuite non sono supportate in tabelle che contengono set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-124">Distributed queries are not supported on tables that contain column sets.</span></span>  
  
-   <span data-ttu-id="cdee1-125">I set di colonne non sono supportati dalla replica.</span><span class="sxs-lookup"><span data-stu-id="cdee1-125">Replication does not support column sets.</span></span>  
  
-   <span data-ttu-id="cdee1-126">I set di colonne non sono supportati da Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="cdee1-126">Change data capture does not support column sets.</span></span>  
  
-   <span data-ttu-id="cdee1-127">Un set di colonne non può appartenere ad alcun tipo di indice,</span><span class="sxs-lookup"><span data-stu-id="cdee1-127">A column set cannot be part of any kind of index.</span></span> <span data-ttu-id="cdee1-128">ad esempio indici XML, indici full-text e viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="cdee1-128">This includes XML indexes, full-text indexes, and indexed views.</span></span> <span data-ttu-id="cdee1-129">Non è inoltre possibile aggiungere un set di colonne come colonna inclusa in un indice.</span><span class="sxs-lookup"><span data-stu-id="cdee1-129">A column set cannot be added as an included column in any index.</span></span>  
  
-   <span data-ttu-id="cdee1-130">Un set di colonne non può essere utilizzato nell'espressione di filtro di un indice filtrato o di statistiche filtrate.</span><span class="sxs-lookup"><span data-stu-id="cdee1-130">A column set cannot be used in the filter expression of a filtered index or filtered statistics.</span></span>  
  
-   <span data-ttu-id="cdee1-131">Quando in una vista è incluso un set di colonne, quest'ultimo viene visualizzato nella vista come una colonna XML.</span><span class="sxs-lookup"><span data-stu-id="cdee1-131">When a view includes a column set, the column set appears in the view as an XML column.</span></span>  
  
-   <span data-ttu-id="cdee1-132">Un set di colonne non può essere incluso nella definizione di una vista indicizzata.</span><span class="sxs-lookup"><span data-stu-id="cdee1-132">A column set cannot be included in an indexed view definition.</span></span>  
  
-   <span data-ttu-id="cdee1-133">Le viste partizionate che includono tabelle in cui sono contenuti set di colonne sono aggiornabili quando la vista partizionata specifica le colonne di tipo sparse in base al nome.</span><span class="sxs-lookup"><span data-stu-id="cdee1-133">Partitioned views that include tables that contain column sets are updatable when the partitioned view specifies the sparse columns by name.</span></span> <span data-ttu-id="cdee1-134">Una vista partizionata non è aggiornabile quando fa riferimento al set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-134">A partitioned view is not updatable when it references the column set.</span></span>  
  
-   <span data-ttu-id="cdee1-135">Le notifiche delle query che fanno riferimento a set di colonne non sono consentite.</span><span class="sxs-lookup"><span data-stu-id="cdee1-135">Query notifications that refer to column sets are not permitted.</span></span>  
  
-   <span data-ttu-id="cdee1-136">Le dimensioni dei dati XML non possono superare i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="cdee1-136">XML data has a size limit of 2 GB.</span></span> <span data-ttu-id="cdee1-137">Se i dati combinati di tutte le colonne di tipo sparse diverse da Null in una riga superano questo limite, la query o l'operazione DML genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="cdee1-137">If the combined data of all the nonnull sparse columns in a row exceeds this limit, the query or DML operation will produce an error.</span></span>  
  
-   <span data-ttu-id="cdee1-138">Per informazioni sui dati restituiti dalla funzione COLUMNS_UPDATED, vedere [Usare le colonne di tipo sparse](use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="cdee1-138">For information about the data that is returned by the COLUMNS_UPDATED function, see [Use Sparse Columns](use-sparse-columns.md).</span></span>  
  
## <a name="guidelines-for-selecting-data-from-a-column-set"></a><span data-ttu-id="cdee1-139">Linee guida per la selezione di dati da un set di colonne</span><span class="sxs-lookup"><span data-stu-id="cdee1-139">Guidelines for Selecting Data from a Column Set</span></span>  
 <span data-ttu-id="cdee1-140">Per selezionare dati da un set di colonne, tenere presente le linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdee1-140">Consider the following guidelines for selecting data from a column set:</span></span>  
  
-   <span data-ttu-id="cdee1-141">Concettualmente, un set di colonne è un tipo di colonna XML calcolata e aggiornabile, che aggrega un set di colonne relazionali sottostanti in un'unica rappresentazione XML.</span><span class="sxs-lookup"><span data-stu-id="cdee1-141">Conceptually, a column set is a type of updatable, computed XML column that aggregates a set of underlying relational columns into a single XML representation.</span></span> <span data-ttu-id="cdee1-142">Il set di colonne supporta solo la proprietà ALL_SPARSE_COLUMNS,</span><span class="sxs-lookup"><span data-stu-id="cdee1-142">The column set only supports the ALL_SPARSE_COLUMNS property.</span></span> <span data-ttu-id="cdee1-143">utilizzata per aggregare tutti i valori diversi da Null di tutte le colonne di tipo sparse per una riga specifica.</span><span class="sxs-lookup"><span data-stu-id="cdee1-143">This property is used to aggregate all nonnull values from all sparse columns for a particular row.</span></span>  
  
-   <span data-ttu-id="cdee1-144">Nell'editor di tabella di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] i set di colonne vengono visualizzati come un campo XML modificabile.</span><span class="sxs-lookup"><span data-stu-id="cdee1-144">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] table editor, column sets are displayed as an editable XML field.</span></span> <span data-ttu-id="cdee1-145">Definire i set di colonne nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="cdee1-145">Define column sets in the format:</span></span>  
  
    ```  
    <column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...  
    ```  
  
     <span data-ttu-id="cdee1-146">Di seguito vengono riportati alcuni esempi di valori di set di colonne:</span><span class="sxs-lookup"><span data-stu-id="cdee1-146">Examples of column set values are as follows:</span></span>  
  
    -   `<sparseProp1>10</sparseProp1><sparseProp3>20</sparseProp3>`  
  
    -   `<DocTitle>Bicycle Parts List</DocTitle><Region>West</Region>`  
  
-   <span data-ttu-id="cdee1-147">Le colonne di tipo sparse in cui sono contenuti valori Null vengono omesse dalla rappresentazione XML del set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-147">Sparse columns that contain null values are omitted from the XML representation for the column set.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="cdee1-148">L'aggiunta di un set di colonne modifica il comportamento delle query SELECT \*.</span><span class="sxs-lookup"><span data-stu-id="cdee1-148">Adding a column set changes the behavior of SELECT \* queries.</span></span> <span data-ttu-id="cdee1-149">La query restituirà il set di colonne come una colonna XML e non restituirà le singole colonne di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="cdee1-149">The query will return the column set as an XML column and not return the individual sparse columns.</span></span> <span data-ttu-id="cdee1-150">È necessario che i progettisti degli schemi e gli sviluppatori del software prestino particolare attenzione a non causare l'interruzione delle applicazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="cdee1-150">Schema designers and software developers must be careful not to break existing applications.</span></span>  
  
## <a name="inserting-or-modifying-data-in-a-column-set"></a><span data-ttu-id="cdee1-151">Inserimento o modifica di dati in un set di colonne</span><span class="sxs-lookup"><span data-stu-id="cdee1-151">Inserting or Modifying Data in a Column Set</span></span>  
 <span data-ttu-id="cdee1-152">Per manipolare i dati di una colonna di tipo sparse, è possibile utilizzare il nome delle colonne singole o fare riferimento al nome del set di colonne e specificarne i valori utilizzando il formato XML del set di colonne stesso.</span><span class="sxs-lookup"><span data-stu-id="cdee1-152">Data manipulation of a sparse column can be performed by using the name of the individual columns, or by referencing the name of the column set and specifying the values of the column set by using the XML format of the column set.</span></span> <span data-ttu-id="cdee1-153">Nella colonna XML le colonne di tipo sparse possono essere visualizzate in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="cdee1-153">Sparse columns can appear in any order in the XML column.</span></span>  
  
 <span data-ttu-id="cdee1-154">Quando i valori di una colonna di tipo sparse vengono inseriti o aggiornati utilizzando il set di colonne XML, i valori inseriti nelle colonne di tipo sparse sottostanti vengono convertiti implicitamente dal tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="cdee1-154">When sparse column values are inserted or updated by using the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="cdee1-155">Nel caso di colonne numeriche, un valore vuoto nel codice XML per la colonna numerica viene convertito in una stringa vuota,</span><span class="sxs-lookup"><span data-stu-id="cdee1-155">In the case of numeric columns, a blank value in the XML for the numeric column converts to an empty string.</span></span> <span data-ttu-id="cdee1-156">provocando l'inserimento di uno zero nella colonna numerica come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cdee1-156">This causes a zero to be inserted into the numeric column as shown in the following example.</span></span>  
  
```  
CREATE TABLE t (i int SPARSE, cs xml column_set FOR ALL_SPARSE_COLUMNS);  
GO  
INSERT t(cs) VALUES ('<i/>');  
GO  
SELECT i FROM t;  
GO  
```  
  
 <span data-ttu-id="cdee1-157">In questo esempio per la colonna `i`non è stato specificato alcun valore, ma è stato inserito il valore `0` .</span><span class="sxs-lookup"><span data-stu-id="cdee1-157">In this example, no value was specified for the column `i`, but the value `0` was inserted.</span></span>  
  
## <a name="using-the-sql_variant-data-type"></a><span data-ttu-id="cdee1-158">Utilizzo del tipo di dati sql_variant</span><span class="sxs-lookup"><span data-stu-id="cdee1-158">Using the sql_variant Data Type</span></span>  
 <span data-ttu-id="cdee1-159">Il tipo di dati `sql_variant` consente di archiviare più tipi di dati diversi, ad esempio `int`, `char` e `date`.</span><span class="sxs-lookup"><span data-stu-id="cdee1-159">The `sql_variant` date type can store multiple different data types, such as `int`, `char`, and `date`.</span></span> <span data-ttu-id="cdee1-160">I set di colonne restituiscono informazioni sul tipo di dati, ad esempio scala, precisione e informazioni sulle impostazioni locali, associate a un valore `sql_variant` come attributi nella colonna XML generata.</span><span class="sxs-lookup"><span data-stu-id="cdee1-160">Column sets output the data type information such as scale, precision, and locale information that is associated with a `sql_variant` value as attributes in the generated XML column.</span></span> <span data-ttu-id="cdee1-161">Se si tenta di specificare questi attributi un'istruzione XML generata dall'utente come input per un'operazione di inserimento o di aggiornamento su un set di colonne, alcuni di questi attributi risultano obbligatori e ad alcuni di essi viene assegnato un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="cdee1-161">If you try to provide these attributes in a custom-generated XML statement as an input for an insert or update operation on a column set, some of these attributes are required and some of them are assigned a default value.</span></span> <span data-ttu-id="cdee1-162">Nella tabella seguente vengono elencati i tipi di dati e i valori predefiniti generati dal server quando il valore non viene specificato.</span><span class="sxs-lookup"><span data-stu-id="cdee1-162">The following table lists the data types and the default values that the server generates when the value is not provided.</span></span>  
  
|<span data-ttu-id="cdee1-163">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="cdee1-163">Data type</span></span>|<span data-ttu-id="cdee1-164">localeID\*</span><span class="sxs-lookup"><span data-stu-id="cdee1-164">localeID\*</span></span>|<span data-ttu-id="cdee1-165">sqlCompareOptions</span><span class="sxs-lookup"><span data-stu-id="cdee1-165">sqlCompareOptions</span></span>|<span data-ttu-id="cdee1-166">sqlCollationVersion</span><span class="sxs-lookup"><span data-stu-id="cdee1-166">sqlCollationVersion</span></span>|<span data-ttu-id="cdee1-167">SqlSortId</span><span class="sxs-lookup"><span data-stu-id="cdee1-167">SqlSortId</span></span>|<span data-ttu-id="cdee1-168">Lunghezza massima</span><span class="sxs-lookup"><span data-stu-id="cdee1-168">Maximum length</span></span>|<span data-ttu-id="cdee1-169">Precision</span><span class="sxs-lookup"><span data-stu-id="cdee1-169">Precision</span></span>|<span data-ttu-id="cdee1-170">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="cdee1-170">Scale</span></span>|  
|---------------|----------------|-----------------------|-------------------------|---------------|--------------------|---------------|-----------|  
|<span data-ttu-id="cdee1-171">`char`, `varchar`, `binary`</span><span class="sxs-lookup"><span data-stu-id="cdee1-171">`char`, `varchar`, `binary`</span></span>|<span data-ttu-id="cdee1-172">-1</span><span class="sxs-lookup"><span data-stu-id="cdee1-172">-1</span></span>|<span data-ttu-id="cdee1-173">Impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="cdee1-173">'Default'</span></span>|<span data-ttu-id="cdee1-174">0</span><span class="sxs-lookup"><span data-stu-id="cdee1-174">0</span></span>|<span data-ttu-id="cdee1-175">0</span><span class="sxs-lookup"><span data-stu-id="cdee1-175">0</span></span>|<span data-ttu-id="cdee1-176">8000</span><span class="sxs-lookup"><span data-stu-id="cdee1-176">8000</span></span>|<span data-ttu-id="cdee1-177">Non applicabile\*\*</span><span class="sxs-lookup"><span data-stu-id="cdee1-177">Not applicable\*\*</span></span>|<span data-ttu-id="cdee1-178">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-178">Not applicable</span></span>|  
|`nvarchar`|<span data-ttu-id="cdee1-179">-1</span><span class="sxs-lookup"><span data-stu-id="cdee1-179">-1</span></span>|<span data-ttu-id="cdee1-180">Impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="cdee1-180">'Default'</span></span>|<span data-ttu-id="cdee1-181">0</span><span class="sxs-lookup"><span data-stu-id="cdee1-181">0</span></span>|<span data-ttu-id="cdee1-182">0</span><span class="sxs-lookup"><span data-stu-id="cdee1-182">0</span></span>|<span data-ttu-id="cdee1-183">4000</span><span class="sxs-lookup"><span data-stu-id="cdee1-183">4000</span></span>|<span data-ttu-id="cdee1-184">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-184">Not applicable</span></span>|<span data-ttu-id="cdee1-185">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-185">Not applicable</span></span>|  
|<span data-ttu-id="cdee1-186">`decimal`, `float`, `real`</span><span class="sxs-lookup"><span data-stu-id="cdee1-186">`decimal`, `float`, `real`</span></span>|<span data-ttu-id="cdee1-187">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-187">Not applicable</span></span>|<span data-ttu-id="cdee1-188">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-188">Not applicable</span></span>|<span data-ttu-id="cdee1-189">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-189">Not applicable</span></span>|<span data-ttu-id="cdee1-190">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-190">Not applicable</span></span>|<span data-ttu-id="cdee1-191">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-191">Not applicable</span></span>|<span data-ttu-id="cdee1-192">18</span><span class="sxs-lookup"><span data-stu-id="cdee1-192">18</span></span>|<span data-ttu-id="cdee1-193">0</span><span class="sxs-lookup"><span data-stu-id="cdee1-193">0</span></span>|  
|<span data-ttu-id="cdee1-194">`integer`, `bigint`, `tinyint`, `smallint`</span><span class="sxs-lookup"><span data-stu-id="cdee1-194">`integer`, `bigint`, `tinyint`, `smallint`</span></span>|<span data-ttu-id="cdee1-195">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-195">Not applicable</span></span>|<span data-ttu-id="cdee1-196">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-196">Not applicable</span></span>|<span data-ttu-id="cdee1-197">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-197">Not applicable</span></span>|<span data-ttu-id="cdee1-198">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-198">Not applicable</span></span>|<span data-ttu-id="cdee1-199">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-199">Not applicable</span></span>|<span data-ttu-id="cdee1-200">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-200">Not applicable</span></span>|<span data-ttu-id="cdee1-201">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-201">Not applicable</span></span>|  
|`datetime2`|<span data-ttu-id="cdee1-202">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-202">Not applicable</span></span>|<span data-ttu-id="cdee1-203">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-203">Not applicable</span></span>|<span data-ttu-id="cdee1-204">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-204">Not applicable</span></span>|<span data-ttu-id="cdee1-205">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-205">Not applicable</span></span>|<span data-ttu-id="cdee1-206">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-206">Not applicable</span></span>|<span data-ttu-id="cdee1-207">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-207">Not applicable</span></span>|<span data-ttu-id="cdee1-208">7</span><span class="sxs-lookup"><span data-stu-id="cdee1-208">7</span></span>|  
|`datetime offset`|<span data-ttu-id="cdee1-209">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-209">Not applicable</span></span>|<span data-ttu-id="cdee1-210">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-210">Not applicable</span></span>|<span data-ttu-id="cdee1-211">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-211">Not applicable</span></span>|<span data-ttu-id="cdee1-212">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-212">Not applicable</span></span>|<span data-ttu-id="cdee1-213">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-213">Not applicable</span></span>|<span data-ttu-id="cdee1-214">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-214">Not applicable</span></span>|<span data-ttu-id="cdee1-215">7</span><span class="sxs-lookup"><span data-stu-id="cdee1-215">7</span></span>|  
|<span data-ttu-id="cdee1-216">`datetime`, `date`, `smalldatetime`</span><span class="sxs-lookup"><span data-stu-id="cdee1-216">`datetime`, `date`, `smalldatetime`</span></span>|<span data-ttu-id="cdee1-217">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-217">Not applicable</span></span>|<span data-ttu-id="cdee1-218">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-218">Not applicable</span></span>|<span data-ttu-id="cdee1-219">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-219">Not applicable</span></span>|<span data-ttu-id="cdee1-220">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-220">Not applicable</span></span>|<span data-ttu-id="cdee1-221">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-221">Not applicable</span></span>|<span data-ttu-id="cdee1-222">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-222">Not applicable</span></span>|<span data-ttu-id="cdee1-223">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-223">Not applicable</span></span>|  
|<span data-ttu-id="cdee1-224">`money`, `smallmoney`</span><span class="sxs-lookup"><span data-stu-id="cdee1-224">`money`, `smallmoney`</span></span>|<span data-ttu-id="cdee1-225">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-225">Not applicable</span></span>|<span data-ttu-id="cdee1-226">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-226">Not applicable</span></span>|<span data-ttu-id="cdee1-227">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-227">Not applicable</span></span>|<span data-ttu-id="cdee1-228">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-228">Not applicable</span></span>|<span data-ttu-id="cdee1-229">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-229">Not applicable</span></span>|<span data-ttu-id="cdee1-230">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-230">Not applicable</span></span>|<span data-ttu-id="cdee1-231">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-231">Not applicable</span></span>|  
|`time`|<span data-ttu-id="cdee1-232">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-232">Not applicable</span></span>|<span data-ttu-id="cdee1-233">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-233">Not applicable</span></span>|<span data-ttu-id="cdee1-234">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-234">Not applicable</span></span>|<span data-ttu-id="cdee1-235">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-235">Not applicable</span></span>|<span data-ttu-id="cdee1-236">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-236">Not applicable</span></span>|<span data-ttu-id="cdee1-237">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="cdee1-237">Not applicable</span></span>|<span data-ttu-id="cdee1-238">7</span><span class="sxs-lookup"><span data-stu-id="cdee1-238">7</span></span>|  
  
 <span data-ttu-id="cdee1-239">\*  localeID -1 indica le impostazioni locali predefinite.</span><span class="sxs-lookup"><span data-stu-id="cdee1-239">\*  localeID -1 means the default locale.</span></span> <span data-ttu-id="cdee1-240">Le impostazioni locali per l'inglese sono rappresentate dal valore 1033.</span><span class="sxs-lookup"><span data-stu-id="cdee1-240">The English locale is 1033.</span></span>  
  
 <span data-ttu-id="cdee1-241">\*\* Non applicabile = Non viene restituito alcun valore per questi attributi durante un'operazione di selezione sul set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-241">\*\*  Not applicable = No values are output for these attributes during a select operation on the column set.</span></span> <span data-ttu-id="cdee1-242">Quando per questo attributo viene specificato un valore dal chiamante nella rappresentazione XML fornita per un set di colonne in un'operazione di inserimento o di aggiornamento, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="cdee1-242">Generates an error when a value is specified for this attribute by the caller in the XML representation provided for a column set in an insert or update operation.</span></span>  
  
## <a name="security"></a><span data-ttu-id="cdee1-243">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cdee1-243">Security</span></span>  
 <span data-ttu-id="cdee1-244">Il funzionamento del modello di sicurezza per un set di colonne è analogo a quello del modello di sicurezza che esiste tra una tabella e le relative colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-244">The security model for a column set works similar to the security model that exists between table and columns.</span></span> <span data-ttu-id="cdee1-245">I set di colonne possono essere visualizzati come una tabella di dimensioni ridotte e un'operazione di selezione è analoga a un'operazione SELECT \* eseguita su tale tabella.</span><span class="sxs-lookup"><span data-stu-id="cdee1-245">Column sets can be visualized as a minitable and a select operation is like a SELECT \* operation on this minitable.</span></span> <span data-ttu-id="cdee1-246">La relazione tra il set di colonne e le colonne di tipo sparse, tuttavia, rappresenta un raggruppamento anziché rappresentare esclusivamente un contenitore.</span><span class="sxs-lookup"><span data-stu-id="cdee1-246">But, the relationship between column set to sparse columns is a grouping relationship instead of strictly a container.</span></span> <span data-ttu-id="cdee1-247">Il modello controlla la sicurezza sulla colonna del set di colonne e applica le operazioni DENY sulle colonne di tipo sparse sottostanti.</span><span class="sxs-lookup"><span data-stu-id="cdee1-247">The security model checks the security on the column set column, and honors the DENY operations on the underlying sparse columns.</span></span> <span data-ttu-id="cdee1-248">Di seguito sono riportate le caratteristiche aggiuntive del modello di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cdee1-248">Additional characteristics of the security model are as follows:</span></span>  
  
-   <span data-ttu-id="cdee1-249">È possibile concedere e revocare le autorizzazioni di sicurezza alla colonna del set di colonne, analogamente a qualsiasi altra colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="cdee1-249">Security permissions can be granted and revoked from the column set column, similar to any other column in the table.</span></span>  
  
-   <span data-ttu-id="cdee1-250">Un'istruzione GRANT o REVOKE dell'autorizzazione SELECT, INSERT, UPDATE, DELETE e REFERENCES su una colonna del set di colonne non si propaga alle colonne membro sottostanti di tale set.</span><span class="sxs-lookup"><span data-stu-id="cdee1-250">A GRANT or REVOKE of SELECT, INSERT, UPDATE, DELETE, and REFERENCES permission on a column set column does not propagate to the underlying member columns of that set.</span></span> <span data-ttu-id="cdee1-251">Questa condizione si applica solo all'utilizzo della colonna del set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-251">It applies only to the usage of the column set column.</span></span> <span data-ttu-id="cdee1-252">L'autorizzazione DENY su un set di colonne si propaga alle colonne di tipo sparse sottostanti della tabella.</span><span class="sxs-lookup"><span data-stu-id="cdee1-252">DENY permission on a column set does propagate to the underlying sparse columns of the table.</span></span>  
  
-   <span data-ttu-id="cdee1-253">Per eseguire le istruzioni SELECT, INSERT, UPDATE e DELETE nella colonna del set di colonne, è necessario che l'utente disponga delle autorizzazioni corrispondenti sulla colonna stessa, nonché dell'autorizzazione corrispondente su tutte le colonne di tipo sparse della tabella.</span><span class="sxs-lookup"><span data-stu-id="cdee1-253">Executing SELECT, INSERT, UPDATE, and DELETE statements on the column set column require that the user has corresponding permissions on the column set column, and also the corresponding permission on all the sparse columns in the table.</span></span> <span data-ttu-id="cdee1-254">Poiché il set di colonne rappresenta tutte le colonne di tipo sparse della tabella, è necessario disporre dell'autorizzazione su tutte le colonne di tipo sparse, incluse quelle che potrebbero anche non subire modifiche.</span><span class="sxs-lookup"><span data-stu-id="cdee1-254">Because the column set represents all the sparse columns in the table, you must have permission on all the sparse columns, and this includes sparse columns that you might not be changing.</span></span>  
  
-   <span data-ttu-id="cdee1-255">L'esecuzione di un'istruzione REVOKE su una colonna di tipo sparse o su un set di colonne imposta automaticamente la sicurezza sul relativo oggetto padre.</span><span class="sxs-lookup"><span data-stu-id="cdee1-255">Executing a REVOKE statement on a sparse column or column set defaults the security to their parent object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cdee1-256">Esempi</span><span class="sxs-lookup"><span data-stu-id="cdee1-256">Examples</span></span>  
 <span data-ttu-id="cdee1-257">Negli esempi seguenti una tabella in cui sono contenuti i documenti è presente il set di colonne comune `DocID` e `Title`.</span><span class="sxs-lookup"><span data-stu-id="cdee1-257">In the following examples, a document table contains the common set of columns `DocID` and `Title`.</span></span> <span data-ttu-id="cdee1-258">Il gruppo Production richiede una colonna `ProductionSpecification` e una colonna `ProductionLocation` per tutti i documenti relativi alla produzione,</span><span class="sxs-lookup"><span data-stu-id="cdee1-258">The Production group wants a `ProductionSpecification` and `ProductionLocation` column for all production documents.</span></span> <span data-ttu-id="cdee1-259">mentre il gruppo Marketing richiede una colonna `MarketingSurveyGroup` per i documenti relativi al marketing.</span><span class="sxs-lookup"><span data-stu-id="cdee1-259">The Marketing group wants a `MarketingSurveyGroup` column for marketing documents.</span></span>  
  
### <a name="a-creating-a-table-that-has-a-column-set"></a><span data-ttu-id="cdee1-260">R.</span><span class="sxs-lookup"><span data-stu-id="cdee1-260">A.</span></span> <span data-ttu-id="cdee1-261">Creazione di una tabella in cui è presente un set di colonne</span><span class="sxs-lookup"><span data-stu-id="cdee1-261">Creating a table that has a column set</span></span>  
 <span data-ttu-id="cdee1-262">Nell'esempio seguente viene creata la tabella che utilizza colonne di tipo sparse e include il set di colonne `SpecialPurposeColumns`.</span><span class="sxs-lookup"><span data-stu-id="cdee1-262">The following example creates the table that uses sparse columns and includes the column set `SpecialPurposeColumns`.</span></span> <span data-ttu-id="cdee1-263">Vengono inserite due righe nella tabella, quindi vengono selezionati dati dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="cdee1-263">The example inserts two rows into the table, and then selects data from the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdee1-264">Questa tabella è costituita solo da cinque colonne per semplificare la visualizzazione e la lettura.</span><span class="sxs-lookup"><span data-stu-id="cdee1-264">This table has only five columns to make it easier to display and read.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
CREATE TABLE DocumentStoreWithColumnSet  
    (DocID int PRIMARY KEY,  
     Title varchar(200) NOT NULL,  
     ProductionSpecification varchar(20) SPARSE NULL,  
     ProductionLocation smallint SPARSE NULL,  
     MarketingSurveyGroup varchar(20) SPARSE NULL,  
     MarketingProgramID int SPARSE NULL,  
     SpecialPurposeColumns XML COLUMN_SET FOR ALL_SPARSE_COLUMNS);  
GO  
```  
  
### <a name="b-inserting-data-to-a-table-by-using-the-names-of-the-sparse-columns"></a><span data-ttu-id="cdee1-265">B.</span><span class="sxs-lookup"><span data-stu-id="cdee1-265">B.</span></span> <span data-ttu-id="cdee1-266">Inserimento di dati in una tabella utilizzando i nomi delle colonne di tipo sparse</span><span class="sxs-lookup"><span data-stu-id="cdee1-266">Inserting data to a table by using the names of the sparse columns</span></span>  
 <span data-ttu-id="cdee1-267">Negli esempi seguenti vengono inserite due righe nella tabella creata nell'esempio A. Negli esempi vengono utilizzati i nomi delle colonne di tipo sparse e non si fa riferimento al set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-267">The following examples insert two rows into the table that is created in example A. The examples use the names of the sparse columns and do not reference the column set.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, ProductionSpecification, ProductionLocation)  
VALUES (1, 'Tire Spec 1', 'AXZZ217', 27);  
GO  
  
INSERT DocumentStoreWithColumnSet (DocID, Title, MarketingSurveyGroup)  
VALUES (2, 'Survey 2142', 'Men 25 - 35');  
GO  
```  
  
### <a name="c-inserting-data-to-a-table-by-using-the-name-of-the-column-set"></a><span data-ttu-id="cdee1-268">C.</span><span class="sxs-lookup"><span data-stu-id="cdee1-268">C.</span></span> <span data-ttu-id="cdee1-269">Inserimento di dati in una tabella utilizzando il nome del set di colonne</span><span class="sxs-lookup"><span data-stu-id="cdee1-269">Inserting data to a table by using the name of the column set</span></span>  
 <span data-ttu-id="cdee1-270">Nell'esempio seguente viene inserita una terza riga nella tabella creata nell'esempio A. In questo caso i nomi delle colonne di tipo sparse non vengono utilizzati,</span><span class="sxs-lookup"><span data-stu-id="cdee1-270">The following example inserts a third row into the table that is created in example A. This time the names of the sparse columns are not used.</span></span> <span data-ttu-id="cdee1-271">ma viene utilizzato il nome del set di colonne. L'inserimento fornisce i valori per due delle quattro colonne di tipo sparse in formato XML.</span><span class="sxs-lookup"><span data-stu-id="cdee1-271">Instead, the name of the column set is used, and the insert provides the values for two of the four sparse columns in XML format.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, SpecialPurposeColumns)  
VALUES (3, 'Tire Spec 2', '<ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>');  
GO  
```  
  
### <a name="d-observing-the-results-of-a-column-set-when-select--is-used"></a><span data-ttu-id="cdee1-272">D.</span><span class="sxs-lookup"><span data-stu-id="cdee1-272">D.</span></span> <span data-ttu-id="cdee1-273">Analisi dei risultati di un set di colonne quando viene utilizzata l'istruzione SELECT \*</span><span class="sxs-lookup"><span data-stu-id="cdee1-273">Observing the results of a column set when SELECT \* is used</span></span>  
 <span data-ttu-id="cdee1-274">Nell'esempio seguente vengono selezionate tutte le colonne dalla tabella che contiene un set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-274">The following example selects all the columns from the table that contains a column set.</span></span> <span data-ttu-id="cdee1-275">Viene restituita una colonna XML con i valori combinati delle colonne di tipo sparse,</span><span class="sxs-lookup"><span data-stu-id="cdee1-275">It returns an XML column with the combined values of the sparse columns.</span></span> <span data-ttu-id="cdee1-276">ma non vengono restituite le singole colonne di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="cdee1-276">It does not return the sparse columns individually.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns FROM DocumentStoreWithColumnSet ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1      Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `2      Survey 2142  <MarketingSurveyGroup>Men 25 - 35</MarketingSurveyGroup>`  
  
 `3      Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="e-observing-the-results-of-selecting-the-column-set-by-name"></a><span data-ttu-id="cdee1-277">E.</span><span class="sxs-lookup"><span data-stu-id="cdee1-277">E.</span></span> <span data-ttu-id="cdee1-278">Analisi dei risultati della selezione del set di colonne in base al nome</span><span class="sxs-lookup"><span data-stu-id="cdee1-278">Observing the results of selecting the column set by name</span></span>  
 <span data-ttu-id="cdee1-279">Poiché i dati di marketing non interessano il reparto Production, in questo esempio viene aggiunta una clausola `WHERE` per limitare l'output.</span><span class="sxs-lookup"><span data-stu-id="cdee1-279">Because the Production department is not interested in the marketing data, this example adds a `WHERE` clause to restrict the output.</span></span> <span data-ttu-id="cdee1-280">Nell'esempio viene utilizzato il nome del set di colonne.</span><span class="sxs-lookup"><span data-stu-id="cdee1-280">The example uses the name of the column set.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns  
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1     Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `3     Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="f-observing-the-results-of-selecting-sparse-columns-by-name"></a><span data-ttu-id="cdee1-281">F.</span><span class="sxs-lookup"><span data-stu-id="cdee1-281">F.</span></span> <span data-ttu-id="cdee1-282">Analisi dei risultati della selezione di colonne di tipo sparse in base al nome</span><span class="sxs-lookup"><span data-stu-id="cdee1-282">Observing the results of selecting sparse columns by name</span></span>  
 <span data-ttu-id="cdee1-283">Quando una tabella contiene un set di colonne, è ancora possibile eseguire una query sulla tabella utilizzando i nomi delle singole colonne come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cdee1-283">When a table contains a column set, you can still query the table by using the individual column names as shown in the following example.</span></span>  
  
```  
SELECT DocID, Title, ProductionSpecification, ProductionLocation   
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        ProductionSpecification ProductionLocation`  
  
 `1     Tire Spec 1  AXZZ217                 27`  
  
 `3     Tire Spec 2  AXW9R411                38`  
  
### <a name="g-updating-a-table-by-using-a-column-set"></a><span data-ttu-id="cdee1-284">G.</span><span class="sxs-lookup"><span data-stu-id="cdee1-284">G.</span></span> <span data-ttu-id="cdee1-285">Aggiornamento di una tabella tramite un set di colonne</span><span class="sxs-lookup"><span data-stu-id="cdee1-285">Updating a table by using a column set</span></span>  
 <span data-ttu-id="cdee1-286">Nell'esempio seguente viene aggiornato il terzo record con i nuovi valori per entrambe le colonne di tipo sparse utilizzate da tale riga.</span><span class="sxs-lookup"><span data-stu-id="cdee1-286">The following example updates the third record with new values for both sparse columns that are used by that row.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification><ProductionLocation>38</ProductionLocation>'  
WHERE DocID = 3 ;  
GO  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cdee1-287">Un'istruzione UPDATE che utilizza un set di colonne aggiorna tutte le colonne di tipo sparse della tabella.</span><span class="sxs-lookup"><span data-stu-id="cdee1-287">An UPDATE statement that uses a column set updates all the sparse columns in the table.</span></span> <span data-ttu-id="cdee1-288">Le colonne di tipo sparse alle quali non viene fatto riferimento vengono impostate su NULL.</span><span class="sxs-lookup"><span data-stu-id="cdee1-288">Sparse columns that are not referenced are updated to NULL.</span></span>  
  
 <span data-ttu-id="cdee1-289">Nell'esempio seguente viene aggiornato il terzo record, ma viene specificato solo il valore di una delle due colonne popolate.</span><span class="sxs-lookup"><span data-stu-id="cdee1-289">The following example updates the third record, but only specifies the value of one of the two populated columns.</span></span> <span data-ttu-id="cdee1-290">La seconda colonna `ProductionLocation` non è inclusa nell'istruzione `UPDATE` e viene impostata su NULL.</span><span class="sxs-lookup"><span data-stu-id="cdee1-290">The second column `ProductionLocation` is not included in the `UPDATE` statement and is updated to NULL.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification>'  
WHERE DocID = 3 ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdee1-291">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdee1-291">See Also</span></span>  
 [<span data-ttu-id="cdee1-292">Utilizzo di colonne di tipo sparse</span><span class="sxs-lookup"><span data-stu-id="cdee1-292">Use Sparse Columns</span></span>](use-sparse-columns.md)  
  
  
