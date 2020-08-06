---
title: LineString | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- LineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: e50d0b86-8b31-4285-be71-ad05c7712cbd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 5a0f77959cfe4492eca6c38951ba2868452d41ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637184"
---
# <a name="linestring"></a><span data-ttu-id="b81b3-102">LineString</span><span class="sxs-lookup"><span data-stu-id="b81b3-102">LineString</span></span>
  <span data-ttu-id="b81b3-103">`LineString` indica un oggetto unidimensionale che rappresenta una sequenza di punti e i segmenti lineari che li connettono.</span><span class="sxs-lookup"><span data-stu-id="b81b3-103">A `LineString` is a one-dimensional object representing a sequence of points and the line segments connecting them.</span></span>

## <a name="linestring-instances"></a><span data-ttu-id="b81b3-104">Istanze LineString</span><span class="sxs-lookup"><span data-stu-id="b81b3-104">LineString Instances</span></span>
 <span data-ttu-id="b81b3-105">Nella figura seguente vengono illustrati esempi di istanze `LineString`.</span><span class="sxs-lookup"><span data-stu-id="b81b3-105">The illustration below shows examples of `LineString` instances.</span></span>

 <span data-ttu-id="b81b3-106">![Esempi di istanze di geometria LineString](../../database-engine/media/linestring.gif "Esempi di istanze di geometria LineString")</span><span class="sxs-lookup"><span data-stu-id="b81b3-106">![Examples of geometry LineString instances](../../database-engine/media/linestring.gif "Examples of geometry LineString instances")</span></span>

 <span data-ttu-id="b81b3-107">Come indicato nell'illustrazione:</span><span class="sxs-lookup"><span data-stu-id="b81b3-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="b81b3-108">La figura 1 rappresenta un'istanza `LineString` semplice non chiusa.</span><span class="sxs-lookup"><span data-stu-id="b81b3-108">Figure 1 is a simple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="b81b3-109">La figura 2 rappresenta un'istanza `LineString` non semplice e non chiusa.</span><span class="sxs-lookup"><span data-stu-id="b81b3-109">Figure 2 is a nonsimple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="b81b3-110">La figura 3 rappresenta un'istanza `LineString` semplice chiusa che, di conseguenza, è un anello.</span><span class="sxs-lookup"><span data-stu-id="b81b3-110">Figure 3 is a closed, simple `LineString` instance, and therefore is a ring.</span></span>

-   <span data-ttu-id="b81b3-111">La figura 4 rappresenta un'istanza `LineString` non semplice chiusa che, di conseguenza, non è un anello.</span><span class="sxs-lookup"><span data-stu-id="b81b3-111">Figure 4 is a closed, nonsimple `LineString` instance, and therefore is not a ring.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="b81b3-112">Istanze accettate</span><span class="sxs-lookup"><span data-stu-id="b81b3-112">Accepted Instances</span></span>
 <span data-ttu-id="b81b3-113">Le istanze `LineString` accettate possono essere di input in una variabile geometry, ma è possibile che non siano istanze `LineString` valide.</span><span class="sxs-lookup"><span data-stu-id="b81b3-113">Accepted `LineString` instances can be input into a geometry variable, but they may not be valid `LineString` instances.</span></span> <span data-ttu-id="b81b3-114">Per poter essere accettata, un'istanza `LineString` deve soddisfare i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="b81b3-114">The following criteria must be met for a `LineString` instance to be accepted.</span></span> <span data-ttu-id="b81b3-115">L'istanza deve essere composta da almeno due punti distinti e deve essere vuota.</span><span class="sxs-lookup"><span data-stu-id="b81b3-115">The instance must be formed of at least two points or it must be empty.</span></span> <span data-ttu-id="b81b3-116">Di seguito sono riportate le istanze LineString accettate.</span><span class="sxs-lookup"><span data-stu-id="b81b3-116">The following LineString instances are accepted.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING EMPTY';
DECLARE @g2 geometry = 'LINESTRING(1 1,2 3,4 8, -6 3)';
DECLARE @g3 geometry = 'LINESTRING(1 1, 1 1)';
```

 <span data-ttu-id="b81b3-117">In `@g3` viene illustrato che un'istanza `LineString` può essere accettata, ma non è valida.</span><span class="sxs-lookup"><span data-stu-id="b81b3-117">`@g3` shows that a `LineString` instance can be accepted, but not valid.</span></span>

 <span data-ttu-id="b81b3-118">L'istanza `LineString` seguente non viene accettata.</span><span class="sxs-lookup"><span data-stu-id="b81b3-118">The following `LineString` instance is not accepted.</span></span> <span data-ttu-id="b81b3-119">Verrà generata un'eccezione `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="b81b3-119">It will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'LINESTRING(1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="b81b3-120">Istanze valide</span><span class="sxs-lookup"><span data-stu-id="b81b3-120">Valid Instances</span></span>
 <span data-ttu-id="b81b3-121">Per poter essere valida, un'istanza `LineString` deve soddisfare i criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="b81b3-121">For a `LineString` instance to be valid it must meet the following criteria.</span></span>

