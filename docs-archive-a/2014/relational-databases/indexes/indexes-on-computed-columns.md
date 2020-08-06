---
title: Indici per le colonne calcolate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, index creation
- index creation [SQL Server], computed columns
- imprecise columns
- persisted computed columns
- precise [SQL Server]
ms.assetid: 8d17ac9c-f3af-4bbb-9cc1-5cf647e994c4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ecbca9e7838c4c9395a8bcb6e11351c40f7037f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725740"
---
# <a name="indexes-on-computed-columns"></a><span data-ttu-id="d11d1-102">Indici per le colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="d11d1-102">Indexes on Computed Columns</span></span>
  <span data-ttu-id="d11d1-103">È possibile definire gli indici per le colonne calcolate purché siano soddisfatti i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11d1-103">You can define indexes on computed columns as long as the following requirements are met:</span></span>  
  
-   <span data-ttu-id="d11d1-104">Requisiti di proprietà</span><span class="sxs-lookup"><span data-stu-id="d11d1-104">Ownership requirements</span></span>  
  
-   <span data-ttu-id="d11d1-105">Requisiti di determinismo</span><span class="sxs-lookup"><span data-stu-id="d11d1-105">Determinism requirements</span></span>  
  
-   <span data-ttu-id="d11d1-106">Requisiti di precisione</span><span class="sxs-lookup"><span data-stu-id="d11d1-106">Precision requirements</span></span>  
  
-   <span data-ttu-id="d11d1-107">Requisiti del tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d11d1-107">Data type requirements</span></span>  
  
