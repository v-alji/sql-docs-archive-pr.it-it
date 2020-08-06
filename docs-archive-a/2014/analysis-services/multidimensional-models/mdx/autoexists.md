---
title: Auto Exist | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 56283497-624c-45b5-8a0d-036b0e331d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd35958a364456c12d58392afe3754f6adcf97b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630125"
---
# <a name="autoexists"></a><span data-ttu-id="73784-102">Auto Exist</span><span class="sxs-lookup"><span data-stu-id="73784-102">Autoexists</span></span>
  <span data-ttu-id="73784-103">Il concetto di *Auto Exist* limita lo spazio del cubo a quelle celle che esistono effettivamente nel cubo, in contrapposizione con quelle che potrebbero esistere come risultato della creazione di tutte le possibili combinazioni di membri delle gerarchie di attributi dalla medesima gerarchia.</span><span class="sxs-lookup"><span data-stu-id="73784-103">The concept of *autoexists* limits the cube space to those cells that actually exist in the cube in contraposition to those that might exist as a result of creating all possible combinations of attribute hierarchy members from the same hierarchy.</span></span> <span data-ttu-id="73784-104">La distinzione è necessaria perché i membri di una gerarchia di attributi non possono coesistere con membri di un'altra gerarchia di attributi nella stessa dimensione.</span><span class="sxs-lookup"><span data-stu-id="73784-104">This is because members of one attribute hierarchy cannot exist with members of another attribute hierarchy in the same dimension.</span></span> <span data-ttu-id="73784-105">Quando in un'istruzione SELECT si utilizzano due o più gerarchie di attributi della medesima dimensione, Analysis Services valuta le espressioni degli attributi per verificare che i relativi membri siano correttamente limitati per soddisfare i criteri di tutti gli altri attributi.</span><span class="sxs-lookup"><span data-stu-id="73784-105">When two or more attribute hierarchies of the same dimension are used in a SELECT statement, Analysis Services evaluates the attributes' expressions to make sure that the members of those attributes are properly confined to meet the criteria of all other attributes.</span></span>  
  
 <span data-ttu-id="73784-106">Si supponga ad esempio di utilizzare gli attributi della dimensione Geografia.</span><span class="sxs-lookup"><span data-stu-id="73784-106">For example, suppose you are working with attributes from the Geography dimension.</span></span> <span data-ttu-id="73784-107">Se una delle espressioni restituisce tutti i membri dell'attributo Città e un'altra limita i membri dell'attributo Paese a tutti i paesi Europai, allora i membri di Città saranno limitati alle sole città che appartengono a paesi Europai.</span><span class="sxs-lookup"><span data-stu-id="73784-107">If you have one expression that returns all members from the City attribute and another expression that confines members from the Country attribute to all countries in Europe, then this will result in the City members being confined to only those cities that belong to countries in Europe.</span></span> <span data-ttu-id="73784-108">Ciò è dovuto alla caratteristica Auto Exist in Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="73784-108">This is because of the autoexists characteristic of Analysis Services.</span></span> <span data-ttu-id="73784-109">un quanto tenta di impedire che i record di dimensioni esclusi nell'espressione di un attributo vengano inclusi dalle espressioni di altri attributi.</span><span class="sxs-lookup"><span data-stu-id="73784-109">Autoexists only applies to attributes from the same dimension because it tries to prevent the dimension records excluded in one attribute expression from being included by the other attribute expressions.</span></span> <span data-ttu-id="73784-110">La caratteristica Auto Exist può inoltre essere interpretata come l'intersezione risultante da diverse espressioni di attributi su righe di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="73784-110">Autoexists can also be understood as the resulting intersection of the different attributes expressions over the dimension rows.</span></span>  
  
## <a name="cell-existence"></a><span data-ttu-id="73784-111">Esistenza della cella</span><span class="sxs-lookup"><span data-stu-id="73784-111">Cell Existence</span></span>  
 <span data-ttu-id="73784-112">Le celle seguenti esistono sempre:</span><span class="sxs-lookup"><span data-stu-id="73784-112">The following cells always exist:</span></span>  
  
-   <span data-ttu-id="73784-113">Il membro (Totale), di ogni gerarchia, quando incrociato con membri di altre gerarchie nella stessa dimensione.</span><span class="sxs-lookup"><span data-stu-id="73784-113">The (All) member, of every hierarchy, when crossed with members of other hierarchies in the same dimension.</span></span>  
  
-   <span data-ttu-id="73784-114">Membri calcolati quando incrociati con gli elementi di pari livello non calcolati o con i padri o discendenti degli elementi di pari livello non calcolati.</span><span class="sxs-lookup"><span data-stu-id="73784-114">Calculated members when crossed with their non-calculated siblings, or with the parents or descendants of their non-calculated siblings.</span></span>  
  
