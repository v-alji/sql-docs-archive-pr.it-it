---
title: CompoundCurve | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae357f9b-e3e2-4cdf-af02-012acda2e466
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 6a899bbe9a17a64083592e1078e8cac93365f02b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624567"
---
# <a name="compoundcurve"></a><span data-ttu-id="f8c74-102">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="f8c74-102">CompoundCurve</span></span>
  <span data-ttu-id="f8c74-103">`CompoundCurve` è una raccolta di zero o più istanze `CircularString` o `LineString` continue di tipo geometry o geography.</span><span class="sxs-lookup"><span data-stu-id="f8c74-103">A `CompoundCurve` is a collection of zero or more continuous `CircularString` or `LineString` instances of either geometry or geography types.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="f8c74-104">Per una descrizione dettagliata ed esempi delle nuove funzionalità spaziali di questa versione, incluso il `CompoundCurve` sottotipo, scaricare il white paper, [nuove funzionalità spaziali in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="f8c74-104">For a detailed description and examples of the new spatial features in this release, including the `CompoundCurve` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

 <span data-ttu-id="f8c74-105">È possibile creare un'istanza `CompoundCurve` vuota, ma affinché `CompoundCurve` sia valida è necessario che vengano rispettati i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8c74-105">An empty `CompoundCurve` instance can be instantiated, but for a `CompoundCurve` to be valid it must meet the following criteria:</span></span>

1.  <span data-ttu-id="f8c74-106">Deve contenere almeno un'istanza `CircularString` o `LineString`.</span><span class="sxs-lookup"><span data-stu-id="f8c74-106">It must contain at least one `CircularString` or `LineString` instance.</span></span>

2.  <span data-ttu-id="f8c74-107">La sequenza di istanze `CircularString` o `LineString` deve essere continua.</span><span class="sxs-lookup"><span data-stu-id="f8c74-107">The sequence of `CircularString` or `LineString` instances must be continuous.</span></span>

 <span data-ttu-id="f8c74-108">Se un oggetto `CompoundCurve` contiene una sequenza di `CircularString` più `LineString` istanze e, l'endpoint finale per ogni istanza, ad eccezione dell'ultima istanza, deve essere l'endpoint iniziale per l'istanza successiva nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="f8c74-108">If a `CompoundCurve` contains a sequence of multiple `CircularString` and `LineString` instances, the ending endpoint for every instance except for the last instance must be the starting endpoint for the next instance in the sequence.</span></span> <span data-ttu-id="f8c74-109">Ciò significa che se il punto finale di un'istanza precedente nella sequenza è (4 3 7 2), il punto iniziale dell'istanza successiva nella sequenza deve essere (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="f8c74-109">This means that if the ending point of a prior instance in the sequence is (4 3 7 2), the starting point for the next instance in the sequence must be (4 3 7 2).</span></span> <span data-ttu-id="f8c74-110">Si noti che i valori Z (elevazione) e M (misura) del punto devono essere anch'essi uguali.</span><span class="sxs-lookup"><span data-stu-id="f8c74-110">Note that Z(elevation) and M(measure) values for the point must also be the same.</span></span> <span data-ttu-id="f8c74-111">Nel caso di una differenza nei due punti, viene generata un'eccezione `System.FormatException` .</span><span class="sxs-lookup"><span data-stu-id="f8c74-111">If there is a difference in the two points, a `System.FormatException` is thrown.</span></span> <span data-ttu-id="f8c74-112">I punti in un'istanza `CircularString` non devono avere un valore Z o M.</span><span class="sxs-lookup"><span data-stu-id="f8c74-112">Points in a `CircularString` do not have to have a Z or M value.</span></span> <span data-ttu-id="f8c74-113">Se non sono presenti valori Z o M per il punto finale dell'istanza precedente, il punto iniziale dell'istanza successiva non potrà includere valori Z o M.</span><span class="sxs-lookup"><span data-stu-id="f8c74-113">If no Z or M values are given for the ending point of the prior instance, the starting point of the next instance cannot include Z or M values.</span></span> <span data-ttu-id="f8c74-114">Se il punto finale della sequenza precedente è (4 3), il punto iniziale della sequenza successiva dovrà essere (4 3). Non potrà essere (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="f8c74-114">If the ending point for the prior sequence is (4 3), the starting point for the next sequence must be (4 3); it cannot be (4 3 7 2).</span></span> <span data-ttu-id="f8c74-115">Tutti i punti in un'istanza `CompoundCurve` non devono avere alcun valore Z oppure devono avere lo stesso valore Z.</span><span class="sxs-lookup"><span data-stu-id="f8c74-115">All points in a `CompoundCurve` instance must have either no Z value or the same Z value.</span></span>

## <a name="compoundcurve-instances"></a><span data-ttu-id="f8c74-116">Istanze CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="f8c74-116">CompoundCurve instances</span></span>
 <span data-ttu-id="f8c74-117">Nell'immagine seguente sono illustrati tipi di `CompoundCurve` validi.</span><span class="sxs-lookup"><span data-stu-id="f8c74-117">The following illustration shows valid `CompoundCurve` types.</span></span>

 ![](../../database-engine/media/f278742e-b861-4555-8b51-3d972b7602bf.png "f278742e-b861-4555-8b51-3d972b7602bf")

### <a name="accepted-instances"></a><span data-ttu-id="f8c74-118">Istanze accettate</span><span class="sxs-lookup"><span data-stu-id="f8c74-118">Accepted instances</span></span>
 <span data-ttu-id="f8c74-119">L'istanza `CompoundCurve` viene accettata se è un'istanza vuota o se soddisfa i criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="f8c74-119">`CompoundCurve` instance is accepted if it is an empty instance or meets the following criteria.</span></span>

1.  <span data-ttu-id="f8c74-120">Tutte le istanze contenute nell'istanza `CompoundCurve` sono istanze di segmenti di arco circolare accettate.</span><span class="sxs-lookup"><span data-stu-id="f8c74-120">All the instances contained by `CompoundCurve` instance are accepted circular arc segment instances.</span></span> <span data-ttu-id="f8c74-121">Per altre informazioni sulle istanze di segmenti di arco circolare accettate, vedere [LineString](linestring.md) e [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="f8c74-121">For more information on accepted circular arc segment instances, see [LineString](linestring.md) and [CircularString](circularstring.md).</span></span>

2.  <span data-ttu-id="f8c74-122">Tutti i segmenti di arco circolare nell'istanza `CompoundCurve` sono connessi.</span><span class="sxs-lookup"><span data-stu-id="f8c74-122">All of the circular arc segments in the `CompoundCurve` instance are connected.</span></span> <span data-ttu-id="f8c74-123">Il primo punto di ogni segmento di arco circolare successivo è uguale all'ultimo punto del segmento di arco circolare precedente.</span><span class="sxs-lookup"><span data-stu-id="f8c74-123">The first point for each succeeding circular arc segment is the same as the last point on the preceding circular arc segment.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f8c74-124">Sono incluse le coordinate Z e M.</span><span class="sxs-lookup"><span data-stu-id="f8c74-124">This includes the Z and M coordinates.</span></span> <span data-ttu-id="f8c74-125">È quindi necessario che tutte e quattro le coordinate X, Y, Z e M siano uguali.</span><span class="sxs-lookup"><span data-stu-id="f8c74-125">So, all four coordinates X, Y, Z, and M must be the same.</span></span>

3.  <span data-ttu-id="f8c74-126">Nessuna delle istanze contenute è un'istanza vuota.</span><span class="sxs-lookup"><span data-stu-id="f8c74-126">None of the contained instances are empty instances.</span></span>

 <span data-ttu-id="f8c74-127">Nell'esempio seguente vengono illustrate le istanze `CompoundCurve` accettate.</span><span class="sxs-lookup"><span data-stu-id="f8c74-127">The following example shows accepted `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
```

 <span data-ttu-id="f8c74-128">Nell'esempio seguente vengono illustrate le istanze `CompoundCurve` non accettate.</span><span class="sxs-lookup"><span data-stu-id="f8c74-128">The following example shows `CompoundCurve` instances that are not accepted.</span></span> <span data-ttu-id="f8c74-129">Queste istanze generano un'eccezione `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="f8c74-129">These instances throw `System.FormatException`.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING EMPTY)';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (1 0, 2 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="f8c74-130">Istanze valide</span><span class="sxs-lookup"><span data-stu-id="f8c74-130">Valid instances</span></span>
 <span data-ttu-id="f8c74-131">Un'istanza `CompoundCurve` è valida se soddisfa i criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="f8c74-131">A `CompoundCurve` instance is valid if it meets the following criteria.</span></span>

1.  <span data-ttu-id="f8c74-132">L'istanza `CompoundCurve` è accettata.</span><span class="sxs-lookup"><span data-stu-id="f8c74-132">The `CompoundCurve` instance is accepted.</span></span>

2.  <span data-ttu-id="f8c74-133">Tutte le istanze di segmenti di arco circolare contenute nell'istanza `CompoundCurve` sono istanze valide.</span><span class="sxs-lookup"><span data-stu-id="f8c74-133">All circular arc segment instances contained by the `CompoundCurve` instance are valid instances.</span></span>

 <span data-ttu-id="f8c74-134">Nell'esempio seguente vengono illustrate le istanze `CompoundCurve` valide.</span><span class="sxs-lookup"><span data-stu-id="f8c74-134">The following example shows valid `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();

```

 <span data-ttu-id="f8c74-135">`@g3` è valida perché l'istanza `CircularString` è valida.</span><span class="sxs-lookup"><span data-stu-id="f8c74-135">`@g3` is valid because the `CircularString` instance is valid.</span></span> <span data-ttu-id="f8c74-136">Per ulteriori informazioni sulla validità dell' `CircularString` istanza, vedere [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="f8c74-136">For more information on the validity of the `CircularString` instance, see [CircularString](circularstring.md).</span></span>

 <span data-ttu-id="f8c74-137">Nell'esempio seguente vengono illustrate le istanze `CompoundCurve` non valide.</span><span class="sxs-lookup"><span data-stu-id="f8c74-137">The following example shows `CompoundCurve` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4, 3 5))';
DECLARE @g2 geometry = 'COMPOUNDCURVE((1 1, 1 1))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 2 3, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="f8c74-138">`@g1` non è valida perché la seconda istanza non è un'istanza LineString valida.</span><span class="sxs-lookup"><span data-stu-id="f8c74-138">`@g1` is not valid because the second instance is not a valid LineString instance.</span></span> <span data-ttu-id="f8c74-139">`@g2` non è valida perché l'istanza `LineString` non è valida.</span><span class="sxs-lookup"><span data-stu-id="f8c74-139">`@g2` is not valid because the `LineString` instance is not valid.</span></span> <span data-ttu-id="f8c74-140">`@g3` non è valida perché l'istanza `CircularString` non è valida.</span><span class="sxs-lookup"><span data-stu-id="f8c74-140">`@g3` is not valid because the `CircularString` instance is not valid.</span></span> <span data-ttu-id="f8c74-141">Per ulteriori informazioni sulle `CircularString` istanze di e valide `LineString` , vedere [CircularString](circularstring.md) e [LineString](linestring.md).</span><span class="sxs-lookup"><span data-stu-id="f8c74-141">For more information on valid `CircularString` and `LineString` instances, see [CircularString](circularstring.md) and [LineString](linestring.md).</span></span>

## <a name="examples"></a><span data-ttu-id="f8c74-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="f8c74-142">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-compooundcurve"></a><span data-ttu-id="f8c74-143">R.</span><span class="sxs-lookup"><span data-stu-id="f8c74-143">A.</span></span> <span data-ttu-id="f8c74-144">Creazione di un'istanza Geometry con un'istanza CompoundCurve vuota</span><span class="sxs-lookup"><span data-stu-id="f8c74-144">Instantiating a geometry instance with an empty CompooundCurve</span></span>
 <span data-ttu-id="f8c74-145">Nell'esempio seguente viene illustrato come creare un'istanza `CompoundCurve` vuota:</span><span class="sxs-lookup"><span data-stu-id="f8c74-145">The following example shows how to create an empty `CompoundCurve` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE EMPTY');
```

### <a name="b-declaring-and-instantiating-a-geometry-instance-using-a-compoundcurve-in-the-same-statement"></a><span data-ttu-id="f8c74-146">B.</span><span class="sxs-lookup"><span data-stu-id="f8c74-146">B.</span></span> <span data-ttu-id="f8c74-147">Dichiarazione e creazione di un'istanza Geometry utilizzando un'istanza CompoundCurve nella stessa istruzione</span><span class="sxs-lookup"><span data-stu-id="f8c74-147">Declaring and instantiating a geometry instance using a CompoundCurve in the same statement</span></span>
 <span data-ttu-id="f8c74-148">L'esempio seguente illustra come dichiarare e inizializzare un'istanza `geometry` con un'istanza `CompoundCurve`nella stessa istruzione:</span><span class="sxs-lookup"><span data-stu-id="f8c74-148">The following example shows how to declare and initialize a `geometry` instance with a `CompoundCurve`in the same statement:</span></span>

```sql
DECLARE @g geometry = 'COMPOUNDCURVE ((2 2, 0 0),CIRCULARSTRING (0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0))';
```

### <a name="c-instantiating-a-geography-instance-with-a-compoundcurve"></a><span data-ttu-id="f8c74-149">C.</span><span class="sxs-lookup"><span data-stu-id="f8c74-149">C.</span></span> <span data-ttu-id="f8c74-150">Creazione di un'istanza Geography con un'istanza CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="f8c74-150">Instantiating a geography instance with a CompoundCurve</span></span>
 <span data-ttu-id="f8c74-151">Nell'esempio seguente viene illustrato come dichiarare e inizializzare un'istanza `geography` con un'istanza `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="f8c74-151">The following example shows how to declare and initialize a `geography` instance with a `CompoundCurve`:</span></span>

```sql
DECLARE @g geography = 'COMPOUNDCURVE(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';
```

### <a name="d-storing-a-square-in-a-compoundcurve-instance"></a><span data-ttu-id="f8c74-152">D.</span><span class="sxs-lookup"><span data-stu-id="f8c74-152">D.</span></span> <span data-ttu-id="f8c74-153">Archiviazione di un quadrato in un'istanza CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="f8c74-153">Storing a square in a CompoundCurve instance</span></span>
 <span data-ttu-id="f8c74-154">Nell'esempio seguente vengono utilizzate due diverse modalità per archiviare un quadrato tramite un'istanza `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="f8c74-154">The following example uses two different ways to use a `CompoundCurve` instance to store a square.</span></span>

```sql
DECLARE @g1 geometry, @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3), (1 3, 3 3),(3 3, 3 1), (3 1, 1 1))');
SET @g2 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3, 3 3, 3 1, 1 1))');
SELECT @g1.STLength(), @g2.STLength();
```

 <span data-ttu-id="f8c74-155">Le lunghezze per `@g1` e `@g2` sono le stesse.</span><span class="sxs-lookup"><span data-stu-id="f8c74-155">The lengths for both `@g1` and `@g2` are the same.</span></span> <span data-ttu-id="f8c74-156">Come illustrato nell'esempio, un'istanza `CompoundCurve` consente di archiviare una o più istanze di `LineString`.</span><span class="sxs-lookup"><span data-stu-id="f8c74-156">Notice from the example that a `CompoundCurve` instance can store one or more instances of `LineString`.</span></span>

### <a name="e-instantiating-a-geometry-instance-using-a-compoundcurve-with-multiple-circularstrings"></a><span data-ttu-id="f8c74-157">E.</span><span class="sxs-lookup"><span data-stu-id="f8c74-157">E.</span></span> <span data-ttu-id="f8c74-158">Creazione di un'istanza Geometry utilizzando un'istanza CompoundCurve con più istanze CircularString</span><span class="sxs-lookup"><span data-stu-id="f8c74-158">Instantiating a geometry instance using a CompoundCurve with multiple CircularStrings</span></span>
 <span data-ttu-id="f8c74-159">Nell'esempio seguente viene illustrato come utilizzare due diverse istanze `CircularString` per creare un'istanza `CompoundCurve`:</span><span class="sxs-lookup"><span data-stu-id="f8c74-159">The following example shows how to use two different `CircularString` instances to initialize a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT @g.STLength();
```

 <span data-ttu-id="f8c74-160">Viene generato l'output seguente: 12,566370... che è l'equivalente di 4&#x03c0; (4 \* pi).</span><span class="sxs-lookup"><span data-stu-id="f8c74-160">This produces the following output: 12.566370... which is the equivalent of 4&#x03c0; (4 \* pi).</span></span> <span data-ttu-id="f8c74-161">L'istanza `CompoundCurve` riportata nell'esempio consente di archiviare un cerchio con un raggio di 2.</span><span class="sxs-lookup"><span data-stu-id="f8c74-161">The `CompoundCurve` instance in the example stores a circle with a radius of 2.</span></span> <span data-ttu-id="f8c74-162">In entrambi gli esempi di codice precedenti non è stato necessario utilizzare un'istanza `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="f8c74-162">Both of the previous code examples did not have to use a `CompoundCurve`.</span></span> <span data-ttu-id="f8c74-163">Per il primo esempio sarebbe stata più semplice un'istanza `LineString` , mentre per il secondo esempio sarebbe stata più semplice un'istanza `CircularString` .</span><span class="sxs-lookup"><span data-stu-id="f8c74-163">For the first example a `LineString` instance would have been simpler, and a `CircularString` instance would have been simpler for the second example.</span></span> <span data-ttu-id="f8c74-164">Nell'esempio successivo viene tuttavia illustrato in quale punto un'istanza `CompoundCurve` costituisce una migliore alternativa.</span><span class="sxs-lookup"><span data-stu-id="f8c74-164">However, the next example shows where a `CompoundCurve` provides a better alternative.</span></span>

