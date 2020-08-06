---
title: Gestione di ambito e contesto (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], context
- scope [MDX]
- CALCULATE statement
- This function [MDX]
- SCOPE statement
- scripts [MDX], scope
ms.assetid: 631e7c20-8be9-4c35-8609-76516aef19d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7cf1e6cea8df00b632e114a5a8756373738ca6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627447"
---
# <a name="managing-scope-and-context-mdx"></a><span data-ttu-id="a3a31-102">Gestione di ambito e contesto (MDX)</span><span class="sxs-lookup"><span data-stu-id="a3a31-102">Managing Scope and Context (MDX)</span></span>
  <span data-ttu-id="a3a31-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uno script MDX (Multidimensional Expressions) può essere applicato all'intero cubo o a determinate parti del cubo, in punti specifici all'interno dell'esecuzione dello script.</span><span class="sxs-lookup"><span data-stu-id="a3a31-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script can apply to the entire cube, or to specific portions of the cube, at specific points within the execution of the script.</span></span> <span data-ttu-id="a3a31-104">Uno script MDX può utilizzare un approccio a livelli per i calcoli all'interno di un cubo, tramite l'utilizzo di sessioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="a3a31-104">The MDX script can take a layered approach to calculations within a cube through the use of calculation passes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3a31-105">Per altre informazioni sull'effetto delle sessioni di calcolo sui calcoli, vedere [Informazioni sull'ordine di calcolo e di valutazione &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="a3a31-105">For more information on how calculation passes can affect calculations, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="a3a31-106">Per controllare le sessioni di calcolo, l'ambito e il contesto in uno script MDX, è possibile utilizzare l'istruzione CALCULATE, la funzione `This` e l'istruzione SCOPE.</span><span class="sxs-lookup"><span data-stu-id="a3a31-106">To control the calculation pass, scope, and context within an MDX script, you specifically use the CACULATE statement, the `This` function, and the SCOPE statement.</span></span>  
  
## <a name="using-the-calculate-statement"></a><span data-ttu-id="a3a31-107">Utilizzo dell'istruzione CALCULATE</span><span class="sxs-lookup"><span data-stu-id="a3a31-107">Using the CALCULATE Statement</span></span>  
 <span data-ttu-id="a3a31-108">L'istruzione CALCULATE popola ogni cella del cubo con dati aggregati.</span><span class="sxs-lookup"><span data-stu-id="a3a31-108">The CALCULATE statement populates each cell in the cube with aggregated data.</span></span> <span data-ttu-id="a3a31-109">Lo script MDX predefinito, ad esempio, include una sola istruzione CALCULATE all'inizio dello script.</span><span class="sxs-lookup"><span data-stu-id="a3a31-109">For example, the default MDX script has a single CALCULATE statement at the beginning of the script.</span></span>  
  
 <span data-ttu-id="a3a31-110">Per altre informazioni sulla sintassi dell'istruzione CALCULATE, vedere [Istruzione CALCULATE &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span><span class="sxs-lookup"><span data-stu-id="a3a31-110">For more information on the syntax of the CALCULATE statement, see [CALCULATE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3a31-111">Se lo script include un'istruzione SCOPE che contiene un'istruzione CALCULATE, MDX valuterà l'istruzione CALCULATE nel contesto del sottocubo definito dall'istruzione SCOPE, non rispetto all'intero cubo.</span><span class="sxs-lookup"><span data-stu-id="a3a31-111">If the script contains a SCOPE statement that contains a CALCULATE statement, MDX evaluates the CALCULATE statement within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
## <a name="using-the-this-function"></a><span data-ttu-id="a3a31-112">Utilizzo della funzione This</span><span class="sxs-lookup"><span data-stu-id="a3a31-112">Using the This Function</span></span>  
 <span data-ttu-id="a3a31-113">La funzione `This` consente di recuperare il sottocubo corrente in uno script MDX.</span><span class="sxs-lookup"><span data-stu-id="a3a31-113">The `This` function lets you retrieve the current subcube within an MDX script.</span></span> <span data-ttu-id="a3a31-114">È possibile utilizzare la funzione `This` per impostare rapidamente su un'espressione MDX il valore delle celle del sottocubo corrente.</span><span class="sxs-lookup"><span data-stu-id="a3a31-114">You can use the `This` function to quickly set the value of cells within the current subcube to an MDX expression.</span></span> <span data-ttu-id="a3a31-115">La funzione `This` viene spesso utilizzata insieme all'istruzione SCOPE per modificare il contenuto di uno specifico sottocubo durante una determinata sessione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="a3a31-115">You often use the `This` function in conjunction with the SCOPE statement to change the contents of a specific subcube during a specific calculation pass.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3a31-116">Se lo script include un'istruzione SCOPE che contiene una funzione `This`, MDX valuterà la funzione `This` nel contesto del sottocubo definito dall'istruzione SCOPE, non rispetto all'intero cubo.</span><span class="sxs-lookup"><span data-stu-id="a3a31-116">If the script contains a SCOPE statement that contains a `This` function, MDX evaluates the `This` function within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
