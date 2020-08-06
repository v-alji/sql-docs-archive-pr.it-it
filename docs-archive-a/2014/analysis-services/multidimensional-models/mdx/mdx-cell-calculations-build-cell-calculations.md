---
title: Compilazione di calcoli di celle in MDX (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculated cells [MDX]
- queries [MDX], cell calculations
- cells [MDX]
- MDX [Analysis Services], calculations
- calculation subcubes [MDX]
- calculated values [MDX]
- Multidimensional Expressions [Analysis Services], cell calculations
ms.assetid: 068aea63-d419-4791-a960-3d74e76f808e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ab3219850c49c2ec16a12aab3ba7db67e9a8721
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718785"
---
# <a name="building-cell-calculations-in-mdx-mdx"></a><span data-ttu-id="d2eeb-102">Compilazione di formule per il calcolo di celle in MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="d2eeb-102">Building Cell Calculations in MDX (MDX)</span></span>
  <span data-ttu-id="d2eeb-103">Nel linguaggio MDX (Multidimensional Expressions) sono disponibili numerosi strumenti per la generazione di valori calcolati, ad esempio membri calcolati, rollup personalizzati e membri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-103">Multidimensional Expressions (MDX) provides you with a number of tools for generating calculated values, such as calculated members, custom rollups, and custom members.</span></span> <span data-ttu-id="d2eeb-104">Utilizzando tali caratteristiche è tuttavia difficile agire su un set specifico di celle o su una singola cella.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-104">However, using these features to affect a specific set of cells, or a single cell for that matter, would be difficult.</span></span>  
  
 <span data-ttu-id="d2eeb-105">Per generare valori calcolati per celle specifiche, è necessario utilizzare la caratteristica MDX per le celle calcolate.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-105">To generated calculated values for specifically for cells, you need to use the calculated cells feature in MDX.</span></span> <span data-ttu-id="d2eeb-106">Le celle calcolate consentono di definire una specifica sezione di celle, detta *sottocubo di calcolo*, e di applicare una formula a ogni singola cella del sottocubo di calcolo in base a una condizione facoltativa applicabile a ogni cella.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-106">Calculated cells let you define a specific slice of cells, called a *calculation subcube*, and apply a formula to each and every cell within the calculation subcube, subject to an optional condition that can be applied to each cell.</span></span>  
  
 <span data-ttu-id="d2eeb-107">Le celle calcolate offrono inoltre funzionalità complesse, ad esempio le formule per la ricerca dell'obiettivo utilizzate negli indicatori di prestazioni chiave (KPI) oppure le formule per l'analisi speculativa.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-107">Calculated cells also offer complex functionality, such as goal-seeking formulas, as used in KPIs, or speculative analysis formulas.</span></span> <span data-ttu-id="d2eeb-108">Questo livello di funzionalità deriva dalla funzionalità di pass-Order in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] che consente di eseguire passaggi ricorsivi con le celle calcolate, con le formule di calcolo applicate a passate specifiche nell'ordine di superamento.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-108">This level of functionality comes from the pass order feature in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that allows recursive passes to be made with calculated cells, with calculation formulas applied at specific passes in the pass order.</span></span> <span data-ttu-id="d2eeb-109">Per altre informazioni sull'ordine di calcolo, vedere [Informazioni sull'ordine di calcolo e di valutazione &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="d2eeb-109">For more information on pass order, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="d2eeb-110">Per quanto concerne l'ambito di creazione, le celle calcolate sono simili sia ai set denominati che ai membri calcolati, poiché possono essere create temporaneamente per la durata di una sessione o di una singola query oppure possono essere rese disponibili a livello globale nell'ambito di un cubo.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-110">In terms of creation scope, calculated cells are similar to both named sets and calculated members in that calculated cells can be temporarily created for the lifetime of either a session or a single query, or made globally available as part of a cube:</span></span>  
  
-   <span data-ttu-id="d2eeb-111">**Ambito query** Per creare una cella calcolata definita come parte di una query MDX e il cui ambito è pertanto limitato alla query, è necessario specificare la parola chiave WITH.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-111">**Query-scoped** To create a calculated cell that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="d2eeb-112">La cella calcolata può essere quindi utilizzata in un'istruzione MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-112">You can then use the calculated cell within an MDX SELECT statement.</span></span> <span data-ttu-id="d2eeb-113">Utilizzando questo approccio è possibile modificare la cella calcolata creata utilizzando la parola chiave `WITH` senza alterare l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-113">Using this approach, the calculated cell created by using the `WITH` keyword can be changed without disturbing the SELECT statement.</span></span>  
  
     <span data-ttu-id="d2eeb-114">Per altre informazioni sulla creazione di membri calcolati mediante la parola chiave WITH, vedere [Creazione di formule per il calcolo di celle con ambito query &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span><span class="sxs-lookup"><span data-stu-id="d2eeb-114">For more information about how to use the WITH keyword to create calculated members, see [Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md).</span></span>  
  
-   <span data-ttu-id="d2eeb-115">**Ambito sessione** Per creare una cella calcolata il cui ambito risulti più ampio del contesto della query, ovvero il cui ambito corrisponda alla durata della sessione MDX, è necessario usare l'istruzione CREATE CELL CALCULATION o l'istruzione ALTER CUBE.</span><span class="sxs-lookup"><span data-stu-id="d2eeb-115">**Session-scoped** To create a calculated member whose scope is wider than the context of the query, that is, whose scope is the lifetime of the MDX session, you use either the CREATE CELL CALCULATION or ALTER CUBE statement.</span></span>  
  
     <span data-ttu-id="d2eeb-116">Per altre informazioni sulla creazione di celle calcolate in una sessione mediante l'istruzione CREATE CELL CALCULATION o l'istruzione ALTER CUBE, vedere [Creazione di celle calcolate con ambito sessione](mdx-cell-calculations-session-scoped-calculated-cells.md)</span><span class="sxs-lookup"><span data-stu-id="d2eeb-116">For more information about how to use either the CREATE CELL CALCULATION or ALTER CUBE statement to create calculated cells in a session, see [Creating Session-Scoped Calculated Cells](mdx-cell-calculations-session-scoped-calculated-cells.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2eeb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2eeb-117">See Also</span></span>  
 <span data-ttu-id="d2eeb-118">[Istruzione ALTER CUBE &#40;&#41;MDX](/sql/mdx/mdx-data-definition-alter-cube) </span><span class="sxs-lookup"><span data-stu-id="d2eeb-118">[ALTER CUBE Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-alter-cube) </span></span>  
 <span data-ttu-id="d2eeb-119">[Istruzione CREATE CELL CALCULATION &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span><span class="sxs-lookup"><span data-stu-id="d2eeb-119">[CREATE CELL CALCULATION Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-cell-calculation) </span></span>  
 <span data-ttu-id="d2eeb-120">[Creazione di calcoli di celle con ambito query &#40;&#41;MDX](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="d2eeb-120">[Creating Query-Scoped Cell Calculations &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 [<span data-ttu-id="d2eeb-121">Nozioni fondamentali sulle query MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d2eeb-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
