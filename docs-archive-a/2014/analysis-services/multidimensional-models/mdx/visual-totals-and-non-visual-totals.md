---
title: Totali visivi e totali non visivi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ea9d02f2-a668-4547-ade5-e3d077a2e1bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ddff047be6a819d05276848cbeb430fb8e4c9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721884"
---
# <a name="visual-totals-and-non-visual-totals"></a><span data-ttu-id="6b477-102">Totali visualizzati e non visualizzati</span><span class="sxs-lookup"><span data-stu-id="6b477-102">Visual Totals and Non Visual Totals</span></span>
  <span data-ttu-id="6b477-103">I totali visualizzati sono totali alla fine di una colonna o riga in cui vengono sommati tutti gli elementi visibili della colonna o riga.</span><span class="sxs-lookup"><span data-stu-id="6b477-103">Visual Totals are totals at the end of a column or row that add up all of the items visible in the column or row.</span></span> <span data-ttu-id="6b477-104">Questo è il comportamento predefinito per la maggior parte delle tabelle visualizzate.</span><span class="sxs-lookup"><span data-stu-id="6b477-104">This is the default behavior for most tables when displayed.</span></span> <span data-ttu-id="6b477-105">Tuttavia, in alcuni casi per l'utente è utile visualizzare solo alcune colonne di una tabella, conservando però i totali per la riga intera, compresi gli elementi non visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6b477-105">However, there are times when the user wants to display only certain columns in a table but keep the totals for the entire row, including those that are not displayed.</span></span> <span data-ttu-id="6b477-106">Questi vengono chiamati `Non Visual Totals`, perché il totale è il risultato di valori visualizzati e non visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6b477-106">These are called `Non Visual Totals`, because the total comes from both the visible and non-visible values.</span></span>  
  
 <span data-ttu-id="6b477-107">Nello scenario riportato di seguito viene illustrato il comportamento dei totali non visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6b477-107">The following scenario demonstrates the behavior of Non Visual totals.</span></span> <span data-ttu-id="6b477-108">Il primo passaggio mostra il comportamento predefinito dei totali visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6b477-108">The first step shows the default behavior of Visual Totals.</span></span>  
  
 <span data-ttu-id="6b477-109">L'esempio che segue è una query di [Adventure Works] per ottenere le cifre di [Reseller Sales Amount] in una tabella in cui le categorie dei prodotti sono le colonne e i tipi di attività dei rivenditori sono le righe.</span><span class="sxs-lookup"><span data-stu-id="6b477-109">The following example is a query of [Adventure Works] to obtain [Reseller Sales Amount] figures in a table where the product categories are the columns and the reseller business types are the rows.</span></span> <span data-ttu-id="6b477-110">Vengono forniti i totali relativi sia ai prodotti che ai rivenditori non appena si esegue l'istruzione SELECT seguente:</span><span class="sxs-lookup"><span data-stu-id="6b477-110">Note that totals are given for both products and resellers when the following SELECT statement is issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from [Adventure Works]`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="6b477-111">Produce i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b477-111">Produces the following results:</span></span>  
  
|||||||  
|-|-|-|-|-|-|  
||<span data-ttu-id="6b477-112">**Tutti i prodotti**</span><span class="sxs-lookup"><span data-stu-id="6b477-112">**All Products**</span></span>|<span data-ttu-id="6b477-113">**Accessori**</span><span class="sxs-lookup"><span data-stu-id="6b477-113">**Accessories**</span></span>|<span data-ttu-id="6b477-114">**Biciclette**</span><span class="sxs-lookup"><span data-stu-id="6b477-114">**Bikes**</span></span>|<span data-ttu-id="6b477-115">**Clothing**</span><span class="sxs-lookup"><span data-stu-id="6b477-115">**Clothing**</span></span>|<span data-ttu-id="6b477-116">**Componenti**</span><span class="sxs-lookup"><span data-stu-id="6b477-116">**Components**</span></span>|  
|<span data-ttu-id="6b477-117">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="6b477-117">**All Resellers**</span></span>|<span data-ttu-id="6b477-118">**$80,450,596.98**</span><span class="sxs-lookup"><span data-stu-id="6b477-118">**$80,450,596.98**</span></span>|<span data-ttu-id="6b477-119">**$571,297.93**</span><span class="sxs-lookup"><span data-stu-id="6b477-119">**$571,297.93**</span></span>|<span data-ttu-id="6b477-120">**$66,302,381.56**</span><span class="sxs-lookup"><span data-stu-id="6b477-120">**$66,302,381.56**</span></span>|<span data-ttu-id="6b477-121">**$1,777,840.84**</span><span class="sxs-lookup"><span data-stu-id="6b477-121">**$1,777,840.84**</span></span>|<span data-ttu-id="6b477-122">**$11,799,076.66**</span><span class="sxs-lookup"><span data-stu-id="6b477-122">**$11,799,076.66**</span></span>|  
|<span data-ttu-id="6b477-123">**Specialty Bike Shop**</span><span class="sxs-lookup"><span data-stu-id="6b477-123">**Specialty Bike Shop**</span></span>|<span data-ttu-id="6b477-124">**$6,756,166.18**</span><span class="sxs-lookup"><span data-stu-id="6b477-124">**$6,756,166.18**</span></span>|<span data-ttu-id="6b477-125">**$65,125.48**</span><span class="sxs-lookup"><span data-stu-id="6b477-125">**$65,125.48**</span></span>|<span data-ttu-id="6b477-126">**$6,080,117.73**</span><span class="sxs-lookup"><span data-stu-id="6b477-126">**$6,080,117.73**</span></span>|<span data-ttu-id="6b477-127">**$252,933.91**</span><span class="sxs-lookup"><span data-stu-id="6b477-127">**$252,933.91**</span></span>|<span data-ttu-id="6b477-128">**$357,989.07**</span><span class="sxs-lookup"><span data-stu-id="6b477-128">**$357,989.07**</span></span>|  
|<span data-ttu-id="6b477-129">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="6b477-129">**Value Added Reseller**</span></span>|<span data-ttu-id="6b477-130">**$34,967,517.33**</span><span class="sxs-lookup"><span data-stu-id="6b477-130">**$34,967,517.33**</span></span>|<span data-ttu-id="6b477-131">**$175,002.81**</span><span class="sxs-lookup"><span data-stu-id="6b477-131">**$175,002.81**</span></span>|<span data-ttu-id="6b477-132">**$30,892,354.33**</span><span class="sxs-lookup"><span data-stu-id="6b477-132">**$30,892,354.33**</span></span>|<span data-ttu-id="6b477-133">**$592,385.71**</span><span class="sxs-lookup"><span data-stu-id="6b477-133">**$592,385.71**</span></span>|<span data-ttu-id="6b477-134">**$3,307,774.48**</span><span class="sxs-lookup"><span data-stu-id="6b477-134">**$3,307,774.48**</span></span>|  
|<span data-ttu-id="6b477-135">**Warehouse**</span><span class="sxs-lookup"><span data-stu-id="6b477-135">**Warehouse**</span></span>|<span data-ttu-id="6b477-136">**$38,726,913.48**</span><span class="sxs-lookup"><span data-stu-id="6b477-136">**$38,726,913.48**</span></span>|<span data-ttu-id="6b477-137">**$331,169.64**</span><span class="sxs-lookup"><span data-stu-id="6b477-137">**$331,169.64**</span></span>|<span data-ttu-id="6b477-138">**$29,329,909.50**</span><span class="sxs-lookup"><span data-stu-id="6b477-138">**$29,329,909.50**</span></span>|<span data-ttu-id="6b477-139">**$932,521.23**</span><span class="sxs-lookup"><span data-stu-id="6b477-139">**$932,521.23**</span></span>|<span data-ttu-id="6b477-140">**$8,133,313.11**</span><span class="sxs-lookup"><span data-stu-id="6b477-140">**$8,133,313.11**</span></span>|  
  
## <a name="non-visual-on-rows-and-columns"></a><span data-ttu-id="6b477-141">Totale non visualizzato su righe e colonne</span><span class="sxs-lookup"><span data-stu-id="6b477-141">Non-Visual on rows and columns</span></span>  
 <span data-ttu-id="6b477-142">Per produrre una tabella solo con i dati per i prodotti Accessories e Clothing, i rivenditori Value Added Reseller e Warehouse, conservando tuttavia i totali complessivi, si potrebbe scrivere una query come la seguente utilizzando NON VISUAL:</span><span class="sxs-lookup"><span data-stu-id="6b477-142">To produce a table with data only for the Accessories and Clothing products, the Value Added Reseller and Warehouse resellers, yet keeping the overall totals could be written as follows using NON VISUAL:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0,`  
  
 `{[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 1`  
  
 `from [Adventure Works])`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="6b477-143">Produce i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b477-143">Produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="6b477-144">**Tutti i prodotti**</span><span class="sxs-lookup"><span data-stu-id="6b477-144">**All Products**</span></span>|<span data-ttu-id="6b477-145">**Accessori**</span><span class="sxs-lookup"><span data-stu-id="6b477-145">**Accessories**</span></span>|<span data-ttu-id="6b477-146">**Clothing**</span><span class="sxs-lookup"><span data-stu-id="6b477-146">**Clothing**</span></span>|  
