---
title: CurvePolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e000a1d8-a049-4542-bfeb-943fd6ab3969
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b90fdbd9a0bc80dfc6a82416d0193b2951fe13ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624562"
---
# <a name="curvepolygon"></a><span data-ttu-id="577e6-102">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="577e6-102">CurvePolygon</span></span>
  <span data-ttu-id="577e6-103">Un'istanza `CurvePolygon` è una superficie topologicamente chiusa definita da un anello di delimitazione esterno e nessuno o più anelli interni</span><span class="sxs-lookup"><span data-stu-id="577e6-103">A `CurvePolygon` is a topologically closed surface defined by an exterior bounding ring and zero or more interior rings</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="577e6-104">Per una descrizione dettagliata ed esempi delle funzionalità spaziali introdotte in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , incluso il `CurvePolygon` sottotipo, scaricare il white paper, [nuove funzionalità spaziali in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="577e6-104">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CurvePolygon` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="577e6-105">I criteri seguenti definiscono gli attributi di un' `CurvePolygon` istanza:</span><span class="sxs-lookup"><span data-stu-id="577e6-105">The following criteria define attributes of a `CurvePolygon` instance:</span></span>  
  
-   <span data-ttu-id="577e6-106">Il limite dell'istanza `CurvePolygon` viene definito dall'anello esterno e da tutti gli anelli interni.</span><span class="sxs-lookup"><span data-stu-id="577e6-106">The boundary of the `CurvePolygon` instance is defined by the exterior ring and all interior rings.</span></span>  
  
-   <span data-ttu-id="577e6-107">L'interno dell'istanza `CurvePolygon` è lo spazio tra l'anello esterno e tutti gli anelli interni.</span><span class="sxs-lookup"><span data-stu-id="577e6-107">The interior of the `CurvePolygon` instance is the space between the exterior ring and all of the interior rings.</span></span>  
  
 <span data-ttu-id="577e6-108">Un'istanza `CurvePolygon` differisce da un'istanza `Polygon` per il fatto che un'istanza `CurvePolygon` può contenere i segmenti di arco circolare seguenti: `CircularString` e `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="577e6-108">A `CurvePolygon` instance differs from a `Polygon` instance in that a `CurvePolygon` instance may contain the following circular arc segments: `CircularString` and `CompoundCurve`.</span></span>  
  
## <a name="compoundcurve-instances"></a><span data-ttu-id="577e6-109">Istanze CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="577e6-109">CompoundCurve instances</span></span>  
 <span data-ttu-id="577e6-110">Nell'illustrazione seguente vengono illustrate figure `CurvePolygon` valide:</span><span class="sxs-lookup"><span data-stu-id="577e6-110">Illustration below shows valid `CurvePolygon` figures:</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="577e6-111">Istanze accettate</span><span class="sxs-lookup"><span data-stu-id="577e6-111">Accepted instances</span></span>  
 <span data-ttu-id="577e6-112">Per poter essere accettata, un'istanza `CurvePolygon` deve essere vuota o contenere solo anelli di arco circolare accettati.</span><span class="sxs-lookup"><span data-stu-id="577e6-112">For a `CurvePolygon` instance to be accepted, it needs to be either empty or contain only circular arc rings that are accepted.</span></span> <span data-ttu-id="577e6-113">Un anello di arco circolare accettato soddisfa i requisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="577e6-113">An accepted circular arc ring meets the following requirements.</span></span>  
  
1.  <span data-ttu-id="577e6-114">È un'istanza `LineString`, `CircularString` o `CompoundCurve` accettata.</span><span class="sxs-lookup"><span data-stu-id="577e6-114">Is an accepted `LineString`, `CircularString`, or `CompoundCurve` instance.</span></span> <span data-ttu-id="577e6-115">Per altre informazioni sulle istanze accettate, vedere [LineString](linestring.md), [CircularString](circularstring.md)e [CompoundCurve](compoundcurve.md).</span><span class="sxs-lookup"><span data-stu-id="577e6-115">For more information on accepted instances, see [LineString](linestring.md), [CircularString](circularstring.md), and [CompoundCurve](compoundcurve.md).</span></span>  
  