### <a name="f-using-a-compoundcurve-to-store-a-semicircle"></a><span data-ttu-id="f8c74-165">F.</span><span class="sxs-lookup"><span data-stu-id="f8c74-165">F.</span></span> <span data-ttu-id="f8c74-166">Utilizzo di un'istanza CompoundCurve per archiviare un semicerchio</span><span class="sxs-lookup"><span data-stu-id="f8c74-166">Using a CompoundCurve to store a semicircle</span></span>
 <span data-ttu-id="f8c74-167">Nell'esempio seguente viene utilizzata un'istanza `CompoundCurve` per archiviare un semicerchio.</span><span class="sxs-lookup"><span data-stu-id="f8c74-167">The following example uses a `CompoundCurve` instance to store a semicircle.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 0 2))');
SELECT @g.STLength();
```

### <a name="g-storing-multiple-circularstring-and-linestring-instances-in-a-compoundcurve"></a><span data-ttu-id="f8c74-168">G.</span><span class="sxs-lookup"><span data-stu-id="f8c74-168">G.</span></span> <span data-ttu-id="f8c74-169">Archiviazione di più istanze CircularString e LineString in un'istanza CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="f8c74-169">Storing multiple CircularString and LineString instances in a CompoundCurve</span></span>
 <span data-ttu-id="f8c74-170">Nell'esempio seguente viene illustrato come è possibile archiviare più istanze `CircularString` e `LineString` tramite un'istanza `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="f8c74-170">The following example shows how multiple `CircularString` and `LineString` instances can be stored by using a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('COMPOUNDCURVE((3 5, 3 3), CIRCULARSTRING(3 3, 5 1, 7 3), (7 3, 7 5), CIRCULARSTRING(7 5, 5 7, 3 5))');
