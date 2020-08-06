---
title: Query MDX di base (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], SELECT statement
- queries [MDX], about queries
- cellsets [MDX]
- SELECT statement [MDX]
- cubes [Analysis Services], SELECT statement
ms.assetid: 4fa5a95a-fec9-4584-875c-dbf030c53e82
author: minewiskan
ms.author: owend
ms.openlocfilehash: b6b1a70753abe8e477bd1e522a37f4513cc12a52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635824"
---
# <a name="the-basic-mdx-query-mdx"></a><span data-ttu-id="917fc-102">Query MDX di base</span><span class="sxs-lookup"><span data-stu-id="917fc-102">The Basic MDX Query (MDX)</span></span>
  <span data-ttu-id="917fc-103">La query MDX (Multidimensional Expressions) di base è l'istruzione SELECT, ovvero la query utilizzata più di frequente in MDX.</span><span class="sxs-lookup"><span data-stu-id="917fc-103">The basic Multidimensional Expressions (MDX) query is the SELECT statement-the most frequently used query in MDX.</span></span> <span data-ttu-id="917fc-104">Se si conosce la sintassi dell'istruzione MDX SELECT, si sa creare una semplice query tramite questa istruzione e si capisce perché in un'istruzione SELECT è necessario specificare un set di risultati, si avrà la padronanza dell'utilizzo di MDX per l'esecuzione di query in dati multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="917fc-104">By understanding how an MDX SELECT statement must specify a result set, what the syntax of the SELECT statement is, and how to create a simple query using the SELECT statement, you will have a solid understanding of how to use MDX to query multidimensional data.</span></span>  
  
## <a name="specifying-a-result-set"></a><span data-ttu-id="917fc-105">Impostazione di un set di risultati</span><span class="sxs-lookup"><span data-stu-id="917fc-105">Specifying a Result Set</span></span>  
 <span data-ttu-id="917fc-106">In MDX l'istruzione SELECT specifica un set di risultati contenente un subset dei dati multidimensionali di un cubo che sono stati restituiti.</span><span class="sxs-lookup"><span data-stu-id="917fc-106">In MDX, the SELECT statement specifies a result set that contains a subset of multidimensional data that has been returned from a cube.</span></span> <span data-ttu-id="917fc-107">Per specificare un set di risultati, una query MDX deve contenere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="917fc-107">To specify a result set, an MDX query must contain the following information:</span></span>  
  
-   <span data-ttu-id="917fc-108">Numero di assi che devono essere inclusi nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="917fc-108">The number of axes that you want the result set to contain.</span></span> <span data-ttu-id="917fc-109">In una query MDX è possibile specificare un massimo di 128 assi.</span><span class="sxs-lookup"><span data-stu-id="917fc-109">You can specify up to 128 axes in an MDX query.</span></span>  
  
-   <span data-ttu-id="917fc-110">Set di membri o tuple da includere in ogni asse della query MDX.</span><span class="sxs-lookup"><span data-stu-id="917fc-110">The set of members or tuples to include on each axis of the MDX query.</span></span>  
  
-   <span data-ttu-id="917fc-111">Il nome del cubo che definisce il contesto della query MDX.</span><span class="sxs-lookup"><span data-stu-id="917fc-111">The name of the cube that sets the context of the MDX query.</span></span>  
  
-   <span data-ttu-id="917fc-112">Set di membri o tuple da includere nell'asse di sezionamento.</span><span class="sxs-lookup"><span data-stu-id="917fc-112">The set of members or tuples to include on the slicer axis.</span></span> <span data-ttu-id="917fc-113">Per altre informazioni sugli assi di sezionamento e della query, vedere [Restrizione della query con gli assi della query e di sezionamento &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span><span class="sxs-lookup"><span data-stu-id="917fc-113">For more information about slicer and query axes, see[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md).</span></span>  
  
 <span data-ttu-id="917fc-114">Per identificare gli assi della query, il cubo su cui verrà eseguita la query e l'asse di sezionamento, l'istruzione MDX deve utilizzare le clausole seguenti:</span><span class="sxs-lookup"><span data-stu-id="917fc-114">To identify the query axes, the cube that will be queried, and the slicer axis, the MDX SELECT statement uses the following clauses:</span></span>  
  