2.  <span data-ttu-id="577e6-116">Dispone almeno di quattro punti.</span><span class="sxs-lookup"><span data-stu-id="577e6-116">Has at least four points.</span></span>  
  
3.  <span data-ttu-id="577e6-117">I punti iniziale e finale condividono le stesse coordinate X e Y.</span><span class="sxs-lookup"><span data-stu-id="577e6-117">The start and end point have the same X and Y coordinates.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="577e6-118">I valori Z e ; vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="577e6-118">Z and M values are ignored.</span></span>  
  
 <span data-ttu-id="577e6-119">Nell'esempio seguente vengono illustrate le istanze `CurvePolygon` accettate.</span><span class="sxs-lookup"><span data-stu-id="577e6-119">The following example shows accepted `CurvePolygon` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0, 0 0))';  
DECLARE @g3 geometry = 'CURVEPOLYGON((0 0 1, 0 0 2, 0 0 3, 0 0 3))'  
DECLARE @g4 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
DECLARE @g5 geography = 'CURVEPOLYGON((-122.3 47, 122.3 -47, 125.7 -49, 121 -38, -122.3 47))';  
```  
  
 <span data-ttu-id="577e6-120">`@g3` viene accettata anche se i punti iniziale e finale hanno valori Z diversi perché i valori Z vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="577e6-120">`@g3` is accepted even though the start and end points have different Z values because Z values are ignored.</span></span> <span data-ttu-id="577e6-121">`@g5` viene accettata anche se l'istanza del tipo `geography` non è valida.</span><span class="sxs-lookup"><span data-stu-id="577e6-121">`@g5` is accepted even though the `geography` type instance is not valid.</span></span>  
  
 <span data-ttu-id="577e6-122">Gli esempi seguenti generano `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="577e6-122">The following examples throw `System.FormatException`.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON((0 5, 0 0, 0 0, 0 0))';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0))';  
