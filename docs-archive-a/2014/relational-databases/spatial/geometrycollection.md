---
title: GeometryCollection | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- GeomCollection geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 4445c0d9-a66b-4d7c-88e4-a66fa6f7d9fd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 71d2234a9b73b7647554e364fe3864f089a47a0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637186"
---
# <a name="geometrycollection"></a><span data-ttu-id="004c3-102">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="004c3-102">GeometryCollection</span></span>
  <span data-ttu-id="004c3-103">`GeometryCollection` è una raccolta di zero o più istanze `geometry` o `geography`.</span><span class="sxs-lookup"><span data-stu-id="004c3-103">A `GeometryCollection` is a collection of zero or more `geometry` or `geography` instances.</span></span> <span data-ttu-id="004c3-104">`GeometryCollection` può essere vuoto.</span><span class="sxs-lookup"><span data-stu-id="004c3-104">A `GeometryCollection` can be empty.</span></span>  
  
## <a name="geometrycollection-instances"></a><span data-ttu-id="004c3-105">Istanze GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="004c3-105">GeometryCollection Instances</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="004c3-106">Istanze accettate</span><span class="sxs-lookup"><span data-stu-id="004c3-106">Accepted Instances</span></span>  
 <span data-ttu-id="004c3-107">Per poter essere accettata, un'istanza `GeometryCollection` deve essere un'istanza `GeometryCollection` vuota oppure tutte le istanze che comprendono l'istanza `GeometryCollection` devono essere istanze accettate.</span><span class="sxs-lookup"><span data-stu-id="004c3-107">For a `GeometryCollection` instance to be accepted, it must either be an empty `GeometryCollection` instance or all the instances comprising the `GeometryCollection` instance must be accepted instances.</span></span> <span data-ttu-id="004c3-108">Nell'esempio seguente vengono illustrate le istanze accettate.</span><span class="sxs-lookup"><span data-stu-id="004c3-108">The following example shows accepted instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
 <span data-ttu-id="004c3-109">Nell'esempio seguente viene generata un'eccezione `System.FormatException`, poiché l'istanza `LinesString` nell'istanza `GeometryCollection` non è accettata.</span><span class="sxs-lookup"><span data-stu-id="004c3-109">The following example throws a `System.FormatException` because the `LinesString` instance in the `GeometryCollection` instance is not accepted.</span></span>  
  
```  
DECLARE @g geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1), POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="004c3-110">Istanze valide</span><span class="sxs-lookup"><span data-stu-id="004c3-110">Valid Instances</span></span>  
 <span data-ttu-id="004c3-111">Un'istanza `GeometryCollection` è valida se tutte le istanze che comprendono l'istanza `GeometryCollection` sono valide.</span><span class="sxs-lookup"><span data-stu-id="004c3-111">A `GeometryCollection` instance is valid when all instances that comprise the `GeometryCollection` instance are valid.</span></span> <span data-ttu-id="004c3-112">Nell'esempio seguente vengono indicate tre istanze `GeometryCollection` valide e un'istanza non valida.</span><span class="sxs-lookup"><span data-stu-id="004c3-112">The following shows three valid `GeometryCollection` instances and one instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g4 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, 1 -5, -5 5, -5 -1, -1 -1)))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="004c3-113">`@g4` non è valida, poiché l'istanza `Polygon` nell'istanza `GeometryCollection` non è valida.</span><span class="sxs-lookup"><span data-stu-id="004c3-113">`@g4` is not valid because the `Polygon` instance in the `GeometryCollection` instance is not valid.</span></span>  
  
 <span data-ttu-id="004c3-114">Per altre informazioni sulle istanze accettate e valide, vedere [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md)e [MultiPolygon](multipolygon.md).</span><span class="sxs-lookup"><span data-stu-id="004c3-114">For more information on accepted and valid instances, see [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md), and [MultiPolygon](multipolygon.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="004c3-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="004c3-115">Examples</span></span>  
 <span data-ttu-id="004c3-116">Nell'esempio seguente viene creata un'istanza di un `geometry``GeometryCollection` con i valori Z in SRID 1 in cui sono incluse le istanze `Point` e `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="004c3-116">The following example instantiates a `geometry``GeometryCollection` with Z values in SRID 1 containing a `Point` instance and a `Polygon` instance.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomCollFromText('GEOMETRYCOLLECTION(POINT(3 3 1), POLYGON((0 0 2, 1 10 3, 1 0 4, 0 0 2)))', 1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="004c3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="004c3-117">See Also</span></span>  
 [<span data-ttu-id="004c3-118">Dati spaziali &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="004c3-118">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
