---
title: Manipolazione di dati (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], data manipulation
- data manipulation [MDX]
- Multidimensional Expressions [Analysis Services], data manipulation
ms.assetid: 4865192e-f46b-4ce5-b51c-9e08dbad5b85
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1a1de8b9a3431d79573cd916fa7273b6d8fa7f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629066"
---
# <a name="manipulating-data-mdx"></a><span data-ttu-id="3ab63-102">Manipolazione dei dati (MDX)</span><span class="sxs-lookup"><span data-stu-id="3ab63-102">Manipulating Data (MDX)</span></span>

<span data-ttu-id="3ab63-103">Le espressioni MDX (Multidimensional Expressions) consentono di eseguire un'ampia gamma di operazioni di manipolazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3ab63-103">Multidimensional Expressions (MDX) can be used to manipulate the data in a variety of ways.</span></span> <span data-ttu-id="3ab63-104">Nell'articolo riportato in questo articolo vengono illustrati alcuni dei concetti più avanzati di manipolazione dei dati nel linguaggio MDX.</span><span class="sxs-lookup"><span data-stu-id="3ab63-104">The article listed in this article cover some of the more advanced concepts of data manipulation in the MDX language.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3ab63-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3ab63-105">In This Section</span></span>

|<span data-ttu-id="3ab63-106">Argomento</span><span class="sxs-lookup"><span data-stu-id="3ab63-106">Topic</span></span>|<span data-ttu-id="3ab63-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ab63-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3ab63-108">Utilizzo dell'istruzione DRILLTHROUGH per il recupero di dati di origine &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="3ab63-108">Using DRILLTHROUGH to Retrieve Source Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-retrieve-source-data-using-drillthrough.md)|<span data-ttu-id="3ab63-109">Descrive l'uso dell'istruzione MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) per il recupero di set di righe di dati di origine, applicabile a una cella in un'origine dati multidimensionale</span><span class="sxs-lookup"><span data-stu-id="3ab63-109">Discusses the use of the MDX [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough) statement to retrieve the rowsets of source data applicable to a cell in a multidimensional data source</span></span>|  
|[<span data-ttu-id="3ab63-110">Utilizzo della funzione RollupChildren &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="3ab63-110">Working with the RollupChildren Function &#40;MDX&#41;</span></span>](mdx-data-manipulation-rollupchildren-function.md)|<span data-ttu-id="3ab63-111">Viene illustrato l'effetto del [ROLLUPCHILDREN](/sql/mdx/rollupchildren-mdx) MDX</span><span class="sxs-lookup"><span data-stu-id="3ab63-111">Discusses the impact of the MDX [RollupChildren](/sql/mdx/rollupchildren-mdx)</span></span>
|[<span data-ttu-id="3ab63-112">Informazioni sull'ordine di calcolo e di valutazione &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="3ab63-112">Understanding Pass Order and Solve Order &#40;MDX&#41;</span></span>](mdx-data-manipulation-understanding-pass-order-and-solve-order.md)|<span data-ttu-id="3ab63-113">Fornisce informazioni dettagliate sull'ordine di soluzione e sull'effetto di tale caratteristica su espressioni, istruzioni e script MDX.</span><span class="sxs-lookup"><span data-stu-id="3ab63-113">Details the concepts of solve order, and how this feature affects MDX expressions, statements, and scripts.</span></span>|  

<!-- ??

|[Script for Search and Replace] function on the analysis of multidimensional data.|

GeneMi is removing this commented row because it is unclear what article its link meant to link to.
Also, I had to add its leading '|' character, for consistency to aid bulk automated updated to our markdown source code.

GeneMi , 2019/01/19
-->

## <a name="see-also"></a><span data-ttu-id="3ab63-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ab63-114">See Also</span></span>

[<span data-ttu-id="3ab63-115">Nozioni fondamentali sulle query MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="3ab63-115">MDX Query Fundamentals (Analysis Services)</span></span>](mdx-query-fundamentals-analysis-services.md)
