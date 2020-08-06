---
title: CircularString | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 9fe06b03-d98c-4337-9f89-54da98f49f9f
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c701cdc2e8538a5b91093e17714fd9f6508d1c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624569"
---
# <a name="circularstring"></a><span data-ttu-id="0a1bc-102">CircularString</span><span class="sxs-lookup"><span data-stu-id="0a1bc-102">CircularString</span></span>
  <span data-ttu-id="0a1bc-103">`CircularString` è una raccolta di zero o più segmenti di arco circolare continui.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-103">A `CircularString` is a collection of zero or more continuous circular arc segments.</span></span> <span data-ttu-id="0a1bc-104">Un segmento di arco circolare è un segmento curvo definito da tre punti su un piano bidimensionale. Il primo punto non può corrispondere al terzo punto.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-104">A circular arc segment is a curved segment defined by three points in a two-dimensional plane; the first point cannot be the same as the third point.</span></span> <span data-ttu-id="0a1bc-105">Se tutti e tre i punti di un segmento di arco circolare sono collineari, il segmento di arco verrà gestito come un segmento di linea.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-105">If all three points of a circular arc segment are collinear, the arc segment is treated as a line segment.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="0a1bc-106">Per una descrizione dettagliata ed esempi delle nuove funzionalità spaziali introdotte in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , incluso il `CircularString` sottotipo, scaricare il white paper, [nuove funzionalità spaziali in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="0a1bc-106">For a detailed description and examples of the new spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CircularString` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

## <a name="circularstring-instances"></a><span data-ttu-id="0a1bc-107">Istanze CircularString</span><span class="sxs-lookup"><span data-stu-id="0a1bc-107">CircularString instances</span></span>
 <span data-ttu-id="0a1bc-108">Nel disegno seguente vengono illustrate le istanze `CircularString` valide:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-108">The drawing below shows valid `CircularString` instances:</span></span>

 ![](../../database-engine/media/5ff17e34-b578-4873-9d33-79500940d0bc.png "5ff17e34-b578-4873-9d33-79500940d0bc")

### <a name="accepted-instances"></a><span data-ttu-id="0a1bc-109">Istanze accettate</span><span class="sxs-lookup"><span data-stu-id="0a1bc-109">Accepted instances</span></span>
 <span data-ttu-id="0a1bc-110">Un' `CircularString` istanza viene accettata se è vuota o contiene un numero dispari di punti, n, dove n > 1.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-110">A `CircularString` instance is accepted if it is either empty or contains an odd number of points, n, where n > 1.</span></span> <span data-ttu-id="0a1bc-111">Le istanze `CircularString` seguenti vengono accettate.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-111">The following `CircularString` instances are accepted.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 2 0, 1 1)';
```

 <span data-ttu-id="0a1bc-112">In `@g3` viene illustrato che l'istanza `CircularString` può essere accettata, ma non è valida.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-112">`@g3` shows that `CircularString` instance may be accepted, but not valid.</span></span> <span data-ttu-id="0a1bc-113">La dichiarazione dell'istanza CircularString seguente non viene accettata.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-113">The following CircularString instance declaration is not accepted.</span></span> <span data-ttu-id="0a1bc-114">Questa dichiarazione genera un'eccezione `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-114">This declaration throws a `System.FormatException`.</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="0a1bc-115">Istanze valide</span><span class="sxs-lookup"><span data-stu-id="0a1bc-115">Valid instances</span></span>
 <span data-ttu-id="0a1bc-116">Un'istanza `CircularString` valida deve essere vuota o disporre degli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-116">A valid `CircularString` instance must be empty or have the following attributes:</span></span>

-   <span data-ttu-id="0a1bc-117">Deve contenere almeno un segmento di arco circolare, cioè avere un minimo di tre punti.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-117">It must contain at least one circular arc segment (that is, have a minimum of three points).</span></span>

-   <span data-ttu-id="0a1bc-118">L'ultimo endpoint per ogni segmento di arco circolare nella sequenza, a eccezione dell'ultimo segmento, deve essere il primo endpoint per il segmento successivo nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-118">The last endpoint for each circular arc segment in the sequence, except for the last segment, must be the first endpoint for the next segment in the sequence.</span></span>

-   <span data-ttu-id="0a1bc-119">Deve contenere un numero di punti dispari.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-119">It must have an odd number of points.</span></span>

-   <span data-ttu-id="0a1bc-120">Non deve sovrapporsi a un intervallo.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-120">It cannot overlap itself over an interval.</span></span>

-   <span data-ttu-id="0a1bc-121">Anche se è possibile che le istanze `CircularString` contengano segmenti di linea, questi ultimi devono essere definiti da tre punti collineari.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-121">Although `CircularString` instances may contain line segments, these line segments must be defined by three collinear points.</span></span>

 <span data-ttu-id="0a1bc-122">Nell'esempio seguente vengono illustrate le istanze `CircularString` valide.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-122">The following example shows valid `CircularString` instances.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1, 0 1)';
