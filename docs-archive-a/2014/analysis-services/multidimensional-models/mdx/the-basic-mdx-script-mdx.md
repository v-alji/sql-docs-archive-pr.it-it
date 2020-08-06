---
title: Script MDX di base (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default MDX scripts
- statements [MDX]
- expressions [MDX], scripts
- scripts [MDX], about scripts
ms.assetid: 83d9afda-7d34-42b5-8f28-20172a905f23
author: minewiskan
ms.author: owend
ms.openlocfilehash: de0d2fea002beda0eca480bd27140bdd202fcb83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721899"
---
# <a name="the-basic-mdx-script-mdx"></a><span data-ttu-id="fd511-102">Script MDX di base (MDX)</span><span class="sxs-lookup"><span data-stu-id="fd511-102">The Basic MDX Script (MDX)</span></span>
  <span data-ttu-id="fd511-103">Uno script MDX (Multidimensional Expressions) definisce il processo di calcolo per un cubo in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd511-103">A Multidimensional Expressions (MDX) script defines the calculation process for a cube in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="fd511-104">Esistono due tipi di script MDX:</span><span class="sxs-lookup"><span data-stu-id="fd511-104">There are two types of MDX scripts:</span></span>  
  
 <span data-ttu-id="fd511-105">**Script MDX predefinito**</span><span class="sxs-lookup"><span data-stu-id="fd511-105">**The default MDX script**</span></span>  
 <span data-ttu-id="fd511-106">Quando si crea un cubo, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] crea uno script MDX predefinito per tale cubo.</span><span class="sxs-lookup"><span data-stu-id="fd511-106">At the time that you create a cube, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates a default MDX script for that cube.</span></span> <span data-ttu-id="fd511-107">Lo script definisce una sessione di calcolo per l'intero cubo.</span><span class="sxs-lookup"><span data-stu-id="fd511-107">This script defines a calculation pass for the whole cube.</span></span>  
  
 <span data-ttu-id="fd511-108">**Script MDX definito dall'utente**</span><span class="sxs-lookup"><span data-stu-id="fd511-108">**User-defined MDX script**</span></span>  
 <span data-ttu-id="fd511-109">Dopo la creazione di un cubo è possibile aggiungervi script MDX definiti dall'utente che estendono le capacità di calcolo del cubo.</span><span class="sxs-lookup"><span data-stu-id="fd511-109">After you have created a cube, you can add user-defined MDX scripts that extend the calculation capabilities of the cube.</span></span>  
  
## <a name="the-default-mdx-script"></a><span data-ttu-id="fd511-110">Script MDX predefinito</span><span class="sxs-lookup"><span data-stu-id="fd511-110">The Default MDX Script</span></span>  
 <span data-ttu-id="fd511-111">Lo script MDX predefinito creato da [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] quando si definisce un cubo contiene una sola istruzione CALCULATE,</span><span class="sxs-lookup"><span data-stu-id="fd511-111">The default MDX script that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates when you define a cube contains a single CALCULATE statement.</span></span> <span data-ttu-id="fd511-112">che si trova all'inizio dello script e indica che l'intero cubo dovrà essere calcolato durante la prima sessione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="fd511-112">This single CALCULATE statement is at the beginning of the default MDX script, and indicates that the entire cube should be calculated during the first calculation pass.</span></span>  
  
 <span data-ttu-id="fd511-113">Lo script MDX predefinito contiene anche i comandi script che creano i set denominati, le assegnazioni e i membri calcolati creati in Progettazione cubi:</span><span class="sxs-lookup"><span data-stu-id="fd511-113">The default MDX script also contains the script commands that create named sets, assignments, and calculated members created in Cube Designer:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="fd511-114">aggiunge direttamente i comandi script allo script MDX predefinito.</span><span class="sxs-lookup"><span data-stu-id="fd511-114">directly adds script commands to the default MDX script.</span></span>  
  
-   <span data-ttu-id="fd511-115">Per ogni set denominato presente nel cubo, esiste un'istruzione CREATE SET corrispondente nello script MDX predefinito.</span><span class="sxs-lookup"><span data-stu-id="fd511-115">For each named set in the cube, a corresponding CREATE SET statement exists in the default MDX script.</span></span>  
  
