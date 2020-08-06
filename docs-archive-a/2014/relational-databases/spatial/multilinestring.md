---
title: MultiLineString | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiLineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 95deeefe-d6c5-4a11-b347-379e4486e7b7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: fdd093d99d055df8e15fc22e3e570e6805e35d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637176"
---
# <a name="multilinestring"></a><span data-ttu-id="bbf38-102">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="bbf38-102">MultiLineString</span></span>
  <span data-ttu-id="bbf38-103">Un `MultiLineString` è una raccolta di zero o più `geometry` istanze di o **GeographyLineString** .</span><span class="sxs-lookup"><span data-stu-id="bbf38-103">A `MultiLineString` is a collection of zero or more `geometry` or **geographyLineString** instances.</span></span>  
  
## <a name="multilinestring-instances"></a><span data-ttu-id="bbf38-104">Istanze MultiLineString</span><span class="sxs-lookup"><span data-stu-id="bbf38-104">MultiLineString instances</span></span>  
 <span data-ttu-id="bbf38-105">Nella figura seguente vengono illustrati esempi di istanze `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="bbf38-105">The illustration below shows examples of `MultiLineString` instances.</span></span>  
  
 <span data-ttu-id="bbf38-106">![Esempi di istanze di geometria MultiLineString](../../database-engine/media/multilinestring.gif "Esempi di istanze di geometria MultiLineString")</span><span class="sxs-lookup"><span data-stu-id="bbf38-106">![Examples of geometry MultiLineString instances](../../database-engine/media/multilinestring.gif "Examples of geometry MultiLineString instances")</span></span>  
  
 <span data-ttu-id="bbf38-107">Come indicato nell'illustrazione:</span><span class="sxs-lookup"><span data-stu-id="bbf38-107">As shown in the illustration:</span></span>  
  
-   <span data-ttu-id="bbf38-108">La figura 1 è un' `MultiLineString` istanza semplice il cui limite è costituito dai quattro endpoint dei due `LineString` elementi.</span><span class="sxs-lookup"><span data-stu-id="bbf38-108">Figure 1 is a simple `MultiLineString` instance whose boundary is the four endpoints of its two `LineString` elements.</span></span>  
  
-   <span data-ttu-id="bbf38-109">La figura 2 è un'istanza di tipo semplice `MultiLineString` perché si intersecano solo gli endpoint degli elementi `LineString`.</span><span class="sxs-lookup"><span data-stu-id="bbf38-109">Figure 2 is a simple `MultiLineString` instance because only the endpoints of the `LineString` elements intersect.</span></span> <span data-ttu-id="bbf38-110">Il limite è rappresentato dai due endpoint non sovrapposti.</span><span class="sxs-lookup"><span data-stu-id="bbf38-110">The boundary is the two non-overlapping endpoints.</span></span>  
  
-   <span data-ttu-id="bbf38-111">La figura 3 è un'istanza di tipo non semplice `MultiLineString` perché l'interno di uno dei suoi elementi `LineString` è intersecato.</span><span class="sxs-lookup"><span data-stu-id="bbf38-111">Figure 3 is a nonsimple `MultiLineString` instance because the interior of one of its `LineString` elements is intersected.</span></span> <span data-ttu-id="bbf38-112">Il limite di questa istanza `MultiLineString` è rappresentato dai quattro endpoint.</span><span class="sxs-lookup"><span data-stu-id="bbf38-112">The boundary of this `MultiLineString` instance is the four endpoints.</span></span>  
  
-   <span data-ttu-id="bbf38-113">La figura 4 rappresenta un'istanza di tipo non semplice, non chiuso `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="bbf38-113">Figure 4 is a nonsimple, nonclosed `MultiLineString` instance.</span></span>  
  
-   <span data-ttu-id="bbf38-114">La figura 5 rappresenta un'istanza di tipo semplice, non chiuso `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="bbf38-114">Figure 5 is a simple, nonclosed `MultiLineString`.</span></span> <span data-ttu-id="bbf38-115">Non è chiuso perché i relativi `LineStrings` elementi non sono chiusi.</span><span class="sxs-lookup"><span data-stu-id="bbf38-115">It is not closed because its `LineStrings` elements are not closed.</span></span> <span data-ttu-id="bbf38-116">È semplice perché nessuna delle parti interne di alcuna istanza `LineStrings` si interseca.</span><span class="sxs-lookup"><span data-stu-id="bbf38-116">It is simple because none of the interiors of any of the `LineStrings` instances intersect.</span></span>  
  
