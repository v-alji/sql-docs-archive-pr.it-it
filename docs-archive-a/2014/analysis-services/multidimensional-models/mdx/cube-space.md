---
title: Spazio del cubo | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c3a012b4-9ca0-4fb8-9c26-5ecc0e2e2b2b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6a6da73815f06aa5ab80f6ad5a9d06227ed842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627448"
---
# <a name="cube-space"></a><span data-ttu-id="f9eac-102">Spazio del cubo</span><span class="sxs-lookup"><span data-stu-id="f9eac-102">Cube Space</span></span>
  <span data-ttu-id="f9eac-103">Lo spazio del cubo è il prodotto dei membri delle gerarchie dell'attributo di un cubo per le misure del cubo.</span><span class="sxs-lookup"><span data-stu-id="f9eac-103">Cube space is the product of the members of a cube's attribute hierarchies with the cube's measures.</span></span> <span data-ttu-id="f9eac-104">Quindi lo spazio del cubo è determinato dal prodotto combinatorio di tutti i membri della gerarchia dell'attributo nel cubo e delle misure del cubo e definisce la dimensione massima del cubo.</span><span class="sxs-lookup"><span data-stu-id="f9eac-104">Therefore, the cube space is determined by the combinatorial product of all attribute hierarchy members in the cube and the cube's measures and defines the maximum size of the cube.</span></span> <span data-ttu-id="f9eac-105">È importante sottolineare che questo spazio comprende tutte le possibili combinazioni di membri della gerarchia dell'attributo, anche combinazioni che si possono considerare impossibili nel mondo reale, ad esempio combinazioni in cui la città è Parigi e i paesi sono Inghilterra o Spagna o Giappone o India o altro.</span><span class="sxs-lookup"><span data-stu-id="f9eac-105">It is important to note that this space includes all possible combinations of attribute hierarchy members; even combinations that might be deem as impossible in the real world i.e. combinations where the city is Paris and the countries are England or Spain or Japan or India or elsewhere.</span></span>  
  
