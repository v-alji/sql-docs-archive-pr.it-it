---
title: Panoramica dei tipi di dati spaziali | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], understanding
- geography data type [SQL Server], spatial data
- planar spatial data [SQL Server], geometry data type
- spatial data types [SQL Server]
ms.assetid: 1615db50-69de-4778-8be6-4e058c00ccd4
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c0548d974e83bfe2b1e103d4458b17078fba8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719758"
---
# <a name="spatial-data-types-overview"></a><span data-ttu-id="800af-102">Panoramica dei tipi di dati spaziali</span><span class="sxs-lookup"><span data-stu-id="800af-102">Spatial Data Types Overview</span></span>
  <span data-ttu-id="800af-103">Esistono due tipi di dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="800af-103">There are two types of spatial data.</span></span> <span data-ttu-id="800af-104">Il tipo di dati `geometry` supporta dati planari o euclidei (terra piatta).</span><span class="sxs-lookup"><span data-stu-id="800af-104">The `geometry` data type supports planar, or Euclidean (flat-earth), data.</span></span> <span data-ttu-id="800af-105">Il tipo di dati `geometry` è conforme a Open Geospatial Consortium (OGC) Simple Features for SQL Specification versione 1.1.0 e a SQL MM (standard ISO).</span><span class="sxs-lookup"><span data-stu-id="800af-105">The `geometry` data type both conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0 and is compliant with SQL MM (ISO standard).</span></span>

 <span data-ttu-id="800af-106">Inoltre, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supporta il tipo di dati `geography`, che archivia dati ellissoidali (terra rotonda), ad esempio coordinate di latitudine e longitudine GPS.</span><span class="sxs-lookup"><span data-stu-id="800af-106">In addition, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports the `geography` data type, which stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="800af-107">Per una descrizione dettagliata e alcuni esempi delle funzionalità spaziali introdotte in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], tra cui i miglioramenti apportati ai tipi di dati spaziali, scaricare il white paper [Nuove funzionalità spaziali di SQL Server, nome in codice "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="800af-107">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including enhancements to the spatial data types, download the white paper, [New Spatial Features in SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

##  <a name="spatial-data-objects"></a><a name="objects"></a> <span data-ttu-id="800af-108">Oggetti dati spaziali</span><span class="sxs-lookup"><span data-stu-id="800af-108">Spatial Data Objects</span></span>
 <span data-ttu-id="800af-109">I tipi di dati `geometry` e `geography` supportano sedici oggetti dati spaziali o tipi di istanza.</span><span class="sxs-lookup"><span data-stu-id="800af-109">The `geometry` and `geography` data types support sixteen spatial data objects, or instance types.</span></span> <span data-ttu-id="800af-110">Solo per undici di questi tipi di istanza, tuttavia, è possibile *creare istanze*. È possibile creare e usare queste istanze (o crearne un'istanza) in un database.</span><span class="sxs-lookup"><span data-stu-id="800af-110">However, only eleven of these instance types are *instantiable*; you can create and work with these instances (or instantiate them) in a database.</span></span> <span data-ttu-id="800af-111">Queste istanze derivano determinate proprietà dai relativi tipi di dati padre che li distinguono come `Points` , **LineStrings, istanze CircularString**, `CompoundCurves` , `Polygons` `CurvePolygons` o come più `geometry` `geography` istanze o in un oggetto `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="800af-111">These instances derive certain properties from their parent data types that distinguish them as `Points`, **LineStrings, CircularStrings**, `CompoundCurves`, `Polygons`, `CurvePolygons` or as multiple `geometry` or `geography` instances in a `GeometryCollection`.</span></span> <span data-ttu-id="800af-112">Il tipo `Geography` dispone di un tipo di istanza aggiuntivo, `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="800af-112">`Geography` type has an additional instance type, `FullGlobe`.</span></span>

 <span data-ttu-id="800af-113">Nella figura seguente viene illustrata la gerarchia `geometry` sulla quale si basano i tipi di dati `geometry` e `geography`.</span><span class="sxs-lookup"><span data-stu-id="800af-113">The figure below depicts the `geometry` hierarchy upon which the `geometry` and `geography` data types are based.</span></span> <span data-ttu-id="800af-114">I tipi istanziabile di `geometry` e `geography` sono indicati in blu.</span><span class="sxs-lookup"><span data-stu-id="800af-114">The instantiable types of `geometry` and `geography` are indicated in blue.</span></span>

 <span data-ttu-id="800af-115">![Gerarchia del tipo di geometria](../../database-engine/media/geom-hierarchy.gif "Gerarchia del tipo di geometria")</span><span class="sxs-lookup"><span data-stu-id="800af-115">![Hierarchy of the geometry type](../../database-engine/media/geom-hierarchy.gif "Hierarchy of the geometry type")</span></span>

 <span data-ttu-id="800af-116">Come indicato nella figura, i dieci tipi istanziabile dei `geometry` tipi di `geography` dati e sono `Point` , `MultiPoint` , `LineString` , `CircularString` , `MultiLineString` , `CompoundCurve` , `Polygon` , `CurvePolygon` , `MultiPolygon` e `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="800af-116">As the figure indicates, the ten instantiable types of the `geometry` and `geography` data types are `Point`, `MultiPoint`, `LineString`, `CircularString`, `MultiLineString`, `CompoundCurve`, `Polygon`, `CurvePolygon`, `MultiPolygon`, and `GeometryCollection`.</span></span> <span data-ttu-id="800af-117">Vi è un tipo aggiuntivo di cui è possibile creare istanze per il tipo di dati geography, ovvero `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="800af-117">There is one additional instantiable type for the geography data type: `FullGlobe`.</span></span> <span data-ttu-id="800af-118">I `geometry` `geography` tipi e possono riconoscere un'istanza specifica purché si tratta di un'istanza ben formata, anche se l'istanza non è definita in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="800af-118">The `geometry` and `geography` types can recognize a specific instance as long as it is a well-formed instance, even if the instance is not defined explicitly.</span></span> <span data-ttu-id="800af-119">Ad esempio, se si definisce un' `Point` istanza in modo esplicito utilizzando il metodo STPointFromText () `geometry` e si `geography` riconosce l'istanza come `Point` , purché l'input del metodo sia ben formato.</span><span class="sxs-lookup"><span data-stu-id="800af-119">For example, if you define a `Point` instance explicitly using the STPointFromText() method, `geometry` and `geography` recognize the instance as a `Point`, as long as the method input is well-formed.</span></span> <span data-ttu-id="800af-120">Se si definisce la stessa istanza utilizzando il metodo `STGeomFromText()`, entrambi i tipi di dati `geometry` e `geography` riconoscono l'istanza come `Point`.</span><span class="sxs-lookup"><span data-stu-id="800af-120">If you define the same instance using the `STGeomFromText()` method, both the `geometry` and `geography` data types recognize the instance as a `Point`.</span></span>

 <span data-ttu-id="800af-121">I sottotipi per i tipi geometry e geography sono divisi in tipi semplici e di raccolta.</span><span class="sxs-lookup"><span data-stu-id="800af-121">The subtypes for geometry and geography types are divided into simple and collection types.</span></span>  <span data-ttu-id="800af-122">Alcuni metodi come `STNumCurves()` possono essere utilizzati solo con tipi semplici.</span><span class="sxs-lookup"><span data-stu-id="800af-122">Some methods like `STNumCurves()` work only with simple types.</span></span>

 <span data-ttu-id="800af-123">I tipi semplici includono:</span><span class="sxs-lookup"><span data-stu-id="800af-123">Simple types include:</span></span>

-   [<span data-ttu-id="800af-124">Point</span><span class="sxs-lookup"><span data-stu-id="800af-124">Point</span></span>](../spatial/point.md)

-   [<span data-ttu-id="800af-125">LineString</span><span class="sxs-lookup"><span data-stu-id="800af-125">LineString</span></span>](../spatial/linestring.md)

-   [<span data-ttu-id="800af-126">CircularString</span><span class="sxs-lookup"><span data-stu-id="800af-126">CircularString</span></span>](../spatial/circularstring.md)

-   [<span data-ttu-id="800af-127">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="800af-127">CompoundCurve</span></span>](../spatial/compoundcurve.md)

-   [<span data-ttu-id="800af-128">Polygon</span><span class="sxs-lookup"><span data-stu-id="800af-128">Polygon</span></span>](../spatial/polygon.md)

-   [<span data-ttu-id="800af-129">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="800af-129">CurvePolygon</span></span>](../spatial/curvepolygon.md)

 <span data-ttu-id="800af-130">I tipi di raccolta includono:</span><span class="sxs-lookup"><span data-stu-id="800af-130">Collection types include:</span></span>

-   [<span data-ttu-id="800af-131">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="800af-131">MultiPoint</span></span>](../spatial/multipoint.md)

-   [<span data-ttu-id="800af-132">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="800af-132">MultiLineString</span></span>](../spatial/multilinestring.md)

-   [<span data-ttu-id="800af-133">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="800af-133">MultiPolygon</span></span>](../spatial/multipolygon.md)

-   [<span data-ttu-id="800af-134">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="800af-134">GeometryCollection</span></span>](../spatial/geometrycollection.md)


##  <a name="differences-between-the-geometry-and-geography-data-types"></a><a name="differences"></a> <span data-ttu-id="800af-135">Differenze tra i tipi di dati geometry e geography</span><span class="sxs-lookup"><span data-stu-id="800af-135">Differences Between the geometry and geography Data Types</span></span>
 <span data-ttu-id="800af-136">I due tipi di dati spaziali si comportano spesso in modo simile, ma esistono alcune differenze fondamentali nel modo in cui i dati vengono archiviati e modificati.</span><span class="sxs-lookup"><span data-stu-id="800af-136">The two types of spatial data often behave quite similarly, but there are some key differences in how the data is stored and manipulated.</span></span>

### <a name="how-connecting-edges-are-defined"></a><span data-ttu-id="800af-137">Definizione dei bordi di collegamento</span><span class="sxs-lookup"><span data-stu-id="800af-137">How connecting edges are defined</span></span>
 <span data-ttu-id="800af-138">I dati di definizione per i tipi `LineString` e `Polygon` sono solo vertici.</span><span class="sxs-lookup"><span data-stu-id="800af-138">The defining data for `LineString` and `Polygon` types are vertices only.</span></span>  <span data-ttu-id="800af-139">Il bordo di collegamento tra due vertici in un tipo geometry è una linea retta.</span><span class="sxs-lookup"><span data-stu-id="800af-139">The connecting edge between two vertices in a geometry type is a straight line.</span></span>  <span data-ttu-id="800af-140">Tuttavia, il bordo di collegamento tra due vertici in un tipo geografico è un corto arco di grande ellissi tra i due vertici.</span><span class="sxs-lookup"><span data-stu-id="800af-140">However, the connecting edge between two vertices in a geography type is a short great elliptic arc between the two vertices.</span></span>  <span data-ttu-id="800af-141">Una grande ellisse è l'intersezione dell'ellissoide con un piano attraverso il centro e un arco di grande ellisse è un segmento di arco sulla grande ellisse.</span><span class="sxs-lookup"><span data-stu-id="800af-141">A great ellipse is the intersection of the ellipsoid with a plane through its center and a great elliptic arc is an arc segment on the great ellipse.</span></span>

### <a name="how-circular-arc-segments-are-defined"></a><span data-ttu-id="800af-142">Definizione di segmenti di arco circolare</span><span class="sxs-lookup"><span data-stu-id="800af-142">How circular arc segments are defined</span></span>
 <span data-ttu-id="800af-143">I segmenti di arco circolare per i tipi geometry vengono definiti sul piano delle coordinate cartesiane XY (i valori Z vengono ignorati).</span><span class="sxs-lookup"><span data-stu-id="800af-143">Circular arc segments for geometry types are defined on the XY Cartesian coordinate plane (Z values are ignored).</span></span> <span data-ttu-id="800af-144">I segmenti di arco circolare per i tipi geography vengono definiti da segmenti di curva su una sfera di riferimento.</span><span class="sxs-lookup"><span data-stu-id="800af-144">Circular arc segments for geography types are defined by curve segments on a reference sphere.</span></span> <span data-ttu-id="800af-145">Qualsiasi parallelo sulla sfera di riferimento può essere definito da due archi circolari complementari in cui i punti per entrambi gli archi hanno un angolo di latitudine costante.</span><span class="sxs-lookup"><span data-stu-id="800af-145">Any parallel on the reference sphere can be defined by two complementary circular arcs where the points for both arcs have a constant latitude angle.</span></span>

### <a name="measurements-in-spatial-data-types"></a><span data-ttu-id="800af-146">Misurazioni nei tipi di dati spaziali</span><span class="sxs-lookup"><span data-stu-id="800af-146">Measurements in spatial data types</span></span>
 <span data-ttu-id="800af-147">Nel sistema planare, o terra piatta, le misurazioni delle distanze e delle aree vengono fornite nella stessa unità di misurazione delle coordinate.</span><span class="sxs-lookup"><span data-stu-id="800af-147">In the planar, or flat-earth, system, measurements of distances and areas are given in the same unit of measurement as coordinates.</span></span> <span data-ttu-id="800af-148">Utilizzando il tipo di dati `geometry`, la distanza tra (2, 2) e (5, 6) è 5 unità, indipendentemente dalle unità utilizzate.</span><span class="sxs-lookup"><span data-stu-id="800af-148">Using the `geometry` data type, the distance between (2, 2) and (5, 6) is 5 units, regardless of the units used.</span></span>

 <span data-ttu-id="800af-149">Nel sistema ellissoidale, o terra rotonda, le coordinate sono fornite in gradi di latitudine e longitudine.</span><span class="sxs-lookup"><span data-stu-id="800af-149">In the ellipsoidal, or round-earth system, coordinates are given in degrees of latitude and longitude.</span></span> <span data-ttu-id="800af-150">Tuttavia, le lunghezze e le aree sono misurate generalmente in metri e metri quadrati, sebbene la misurazione possa dipendere dall'identificatore di riferimento spaziale (SRID) dell'istanza `geography`.</span><span class="sxs-lookup"><span data-stu-id="800af-150">However, lengths and areas are usually measured in meters and square meters, though the measurement may depend on the spatial reference identifier (SRID) of the `geography` instance.</span></span> <span data-ttu-id="800af-151">L'unità di misurazione più comune per il tipo di dati `geography` è il metro.</span><span class="sxs-lookup"><span data-stu-id="800af-151">The most common unit of measurement for the `geography` data type is meters.</span></span>

### <a name="orientation-of-spatial-data"></a><span data-ttu-id="800af-152">Orientamento dei dati spaziali</span><span class="sxs-lookup"><span data-stu-id="800af-152">Orientation of spatial data</span></span>
 <span data-ttu-id="800af-153">Nel sistema planare l'orientamento dell'anello di un poligono non è un fattore di particolare rilevanza.</span><span class="sxs-lookup"><span data-stu-id="800af-153">In the planar system, the ring orientation of a polygon is not an important factor.</span></span> <span data-ttu-id="800af-154">Ad esempio, un poligono descritto da ((0, 0), (10, 0), (0, 20), (0, 0)) è identico al poligono descritto da ((0, 0), (0, 20), (10, 0), (0, 0)).</span><span class="sxs-lookup"><span data-stu-id="800af-154">For example, a polygon described by ((0, 0), (10, 0), (0, 20), (0, 0)) is the same as a polygon described by ((0, 0), (0, 20), (10, 0), (0, 0)).</span></span> <span data-ttu-id="800af-155">OGC Simple Features for SQL Specification non indica un ordinamento dell'anello e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] non impone tale ordinamento.</span><span class="sxs-lookup"><span data-stu-id="800af-155">The OGC Simple Features for SQL Specification does not dictate a ring ordering, and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not enforce ring ordering.</span></span>

 <span data-ttu-id="800af-156">In un sistema ellissoidale, un poligono non ha significato, o è ambiguo, senza un orientamento.</span><span class="sxs-lookup"><span data-stu-id="800af-156">In an ellipsoidal system, a polygon has no meaning, or is ambiguous, without an orientation.</span></span> <span data-ttu-id="800af-157">Ad esempio, un anello intorno all'equatore descrive l'emisfero nord o sud?</span><span class="sxs-lookup"><span data-stu-id="800af-157">For example, does a ring around the equator describe the northern or southern hemisphere?</span></span> <span data-ttu-id="800af-158">Se si utilizza il tipo di dati `geography` per archiviare l'istanza spaziale, è necessario specificare l'orientamento dell'anello e descrivere accuratamente la posizione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="800af-158">If we use the `geography` data type to store the spatial instance, we must specify the orientation of the ring and accurately describe the location of the instance.</span></span> <span data-ttu-id="800af-159">L'interno del poligono in un sistema ellissoidale è definito dal lato sinistro della regola.</span><span class="sxs-lookup"><span data-stu-id="800af-159">The interior of the polygon in an ellipsoidal system is defined by the left-hand rule.</span></span>

 <span data-ttu-id="800af-160">Quando il livello di compatibilità è 100 o inferiore in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] `geography` , il tipo di dati presenta le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="800af-160">When the compatibility level is 100 or below in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] then the `geography` data type has the following restrictions:</span></span>

