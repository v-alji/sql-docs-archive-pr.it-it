---
title: Convenzioni per la combinazione di condizioni di ricerca nel riquadro Criteri (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], combining
- precedence [SQL Server], Criteria pane
- search criteria [SQL Server], combining conditions
- multiple OR clauses
- combining search conditions
- OR operator
- AND, Criteria pane
- multiple AND clauses
ms.assetid: d4859be5-ff5b-48b2-a101-ad40c6dbcc68
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684521baa87d5325366a0e18296cd35342a0e947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711487"
---
# <a name="conventions-for-combining-search-conditions-in-the-criteria-pane-visual-database-tools"></a><span data-ttu-id="12d74-102">Convenzioni per la combinazione delle condizioni di ricerca nel riquadro Criteri (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="12d74-102">Conventions for Combining Search Conditions in the Criteria Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="12d74-103">È possibile creare query con qualsiasi numero di condizioni di ricerca, collegate con qualsiasi numero di operatori AND e OR.</span><span class="sxs-lookup"><span data-stu-id="12d74-103">You can create queries that include any number of search conditions, linked with any number of AND and OR operators.</span></span> <span data-ttu-id="12d74-104">Poiché una query con una combinazione di clausole AND e OR può diventare complessa, è utile capire come viene interpretata durante la sua esecuzione e come viene rappresentata nel [riquadro Criteri](visual-database-tools.md) e nel [riquadro SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12d74-104">A query with a combination of AND and OR clauses can become complex, so it is helpful to understand how such a query is interpreted when you execute it, and how such a query is represented in the [Criteria Pane](visual-database-tools.md) and [SQL Pane](sql-pane-visual-database-tools.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12d74-105">Per altre informazioni sulle condizioni di ricerca che contengono solo un operatore AND o OR, vedere [Definizione di più condizioni di ricerca per una sola colonna &#40;Visual Database Tools &#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) e [Definizione di più condizioni di ricerca per più colonne &#40;Visual Database Tools &#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12d74-105">For details about search conditions that contain only one AND or OR operator, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md) and [Specify Multiple Search Conditions for Multiple Columns &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-multiple-columns-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="12d74-106">Più avanti sarà possibile reperire informazioni relative a:</span><span class="sxs-lookup"><span data-stu-id="12d74-106">Below you will find information about:</span></span>  
  
-   <span data-ttu-id="12d74-107">Precedenza di AND e OR nelle query in cui sono presenti entrambi.</span><span class="sxs-lookup"><span data-stu-id="12d74-107">The precedence of AND and OR in queries that contain both.</span></span>  
  
-   <span data-ttu-id="12d74-108">Modo in cui le condizioni nelle clausole AND e OR stabiliscono una relazione logica reciproca.</span><span class="sxs-lookup"><span data-stu-id="12d74-108">How the conditions in AND and OR clauses relate logically to one another.</span></span>  
  