-   <span data-ttu-id="bbf38-117">La figura 6 rappresenta un'istanza di tipo semplice e chiuso `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="bbf38-117">Figure 6 is a simple, closed `MultiLineString` instance.</span></span> <span data-ttu-id="bbf38-118">È chiusa perché tutti i suoi elementi sono chiusi.</span><span class="sxs-lookup"><span data-stu-id="bbf38-118">It is closed because all its elements are closed.</span></span> <span data-ttu-id="bbf38-119">È semplice perché nessuno dei suoi elementi si interseca con le parti interne.</span><span class="sxs-lookup"><span data-stu-id="bbf38-119">It is simple because none of its elements intersect at the interiors.</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="bbf38-120">Istanze accettate</span><span class="sxs-lookup"><span data-stu-id="bbf38-120">Accepted instances</span></span>  
 <span data-ttu-id="bbf38-121">Per poter essere accettata, un'istanza di `MultiLineString` deve essere vuota o comprendere esclusivamente istanze di `LineString` accettate.</span><span class="sxs-lookup"><span data-stu-id="bbf38-121">For a `MultiLineString` instance to be accepted it must either be empty or comprised of only `LineString` intances that are accepted.</span></span> <span data-ttu-id="bbf38-122">Per ulteriori informazioni sulle istanze accettate `LineString` , vedere [LineString](../spatial/linestring.md).</span><span class="sxs-lookup"><span data-stu-id="bbf38-122">For more information on accepted `LineString` instances, see [LineString](../spatial/linestring.md).</span></span> <span data-ttu-id="bbf38-123">Negli esempi seguenti vengono illustrate alcune istanze `MultiLineString` accettate.</span><span class="sxs-lookup"><span data-stu-id="bbf38-123">The following are examples of accepted `MultiLineString` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
```  
  
 <span data-ttu-id="bbf38-124">Nell'esempio seguente viene generata un'eccezione `System.FormatException`, poiché la seconda istanza di `LineString` non è valida.</span><span class="sxs-lookup"><span data-stu-id="bbf38-124">The following example throws a `System.FormatException` because the second `LineString` instance is not valid.</span></span>  
  
```  
DECLARE @g geometry = 'MULTILINESTRING((1 1, 3 5),(-5 3))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="bbf38-125">Istanze valide</span><span class="sxs-lookup"><span data-stu-id="bbf38-125">Valid instances</span></span>  
 <span data-ttu-id="bbf38-126">Per poter essere valida, un'istanza `MultiLineString` deve soddisfare i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbf38-126">For a `MultiLineString` instance to be valid it must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="bbf38-127">Tutte le istanze che comprendono l'istanza `MultiLineString` devono essere istanze `LineString` valide.</span><span class="sxs-lookup"><span data-stu-id="bbf38-127">All instances comprising the `MultiLineString` instance must be valid `LineString` instances.</span></span>  
  
2.  <span data-ttu-id="bbf38-128">Due istanze `LineString` che comprendono l'istanza di `MultiLineString` possono sovrapporsi a un intervallo.</span><span class="sxs-lookup"><span data-stu-id="bbf38-128">No two `LineString` instances comprising the `MultiLineString` instance may overlap over an interval.</span></span> <span data-ttu-id="bbf38-129">Le istanze di `LineString` possono solo intersecarsi oppure toccarsi reciprocamente o con altre istanze di `LineString` in un numero finito di punti.</span><span class="sxs-lookup"><span data-stu-id="bbf38-129">The `LineString` instances can only intersect or touch themselves or other `LineString` instances at a finite number of points.</span></span>  
  
 <span data-ttu-id="bbf38-130">Nell'esempio seguente vengono indicate tre istanze `MultiLineString` valide e un'istanza `MultiLineString` non valida.</span><span class="sxs-lookup"><span data-stu-id="bbf38-130">The following example shows three valid `MultiLineString` instances and one `MultiLineString` instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="bbf38-131">`@g4` non è valida, poiché la seconda istanza `LineString` si sovrappone alla prima istanza `LineString` in un intervallo.</span><span class="sxs-lookup"><span data-stu-id="bbf38-131">`@g4` is not valid because the second `LineString` instance overlaps the first `LineString` instance at an interval.</span></span> <span data-ttu-id="bbf38-132">Si toccano in un numero infinito di punti.</span><span class="sxs-lookup"><span data-stu-id="bbf38-132">They touch at an infinite number of points.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="bbf38-133">Esempi</span><span class="sxs-lookup"><span data-stu-id="bbf38-133">Examples</span></span>  
 <span data-ttu-id="bbf38-134">L'esempio seguente crea un'istanza `geometry``MultiLineString` che contiene due elementi `LineString` con SRID 0.</span><span class="sxs-lookup"><span data-stu-id="bbf38-134">The following example creates a simple `geometry``MultiLineString` instance containing two `LineString` elements with the SRID 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
```  
  
 <span data-ttu-id="bbf38-135">Per creare un'istanza di questa istanza con un diverso SRID, utilizzare `STGeomFromText()` o `STMLineStringFromText()`.</span><span class="sxs-lookup"><span data-stu-id="bbf38-135">To instantiate this instance with a different SRID, use `STGeomFromText()` or `STMLineStringFromText()`.</span></span> <span data-ttu-id="bbf38-136">È anche possibile utilizzare `Parse()` e quindi modificare l'identificatore SRID, come mostrato dall'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bbf38-136">You can also use `Parse()` and then modify the SRID, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
SET @g.STSrid = 13;  
```  
  
## <a name="see-also"></a><span data-ttu-id="bbf38-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbf38-137">See Also</span></span>  
 <span data-ttu-id="bbf38-138">[STLength &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="bbf38-138">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span></span>  
 <span data-ttu-id="bbf38-139">[STIsClosed &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="bbf38-139">[STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span></span>  
 <span data-ttu-id="bbf38-140">[LineString](../spatial/linestring.md) </span><span class="sxs-lookup"><span data-stu-id="bbf38-140">[LineString](../spatial/linestring.md) </span></span>  
 [<span data-ttu-id="bbf38-141">Dati spaziali &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bbf38-141">Spatial Data &#40;SQL Server&#41;</span></span>](../spatial/spatial-data-sql-server.md)  
  
  