-   <span data-ttu-id="800af-161">Ogni istanza `geography` deve adattarsi all'interno di un singolo emisfero.</span><span class="sxs-lookup"><span data-stu-id="800af-161">Each `geography` instance must fit inside a single hemisphere.</span></span> <span data-ttu-id="800af-162">Non è possibile archiviare oggetti spaziali con dimensioni maggiori di un emisfero.</span><span class="sxs-lookup"><span data-stu-id="800af-162">No spatial objects larger than a hemisphere can be stored.</span></span>

-   <span data-ttu-id="800af-163">Qualsiasi istanza `geography` di una rappresentazione Well-Known Text (WKT) o Well-Known Binary (WKB) OCG che produca un oggetto più grande di un emisfero genera una `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="800af-163">Any `geography` instance from an Open Geospatial Consortium (OGC) Well-Known Text (WKT) or Well-Known Binary (WKB) representation that produces an object larger than a hemisphere throws an `ArgumentException`.</span></span>

-   <span data-ttu-id="800af-164">I `geography` metodi con tipo di dati che richiedono l'input di due `geography` istanze, ad esempio STIntersection (), STUnion (), STDifference () e STSymDifference (), restituiranno null se i risultati dei metodi non si adattano a un singolo emisfero.</span><span class="sxs-lookup"><span data-stu-id="800af-164">The `geography` data type methods that require the input of two `geography` instances, such as STIntersection(), STUnion(), STDifference(), and STSymDifference(), will return null if the results from the methods do not fit inside a single hemisphere.</span></span> <span data-ttu-id="800af-165">Anche STBuffer() restituirà Null se l'output supera un singolo emisfero.</span><span class="sxs-lookup"><span data-stu-id="800af-165">STBuffer() will also return null if the output exceeds a single hemisphere.</span></span>

 <span data-ttu-id="800af-166">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]`FullGlobe` è un tipo speciale di Polygon che copre l'intero globo.</span><span class="sxs-lookup"><span data-stu-id="800af-166">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` is a special type of Polygon that covers the entire globe.</span></span> <span data-ttu-id="800af-167">`FullGlobe` dispone di un'area, ma non ha bordi o vertici.</span><span class="sxs-lookup"><span data-stu-id="800af-167">`FullGlobe` has an area, but no borders or vertices.</span></span>