## <a name="autoexists-and-cube-space"></a><span data-ttu-id="f9eac-106">Spazio del cubo e Auto Exist</span><span class="sxs-lookup"><span data-stu-id="f9eac-106">Autoexists and cube space</span></span>  
 <span data-ttu-id="f9eac-107">Il concetto di *Auto Exist* limita questo spazio del cubo alle celle effettivamente esistenti.</span><span class="sxs-lookup"><span data-stu-id="f9eac-107">The concept of *autoexists* limits this cube space to those cells that actually exist.</span></span> <span data-ttu-id="f9eac-108">È possibile che membri di una gerarchia dell'attributo non contengano membri di un'altra gerarchia dell'attributo nella stessa dimensione.</span><span class="sxs-lookup"><span data-stu-id="f9eac-108">Members of an attribute hierarchy in a dimension may not exist with members of another attribute hierarchy in the same dimension.</span></span>  
  
 <span data-ttu-id="f9eac-109">Se, ad esempio, si dispone di un cubo con una gerarchia dell'attributo City, una gerarchia dell'attributo Country e una misura Internet Sales Amount, lo spazio di questo cubo include solo i membri che esistono in ogni livello superiore.</span><span class="sxs-lookup"><span data-stu-id="f9eac-109">For example, if you have a cube that has a City attribute hierarchy, a Country attribute hierarchy, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="f9eac-110">Se, ad esempio, la gerarchia dell'attributo City include le città di New York, London, Paris, Tokyo e Melbourne e la gerarchia dell'attributo Country include i paesi Stati Uniti, United Kingdom, France, Japan e Australia, lo spazio del cubo non include lo spazio (cella) nel punto di intersezione tra Paris e Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="f9eac-110">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="f9eac-111">Quando si esegue una query su celle inesistenti, tali celle restituiscono valori Null, cioè non possono contenere calcoli e non è possibile definire un calcolo esegua operazioni di scrittura in questo spazio.</span><span class="sxs-lookup"><span data-stu-id="f9eac-111">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="f9eac-112">L'istruzione seguente, ad esempio, include celle che non esistono.</span><span class="sxs-lookup"><span data-stu-id="f9eac-112">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f9eac-113">In questa query viene usata la funzione [Members (Set) (MDX)](/sql/mdx/members-set-mdx) per restituire il set di membri della gerarchia dell'attributo Gender sull'asse delle colonne e questo set viene incrociato con il set di membri specificato della gerarchia dell'attributo Customer sull'asse delle righe.</span><span class="sxs-lookup"><span data-stu-id="f9eac-113">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="f9eac-114">Quando si esegue la query precedente, nella cella nel punto di intersezione tra Aaron A. Allen e Female viene visualizzato un valore null.</span><span class="sxs-lookup"><span data-stu-id="f9eac-114">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="f9eac-115">Analogamente, viene visualizzato un valore Null nella cella nel punto di intersezione tra Abigail Clark e Male.</span><span class="sxs-lookup"><span data-stu-id="f9eac-115">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="f9eac-116">Sebbene non esistano e non possano contenere valori, le celle inesistenti possono essere visualizzate nel risultato restituito da una query.</span><span class="sxs-lookup"><span data-stu-id="f9eac-116">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="f9eac-117">Quando si usa la funzione [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) per restituire il prodotto incrociato dei membri della gerarchia dell'attributo dalle gerarchie dell'attributo nella stessa dimensione, Auto Exist limita le tuple da restituire al set di tuple effettivamente esistenti, invece di restituire un prodotto cartesiano completo.</span><span class="sxs-lookup"><span data-stu-id="f9eac-117">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="f9eac-118">Ad esempio, eseguire e quindi esaminare i risultati dell'esecuzione della query seguente.</span><span class="sxs-lookup"><span data-stu-id="f9eac-118">For example, run and then examine the results from the execution of the following query.</span></span>  
  
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
>  <span data-ttu-id="f9eac-119">Si noti che per designare l'asse delle colonne viene utilizzato 0, la forma abbreviata per Axis(0), indicante l'asse delle colonne.</span><span class="sxs-lookup"><span data-stu-id="f9eac-119">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="f9eac-120">La query precedente restituisce solo le celle dei membri di ogni gerarchia dell'attributo della query che esistono in ogni livello superiore.</span><span class="sxs-lookup"><span data-stu-id="f9eac-120">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="f9eac-121">La query precedente può anche essere scritta con la nuova variante \* della funzione [ \* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="f9eac-121">The previous query can also be written using the new \* variant of the [\* (Crossjoin) (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="f9eac-122">La query precedente può anche essere scritta nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f9eac-122">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="f9eac-123">I valori delle celle restituiti saranno identici, sebbene i metadati nel set di risultati saranno diversi.</span><span class="sxs-lookup"><span data-stu-id="f9eac-123">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="f9eac-124">Con la query precedente, ad esempio, la gerarchia Country è stata spostata sull'asse di sezionamento (nella clausola WHERE) e pertanto non viene visualizzata in modo esplicito nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="f9eac-124">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="f9eac-125">Ognuna di queste tre query precedenti dimostra l'effetto del comportamento di auto exist in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9eac-125">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="user-defined-hierarchies-and-cube-space"></a><span data-ttu-id="f9eac-126">Gerarchie definite dall'utente e spazio del cubo</span><span class="sxs-lookup"><span data-stu-id="f9eac-126">User-Defined Hierarchies and Cube Space</span></span>  
 <span data-ttu-id="f9eac-127">Negli esempi precedenti di questo argomento vengono definite le posizioni nello spazio del cubo utilizzando le gerarchie dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f9eac-127">The previous examples in this topic define positions in cube space by using attribute hierarchies.</span></span> <span data-ttu-id="f9eac-128">È tuttavia possibile definire una posizione nello spazio del cubo anche utilizzando gerarchie definite dall'utente in base alle gerarchie dell'attributo in una dimensione.</span><span class="sxs-lookup"><span data-stu-id="f9eac-128">However, you can also define a position in cube space by using user-defined hierarchies that have been defined based on attribute hierarchies in a dimension.</span></span> <span data-ttu-id="f9eac-129">Una gerarchia definita dall'utente è una gerarchia di gerarchie dell'attributo utilizzata per facilitare l'esplorazione dei dati del cubo da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="f9eac-129">A user-defined hierarchy is a hierarchy of attribute hierarchies designed to facilitate browsing of cube data by users.</span></span>  
  
 <span data-ttu-id="f9eac-130">È ad esempio possibile scrivere la query `CROSSJOIN` della sezione precedente anche come segue:</span><span class="sxs-lookup"><span data-stu-id="f9eac-130">For example, the `CROSSJOIN` query in the previous section could also have been written as follows:</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[Customer Geography].[State-Province].Members  
   )   
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="f9eac-131">Nella query precedente la gerarchia definita dall'utente Customer Geography all'interno della dimensione Customer viene utilizzata per definire la posizione nello spazio del cubo definita in precedenza utilizzando una gerarchia dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f9eac-131">In the previous query, the Customer Geography user-defined hierarchy within the Customer dimension is used to define the position in cube space that was previously defined by using an attribute hierarchy.</span></span> <span data-ttu-id="f9eac-132">La medesima posizione nello spazio del cubo può essere definita utilizzando gerarchie dell'attributo o gerarchie definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f9eac-132">The identical position in cube space can be defined by using either attribute hierarchies or user-defined hierarchies.</span></span>  
  