## <a name="providing-non-existing-cells"></a><span data-ttu-id="73784-115">Celle non esistenti</span><span class="sxs-lookup"><span data-stu-id="73784-115">Providing Non-existing cells</span></span>  
 <span data-ttu-id="73784-116">Una cella non esistente è una cella fornita dal sistema in risposta a una query o a un calcolo che richiede una cella che non esiste nel cubo.</span><span class="sxs-lookup"><span data-stu-id="73784-116">A non-existing cell is a cell provided by the system as a response to a query or calculation that requests a cell that does not exist in the cube.</span></span> <span data-ttu-id="73784-117">Se, ad esempio, si dispone di un cubo con una gerarchia dell'attributo City e una gerarchia dell'attributo Country che appartiene alla dimensione Geography e una misura Internet Sales Amount, lo spazio di questo cubo include solo i membri che esistono in ogni livello superiore.</span><span class="sxs-lookup"><span data-stu-id="73784-117">For example, if you have a cube that has a City attribute hierarchy and a Country attribute hierarchy that belong to the Geography dimension, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="73784-118">Se, ad esempio, la gerarchia dell'attributo City include le città di New York, London, Paris, Tokyo e Melbourne e la gerarchia dell'attributo Country include i paesi Stati Uniti, United Kingdom, France, Japan e Australia, lo spazio del cubo non include lo spazio (cella) nel punto di intersezione tra Paris e Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="73784-118">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="73784-119">Quando si esegue una query su celle inesistenti, tali celle restituiscono valori Null, cioè non possono contenere calcoli e non è possibile definire un calcolo esegua operazioni di scrittura in questo spazio.</span><span class="sxs-lookup"><span data-stu-id="73784-119">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="73784-120">L'istruzione seguente, ad esempio, include celle che non esistono.</span><span class="sxs-lookup"><span data-stu-id="73784-120">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="73784-121">In questa query viene usata la funzione [Members (Set) (MDX)](/sql/mdx/members-set-mdx) per restituire il set di membri della gerarchia dell'attributo Gender sull'asse delle colonne e questo set viene incrociato con il set di membri specificato della gerarchia dell'attributo Customer sull'asse delle righe.</span><span class="sxs-lookup"><span data-stu-id="73784-121">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="73784-122">Quando si esegue la query precedente, nella cella nel punto di intersezione tra Aaron A. Allen e Female viene visualizzato un valore null.</span><span class="sxs-lookup"><span data-stu-id="73784-122">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="73784-123">Analogamente, viene visualizzato un valore Null nella cella nel punto di intersezione tra Abigail Clark e Male.</span><span class="sxs-lookup"><span data-stu-id="73784-123">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="73784-124">Sebbene non esistano e non possano contenere valori, le celle inesistenti possono essere visualizzate nel risultato restituito da una query.</span><span class="sxs-lookup"><span data-stu-id="73784-124">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="73784-125">Quando si usa la funzione [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) per restituire il prodotto incrociato dei membri della gerarchia dell'attributo dalle gerarchie dell'attributo nella stessa dimensione, Auto Exist limita le tuple da restituire al set di tuple effettivamente esistenti, invece di restituire un prodotto cartesiano completo.</span><span class="sxs-lookup"><span data-stu-id="73784-125">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="73784-126">Ad esempio, eseguire e quindi esaminare i risultati dell'esecuzione della query seguente.</span><span class="sxs-lookup"><span data-stu-id="73784-126">For example, run and then examine the results from the execution of the following query.</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[State-Province].Members  
  ) ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="73784-127">Si noti che per designare l'asse delle colonne viene utilizzato 0, la forma abbreviata per Axis(0), indicante l'asse delle colonne.</span><span class="sxs-lookup"><span data-stu-id="73784-127">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="73784-128">La query precedente restituisce solo le celle dei membri di ogni gerarchia dell'attributo della query che esistono in ogni livello superiore.</span><span class="sxs-lookup"><span data-stu-id="73784-128">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="73784-129">La query precedente può anche essere scritta con la nuova variante \* della funzione [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="73784-129">The previous query can also be written using the new \* variant of the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="73784-130">La query precedente può anche essere scritta nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="73784-130">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="73784-131">I valori delle celle restituiti saranno identici, sebbene i metadati nel set di risultati saranno diversi.</span><span class="sxs-lookup"><span data-stu-id="73784-131">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="73784-132">Con la query precedente, ad esempio, la gerarchia Country è stata spostata sull'asse di sezionamento (nella clausola WHERE) e pertanto non viene visualizzata in modo esplicito nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="73784-132">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="73784-133">Ognuna di queste tre query precedenti dimostra l'effetto del comportamento di auto exist in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73784-133">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="deep-and-shallow-autoexists"></a><span data-ttu-id="73784-134">Auto Exist completo e superficiale</span><span class="sxs-lookup"><span data-stu-id="73784-134">Deep and Shallow Autoexists</span></span>  
 <span data-ttu-id="73784-135">La caratteristica Auto Exist può essere applicata in modo completo o superficiale alle espressioni.</span><span class="sxs-lookup"><span data-stu-id="73784-135">Autoexists can be applied to the expressions as Deep or Shallow.</span></span> <span data-ttu-id="73784-136">`Deep Autoexists` significa che tutte le espressioni verranno valutate per soddisfare lo spazio più completo possibile dopo l'applicazione delle espressioni di sezionamento, delle espressioni sub-SELECT nell'asse e così via.</span><span class="sxs-lookup"><span data-stu-id="73784-136">`Deep Autoexists` means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span> <span data-ttu-id="73784-137">`Shallow Autoexists` significa che espressioni esterne vengono valutate prima dell'espressione corrente e i risultati vengono specificati nell'espressione corrente.</span><span class="sxs-lookup"><span data-stu-id="73784-137">`Shallow Autoexists` means that external expressions are evaluated before the current expression and those results are passed to the current expression.</span></span> <span data-ttu-id="73784-138">Per impostazione predefinita la caratteristica Auto Exist viene applicata in modo completo.</span><span class="sxs-lookup"><span data-stu-id="73784-138">The default setting is deep autoexists.</span></span>  
  
 <span data-ttu-id="73784-139">Lo scenario e gli esempi riportati di seguito consentiranno di illustrare i tipi diversi di Auto Exist.</span><span class="sxs-lookup"><span data-stu-id="73784-139">The following scenario and samples will help to illustrate the different types of Autoexistss.</span></span> <span data-ttu-id="73784-140">Negli esempi riportati di seguito verranno creati due set, uno come espressione calcolata e l'altro come espressione costante.</span><span class="sxs-lookup"><span data-stu-id="73784-140">In the following examples two sets will be created: one as a calculated expression and the other as a constant expression.</span></span>  
  
 `//Obtain the Top 10 best reseller selling products by Name`  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="73784-141">Il set di risultati che si ottiene è il seguente:</span><span class="sxs-lookup"><span data-stu-id="73784-141">The obtained result set is:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="73784-142">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-142">**Reseller Sales Amount**</span></span>|<span data-ttu-id="73784-143">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-143">**Discount Amount**</span></span>|<span data-ttu-id="73784-144">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="73784-144">**PCT Discount**</span></span>|  
