---
title: Informazioni sull'ordine di valutazione e di valutazione (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- evaluation order [MDX]
- calculation order [MDX]
- SOLVE_ORDER property
- queries [MDX], solve orders
- solve orders [MDX]
- pass orders [MDX]
- expressions [MDX], solve orders
ms.assetid: 7ed7d4ee-4644-4c5d-99a4-c4b429d0203c
author: minewiskan
ms.author: owend
ms.openlocfilehash: d92ccd9d1eeb05272a95c6f429f8c756bcb0022e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627443"
---
# <a name="understanding-pass-order-and-solve-order-mdx"></a><span data-ttu-id="1e56d-102">Informazioni sull'ordine di calcolo e di valutazione (MDX)</span><span class="sxs-lookup"><span data-stu-id="1e56d-102">Understanding Pass Order and Solve Order (MDX)</span></span>
  <span data-ttu-id="1e56d-103">L'operazione di calcolo di un cubo, risultante da uno script MDX, può essere suddivisa in numerose fasi di calcolo a seconda dell'utilizzo delle varie funzionalità correlate ai calcoli.</span><span class="sxs-lookup"><span data-stu-id="1e56d-103">When a cube is calculated as the result of an MDX script, it can go through many stages of computation depending on the use of various calculation-related features.</span></span> <span data-ttu-id="1e56d-104">Ognuna di queste fasi viene indicata come sessione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="1e56d-104">Each of these stages is referred to as a calculation pass.</span></span>  
  
 <span data-ttu-id="1e56d-105">Per fare riferimento a una sessione di calcolo è possibile specificare una posizione ordinale, denominata numero della sessione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="1e56d-105">A calculation pass can be referred to by an ordinal position, called the calculation pass number.</span></span> <span data-ttu-id="1e56d-106">Il numero di sessioni di calcolo necessario per elaborare completamente tutte le celle di un cubo è noto come livello di nidificazione della sessione di calcolo del cubo.</span><span class="sxs-lookup"><span data-stu-id="1e56d-106">The count of calculation passes that are required to fully compute all the cells of a cube is referred to as the calculation pass depth of the cube.</span></span>  
  
 <span data-ttu-id="1e56d-107">I dati writeback e delle tabelle dei fatti influiscono solo sulla sessione 0.</span><span class="sxs-lookup"><span data-stu-id="1e56d-107">Fact table and writeback data only impact pass 0.</span></span> <span data-ttu-id="1e56d-108">Gli script popolano i dati dopo la sessione 0. Per ogni istruzione di assegnazione e calcolo in uno script viene creata una nuova sessione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="1e56d-108">Scripts populate data after pass 0; each assignment and calculate statement in a script creates a new pass.</span></span> <span data-ttu-id="1e56d-109">Esternamente allo script MDX, i riferimenti alla sessione assoluta 0 si riferiscono all'ultima sessione creata dallo script per il cubo.</span><span class="sxs-lookup"><span data-stu-id="1e56d-109">Outside the MDX script, references to absolute pass 0 refer to the last pass created by the script for the cube.</span></span>  
  
 <span data-ttu-id="1e56d-110">In tutte le sessioni vengono creati membri calcolati, ma l'espressione viene applicata alla sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="1e56d-110">Calculated members are created at all passes, but the expression is applied at the current pass.</span></span> <span data-ttu-id="1e56d-111">Le sessioni precedenti contengono la misura calcolata, ma con un valore Null.</span><span class="sxs-lookup"><span data-stu-id="1e56d-111">Prior passes contain the calculated measure, but with a null value.</span></span>  
  
## <a name="solve-order"></a><span data-ttu-id="1e56d-112">Ordine di valutazione</span><span class="sxs-lookup"><span data-stu-id="1e56d-112">Solve Order</span></span>  
 <span data-ttu-id="1e56d-113">L'ordine di valutazione determina la priorità di calcolo in presenza di espressioni in conflitto.</span><span class="sxs-lookup"><span data-stu-id="1e56d-113">Solve order determines the priority of calculation in the event of competing expressions.</span></span> <span data-ttu-id="1e56d-114">Nell'ambito di una singola sessione, l'ordine di valutazione determina quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1e56d-114">Within a single pass, solve order determines two things:</span></span>  
  