### <a name="this-function-example"></a><span data-ttu-id="a3a31-117">Esempio di funzione This</span><span class="sxs-lookup"><span data-stu-id="a3a31-117">This Function Example</span></span>  
 <span data-ttu-id="a3a31-118">Nel seguente esempio di comando di script MDX la funzione `This` viene utilizzata per incrementare del 10% il valore della misura Amount, nel gruppo di misure Finance del cubo di esempio [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)], per i bambini del membro Redmond della dimensione Customer:</span><span class="sxs-lookup"><span data-stu-id="a3a31-118">The following MDX script command example uses the `This` function to increase the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension:</span></span>  
  
```  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="a3a31-119">Per ulteriori informazioni sulla sintassi della `This` funzione, vedere [questo &#40;&#41;MDX ](/sql/mdx/this-mdx).</span><span class="sxs-lookup"><span data-stu-id="a3a31-119">For more information on the syntax of the `This` function, see [This &#40;MDX&#41;](/sql/mdx/this-mdx).</span></span>  
  
## <a name="using-the-scope-statement"></a><span data-ttu-id="a3a31-120">Utilizzo dell'istruzione SCOPE</span><span class="sxs-lookup"><span data-stu-id="a3a31-120">Using the SCOPE Statement</span></span>  
 <span data-ttu-id="a3a31-121">L'istruzione SCOPE definisce il sottocubo corrente che contiene e specifica l'ambito di altre espressioni e istruzioni MDX dello script MDX.</span><span class="sxs-lookup"><span data-stu-id="a3a31-121">The SCOPE statement defines the current subcube that contains, and specifies the scope of, other MDX expressions and statements within an MDX script.</span></span> <span data-ttu-id="a3a31-122">MDX valuta tali espressioni e istruzioni MDX aggiuntive, comprese la funzione `This` e l'istruzione CALCULATE, nel contesto del sottocubo.</span><span class="sxs-lookup"><span data-stu-id="a3a31-122">MDX evaluates this other MDX expressions and statements, including the `This` function and the CALCULATE statement, within the context of the subcube.</span></span>  
  
 <span data-ttu-id="a3a31-123">Un'istruzione SCOPE è dinamica, ma non iterativa.</span><span class="sxs-lookup"><span data-stu-id="a3a31-123">A SCOPE statement is dynamic, but not iterative in nature.</span></span> <span data-ttu-id="a3a31-124">Le istruzioni contenute in un'istruzione SCOPE vengono eseguite una volta sola, ma il sottocubo può essere determinato dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="a3a31-124">The statements contained within a SCOPE statement run once, but the subcube itself can be dynamically determined.</span></span> <span data-ttu-id="a3a31-125">Si consideri ad esempio un cubo di nome SampleCube.</span><span class="sxs-lookup"><span data-stu-id="a3a31-125">For example, you have a cube named SampleCube.</span></span> <span data-ttu-id="a3a31-126">A tale cubo viene applicata l'istruzione SCOPE seguente, per creare un sottocubo che definisce come contesto il risultato della funzione ALLMEMBERS applicata alla dimensione Measures:</span><span class="sxs-lookup"><span data-stu-id="a3a31-126">Against the SampleCube cube, you apply the following SCOPE statement to define a subcube the defines the context as the ALLMEMBERS within the Measures dimension:</span></span>  
  
 `SCOPE([Measures].ALLMEMBERS);`  
  
 `THIS = [Measures].ALLMEMBERS.COUNT;`  
  
 `END SCOPE;`  
  
 <span data-ttu-id="a3a31-127">Le istruzioni e le espressioni contenute in questa istruzione SCOPE vengono eseguite una volta sola.</span><span class="sxs-lookup"><span data-stu-id="a3a31-127">The statements and expressions within this SCOPE statement run once.</span></span>  
  
 <span data-ttu-id="a3a31-128">Si supponga ora che un utente aziendale esegua la query MDX seguente, che contiene una sola misura di nome ExistingMeasure, sul cubo SampleCube:</span><span class="sxs-lookup"><span data-stu-id="a3a31-128">Now, a business user runs the following MDX query that contains one measure, named ExistingMeasure, against the SampleCube cube:</span></span>  
  
 `WITH MEMBER [Measures].[NewMeasure] AS '1'`  
  
 `SELECT`  
  
 `[Measures].ALLMEMBERS ON COLUMNS,`  
  
 `[Customer].DEFAULTMEMBER ON ROWS`  
  
 `FROM`  
  
 `[SampleCube]`  
  
 <span data-ttu-id="a3a31-129">Il set di celle restituito dalla query è simile all'output illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a3a31-129">The cellset returned from the query resembles the output shown in the following table.</span></span>  
  
||<span data-ttu-id="a3a31-130">[ExistingMeasure]</span><span class="sxs-lookup"><span data-stu-id="a3a31-130">[ExistingMeasure]</span></span>|<span data-ttu-id="a3a31-131">[NewMeasure]</span><span class="sxs-lookup"><span data-stu-id="a3a31-131">[NewMeasure]</span></span>|  
|-|-------------------------|--------------------|  
|<span data-ttu-id="a3a31-132">[Customer].[All]</span><span class="sxs-lookup"><span data-stu-id="a3a31-132">[Customer].[All]</span></span>|<span data-ttu-id="a3a31-133">2</span><span class="sxs-lookup"><span data-stu-id="a3a31-133">2</span></span>|<span data-ttu-id="a3a31-134">2</span><span class="sxs-lookup"><span data-stu-id="a3a31-134">2</span></span>|  
  
 <span data-ttu-id="a3a31-135">Osservando il set di celle restituito, è possibile notare che il valore ExistingMeasure incluso nell'istruzione SCOPE dello script MDX viene aggiornato dinamicamente dopo la definizione della misura NewMeasure.</span><span class="sxs-lookup"><span data-stu-id="a3a31-135">Looking at the returned cellset, notice how the ExistingMeasure value, included in the SCOPE statement within the MDX script, is dynamically updated after the measure NewMeasure was defined.</span></span>  
  
 <span data-ttu-id="a3a31-136">Un'istruzione SCOPE può essere nidificata in un'altra istruzione SCOPE.</span><span class="sxs-lookup"><span data-stu-id="a3a31-136">A SCOPE statement can be nested within another SCOPE statement.</span></span> <span data-ttu-id="a3a31-137">Poiché l'istruzione SCOPE non è iterativa, la nidificazione delle istruzioni SCOPE viene utilizzata principalmente per suddividere ulteriormente un sottocubo per scopi particolari.</span><span class="sxs-lookup"><span data-stu-id="a3a31-137">However, as the SCOPE statement is not iterative, the primary purpose for nesting SCOPE statements is to further subdivide a subcube for special treatment.</span></span>  
  
### <a name="scope-statement-example"></a><span data-ttu-id="a3a31-138">Esempio di istruzione SCOPE</span><span class="sxs-lookup"><span data-stu-id="a3a31-138">SCOPE Statement Example</span></span>  
 <span data-ttu-id="a3a31-139">Nell'esempio di script MDX seguente l'istruzione SCOPE viene utilizzata per incrementare del 10% il valore della misura Amount, nel gruppo di misure Finance del cubo di esempio [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] , per i bambini del membro Redmond della dimensione Customer.</span><span class="sxs-lookup"><span data-stu-id="a3a31-139">The following MDX script example uses a SCOPE statement to sets the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension.</span></span> <span data-ttu-id="a3a31-140">Un'altra istruzione SCOPE modifica tuttavia il sottocubo in modo da includere la misura Amount per i bambini dell'anno di calendario 2002.</span><span class="sxs-lookup"><span data-stu-id="a3a31-140">However, another SCOPE statement changes the subcube to include the Amount measure for the children of the 2002 calendar year.</span></span> <span data-ttu-id="a3a31-141">La misura Amount viene infine aggregata solo per tale sottocubo, mentre i valori aggregati per la misura Amount relativa agli altri anni di calendario restano invariati.</span><span class="sxs-lookup"><span data-stu-id="a3a31-141">Finally, the Amount measure is then aggregated only for that subcube, leaving the aggregated values for the Amount measure in other calendar years unchanged.</span></span>  
  
```  
/* Calculate the entire cube first. */  
CALCULATE;  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="a3a31-142">Per altre informazioni sulla sintassi dell'istruzione SCOPE, vedere [Istruzione SCOPE &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span><span class="sxs-lookup"><span data-stu-id="a3a31-142">For more information on the syntax of the SCOPE statement, see [SCOPE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a31-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3a31-143">See Also</span></span>  
 <span data-ttu-id="a3a31-144">[Guida di riferimento al linguaggio MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="a3a31-144">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 <span data-ttu-id="a3a31-145">[Script MDX di base &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="a3a31-145">[The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span></span>  
 [<span data-ttu-id="a3a31-146">Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a3a31-146">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