|<span data-ttu-id="73784-145">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="73784-145">**Mountain-200**</span></span>|<span data-ttu-id="73784-146">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="73784-146">**$14,356,699.36**</span></span>|<span data-ttu-id="73784-147">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="73784-147">**$19,012.71**</span></span>|<span data-ttu-id="73784-148">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="73784-148">**0.13%**</span></span>|  
|<span data-ttu-id="73784-149">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="73784-149">**Road-250**</span></span>|<span data-ttu-id="73784-150">**$9,377,457.68**</span><span class="sxs-lookup"><span data-stu-id="73784-150">**$9,377,457.68**</span></span>|<span data-ttu-id="73784-151">**$4,032.47**</span><span class="sxs-lookup"><span data-stu-id="73784-151">**$4,032.47**</span></span>|<span data-ttu-id="73784-152">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="73784-152">**0.04%**</span></span>|  
|<span data-ttu-id="73784-153">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="73784-153">**Mountain-100**</span></span>|<span data-ttu-id="73784-154">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="73784-154">**$8,568,958.27**</span></span>|<span data-ttu-id="73784-155">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="73784-155">**$139,393.27**</span></span>|<span data-ttu-id="73784-156">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="73784-156">**1.63%**</span></span>|  
|<span data-ttu-id="73784-157">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="73784-157">**Road-650**</span></span>|<span data-ttu-id="73784-158">**$7,442,141.81**</span><span class="sxs-lookup"><span data-stu-id="73784-158">**$7,442,141.81**</span></span>|<span data-ttu-id="73784-159">**$39,698.30**</span><span class="sxs-lookup"><span data-stu-id="73784-159">**$39,698.30**</span></span>|<span data-ttu-id="73784-160">**0.53%**</span><span class="sxs-lookup"><span data-stu-id="73784-160">**0.53%**</span></span>|  
|<span data-ttu-id="73784-161">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="73784-161">**Touring-1000**</span></span>|<span data-ttu-id="73784-162">**$6,723,794.29**</span><span class="sxs-lookup"><span data-stu-id="73784-162">**$6,723,794.29**</span></span>|<span data-ttu-id="73784-163">**$166,144.17**</span><span class="sxs-lookup"><span data-stu-id="73784-163">**$166,144.17**</span></span>|<span data-ttu-id="73784-164">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="73784-164">**2.47%**</span></span>|  
|<span data-ttu-id="73784-165">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="73784-165">**Road-550-W**</span></span>|<span data-ttu-id="73784-166">**$3,668,383.88**</span><span class="sxs-lookup"><span data-stu-id="73784-166">**$3,668,383.88**</span></span>|<span data-ttu-id="73784-167">**$1,901.97**</span><span class="sxs-lookup"><span data-stu-id="73784-167">**$1,901.97**</span></span>|<span data-ttu-id="73784-168">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="73784-168">**0.05%**</span></span>|  
|<span data-ttu-id="73784-169">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="73784-169">**Road-350-W**</span></span>|<span data-ttu-id="73784-170">**$3,665,932.31**</span><span class="sxs-lookup"><span data-stu-id="73784-170">**$3,665,932.31**</span></span>|<span data-ttu-id="73784-171">**$20,946.50**</span><span class="sxs-lookup"><span data-stu-id="73784-171">**$20,946.50**</span></span>|<span data-ttu-id="73784-172">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="73784-172">**0.57%**</span></span>|  
|<span data-ttu-id="73784-173">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="73784-173">**HL Mountain Frame**</span></span>|<span data-ttu-id="73784-174">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="73784-174">**$3,365,069.27**</span></span>|<span data-ttu-id="73784-175">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="73784-175">**$174.11**</span></span>|<span data-ttu-id="73784-176">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="73784-176">**0.01%**</span></span>|  
|<span data-ttu-id="73784-177">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="73784-177">**Road-150**</span></span>|<span data-ttu-id="73784-178">**$2,363,805.16**</span><span class="sxs-lookup"><span data-stu-id="73784-178">**$2,363,805.16**</span></span>|<span data-ttu-id="73784-179">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="73784-179">**$0.00**</span></span>|<span data-ttu-id="73784-180">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="73784-180">**0.00%**</span></span>|  
|<span data-ttu-id="73784-181">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="73784-181">**Touring-3000**</span></span>|<span data-ttu-id="73784-182">**$2,046,508.26**</span><span class="sxs-lookup"><span data-stu-id="73784-182">**$2,046,508.26**</span></span>|<span data-ttu-id="73784-183">**$79,582.15**</span><span class="sxs-lookup"><span data-stu-id="73784-183">**$79,582.15**</span></span>|<span data-ttu-id="73784-184">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="73784-184">**3.89%**</span></span>|  
  
 <span data-ttu-id="73784-185">Il set di prodotti ottenuto sembra uguale a Preferred10Products, riportato di seguito per verifica:</span><span class="sxs-lookup"><span data-stu-id="73784-185">The obtained set of products seems to be the same as Preferred10Products; so, verifying the Preferred10Products set:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="73784-186">In base ai risultati seguenti, i due set (Top10SellingProducts, Preferred10Products) sono identici</span><span class="sxs-lookup"><span data-stu-id="73784-186">As per the following results, both sets (Top10SellingProducts, Preferred10Products) are the same</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="73784-187">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-187">**Reseller Sales Amount**</span></span>|<span data-ttu-id="73784-188">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-188">**Discount Amount**</span></span>|<span data-ttu-id="73784-189">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="73784-189">**PCT Discount**</span></span>|  
