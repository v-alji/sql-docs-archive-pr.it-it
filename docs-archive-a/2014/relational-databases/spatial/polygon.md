---
title: Poligono | Microsoft Docs
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry subtypes [SQL Server]
- Polygon geometry subtype [SQL Server]
ms.assetid: b6a21c3c-fdb8-4187-8229-1c488454fdfb
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 040bb8a2558cc57b1b99a3ce984bec3c8925bc0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637168"
---
# <a name="polygon"></a><span data-ttu-id="c9a3b-102">Polygon</span><span class="sxs-lookup"><span data-stu-id="c9a3b-102">Polygon</span></span>
  <span data-ttu-id="c9a3b-103">Un `Polygon` è una superficie bidimensionale archiviata come una sequenza di punti che definiscono un anello di delimitazione esterno e nessuno o più anelli interni.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-103">A `Polygon` is a two-dimensional surface stored as a sequence of points defining an exterior bounding ring and zero or more interior rings.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="c9a3b-104">Istanze Polygon</span><span class="sxs-lookup"><span data-stu-id="c9a3b-104">Polygon instances</span></span>
 <span data-ttu-id="c9a3b-105">Un'istanza `Polygon` può essere formata da un anello che ha almeno tre punti distinti.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-105">A `Polygon` instance can be formed from a ring that has at least three distinct points.</span></span> <span data-ttu-id="c9a3b-106">Un'istanza `Polygon` può essere anche vuota.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-106">A `Polygon` instance can also be empty.</span></span>

 <span data-ttu-id="c9a3b-107">L'anello esterno e ogni anello interno di un `Polygon` ne definiscono il limite.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-107">The exterior and any interior rings of a `Polygon` define its boundary.</span></span> <span data-ttu-id="c9a3b-108">Lo spazio all'interno degli anelli definisce l'interno del `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-108">The space within the rings defines the interior of the `Polygon`.</span></span>

 <span data-ttu-id="c9a3b-109">Nella figura seguente vengono illustrati esempi di istanze `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-109">The illustration below shows examples of `Polygon` instances.</span></span>

 <span data-ttu-id="c9a3b-110">![Esempi di istanze di geometria Polygon](../../database-engine/media/polygon.gif "Esempi di istanze di geometria Polygon")</span><span class="sxs-lookup"><span data-stu-id="c9a3b-110">![Examples of geometry Polygon instances](../../database-engine/media/polygon.gif "Examples of geometry Polygon instances")</span></span>

 <span data-ttu-id="c9a3b-111">Come indicato nell'illustrazione:</span><span class="sxs-lookup"><span data-stu-id="c9a3b-111">As shown in the illustration:</span></span>

1.  <span data-ttu-id="c9a3b-112">La figura 1 è un'istanza `Polygon` il cui limite è definito da un anello esterno.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-112">Figure 1 is a `Polygon` instance whose boundary is defined by an exterior ring.</span></span>

2.  <span data-ttu-id="c9a3b-113">La figura 2 è un'istanza `Polygon` il cui limite è definito da un anello esterno e due anelli interni.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-113">Figure 2 is a `Polygon` instance whose boundary is defined by an exterior ring and two interior rings.</span></span> <span data-ttu-id="c9a3b-114">L'area negli anelli interni è parte dell'esterno dell'istanza `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-114">The area inside the interior rings is part of the exterior of the `Polygon` instance.</span></span>

3.  <span data-ttu-id="c9a3b-115">La figura 3 è un'istanza `Polygon` valida perché i suoi anelli interni si intersecano in un solo punto tangente.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-115">Figure 3 is a valid `Polygon` instance because its interior rings intersect at a single tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="c9a3b-116">Istanze accettate</span><span class="sxs-lookup"><span data-stu-id="c9a3b-116">Accepted instances</span></span>
 <span data-ttu-id="c9a3b-117">Le istanze `Polygon` accettate sono istanze che possono essere archiviate in una variabile `geometry` o `geography` senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-117">Accepted `Polygon` instances are instances that can be stored in a `geometry` or `geography` variable without throwing an exception.</span></span> <span data-ttu-id="c9a3b-118">Di seguito sono riportate le istanze `Polygon` accettate.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-118">The following are accepted `Polygon` instances:</span></span>

-   <span data-ttu-id="c9a3b-119">Istanza `Polygon` vuota</span><span class="sxs-lookup"><span data-stu-id="c9a3b-119">An Empty `Polygon` instance</span></span>

-   <span data-ttu-id="c9a3b-120">Un'istanza `Polygon` che dispone di un anello esterno accettabile e di zero o più anelli interni accettabili</span><span class="sxs-lookup"><span data-stu-id="c9a3b-120">A `Polygon` instance that has an acceptable exterior ring and zero or more acceptable interior rings</span></span>

 <span data-ttu-id="c9a3b-121">I criteri seguenti sono necessari affinché un anello sia accettabile.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-121">The following criteria are needed for a ring to be acceptable.</span></span>