-   <span data-ttu-id="12d74-109">Modo in cui le query che contengono AND e OR vengono rappresentate in Progettazione query e Progettazione viste nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="12d74-109">How the Query and View Designer represents in the Criteria Pane queries that contain both AND and OR.</span></span>  
  
 <span data-ttu-id="12d74-110">Per semplificare la comprensione degli argomenti illustrati di seguito, si supponga di utilizzare una tabella `employee` che contiene le colonne `hire_date`, `job_lvl`e `status`.</span><span class="sxs-lookup"><span data-stu-id="12d74-110">To help you understand the discussion below, imagine that you are working with an `employee` table containing the columns `hire_date`, `job_lvl`, and `status`.</span></span> <span data-ttu-id="12d74-111">Negli esempi si ipotizza la necessità di ottenere informazioni sull'anzianità di servizio dei dipendenti (ovvero la data di assunzione di un dipendente), sul tipo di mansione svolta da un dipendente (il livello dell'attività) e sullo stato del dipendente (ad esempio se è in pensione).</span><span class="sxs-lookup"><span data-stu-id="12d74-111">The examples assume that you need to know information such as how long an employee has worked with the company (that is, what the employee's hire date is), what type of job the employee performs (what the job level is), and the employee's status (for example, retired).</span></span>  
  
## <a name="precedence-of-and-and-or"></a><span data-ttu-id="12d74-112">Precedenza di AND e OR</span><span class="sxs-lookup"><span data-stu-id="12d74-112">Precedence of AND and OR</span></span>  
 <span data-ttu-id="12d74-113">Quando viene eseguita una query, in primo luogo vengono valutate le clausole collegate con l'operatore AND e quindi quelle collegate con OR.</span><span class="sxs-lookup"><span data-stu-id="12d74-113">When a query is executed, it evaluates first the clauses linked with AND, and then those linked with OR.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12d74-114">L'operatore NOT ha la precedenza sia rispetto a AND che rispetto a OR.</span><span class="sxs-lookup"><span data-stu-id="12d74-114">The NOT operator takes precedence over both AND and OR.</span></span>  
  
 <span data-ttu-id="12d74-115">Per trovare, ad esempio, i dipendenti assunti da oltre cinque anni in attività di basso livello o dipendenti con un livello di attività intermedio indipendentemente dalla data di assunzione, è possibile costruire una clausola WHERE come la seguente:</span><span class="sxs-lookup"><span data-stu-id="12d74-115">For example, to find either employees who have been with the company for more than five years in lower-level jobs or employees with middle-level jobs without regard for their hire date, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   job_lvl = 100 OR  
   job_lvl = 200  
  
```  
  
 <span data-ttu-id="12d74-116">Per modificare la precedenza predefinita dell'operatore AND rispetto all'operatore OR, è possibile delimitare con parentesi specifiche condizioni nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="12d74-116">To override the default precedence of AND over OR, you can put parentheses around specific conditions in the SQL pane.</span></span> <span data-ttu-id="12d74-117">Le condizioni fra parentesi vengono sempre valutate per prime.</span><span class="sxs-lookup"><span data-stu-id="12d74-117">Conditions in parentheses are always evaluated first.</span></span> <span data-ttu-id="12d74-118">Per trovare, ad esempio, tutti i dipendenti che appartengono a una società da oltre cinque anni con livello di attività basso o intermedio, è possibile costruire una clausola WHERE come la seguente:</span><span class="sxs-lookup"><span data-stu-id="12d74-118">For example, to find all employees who have been with the company more than five years in either lower or middle-level jobs, you can construct a WHERE clause such as the following:</span></span>  
  
```  
WHERE   
   hire_date < '01/01/95' AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
> [!TIP]  
>  <span data-ttu-id="12d74-119">Per questioni di chiarezza, è sempre consigliabile inserire parentesi quando si combinano clausole AND e OR invece di fare semplicemente affidamento sulla precedenza predefinita.</span><span class="sxs-lookup"><span data-stu-id="12d74-119">It is recommended that, for clarity, you always include parentheses when combining AND and OR clauses instead of relying on the default precedence.</span></span>  
  
## <a name="how-and-works-with-multiple-or-clauses"></a><span data-ttu-id="12d74-120">Funzionamento di AND con più clausole OR</span><span class="sxs-lookup"><span data-stu-id="12d74-120">How AND Works with Multiple OR Clauses</span></span>  
 <span data-ttu-id="12d74-121">La comprensione dei modi di correlazione delle clausole AND e OR combinate può risultare di aiuto nella costruzione e comprensione di query complesse in Progettazione query e Progettazione viste.</span><span class="sxs-lookup"><span data-stu-id="12d74-121">Understanding how AND and OR clauses are related when combined can help you construct and understand complex queries in the Query and View Designer.</span></span>  
  
 <span data-ttu-id="12d74-122">Se vengono collegate più condizioni con AND, il primo set di condizioni collegato con AND viene applicato a tutte le condizioni nel secondo set.</span><span class="sxs-lookup"><span data-stu-id="12d74-122">If you link multiple conditions using AND, the first set of conditions linked with AND applies to all the conditions in the second set.</span></span> <span data-ttu-id="12d74-123">In altri termini, una condizione collegata con AND a un'altra condizione viene distribuita a tutte le condizioni nel secondo set.</span><span class="sxs-lookup"><span data-stu-id="12d74-123">In other words, a condition linked with AND to another condition is distributed to all the conditions in the second set.</span></span> <span data-ttu-id="12d74-124">La seguente rappresentazione schematica mostra, ad esempio, una condizione AND collegata a un set di condizioni OR:</span><span class="sxs-lookup"><span data-stu-id="12d74-124">For example, the following schematic representation shows an AND condition linked to a set of OR conditions:</span></span>  
  
```  
A AND (B OR C)  
```  
  
 <span data-ttu-id="12d74-125">La precedente rappresentazione è logicamente equivalente alla seguente rappresentazione schematica, che mostra come la condizione AND viene distribuita nel secondo set di condizioni:</span><span class="sxs-lookup"><span data-stu-id="12d74-125">The representation above is logically equivalent to the following schematic representation, which shows how the AND condition is distributed to the second set of conditions:</span></span>  
  
```  
(A AND B) OR (A AND C)  
```  
  
 <span data-ttu-id="12d74-126">Questo principio di distribuzione influisce sull'utilizzo di Progettazione query e Progettazione viste.</span><span class="sxs-lookup"><span data-stu-id="12d74-126">This distributive principle affects how you use the Query and View Designer.</span></span> <span data-ttu-id="12d74-127">Si supponga, ad esempio, di dover cercare tutti i dipendenti assunti da oltre cinque anni con livello di attività basso o intermedio.</span><span class="sxs-lookup"><span data-stu-id="12d74-127">For example, imagine that you are looking for all employees who have been with the company more than five years in either lower or middle-level jobs.</span></span> <span data-ttu-id="12d74-128">È possibile immettere la seguente clausola WHERE nell'istruzione nel riquadro SQL:</span><span class="sxs-lookup"><span data-stu-id="12d74-128">You enter the following WHERE clause into the statement in the SQL pane:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
   (job_lvl = 100 OR job_lvl = 200)  
```  
  
 <span data-ttu-id="12d74-129">La clausola collegata con AND si applica a entrambe le clausole collegate con OR.</span><span class="sxs-lookup"><span data-stu-id="12d74-129">The clause linked with AND applies to both clauses linked with OR.</span></span> <span data-ttu-id="12d74-130">Un modo esplicito per esprimere tale istruzione consiste nel ripetere la condizione AND per ogni condizione nella clausola OR.</span><span class="sxs-lookup"><span data-stu-id="12d74-130">An explicit way to express this is to repeat the AND condition once for each condition in the OR clause.</span></span> <span data-ttu-id="12d74-131">La seguente istruzione è più esplicita (e lunga) rispetto all'istruzione precedente, ma è logicamente equivalente:</span><span class="sxs-lookup"><span data-stu-id="12d74-131">The following statement is more explicit (and longer) than the previous statement, but is logically equivalent to it:</span></span>  
  
```  
WHERE    (hire_date < '01/01/95' ) AND  
  (job_lvl = 100) OR   
  (hire_date < '01/01/95' ) AND   
  (job_lvl = 200)  
```  
  
 <span data-ttu-id="12d74-132">Il principio di distribuzione delle clausole AND alle clausole OR collegate si applica indipendentemente dal numero di condizioni interessate.</span><span class="sxs-lookup"><span data-stu-id="12d74-132">The principle of distributing AND clauses to linked OR clauses applies no matter how many individual conditions are involved.</span></span> <span data-ttu-id="12d74-133">Si supponga, ad esempio, di voler trovare i dipendenti di livello superiore o intermedio assunti da oltre cinque anni o che sono in pensione.</span><span class="sxs-lookup"><span data-stu-id="12d74-133">For example, imagine that you want to find higher or middle-level employees who have been with the company more than five years or are retired.</span></span> <span data-ttu-id="12d74-134">La clausola WHERE potrebbe essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="12d74-134">The WHERE clause might look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 OR job_lvl = 300) AND  
   (hire_date < '01/01/95' ) OR (status = 'R')  
```  
  
 <span data-ttu-id="12d74-135">Una volta distribuite le condizioni collegate con AND, la clausola WHERE assumerà questo aspetto:</span><span class="sxs-lookup"><span data-stu-id="12d74-135">After the conditions linked with AND have been distributed, the WHERE clause will look like this:</span></span>  
  
```  
WHERE   
   (job_lvl = 200 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 200 AND status = 'R') OR  
   (job_lvl = 300 AND hire_date < '01/01/95' ) OR  
   (job_lvl = 300 AND status = 'R')   
```  
  
## <a name="how-multiple-and-and-or-clauses-are-represented-in-the-criteria-pane"></a><span data-ttu-id="12d74-136">Rappresentazione di più clausole AND e OR nel riquadro Criteri</span><span class="sxs-lookup"><span data-stu-id="12d74-136">How Multiple AND and OR Clauses Are Represented in the Criteria Pane</span></span>  
 <span data-ttu-id="12d74-137">Le condizioni di ricerca vengono rappresentate nel [riquadro Criteri](visual-database-tools.md)di Progettazione query e Progettazione viste.</span><span class="sxs-lookup"><span data-stu-id="12d74-137">The Query and View Designer represents your search conditions in the [Criteria Pane](visual-database-tools.md).</span></span> <span data-ttu-id="12d74-138">In alcuni casi che riguardano più clausole collegate con AND e OR tuttavia la rappresentazione nel riquadro Criteri potrebbe risultare diversa da quella desiderata.</span><span class="sxs-lookup"><span data-stu-id="12d74-138">However, in some cases that involve multiple clauses linked with AND and OR, the representation in the Criteria Pane might not be what you expect.</span></span> <span data-ttu-id="12d74-139">Inoltre, se si modifica una query nel riquadro Criteri o nel [riquadro Diagramma](diagram-pane-visual-database-tools.md), si potrebbe notare che l'istruzione SQL è diversa rispetto a quella specificata.</span><span class="sxs-lookup"><span data-stu-id="12d74-139">In addition, if you modify your query in the Criteria Pane or [Diagram Pane](diagram-pane-visual-database-tools.md), you might find that your SQL statement has been changed from what you entered.</span></span>  
  
 <span data-ttu-id="12d74-140">In generale, queste regole determinano il modo in cui le clausole AND e OR vengono visualizzate nel riquadro Criteri:</span><span class="sxs-lookup"><span data-stu-id="12d74-140">In general, these rules dictate how AND and OR clauses appear in the Criteria Pane:</span></span>  
  
-   <span data-ttu-id="12d74-141">Tutte le condizioni collegate con AND vengono visualizzate nella colonna **Filtro** della griglia o nella stessa colonna **Or...** .</span><span class="sxs-lookup"><span data-stu-id="12d74-141">All conditions linked with AND appear in the **Filter** grid column or in the same **Or...** column.</span></span>  
  
-   <span data-ttu-id="12d74-142">Tutte le condizioni collegate con OR vengono visualizzate in colonne **Or...** separate.</span><span class="sxs-lookup"><span data-stu-id="12d74-142">All conditions linked with OR appear in separate **Or...** columns.</span></span>  
  
-   <span data-ttu-id="12d74-143">Se il risultato logico di una combinazione di clausole AND e OR è che la clausola AND viene distribuita in più clausole OR, nel riquadro Criteri questa situazione viene rappresentata in modo esplicito ripetendo la clausola AND il numero di volte necessario.</span><span class="sxs-lookup"><span data-stu-id="12d74-143">If the logical result of a combination of AND and OR clauses is that the AND is distributed into several OR clauses, the Criteria Pane represents this explicitly by repeating the AND clause as many times as necessary.</span></span>  
  
 <span data-ttu-id="12d74-144">Nel riquadro SQL si potrebbe creare, ad esempio, una condizione di ricerca come la seguente, in cui due clausole collegate con AND hanno la precedenza rispetto alla terza collegata con OR:</span><span class="sxs-lookup"><span data-stu-id="12d74-144">For example, in the SQL pane you might create a search condition such as the following, in which two clauses linked with AND take precedence over a third one linked with OR:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  (job_lvl = 100) OR   
  (status = 'R')  
```  
  
 <span data-ttu-id="12d74-145">In Progettazione query e Progettazione viste questa clausola WHERE viene rappresentata nel riquadro Criteri come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="12d74-145">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="12d74-146">![Precedenza della clausola OR nel riquadro Criteri](../../database-engine/media//vs-criteriapane1.gif "Precedenza della clausola OR nel riquadro Criteri")</span><span class="sxs-lookup"><span data-stu-id="12d74-146">![OR clause precedence in the Criteria Pane](../../database-engine/media//vs-criteriapane1.gif "OR clause precedence in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="12d74-147">Tuttavia, se la clausola OR collegata ha la precedenza rispetto a una clausola AND, la clausola AND viene ripetuta per ogni clausola OR.</span><span class="sxs-lookup"><span data-stu-id="12d74-147">However, if the linked OR clauses take precedence over an AND clause, the AND clause is repeated for each OR clause.</span></span> <span data-ttu-id="12d74-148">In questo modo la clausola AND viene distribuita per ogni clausola OR.</span><span class="sxs-lookup"><span data-stu-id="12d74-148">This causes the AND clause to be distributed to each OR clause.</span></span> <span data-ttu-id="12d74-149">Nel riquadro SQL si potrebbe creare ad esempio una clausola WHERE come la seguente:</span><span class="sxs-lookup"><span data-stu-id="12d74-149">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ( (job_lvl = 100) OR   
  (status = 'R') )  
```  
  
 <span data-ttu-id="12d74-150">In Progettazione query e Progettazione viste questa clausola WHERE viene rappresentata nel riquadro Criteri come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="12d74-150">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="12d74-151">![Più clausole AND e OR nel riquadro Criteri](../../database-engine/media//vs-criteriapane2.gif "Più clausole AND e OR nel riquadro Criteri")</span><span class="sxs-lookup"><span data-stu-id="12d74-151">![Multiple AND and OR clauses in the Criteria Pane](../../database-engine/media//vs-criteriapane2.gif "Multiple AND and OR clauses in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="12d74-152">Se le clausole OR collegate interessano soltanto una colonna di dati, Progettazione query e Progettazione viste consentono di inserire l'intera clausola OR in una singola cella della griglia, eliminando la necessità di ripetere la clausola AND.</span><span class="sxs-lookup"><span data-stu-id="12d74-152">If the linked OR clauses involve only one data column, the Query and View Designer can place the entire OR clause into a single cell of the grid, avoiding the need to repeat the AND clause.</span></span> <span data-ttu-id="12d74-153">Nel riquadro SQL si potrebbe creare ad esempio una clausola WHERE come la seguente:</span><span class="sxs-lookup"><span data-stu-id="12d74-153">For example, in the SQL pane you might create a WHERE clause such as the following:</span></span>  
  
```  
WHERE (hire_date < '01/01/95' ) AND   
  ((status = 'R') OR (status = 'A'))  
```  
  
 <span data-ttu-id="12d74-154">In Progettazione query e Progettazione viste questa clausola WHERE viene rappresentata nel riquadro Criteri come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="12d74-154">The Query and View Designer represents this WHERE clause in the Criteria Pane as follows:</span></span>  
  
 <span data-ttu-id="12d74-155">![Clausole OR collegate definite nel riquadro dei criteri](../../database-engine/media//vs-criteriapane3.gif "Clausole OR collegate definite nel riquadro dei criteri")</span><span class="sxs-lookup"><span data-stu-id="12d74-155">![Linked OR clauses defined in the Criteria Pane](../../database-engine/media//vs-criteriapane3.gif "Linked OR clauses defined in the Criteria Pane")</span></span>  
  
 <span data-ttu-id="12d74-156">Se si apporta una modifica alla query, ad esempio modificando uno dei valori nel riquadro Criteri, in Progettazione query e Progettazione viste l'istruzione SQL verrà ricreata nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="12d74-156">If you make a change to the query (such as changing one of the values in the Criteria Pane), the Query and View Designer recreates the SQL statement in the SQL pane.</span></span> <span data-ttu-id="12d74-157">L'istruzione SQL ricreata sarà analoga alla visualizzazione del riquadro Criteri invece che all'istruzione originaria.</span><span class="sxs-lookup"><span data-stu-id="12d74-157">The recreated SQL statement will resemble the Criteria Pane display rather than your original statement.</span></span> <span data-ttu-id="12d74-158">Se ad esempio il riquadro Criteri contiene clausole AND distribuite, l'istruzione risultante nel riquadro SQL verrà ricreata con clausole AND distribuite esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="12d74-158">For example, if the Criteria Pane contains distributed AND clauses, the resulting statement in the SQL pane will be recreated with explicit distributed AND clauses.</span></span> <span data-ttu-id="12d74-159">Per ulteriori informazioni, tornare a "Funzionamento di AND con più clausole OR" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="12d74-159">For details, see "How AND Works with Multiple OR Clauses" earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d74-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12d74-160">See Also</span></span>  
 [<span data-ttu-id="12d74-161">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="12d74-161">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
