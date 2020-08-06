---
title: Sintassi ed esempi di filtri dei modelli (Analysis Services-Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filter syntax [data mining]
- filters [data mining]
- filters [Analysis Services]
ms.assetid: c729d9b3-8fda-405e-9497-52b2d7493eae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7ca200d179c0fe81b948793a4b4478f71502657
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712651"
---
# <a name="model-filter-syntax-and-examples-analysis-services---data-mining"></a><span data-ttu-id="9f9b5-102">Sintassi ed esempi di filtri dei modelli (Analysis Services – Data mining)</span><span class="sxs-lookup"><span data-stu-id="9f9b5-102">Model Filter Syntax and Examples (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="9f9b5-103">In questa sezione vengono fornite informazioni dettagliate sulla sintassi dei filtri dei modelli, insieme alle espressioni di esempio.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-103">This section provides detailed information about the syntax for model filters, together with sample expressions.</span></span>  
  
 
  
##  <a name="filter-syntax"></a><a name="bkmk_Syntax"></a> <span data-ttu-id="9f9b5-104">Filter Syntax</span><span class="sxs-lookup"><span data-stu-id="9f9b5-104">Filter Syntax</span></span>  
 <span data-ttu-id="9f9b5-105">Le espressioni di filtro in genere sono equivalenti al contenuto di una clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-105">Filter expressions generally are equivalent to the content of a WHERE clause.</span></span> <span data-ttu-id="9f9b5-106">È possibile connettere più condizioni utilizzando gli operatori logici `AND`, `OR` e `NOT`.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-106">You can connect multiple conditions by using the logical operators `AND`, `OR`, and `NOT`.</span></span>  
  
 <span data-ttu-id="9f9b5-107">Nelle tabelle nidificate è anche possibile utilizzare gli operatori `EXISTS` e `NOT EXISTS`</span><span class="sxs-lookup"><span data-stu-id="9f9b5-107">In nested tables, you can also use the `EXISTS` and `NOT EXISTS` operators.</span></span> <span data-ttu-id="9f9b5-108">Una condizione `EXISTS` restituisce `true` se la sottoquery restituisce almeno una riga.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-108">An `EXISTS` condition evaluates to `true` if the subquery returns at least one row.</span></span> <span data-ttu-id="9f9b5-109">Ciò risulta utile nei case in cui si desidera limitare il modello ai case che contengono un determinato valore nella tabella nidificata: ad esempio, i clienti che hanno acquistato almeno una volta un articolo.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-109">This is useful in cases where you want to restrict the model to cases that contain a particular value in the nested table: for example, customers who have purchased an item at least once.</span></span>  
  
 <span data-ttu-id="9f9b5-110">Una condizione `NOT EXISTS` restituisce `true` se la condizione specifica nella sottoquery non esiste.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-110">A `NOT EXISTS` condition evaluates to `true` if the condition specified in the subquery does not exist.</span></span> <span data-ttu-id="9f9b5-111">Ad esempio, quando si desidera limitare il modello ai clienti che non hanno mai acquistato un determinato articolo.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-111">An example is when you want to restrict the model to customers who have never purchased a particular item.</span></span>  
  
 <span data-ttu-id="9f9b5-112">La sintassi generale è la seguente:</span><span class="sxs-lookup"><span data-stu-id="9f9b5-112">The general syntax is as follows:</span></span>  
  
```  
<filter>::=<predicate list>  | ( <predicate list> )  
<predicate list>::= <predicate> | [<logical_operator> <predicate list>]   
<logical_operator::= AND| OR  
<predicate>::= NOT <predicate>|( <predicate> ) <avPredicate> | <nestedTablePredicate> | ( <predicate> )   
<avPredicate>::= <columnName> <operator> <scalar> | <columnName> IS [NOT] NULL  
<operator>::= = | != | <> | > | >= | < | <=  
<nestedTablePredicate>::= EXISTS (<subquery>)  
<subquery>::=SELECT * FROM <columnName>[ WHERE  <predicate list> ]  
```  
  
 <span data-ttu-id="9f9b5-113">*filtro*</span><span class="sxs-lookup"><span data-stu-id="9f9b5-113">*filter*</span></span>  
 <span data-ttu-id="9f9b5-114">Contiene uno o più predicati, connessi da operatori logici.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-114">Contains one or more predicates, connected by logical operators.</span></span>  
  
 <span data-ttu-id="9f9b5-115">*elenco predicati*</span><span class="sxs-lookup"><span data-stu-id="9f9b5-115">*predicate list*</span></span>  
 <span data-ttu-id="9f9b5-116">Una o più espressioni di filtro valide, separate da operatori logici.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-116">One or more valid filter expressions, separated by logical operators.</span></span>  
  
 <span data-ttu-id="9f9b5-117">*columnName*</span><span class="sxs-lookup"><span data-stu-id="9f9b5-117">*columnName*</span></span>  
 <span data-ttu-id="9f9b5-118">Nome della colonna della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-118">The name of a mining structure column.</span></span>  
  
 <span data-ttu-id="9f9b5-119">operatore logico</span><span class="sxs-lookup"><span data-stu-id="9f9b5-119">logical operator</span></span>  
 <span data-ttu-id="9f9b5-120">`AND`, `OR`, `NOT`</span><span class="sxs-lookup"><span data-stu-id="9f9b5-120">`AND`, `OR`, `NOT`</span></span>  
  
 <span data-ttu-id="9f9b5-121">*avPredicate*</span><span class="sxs-lookup"><span data-stu-id="9f9b5-121">*avPredicate*</span></span>  
 <span data-ttu-id="9f9b5-122">Espressione del filtro che può essere applicata solo a una colonna scalare della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-122">Filter expression that can be applied to scalar mining structure column only.</span></span> <span data-ttu-id="9f9b5-123">Un'espressione *avPredicate* può essere usata sia nei filtri dei modelli sia nei filtri della tabella annidata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-123">An *avPredicate* expression can be used in both model filters or nested table filters.</span></span>  
  
 <span data-ttu-id="9f9b5-124">Un'espressione che utilizza alcuni degli operatori seguenti può essere applicata solo a una colonna continua.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-124">An expression that uses any of the following operators can only be applied to a continuous column.</span></span> <span data-ttu-id="9f9b5-125">:</span><span class="sxs-lookup"><span data-stu-id="9f9b5-125">:</span></span>  
  
-   <span data-ttu-id="9f9b5-126">**\<**(minore di)</span><span class="sxs-lookup"><span data-stu-id="9f9b5-126">**\<** (less than)</span></span>  
  
-   <span data-ttu-id="9f9b5-127">**>**(maggiore di)</span><span class="sxs-lookup"><span data-stu-id="9f9b5-127">**>** (greater than)</span></span>  
  
-   <span data-ttu-id="9f9b5-128">**>=**(maggiore o uguale a)</span><span class="sxs-lookup"><span data-stu-id="9f9b5-128">**>=** (greater than or equal to)</span></span>  
  
-   <span data-ttu-id="9f9b5-129">**\<=**(minore o uguale a)</span><span class="sxs-lookup"><span data-stu-id="9f9b5-129">**\<=** (less than or equal to)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f9b5-130">Indipendentemente dal tipo di dati, questi operatori non possono essere applicati a una colonna di tipo `Discrete`, `Discretized` o `Key`.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-130">Regardless of the data type, these operators cannot be applied to a column that has the type `Discrete`, `Discretized`, or `Key`.</span></span>  
  
 <span data-ttu-id="9f9b5-131">Un'espressione che utilizza alcuni degli operatori seguenti può essere applicata a una colonna continua, discreta, discretizzata o chiave:</span><span class="sxs-lookup"><span data-stu-id="9f9b5-131">An expression that uses any of the following operators can be applied to a continuous, discrete, discretized, or key column:</span></span>  
  
-   <span data-ttu-id="9f9b5-132">**=** è uguale a</span><span class="sxs-lookup"><span data-stu-id="9f9b5-132">**=** (equals)</span></span>  
  
-   <span data-ttu-id="9f9b5-133">**! =** (diverso da)</span><span class="sxs-lookup"><span data-stu-id="9f9b5-133">**!=** (not equal to)</span></span>  
  
-   <span data-ttu-id="9f9b5-134">**È NULL**</span><span class="sxs-lookup"><span data-stu-id="9f9b5-134">**IS NULL**</span></span>  
  
 <span data-ttu-id="9f9b5-135">Se l'argomento *avPredicate*si applica a una colonna discretizzata, il valore usato nel filtro può essere qualsiasi valore in un bucket specifico.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-135">If the argument, *avPredicate*, applies to a discretized column, the value used in the filter can be any value in a specific bucket.</span></span>  
  
 <span data-ttu-id="9f9b5-136">In altre parole, la condizione non viene definita come `AgeDisc = '25-35'`, ma viene invece calcolata e viene quindi usato un valore dall'intervallo.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-136">In other words, you do not define the condition as `AgeDisc = '25-35'`, but instead compute and then use a value from that interval.</span></span>  
  
 <span data-ttu-id="9f9b5-137">Esempio:  `AgeDisc = 27`  indica qualsiasi valore nello stesso intervallo di 27, in questo caso 25-35.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-137">Example:  `AgeDisc = 27`  means any value in the same interval as 27, which in this case is 25-35.</span></span>  
  
 <span data-ttu-id="9f9b5-138">*nestedTablePredicate*</span><span class="sxs-lookup"><span data-stu-id="9f9b5-138">*nestedTablePredicate*</span></span>  
 <span data-ttu-id="9f9b5-139">Espressione di filtro applicabile a una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-139">Filter expression that applies to a nested table.</span></span> <span data-ttu-id="9f9b5-140">Può essere utilizzata solo nei filtri dei modelli.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-140">Can be used in model filters only.</span></span>  
  
 <span data-ttu-id="9f9b5-141">L'argomento della sottoquery dell'argomento, *nestedTablePredicate*, può essere applicato solo a una colonna della struttura di data mining della tabella</span><span class="sxs-lookup"><span data-stu-id="9f9b5-141">The sub-query argument of the argument, *nestedTablePredicate*, can only apply to a table mining structure column</span></span>  
  
 <span data-ttu-id="9f9b5-142">Sottoquery</span><span class="sxs-lookup"><span data-stu-id="9f9b5-142">subquery</span></span>  
 <span data-ttu-id="9f9b5-143">Istruzione SELECT seguita da un predicato valido o da un elenco di predicati.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-143">A SELECT statement followed by a valid predicate or list of predicates.</span></span>  
  
 <span data-ttu-id="9f9b5-144">Tutti i predicati devono corrispondere al tipo descritto in *avPredicates*.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-144">All the predicates must be of the type described in *avPredicates*.</span></span> <span data-ttu-id="9f9b5-145">Inoltre, i predicati possono fare riferimento solo a colonne incluse nella tabella annidata attuale, identificata dall'argomento *columnName*.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-145">Furthermore, the predicates can refer only to columns that are included in the current nested table, identified by the argument, *columnName*.</span></span>  
  
### <a name="limitations-on-filter-syntax"></a><span data-ttu-id="9f9b5-146">Limitazioni della sintassi del filtro</span><span class="sxs-lookup"><span data-stu-id="9f9b5-146">Limitations on Filter Syntax</span></span>  
 <span data-ttu-id="9f9b5-147">Ai filtri si applicano le seguenti restrizioni:</span><span class="sxs-lookup"><span data-stu-id="9f9b5-147">The following restrictions apply to filters:</span></span>  
  
-   <span data-ttu-id="9f9b5-148">Un filtro può contenere solo predicati semplici.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-148">A filter can contain only simple predicates.</span></span> <span data-ttu-id="9f9b5-149">Questi includono operatori matematici, scalari e nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-149">These include mathematical operators, scalars, and column names.</span></span>  
  
-   <span data-ttu-id="9f9b5-150">Le funzioni definite dall'utente non sono supportate nella sintassi del filtro.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-150">User-defined functions are not supported in the filter syntax.</span></span>  
  
-   <span data-ttu-id="9f9b5-151">Gli operatori non booleani, come i segni più o meno, non sono supportati nella sintassi del filtro.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-151">Non-Boolean operators, such as the plus or minus signs, are not supported in the filter syntax.</span></span>  
  
## <a name="examples-of-filters"></a><span data-ttu-id="9f9b5-152">Esempi di filtri</span><span class="sxs-lookup"><span data-stu-id="9f9b5-152">Examples of Filters</span></span>  
 <span data-ttu-id="9f9b5-153">Negli esempi seguenti viene illustrato l'utilizzo di filtri applicati a un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-153">The following examples demonstrate the use of filters applied to a mining model.</span></span> <span data-ttu-id="9f9b5-154">Se si crea l'espressione di filtro usando [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], nella finestra **Proprietà** e nel riquadro **Espressione** della finestra di dialogo del filtro viene visualizzata solo la stringa presente dopo le parole chiave WITH FILTER.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-154">If you create the filter expression by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Property** window and the **Expression** pane of the filter dialog box, you would see only the string that appears after the WITH FILTER keywords.</span></span> <span data-ttu-id="9f9b5-155">La definizione della struttura di data mining viene inclusa per semplificare e comprendere il tipo di colonna e l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-155">Here, the definition of the mining structure is included to make it easier to understand the column type and usage.</span></span>  
  
###  <a name="example-1-typical-case-level-filtering"></a><a name="bkmk_Ex1"></a> <span data-ttu-id="9f9b5-156">Esempio 1: Applicazione di filtri tipica a livello del case</span><span class="sxs-lookup"><span data-stu-id="9f9b5-156">Example 1: Typical Case-Level Filtering</span></span>  
 <span data-ttu-id="9f9b5-157">In questo esempio viene mostrato un semplice filtro che limita i case utilizzati nel modello ai clienti la cui occupazione è architetto e la cui età è superiore a 30 anni.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-157">This example shows a simple filter that restricts the cases used in the model to customers whose occupation is architect and whose age is over 30.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_1  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH FILTER (Age > 30 AND Occupation='Architect')  
```  
  

  
###  <a name="example-2-case-level-filtering-using-nested-table-attributes"></a><a name="bkmk_Ex2"></a> <span data-ttu-id="9f9b5-158">Esempio 2: Applicazione di filtri a livello del case utilizzando gli attributi delle tabelle nidificate</span><span class="sxs-lookup"><span data-stu-id="9f9b5-158">Example 2: Case-Level Filtering using Nested Table Attributes</span></span>  
 <span data-ttu-id="9f9b5-159">Se la struttura di data mining contiene tabelle nidificate, è possibile filtrare in base all'esistenza di un valore in una tabella nidificata o in base alle righe della tabella nidificata che contengono un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-159">If your mining structure contains nested tables, you can either filter on the existence of a value in a nested table, or filter on nested table rows that contain a specific value.</span></span> <span data-ttu-id="9f9b5-160">In questo esempio i case utilizzati per il modello vengono limitati ai clienti di età superiore ai 30 anni che hanno effettuato almeno un acquisto che include latte.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-160">This example restricts the cases used for the model to customers over the age of 30 who made at least one purchase that included milk.</span></span>  
  
 <span data-ttu-id="9f9b5-161">Come mostrato nell'esempio, non è necessario che il filtro utilizzi solo colonne incluse nel modello.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-161">As this example shows, it is not necessary that the filter use only columns that are included in the model.</span></span> <span data-ttu-id="9f9b5-162">La tabella annidata **Prodotti** fa parte della struttura di data mining, ma non è inclusa nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-162">The nested table **Products** is part of the mining structure, but is not included in the mining model.</span></span> <span data-ttu-id="9f9b5-163">Tuttavia, è ancora possibile filtrare in base a valori e attributi nella tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-163">However, you can still filter on values and attributes in the nested table.</span></span> <span data-ttu-id="9f9b5-164">Per visualizzare i dettagli di questi case, è necessario attivare il drill-through.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-164">To view the details of these cases, drillthrough must be enabled.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_2  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT  
)  
WITH DRILLTHROUGH,   
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk')  
)  
```  
  
 
  
###  <a name="example-3-case-level-filtering-on-multiple-nested-table-attributes"></a><a name="bkmk_Ex3"></a> <span data-ttu-id="9f9b5-165">Esempio 3: Applicazione di filtri a livello del case su più attributi delle tabelle nidificate</span><span class="sxs-lookup"><span data-stu-id="9f9b5-165">Example 3: Case-Level Filtering on Multiple Nested Table Attributes</span></span>  
 <span data-ttu-id="9f9b5-166">In questo esempio viene mostrato un filtro in tre parti: una condizione viene applicata alla tabella del case, un'altra a un attributo nella tabella nidificata e un'altra a un valore specifico in una delle colonne della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-166">This example shows a three-part filter: a condition applies to the case table, another condition to an attribute in the nested table, and another condition on a specific value in one of the nested table columns.</span></span>  
  
 <span data-ttu-id="9f9b5-167">La prima condizione nel filtro, `Age > 30`, si applica a una colonna nella tabella del case.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-167">The first condition in the filter, `Age > 30`, applies to a column in the case table.</span></span> <span data-ttu-id="9f9b5-168">Le altre condizioni vengono applicate alla tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-168">The remaining conditions apply to the nested table.</span></span>  
  
 <span data-ttu-id="9f9b5-169">La seconda condizione, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, verifica la presenza di almeno un acquisto nella tabella annidata che include il latte.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-169">The second condition, `EXISTS (SELECT * FROM Products WHERE ProductName='Milk'`, checks for the presence of at least one purchase in the nested table that included milk.</span></span> <span data-ttu-id="9f9b5-170">La terza condizione, `Quantity>=2`, indica che il cliente deve aver acquistato almeno due unità di latte in una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-170">The third condition, `Quantity>=2`, means that the customer must have purchased at least two units of milk in a single transaction.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_3  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
)  
)  
FILTER (Age > 30 AND EXISTS (SELECT * FROM Products WHERE ProductName='Milk'  AND Quantity >= 2)   
)  
```  
  

  
###  <a name="example-4-case-level-filtering-on-absence-of-nested-table-attributes"></a><a name="bkmk_Ex4"></a> <span data-ttu-id="9f9b5-171">Esempio 4: Applicazione di filtri a livello del case in assenza di attributi delle tabelle nidificate</span><span class="sxs-lookup"><span data-stu-id="9f9b5-171">Example 4: Case-Level Filtering On Absence of Nested Table Attributes</span></span>  
 <span data-ttu-id="9f9b5-172">In questo esempio viene illustrata la limitazione dei case ai clienti che non ha acquistato un articolo specifico, filtrando in base all'assenza di un attributo nella tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-172">This example shows how to limit cases to customer who did not purchase a specific item, by filtering on the absence of an attribute in the nested table.</span></span> <span data-ttu-id="9f9b5-173">In questo esempio, viene eseguito il training del modello utilizzando i clienti di età superiore ai 30 anni che non hanno mai comprato latte.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-173">In this example, the model is trained using customers over the age of 30 who have never bought milk.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_4  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName  
)  
)  
FILTER (Age > 30 AND NOT EXISTS (SELECT * FROM Products WHERE ProductName='Milk') )  
```  
  

  
###  <a name="example-5-filtering-on-multiple-nested-table-values"></a><a name="bkmk_Ex5"></a> <span data-ttu-id="9f9b5-174">Esempio 5: Applicazione di filtri su più valori delle tabelle nidificate</span><span class="sxs-lookup"><span data-stu-id="9f9b5-174">Example 5: Filtering on Multiple Nested Table Values</span></span>  
 <span data-ttu-id="9f9b5-175">Lo scopo dell'esempio è mostrare l'applicazione del filtro sulla tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-175">The purpose of the example is to show nested table filtering.</span></span> <span data-ttu-id="9f9b5-176">Il filtro della tabella nidificata viene applicato dopo il filtro del case e si limita solo alle righe della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-176">The nested table filter is applied after the case filter, and only restricts nested table rows.</span></span>  
  
 <span data-ttu-id="9f9b5-177">Questo modello può contenere più case con tabelle nidificate vuote perché EXISTS non è specificato.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-177">This model could contain multiple cases with empty nested tables because EXISTS is not specified.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_5  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