-   <span data-ttu-id="c9a3b-122">L'istanza `LineString` deve essere accettata.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-122">The `LineString` instance must be accepted.</span></span>

-   <span data-ttu-id="c9a3b-123">L'istanza `LineString` deve disporre di almeno quattro punti.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-123">The `LineString` instance must have at least four points.</span></span>

-   <span data-ttu-id="c9a3b-124">I punti iniziale e finale dell'istanza `LineString` devono essere gli stessi.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-124">The starting and ending points of the `LineString` instance must be the same.</span></span>

 <span data-ttu-id="c9a3b-125">Nell'esempio seguente vengono illustrate le istanze `Polygon` accettate.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-125">The following example shows accepted `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON EMPTY';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 1))';
DECLARE @g3 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 3 3, 0 3, 0 0))';
DECLARE @g4 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(3 0, 6 0, 6 3, 3 3, 3 0))';
DECLARE @g5 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
```

 <span data-ttu-id="c9a3b-126">Come illustrato in `@g4` e `@g5`, è possibile che un'istanza di `Polygon` accettata non sia un'istanza di `Polygon` valida.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-126">As `@g4` and `@g5` show an accepted `Polygon` instance may not be a valid `Polygon` instance.</span></span> <span data-ttu-id="c9a3b-127">`@g5` mostra anche che un'istanza Polygon, per essere accettata, deve contenere solo un anello con quattro punti qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-127">`@g5` also shows that a Polygon instance needs to only contain a ring with any four points to be accepted.</span></span>

 <span data-ttu-id="c9a3b-128">Negli esempi seguenti viene generata un'eccezione `System.FormatException`, poiché le istanze `Polygon` non vengono accettate.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-128">The following examples throw a `System.FormatException` because the `Polygon` instances are not accepted.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((1 1, 3 3, 1 1))';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 5))';
```

 <span data-ttu-id="c9a3b-129">`@g1` non viene accettata perché l'istanza di `LineString` per l'anello esterno non contiene un numero di punti sufficiente.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-129">`@g1` is not accepted because the `LineString` instance for the exterior ring does not contain enough points.</span></span> <span data-ttu-id="c9a3b-130">`@g2` non viene accettata perché il punto iniziale dell'istanza di `LineString` per l'anello esterno non corrisponde al punto finale.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-130">`@g2` is not accepted because the starting point of the exterior ring `LineString` instance is not the same as the ending point.</span></span> <span data-ttu-id="c9a3b-131">Nell'esempio seguente è presente un anello esterno accettabile, ma l'anello interno non è accettabile.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-131">The following example has an acceptable exterior ring, but the interior ring is not acceptable.</span></span> <span data-ttu-id="c9a3b-132">Viene inoltre generata un'eccezione `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-132">This also throws a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 0 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="c9a3b-133">Istanze valide</span><span class="sxs-lookup"><span data-stu-id="c9a3b-133">Valid instances</span></span>
 <span data-ttu-id="c9a3b-134">Gli anelli interni di un `Polygon` possono toccare se stessi e toccarsi tra di loro in ogni punto di tangenza, ma se gli anelli interni di un `Polygon` si incrociano, l'istanza non è valida.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-134">The interior rings of a `Polygon` can touch both themselves and each other at single tangent points, but if the interior rings of a `Polygon` cross, the instance is not valid.</span></span>

 <span data-ttu-id="c9a3b-135">Nell'esempio seguente vengono illustrate le istanze `Polygon` valide.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-135">The following example shows valid `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, -5 -10, -10 0))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="c9a3b-136">`@g3` è valida perché i due anelli interni si toccano in un solo punto e non si incrociano.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-136">`@g3` is valid because the two interior rings touch at a single point and do not cross each other.</span></span> <span data-ttu-id="c9a3b-137">Nell'esempio seguente vengono illustrate le istanze `Polygon` non valide.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-137">The following example shows `Polygon` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (20 0, 0 10, 0 -20, 20 0))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (5 0, 1 5, 1 -5, 5 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, 0 -10, -10 0))';