```  
  
 <span data-ttu-id="577e6-123">`@g1` non viene accettata perché i punti iniziale e finale non hanno lo stesso valore Y.</span><span class="sxs-lookup"><span data-stu-id="577e6-123">`@g1` is not accepted because the start and end points do not have the same Y value.</span></span> <span data-ttu-id="577e6-124">`@g2` non viene accettata perché l'anello non dispone di un numero di punti sufficiente.</span><span class="sxs-lookup"><span data-stu-id="577e6-124">`@g2` is not accepted because the ring does not have enough points.</span></span>  
  
### <a name="valid-instances"></a><span data-ttu-id="577e6-125">Istanze valide</span><span class="sxs-lookup"><span data-stu-id="577e6-125">Valid instances</span></span>  
 <span data-ttu-id="577e6-126">Perché un'istanza `CurvePolygon` sia valida, è necessario che l'anello interno e quello esterno soddisfino i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="577e6-126">For a `CurvePolygon` instance to be valid both exterior and interior rings must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="577e6-127">Possono toccarsi solo in corrispondenza di singoli punti tangenti.</span><span class="sxs-lookup"><span data-stu-id="577e6-127">They may only touch at single tangent points.</span></span>  
  
2.  <span data-ttu-id="577e6-128">Non possono incrociarsi.</span><span class="sxs-lookup"><span data-stu-id="577e6-128">They cannot cross each other.</span></span>  
  
3.  <span data-ttu-id="577e6-129">Ogni anello deve contenere almeno quattro punti.</span><span class="sxs-lookup"><span data-stu-id="577e6-129">Each ring must contain at least four points.</span></span>  
  
4.  <span data-ttu-id="577e6-130">Ogni anello deve essere un tipo di curva accettabile.</span><span class="sxs-lookup"><span data-stu-id="577e6-130">Each ring must be an acceptable curve type.</span></span>  
  
 <span data-ttu-id="577e6-131">Le istanze `CurvePolygon` devono inoltre soddisfare criteri specifici a seconda di se sono di un tipo di dati `geometry` o `geography`.</span><span class="sxs-lookup"><span data-stu-id="577e6-131">`CurvePolygon` instances also need to meet specific criteria depending on whether they are `geometry` or `geography` data types.</span></span>  
  
#### <a name="geometry-data-type"></a><span data-ttu-id="577e6-132">Tipo di dati geometry</span><span class="sxs-lookup"><span data-stu-id="577e6-132">Geometry data type</span></span>  
 <span data-ttu-id="577e6-133">Un'istanza **geometryCurvePolygon** valida deve avere gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="577e6-133">A valid **geometryCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="577e6-134">Tutti gli anelli interni devono essere contenuti nell'anello esterno.</span><span class="sxs-lookup"><span data-stu-id="577e6-134">All the interior rings must be contained within the exterior ring.</span></span>  
  
2.  <span data-ttu-id="577e6-135">Può disporre di più anelli interni, ma un anello interno non può contenere un altro anello interno.</span><span class="sxs-lookup"><span data-stu-id="577e6-135">May have multiple interior rings, but an interior ring cannot contain another interior ring.</span></span>  
  
3.  <span data-ttu-id="577e6-136">Nessun anello può incrociare se stesso o un altro anello.</span><span class="sxs-lookup"><span data-stu-id="577e6-136">No ring can cross itself or another ring.</span></span>  
  
4.  <span data-ttu-id="577e6-137">Gli anelli possono toccarsi solo in corrispondenza di singoli punti tangenti (il numero di punti dove gli anelli si toccano deve essere limitato).</span><span class="sxs-lookup"><span data-stu-id="577e6-137">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
5.  <span data-ttu-id="577e6-138">L'interno del poligono deve essere connesso.</span><span class="sxs-lookup"><span data-stu-id="577e6-138">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="577e6-139">L'esempio seguente illustra un'istanza **geometryCurvePolygon** valida.</span><span class="sxs-lookup"><span data-stu-id="577e6-139">The following example shows valid **geometryCurvePolygon** instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
SELECT @g1.STIsValid(), @g2.STIsValid();  
```  
  
 <span data-ttu-id="577e6-140">Le istanze CurvePolygon dispongono delle stesse regole di validità delle istanze Polygon, ad eccezione del fatto che le istanze CurvePolygon possono accettare i nuovi tipi di segmento di arco circolare.</span><span class="sxs-lookup"><span data-stu-id="577e6-140">CurvePolygon instances have the same validity rules as Polygon instances with the exception that CurvePolygon instances may accept the new circular arc segment types.</span></span> <span data-ttu-id="577e6-141">Per altri esempi di istanze valide o non valide, vedere [Polygon](polygon.md).</span><span class="sxs-lookup"><span data-stu-id="577e6-141">For more examples of instances that are valid or not valid, see [Polygon](polygon.md).</span></span>  
  
#### <a name="geography-data-type"></a><span data-ttu-id="577e6-142">Tipo di dati geography</span><span class="sxs-lookup"><span data-stu-id="577e6-142">Geography data type</span></span>  
 <span data-ttu-id="577e6-143">Un'istanza **geographyCurvePolygon** valida deve avere gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="577e6-143">A valid **geographyCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="577e6-144">L'interno del poligono viene connesso utilizzando il lato sinistro della regola.</span><span class="sxs-lookup"><span data-stu-id="577e6-144">The interior of the polygon is connected using the left-hand rule.</span></span>  
  
2.  <span data-ttu-id="577e6-145">Nessun anello può incrociare se stesso o un altro anello.</span><span class="sxs-lookup"><span data-stu-id="577e6-145">No ring can cross itself or another ring.</span></span>  
  
3.  <span data-ttu-id="577e6-146">Gli anelli possono toccarsi solo in corrispondenza di singoli punti tangenti (il numero di punti dove gli anelli si toccano deve essere limitato).</span><span class="sxs-lookup"><span data-stu-id="577e6-146">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
4.  <span data-ttu-id="577e6-147">L'interno del poligono deve essere connesso.</span><span class="sxs-lookup"><span data-stu-id="577e6-147">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="577e6-148">Nell'esempio seguente viene illustrata un'istanza CurvePolygon geography valida.</span><span class="sxs-lookup"><span data-stu-id="577e6-148">The following example shows a valid geography CurvePolygon instance.</span></span>  
  