-   <span data-ttu-id="d11d1-108">Requisiti dell'opzione SET</span><span class="sxs-lookup"><span data-stu-id="d11d1-108">SET option requirements</span></span>  
  
 <span data-ttu-id="d11d1-109">**Ownership Requirements**</span><span class="sxs-lookup"><span data-stu-id="d11d1-109">**Ownership Requirements**</span></span>  
  
 <span data-ttu-id="d11d1-110">Tutti i riferimenti a funzioni nella colonna calcolata devono avere lo stesso proprietario della tabella.</span><span class="sxs-lookup"><span data-stu-id="d11d1-110">All function references in the computed column must have the same owner as the table.</span></span>  
  
 <span data-ttu-id="d11d1-111">**Determinism Requirements**</span><span class="sxs-lookup"><span data-stu-id="d11d1-111">**Determinism Requirements**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d11d1-112">Le espressioni sono deterministiche se restituiscono sempre lo stesso risultato per un determinato set di input.</span><span class="sxs-lookup"><span data-stu-id="d11d1-112">Expressions are deterministic if they always return the same result for a specified set of inputs.</span></span> <span data-ttu-id="d11d1-113">La proprietà **IsDeterministic** della funzione [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) indica se una *computed_column_expression* è deterministica.</span><span class="sxs-lookup"><span data-stu-id="d11d1-113">The **IsDeterministic** property of the [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) function reports whether a *computed_column_expression* is deterministic.</span></span>  
  
 <span data-ttu-id="d11d1-114">La *computed_column_expression* deve essere deterministica.</span><span class="sxs-lookup"><span data-stu-id="d11d1-114">The *computed_column_expression* must be deterministic.</span></span> <span data-ttu-id="d11d1-115">Una *computed_column_expression* è deterministica quando viene soddisfatta una o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11d1-115">A *computed_column_expression* is deterministic when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="d11d1-116">Tutte le funzioni alle quali l'espressione fa riferimento sono deterministiche e precise.</span><span class="sxs-lookup"><span data-stu-id="d11d1-116">All functions that are referenced by the expression are deterministic and precise.</span></span> <span data-ttu-id="d11d1-117">Queste funzioni includono funzioni definite dall'utente e funzioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="d11d1-117">These functions include both user-defined and built-in functions.</span></span> <span data-ttu-id="d11d1-118">Per altre informazioni, vedere [Funzioni deterministiche e non deterministiche](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d11d1-118">For more information, see [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span></span> <span data-ttu-id="d11d1-119">Le funzioni potrebbero non essere precise se la colonna calcolata è PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="d11d1-119">Functions might be imprecise if the computed column is PERSISTED.</span></span> <span data-ttu-id="d11d1-120">Per altre informazioni, vedere [Creazione di indici per colonne calcolate persistenti](#BKMK_persisted) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d11d1-120">For more information, see [Creating Indexes on Persisted Computed Columns](#BKMK_persisted) later in this topic.</span></span>  
  
-   <span data-ttu-id="d11d1-121">Tutte le colonne alle quali viene fatto riferimento nell'espressione appartengono alla tabella contenente la colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="d11d1-121">All columns that are referenced in the expression come from the table that contains the computed column.</span></span>  
  
-   <span data-ttu-id="d11d1-122">Nessun riferimento a una colonna estrae dati da più righe.</span><span class="sxs-lookup"><span data-stu-id="d11d1-122">No column reference pulls data from multiple rows.</span></span> <span data-ttu-id="d11d1-123">Ad esempio, funzioni di aggregazione quali SUM o AVG dipendono dai dati presenti in più righe e renderebbero non deterministica una *computed_column_expression* .</span><span class="sxs-lookup"><span data-stu-id="d11d1-123">For example, aggregate functions such as SUM or AVG depend on data from multiple rows and would make a *computed_column_expression* nondeterministic.</span></span>  
  
-   <span data-ttu-id="d11d1-124">L'espressione *computed_column_expression* è priva di accesso ai dati di sistema o ai dati utente.</span><span class="sxs-lookup"><span data-stu-id="d11d1-124">The *computed_column_expression* has no system data access or user data access.</span></span>  
  
 <span data-ttu-id="d11d1-125">Qualsiasi colonna calcolata contenente un'espressione CLR (Common Language Runtime) deve essere deterministica e contrassegnata come PERSISTED prima di poter essere indicizzata.</span><span class="sxs-lookup"><span data-stu-id="d11d1-125">Any computed column that contains a common language runtime (CLR) expression must be deterministic and marked PERSISTED before the column can be indexed.</span></span> <span data-ttu-id="d11d1-126">Le espressioni di tipo CLR definito dall'utente sono consentite nelle definizioni delle colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="d11d1-126">CLR user-defined type expressions are allowed in computed column definitions.</span></span> <span data-ttu-id="d11d1-127">Le colonne calcolate di tipo CLR definito dall'utente possono essere indicizzate purché il tipo sia confrontabile.</span><span class="sxs-lookup"><span data-stu-id="d11d1-127">Computed columns whose type is a CLR user-defined type can be indexed as long as the type is comparable.</span></span> <span data-ttu-id="d11d1-128">Per altre informazioni, vedere [Tipi CLR definiti dall'utente](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="d11d1-128">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d11d1-129">Quando si fa riferimento ai valori letterali stringa del tipo di dati relativo alla data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], si consiglia di convertire in modo esplicito il valore letterale nel tipo di data che si desidera utilizzando uno stile di formato di data deterministico.</span><span class="sxs-lookup"><span data-stu-id="d11d1-129">When you refer to string literals of the date data type in indexed computed columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], we recommend that you explicitly convert the literal to the date type that you want by using a deterministic date format style.</span></span> <span data-ttu-id="d11d1-130">Per un elenco degli stili del formato di data deterministici, vedere [CAST e CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d11d1-130">For a list of the date format styles that are deterministic, see [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span> <span data-ttu-id="d11d1-131">Le espressioni che prevedono la conversione implicita delle stringhe di carattere nei tipi di dati relativi alla data vengono considerate non deterministiche, a meno che il livello di compatibilità del database non venga impostato su 80 o su un valore inferiore.</span><span class="sxs-lookup"><span data-stu-id="d11d1-131">Expressions that involve implicit conversion of character strings to date data types are considered nondeterministic, unless the database compatibility level is set to 80 or earlier.</span></span> <span data-ttu-id="d11d1-132">Ciò è dovuto al fatto che i risultati dipendono dalle impostazioni [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) e [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) della sessione del server.</span><span class="sxs-lookup"><span data-stu-id="d11d1-132">This is because the results depend on the [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) and [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) settings of the server session.</span></span> <span data-ttu-id="d11d1-133">I risultati dell'espressione `CONVERT (datetime, '30 listopad 1996', 113)` dipendono ad esempio dall'impostazione LANGUAGE, in quanto la stringa '`30 listopad 1996`' indica mesi diversi in diverse lingue.</span><span class="sxs-lookup"><span data-stu-id="d11d1-133">For example, the results of the expression `CONVERT (datetime, '30 listopad 1996', 113)` depend on the LANGUAGE setting because the string '`30 listopad 1996`' means different months in different languages.</span></span> <span data-ttu-id="d11d1-134">Analogamente, nell'espressione `DATEADD(mm,3,'2000-12-01')`, [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interpreta la stringa `'2000-12-01'` in base all'impostazione DATEFORMAT.</span><span class="sxs-lookup"><span data-stu-id="d11d1-134">Similarly, in the expression `DATEADD(mm,3,'2000-12-01')`, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interprets the string `'2000-12-01'` based on the DATEFORMAT setting.</span></span>  
>   
>  <span data-ttu-id="d11d1-135">Anche la conversione implicita dei dati di tipo carattere non Unicode tra regole di confronto viene considerata non deterministica, a meno che il livello di compatibilità non sia impostato su un valore minore o uguale a 80.</span><span class="sxs-lookup"><span data-stu-id="d11d1-135">Implicit conversion of non-Unicode character data between collations is also considered nondeterministic, unless the compatibility level is set to 80 or earlier.</span></span>  
>   
>  <span data-ttu-id="d11d1-136">Se l'impostazione del livello di compatibilità del database è 90, non è possibile creare indici su colonne calcolate contenenti tali espressioni.</span><span class="sxs-lookup"><span data-stu-id="d11d1-136">When the database compatibility level setting is 90, you cannot create indexes on computed columns that contain these expressions.</span></span> <span data-ttu-id="d11d1-137">Tuttavia, le colonne calcolate esistenti che includono queste espressioni da un database aggiornato sono gestibili.</span><span class="sxs-lookup"><span data-stu-id="d11d1-137">However, existing computed columns that contain these expressions from an upgraded database are maintainable.</span></span> <span data-ttu-id="d11d1-138">Se si utilizzano colonne calcolate che includono conversioni implicite da valori di tipo stringa a valori di tipo data, verificare che le impostazioni LANGUAGE e DATEFORMAT siano consistenti nei database e nelle applicazioni per evitare l'eventuale danneggiamento dell'indice.</span><span class="sxs-lookup"><span data-stu-id="d11d1-138">If you use indexed computed columns that contain implicit string to date conversions, to avoid possible index corruption, make sure that the LANGUAGE and DATEFORMAT settings are consistent in your databases and applications.</span></span>  
  
 <span data-ttu-id="d11d1-139">**Precision Requirements**</span><span class="sxs-lookup"><span data-stu-id="d11d1-139">**Precision Requirements**</span></span>  
  
 <span data-ttu-id="d11d1-140">La *computed_column_expression* deve essere precisa.</span><span class="sxs-lookup"><span data-stu-id="d11d1-140">The *computed_column_expression* must be precise.</span></span> <span data-ttu-id="d11d1-141">Una *computed_column_expression* è precisa quando viene soddisfatta una o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d11d1-141">A *computed_column_expression* is precise when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="d11d1-142">Non è un'espressione dei tipi di dati `float` o `real`.</span><span class="sxs-lookup"><span data-stu-id="d11d1-142">It is not an expression of the `float` or `real` data types.</span></span>  
  
-   <span data-ttu-id="d11d1-143">Nella definizione dell'espressione non viene utilizzato il tipo di dati `float` o `real`.</span><span class="sxs-lookup"><span data-stu-id="d11d1-143">It does not use a `float` or `real` data type in its definition.</span></span> <span data-ttu-id="d11d1-144">Ad esempio, nell'istruzione seguente la colonna `y` è di tipo `int` ed è deterministica, ma non precisa:</span><span class="sxs-lookup"><span data-stu-id="d11d1-144">For example, in the following statement, column `y` is `int` and deterministic but not precise.</span></span>  
  
    ```  
    CREATE TABLE t2 (a int, b int, c int, x float,   
       y AS CASE x   
             WHEN 0 THEN a   
             WHEN 1 THEN b   
             ELSE c   
          END);  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="d11d1-145">Le espressioni di tipo `float` o `real` sono considerate non precise e non possono essere utilizzate come chiavi di un indice. Le espressioni `float` o `real` sono quindi utilizzabili in una vista indicizzata ma non come chiavi.</span><span class="sxs-lookup"><span data-stu-id="d11d1-145">Any `float` or `real` expression is considered imprecise and cannot be a key of an index; a `float` or `real` expression can be used in an indexed view but not as a key.</span></span> <span data-ttu-id="d11d1-146">Questa considerazione è valida anche per le colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="d11d1-146">This is true also for computed columns.</span></span> <span data-ttu-id="d11d1-147">Funzioni, espressioni oppure funzioni definite dall'utente sono considerate non precise se includono espressioni `float` oppure `real`.</span><span class="sxs-lookup"><span data-stu-id="d11d1-147">Any function, expression, or user-defined function is considered imprecise if it contains any `float` or `real` expressions.</span></span> <span data-ttu-id="d11d1-148">Sono comprese le espressioni logiche (confronti).</span><span class="sxs-lookup"><span data-stu-id="d11d1-148">This includes logical ones (comparisons).</span></span>  
  
 <span data-ttu-id="d11d1-149">La proprietà **IsPrecise** della funzione COLUMNPROPERTY indica se una *computed_column_expression* è precisa.</span><span class="sxs-lookup"><span data-stu-id="d11d1-149">The **IsPrecise** property of the COLUMNPROPERTY function reports whether a *computed_column_expression* is precise.</span></span>  
  
 <span data-ttu-id="d11d1-150">**Data Type Requirements**</span><span class="sxs-lookup"><span data-stu-id="d11d1-150">**Data Type Requirements**</span></span>  
  
-   <span data-ttu-id="d11d1-151">Il *computed_column_expression* definito per la colonna calcolata non può restituire i `text` `ntext` tipi di dati, o `image` .</span><span class="sxs-lookup"><span data-stu-id="d11d1-151">The *computed_column_expression* defined for the computed column cannot evaluate to the `text`, `ntext`, or `image` data types.</span></span>  
  
-   <span data-ttu-id="d11d1-152">Le colonne calcolate derivate dai tipi di dati `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` e `xml` possono essere indicizzate purché il tipo di dati della colonna calcolata sia consentito come colonna chiave indice.</span><span class="sxs-lookup"><span data-stu-id="d11d1-152">Computed columns derived from `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, and `xml` data types can be indexed as long as the computed column data type is allowable as an index key column.</span></span>  
  
-   <span data-ttu-id="d11d1-153">Le colonne calcolate derivate dai tipi di dati `image`, `ntext` e `text` possono essere colonne non chiave (incluse) in un indice non cluster purché il tipo di dati della colonna calcolata sia consentito come colonna non chiave dell'indice.</span><span class="sxs-lookup"><span data-stu-id="d11d1-153">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey (included) columns in a nonclustered index as long as the computed column data type is allowable as a nonkey index column.</span></span>  
  
 <span data-ttu-id="d11d1-154">**Requisiti dell'opzione SET**</span><span class="sxs-lookup"><span data-stu-id="d11d1-154">**SET Option Requirements**</span></span>  
  
-   <span data-ttu-id="d11d1-155">Quando viene eseguita l'istruzione CREATE TABLE o ALTER TABLE che definisce la colonna calcolata, è necessario impostare su ON l'opzione a livello di connessione ANSI_NULL.</span><span class="sxs-lookup"><span data-stu-id="d11d1-155">The ANSI_NULLS connection-level option must be set to ON when the CREATE TABLE or ALTER TABLE statement that defines the computed column is executed.</span></span> <span data-ttu-id="d11d1-156">La funzione [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) indica se l'opzione è impostata su ON nella proprietà **IsAnsiNullsOn** .</span><span class="sxs-lookup"><span data-stu-id="d11d1-156">The [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) function reports whether the option is on through the **IsAnsiNullsOn** property.</span></span>  
  
-   <span data-ttu-id="d11d1-157">Per la connessione in corrispondenza della quale viene creato l'indice e per tutte le connessioni che tentano di eseguire istruzioni INSERT, UPDATE o DELETE che modificano i valori dell'indice, sei opzioni SET devono essere impostate su ON e un'opzione SET deve essere impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="d11d1-157">The connection on which the index is created, and all connections trying INSERT, UPDATE, or DELETE statements that will change values in the index, must have six SET options set to ON and one option set to OFF.</span></span> <span data-ttu-id="d11d1-158">Per tutte le eventuali istruzioni SELECT eseguite da una connessione per la quale non sono state definite esattamente le impostazioni delle opzioni indicate di seguito, Query Optimizer ignora gli indici definiti su una colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="d11d1-158">The optimizer ignores an index on a computed column for any SELECT statement executed by a connection that does not have these same option settings.</span></span>  
  
    -   <span data-ttu-id="d11d1-159">L'opzione NUMERIC_ROUNDABORT deve essere impostata su OFF e le opzioni seguenti su ON.</span><span class="sxs-lookup"><span data-stu-id="d11d1-159">The NUMERIC_ROUNDABORT option must be set to OFF, and the following options must be set to ON:</span></span>  
  
    -   <span data-ttu-id="d11d1-160">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="d11d1-160">ANSI_NULLS</span></span>  
  
    -   <span data-ttu-id="d11d1-161">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="d11d1-161">ANSI_PADDING</span></span>  
  
    -   <span data-ttu-id="d11d1-162">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="d11d1-162">ANSI_WARNINGS</span></span>  
  
    -   <span data-ttu-id="d11d1-163">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="d11d1-163">ARITHABORT</span></span>  
  
    -   <span data-ttu-id="d11d1-164">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="d11d1-164">CONCAT_NULL_YIELDS_NULL</span></span>  
  
    -   <span data-ttu-id="d11d1-165">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="d11d1-165">QUOTED_IDENTIFIER</span></span>  
  
     <span data-ttu-id="d11d1-166">Quando il livello di compatibilità del database è impostato su 90 o su un valore maggiore, l'impostazione di ANSI_WARNINGS su ON comporta anche l'impostazione implicita di ARITHABORT su ON.</span><span class="sxs-lookup"><span data-stu-id="d11d1-166">Setting ANSI_WARNINGS to ON implicitly sets ARITHABORT to ON when the database compatibility level is set to 90 or higher.</span></span>  
  
##  <a name="creating-indexes-on-persisted-computed-columns"></a><a name="BKMK_persisted"></a> <span data-ttu-id="d11d1-167">Creazione di indici per colonne calcolate persistenti</span><span class="sxs-lookup"><span data-stu-id="d11d1-167">Creating Indexes on Persisted Computed Columns</span></span>  
 <span data-ttu-id="d11d1-168">È possibile creare un indice su una colonna calcolata. definita da un'espressione deterministica, ma non precisa, se la colonna è contrassegnata come PERSISTED nell'istruzione CREATE TABLE oppure ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="d11d1-168">You can create an index on a computed column that is defined with a deterministic, but imprecise, expression if the column is marked PERSISTED in the CREATE TABLE or ALTER TABLE statement.</span></span> <span data-ttu-id="d11d1-169">Ciò significa che [!INCLUDE[ssDE](../../../includes/ssde-md.md)] utilizza questi valori salvati in modo permanente quando crea un indice sulla colonna e quando viene fatto riferimento all'indice in una query.</span><span class="sxs-lookup"><span data-stu-id="d11d1-169">This means that the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] uses these persisted values when it creates an index on the column, and when the index is referenced in a query.</span></span> <span data-ttu-id="d11d1-170">Questa opzione consente di creare un indice in una colonna calcolata quando [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)] è deterministico e preciso.</span><span class="sxs-lookup"><span data-stu-id="d11d1-170">This option enables you to create an index on a computed column when [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)], is both deterministic and precise.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="d11d1-171">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="d11d1-171">Related Content</span></span>  
 [<span data-ttu-id="d11d1-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d11d1-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
  