DECLARE @g4 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 1 5, 0 -10, -10 0))';
DECLARE @g5 geometry = 'POLYGON((10 0, 0 10, 0 -10, 10 0), (-20 -20, -20 20, 20 20, 20 -20, -20 -20) )';
DECLARE @g6 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid(), @g5.STIsValid(), @g6.STIsValid();
```

 <span data-ttu-id="c9a3b-138">`@g1` non è valida perché l'anello interno tocca l'anello esterno in due punti.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-138">`@g1` is not valid because the inner ring touches the exterior ring in two places.</span></span> <span data-ttu-id="c9a3b-139">`@g2` non è valida perché il secondo anello interno si trova all'interno del primo anello interno.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-139">`@g2` is not valid because the second inner ring in within the interior of the first inner ring.</span></span> <span data-ttu-id="c9a3b-140">`@g3` non è valida perché i due anelli interni si toccano in più punti consecutivi.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-140">`@g3` is not valid because the two inner rings touch at multiple consecutive points.</span></span> <span data-ttu-id="c9a3b-141">`@g4` non è valida perché gli interni dei due anelli interni si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-141">`@g4` is not valid because the interiors of the two inner rings overlap.</span></span> <span data-ttu-id="c9a3b-142">`@g5` non è valida perché l'anello esterno non è il primo anello.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-142">`@g5` is not valid because the exterior ring is not the first ring.</span></span> <span data-ttu-id="c9a3b-143">`@g6` non è valida perché l'anello non presenta almeno tre punti distinti.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-143">`@g6` is not valid because the ring does not have at least three distinct points.</span></span>

## <a name="examples"></a><span data-ttu-id="c9a3b-144">Esempi</span><span class="sxs-lookup"><span data-stu-id="c9a3b-144">Examples</span></span>
 <span data-ttu-id="c9a3b-145">Nell'esempio seguente viene creata un'istanza `geometry``Polygon` semplice con un foro e SRID 10.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-145">The following example creates a simple `geometry``Polygon` instance with a hole and SRID 10.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STPolyFromText('POLYGON((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1))', 10);
```

 <span data-ttu-id="c9a3b-146">Un'istanza non valida può essere immessa e convertita in un'istanza `geometry` valida.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-146">Aninstance that is not valid may be entered and converted to a valid `geometry` instance.</span></span> <span data-ttu-id="c9a3b-147">Nell'esempio seguente di un `Polygon`, gli anelli interni ed esterni si sovrappongono e l'istanza non è valida.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-147">In the following example of a `Polygon`, the interior and exterior rings overlap and the instance is not valid.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('POLYGON((1 0, 0 1, 1 2, 2 1, 1 0), (2 0, 1 1, 2 2, 3 1, 2 0))');
```

 <span data-ttu-id="c9a3b-148">Nell'esempio seguente, l'istanza non valida è resa valida con `MakeValid()`.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-148">In the following example, the invalid instance is made valid with `MakeValid()`.</span></span>

```
SET @g = @g.MakeValid();
SELECT @g.ToString();
```

 <span data-ttu-id="c9a3b-149">L'istanza `geometry` restituita dall'esempio precedente è un `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-149">The `geometry` instance returned from the above example is a `MultiPolygon`.</span></span>

```
MULTIPOLYGON (((2 0, 3 1, 2 2, 1.5 1.5, 2 1, 1.5 0.5, 2 0)), ((1 0, 1.5 0.5, 1 1, 1.5 1.5, 1 2, 0 1, 1 0)))
```

 <span data-ttu-id="c9a3b-150">Di seguito è riportato un altro esempio della conversione di un'istanza non valida in un'istanza geometry valida.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-150">Here is another example of converting an invalid instance to a valid geometry instance.</span></span> <span data-ttu-id="c9a3b-151">Nell'esempio seguente l'istanza `Polygon` è stata creata utilizzando tre punti esattamente uguali:</span><span class="sxs-lookup"><span data-stu-id="c9a3b-151">In the following example the `Polygon` instance has been created using three points that are exactly the same:</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('POLYGON((1 3, 1 3, 1 3, 1 3))');
SET @g = @g.MakeValid();
SELECT @g.ToString()
```

 <span data-ttu-id="c9a3b-152">L'istanza geometry restituita sopra è `Point(1 3)`.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-152">The geometry instance returned above is a `Point(1 3)`.</span></span>  <span data-ttu-id="c9a3b-153">Se l'istanza `Polygon` indicata è `POLYGON((1 3, 1 5, 1 3, 1 3))` , `MakeValid()` restituirà `LINESTRING(1 3, 1 5)`.</span><span class="sxs-lookup"><span data-stu-id="c9a3b-153">If the `Polygon` given is `POLYGON((1 3, 1 5, 1 3, 1 3))` then `MakeValid()` would return `LINESTRING(1 3, 1 5)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9a3b-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9a3b-154">See Also</span></span>
 <span data-ttu-id="c9a3b-155">[STArea &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) STPointOnSurface &#40;tipo di [dati geometry&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) dati spaziali [MultiPolygon](../spatial/polygon.md) &#40;[SQL Server](../spatial/spatial-data-sql-server.md)&#41;[STIsValid &#40;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) tipo di dati geography&#41;STIsValid &#40;[Geometry](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)&#41;</span><span class="sxs-lookup"><span data-stu-id="c9a3b-155">[STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [MultiPolygon](../spatial/polygon.md) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)</span></span>


