---
title: Contesto di calcolo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aec8aa98-b77d-4f8f-9684-2618b1d8e970
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6d14df51c6ec37fb96520af7acf207227ae4ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716892"
---
# <a name="calculation-context"></a><span data-ttu-id="49683-102">Contesto di calcolo</span><span class="sxs-lookup"><span data-stu-id="49683-102">Calculation Context</span></span>
  <span data-ttu-id="49683-103">Il contesto di calcolo è il sottospazio noto del cubo in cui viene valutata un'espressione e in cui tutte le coordinate sono note in modo esplicito o si possono derivare dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="49683-103">The calculation context is the known subspace of the cube where an expression is evaluated and all coordinates are either explicitly known or can be derived from the expression.</span></span>  
  
## <a name="determining-the-calculation-context"></a><span data-ttu-id="49683-104">Determinazione del contesto di calcolo</span><span class="sxs-lookup"><span data-stu-id="49683-104">Determining the calculation context</span></span>  
 <span data-ttu-id="49683-105">Ogni set, membro, tupla o funzione numerica viene eseguita nel contesto dell'intera istruzione o espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="49683-105">Every set, member, tuple, or numeric function executes in the context of the entire MDX expression or statement.</span></span> <span data-ttu-id="49683-106">Quando un argomento, ad esempio una tupla, viene passato a una funzione, vengono specificate in modo esplicito solo alcune delle coordinate dello spazio del cubo.</span><span class="sxs-lookup"><span data-stu-id="49683-106">When an argument, such as a tuple, is passed to a function, only some of the coordinates in the cube space are explicitly provided.</span></span> <span data-ttu-id="49683-107">Le altre coordinate vengono ottenute in base al contesto di calcolo corrente.</span><span class="sxs-lookup"><span data-stu-id="49683-107">The other coordinates are obtained based on the current calculation context.</span></span>  
  
 <span data-ttu-id="49683-108">Il contesto di calcolo per le coordinate di celle e i membri dell'attributo non specificati viene determinato nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="49683-108">The calculation context for unspecified cell coordinates and attribute members is determined in the following order:</span></span>  
  
1.  <span data-ttu-id="49683-109">Clausola FROM (se applicabile): questa clausola consente di specificare un intero cubo o un sottocubo sotto forma di istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="49683-109">The FROM clause (if applicable) - this clause can either specify an entire cube or can specify a subcube in the form of a SELECT statement.</span></span>  
  
2.  <span data-ttu-id="49683-110">Clausola WHERE (se applicabile): clausola, anche nota come *asse di sezionamento*, in cui si specifica un set, una tupla o un membro che limita i membri restituiti sull'asse delle colonne e delle righe da una query.</span><span class="sxs-lookup"><span data-stu-id="49683-110">The WHERE clause (if applicable) - this clause, which is also known as the *slicer axis*, on which you specify a set, tuple, or member that restricts the members returned on the column and row axis by a query.</span></span> <span data-ttu-id="49683-111">Concettualmente, il membro predefinito di ogni gerarchia dell'attributo non specificato in modo esplicito sull'asse delle colonne o delle righe fa parte dell'asse di sezionamento.</span><span class="sxs-lookup"><span data-stu-id="49683-111">Conceptually, the default member of every attribute hierarchy that is not explicitly specified on column or row axis is part of the slicer axis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49683-112">Quando le coordinate di celle per un determinato attributo vengono specificate sia sull'asse di sezionamento che su un altro asse, è possibile che le coordinate specificate nella funzione abbiano la precedenza nel determinare i membri del set sull'asse.</span><span class="sxs-lookup"><span data-stu-id="49683-112">When cell coordinates for a particular attribute are specified on both the slicer axis and on another axis, the coordinates specified in the function may take precedence in determining the members of the set on the axis.</span></span> <span data-ttu-id="49683-113">[Filter (MDX)](/sql/mdx/filter-mdx) e [Order (MDX)](/sql/mdx/order-mdx) sono esempi di tali funzioni. È possibile filtrare o ordinare un risultato in base ai membri dell'attributo esclusi dal contesto di calcolo dalla clausola WHERE o da un'istruzione SELECT nella clausola FROM.</span><span class="sxs-lookup"><span data-stu-id="49683-113">The [Filter (MDX)](/sql/mdx/filter-mdx) and [Order (MDX)](/sql/mdx/order-mdx) functions are examples of such functions - you can filter or order a result by attribute members that are excluded from the calculation context by the WHERE clause, or by a SELECT statement in the FROM clause.</span></span>  
  
3.  <span data-ttu-id="49683-114">Set denominati e membri calcolati definiti nella query o nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="49683-114">The named sets and calculated members defined in the query or expression.</span></span>  
  