WITH DRILLTHROUGH  
```  
  

  
###  <a name="example-6-filtering-on-nested-table-attributes-and-exists"></a><a name="bkmk_Ex6"></a> <span data-ttu-id="9f9b5-178">Esempio 6: Applicazione di filtri in base agli attributi delle tabelle nidificate e alla clausola EXISTS</span><span class="sxs-lookup"><span data-stu-id="9f9b5-178">Example 6: Filtering on Nested Table Attributes and EXISTS</span></span>  
 <span data-ttu-id="9f9b5-179">In questo esempio, il filtro nella tabella nidificata limita le righe a quelle che contengono latte o acqua imbottigliata.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-179">In this example, the filter on the nested table restricts the rows to those that contain either milk or bottled water.</span></span> <span data-ttu-id="9f9b5-180">Quindi, i case nel modello vengono limitati utilizzando un'istruzione `EXISTS`.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-180">Then, the cases in the model are restricted by using an `EXISTS` statement.</span></span> <span data-ttu-id="9f9b5-181">Ciò assicura che la tabella nidificata non è vuota.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-181">This makes sure that the nested table is not empty.</span></span>  
  
```  
ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_6  
(  
CustomerId,  
Age,  
Occupation,  
MaritalStatus PREDICT,  
Products PREDICT  
(  
ProductName KEY,  
Quantity        
) WITH FILTER(ProductName='Milk' OR ProductName='bottled water')  
)  
FILTER (EXISTS (Products))  
```  
  

  
###  <a name="example-7-complex-filter-combinations"></a><a name="bkmk_Ex7"></a> <span data-ttu-id="9f9b5-182">Esempio 7: Combinazioni di filtri complessi</span><span class="sxs-lookup"><span data-stu-id="9f9b5-182">Example 7: Complex Filter Combinations</span></span>  
 <span data-ttu-id="9f9b5-183">Lo scenario per questo modello è simile a quello dell'esempio 4, ma è molto più complesso.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-183">The scenario for this model resembles that of Example 4, but is far more complex.</span></span> <span data-ttu-id="9f9b5-184">La tabella nidificata, **ProductsOnSale**, ha la condizione `(OnSale)` di filtro che indica che il valore di **OnSale** deve essere `true` per il prodotto elencato in **ProductName**.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-184">The nested table, **ProductsOnSale**, has the filter condition `(OnSale)` meaning that the value of **OnSale** must be `true` for the product listed in **ProductName**.</span></span> <span data-ttu-id="9f9b5-185">In questo caso, **OnSale** è una colonna della struttura.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-185">Here, **OnSale** is a structure column.</span></span>  
  
 <span data-ttu-id="9f9b5-186">La seconda parte del filtro, per **ProductsNotOnSale**, ripete questa sintassi, ma filtra i prodotti per i quali il valore di **OnSale** è `not true``(!OnSale)` .</span><span class="sxs-lookup"><span data-stu-id="9f9b5-186">The second part of the filter, for **ProductsNotOnSale**, repeats this syntax, but filters on products for which the value of **OnSale** is `not true``(!OnSale)`.</span></span>  
  
 <span data-ttu-id="9f9b5-187">Infine, le condizioni vengono combinate e viene aggiunta un'ulteriore restrizione alla tabella del case.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-187">Finally, the conditions are combined and one additional restriction is added to the case table.</span></span> <span data-ttu-id="9f9b5-188">Il risultato è la stima degli acquisti di prodotti nell'elenco **ProductsNotOnSale** , in base ai case inclusi nell'elenco **ProductsOnSale** , per tutti i clienti di età superiore ai 25 anni.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-188">The result is to predict purchases of products in the **ProductsNotOnSale** list, based on the cases that are included in the **ProductsOnSale** list, for all customers over the age of 25.</span></span>  
  
 `ALTER MINING STRUCTURE MyStructure  ADD MINING MODEL MyModel_7`  
  
 `(`  
  
 `CustomerId,`  
  
 `Age,`  
  
 `Occupation,`  
  
 `MaritalStatus,`  
  
 `ProductsOnSale`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(OnSale),`  
  
 `ProductsNotOnSale PREDICT ONLY`  
  
 `(`  
  
 `ProductName KEY`  
  
 `) WITH FILTER(!OnSale)`  
  
 `)`  
  
 `WITH DRILLTHROUGH,`  
  
 `FILTER (EXISTS (ProductsOnSale) AND EXISTS(ProductsNotOnSale) AND Age > 25)`  
  
  
  
###  <a name="example-8-filtering-on-dates"></a><a name="bkmk_Ex8"></a> <span data-ttu-id="9f9b5-189">Esempio 8: Filtri sulle date</span><span class="sxs-lookup"><span data-stu-id="9f9b5-189">Example 8: Filtering on Dates</span></span>  
 <span data-ttu-id="9f9b5-190">È possibile filtrare le colonne di input in base alle date, come per qualsiasi altro tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-190">You can filter input columns on dates, as you would any other data.</span></span> <span data-ttu-id="9f9b5-191">Le date contenute in una colonna di tipo data/ora sono valori continui; è quindi possibile specificare un intervallo di date utilizzando operatori quali maggiore di (>) o minore di (<).</span><span class="sxs-lookup"><span data-stu-id="9f9b5-191">Dates contained in a column of type date/time are continuous values; therefore, you can specify a date range by using operators such as greater than (>) or less than (<).</span></span> <span data-ttu-id="9f9b5-192">Se l'origine dati non rappresenta le date come tipo di dati Continuous, ma come valori discreti o di testo, non sarà possibile filtrare in base a un intervallo di date, ma sarà necessario specificare singoli valori discreti.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-192">If your data source does not represent dates by a Continuous data type, but as discrete or text values, you cannot filter on a date range, but must specify individual discrete values.</span></span>  
  
 <span data-ttu-id="9f9b5-193">Tuttavia, non è possibile creare un filtro sulla colonna delle date in un modello Time Series se la colonna delle date utilizzata per il filtro è anche la colonna chiave per il modello.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-193">However, you cannot create a filter on the date column in a time series model if the date column used for the filter is also the key column for the model.</span></span> <span data-ttu-id="9f9b5-194">Ciò accade perché nei modelli Time Series e Sequence Clustering la colonna delle date potrebbe essere gestita come tipo `KeyTime` o `KeySequence`.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-194">That is because, in time series models and sequence clustering models, the date column might be handled as type `KeyTime` or `KeySequence`.</span></span>  
  
 <span data-ttu-id="9f9b5-195">Quando è necessario applicare un filtro alle date continue in un modello Time Series, è possibile creare una copia della colonna nella struttura di data mining e filtrare il modello nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-195">If you need to filter on continuous dates in a time series model, you can create a copy of the column in the mining structure, and filter the model on the new column.</span></span>  
  
 <span data-ttu-id="9f9b5-196">L'espressione seguente, ad esempio, rappresenta un filtro applicato a una colonna delle date di tipo `Continuous` aggiunta al modello Forecasting.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-196">For example, the following expression represents a filter on a date column of type `Continuous` that has been added to the Forecasting model.</span></span>  
  
 `=[DateCopy] > '12:31:2003:00:00:00'`  
  
> [!NOTE]  
>  <span data-ttu-id="9f9b5-197">L'aggiunta di una qualsiasi colonna al modello può influire sui risultati.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-197">Note that any extra columns that you add to the model might affect the results.</span></span> <span data-ttu-id="9f9b5-198">Pertanto, se non si desidera che la colonna venga utilizzata nel calcolo della serie, sarà necessario aggiungere la colonna solo alla struttura di data mining e non al modello.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-198">Therefore, if you do not want the column to be used in computation of the series, you should add the column only to the mining structure, and not to the model.</span></span> <span data-ttu-id="9f9b5-199">È inoltre possibile impostare il flag del modello della colonna su `PredictOnly` o `Ignore`.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-199">You can also set the model flag on the column to `PredictOnly` or to `Ignore`.</span></span> <span data-ttu-id="9f9b5-200">Per altre informazioni, vedere [Flag di modellazione &#40;data mining&#41;](modeling-flags-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9f9b5-200">For more information, see [Modeling Flags &#40;Data Mining&#41;](modeling-flags-data-mining.md).</span></span>  
  
 <span data-ttu-id="9f9b5-201">Per altri tipi di modello, è possibile utilizzare le date come criteri di input o criteri di filtro come si farebbe per qualsiasi altra colonna.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-201">For other model types, you can use dates as input criteria or filter criteria just like you would in any other column.</span></span> <span data-ttu-id="9f9b5-202">Tuttavia, se è necessario utilizzare un livello di granularità specifico non supportato da un tipo di dati `Continuous`, sarà possibile creare un valore derivato nell'origine dati utilizzando delle espressioni per estrarre l'unità da utilizzare per filtri e analisi.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-202">However, if you need to use a specific level of granularity that is not supported by a `Continuous` data type, you can create a derived value in the data source by using expressions to extract the unit to use in filtering and analysis.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9f9b5-203">Quando si specificano le date come criteri di filtro, è necessario usare il formato seguente, indipendentemente dal formato di data del sistema operativo attualmente in uso: `mm/dd/yyyy`.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-203">When you specify a dates as filter criteria, you must use the following format, regardless of the date format for the current OS: `mm/dd/yyyy`.</span></span> <span data-ttu-id="9f9b5-204">Qualsiasi altro formato restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-204">Any other format results in an error.</span></span>  
  
 <span data-ttu-id="9f9b5-205">Se, ad esempio, si desidera filtrare i risultati del call center in modo da visualizzare solo i fine settimana, è possibile creare un'espressione nella vista origine dati che estragga il nome del giorno della settimana per ciascuna data e utilizzare quindi il valore del nome del giorno della settimana come input o come un valore discreto per i filtri.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-205">For example, if you want to filter your call center results to show only weekends, you can create an expression in the data source view that extracts the weekday name for each date, and then use that weekday name value for input or as a discrete value in filtering.</span></span> <span data-ttu-id="9f9b5-206">È sufficiente ricordare che la ripetizione dei valori può influire sul modello ed è quindi necessario utilizzare solo una delle colonne, non la colonna delle date insieme al valore derivato.</span><span class="sxs-lookup"><span data-stu-id="9f9b5-206">Just remember that repeating values can affect the model, so you should use only one of the columns, not the date column plus the derived value.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="9f9b5-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f9b5-207">See Also</span></span>  
 <span data-ttu-id="9f9b5-208">[Filtri per i modelli di data mining &#40;Analysis Services-&#41;di data mining](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9f9b5-208">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="9f9b5-209">Test e convalida &#40;Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="9f9b5-209">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
  
