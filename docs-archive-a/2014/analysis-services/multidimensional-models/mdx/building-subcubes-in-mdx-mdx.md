---
title: Compilazione di sottocubi in MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [MDX], subcubes
- subcubes [MDX]
- filtered views [MDX]
- MDX [Analysis Services], subcubes
- Multidimensional Expressions [Analysis Services], subcubes
- CREATE SUBCUBE statement
ms.assetid: 5403a62b-99ac-4d83-b02a-89bf78bf0f46
author: minewiskan
ms.author: owend
ms.openlocfilehash: 653b4d30aa86f52179c7b13619ac4347aa65c339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630121"
---
# <a name="building-subcubes-in-mdx-mdx"></a><span data-ttu-id="de27b-102">Compilazione di sottocubi in MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="de27b-102">Building Subcubes in MDX (MDX)</span></span>
  <span data-ttu-id="de27b-103">Un sottocubo è un subset di un cubo che rappresenta una vista filtrata dei dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="de27b-103">A subcube is a subset of a cube on representing a filtered view of the underlying data.</span></span> <span data-ttu-id="de27b-104">Riducendo il cubo a un sottocubo, è possibile migliorare le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="de27b-104">By limiting the cube to a subcube, you can improve query performance.</span></span>  
  
 <span data-ttu-id="de27b-105">Per definire un sottocubo, è possibile usare l'istruzione [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) , come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="de27b-105">To define a subcube, you use the [CREATE SUBCUBE](/sql/mdx/mdx-data-definition-create-subcube) statement, as described in this topic.</span></span>  
  
## <a name="create-subcube-syntax"></a><span data-ttu-id="de27b-106">Sintassi di CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="de27b-106">CREATE SUBCUBE Syntax</span></span>  
 <span data-ttu-id="de27b-107">Per creare un sottocubo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="de27b-107">Use the following syntax to create a subcube:</span></span>  
  
```  
CREATE SUBCUBE Subcube_Identifier AS Subcube_Expression  
```  
  
 <span data-ttu-id="de27b-108">La sintassi di CREATE SUBCUBE è piuttosto semplice.</span><span class="sxs-lookup"><span data-stu-id="de27b-108">The CREATE SUBCUBE syntax is fairly simple.</span></span> <span data-ttu-id="de27b-109">Il parametro *Subcube_Identifier* identifica il cubo su cui sarà basato il sottocubo.</span><span class="sxs-lookup"><span data-stu-id="de27b-109">The *Subcube_Identifier* parameter identifies the cube on which the subcube will be based.</span></span> <span data-ttu-id="de27b-110">Il parametro *Subcube_Expression* seleziona la parte del cubo che costituirà il sottocubo</span><span class="sxs-lookup"><span data-stu-id="de27b-110">The *Subcube_Expression* parameter selects the part of the cube that will become the subcube</span></span>  
  
 <span data-ttu-id="de27b-111">Dopo la creazione del sottocubo, quest'ultimo diventerà il contesto di tutte le query MDX fino alla chiusura della sessione o all'esecuzione dell'istruzione [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) .</span><span class="sxs-lookup"><span data-stu-id="de27b-111">After you create a subcube, that subcube becomes the context for all MDX queries until either the session closes or you run the [DROP SUBCUBE](/sql/mdx/mdx-data-definition-drop-subcube) statement.</span></span>  
  
### <a name="what-a-subcube-contains"></a><span data-ttu-id="de27b-112">Contenuto di un sottocubo</span><span class="sxs-lookup"><span data-stu-id="de27b-112">What a Subcube Contains</span></span>  
 <span data-ttu-id="de27b-113">Anche se è piuttosto semplice da utilizzare, l'istruzione CREATE SUBCUBE in sé non indica esplicitamente tutti i membri che faranno parte del sottocubo.</span><span class="sxs-lookup"><span data-stu-id="de27b-113">Although the CREATE SUBCUBE statement is fairly simple to use, the statement itself does not explicitly show all the members that become part of a subcube.</span></span> <span data-ttu-id="de27b-114">Nella definizione di un sottocubo valgono le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="de27b-114">In defining a subcube, the following rules apply:</span></span>  
  
-   <span data-ttu-id="de27b-115">Se si include il membro `(All)` di una gerarchia, verranno inclusi tutti i membri della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="de27b-115">If you include the `(All)` member of a hierarchy, you include every member of that hierarchy.</span></span>  
  
-   <span data-ttu-id="de27b-116">Se si include un membro, verranno inclusi tutti i predecessori e i discendenti di tale membro.</span><span class="sxs-lookup"><span data-stu-id="de27b-116">If you include any member, you include that member's ascendants and descendants.</span></span>  
  
-   <span data-ttu-id="de27b-117">Se si includono tutti i membri di un livello, verranno inclusi tutti i membri della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="de27b-117">If you include every member from a level, you include all members from the hierarchy.</span></span> <span data-ttu-id="de27b-118">I membri di altre gerarchie che non corrispondono a membri del livello (ad esempio, una gerarchia sbilanciata come nel caso di una città per cui non esistono clienti) verranno esclusi.</span><span class="sxs-lookup"><span data-stu-id="de27b-118">Members from other hierarchies will be excluded if those members do not exist with members from the level (for example, an unbalanced hierarchy such as a city that does not contain customers).</span></span>  
  