-   <span data-ttu-id="917fc-115">Clausola SELECT che determina gli assi della query di un'istruzione MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="917fc-115">A SELECT clause that determines the query axes of an MDX SELECT statement.</span></span> <span data-ttu-id="917fc-116">Per altre informazioni sulla formulazione degli assi della query in una clausola SELECT, vedere [Impostazione del contenuto di un asse della query &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="917fc-116">For more information about the construction of query axes in a SELECT clause, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="917fc-117">Clausola FROM che determina il cubo su cui eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="917fc-117">A FROM clause that determines which cube will be queried.</span></span> <span data-ttu-id="917fc-118">Per altre informazioni sulla clausola FROM, vedere [Istruzione SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="917fc-118">For more information about the FROM clause, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
-   <span data-ttu-id="917fc-119">Clausola WHERE facoltativa che determina i membri o le tuple da utilizzare nell'asse di sezionamento per limitare i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="917fc-119">An optional WHERE clause that determines which members or tuples to use on the slicer axis to restrict the data returned.</span></span> <span data-ttu-id="917fc-120">Per altre informazioni sulla formulazione di un asse di sezionamento in una clausola WHERE, vedere [Impostazione del contenuto di un asse di sezionamento &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="917fc-120">For more information about the construction of a slicer axis in a WHERE clause, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="917fc-121">Per altre informazioni sulle varie clausole dell'istruzione SELECT, vedere [Istruzione SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="917fc-121">For more detailed information about the various clauses of the SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="select-statement-syntax"></a><span data-ttu-id="917fc-122">Sintassi dell'istruzione SELECT</span><span class="sxs-lookup"><span data-stu-id="917fc-122">SELECT Statement Syntax</span></span>  
 <span data-ttu-id="917fc-123">La sintassi seguente illustra un'istruzione SELECT di base in cui sono specificate le clausole SELECT, FROM e WHERE:</span><span class="sxs-lookup"><span data-stu-id="917fc-123">The following syntax shows a basic SELECT statement that includes the use of the SELECT, FROM, and WHERE clauses:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ]   
SELECT [ * | ( <SELECT query axis clause>   
    [ , <SELECT query axis clause> ... ] ) ]  
FROM <SELECT subcube clause>   
[ <SELECT slicer axis clause> ]  
[ <SELECT cell property list clause> ]  
```  
  
 <span data-ttu-id="917fc-124">L'istruzione MDX SELECT supporta sintassi facoltativa, ad esempio la parola chiave WITH, l'utilizzo di funzioni MDX per la creazione di membri calcolati per l'inclusione di un asse o un asse di sezionamento e la restituzione dei valori di proprietà di celle specifiche come parte della query.</span><span class="sxs-lookup"><span data-stu-id="917fc-124">The MDX SELECT statement supports optional syntax, such as the WITH keyword, the use of MDX functions to create calculated members for inclusion in an axis or slicer axis, and the ability to return the values of specific cell properties as part of the query.</span></span> <span data-ttu-id="917fc-125">Per altre informazioni sull'istruzione MDX SELECT, vedere [Istruzione SELECT &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="917fc-125">For more information about the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
### <a name="comparing-the-syntax-of-the-mdx-select-statement-to-sql"></a><span data-ttu-id="917fc-126">Confronto tra la sintassi dell'istruzione MDX SELECT e SQL</span><span class="sxs-lookup"><span data-stu-id="917fc-126">Comparing the Syntax of the MDX SELECT Statement to SQL</span></span>  
 <span data-ttu-id="917fc-127">Il formato della sintassi di un'istruzione MDX SELECT è simile alla sintassi SQL.</span><span class="sxs-lookup"><span data-stu-id="917fc-127">The syntax format for the MDX SELECT statement is similar to that of SQL syntax.</span></span> <span data-ttu-id="917fc-128">Sussistono tuttavia diverse differenze essenziali:</span><span class="sxs-lookup"><span data-stu-id="917fc-128">However, there are several fundamental differences:</span></span>  
  
-   <span data-ttu-id="917fc-129">La sintassi MDX distingue i set circondando le tuple o i membri tra parentesi graffe (caratteri {e}). Per ulteriori informazioni sulla sintassi di membri, Tuple e set, vedere [utilizzo di membri, Tuple e set &#40;&#41;MDX ](working-with-members-tuples-and-sets-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="917fc-129">MDX syntax distinguishes sets by surrounding tuples or members with braces (the { and } characters.) For more information about member, tuple, and set syntax, see [Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md).</span></span>  
  
-   <span data-ttu-id="917fc-130">Le query MDX possono includere 0, 1, 2 e fino a 128 assi della query nell'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="917fc-130">MDX queries can have 0, 1, 2 or up to 128 query axes in the SELECT statement.</span></span> <span data-ttu-id="917fc-131">Ciascun asse si comporta esattamente allo stesso modo, a differenza di SQL in cui sussistono differenze significative tra il comportamento delle righe e il comportamento delle colonne di una query.</span><span class="sxs-lookup"><span data-stu-id="917fc-131">Each axis behaves in exactly the same way, unlike SQL where there are significant differences between how the rows and the columns of a query behave.</span></span>  
  
-   <span data-ttu-id="917fc-132">In modo analogo a una query SQL, la clausola FROM indica l'origine dei dati per la query MDX.</span><span class="sxs-lookup"><span data-stu-id="917fc-132">As with an SQL query, the FROM clause names the source of the data for the MDX query.</span></span> <span data-ttu-id="917fc-133">La clausola FROM di MDX tuttavia è limitata a un solo cubo.</span><span class="sxs-lookup"><span data-stu-id="917fc-133">However, the MDX FROM clause is restricted to a single cube.</span></span> <span data-ttu-id="917fc-134">Le informazioni di altri cubi possono essere recuperate per singoli valori tramite la funzione LookupCube.</span><span class="sxs-lookup"><span data-stu-id="917fc-134">Information from other cubes can be retrieved on a value-by-value basis by using the LookupCube function.</span></span>  
  
-   <span data-ttu-id="917fc-135">La clausola WHERE descrive l'asse di sezionamento in una query MDX</span><span class="sxs-lookup"><span data-stu-id="917fc-135">The WHERE clause describes the slicer axis in an MDX query.</span></span> <span data-ttu-id="917fc-136">e opera come un asse aggiuntivo invisibile nella query, sezionando i valori visualizzati nelle celle nel set di risultati. Diversamente dalla clausola SQL WHERE, questa clausola non influisce direttamente su quanto visualizzato nell'asse delle righe della query.</span><span class="sxs-lookup"><span data-stu-id="917fc-136">It acts as something like an invisible, extra axis in the query, slicing the values that appear in the cells in the result set; unlike the SQL WHERE clause it does not directly affect what appears on the rows axis of the query.</span></span> <span data-ttu-id="917fc-137">La funzionalità della clausola SQL WHERE è disponibile tramite altre funzioni MDX, ad esempio la funzione FILTER.</span><span class="sxs-lookup"><span data-stu-id="917fc-137">The functionality of the SQL WHERE clause is available through other MDX functions such as the FILTER function.</span></span>  
  
## <a name="select-statement-example"></a><span data-ttu-id="917fc-138">Esempio di istruzione SELECT</span><span class="sxs-lookup"><span data-stu-id="917fc-138">SELECT Statement Example</span></span>  
 <span data-ttu-id="917fc-139">Nell'esempio seguente viene illustrata una query MDX di base in cui è utilizzata l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="917fc-139">The following example shows a basic MDX query that uses the SELECT statement.</span></span> <span data-ttu-id="917fc-140">Questa query restituisce un set di risultati contenente le vendite e le imposte relative agli anni 2002 e 2003 per le aree di vendita della zona sudoccidentale.</span><span class="sxs-lookup"><span data-stu-id="917fc-140">This query returns a result set that contains the 2002 and 2003 sales and tax amounts for the Southwest sales territories.</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON COLUMNS,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON ROWS  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="917fc-141">Nell'esempio la query definisce le informazioni del set di risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="917fc-141">In this example, the query defines the following result set information:</span></span>  
  
-   <span data-ttu-id="917fc-142">La clausola SELECT imposta le assi della query come membri Sales Amount e Tax Amount della dimensione Measures e i membri 2002 e 2003 della dimensione Date.</span><span class="sxs-lookup"><span data-stu-id="917fc-142">The SELECT clause sets the query axes as the Sales Amount and Tax Amount members of the Measures dimension, and the 2002 and 2003 members of the Date dimension.</span></span>  
  
-   <span data-ttu-id="917fc-143">La clausola FROM indica che l'origine dei dati è il cubo Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="917fc-143">The FROM clause indicates that the data source is the Adventure Works cube.</span></span>  
  
-   <span data-ttu-id="917fc-144">La clausola WHERE definisce l'asse di sezionamento come membro Southwest della dimensione Sales Territory.</span><span class="sxs-lookup"><span data-stu-id="917fc-144">The WHERE clause defines the slicer axis as the Southwest member of the Sales Territory dimension.</span></span>  
  
 <span data-ttu-id="917fc-145">Si noti che nella query di esempio sono utilizzati anche gli alias di asse COLUMNS e ROWS.</span><span class="sxs-lookup"><span data-stu-id="917fc-145">Notice that the query example also uses the COLUMNS and ROWS axis aliases.</span></span> <span data-ttu-id="917fc-146">In alternativa è possibile specificare la posizione ordinale degli assi.</span><span class="sxs-lookup"><span data-stu-id="917fc-146">The ordinal positions for these axes could also have been used.</span></span> <span data-ttu-id="917fc-147">Nell'esempio seguente viene illustrata la stessa query MDX in cui è tuttavia specificata la posizione ordinale dei vari assi:</span><span class="sxs-lookup"><span data-stu-id="917fc-147">The following example shows how the MDX query could have been written to use the ordinal position of each axis:</span></span>  
  
```  
SELECT  
    { [Measures].[Sales Amount],   
        [Measures].[Tax Amount] } ON 0,  
    { [Date].[Fiscal].[Fiscal Year].&[2002],   
        [Date].[Fiscal].[Fiscal Year].&[2003] } ON 1  
FROM [Adventure Works]  
WHERE ( [Sales Territory].[Southwest] )  
```  
  
 <span data-ttu-id="917fc-148">Per esempi più dettagliati, vedere [Impostazione del contenuto di un asse della query &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)e [Impostazione del contenuto di un asse di sezionamento &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="917fc-148">For more detailed examples, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)and [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="917fc-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="917fc-149">See Also</span></span>  
 <span data-ttu-id="917fc-150">[Concetti chiave di MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="917fc-150">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 [<span data-ttu-id="917fc-151">Istruzione SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="917fc-151">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