SELECT @g.STLength();
```

### <a name="h-storing-instances-with-z-and-m-values"></a><span data-ttu-id="f8c74-171">H.</span><span class="sxs-lookup"><span data-stu-id="f8c74-171">H.</span></span> <span data-ttu-id="f8c74-172">Archiviazione di istanze con valori Z e M</span><span class="sxs-lookup"><span data-stu-id="f8c74-172">Storing instances with Z and M values</span></span>
 <span data-ttu-id="f8c74-173">Nell'esempio seguente viene illustrato come utilizzare un'istanza `CompoundCurve` per archiviare una sequenza di istanze `CircularString` e `LineString` con valori Z e M.</span><span class="sxs-lookup"><span data-stu-id="f8c74-173">The following example shows how to use a `CompoundCurve` instance to store a sequence of `CircularString` and `LineString` instances with both Z and M values.</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(7 5 4 2, 5 7 4 2, 3 5 4 2), (3 5 4 2, 8 7 4 2))');
```

### <a name="i-illustrating-why-circularstring-instances-must-be-explicitly-declared"></a><span data-ttu-id="f8c74-174">I.</span><span class="sxs-lookup"><span data-stu-id="f8c74-174">I.</span></span> <span data-ttu-id="f8c74-175">Descrizione del motivo per cui le istanze CircularString devono essere dichiarate in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="f8c74-175">Illustrating why CircularString instances must be explicitly declared</span></span>
 <span data-ttu-id="f8c74-176">Nell'esempio seguente viene illustrato il motivo per cui è necessario dichiarare in modo esplicito le istanze `CircularString` .</span><span class="sxs-lookup"><span data-stu-id="f8c74-176">The following example shows why `CircularString` instances must be explicitly declared.</span></span> <span data-ttu-id="f8c74-177">Il programmatore sta tentando di archiviare un cerchio in un'istanza `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="f8c74-177">The programmer is trying to store a circle in a `CompoundCurve` instance.</span></span>

```sql
DECLARE @g1 geometry;  
DECLARE @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 2 4, 0 2))');
SELECT 'Circle One', @g1.STLength() AS Perimeter;  -- gives an inaccurate amount
SET @g2 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT 'Circle Two', @g2.STLength() AS Perimeter;  -- now we get an accurate amount
```

 <span data-ttu-id="f8c74-178">L'output è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f8c74-178">The output is as follows:</span></span>

```
Circle One11.940039...
Circle Two12.566370...
```

 <span data-ttu-id="f8c74-179">Il perimetro per Circle Two è approssimativamente 4&#x03c0; (4 \* pi), che corrisponde al valore effettivo del perimetro.</span><span class="sxs-lookup"><span data-stu-id="f8c74-179">The perimeter for Circle Two is approximately 4&#x03c0; (4 \* pi), which is the actual value for the perimeter.</span></span> <span data-ttu-id="f8c74-180">Il perimetro per Circle One, tuttavia, è significativamente impreciso.</span><span class="sxs-lookup"><span data-stu-id="f8c74-180">However, the perimeter for Circle One is significantly inaccurate.</span></span> <span data-ttu-id="f8c74-181">L'istanza `CompoundCurve` di Circle One consente l'archiviazione di un segmento di arco circolare (ABC) e di due segmenti di linea (CD, DA).</span><span class="sxs-lookup"><span data-stu-id="f8c74-181">Circle One's `CompoundCurve` instance stores one circular arc segment (ABC) and two line segments (CD, DA).</span></span> <span data-ttu-id="f8c74-182">Tramite l'istanza `CompoundCurve` devono essere archiviati due segmenti di arco circolare (ABC, CDA) per definire un cerchio.</span><span class="sxs-lookup"><span data-stu-id="f8c74-182">The `CompoundCurve` instance has to store two circular arc segments (ABC, CDA) to define a circle.</span></span> <span data-ttu-id="f8c74-183">Tramite un'istanza `LineString` viene definito il secondo set di punti (4 2, 2 4, 0 2) nell'istanza `CompoundCurve` di Circle One.</span><span class="sxs-lookup"><span data-stu-id="f8c74-183">A `LineString` instance defines the second set of points (4 2, 2 4, 0 2) in Circle One's `CompoundCurve` instance.</span></span> <span data-ttu-id="f8c74-184">È necessario dichiarare in modo esplicito un'istanza `CircularString` in un'istanza `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="f8c74-184">You have to explicitly declare a `CircularString` instance inside a `CompoundCurve`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8c74-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8c74-185">See Also</span></span>
 <span data-ttu-id="f8c74-186">Tipo di dati [STIsValid &#40;geometry&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndPoint &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [punto](point.md) di [Panoramica dei tipi di dati spaziali](spatial-data-types-overview.md) [CircularString](circularstring.md) [LineString](linestring.md)</span><span class="sxs-lookup"><span data-stu-id="f8c74-186">[STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [Spatial Data Types Overview](spatial-data-types-overview.md) [Point](point.md)</span></span>