### <a name="outer-and-inner-rings-not-important-in-geography-data-type"></a><span data-ttu-id="800af-168">Anelli interni ed esterni non rilevanti nel tipo di dati geography</span><span class="sxs-lookup"><span data-stu-id="800af-168">Outer and inner rings not important in geography data type</span></span>
 <span data-ttu-id="800af-169">In OGC Simple Features for SQL Specification vengono trattati anelli esterni e interni, ma questa distinzione non è molto utile per il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` tipo di dati; qualsiasi anello di un poligono può essere considerato come l'anello esterno.</span><span class="sxs-lookup"><span data-stu-id="800af-169">The OGC Simple Features for SQL Specification discusses outer rings and inner rings, but this distinction makes little sense for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` data type; any ring of a polygon can be taken to be the outer ring.</span></span>

 <span data-ttu-id="800af-170">Per ulteriori informazioni sulle specifiche OGC, vedere quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="800af-170">For more information on OGC specifications, see the following:</span></span>

-   [<span data-ttu-id="800af-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span><span class="sxs-lookup"><span data-stu-id="800af-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93627)

-   <span data-ttu-id="800af-172">[OGC Specifications, Simple Feature Access Part 2 - SQL Options](https://go.microsoft.com/fwlink/?LinkId=93628) (Specifiche OGC, accesso semplificato alle caratteristiche Parte 2 - Opzioni SQL)</span><span class="sxs-lookup"><span data-stu-id="800af-172">[OGC Specifications, Simple Feature Access Part 2 - SQL Options](https://go.microsoft.com/fwlink/?LinkId=93628)</span></span>


##  <a name="circular-arc-segments"></a><a name="circular"></a> <span data-ttu-id="800af-173">Segmenti di arco circolare</span><span class="sxs-lookup"><span data-stu-id="800af-173">Circular Arc Segments</span></span>
 <span data-ttu-id="800af-174">Tre tipi di cui è possibile creare istanze possono accettare segmenti di arco circolare: `CircularString`, `CompoundCurve` e `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="800af-174">Three instantiable types can take circular arc segments: `CircularString`, `CompoundCurve`, and `CurvePolygon`.</span></span>  <span data-ttu-id="800af-175">Un segmento di arco circolare è definito da tre punti in un piano bidimensionale. Il terzo punto non può corrispondere al primo punto.</span><span class="sxs-lookup"><span data-stu-id="800af-175">A circular arc segment is defined by three points in a two dimensional plane and the third point cannot be the same as the first point.</span></span>

 <span data-ttu-id="800af-176">Nelle figure A e B vengono illustrati segmenti di arco circolare tipici.</span><span class="sxs-lookup"><span data-stu-id="800af-176">Figures A and B show typical circular arc segments.</span></span> <span data-ttu-id="800af-177">Si noti come ognuno dei tre punti giace sul perimetro di un cerchio.</span><span class="sxs-lookup"><span data-stu-id="800af-177">Note how each of the three points lie on the perimeter of a circle.</span></span>

 <span data-ttu-id="800af-178">Nelle figure C e D viene illustrato come un segmento di linea possa essere definito segmento di arco circolare.</span><span class="sxs-lookup"><span data-stu-id="800af-178">Figures C and D show how a line segment can be defined as a circular arc segment.</span></span>  <span data-ttu-id="800af-179">Si noti che sono ancora necessari tre punti per definire il segmento di arco circolare, diversamente da un segmento di linea regolare, che può essere definito solo da due punti.</span><span class="sxs-lookup"><span data-stu-id="800af-179">Note that three points are still needed to define the circular arc segment unlike a regular line segment which can be defined by just two points.</span></span>

 <span data-ttu-id="800af-180">I metodi che operano sui tipi di segmento di arco circolare utilizzano segmenti di linea retta per simulare l'arco circolare. Il numero di segmenti di linea utilizzati per simulare l'arco dipenderanno dalla lunghezza e dalla curvatura dell'arco. Benché sia possibile archiviare i valori Z per ognuno dei tipi di segmento di arco circolare, i metodi non utilizzeranno i valori Z nei calcoli.</span><span class="sxs-lookup"><span data-stu-id="800af-180">Methods operating on circular arc segment types use straight line segments to approximate the circular arc. The number of line segments used to approximate the arc will depend on the length and curvature of the arc. Z values can be stored for each of the circular arc segment types; however, methods will not use the Z values in their calculations.</span></span>

> [!NOTE]
>  <span data-ttu-id="800af-181">Se si specificano valori Z per segmenti di arco circolare, tali valori devono essere gli stessi per tutti i punti nel segmento di arco circolare perché questo venga accettato per l'input.</span><span class="sxs-lookup"><span data-stu-id="800af-181">If Z values are given for circular arc segments then they must be the same for all points in the circular arc segment for it to be accepted for input.</span></span> <span data-ttu-id="800af-182">Ad esempio, `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` è ammesso, mentre `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` non lo è.</span><span class="sxs-lookup"><span data-stu-id="800af-182">For example: `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` is accepted, but `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` is not accepted.</span></span>

### <a name="linestring-and-circularstring-comparison"></a><span data-ttu-id="800af-183">Confronto tra LineString e CircularString</span><span class="sxs-lookup"><span data-stu-id="800af-183">LineString and CircularString comparison</span></span>
 <span data-ttu-id="800af-184">Nel diagramma seguente vengono illustrati triangoli isosceli identici. Nel triangolo A vengono utilizzati segmenti di linea per definire il triangolo, mentre nel triangolo B vengono utilizzati segmenti di arco circolare.</span><span class="sxs-lookup"><span data-stu-id="800af-184">The following diagram shows identical isosceles triangles (triangle A uses line segments to define the triangle and triangle B uses circular arc segments to defined the triangle):</span></span>

 ![](../../database-engine/media/7e382f76-59da-4b62-80dc-caf93e637c14.png "7e382f76-59da-4b62-80dc-caf93e637c14")

 <span data-ttu-id="800af-185">In questo esempio viene illustrato come archiviare i triangoli isosceli precedenti utilizzando un'istanza `LineString` e un'istanza `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="800af-185">This example shows how to store the above isosceles triangles using both a `LineString` instance and `CircularString` instance:</span></span>

```sql
DECLARE @g1 geometry;
DECLARE @g2 geometry;
SET @g1 = geometry::STGeomFromText('LINESTRING(1 1, 5 1, 3 5, 1 1)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(1 1, 3 1, 5 1, 4 3, 3 5, 2 3, 1 1)', 0);
IF @g1.STIsValid() = 1 AND @g2.STIsValid() = 1
  BEGIN
      SELECT @g1.ToString(), @g2.ToString()
      SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length]
  END
```

 <span data-ttu-id="800af-186">Si noti che un'istanza `CircularString` richiede sette punti per definire il triangolo, mentre un'istanza `LineString` richiede solo quattro punti.</span><span class="sxs-lookup"><span data-stu-id="800af-186">Notice that a `CircularString` instance requires seven points to define the triangle, but a `LineString` instance requires only four points to define the triangle.</span></span> <span data-ttu-id="800af-187">Il motivo è che un'istanza `CircularString` archivia segmenti di arco circolare e non segmenti di linea.</span><span class="sxs-lookup"><span data-stu-id="800af-187">The reason for this is that a `CircularString` instance stores circular arc segments and not line segments.</span></span> <span data-ttu-id="800af-188">Di conseguenza, i lati del triangolo archiviati nell'istanza `CircularString` sono ABC, CDE ed EFA, mentre i lati del triangolo archiviati nell'istanza `LineString` sono AC, CE ed EA.</span><span class="sxs-lookup"><span data-stu-id="800af-188">So the sides of the triangle stored in the `CircularString` instance are ABC, CDE, and EFA whereas the sides of the triangle stored in the `LineString` instance are AC, CE, and EA.</span></span>

 <span data-ttu-id="800af-189">Si consideri il frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="800af-189">Consider the following code snippet:</span></span>

```sql
SET @g1 = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 4 0)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(0 0, 2 2, 4 0)', 0);
SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length];
```

 <span data-ttu-id="800af-190">Il frammento di codice produrrà i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="800af-190">This snippet will produce the following results:</span></span>

```
LS LengthCS Length
5.65685...6.28318...
```

 <span data-ttu-id="800af-191">Nella figura seguente viene illustrato il modo in cui viene archiviato ogni tipo (la linea rossa mostra la `LineString``@g1` linea blu `CircularString``@g2` ):</span><span class="sxs-lookup"><span data-stu-id="800af-191">The following illustration shows how each type is stored (red line shows `LineString``@g1`, blue line shows `CircularString``@g2`):</span></span>

 ![](../../database-engine/media/e52157b5-5160-4a4b-8560-50cdcf905b76.png "e52157b5-5160-4a4b-8560-50cdcf905b76")

 <span data-ttu-id="800af-192">Come illustrato nella figura precedente, le istanze `CircularString` utilizzano un numero minore di punti per archiviare i limiti delle curve con maggiore precisione delle istanze `LineString`.</span><span class="sxs-lookup"><span data-stu-id="800af-192">As the illustration above shows, `CircularString` instances use fewer points to store curve boundaries with greater precision than `LineString` instances.</span></span> <span data-ttu-id="800af-193">Le istanze `CircularString` sono ideali per l'archiviazione di limiti circolari come un raggio cercato di venti miglia da un punto specifico.</span><span class="sxs-lookup"><span data-stu-id="800af-193">`CircularString` instances are useful for storing circular boundaries like a twenty-mile search radius from a specific point.</span></span> <span data-ttu-id="800af-194">Le istanze `LineString` sono ideali per l'archiviazione di limiti lineari come un blocco urbano quadrato.</span><span class="sxs-lookup"><span data-stu-id="800af-194">`LineString` instances are good for storing boundaries that are linear like a square city block.</span></span>

### <a name="linestring-and-compoundcurve-comparison"></a><span data-ttu-id="800af-195">Confronto tra LineString e CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="800af-195">LineString and CompoundCurve comparison</span></span>
 <span data-ttu-id="800af-196">Negli esempi di codice seguenti viene illustrato come archiviare la stessa figura utilizzando istanze `LineString` e `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="800af-196">The following code examples show how to store the same figure using `LineString` and `CompoundCurve` instances:</span></span>

```sql
SET @g = geometry::Parse('LINESTRING(2 2, 4 2, 4 4, 2 4, 2 2)');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2), (4 2, 4 4), (4 4, 2 4), (2 4, 2 2))');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2, 4 4, 2 4, 2 2))');
```

 <span data-ttu-id="800af-197">oppure</span><span class="sxs-lookup"><span data-stu-id="800af-197">or</span></span>

 <span data-ttu-id="800af-198">Negli esempi precedenti un'istanza `LineString` o un'istanza `CompoundCurve` potrebbe archiviare la figura.</span><span class="sxs-lookup"><span data-stu-id="800af-198">In the examples above, either a `LineString` instance or a `CompoundCurve` instance could store the figure.</span></span>  <span data-ttu-id="800af-199">Nell'esempio seguente viene utilizzata un'istanza `CompoundCurve` per archiviare una sezione di un grafico a torta:</span><span class="sxs-lookup"><span data-stu-id="800af-199">This next example uses a `CompoundCurve` to store a pie slice:</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(2 2, 1 3, 0 2),(0 2, 1 0, 2 2))');
```

 <span data-ttu-id="800af-200">Un'istanza `CompoundCurve` consente di archiviare direttamente il segmento di arco circolare (2 2, 1 3, 0 2), mentre con un'istanza `LineString` è necessario convertire la curva in diversi segmenti di linea più piccoli.</span><span class="sxs-lookup"><span data-stu-id="800af-200">A `CompoundCurve` instance can store the circular arc segment (2 2, 1 3, 0 2) directly whereas a `LineString` instance would have to convert the curve into several smaller line segments.</span></span>