##  <a name="attribute-relationships-and-cube-space"></a><a name="AttribRelationships"></a> <span data-ttu-id="f9eac-133">Relazioni tra attributi e spazio del cubo</span><span class="sxs-lookup"><span data-stu-id="f9eac-133">Attribute Relationships and Cube Space</span></span>  
 <span data-ttu-id="f9eac-134">La definizione delle relazioni tra attributi correlati migliora le prestazioni delle query (facilitando la creazione di aggregazioni appropriate) e influisce sul membro di una gerarchia dell'attributo correlata che include un membro della gerarchia dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f9eac-134">Defining attribute relationships between related attributes improves query performance (by facilitating the creation of appropriate aggregations) and affects the member of a related attribute hierarchy that appears with an attribute hierarchy member.</span></span> <span data-ttu-id="f9eac-135">Quando, ad esempio, si definisce una tupla che include un membro della gerarchia dell'attributo City e la tupla non definisce in modo esplicito il membro della gerarchia dell'attributo Country, ci si potrebbe aspettare che il membro predefinito della gerarchia dell'attributo Country fosse il membro correlato della gerarchia dell'attributo Country.</span><span class="sxs-lookup"><span data-stu-id="f9eac-135">For example, when you define a tuple that includes a member from the City attribute hierarchy and the tuple does not explicitly define the Country attribute hierarchy member, you might expect that the default Country attribute hierarchy member would be the related member of the Country attribute hierarchy.</span></span> <span data-ttu-id="f9eac-136">Questo tuttavia si verifica solo se tra la gerarchia dell'attributo City e la gerarchia dell'attributo Country è definita una relazione tra attributi.</span><span class="sxs-lookup"><span data-stu-id="f9eac-136">However, this is only true if an attribute relationship is defined between the City attribute hierarchy and the Country attribute hierarchy.</span></span>  
  
 <span data-ttu-id="f9eac-137">Nell'esempio seguente viene restituito il membro di una gerarchia dell'attributo correlata non inclusa in modo esplicito nella query.</span><span class="sxs-lookup"><span data-stu-id="f9eac-137">The following example returns the member of a related attribute hierarchy that is not included explicitly in the query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Country.CurrentMember.Name  