|<span data-ttu-id="6b477-147">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="6b477-147">**All Resellers**</span></span>|<span data-ttu-id="6b477-148">**$80,450,596.98**</span><span class="sxs-lookup"><span data-stu-id="6b477-148">**$80,450,596.98**</span></span>|<span data-ttu-id="6b477-149">**$571,297.93**</span><span class="sxs-lookup"><span data-stu-id="6b477-149">**$571,297.93**</span></span>|<span data-ttu-id="6b477-150">**$1,777,840.84**</span><span class="sxs-lookup"><span data-stu-id="6b477-150">**$1,777,840.84**</span></span>|  
|<span data-ttu-id="6b477-151">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="6b477-151">**Value Added Reseller**</span></span>|<span data-ttu-id="6b477-152">**$34,967,517.33**</span><span class="sxs-lookup"><span data-stu-id="6b477-152">**$34,967,517.33**</span></span>|<span data-ttu-id="6b477-153">**$175,002.81**</span><span class="sxs-lookup"><span data-stu-id="6b477-153">**$175,002.81**</span></span>|<span data-ttu-id="6b477-154">**$592,385.71**</span><span class="sxs-lookup"><span data-stu-id="6b477-154">**$592,385.71**</span></span>|  
|<span data-ttu-id="6b477-155">**Warehouse**</span><span class="sxs-lookup"><span data-stu-id="6b477-155">**Warehouse**</span></span>|<span data-ttu-id="6b477-156">**$38,726,913.48**</span><span class="sxs-lookup"><span data-stu-id="6b477-156">**$38,726,913.48**</span></span>|<span data-ttu-id="6b477-157">**$331,169.64**</span><span class="sxs-lookup"><span data-stu-id="6b477-157">**$331,169.64**</span></span>|<span data-ttu-id="6b477-158">**$932,521.23**</span><span class="sxs-lookup"><span data-stu-id="6b477-158">**$932,521.23**</span></span>|  
  