### <a name="circularstring-and-compoundcurve-comparison"></a><span data-ttu-id="800af-201">Confronto tra CircularString e CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="800af-201">CircularString and CompoundCurve comparison</span></span>
 <span data-ttu-id="800af-202">Nell'esempio di codice seguente viene illustrata l'archiviazione di una sezione di un grafico a torta in un'istanza `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="800af-202">The following code example shows how the pie slice can be stored in a `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');
SELECT @g.ToString(), @g.STLength();
```

 <span data-ttu-id="800af-203">Per archiviare la sezione del grafico a torta utilizzando un'istanza `CircularString`, è necessario utilizzare tre punti per ogni segmento di linea.</span><span class="sxs-lookup"><span data-stu-id="800af-203">To store the pie slice using a `CircularString` instance requires that three points be used for each line segment.</span></span>  <span data-ttu-id="800af-204">Se un punto intermedio non è noto, deve essere calcolato oppure è necessario raddoppiare l'endpoint del segmento di linea, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="800af-204">If an intermediate point is not known, it either has to be calculated or the endpoint of the line segment has to be doubled as the following snippet shows:</span></span>

```sql
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 3 6.3246, 3 6.3246, 0 7, -3 6.3246, 0 0, 0 0)');
```

 <span data-ttu-id="800af-205">`CompoundCurve`le istanze consentono `LineString` entrambi `CircularString` i componenti e, in modo che sia necessario conoscere solo due punti nei segmenti di linea della fetta di torta.</span><span class="sxs-lookup"><span data-stu-id="800af-205">`CompoundCurve` instances allow both `LineString` and `CircularString` components so that only two points to the line segments of the pie slice need to be known.</span></span>  <span data-ttu-id="800af-206">In questo esempio di codice viene illustrato come utilizzare un'istanza `CompoundCurve` per archiviare la stessa figura:</span><span class="sxs-lookup"><span data-stu-id="800af-206">This code example shows how to use a `CompoundCurve` to store the same figure:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING( 3 6.3246, 0 7, -3 6.3246), (-3 6.3246, 0 0, 3 6.3246))');
SELECT @g.ToString(), @g.STLength();
```