-   <span data-ttu-id="1e56d-115">Ordine in cui vengono [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] valutate dimensioni, membri, membri calcolati, rollup personalizzati e celle calcolate.</span><span class="sxs-lookup"><span data-stu-id="1e56d-115">The order in which [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates dimensions, members, calculated members, custom rollups, and calculated cells.</span></span>  
  
-   <span data-ttu-id="1e56d-116">L'ordine utilizzato da [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] per calcolare membri personalizzati, membri calcolati, rollup personalizzati e celle calcolate.</span><span class="sxs-lookup"><span data-stu-id="1e56d-116">The order in which [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates custom members, calculated members, custom rollup, and calculated cells.</span></span>  
  
 <span data-ttu-id="1e56d-117">Viene data la precedenza al membro con l'ordine di valutazione più alto.</span><span class="sxs-lookup"><span data-stu-id="1e56d-117">The member with the highest solve order takes precedence.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e56d-118">L'unica eccezione è rappresentata dalla funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="1e56d-118">The exception to this precedence is the Aggregate function.</span></span> <span data-ttu-id="1e56d-119">Per i membri calcolati con la funzione di aggregazione viene applicato un ordine di valutazione inferiore rispetto a qualsiasi misura calcolata intersecante.</span><span class="sxs-lookup"><span data-stu-id="1e56d-119">Calculated members with the Aggregate function have a lower solve order than any intersecting calculated measure.</span></span>  
  
## <a name="solve-order-values-and-precedence"></a><span data-ttu-id="1e56d-120">Valori dell'ordine di valutazione e precedenze</span><span class="sxs-lookup"><span data-stu-id="1e56d-120">Solve Order Values and Precedence</span></span>  
 <span data-ttu-id="1e56d-121">I valori dell'ordine di valutazione sono compresi tra -8181 e 65535.</span><span class="sxs-lookup"><span data-stu-id="1e56d-121">Solve order values can range from -8181 to 65535.</span></span> <span data-ttu-id="1e56d-122">In questo intervallo, alcuni valori dell'ordine di valutazione corrispondono a tipi specifici di calcoli, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e56d-122">In this range, some solve order values correspond to specific kinds of calculations, as shown in the following table.</span></span>  
  
|<span data-ttu-id="1e56d-123">Calcolo</span><span class="sxs-lookup"><span data-stu-id="1e56d-123">Calculation</span></span>|<span data-ttu-id="1e56d-124">Ordine di valutazione</span><span class="sxs-lookup"><span data-stu-id="1e56d-124">Solve Order</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1e56d-125">Formule personalizzate membro</span><span class="sxs-lookup"><span data-stu-id="1e56d-125">Custom member formulas</span></span>|<span data-ttu-id="1e56d-126">-5119</span><span class="sxs-lookup"><span data-stu-id="1e56d-126">-5119</span></span>|  
|<span data-ttu-id="1e56d-127">Operatori unari</span><span class="sxs-lookup"><span data-stu-id="1e56d-127">Unary operators</span></span>|<span data-ttu-id="1e56d-128">-5119</span><span class="sxs-lookup"><span data-stu-id="1e56d-128">-5119</span></span>|  
|<span data-ttu-id="1e56d-129">Calcolo di totali visualizzati</span><span class="sxs-lookup"><span data-stu-id="1e56d-129">Visual totals calculation</span></span>|<span data-ttu-id="1e56d-130">-4096</span><span class="sxs-lookup"><span data-stu-id="1e56d-130">-4096</span></span>|  
|<span data-ttu-id="1e56d-131">Tutti gli altri calcoli (se non diversamente specificato)</span><span class="sxs-lookup"><span data-stu-id="1e56d-131">All other calculations (if not otherwise specified)</span></span>|<span data-ttu-id="1e56d-132">0</span><span class="sxs-lookup"><span data-stu-id="1e56d-132">0</span></span>|  
  
 <span data-ttu-id="1e56d-133">È consigliabile utilizzare esclusivamente numeri interi positivi per l'impostazione dei valori dell'ordine di valutazione.</span><span class="sxs-lookup"><span data-stu-id="1e56d-133">It is highly recommended that you use only positive integers when setting solve order values.</span></span> <span data-ttu-id="1e56d-134">Se si assegnano valori inferiori a quelli indicati nella tabella precedente, il risultato della sessione di calcolo può diventare imprevedibile.</span><span class="sxs-lookup"><span data-stu-id="1e56d-134">If you assign values that are lower than the solve order values shown in the previous table, the calculation pass can become unpredictable.</span></span> <span data-ttu-id="1e56d-135">Se, ad esempio, al calcolo per un membro calcolato viene assegnato un valore dell'ordine di valutazione inferiore al valore predefinito delle formule di rollup personalizzato, che corrisponde a -5119,</span><span class="sxs-lookup"><span data-stu-id="1e56d-135">For example, the calculation for a calculated member receives a solve order value that is lower than the default custom rollup formula value of -5119.</span></span> <span data-ttu-id="1e56d-136">tale valore comporta l'esecuzione del calcolo dei membri calcolati prima delle formule di rollup personalizzato e può produrre risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="1e56d-136">Such a low solve order value causes the calculated members to be calculated before the custom rollup formulas, and can produce incorrect results.</span></span>  
  
### <a name="creating-and-changing-solve-order"></a><span data-ttu-id="1e56d-137">Creazione e modifica dell'ordine di valutazione</span><span class="sxs-lookup"><span data-stu-id="1e56d-137">Creating and Changing Solve Order</span></span>  
 <span data-ttu-id="1e56d-138">Nel **riquadro Calcoli**di Progettazione cubi è possibile modificare l'ordine di valutazione per i membri calcolati e le celle calcolate modificando l'ordine dei calcoli.</span><span class="sxs-lookup"><span data-stu-id="1e56d-138">In Cube Designer, on the **Calculations Pane**, you can change the solve order for calculated members and calculated cells by changing the order of the calculations.</span></span>  
  
 <span data-ttu-id="1e56d-139">In MDX è possibile utilizzare la parola chiave `SOLVE_ORDER` per creare o modificare l'ordine di valutazione per membri calcolati e celle calcolate.</span><span class="sxs-lookup"><span data-stu-id="1e56d-139">In MDX, you can use the `SOLVE_ORDER` keyword to create or change calculated members and calculated cells.</span></span>  
  
## <a name="solve-order-examples"></a><span data-ttu-id="1e56d-140">Esempi di ordine di valutazione</span><span class="sxs-lookup"><span data-stu-id="1e56d-140">Solve Order Examples</span></span>  
 <span data-ttu-id="1e56d-141">Per illustrare le potenziali complessità correlate all'ordine di valutazione, la serie seguente di query MDX inizia con due query che singolarmente non presentano problemi a livello di ordine di valutazione.</span><span class="sxs-lookup"><span data-stu-id="1e56d-141">To illustrate the potential complexities of solve order, the following series of MDX queries starts with two queries that each individually have no solve order issues.</span></span> <span data-ttu-id="1e56d-142">Queste due query vengono quindi combinate in una singola query, che richiede l'applicazione dell'ordine di valutazione.</span><span class="sxs-lookup"><span data-stu-id="1e56d-142">These two queries are then combined into a query that requires solve order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e56d-143">È possibile eseguire queste query MDX sul database multidimensionale di esempio Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="1e56d-143">You can run these MDX queries against the Adventure Works sample multidimensional database.</span></span> <span data-ttu-id="1e56d-144">È possibile scaricare l'esempio relativo ai [modelli multidimensionali di AdventureWorks per SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) dal sito codeplex.</span><span class="sxs-lookup"><span data-stu-id="1e56d-144">You can download the [AdventureWorks Multidimensional Models SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) sample from the codeplex site.</span></span>  
  
### <a name="query-1-differences-in-income-and-expenses"></a><span data-ttu-id="1e56d-145">Query 1-differenze tra reddito e spese</span><span class="sxs-lookup"><span data-stu-id="1e56d-145">Query 1-Differences in Income and Expenses</span></span>  
 <span data-ttu-id="1e56d-146">Per la prima query MDX, calcolare la differenza tra vendite e costi per ogni anno costruendo una semplice query MDX simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1e56d-146">For the first MDX query, calculate the difference in sales and costs for each year by constructing a simple MDX query similar to the following example:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] )  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="1e56d-147">In questa query è presente un solo membro calcolato, cioè `Year Difference`.</span><span class="sxs-lookup"><span data-stu-id="1e56d-147">In this query, there is only one calculated member, `Year Difference`.</span></span> <span data-ttu-id="1e56d-148">Essendo presente un solo membro calcolato, l'ordine di valutazione è irrilevante, a condizione che nel cubo non vengano utilizzati membri calcolati.</span><span class="sxs-lookup"><span data-stu-id="1e56d-148">Because there is only one calculated member, solve order is not an issue, as long as the cube does not use any calculated members.</span></span>  
  
 <span data-ttu-id="1e56d-149">Questa query MDX genera un set di risultati simile a quello illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e56d-149">This MDX query produces a result set similar to the following table.</span></span>  
  
||<span data-ttu-id="1e56d-150">Importo vendite Internet</span><span class="sxs-lookup"><span data-stu-id="1e56d-150">Internet Sales Amount</span></span>|<span data-ttu-id="1e56d-151">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="1e56d-151">Internet Total Product Cost</span></span>|  
|-|---------------------------|---------------------------------|  
|<span data-ttu-id="1e56d-152">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="1e56d-152">**CY 2007**</span></span>|<span data-ttu-id="1e56d-153">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="1e56d-153">$9,791,060.30</span></span>|<span data-ttu-id="1e56d-154">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="1e56d-154">$5,718,327.17</span></span>|  
|<span data-ttu-id="1e56d-155">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="1e56d-155">**CY 2008**</span></span>|<span data-ttu-id="1e56d-156">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="1e56d-156">$9,770,899.74</span></span>|<span data-ttu-id="1e56d-157">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="1e56d-157">$5,721,205.24</span></span>|  
|<span data-ttu-id="1e56d-158">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="1e56d-158">**Year Difference**</span></span>|<span data-ttu-id="1e56d-159">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="1e56d-159">($20,160.56)</span></span>|<span data-ttu-id="1e56d-160">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="1e56d-160">$2,878.06</span></span>|  
  
### <a name="query-2-percentage-of-income-after-expenses"></a><span data-ttu-id="1e56d-161">Query 2-percentuale di reddito dopo le spese</span><span class="sxs-lookup"><span data-stu-id="1e56d-161">Query 2-Percentage of Income after Expenses</span></span>  
 <span data-ttu-id="1e56d-162">Per la seconda query, calcolare la percentuale di reddito al netto delle spese per ogni anno utilizzando la query MDX seguente:</span><span class="sxs-lookup"><span data-stu-id="1e56d-162">For the second query, calculate the percentage of income after expenses for each year using the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Measures].[Profit Margin] AS   
([Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent"  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="1e56d-163">In questa query MDX, come nella precedente, è presente un solo membro calcolato, `Profit Margin`, e pertanto non presenta complicazioni relativamente all'ordine di valutazione.</span><span class="sxs-lookup"><span data-stu-id="1e56d-163">This MDX query, like the previous one, has only a single calculated member, `Profit Margin`, and therefore does not have any solve order complications.</span></span>  
  
 <span data-ttu-id="1e56d-164">Questa query MDX genera un set di risultati leggermente diverso, simile a quello illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e56d-164">This MDX query produces a slightly different result set, similar to the following table.</span></span>  
  
||<span data-ttu-id="1e56d-165">Importo vendite Internet</span><span class="sxs-lookup"><span data-stu-id="1e56d-165">Internet Sales Amount</span></span>|<span data-ttu-id="1e56d-166">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="1e56d-166">Internet Total Product Cost</span></span>|<span data-ttu-id="1e56d-167">Profit Margin</span><span class="sxs-lookup"><span data-stu-id="1e56d-167">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="1e56d-168">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="1e56d-168">**CY 2007**</span></span>|<span data-ttu-id="1e56d-169">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="1e56d-169">$9,791,060.30</span></span>|<span data-ttu-id="1e56d-170">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="1e56d-170">$5,718,327.17</span></span>|<span data-ttu-id="1e56d-171">41.60%</span><span class="sxs-lookup"><span data-stu-id="1e56d-171">41.60%</span></span>|  
|<span data-ttu-id="1e56d-172">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="1e56d-172">**CY 2008**</span></span>|<span data-ttu-id="1e56d-173">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="1e56d-173">$9,770,899.74</span></span>|<span data-ttu-id="1e56d-174">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="1e56d-174">$5,721,205.24</span></span>|<span data-ttu-id="1e56d-175">41.45%</span><span class="sxs-lookup"><span data-stu-id="1e56d-175">41.45%</span></span>|  
  
 <span data-ttu-id="1e56d-176">Le differenze nei set di risultati della prima e della seconda query sono dovute alla diversa posizione del membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="1e56d-176">The difference in result sets between the first query and the second query comes from the difference in placement of the calculated member.</span></span> <span data-ttu-id="1e56d-177">Nella prima query il membro calcolato fa parte dell'asse ROWS e non dell'asse COLUMNS indicato nella seconda query.</span><span class="sxs-lookup"><span data-stu-id="1e56d-177">In the first query, the calculated member is part of the ROWS axis, not the COLUMNS axis shown in the second query.</span></span> <span data-ttu-id="1e56d-178">Questa differenza di posizione diventa importante nella query successiva, in cui i due membri calcolati vengono combinati in una singola query MDX.</span><span class="sxs-lookup"><span data-stu-id="1e56d-178">This difference in placement becomes important in the next query, which combines the two calculated members in a single MDX query.</span></span>  
  
### <a name="query-3-combined-year-difference-and-net-income-calculations"></a><span data-ttu-id="1e56d-179">Query 3: differenza tra anno combinato e calcolo del reddito netto</span><span class="sxs-lookup"><span data-stu-id="1e56d-179">Query 3-Combined Year Difference and Net Income Calculations</span></span>  
 <span data-ttu-id="1e56d-180">Nella query finale, in cui vengono combinati entrambi gli esempi precedenti in una singola query MDX, l'ordine di valutazione diventa importante a causa dei calcoli in entrambe le colonne e le righe.</span><span class="sxs-lookup"><span data-stu-id="1e56d-180">In this final query combining both of the previous examples into a single MDX query, solve order becomes important because of the calculations on both columns and rows.</span></span> <span data-ttu-id="1e56d-181">Per assicurarsi che i calcoli vengano eseguiti nella sequenza corretta, definire la sequenza di esecuzione dei calcoli tramite la parola chiave `SOLVE_ORDER`.</span><span class="sxs-lookup"><span data-stu-id="1e56d-181">To make sure that the calculations occur in the correct sequence, define the sequence in which the calculations occur by using the `SOLVE_ORDER` keyword.</span></span>  
  
 <span data-ttu-id="1e56d-182">La parola chiave `SOLVE_ORDER` consente di specificare l'ordine di valutazione dei membri calcolati in una query MDX o in un comando `CREATE MEMBER`.</span><span class="sxs-lookup"><span data-stu-id="1e56d-182">The `SOLVE_ORDER` keyword specifies the solve order of calculated members in an MDX query or a `CREATE MEMBER` command.</span></span> <span data-ttu-id="1e56d-183">I valori integer utilizzati con la parola chiave `SOLVE_ORDER` sono relativi e non devono necessariamente iniziare da zero o essere consecutivi.</span><span class="sxs-lookup"><span data-stu-id="1e56d-183">The integer values used with the `SOLVE_ORDER` keyword are relative, do not need to start at zero, and do not need to be consecutive.</span></span> <span data-ttu-id="1e56d-184">Il valore indica semplicemente al sistema MDX di calcolare un membro in base ai valori derivati dal calcolo dei membri con un valore superiore.</span><span class="sxs-lookup"><span data-stu-id="1e56d-184">The value simply tells MDX to calculate a member based on values derived from calculating members with a higher value.</span></span> <span data-ttu-id="1e56d-185">Se un membro calcolato viene definito senza la parola chiave `SOLVE_ORDER`, il relativo valore predefinito sarà zero.</span><span class="sxs-lookup"><span data-stu-id="1e56d-185">If a calculated member is defined without the `SOLVE_ORDER` keyword, the default value of that calculated member is zero.</span></span>  
  
 <span data-ttu-id="1e56d-186">Se ad esempio si combinano i calcoli utilizzati nelle prime due query di esempio, i due membri calcolati `Year Difference` e `Profit Margin`si intersecano in corrispondenza di una singola cella nel set di dati risultante dell'esempio di query MDX.</span><span class="sxs-lookup"><span data-stu-id="1e56d-186">For example, if you combine the calculations used in the first two example queries, the two calculated members, `Year Difference` and `Profit Margin`, intersect at a single cell in the result dataset of the MDX query example.</span></span> <span data-ttu-id="1e56d-187">L'unico modo per determinare come questa cella verrà valutata da [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] consiste nell'usare l'ordine di valutazione.</span><span class="sxs-lookup"><span data-stu-id="1e56d-187">The only way to determine how [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] will evaluate this cell is by the solve order.</span></span> <span data-ttu-id="1e56d-188">Le formule utilizzate per creare la cella genereranno risultati diversi a seconda dell'ordine di valutazione dei due membri calcolati.</span><span class="sxs-lookup"><span data-stu-id="1e56d-188">The formulas that are used to construct this cell will produce different results depending upon the solve order of the two calculated members.</span></span>  
  
 <span data-ttu-id="1e56d-189">Provare innanzitutto a combinare nella query MDX seguente i calcoli utilizzati nelle prime due query:</span><span class="sxs-lookup"><span data-stu-id="1e56d-189">First, try combining the calculations used in the first two queries in the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 1  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 2  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="1e56d-190">In questo esempio di query MDX combinata, a `Profit Margin` è associato l'ordine di valutazione più alto, pertanto ha la precedenza quando le due espressioni interagiscono.</span><span class="sxs-lookup"><span data-stu-id="1e56d-190">In this combined MDX query example, `Profit Margin` has the highest solve order, so it takes precedence when the two expressions interact.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="1e56d-191">valuta la cella in questione tramite la formula `Profit Margin` .</span><span class="sxs-lookup"><span data-stu-id="1e56d-191">evaluates the cell in question by using the `Profit Margin` formula.</span></span> <span data-ttu-id="1e56d-192">Nella tabella seguente sono riportati i risultati di questo calcolo nidificato.</span><span class="sxs-lookup"><span data-stu-id="1e56d-192">The results of this nested calculation, as shown in the following table.</span></span>  
  
||<span data-ttu-id="1e56d-193">Importo vendite Internet</span><span class="sxs-lookup"><span data-stu-id="1e56d-193">Internet Sales Amount</span></span>|<span data-ttu-id="1e56d-194">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="1e56d-194">Internet Total Product Cost</span></span>|<span data-ttu-id="1e56d-195">Profit Margin</span><span class="sxs-lookup"><span data-stu-id="1e56d-195">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="1e56d-196">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="1e56d-196">**CY 2007**</span></span>|<span data-ttu-id="1e56d-197">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="1e56d-197">$9,791,060.30</span></span>|<span data-ttu-id="1e56d-198">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="1e56d-198">$5,718,327.17</span></span>|<span data-ttu-id="1e56d-199">41.60%</span><span class="sxs-lookup"><span data-stu-id="1e56d-199">41.60%</span></span>|  
|<span data-ttu-id="1e56d-200">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="1e56d-200">**CY 2008**</span></span>|<span data-ttu-id="1e56d-201">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="1e56d-201">$9,770,899.74</span></span>|<span data-ttu-id="1e56d-202">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="1e56d-202">$5,721,205.24</span></span>|<span data-ttu-id="1e56d-203">41.45%</span><span class="sxs-lookup"><span data-stu-id="1e56d-203">41.45%</span></span>|  
|<span data-ttu-id="1e56d-204">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="1e56d-204">**Year Difference**</span></span>|<span data-ttu-id="1e56d-205">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="1e56d-205">($20,160.56)</span></span>|<span data-ttu-id="1e56d-206">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="1e56d-206">$2,878.06</span></span>|<span data-ttu-id="1e56d-207">114.28%</span><span class="sxs-lookup"><span data-stu-id="1e56d-207">114.28%</span></span>|  
  
 <span data-ttu-id="1e56d-208">Il risultato nella cella condivisa è basato sulla formula per `Profit Margin`.</span><span class="sxs-lookup"><span data-stu-id="1e56d-208">The result in the shared cell is based on the formula for `Profit Margin`.</span></span> <span data-ttu-id="1e56d-209">Ciò significa che in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] viene calcolato il risultato nella cella condivisa con i dati di `Year Difference` , generando la formula seguente (il risultato è arrotondato per maggiore chiarezza):</span><span class="sxs-lookup"><span data-stu-id="1e56d-209">That is, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell with the `Year Difference` data, producing the following formula (the result is rounded for clarity):</span></span>  
  
```  
((9,770,899.74 - 9,791,060.30) - (5,721,205.24 - 5,718,327.17)) / (9,770,899.74 - 9,791,060.30) = 1.14275744   
```  
  
 <span data-ttu-id="1e56d-210">oppure</span><span class="sxs-lookup"><span data-stu-id="1e56d-210">or</span></span>  
  
```  
(23,038.63) / (20,160.56) = 114.28%  
```  
  
 <span data-ttu-id="1e56d-211">È chiaramente errata.</span><span class="sxs-lookup"><span data-stu-id="1e56d-211">This is clearly incorrect.</span></span> <span data-ttu-id="1e56d-212">Il risultato nella cella condivisa viene tuttavia calcolato diversamente in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] se si cambiano gli ordini di valutazione per i membri calcolati nella query MDX.</span><span class="sxs-lookup"><span data-stu-id="1e56d-212">However, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell differently if you switch the solve orders for the calculated members in the MDX query.</span></span> <span data-ttu-id="1e56d-213">Nella query MDX combinata seguente viene invertito l'ordine di valutazione dei membri calcolati:</span><span class="sxs-lookup"><span data-stu-id="1e56d-213">The following combined MDX query reverses the solve order for the calculated members:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 2  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 1  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="1e56d-214">Poiché l'ordine dei membri calcolati è stato cambiato, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] viene usate la formula `Year Difference` per valutare la cella, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1e56d-214">As the order of the calculated members has been switched, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses the `Year Difference` formula to evaluate the cell, as shown in the following table.</span></span>  
  
