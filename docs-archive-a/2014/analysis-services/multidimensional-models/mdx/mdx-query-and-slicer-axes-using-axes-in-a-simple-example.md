---
title: Utilizzo di assi di query e di sezionamento in un semplice esempio (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- query axis [MDX]
ms.assetid: 85bcb26f-5971-4153-b334-61f8d8b475b5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 324f082fd6659592e56af65680bd4aa623c625d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635238"
---
# <a name="using-query-and-slicer-axes-in-a-simple-example-mdx"></a><span data-ttu-id="46767-102">Utilizzo di assi di query e assi di sezionamento in un semplice esempio (MDX)</span><span class="sxs-lookup"><span data-stu-id="46767-102">Using Query and Slicer Axes in a Simple Example (MDX)</span></span>
  <span data-ttu-id="46767-103">Il semplice esempio presentato in questo argomento illustra le nozioni fondamentali sull'impostazione e l'utilizzo di assi di query e assi di sezionamento.</span><span class="sxs-lookup"><span data-stu-id="46767-103">The simple example presented in this topic illustrates the basics of specifying and using query and slicer axes.</span></span>  
  
## <a name="the-cube"></a><span data-ttu-id="46767-104">Il cubo</span><span class="sxs-lookup"><span data-stu-id="46767-104">The Cube</span></span>  
 <span data-ttu-id="46767-105">Viene utilizzato un cubo con il nome TestCube e due semplici dimensioni, Route e Time.</span><span class="sxs-lookup"><span data-stu-id="46767-105">A cube, named TestCube, has two simple dimensions named Route and Time.</span></span> <span data-ttu-id="46767-106">Ogni dimensione include un'unica gerarchia utente, Route e Time rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="46767-106">Each dimension has only one user hierarchy, named Route and Time respectively.</span></span> <span data-ttu-id="46767-107">Poiché le misure del cubo fanno parte della dimensione Measures, il cubo ha in tutto tre dimensioni.</span><span class="sxs-lookup"><span data-stu-id="46767-107">Because the measures of the cube are part of the Measures dimension, this cube has three dimensions in all.</span></span>  
  
## <a name="the-query"></a><span data-ttu-id="46767-108">La query</span><span class="sxs-lookup"><span data-stu-id="46767-108">The Query</span></span>  
 <span data-ttu-id="46767-109">La query deve restituire una matrice in cui è possibile confrontare la misura Packages su vari canali di distribuzione e periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="46767-109">The query is to provide a matrix in which the Packages measure can be compared across routes and times.</span></span>  
  
 <span data-ttu-id="46767-110">Nella seguente query MDX di esempio gli assi della query sono costituiti dalle gerarchie Route e Time, mentre la dimensione Measures costituisce l'asse di sezionamento.</span><span class="sxs-lookup"><span data-stu-id="46767-110">In the following MDX query example, the Route and Time hierarchies are the query axes, and the Measures dimension is the slicer axis.</span></span> <span data-ttu-id="46767-111">La funzione [Members](/sql/mdx/members-set-mdx) indica che MDX utilizzerà i membri della gerarchia o del livello per costruire un set.</span><span class="sxs-lookup"><span data-stu-id="46767-111">The [Members](/sql/mdx/members-set-mdx) function indicates that MDX will use the members of the hierarchy or level to construct a set.</span></span> <span data-ttu-id="46767-112">Poiché viene utilizzata la funzione `Members`, non è necessario definire esplicitamente ogni membro di una gerarchia o di un livello specifico in una query MDX.</span><span class="sxs-lookup"><span data-stu-id="46767-112">The use of the `Members` function means that you do not have to explicitly state each member of a specific hierarchy or level in an MDX query.</span></span>  
  
```  
SELECT  
   { Route.nonground.Members } ON COLUMNS,  
   { Time.[1st half].Members } ON ROWS  
FROM TestCube  
WHERE ( [Measures].[Packages] )  
```  
  
## <a name="the-results"></a><span data-ttu-id="46767-113">I risultati</span><span class="sxs-lookup"><span data-stu-id="46767-113">The Results</span></span>  
 <span data-ttu-id="46767-114">Il risultato è costituito da una griglia che identifica il valore della misura Packages per ogni intersezione delle dimensioni degli assi COLUMNS e ROWS.</span><span class="sxs-lookup"><span data-stu-id="46767-114">The result is a grid that identifies the value of the Packages measure at each intersection of the COLUMNS and ROWS axis dimensions.</span></span> <span data-ttu-id="46767-115">Tale griglia è illustrata nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="46767-115">The following table shows how this grid would look.</span></span>  
  
||<span data-ttu-id="46767-116">air</span><span class="sxs-lookup"><span data-stu-id="46767-116">air</span></span>|<span data-ttu-id="46767-117">sea</span><span class="sxs-lookup"><span data-stu-id="46767-117">sea</span></span>|  
|-|---------|---------|  
|<span data-ttu-id="46767-118">1st quarter</span><span class="sxs-lookup"><span data-stu-id="46767-118">1st quarter</span></span>|<span data-ttu-id="46767-119">60</span><span class="sxs-lookup"><span data-stu-id="46767-119">60</span></span>|<span data-ttu-id="46767-120">50</span><span class="sxs-lookup"><span data-stu-id="46767-120">50</span></span>|  
|<span data-ttu-id="46767-121">2nd quarter</span><span class="sxs-lookup"><span data-stu-id="46767-121">2nd quarter</span></span>|<span data-ttu-id="46767-122">45</span><span class="sxs-lookup"><span data-stu-id="46767-122">45</span></span>|<span data-ttu-id="46767-123">45</span><span class="sxs-lookup"><span data-stu-id="46767-123">45</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46767-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46767-124">See Also</span></span>  
 <span data-ttu-id="46767-125">[Impostazione del contenuto di un asse della query &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span><span class="sxs-lookup"><span data-stu-id="46767-125">[Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span></span>  
 [<span data-ttu-id="46767-126">Impostazione del contenuto di un asse di sezionamento &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="46767-126">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