```  
DECLARE @g geography = 'CURVEPOLYGON((-122.3 47, 122.3 47, 125.7 49, 121 38, -122.3 47))';  
SELECT @g.STIsValid();  
```  
  
## <a name="examples"></a><span data-ttu-id="577e6-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="577e6-149">Examples</span></span>  
  
### <a name="a-instantiating-a-geometry-instance-with-an-empty-curvepolygon"></a><span data-ttu-id="577e6-150">R.</span><span class="sxs-lookup"><span data-stu-id="577e6-150">A.</span></span> <span data-ttu-id="577e6-151">Creazione di un'istanza Geometry con un'istanza CurvePolygon vuota</span><span class="sxs-lookup"><span data-stu-id="577e6-151">Instantiating a Geometry Instance with an Empty CurvePolygon</span></span>  
 <span data-ttu-id="577e6-152">In questo esempio viene illustrato come creare un'istanza `CurvePolygon` vuota:</span><span class="sxs-lookup"><span data-stu-id="577e6-152">This example shows how to create an empty `CurvePolygon` instance:</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON EMPTY');  
```  
  
### <a name="b-declaring-and-instantiating-a-geometry-instance-with-a-curvepolygon-in-the-same-statement"></a><span data-ttu-id="577e6-153">B.</span><span class="sxs-lookup"><span data-stu-id="577e6-153">B.</span></span> <span data-ttu-id="577e6-154">Dichiarazione e creazione di un'istanza Geometry utilizzando un'istanza CurvePolygon nella stessa istruzione</span><span class="sxs-lookup"><span data-stu-id="577e6-154">Declaring and Instantiating a Geometry Instance with a CurvePolygon in the Same Statement</span></span>  
 <span data-ttu-id="577e6-155">In questo frammento di codice viene illustrato come dichiarare e inizializzare un'istanza geometry con un'istanza `CurvePolygon` nella stessa istruzione:</span><span class="sxs-lookup"><span data-stu-id="577e6-155">This code snippet shows how to declare and initialize a geometry instance with a `CurvePolygon` in the same statement:</span></span>  
  
```sql  
DECLARE @g geometry = 'CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))'  
```  
  
### <a name="c-instantiating-a-geography-instance-with-a-curvepolygon"></a><span data-ttu-id="577e6-156">C.</span><span class="sxs-lookup"><span data-stu-id="577e6-156">C.</span></span> <span data-ttu-id="577e6-157">Creazione di un'istanza Geography con un'istanza CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="577e6-157">Instantiating a Geography Instance with a CurvePolygon</span></span>  
 <span data-ttu-id="577e6-158">Nel frammento di codice seguente viene illustrato come dichiarare e inizializzare un'istanza `geography` con un'istanza `CurvePolygon`:</span><span class="sxs-lookup"><span data-stu-id="577e6-158">This code snippet shows how to declare and initialize a `geography` instance with a `CurvePolygon`:</span></span>  
  
```sql  
DECLARE @g geography = 'CURVEPOLYGON(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';  
```  
  
### <a name="d-storing-a-curvepolygon-with-only-an-exterior-bounding-ring"></a><span data-ttu-id="577e6-159">D.</span><span class="sxs-lookup"><span data-stu-id="577e6-159">D.</span></span> <span data-ttu-id="577e6-160">Archiviazione di un'istanza CurvePolygon con un solo anello di delimitazione esterno</span><span class="sxs-lookup"><span data-stu-id="577e6-160">Storing a CurvePolygon with Only an Exterior Bounding Ring</span></span>  
 <span data-ttu-id="577e6-161">In questo esempio viene illustrato come archiviare un cerchio semplice in un'istanza `CurvePolygon` (per definire il cerchio viene utilizzato solo un anello di delimitazione esterno):</span><span class="sxs-lookup"><span data-stu-id="577e6-161">This example shows how to store a simple circle in a `CurvePolygon` instance (only an exterior bounding ring is used to define the circle):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
### <a name="e-storing-a-curvepolygon-containing-interior-rings"></a><span data-ttu-id="577e6-162">E.</span><span class="sxs-lookup"><span data-stu-id="577e6-162">E.</span></span> <span data-ttu-id="577e6-163">Archiviazione di un'istanza CurvePolygon contenente anelli interni</span><span class="sxs-lookup"><span data-stu-id="577e6-163">Storing a CurvePolygon Containing Interior Rings</span></span>  
 <span data-ttu-id="577e6-164">In questo esempio viene creato un anello in un'istanza `CurvePolygon` (per definire l'anello vengono utilizzati sia un anello di delimitazione esterno che un anello interno):</span><span class="sxs-lookup"><span data-stu-id="577e6-164">This example creates a donut in a `CurvePolygon` instance (both an exterior bounding ring and an interior ring is used to define the donut):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 4, 4 0, 8 4, 4 8, 0 4), CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
 <span data-ttu-id="577e6-165">In questo esempio viene illustrata sia un'istanza `CurvePolygon` valida che un'istanza non valida in caso di utilizzo di anelli interni:</span><span class="sxs-lookup"><span data-stu-id="577e6-165">This example shows both a valid `CurvePolygon` instance and an invalid instance when using interior rings:</span></span>  
  
```sql  
DECLARE @g1 geometry, @g2 geometry;  
SET @g1 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (-2 2, 2 2, 2 -2, -2 -2, -2 2))');  
IF @g1.STIsValid() = 1  
  BEGIN  
     SELECT @g1.STArea();  
  END  