-   <span data-ttu-id="de27b-119">Un sottocubo contiene sempre tutti i membri `(All)` del cubo.</span><span class="sxs-lookup"><span data-stu-id="de27b-119">A subcube will always contain every `(All)` member from the cube.</span></span>  
  
 <span data-ttu-id="de27b-120">I valori di aggregazione inclusi nel sottocubo verranno inoltre totalizzati visivamente.</span><span class="sxs-lookup"><span data-stu-id="de27b-120">Additionally, aggregate values within the subcube are visually totaled.</span></span> <span data-ttu-id="de27b-121">Si consideri ad esempio un sottocubo contenente `USA`, `WA`e `OR`.</span><span class="sxs-lookup"><span data-stu-id="de27b-121">For example, a subcube contains `USA`, `WA`, and `OR`.</span></span> <span data-ttu-id="de27b-122">Il valore di aggregazione di `USA` sarà costituito dalla somma di `{WA,OR}` , perché `WA` e `OR` sono gli unici stati definiti dal sottocubo.</span><span class="sxs-lookup"><span data-stu-id="de27b-122">The aggregate value for `USA` will be the sum of `{WA,OR}` because `WA` and `OR` are the only states defined by the subcube.</span></span> <span data-ttu-id="de27b-123">Tutti gli altri stati verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="de27b-123">All other states will be ignored.</span></span>  
  
 <span data-ttu-id="de27b-124">I riferimenti espliciti alle celle esterne al sottocubo restituiscono inoltre valori di cella che vengono valutati nel contesto dell'intero cubo.</span><span class="sxs-lookup"><span data-stu-id="de27b-124">Also, explicit references to cells outside the subcube return cell values that are evaluated in the context of the whole cube.</span></span> <span data-ttu-id="de27b-125">Si immagini ad esempio di creare un sottocubo limitato all'anno corrente.</span><span class="sxs-lookup"><span data-stu-id="de27b-125">For example, you create a subcube that is limited to the current year.</span></span> <span data-ttu-id="de27b-126">Si usa quindi la funzione [ParallelPeriod](/sql/mdx/parallelperiod-mdx) per confrontare l'anno corrente con quello precedente.</span><span class="sxs-lookup"><span data-stu-id="de27b-126">You then use the [ParallelPeriod](/sql/mdx/parallelperiod-mdx) function to compare the current year to the previous year.</span></span> <span data-ttu-id="de27b-127">La differenza nei valori verrà restituita anche se il valore dell'anno precedente è esterno al sottocubo.</span><span class="sxs-lookup"><span data-stu-id="de27b-127">The difference in values will be returned even though the previous year's value lies outside the subcube.</span></span>  
  
 <span data-ttu-id="de27b-128">Infine, se il contesto originale non viene sovrascritto, le funzioni sui set valutate in una sub-SELECT verranno valutate nel contesto della sub-SELECT.</span><span class="sxs-lookup"><span data-stu-id="de27b-128">Finally, if the original context is not overwritten, set functions evaluated in a subselect are evaluated in the context of the subselect.</span></span> <span data-ttu-id="de27b-129">Se il contesto viene sovrascritto, le funzioni sui set verranno valutate nel contesto dell'intero cubo.</span><span class="sxs-lookup"><span data-stu-id="de27b-129">If the context is overwritten, set functions are evaluated in the context of the whole cube.</span></span>  
  
## <a name="create-subcube-example"></a><span data-ttu-id="de27b-130">Esempio di CREATE SUBCUBE</span><span class="sxs-lookup"><span data-stu-id="de27b-130">CREATE SUBCUBE Example</span></span>  
 <span data-ttu-id="de27b-131">Nell'esempio seguente viene creato un sottocubo che restringe il cubo Budget ai soli conti 4200 e 4300:</span><span class="sxs-lookup"><span data-stu-id="de27b-131">The following example creates a subcube that restricts the Budget cube to only accounts 4200 and 4300:</span></span>  
  
 `CREATE SUBCUBE Budget AS SELECT {[Account].[Account].&[4200], [Account].[Account].&[4300] } ON 0 FROM Budget`  
  
 <span data-ttu-id="de27b-132">Poiché è stato creato un sottocubo per la sessione, tutte le query successive verranno eseguite sul sottocubo, non sull'intero cubo.</span><span class="sxs-lookup"><span data-stu-id="de27b-132">Having created a subcube for the session, any subsequent queries will be against the subcube, not the whole cube.</span></span> <span data-ttu-id="de27b-133">Se ad esempio si esegue la query seguente,</span><span class="sxs-lookup"><span data-stu-id="de27b-133">For example, you run the following query.</span></span> <span data-ttu-id="de27b-134">verranno restituiti solo membri dei conti 4200 e 4300.</span><span class="sxs-lookup"><span data-stu-id="de27b-134">This query will only return members from accounts 4200 and 4300.</span></span>  
  
 `SELECT [Account].[Account].Members ON 0, Measures.Members ON 1 FROM Budget`  
  
## <a name="see-also"></a><span data-ttu-id="de27b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de27b-135">See Also</span></span>  
 <span data-ttu-id="de27b-136">[Definizione del contesto di cubo in una query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="de27b-136">[Establishing Cube Context in a Query &#40;MDX&#41;](establishing-cube-context-in-a-query-mdx.md) </span></span>  
 [<span data-ttu-id="de27b-137">Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="de27b-137">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