## <a name="non-visual-on-rows"></a><span data-ttu-id="6b477-159">Totale non visualizzato sulle righe</span><span class="sxs-lookup"><span data-stu-id="6b477-159">Non-Visual on rows</span></span>  
 <span data-ttu-id="6b477-160">Per produrre una tabella che visivamente somma le colonne, ma per i totali delle righe riporta il totale vero di [Category], immettere la query seguente:</span><span class="sxs-lookup"><span data-stu-id="6b477-160">To produce a table that visually totals the columns but for row totals brings the true total of all [Category], the following query should be issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0`  
  
 `from ( Select {[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 0`  
  
 `from [Adventure Works])`  
  
 `)`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="6b477-161">Notare come NON VISUAL è applicato solo a [Category].</span><span class="sxs-lookup"><span data-stu-id="6b477-161">Note how NON VISUAL is only applied to [Category].</span></span>  
  
 <span data-ttu-id="6b477-162">La query precedente produce i seguenti risultati:</span><span class="sxs-lookup"><span data-stu-id="6b477-162">The above query produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="6b477-163">All Products</span><span class="sxs-lookup"><span data-stu-id="6b477-163">All Products</span></span>|<span data-ttu-id="6b477-164">Accessori</span><span class="sxs-lookup"><span data-stu-id="6b477-164">Accessories</span></span>|<span data-ttu-id="6b477-165">Clothing</span><span class="sxs-lookup"><span data-stu-id="6b477-165">Clothing</span></span>|  
|<span data-ttu-id="6b477-166">All Resellers</span><span class="sxs-lookup"><span data-stu-id="6b477-166">All Resellers</span></span>|<span data-ttu-id="6b477-167">$73,694,430.80</span><span class="sxs-lookup"><span data-stu-id="6b477-167">$73,694,430.80</span></span>|<span data-ttu-id="6b477-168">$506,172.45</span><span class="sxs-lookup"><span data-stu-id="6b477-168">$506,172.45</span></span>|<span data-ttu-id="6b477-169">$1,524,906.93</span><span class="sxs-lookup"><span data-stu-id="6b477-169">$1,524,906.93</span></span>|  
|<span data-ttu-id="6b477-170">Value Added Reseller</span><span class="sxs-lookup"><span data-stu-id="6b477-170">Value Added Reseller</span></span>|<span data-ttu-id="6b477-171">$34,967,517.33</span><span class="sxs-lookup"><span data-stu-id="6b477-171">$34,967,517.33</span></span>|<span data-ttu-id="6b477-172">$175,002.81</span><span class="sxs-lookup"><span data-stu-id="6b477-172">$175,002.81</span></span>|<span data-ttu-id="6b477-173">$592,385.71</span><span class="sxs-lookup"><span data-stu-id="6b477-173">$592,385.71</span></span>|  
|<span data-ttu-id="6b477-174">Warehouse</span><span class="sxs-lookup"><span data-stu-id="6b477-174">Warehouse</span></span>|<span data-ttu-id="6b477-175">$38,726,913.48</span><span class="sxs-lookup"><span data-stu-id="6b477-175">$38,726,913.48</span></span>|<span data-ttu-id="6b477-176">$331,169.64</span><span class="sxs-lookup"><span data-stu-id="6b477-176">$331,169.64</span></span>|<span data-ttu-id="6b477-177">$932,521.23</span><span class="sxs-lookup"><span data-stu-id="6b477-177">$932,521.23</span></span>|  
  
 <span data-ttu-id="6b477-178">Se si confrontano i risultati precedenti, è possibile osservare che la riga [All Resellers] si aggiunge ai valori visualizzati di [Value Added Reseller] e [Warehouse] ma che la colonna [All Products] mostra il valore totale per tutti i prodotti, compresi quelli non visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6b477-178">When compared with the previous results, you can observe that the [All Resellers] row now adds up to the displayed values for [Value Added Reseller] and [Warehouse] but that the [All Products] column shows the total value for all products, including those not displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b477-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b477-179">See Also</span></span>  
 <span data-ttu-id="6b477-180">[Concetti chiave di MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="6b477-180">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="6b477-181">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="6b477-181">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="6b477-182">[Utilizzo di membri, Tuple e set &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="6b477-182">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="6b477-183">[Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="6b477-183">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="6b477-184">[Query MDX di base &#40;&#41;MDX](mdx-query-the-basic-query.md) </span><span class="sxs-lookup"><span data-stu-id="6b477-184">[The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md) </span></span>  
 <span data-ttu-id="6b477-185">[Limitazione della query con gli assi di query e di sezionamento &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span><span class="sxs-lookup"><span data-stu-id="6b477-185">[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span></span>  
 [<span data-ttu-id="6b477-186">Definizione del contesto di cubo in una query &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="6b477-186">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)  
  
  