### <a name="polygon-and-curvepolygon-comparison"></a><span data-ttu-id="800af-207">Confronto tra Polygon e CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="800af-207">Polygon and CurvePolygon comparison</span></span>
 <span data-ttu-id="800af-208">Le istanze `CurvePolygon` possono utilizzare istanze `CircularString` e `CompoundCurve` per definire i relativi anelli esterni e interni.</span><span class="sxs-lookup"><span data-stu-id="800af-208">`CurvePolygon` instances can use `CircularString` and `CompoundCurve` instances when defining their exterior and interior rings.</span></span>  <span data-ttu-id="800af-209">Le istanze `Polygon` non possono utilizzare i tipi di segmento di arco circolare: `CircularString` e `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="800af-209">`Polygon` instances cannot use the circular arc segment types: `CircularString` and `CompoundCurve`.</span></span>


## <a name="see-also"></a><span data-ttu-id="800af-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="800af-210">See Also</span></span>
 <span data-ttu-id="800af-211">[Dati spaziali &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [metodo del tipo di dati geometry riferimento al metodo](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) del tipo di dati [geography](/sql/t-sql/spatial-geography/spatial-types-geography) [riferimento STNumCurves &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;tipo di dati geography&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) STGeomFromText &#40;tipo di [dati geometry&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;tipo di dati geography&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span><span class="sxs-lookup"><span data-stu-id="800af-211">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) [geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span></span>


