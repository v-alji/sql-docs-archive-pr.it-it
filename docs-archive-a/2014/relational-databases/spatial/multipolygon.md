---
title: MultiPolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPolygon geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 2c5db358-2a16-49d9-aac5-a74e86813932
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f18fd2485c9b2e62586d9f3e81f76f6cf680dbfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637172"
---
# <a name="multipolygon"></a><span data-ttu-id="b097b-102">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="b097b-102">MultiPolygon</span></span>
  <span data-ttu-id="b097b-103">Un'istanza `MultiPolygon` è una raccolta di zero o più istanze `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="b097b-103">A `MultiPolygon` instance is a collection of zero or more `Polygon` instances.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="b097b-104">Istanze Polygon</span><span class="sxs-lookup"><span data-stu-id="b097b-104">Polygon Instances</span></span>
 <span data-ttu-id="b097b-105">Nella figura seguente vengono illustrati esempi di istanze `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="b097b-105">The illustration below shows examples of `MultiPolygon` instances.</span></span>

 <span data-ttu-id="b097b-106">![Esempi di istanze di geometria MultiPolygon](../../database-engine/media/multipolygon.gif "Esempi di istanze di geometria MultiPolygon")</span><span class="sxs-lookup"><span data-stu-id="b097b-106">![Examples of geometry MultiPolygon instances](../../database-engine/media/multipolygon.gif "Examples of geometry MultiPolygon instances")</span></span>

 <span data-ttu-id="b097b-107">Come indicato nell'illustrazione:</span><span class="sxs-lookup"><span data-stu-id="b097b-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="b097b-108">Nella figura 1 viene rappresentata un'istanza `MultiPolygon` con due elementi `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="b097b-108">Figure 1 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="b097b-109">Il limite è definito dai due anelli esterni e dai tre anelli interni.</span><span class="sxs-lookup"><span data-stu-id="b097b-109">The boundary is defined by the two exterior rings and the three interior rings.</span></span>

-   <span data-ttu-id="b097b-110">Nella figura 2 viene rappresentata un'istanza `MultiPolygon` con due elementi `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="b097b-110">Figure 2 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="b097b-111">Il limite è definito dai due anelli esterni e dai tre anelli interni.</span><span class="sxs-lookup"><span data-stu-id="b097b-111">The boundary is defined by the two exterior rings and the three interior rings.</span></span> <span data-ttu-id="b097b-112">I due elementi `Polygon` si intersecano in un punto di tangenza.</span><span class="sxs-lookup"><span data-stu-id="b097b-112">The two `Polygon` elements intersect at a tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="b097b-113">Istanze accettate</span><span class="sxs-lookup"><span data-stu-id="b097b-113">Accepted Instances</span></span>
 <span data-ttu-id="b097b-114">Viene accettata un'istanza `MultiPolygon` se viene soddisfatta una delle condizioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b097b-114">A `MultiPolygon` instance is accepted one of the following conditions is met.</span></span>

-   <span data-ttu-id="b097b-115">È un'istanza `MultiPolygon` vuota.</span><span class="sxs-lookup"><span data-stu-id="b097b-115">It is an empty `MultiPolygon` instance.</span></span>

-   <span data-ttu-id="b097b-116">Tutte le istanze che comprendono l'istanza `MultiPolygon` sono istanze `Polygon` accettate.</span><span class="sxs-lookup"><span data-stu-id="b097b-116">All instances comprising the `MultiPolygon` instance are accepted `Polygon` instances.</span></span> <span data-ttu-id="b097b-117">Per ulteriori informazioni sulle istanze accettate `Polygon` , vedere [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="b097b-117">For more information on accepted `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

 <span data-ttu-id="b097b-118">Negli esempi seguenti vengono illustrate alcune istanze `MultiPolygon` accettate.</span><span class="sxs-lookup"><span data-stu-id="b097b-118">The following examples show accepted `MultiPolygon` instances.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