|<span data-ttu-id="73784-190">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="73784-190">**Mountain-200**</span></span>|<span data-ttu-id="73784-191">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="73784-191">**$14,356,699.36**</span></span>|<span data-ttu-id="73784-192">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="73784-192">**$19,012.71**</span></span>|<span data-ttu-id="73784-193">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="73784-193">**0.13%**</span></span>|  
|<span data-ttu-id="73784-194">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="73784-194">**Road-250**</span></span>|<span data-ttu-id="73784-195">**$9,377,457.68**</span><span class="sxs-lookup"><span data-stu-id="73784-195">**$9,377,457.68**</span></span>|<span data-ttu-id="73784-196">**$4,032.47**</span><span class="sxs-lookup"><span data-stu-id="73784-196">**$4,032.47**</span></span>|<span data-ttu-id="73784-197">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="73784-197">**0.04%**</span></span>|  
|<span data-ttu-id="73784-198">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="73784-198">**Mountain-100**</span></span>|<span data-ttu-id="73784-199">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="73784-199">**$8,568,958.27**</span></span>|<span data-ttu-id="73784-200">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="73784-200">**$139,393.27**</span></span>|<span data-ttu-id="73784-201">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="73784-201">**1.63%**</span></span>|  
|<span data-ttu-id="73784-202">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="73784-202">**Road-650**</span></span>|<span data-ttu-id="73784-203">**$7,442,141.81**</span><span class="sxs-lookup"><span data-stu-id="73784-203">**$7,442,141.81**</span></span>|<span data-ttu-id="73784-204">**$39,698.30**</span><span class="sxs-lookup"><span data-stu-id="73784-204">**$39,698.30**</span></span>|<span data-ttu-id="73784-205">**0.53%**</span><span class="sxs-lookup"><span data-stu-id="73784-205">**0.53%**</span></span>|  
|<span data-ttu-id="73784-206">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="73784-206">**Touring-1000**</span></span>|<span data-ttu-id="73784-207">**$6,723,794.29**</span><span class="sxs-lookup"><span data-stu-id="73784-207">**$6,723,794.29**</span></span>|<span data-ttu-id="73784-208">**$166,144.17**</span><span class="sxs-lookup"><span data-stu-id="73784-208">**$166,144.17**</span></span>|<span data-ttu-id="73784-209">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="73784-209">**2.47%**</span></span>|  
|<span data-ttu-id="73784-210">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="73784-210">**Road-550-W**</span></span>|<span data-ttu-id="73784-211">**$3,668,383.88**</span><span class="sxs-lookup"><span data-stu-id="73784-211">**$3,668,383.88**</span></span>|<span data-ttu-id="73784-212">**$1,901.97**</span><span class="sxs-lookup"><span data-stu-id="73784-212">**$1,901.97**</span></span>|<span data-ttu-id="73784-213">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="73784-213">**0.05%**</span></span>|  
|<span data-ttu-id="73784-214">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="73784-214">**Road-350-W**</span></span>|<span data-ttu-id="73784-215">**$3,665,932.31**</span><span class="sxs-lookup"><span data-stu-id="73784-215">**$3,665,932.31**</span></span>|<span data-ttu-id="73784-216">**$20,946.50**</span><span class="sxs-lookup"><span data-stu-id="73784-216">**$20,946.50**</span></span>|<span data-ttu-id="73784-217">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="73784-217">**0.57%**</span></span>|  
|<span data-ttu-id="73784-218">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="73784-218">**HL Mountain Frame**</span></span>|<span data-ttu-id="73784-219">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="73784-219">**$3,365,069.27**</span></span>|<span data-ttu-id="73784-220">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="73784-220">**$174.11**</span></span>|<span data-ttu-id="73784-221">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="73784-221">**0.01%**</span></span>|  
|<span data-ttu-id="73784-222">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="73784-222">**Road-150**</span></span>|<span data-ttu-id="73784-223">**$2,363,805.16**</span><span class="sxs-lookup"><span data-stu-id="73784-223">**$2,363,805.16**</span></span>|<span data-ttu-id="73784-224">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="73784-224">**$0.00**</span></span>|<span data-ttu-id="73784-225">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="73784-225">**0.00%**</span></span>|  
|<span data-ttu-id="73784-226">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="73784-226">**Touring-3000**</span></span>|<span data-ttu-id="73784-227">**$2,046,508.26**</span><span class="sxs-lookup"><span data-stu-id="73784-227">**$2,046,508.26**</span></span>|<span data-ttu-id="73784-228">**$79,582.15**</span><span class="sxs-lookup"><span data-stu-id="73784-228">**$79,582.15**</span></span>|<span data-ttu-id="73784-229">**3,89%**</span><span class="sxs-lookup"><span data-stu-id="73784-229">**3.89%**</span></span>|  
  
 <span data-ttu-id="73784-230">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="73784-230">The following example will illustrate the concept of deep Autoexists.</span></span> <span data-ttu-id="73784-231">Nell'esempio si filtra Top10SellingProducts in base all'attributo [Product].[Product Line] per i membri del gruppo [Mountain].</span><span class="sxs-lookup"><span data-stu-id="73784-231">In the example we are filtering Top10SellingProducts by [Product].[Product Line] attribute for those in [Mountain] group.</span></span> <span data-ttu-id="73784-232">Si noti che entrambi gli attributi (sezionamento e asse) appartengono alla stessa dimensione, [Product].</span><span class="sxs-lookup"><span data-stu-id="73784-232">Note that both attributes (slicer and axis) belong to the same dimension, [Product].</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `// Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="73784-233">Viene prodotto il set di risultati seguente:</span><span class="sxs-lookup"><span data-stu-id="73784-233">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="73784-234">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-234">**Reseller Sales Amount**</span></span>|<span data-ttu-id="73784-235">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-235">**Discount Amount**</span></span>|<span data-ttu-id="73784-236">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="73784-236">**PCT Discount**</span></span>|  
|<span data-ttu-id="73784-237">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="73784-237">**Mountain-200**</span></span>|<span data-ttu-id="73784-238">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="73784-238">**$14,356,699.36**</span></span>|<span data-ttu-id="73784-239">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="73784-239">**$19,012.71**</span></span>|<span data-ttu-id="73784-240">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="73784-240">**0.13%**</span></span>|  
|<span data-ttu-id="73784-241">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="73784-241">**Mountain-100**</span></span>|<span data-ttu-id="73784-242">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="73784-242">**$8,568,958.27**</span></span>|<span data-ttu-id="73784-243">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="73784-243">**$139,393.27**</span></span>|<span data-ttu-id="73784-244">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="73784-244">**1.63%**</span></span>|  
|<span data-ttu-id="73784-245">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="73784-245">**HL Mountain Frame**</span></span>|<span data-ttu-id="73784-246">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="73784-246">**$3,365,069.27**</span></span>|<span data-ttu-id="73784-247">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="73784-247">**$174.11**</span></span>|<span data-ttu-id="73784-248">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="73784-248">**0.01%**</span></span>|  
|<span data-ttu-id="73784-249">**Mountain-300**</span><span class="sxs-lookup"><span data-stu-id="73784-249">**Mountain-300**</span></span>|<span data-ttu-id="73784-250">**$1,907,249.38**</span><span class="sxs-lookup"><span data-stu-id="73784-250">**$1,907,249.38**</span></span>|<span data-ttu-id="73784-251">**$876.95**</span><span class="sxs-lookup"><span data-stu-id="73784-251">**$876.95**</span></span>|<span data-ttu-id="73784-252">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="73784-252">**0.05%**</span></span>|  
|<span data-ttu-id="73784-253">**Mountain-500**</span><span class="sxs-lookup"><span data-stu-id="73784-253">**Mountain-500**</span></span>|<span data-ttu-id="73784-254">**$1,067,327.31**</span><span class="sxs-lookup"><span data-stu-id="73784-254">**$1,067,327.31**</span></span>|<span data-ttu-id="73784-255">**$17,266.09**</span><span class="sxs-lookup"><span data-stu-id="73784-255">**$17,266.09**</span></span>|<span data-ttu-id="73784-256">**1,62%**</span><span class="sxs-lookup"><span data-stu-id="73784-256">**1.62%**</span></span>|  
|<span data-ttu-id="73784-257">**Mountain-400-W**</span><span class="sxs-lookup"><span data-stu-id="73784-257">**Mountain-400-W**</span></span>|<span data-ttu-id="73784-258">**$592,450.05**</span><span class="sxs-lookup"><span data-stu-id="73784-258">**$592,450.05**</span></span>|<span data-ttu-id="73784-259">**$303.49**</span><span class="sxs-lookup"><span data-stu-id="73784-259">**$303.49**</span></span>|<span data-ttu-id="73784-260">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="73784-260">**0.05%**</span></span>|  
|<span data-ttu-id="73784-261">**LL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="73784-261">**LL Mountain Frame**</span></span>|<span data-ttu-id="73784-262">**$521,864.42**</span><span class="sxs-lookup"><span data-stu-id="73784-262">**$521,864.42**</span></span>|<span data-ttu-id="73784-263">**$252.41**</span><span class="sxs-lookup"><span data-stu-id="73784-263">**$252.41**</span></span>|<span data-ttu-id="73784-264">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="73784-264">**0.05%**</span></span>|  
|<span data-ttu-id="73784-265">**ML Mountain Frame-W**</span><span class="sxs-lookup"><span data-stu-id="73784-265">**ML Mountain Frame-W**</span></span>|<span data-ttu-id="73784-266">**$482,953.16**</span><span class="sxs-lookup"><span data-stu-id="73784-266">**$482,953.16**</span></span>|<span data-ttu-id="73784-267">**$206.95**</span><span class="sxs-lookup"><span data-stu-id="73784-267">**$206.95**</span></span>|<span data-ttu-id="73784-268">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="73784-268">**0.04%**</span></span>|  
|<span data-ttu-id="73784-269">**ML Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="73784-269">**ML Mountain Frame**</span></span>|<span data-ttu-id="73784-270">**$343,785.29**</span><span class="sxs-lookup"><span data-stu-id="73784-270">**$343,785.29**</span></span>|<span data-ttu-id="73784-271">**$161.82**</span><span class="sxs-lookup"><span data-stu-id="73784-271">**$161.82**</span></span>|<span data-ttu-id="73784-272">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="73784-272">**0.05%**</span></span>|  
|<span data-ttu-id="73784-273">**Women's Mountain Shorts**</span><span class="sxs-lookup"><span data-stu-id="73784-273">**Women's Mountain Shorts**</span></span>|<span data-ttu-id="73784-274">**$260,304.09**</span><span class="sxs-lookup"><span data-stu-id="73784-274">**$260,304.09**</span></span>|<span data-ttu-id="73784-275">**$6,675.56**</span><span class="sxs-lookup"><span data-stu-id="73784-275">**$6,675.56**</span></span>|<span data-ttu-id="73784-276">**2,56%**</span><span class="sxs-lookup"><span data-stu-id="73784-276">**2.56%**</span></span>|  
  
 <span data-ttu-id="73784-277">Nel set di risultati precedente si registrano sette nuove presenze nell'elenco Top10SellingProducts, mentre Mountain-200, Mountain-100 e HL Mountain Frame sono stati spostati all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="73784-277">In the above result set we have seven newcomers to the list of Top10SellingProducts and Mountain-200, Mountain-100, and HL Mountain Frame have moved to the top of the list.</span></span> <span data-ttu-id="73784-278">Questi tre valori sono frammisti.</span><span class="sxs-lookup"><span data-stu-id="73784-278">In the previous result set those three values were interspersed.</span></span>  
  
 <span data-ttu-id="73784-279">Questa caratteristica viene denominata Auto Exist completa perché il set Top10SellingProducts viene valutato per soddisfare le condizioni di sezionamento della query.</span><span class="sxs-lookup"><span data-stu-id="73784-279">This is called Deep Autoexists, because the Top10SellingProducts set is evaluated to meet the slicing conditions of the query.</span></span> <span data-ttu-id="73784-280">Auto Exist completo significa che tutte le espressioni verranno valutate per soddisfare lo spazio più completo possibile dopo l'applicazioni delle espressioni di sezionamento, delle espressioni sub-SELECT nell'asse e così via.</span><span class="sxs-lookup"><span data-stu-id="73784-280">Deep Autoexists means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span>  
  
 <span data-ttu-id="73784-281">Tuttavia, è possibile decidere di eseguire l'analisi su Top10SellingProducts, in quanto equivalente a Preferred10Products, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="73784-281">However, one might want to be able to do the analysis over the Top10SellingProducts as equivalent to Preferred10Products, as in the following example:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="73784-282">Viene prodotto il set di risultati seguente:</span><span class="sxs-lookup"><span data-stu-id="73784-282">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="73784-283">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-283">**Reseller Sales Amount**</span></span>|<span data-ttu-id="73784-284">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-284">**Discount Amount**</span></span>|<span data-ttu-id="73784-285">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="73784-285">**PCT Discount**</span></span>|  
|<span data-ttu-id="73784-286">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="73784-286">**Mountain-200**</span></span>|<span data-ttu-id="73784-287">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="73784-287">**$14,356,699.36**</span></span>|<span data-ttu-id="73784-288">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="73784-288">**$19,012.71**</span></span>|<span data-ttu-id="73784-289">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="73784-289">**0.13%**</span></span>|  
|<span data-ttu-id="73784-290">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="73784-290">**Mountain-100**</span></span>|<span data-ttu-id="73784-291">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="73784-291">**$8,568,958.27**</span></span>|<span data-ttu-id="73784-292">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="73784-292">**$139,393.27**</span></span>|<span data-ttu-id="73784-293">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="73784-293">**1.63%**</span></span>|  
|<span data-ttu-id="73784-294">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="73784-294">**HL Mountain Frame**</span></span>|<span data-ttu-id="73784-295">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="73784-295">**$3,365,069.27**</span></span>|<span data-ttu-id="73784-296">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="73784-296">**$174.11**</span></span>|<span data-ttu-id="73784-297">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="73784-297">**0.01%**</span></span>|  
  
 <span data-ttu-id="73784-298">Nei risultati precedenti il sezionamento fornisce un risultato che contiene solo i prodotti dell'elenco Preferred10Products che fanno parte del gruppo [Mountain] in [Product].[Product Line], come previsto, in quanto Preferred10Products è un'espressione costante.</span><span class="sxs-lookup"><span data-stu-id="73784-298">In the above results, the slicing gives a result that contains only those products from Preferred10Products that are part of the [Mountain] group in [Product].[Product Line]; as expected, because Preferred10Products is a constant expression.</span></span>  
  
 <span data-ttu-id="73784-299">Questo set di risultati viene interpretato anche come Auto Exist superficiale,</span><span class="sxs-lookup"><span data-stu-id="73784-299">This result set is also understood as Shallow Autoexists.</span></span> <span data-ttu-id="73784-300">in quanto l'espressione viene valutata prima della clausola di sezionamento.</span><span class="sxs-lookup"><span data-stu-id="73784-300">This is because the expression is evaluated before the slicing clause.</span></span> <span data-ttu-id="73784-301">Nell'esempio precedente, l'espressione è un'espressione costante a scopo illustrativo, al fine di presentare il concetto.</span><span class="sxs-lookup"><span data-stu-id="73784-301">In the previous example, the expression was a constant expression for illustration purposes in order to introduce the concept.</span></span>  
  
 <span data-ttu-id="73784-302">Il comportamento di Auto Exist può essere modificato a livello di sessione utilizzando la proprietà della stringa di connessione `Autoexists`.</span><span class="sxs-lookup"><span data-stu-id="73784-302">Autoexists behavior can be modified at the session level using the `Autoexists` connection string property.</span></span> <span data-ttu-id="73784-303">L'esempio seguente inizia con l'apertura di una nuova sessione e l'aggiunta della proprietà *Autoexists=3* alla stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="73784-303">The following example begins by opening a new session and adding the *Autoexists=3* property to the connection string.</span></span> <span data-ttu-id="73784-304">Per eseguire l'esempio, è necessario aprire una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="73784-304">You must open a new connection in order to do the example.</span></span> <span data-ttu-id="73784-305">Una volta stabilita la connessione con l'impostazione Auto Exist, quest'ultima rimarrà effettiva fino al termine della connessione.</span><span class="sxs-lookup"><span data-stu-id="73784-305">Once the connection is established with the Autoexist setting it will remain in effect until that connection is finished.</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `//Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="73784-306">Nel set di risultati seguente è illustrato il comportamento superficiale di Auto Exist.</span><span class="sxs-lookup"><span data-stu-id="73784-306">The following result set now shows the shallow behavior of Autoexists.</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="73784-307">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-307">**Reseller Sales Amount**</span></span>|<span data-ttu-id="73784-308">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="73784-308">**Discount Amount**</span></span>|<span data-ttu-id="73784-309">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="73784-309">**PCT Discount**</span></span>|  