DECLARE @g4 geometry = 'CIRCULARSTRING(1 1, 2 2, 2 2)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(),@g4.STIsValid();
```

 <span data-ttu-id="0a1bc-123">Un'istanza `CircularString` deve contenere almeno due segmenti di arco circolare per definire un cerchio completo.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-123">A `CircularString` instance must contain at least two circular arc segments to define a complete circle.</span></span> <span data-ttu-id="0a1bc-124">In un'istanza `CircularString` non può essere utilizzato un singolo segmento di arco circolare, ad esempio (1 1, 3 1, 1 1), per definire un cerchio completo.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-124">A `CircularString` instance cannot use a single circular arc segment (such as (1 1, 3 1, 1 1)) to define a complete circle.</span></span> <span data-ttu-id="0a1bc-125">Utilizzare (1 1, 2 2, 3 1, 2 0, 1 1) per definire il cerchio.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-125">Use (1 1, 2 2, 3 1, 2 0, 1 1) to define the circle.</span></span>

 <span data-ttu-id="0a1bc-126">Nell'esempio seguente vengono illustrate le istanze CircularString non valide.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-126">The following example shows CircularString instances that are not valid.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING(1 1, 2 0, 1 1)';
DECLARE @g2 geometry = 'CIRCULARSTRING(0 0, 0 0, 0 0)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

### <a name="instances-with-collinear-points"></a><span data-ttu-id="0a1bc-127">Istanze con punti collineari</span><span class="sxs-lookup"><span data-stu-id="0a1bc-127">Instances with collinear points</span></span>
 <span data-ttu-id="0a1bc-128">Nei casi seguenti un segmento di arco circolare sarà considerato come un segmento di linea:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-128">In the following cases a circular arc segment will be treated as a line segment:</span></span>

-   <span data-ttu-id="0a1bc-129">Quando tutti e i tre punti sono collineari, ad esempio, (1 3, 4 4, 7 5).</span><span class="sxs-lookup"><span data-stu-id="0a1bc-129">When all three points are collinear (for example, (1 3, 4 4, 7 5)).</span></span>

-   <span data-ttu-id="0a1bc-130">Quando il primo punto e il punto medio sono gli stessi, ma il terzo punto è diverso, ad esempio, (1 3, 1 3, 7 5).</span><span class="sxs-lookup"><span data-stu-id="0a1bc-130">When the first and middle point are the same, but the third point is different (for example, (1 3, 1 3, 7 5)).</span></span>

-   <span data-ttu-id="0a1bc-131">Quando il punto medio e l'ultimo punto sono gli stessi, ma il primo punto è diverso, ad esempio, (1 3, 4 4, 4 4).</span><span class="sxs-lookup"><span data-stu-id="0a1bc-131">When the middle and last point are the same, but the first point is different (for example, (1 3, 4 4, 4 4)).</span></span>

## <a name="examples"></a><span data-ttu-id="0a1bc-132">Esempi</span><span class="sxs-lookup"><span data-stu-id="0a1bc-132">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-circularstring"></a><span data-ttu-id="0a1bc-133">R.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-133">A.</span></span> <span data-ttu-id="0a1bc-134">Creazione di un'istanza Geometry con un'istanza CircularString vuota</span><span class="sxs-lookup"><span data-stu-id="0a1bc-134">Instantiating a Geometry Instance with an Empty CircularString</span></span>
 <span data-ttu-id="0a1bc-135">In questo esempio viene illustrato come creare un'istanza `CircularString` vuota:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-135">This example shows how to create an empty `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING EMPTY');
```

### <a name="b-instantiating-a-geometry-instance-using-a-circularstring-with-one-circular-arc-segment"></a><span data-ttu-id="0a1bc-136">B.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-136">B.</span></span> <span data-ttu-id="0a1bc-137">Creazione di un'istanza Geometry utilizzando un'istanza CircularString con un segmento di arco circolare</span><span class="sxs-lookup"><span data-stu-id="0a1bc-137">Instantiating a Geometry Instance Using a CircularString with One Circular Arc Segment</span></span>
 <span data-ttu-id="0a1bc-138">Nell'esempio seguente viene illustrato come creare un'istanza `CircularString` con un solo segmento di arco circolare (mezzo cerchio):</span><span class="sxs-lookup"><span data-stu-id="0a1bc-138">The following example shows how to create a `CircularString` instance with a single circular arc segment (half-circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry:: STGeomFromText('CIRCULARSTRING(2 0, 1 1, 0 0)', 0);
SELECT @g.ToString();
```