||<span data-ttu-id="1e56d-215">Importo vendite Internet</span><span class="sxs-lookup"><span data-stu-id="1e56d-215">Internet Sales Amount</span></span>|<span data-ttu-id="1e56d-216">Internet Total Product Cost</span><span class="sxs-lookup"><span data-stu-id="1e56d-216">Internet Total Product Cost</span></span>|<span data-ttu-id="1e56d-217">Profit Margin</span><span class="sxs-lookup"><span data-stu-id="1e56d-217">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="1e56d-218">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="1e56d-218">**CY 2007**</span></span>|<span data-ttu-id="1e56d-219">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="1e56d-219">$9,791,060.30</span></span>|<span data-ttu-id="1e56d-220">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="1e56d-220">$5,718,327.17</span></span>|<span data-ttu-id="1e56d-221">41.60%</span><span class="sxs-lookup"><span data-stu-id="1e56d-221">41.60%</span></span>|  
|<span data-ttu-id="1e56d-222">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="1e56d-222">**CY 2008**</span></span>|<span data-ttu-id="1e56d-223">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="1e56d-223">$9,770,899.74</span></span>|<span data-ttu-id="1e56d-224">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="1e56d-224">$5,721,205.24</span></span>|<span data-ttu-id="1e56d-225">41.45%</span><span class="sxs-lookup"><span data-stu-id="1e56d-225">41.45%</span></span>|  
|<span data-ttu-id="1e56d-226">**Year Difference**</span><span class="sxs-lookup"><span data-stu-id="1e56d-226">**Year Difference**</span></span>|<span data-ttu-id="1e56d-227">($20,160.56)</span><span class="sxs-lookup"><span data-stu-id="1e56d-227">($20,160.56)</span></span>|<span data-ttu-id="1e56d-228">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="1e56d-228">$2,878.06</span></span>|<span data-ttu-id="1e56d-229">(0.15%)</span><span class="sxs-lookup"><span data-stu-id="1e56d-229">(0.15%)</span></span>|  
  
 <span data-ttu-id="1e56d-230">Poiché nella query viene usata la formula `Year Difference` con i dati `Profit Margin` , la formula per la cella condivisa assomiglia al calcolo seguente:</span><span class="sxs-lookup"><span data-stu-id="1e56d-230">Because this query uses the `Year Difference` formula with the `Profit Margin` data, the formula for the shared cell resembles the following calculation:</span></span>  
  