|<span data-ttu-id="73784-310">**Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="73784-310">**Mountain-200**</span></span>|<span data-ttu-id="73784-311">**$14,356,699.36**</span><span class="sxs-lookup"><span data-stu-id="73784-311">**$14,356,699.36**</span></span>|<span data-ttu-id="73784-312">**$19,012.71**</span><span class="sxs-lookup"><span data-stu-id="73784-312">**$19,012.71**</span></span>|<span data-ttu-id="73784-313">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="73784-313">**0.13%**</span></span>|  
|<span data-ttu-id="73784-314">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="73784-314">**Mountain-100**</span></span>|<span data-ttu-id="73784-315">**$8,568,958.27**</span><span class="sxs-lookup"><span data-stu-id="73784-315">**$8,568,958.27**</span></span>|<span data-ttu-id="73784-316">**$139,393.27**</span><span class="sxs-lookup"><span data-stu-id="73784-316">**$139,393.27**</span></span>|<span data-ttu-id="73784-317">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="73784-317">**1.63%**</span></span>|  
|<span data-ttu-id="73784-318">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="73784-318">**HL Mountain Frame**</span></span>|<span data-ttu-id="73784-319">**$3,365,069.27**</span><span class="sxs-lookup"><span data-stu-id="73784-319">**$3,365,069.27**</span></span>|<span data-ttu-id="73784-320">**$174.11**</span><span class="sxs-lookup"><span data-stu-id="73784-320">**$174.11**</span></span>|<span data-ttu-id="73784-321">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="73784-321">**0.01%**</span></span>|  
  
 <span data-ttu-id="73784-322">Il comportamento di Auto Exist può essere modificato utilizzando il parametro auto EXISTs = [1 | 2 | 3] nella stringa di connessione. vedere [Proprietà XMLA supportate &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) e <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> per l'utilizzo dei parametri.</span><span class="sxs-lookup"><span data-stu-id="73784-322">Autoexists behavior can be modified by using the AUTOEXISTS=[1|2|3] parameter in the connection string; see [Supported XMLA Properties &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) and <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> for parameter usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73784-323">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73784-323">See Also</span></span>  
 <span data-ttu-id="73784-324">[Concetti chiave di MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="73784-324">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="73784-325">[Spazio del cubo](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="73784-325">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="73784-326">[Tuple](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="73784-326">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="73784-327">[Utilizzo di membri, Tuple e set &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="73784-327">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="73784-328">[Totali visivi e totali non visualizzati](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="73784-328">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="73784-329">[Guida di riferimento al linguaggio MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="73784-329">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="73784-330">Guida di riferimento a MDX &#40;Multidimensional Expressions&#41;</span><span class="sxs-lookup"><span data-stu-id="73784-330">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