SET @g2 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (0 5, 5 0, 0 -5, -5 0, 0 5))');  
IF @g2.STIsValid() = 1  
  BEGIN  
     SELECT @g2.STArea();  
  END  
SELECT @g1.STIsValid() AS G1, @g2.STIsValid() AS G2;  
```  
  
 <span data-ttu-id="577e6-166">Sia per @g1 che per @g2 viene usato lo stesso anello di delimitazione esterno: un cerchio con un raggio di 5 ed entrambi usano un quadrato per un anello interno.</span><span class="sxs-lookup"><span data-stu-id="577e6-166">Both @g1 and @g2 use the same exterior bounding ring: a circle with a radius of 5 and they both use a square for an interior ring.</span></span>  <span data-ttu-id="577e6-167">Tuttavia, l'istanza @g1 è valida, mentre l'istanza @g2 non lo è.</span><span class="sxs-lookup"><span data-stu-id="577e6-167">However, the instance @g1 is valid, but the instance @g2 is invalid.</span></span>  <span data-ttu-id="577e6-168">@g2 è non valida perché l'anello interno divide lo spazio interno delimitato dall'anello esterno in quattro aree separate.</span><span class="sxs-lookup"><span data-stu-id="577e6-168">The reason that @g2 is invalid is that the interior ring splits the interior space bounded by the exterior ring into four separate regions.</span></span>  <span data-ttu-id="577e6-169">Nel disegno seguente viene illustrata questa condizione:</span><span class="sxs-lookup"><span data-stu-id="577e6-169">The following drawing shows what occurred:</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577e6-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="577e6-170">See Also</span></span>  
 <span data-ttu-id="577e6-171">[Polygon](polygon.md) </span><span class="sxs-lookup"><span data-stu-id="577e6-171">[Polygon](polygon.md) </span></span>  
 <span data-ttu-id="577e6-172">[CircularString](circularstring.md) </span><span class="sxs-lookup"><span data-stu-id="577e6-172">[CircularString](circularstring.md) </span></span>  
 <span data-ttu-id="577e6-173">[CompoundCurve](compoundcurve.md) </span><span class="sxs-lookup"><span data-stu-id="577e6-173">[CompoundCurve](compoundcurve.md) </span></span>  
 <span data-ttu-id="577e6-174">[Guida di riferimento ai metodi per il tipo di dati geometry](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="577e6-174">[geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span></span>  
 <span data-ttu-id="577e6-175">[Guida di riferimento ai metodi per il tipo di dati geography](/sql/t-sql/spatial-geography/spatial-types-geography) </span><span class="sxs-lookup"><span data-stu-id="577e6-175">[geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) </span></span>  
 [<span data-ttu-id="577e6-176">Panoramica dei tipi di dati spaziali</span><span class="sxs-lookup"><span data-stu-id="577e6-176">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