```  
(($9,770,899.74 - 5,721,205.24) / $9,770,899.74) - ((9,791,060.30 - 5,718,327.17) / 9,791,060.30) = -0.15   
```  
  
 <span data-ttu-id="1e56d-231">Oppure</span><span class="sxs-lookup"><span data-stu-id="1e56d-231">Or</span></span>  
  
```  
0.4145 - 0.4160= -0.15  
```  
  
## <a name="additional-considerations"></a><span data-ttu-id="1e56d-232">Ulteriori considerazioni</span><span class="sxs-lookup"><span data-stu-id="1e56d-232">Additional Considerations</span></span>  
 <span data-ttu-id="1e56d-233">L'ordine di valutazione può essere un aspetto estremamente complesso da affrontare, soprattutto in cubi con un numero elevato di dimensioni che includono membri calcolati, formule di rollup personalizzato o celle calcolate.</span><span class="sxs-lookup"><span data-stu-id="1e56d-233">Solve order can be a very complex issue to deal with, especially in cubes with a high number of dimensions involving calculated member, custom rollup formulas, or calculated cells.</span></span> <span data-ttu-id="1e56d-234">Quando in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] viene valutata una query MDX, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] prende in considerazione i valori dell'ordine di valutazione per tutti gli elementi coinvolti in una determinata sessione, incluse le dimensioni del cubo specificate nella query MDX.</span><span class="sxs-lookup"><span data-stu-id="1e56d-234">When [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates an MDX query, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] takes into account the solve order values for everything involved within a given pass, including the dimensions of the cube specified in the MDX query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e56d-235">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e56d-235">See Also</span></span>  
 <span data-ttu-id="1e56d-236">[CalculationCurrentPass &#40;&#41;MDX](/sql/mdx/calculationcurrentpass-mdx) </span><span class="sxs-lookup"><span data-stu-id="1e56d-236">[CalculationCurrentPass &#40;MDX&#41;](/sql/mdx/calculationcurrentpass-mdx) </span></span>  
 <span data-ttu-id="1e56d-237">[CalculationPassValue &#40;&#41;MDX](/sql/mdx/calculationpassvalue-mdx) </span><span class="sxs-lookup"><span data-stu-id="1e56d-237">[CalculationPassValue &#40;MDX&#41;](/sql/mdx/calculationpassvalue-mdx) </span></span>  
 <span data-ttu-id="1e56d-238">[Istruzione CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="1e56d-238">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 [<span data-ttu-id="1e56d-239">Manipolazione dei dati &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="1e56d-239">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