SELECT Measures.x ON 0,  
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f9eac-138">Si noti che la `WITH` parola chiave viene utilizzata con le funzioni [CurrentMember (MDX)](/sql/mdx/current-mdx) e [Name (MDX)](/sql/mdx/members-string-mdx) per creare un membro calcolato da utilizzare nella query.</span><span class="sxs-lookup"><span data-stu-id="f9eac-138">Notice that the `WITH` keyword is used with the [CurrentMember (MDX)](/sql/mdx/current-mdx) and [Name (MDX)](/sql/mdx/members-string-mdx) functions to create a calculated member for use in the query.</span></span> <span data-ttu-id="f9eac-139">Per altre informazioni, vedere [Query MDX di base &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="f9eac-139">For more information, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
 <span data-ttu-id="f9eac-140">Nella query precedente, viene restituito il nome del membro della gerarchia dell'attributo Country associata a ogni membro della gerarchia dell'attributo State.</span><span class="sxs-lookup"><span data-stu-id="f9eac-140">In the previous query, the name of the member of the Country attribute hierarchy that is associated with each member of the State attribute hierarchy is returned.</span></span> <span data-ttu-id="f9eac-141">Viene visualizzato il membro Country previsto, perché tra gli attributi City e Country è definita una relazione.</span><span class="sxs-lookup"><span data-stu-id="f9eac-141">The expected Country member appears (because an attribute relationship is defined between the City and Country attributes).</span></span> <span data-ttu-id="f9eac-142">Se tuttavia tra le gerarchie dell'attributo della stessa dimensione non venisse definita alcuna relazione tra attributi, verrebbe restituito il membro (Totale), come illustrato nella query seguente.</span><span class="sxs-lookup"><span data-stu-id="f9eac-142">However, if no attribute relationship were defined between attribute hierarchies in the same dimension, the (All) member would be returned, as illustrated in the following query.</span></span>  
  
```  
WITH MEMBER Measures.x AS   
   Customer.Education.Currentmember.Name  
SELECT Measures.x  ON 0,   
Customer.City.Members ON 1  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="f9eac-143">Nella query precedente viene restituito il membro (Totale) ("All Customers"), perché non esiste alcuna relazione tra Education e City.</span><span class="sxs-lookup"><span data-stu-id="f9eac-143">In the previous query, the (All) member ("All Customers") is returned, because there is no relationship between Education and City.</span></span> <span data-ttu-id="f9eac-144">Pertanto, il membro (Totale) della gerarchia dell'attributo Education sarà il membro predefinito della gerarchia dell'attributo Education utilizzata in qualsiasi tupla con la gerarchia dell'attributo City dove nessun membro Education è specificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="f9eac-144">Therefore, the (All) member of the Education attribute hierarchy would be the default member of the Education attribute hierarchy used in any tuple involving the City attribute hierarchy where an Education member is not explicitly provided.</span></span>  
  
## <a name="calculation-context"></a><span data-ttu-id="f9eac-145">Contesto di calcolo</span><span class="sxs-lookup"><span data-stu-id="f9eac-145">Calculation Context</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9eac-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9eac-146">See Also</span></span>  
 <span data-ttu-id="f9eac-147">[Concetti chiave di MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f9eac-147">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="f9eac-148">[Tuple](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="f9eac-148">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="f9eac-149">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="f9eac-149">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="f9eac-150">[Utilizzo di membri, Tuple e set &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="f9eac-150">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="f9eac-151">[Totali visivi e totali non visualizzati](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="f9eac-151">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="f9eac-152">[Guida di riferimento al linguaggio MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="f9eac-152">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="f9eac-153">Guida di riferimento a MDX &#40;Multidimensional Expressions&#41;</span><span class="sxs-lookup"><span data-stu-id="f9eac-153">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