### <a name="c-instantiating-a-geometry-instance-using-a-circularstring-with-multiple-circular-arc-segments"></a><span data-ttu-id="0a1bc-139">C.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-139">C.</span></span> <span data-ttu-id="0a1bc-140">Creazione di un'istanza Geometry utilizzando un'istanza CircularString con più segmenti di arco circolare</span><span class="sxs-lookup"><span data-stu-id="0a1bc-140">Instantiating a Geometry Instance Using a CircularString with Multiple Circular Arc Segments</span></span>
 <span data-ttu-id="0a1bc-141">Nell'esempio seguente viene illustrato come creare un'istanza `CircularString` con più di un segmento di arco circolare (cerchio completo):</span><span class="sxs-lookup"><span data-stu-id="0a1bc-141">The following example shows how to create a `CircularString` instance with more than one circular arc segment (full circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING(2 1, 1 2, 0 1, 1 0, 2 1)');
SELECT 'Circumference = ' + CAST(@g.STLength() AS NVARCHAR(10));  
```

 <span data-ttu-id="0a1bc-142">Viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-142">This produces the following output:</span></span>

```
Circumference = 6.28319
```

 <span data-ttu-id="0a1bc-143">Confrontare l'output quando viene utilizzata `LineString` anziché `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-143">Compare the output when `LineString` is used instead of `CircularString`:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(2 1, 1 2, 0 1, 1 0, 2 1)', 0);
SELECT 'Perimeter = ' + CAST(@g.STLength() AS NVARCHAR(10));
```

 <span data-ttu-id="0a1bc-144">Viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-144">This produces the following output:</span></span>

```
Perimeter = 5.65685
```

 <span data-ttu-id="0a1bc-145">Si noti che il valore per l' `CircularString` esempio è vicino a 2&#x03c0; (2 \* pi), che corrisponde alla circonferenza effettiva del cerchio.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-145">Notice that the value for the `CircularString` example is close to 2&#x03c0; (2 \* pi), which is the actual circumference of the circle.</span></span>

### <a name="d-declaring-and-instantiating-a-geometry-instance-with-a-circularstring-in-the-same-statement"></a><span data-ttu-id="0a1bc-146">D.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-146">D.</span></span> <span data-ttu-id="0a1bc-147">Dichiarazione e creazione di un'istanza Geometry utilizzando un'istanza CircularString nella stessa istruzione</span><span class="sxs-lookup"><span data-stu-id="0a1bc-147">Declaring and Instantiating a Geometry Instance with a CircularString in the Same Statement</span></span>
 <span data-ttu-id="0a1bc-148">In questo frammento viene illustrato come dichiarare e creare un'istanza `geometry` con un'istanza `CircularString` nella stessa istruzione:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-148">This snippet shows how to declare and instantiate a `geometry` instance with a `CircularString` in the same statement:</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)';
```

### <a name="e-instantiating-a-geography-instance-with-a-circularstring"></a><span data-ttu-id="0a1bc-149">E.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-149">E.</span></span> <span data-ttu-id="0a1bc-150">Creazione di un'istanza Geometry con un'istanza CircularString</span><span class="sxs-lookup"><span data-stu-id="0a1bc-150">Instantiating a Geography Instance with a CircularString</span></span>
 <span data-ttu-id="0a1bc-151">Nell'esempio seguente viene illustrato come dichiarare e creare un'istanza `geography` con un'istanza `CircularString`:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-151">The following example shows how to declare and instantiate a `geography` instance with a `CircularString`:</span></span>

```sql
DECLARE @g geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';
```

### <a name="f-instantiating-a-geometry-instance-with-a-circularstring-that-is-a-straight-line"></a><span data-ttu-id="0a1bc-152">F.</span><span class="sxs-lookup"><span data-stu-id="0a1bc-152">F.</span></span> <span data-ttu-id="0a1bc-153">Creazione di un'istanza Geometry con un'istanza CircularString che corrisponde a una linea retta</span><span class="sxs-lookup"><span data-stu-id="0a1bc-153">Instantiating a Geometry Instance with a CircularString that is a Straight Line</span></span>
 <span data-ttu-id="0a1bc-154">Nell'esempio seguente viene illustrato come creare un'istanza `CircularString` che corrisponde a una linea retta:</span><span class="sxs-lookup"><span data-stu-id="0a1bc-154">The following example shows how to create a `CircularString` instance that is a straight line:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('CIRCULARSTRING(0 0, 1 2, 2 4)', 0);
```

## <a name="see-also"></a><span data-ttu-id="0a1bc-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a1bc-155">See Also</span></span>
 <span data-ttu-id="0a1bc-156">[Cenni preliminari sui tipi di dati spaziali](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;geography data type&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;Geometry Data Type&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;geometry data type](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)&#41;STIsValid &#40;[geography data type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) STLength &#40;Geometry [Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) Data Type&#41;STEndPoint &#40;Geometry Data Type [&#41;STPointN](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [&#40;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) Geometry Data Type&#41;STNumPoints &#40;Geometry Data Type [&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) Geometry Data Type&#41;[STIsClosed &#40;Geometry](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) data [Type&#41;](linestring.md) [STPointOnSurface &#40;Geometry](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)</span><span class="sxs-lookup"><span data-stu-id="0a1bc-156">[Spatial Data Types Overview](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span></span>