-   <span data-ttu-id="fd511-116">Per ogni membro calcolato definito nel cubo, esiste un'istruzione CREATE MEMBER corrispondente nello script MDX predefinito.</span><span class="sxs-lookup"><span data-stu-id="fd511-116">For each calculated member defined in the cube, a corresponding CREATE MEMBER statement exists in the default MDX script.</span></span>  
  
 <span data-ttu-id="fd511-117">È possibile controllare l'ordine dei comandi script, dei set denominati e dei membri calcolati nello script MDX predefinito usando la scheda **Calcoli** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="fd511-117">You can control the order of script commands, named sets, and calculated members in the default MDX script by using the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="fd511-118">Per altre informazioni sulla definizione dei calcoli archiviati nello script MDX predefinito, vedere [Calcoli nei modelli multidimensionali](../calculations-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="fd511-118">For more information on defining calculations stored in the default MDX script, see [Calculations in Multidimensional Models](../calculations-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="fd511-119">Se a un cubo non è associato alcuno script MDX, il cubo utilizzerà lo script MDX predefinito.</span><span class="sxs-lookup"><span data-stu-id="fd511-119">If there is no MDX script associated with a cube, the cube assumes the default MDX script.</span></span> <span data-ttu-id="fd511-120">Un cubo deve essere associato ad almeno uno script MDX, perché si basa sullo script MDX per determinare il comportamento di calcolo.</span><span class="sxs-lookup"><span data-stu-id="fd511-120">A cube needs to be associated with at least one MDX script because a cube relies on the MDX script to determine calculation behavior.</span></span> <span data-ttu-id="fd511-121">In altre parole, un cubo non associato a uno script MDX o associato a uno script MDX vuoto non è in grado di calcolare alcuna cella.</span><span class="sxs-lookup"><span data-stu-id="fd511-121">In other words, a cube that was not associated with an MDX script or was associated with an empty MDX script could not and would not be able to calculate any cells.</span></span> <span data-ttu-id="fd511-122">Se si creano cubi a livello di programmazione, utilizzando comandi ASSL (Analysis Services Scripting Language) o tramite AMO (Analysis Management Objects), è consigliabile creare anche uno script MDX predefinito contenente una singola istruzione CALCULATE per il cubo.</span><span class="sxs-lookup"><span data-stu-id="fd511-122">If you programmatically create cubes, either by using Analysis Services Scripting Language (ASSL) commands or by using Analysis Management Objects (AMO), it is recommended that you create a default MDX script containing a single CALCULATE statement for the cube.</span></span>  
  
## <a name="mdx-script-content"></a><span data-ttu-id="fd511-123">Contenuto degli script MDX</span><span class="sxs-lookup"><span data-stu-id="fd511-123">MDX Script Content</span></span>  
 <span data-ttu-id="fd511-124">Uno script MDX può contenere le istruzioni e le espressioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd511-124">An MDX script can contain the following statements and expressions:</span></span>  
  
 <span data-ttu-id="fd511-125">Tutte le istruzioni di scripting MDX</span><span class="sxs-lookup"><span data-stu-id="fd511-125">All MDX scripting statements</span></span>  
 <span data-ttu-id="fd511-126">Negli script MDX le istruzioni di scripting MDX controllano il contesto e l'ambito dei calcoli e gestiscono il comportamento delle altre istruzioni contenute nello script MDX.</span><span class="sxs-lookup"><span data-stu-id="fd511-126">In MDX scripts, MDX scripting statements control the context and scope of calculations, and manage the behavior of other statements in the MDX script.</span></span> <span data-ttu-id="fd511-127">Questa categoria include le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd511-127">This category includes the following statements:</span></span>  
  