4.  <span data-ttu-id="49683-115">Tuple e set specificati sugli assi delle righe e delle colonne, utilizzando il membro predefinito per gli attributi non inclusi nell'asse delle righe, delle colonne o di sezionamento.</span><span class="sxs-lookup"><span data-stu-id="49683-115">The tuples and sets specified on the row and column axes, utilizing the default member for attributes that do not appear on the row, column, or slicer axis.</span></span>  
  
5.  <span data-ttu-id="49683-116">Celle del cubo o del sottocubo su ogni asse, eliminando le tuple vuote sull'asse e applicando la clausola HAVING.</span><span class="sxs-lookup"><span data-stu-id="49683-116">The cube or subcube cells on each axis, eliminating empty tuples on the axis and applying the HAVING clause.</span></span>  
  
6.  <span data-ttu-id="49683-117">Per altre informazioni, vedere [Definizione del contesto di cubo in una query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="49683-117">For more information, see [Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md).</span></span>  
  
 <span data-ttu-id="49683-118">Nella query seguente il contesto di calcolo per l'asse delle righe viene limitato dal membro dell'attributo Country e dal membro dell'attributo Calendar Year specificati nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="49683-118">In the following query, the calculation context for the row axis is restricted by the Country attribute member and the Calendar Year attribute member that are specified in the WHERE clause.</span></span>  
  
```  
SELECT Customer.City.City.Members ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France, [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="49683-119">Se, tuttavia, si modifica questa query specificando la funzione `FILTER` sull'asse delle righe e si utilizza un membro della gerarchia dell'attributo Calendar Year nella funzione `FILTER`, è possibile modificare il membro dell'attributo della gerarchia dell'attributo Calendar Year utilizzato per specificare il contesto di calcolo per i membri del set sull'asse delle righe.</span><span class="sxs-lookup"><span data-stu-id="49683-119">However, if you modify this query by specifying the `FILTER` function on the row axis, and utilize a Calendar Year attribute hierarchy member in the `FILTER` function, then the attribute member from the Calendar Year attribute hierarchy that is used to provide the calculation context for the members of the set on the column axis can be modified.</span></span>  
  
```  
SELECT FILTER  
   (  
      Customer.City.City.Members,   
         ([Date].[Calendar].[Calendar Year].[CY 2003],  
            Measures.[Internet Order Quantity]) > 75   
   ) ON 0  
FROM [Adventure Works]  
WHERE (Customer.Country.France,  
   [Date].[Calendar].[Calendar Year].[CY 2004],  
   Measures.[Internet Sales Amount])  
```  
  
 <span data-ttu-id="49683-120">Nella query precedente il contesto di calcolo per le celle nelle tuple incluse nell'asse delle colonne viene filtrato dal membro CY 2003 della gerarchia dell'attributo Calendar Year, anche se il contesto di calcolo nominale per la gerarchia dell'attributo Calendar Year è CY 2004.</span><span class="sxs-lookup"><span data-stu-id="49683-120">In the previous query, the calculation context for the cells in the tuples that appear on the column axis is filtered by the CY 2003 member of the Calendar Year attribute hierarchy, even though the nominal calculation context for the Calendar Year attribute hierarchy is CY 2004.</span></span> <span data-ttu-id="49683-121">Viene inoltre filtrato in base alla misura Internet Order Quantity.</span><span class="sxs-lookup"><span data-stu-id="49683-121">Furthermore, it is filtered by the Internet Order Quantity measure.</span></span> <span data-ttu-id="49683-122">Tuttavia, dopo avere impostato i membri del set sull'asse delle colonne, il contesto di calcolo per i valori dei membri inclusi nell'asse viene nuovamente determinato dalla clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="49683-122">However, once the members of the set on the column axis is set, the calculation context for the values for the members that appear on the axis is again determined by the WHERE clause.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="49683-123">Per migliorare le prestazioni delle query, è consigliabile eliminare i membri e le tuple quanto prima durante il processo di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="49683-123">To increase query performance, you should eliminate members and tuples as early in the resolution process as possible.</span></span> <span data-ttu-id="49683-124">In questo modo, i calcoli complessi in fase di query nel set finale di membri vengono eseguiti sul minor numero possibile di celle.</span><span class="sxs-lookup"><span data-stu-id="49683-124">In this manner, complex query time calculations on the final set of members operate on the fewest cells possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49683-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49683-125">See Also</span></span>  
 <span data-ttu-id="49683-126">[Definizione del contesto di cubo in una query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="49683-126">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 <span data-ttu-id="49683-127">[Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="49683-127">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 [<span data-ttu-id="49683-128">Concetti chiave di MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="49683-128">Key Concepts in MDX &#40;Analysis Services&#41;</span></span>](../key-concepts-in-mdx-analysis-services.md)  
  
  