1.  <span data-ttu-id="b81b3-122">L'istanza `LineString` deve essere accettata.</span><span class="sxs-lookup"><span data-stu-id="b81b3-122">The `LineString` instance must be accepted.</span></span>

2.  <span data-ttu-id="b81b3-123">Se un'istanza `LineString` non è vuota, deve contenere almeno due punti distinti.</span><span class="sxs-lookup"><span data-stu-id="b81b3-123">If a `LineString` instance is not empty then it must contain at least two distinct points.</span></span>

3.  <span data-ttu-id="b81b3-124">L'istanza `LineString` non può sovrapporti a un intervallo di due o più punti consecutivi.</span><span class="sxs-lookup"><span data-stu-id="b81b3-124">The `LineString` instance cannot overlap itself over an interval of two or more consecutive points.</span></span>

 <span data-ttu-id="b81b3-125">Le istanze `LineString` seguenti sono valide.</span><span class="sxs-lookup"><span data-stu-id="b81b3-125">The following `LineString` instances are valid.</span></span>

```
DECLARE @g1 geometry= 'LINESTRING EMPTY';
DECLARE @g2 geometry= 'LINESTRING(1 1, 3 3)';
DECLARE @g3 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0)';
DECLARE @g4 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();

```

 <span data-ttu-id="b81b3-126">Le istanze `LineString` seguenti non sono valide.</span><span class="sxs-lookup"><span data-stu-id="b81b3-126">The following `LineString` instances are not valid.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING(1 4, 3 4, 2 4, 2 0)';
DECLARE @g2 geometry = 'LINESTRING(1 1, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

> [!WARNING]
>  <span data-ttu-id="b81b3-127">Il rilevamento delle sovrapposizioni di `LineString` è basato su calcoli a virgola mobile inesatti.</span><span class="sxs-lookup"><span data-stu-id="b81b3-127">The detection of `LineString` overlaps is based on floating-point calculations, which are not exact.</span></span>

## <a name="examples"></a><span data-ttu-id="b81b3-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="b81b3-128">Examples</span></span>
 <span data-ttu-id="b81b3-129">L'esempio seguente illustra come creare un'istanza `geometry``LineString` con tre punti e un SRID di 0:</span><span class="sxs-lookup"><span data-stu-id="b81b3-129">The following example shows how to create a `geometry``LineString` instance with three points and an SRID of 0:</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1, 2 4, 3 9)', 0);
```

 <span data-ttu-id="b81b3-130">Ogni punto nell'istanza `LineString` può contenere valori Z (innalzamento) e M (misura).</span><span class="sxs-lookup"><span data-stu-id="b81b3-130">Each point in the `LineString` instance may contain Z (elevation) and M (measure) values.</span></span> <span data-ttu-id="b81b3-131">In questo esempio vengono aggiunti i valori M all'istanza `LineString` creata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="b81b3-131">This example adds M values to the `LineString` instance created in the example above.</span></span> <span data-ttu-id="b81b3-132">M e Z possono essere valori Null.</span><span class="sxs-lookup"><span data-stu-id="b81b3-132">M and Z can be null values.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1 NULL 0, 2 4 NULL 12.3, 3 9 NULL 24.5)', 0);
```

 <span data-ttu-id="b81b3-133">Nell'esempio seguente viene illustrato come creare un'istanza `geometry LineString` con due punti uguali.</span><span class="sxs-lookup"><span data-stu-id="b81b3-133">The following example shows how to create a `geometry LineString` instance with two points that are the same.</span></span> <span data-ttu-id="b81b3-134">Una chiamata a `IsValid` indica che l'istanza `LineString` non è valida e una chiamata a `MakeValid` convertirà l'istanza `LineString` in un `Point`.</span><span class="sxs-lookup"><span data-stu-id="b81b3-134">A call to `IsValid` indicates that the `LineString` instance is not valid and a call to `MakeValid` will convert the `LineString` instance into a `Point`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::STGeomFromText('LINESTRING(1 3, 1 3)',0);
IF @g.STIsValid() = 1
  BEGIN
     SELECT @g.ToString() + ' is a valid LineString.';  
  END
ELSE
  BEGIN
     SELECT @g.ToString() + ' is not a valid LineString.';
     SET @g = @g.MakeValid();
     SELECT @g.ToString() + ' is a valid Point.';  
  END

```

 <span data-ttu-id="b81b3-135">Il frammento di codice precedente restituirà quando segue:</span><span class="sxs-lookup"><span data-stu-id="b81b3-135">The above code snippet will return the following:</span></span>

```
LINESTRING(1 3, 1 3) is not a valid LineString
POINT(1 3) is a valid Point.
```

## <a name="see-also"></a><span data-ttu-id="b81b3-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b81b3-136">See Also</span></span>
 <span data-ttu-id="b81b3-137">[STLength &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndPoint &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) STIsRing &#40;tipo di [dati geometry&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;Geometry](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)&#41;[Data Spatial](../spatial/spatial-data-sql-server.md) &#40;SQL Server</span><span class="sxs-lookup"><span data-stu-id="b81b3-137">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