-   [<span data-ttu-id="fd511-128">CALCOLARE</span><span class="sxs-lookup"><span data-stu-id="fd511-128">CALCULATE</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
-   [<span data-ttu-id="fd511-129">CONGELARE</span><span class="sxs-lookup"><span data-stu-id="fd511-129">FREEZE</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
-   [<span data-ttu-id="fd511-130">AMBITO</span><span class="sxs-lookup"><span data-stu-id="fd511-130">SCOPE</span></span>](/sql/mdx/mdx-scripting-scope)  
  
 <span data-ttu-id="fd511-131">Per altre informazioni sulle istruzioni di scripting MDX, vedere [Istruzioni di scripting MDX &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span><span class="sxs-lookup"><span data-stu-id="fd511-131">For more information on MDX scripting statements, see [MDX Scripting Statements &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span></span>  
  
 [<span data-ttu-id="fd511-132">CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="fd511-132">CREATE MEMBER</span></span>](/sql/mdx/mdx-data-definition-create-member)  
 <span data-ttu-id="fd511-133">L'istruzione CREATE MEMBER crea membri calcolati.</span><span class="sxs-lookup"><span data-stu-id="fd511-133">The CREATE MEMBER statement creates calculated members.</span></span> <span data-ttu-id="fd511-134">Per altre informazioni sulla creazione di membri calcolati, vedere [Compilazione di membri calcolati in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="fd511-134">For more information about how to create calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
 [<span data-ttu-id="fd511-135">CREATE SET</span><span class="sxs-lookup"><span data-stu-id="fd511-135">CREATE SET</span></span>](/sql/mdx/mdx-data-definition-create-set)  
 <span data-ttu-id="fd511-136">L'istruzione CREATE SET crea set denominati.</span><span class="sxs-lookup"><span data-stu-id="fd511-136">The CREATE SET statement creates named sets.</span></span> <span data-ttu-id="fd511-137">Per altre informazioni sulla procedura per creare set denominati, vedere [Compilazione di set denominati in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="fd511-137">For more information about how to create names sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="fd511-138">Istruzioni condizionali</span><span class="sxs-lookup"><span data-stu-id="fd511-138">Conditional statements</span></span>  
 <span data-ttu-id="fd511-139">Le istruzioni condizionali aggiungono logica condizionale agli script MDX.</span><span class="sxs-lookup"><span data-stu-id="fd511-139">Conditional statements add conditional logic to MDX scripts.</span></span> <span data-ttu-id="fd511-140">Questa categoria include le istruzioni [CASE](/sql/mdx/case-statement-mdx) e [IF](/sql/mdx/mdx-scripting-if) .</span><span class="sxs-lookup"><span data-stu-id="fd511-140">This category includes the [CASE](/sql/mdx/case-statement-mdx) and [IF](/sql/mdx/mdx-scripting-if) statements.</span></span>  
  
 <span data-ttu-id="fd511-141">Espressioni di assegnazione</span><span class="sxs-lookup"><span data-stu-id="fd511-141">Assignment expressions</span></span>  
 <span data-ttu-id="fd511-142">Un'espressione di assegnazione assegna un'espressione, ad esempio un valore, a un sottocubo soggetto a vincoli.</span><span class="sxs-lookup"><span data-stu-id="fd511-142">An assignment expression assigns an expression, such as a value, to a constrained subcube.</span></span> <span data-ttu-id="fd511-143">Un'espressione di sottocubo soggetta a vincoli è una raccolta di espressioni set soggette a vincoli che definisce i limiti di un sottocubo in uno script MDX.</span><span class="sxs-lookup"><span data-stu-id="fd511-143">A constrained subcube expression is a collection of constrained set expressions that define the "edges" of a subcube within an MDX script.</span></span> <span data-ttu-id="fd511-144">Nei frammenti di codice seguenti viene illustrata la sintassi di un'espressione di sottocubo soggetta a vincoli:</span><span class="sxs-lookup"><span data-stu-id="fd511-144">The following codes shows the syntax for a constrained subcube expression:</span></span>  
  
```  
<Constrained subcube> ::= (   
    ( <Constrained set> [<Crossjoin operator> <Constrained set>...] |  
    <ROOT function> |  
    <TREE function> |  
    LEAVES() |  
    * ) [, <Constrained subcube>...]  
<Constrained set> ::=   
    <Natural hierarchy>.MEMBERS |   
    <Natural hierarchy>.LEVEL(<numeric expression>).MEMBERS |   
    { <Natural hierarchy member> } |   
    DESCENDANTS( <Natural hierarchy member>, <Level expression>, ( SELF | AFTER | SELF_AND_AFTER ) ) |   
    DESCENDANTS( <Natural hierarchy member>, , LEAVES )  
<Natural hierarchy> ::= <Hierarchy identifier>  
<Natural hierarchy member> ::= <Natural hierarchy>.<identifier>[.<identifier>...]  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd511-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd511-145">See Also</span></span>  
 <span data-ttu-id="fd511-146">[Guida di riferimento al linguaggio MDX &#40;&#41;MDX](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="fd511-146">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="fd511-147">Nozioni fondamentali sullo scripting MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fd511-147">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