```

 <span data-ttu-id="b097b-119">Nell'esempio seguente viene illustrata un'istanza MultiPolygon che genererà un'eccezione `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="b097b-119">The following example shows a MultiPolygon instance that will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3)))';
```

 <span data-ttu-id="b097b-120">La seconda istanza in MultiPolygon è un'istanza di LineString e non un'istanza Polygon accettata.</span><span class="sxs-lookup"><span data-stu-id="b097b-120">The second instance in the MultiPolygon is a LineString instance and not an accepted Polygon instance.</span></span>

### <a name="valid-instances"></a><span data-ttu-id="b097b-121">Istanze valide</span><span class="sxs-lookup"><span data-stu-id="b097b-121">Valid Instances</span></span>
 <span data-ttu-id="b097b-122">Un'istanza `MultiPolygon` è valida se è un'istanza `MultiPolygon` vuota o se soddisfa i criteri indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="b097b-122">A `MultiPolygon` instance is valid if it is an empty `MultiPolygon` instance or if it meets the following criteria.</span></span>

1.  <span data-ttu-id="b097b-123">Tutte le istanze che comprendono l'istanza `MultiPolygon` sono istanze `Polygon` valide.</span><span class="sxs-lookup"><span data-stu-id="b097b-123">All of the instances comprising the `MultiPolygon` instance are valid `Polygon` instances.</span></span> <span data-ttu-id="b097b-124">Per le `Polygon` istanze valide, vedere [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="b097b-124">For valid `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

2.  <span data-ttu-id="b097b-125">Nessuna delle istanze `Polygon` che comprendono l'istanza `MultiPolygon` si sovrappone.</span><span class="sxs-lookup"><span data-stu-id="b097b-125">None of the `Polygon` instances comprising the `MultiPolygon` instance overlap.</span></span>

 <span data-ttu-id="b097b-126">Nell'esempio seguente vengono indicate due istanze `MultiPolygon` valide e un'istanza `MultiPolygon` valida.</span><span class="sxs-lookup"><span data-stu-id="b097b-126">The following example shows two valid `MultiPolygon` instances and one invalid `MultiPolygon` instance.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="b097b-127">`@g2` è valida perché le due istanze di `Polygon` si toccano solo in corrispondenza di un punto tangente.</span><span class="sxs-lookup"><span data-stu-id="b097b-127">`@g2` is valid because the two `Polygon` instances touch only at a tangent point.</span></span> <span data-ttu-id="b097b-128">`@g3` non è valida perché gli interni delle due istanze di `Polygon` si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="b097b-128">`@g3` is not valid because the interiors of the two `Polygon` instances overlap each other.</span></span>

## <a name="examples"></a><span data-ttu-id="b097b-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="b097b-129">Examples</span></span>
 <span data-ttu-id="b097b-130">L'esempio seguente illustra la creazione di un'istanza `geometry``MultiPolygon` e viene restituito il Well-Known Text (WKT) del secondo componente.</span><span class="sxs-lookup"><span data-stu-id="b097b-130">The following example shows the creation of a `geometry``MultiPolygon` instance and returns the Well-Known Text (WKT) of the second component.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON(((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1)), ((9 9, 9 10, 10 9, 9 9)))');
SELECT @g.STGeometryN(2).STAsText();
```

 <span data-ttu-id="b097b-131">In questo esempio viene creata un'istanza `MultiPolygon` vuota.</span><span class="sxs-lookup"><span data-stu-id="b097b-131">This example instantiates an empty `MultiPolygon` instance.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON EMPTY');
```

## <a name="see-also"></a><span data-ttu-id="b097b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b097b-132">See Also</span></span>
 <span data-ttu-id="b097b-133">[Poligono](../spatial/polygon.md) [STArea &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [dati spaziali](../spatial/spatial-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b097b-133">[Polygon](../spatial/polygon.md) [STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


