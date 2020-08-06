---
title: Compilazione di misure in MDX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0347835-4983-4d26-acbb-6c8fae7992bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac49d37f11584bfbc5d372241056da39e7dd8c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627446"
---
# <a name="building-measures-in-mdx"></a><span data-ttu-id="8b1c4-102">Compilazione di misure in MDX</span><span class="sxs-lookup"><span data-stu-id="8b1c4-102">Building Measures in MDX</span></span>
  <span data-ttu-id="8b1c4-103">Nelle espressioni MDX una misura è un'espressione DAX denominata che viene risolta tramite il calcolo dell'espressione per la restituzione di un valore in un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="8b1c4-103">In Multidimensional Expressions (MDX), a measure is a named DAX expression that is resolved by calculating the expression to return a value in a Tabular Model.</span></span> <span data-ttu-id="8b1c4-104">Dietro a questa definizione apparentemente semplice si nasconde un'enorme quantità di informazioni.</span><span class="sxs-lookup"><span data-stu-id="8b1c4-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="8b1c4-105">La possibilità di creare e utilizzare misure in una query MDX offre capacità notevoli per la manipolazione dei dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="8b1c4-105">The ability to construct and use measures in an MDX query provides a great deal of manipulation capability for tabular data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8b1c4-106">Le misure possono essere definite solo nei modelli tabulari. Se il database viene impostato in modalità multidimensionale, la creazione di una misura genera un errore</span><span class="sxs-lookup"><span data-stu-id="8b1c4-106">Measures can only be defined in tabular models; if your database is set in multidimensional mode, creating a measure will generate an error</span></span>  
  
 <span data-ttu-id="8b1c4-107">Per creare una misura definita come parte di una query MDX, pertanto con ambito limitato alla query, è necessario utilizzare la parola chiave WITH.</span><span class="sxs-lookup"><span data-stu-id="8b1c4-107">To create a measure that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="8b1c4-108">È quindi possibile utilizzare tale misura in un'istruzione MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="8b1c4-108">You can then use the measure within an MDX SELECT statement.</span></span> <span data-ttu-id="8b1c4-109">In tal modo, è possibile modificare il membro calcolato creato utilizzando la parola chiave WITH senza alterare l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="8b1c4-109">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span> <span data-ttu-id="8b1c4-110">In MDX, tuttavia, si fa riferimento alla misura in modo diverso rispetto a quanto avviene nelle espressioni DAX. Per fare riferimento alla misura è necessario assegnare a essa un nome come membro della dimensione [Measures], come illustrato nell'esempio MDX seguente:</span><span class="sxs-lookup"><span data-stu-id="8b1c4-110">However, in MDX you reference the measure in a different way than when in DAX expressions; to reference the measure you name it as a member of the [Measures] dimension, see the following MDX example:</span></span>  
  
```  
with measure  'Sales Territory'[Total Sales Amount] = SUM('Internet Sales'[Sales Amount]) + SUM('Reseller Sales'[Sales Amount])  
select measures.[Total Sales Amount] on columns  
     ,NON EMPTY [Date].[Calendar Year].children on rows  
from [Model]  
  
```  
  
 <span data-ttu-id="8b1c4-111">Dall'esecuzione verranno restituiti i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b1c4-111">It will return the following data when executed:</span></span>  
  
||<span data-ttu-id="8b1c4-112">Total Sales Amount</span><span class="sxs-lookup"><span data-stu-id="8b1c4-112">Total Sales Amount</span></span>||  
|-|------------------------|-|  
|<span data-ttu-id="8b1c4-113">2001</span><span class="sxs-lookup"><span data-stu-id="8b1c4-113">2001</span></span>|<span data-ttu-id="8b1c4-114">11331808.96</span><span class="sxs-lookup"><span data-stu-id="8b1c4-114">11331808.96</span></span>||  
|<span data-ttu-id="8b1c4-115">2002</span><span class="sxs-lookup"><span data-stu-id="8b1c4-115">2002</span></span>|<span data-ttu-id="8b1c4-116">30674773.18</span><span class="sxs-lookup"><span data-stu-id="8b1c4-116">30674773.18</span></span>||  
|<span data-ttu-id="8b1c4-117">2003</span><span class="sxs-lookup"><span data-stu-id="8b1c4-117">2003</span></span>|<span data-ttu-id="8b1c4-118">41993729.72</span><span class="sxs-lookup"><span data-stu-id="8b1c4-118">41993729.72</span></span>||  
|<span data-ttu-id="8b1c4-119">2004</span><span class="sxs-lookup"><span data-stu-id="8b1c4-119">2004</span></span>|<span data-ttu-id="8b1c4-120">25808962.34</span><span class="sxs-lookup"><span data-stu-id="8b1c4-120">25808962.34</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="8b1c4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b1c4-121">See Also</span></span>  
 <span data-ttu-id="8b1c4-122">[Istruzione CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="8b1c4-122">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="8b1c4-123">[Guida di riferimento alle funzioni MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="8b1c4-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="8b1c4-124">Istruzione SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="8b1c4-124">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
