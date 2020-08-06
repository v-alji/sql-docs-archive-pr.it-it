---
title: Creare, costruire ed eseguire query di istanze di geometria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- planar spatial data [SQL Server], getting started
- geometry data type [SQL Server], getting started
ms.assetid: c6b5c852-37d2-48d0-a8ad-e43bb80d6514
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 539f3f8bb1d9a1c277d6317cc571cf8bcb281833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624563"
---
# <a name="create-construct-and-query-geometry-instances"></a><span data-ttu-id="9860f-102">Creazione, costruzione e query di istanze geometry</span><span class="sxs-lookup"><span data-stu-id="9860f-102">Create, Construct, and Query geometry Instances</span></span>
  <span data-ttu-id="9860f-103">Il tipo di dati spaziali planare, `geometry`, rappresenta i dati in un sistema di coordinate euclideo (piano).</span><span class="sxs-lookup"><span data-stu-id="9860f-103">The planar spatial data type, `geometry`, represents data in a Euclidean (flat) coordinate system.</span></span> <span data-ttu-id="9860f-104">Questo tipo è implementato come tipo di dati CLR (Common Language Runtime) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9860f-104">This type is implemented as a common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9860f-105">Il tipo `geometry` è predefinito e disponibile in ogni database.</span><span class="sxs-lookup"><span data-stu-id="9860f-105">The `geometry` type is predefined and available in each database.</span></span> <span data-ttu-id="9860f-106">È possibile creare colonne di tabella di tipo `geometry` e operare sui dati `geometry` nello stesso modo in cui si utilizzano gli altri tipi CLR.</span><span class="sxs-lookup"><span data-stu-id="9860f-106">You can create table columns of type `geometry` and operate on `geometry` data in the same manner as you would use other CLR types.</span></span>  
  
 <span data-ttu-id="9860f-107">Il tipo di dati `geometry` (planare) supportato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è conforme allo standard Open Geospatial Consortium (OGC) Simple Features for SQL Specification versione 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="9860f-107">The `geometry` data type (planar) supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0.</span></span>  
  
 <span data-ttu-id="9860f-108">Per ulteriori informazioni sulle specifiche OGC, vedere quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9860f-108">For more information on OGC specifications, see the following:</span></span>  
  
-   [<span data-ttu-id="9860f-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span><span class="sxs-lookup"><span data-stu-id="9860f-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)  
  
-   <span data-ttu-id="9860f-110">[OGC Specifications, Simple Feature Access Part 2 - SQL Options](https://go.microsoft.com/fwlink/?LinkId=93629) (Specifiche OGC, accesso semplificato alle caratteristiche Parte 2 - Opzioni SQL)</span><span class="sxs-lookup"><span data-stu-id="9860f-110">[OGC Specifications, Simple Feature Access Part 2 - SQL Options](https://go.microsoft.com/fwlink/?LinkId=93629)</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9860f-111">supporta un subset dello standard GML 3.1 esistente che viene definito nello schema seguente: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span><span class="sxs-lookup"><span data-stu-id="9860f-111">supports a subset of the existing GML 3.1 standard which is defined in the following schema: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span></span>  
  
##  <a name="creating-or-constructing-a-new-geometry-instance"></a><a name="creating"></a> <span data-ttu-id="9860f-112">Creazione o costruzione di una nuova istanza geometry</span><span class="sxs-lookup"><span data-stu-id="9860f-112">Creating or constructing a new geometry instance</span></span>  
  
###  <a name="creating-a-new-geometry-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="9860f-113">Creazione di una nuova istanza geometry da un'istanza esistente</span><span class="sxs-lookup"><span data-stu-id="9860f-113">Creating a New geometry Instance from an Existing Instance</span></span>  
 <span data-ttu-id="9860f-114">Il tipo di dati `geometry` offre molti metodi predefiniti che è possibile utilizzare per creare nuove istanze `geometry` in base a quelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="9860f-114">The `geometry` data type provides numerous built-in methods you can use to create new `geometry` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="9860f-115">**Per creare un buffer relativo a una geometria**</span><span class="sxs-lookup"><span data-stu-id="9860f-115">**To create a buffer around a geometry**</span></span>  
 [<span data-ttu-id="9860f-116">STBuffer &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-116">STBuffer &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stbuffer-geometry-data-type)  
  
 [<span data-ttu-id="9860f-117">BufferWithTolerance &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-117">BufferWithTolerance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/bufferwithtolerance-geometry-data-type)  
  
 <span data-ttu-id="9860f-118">**Per creare una versione semplificata di una geometria**</span><span class="sxs-lookup"><span data-stu-id="9860f-118">**To create a simplified version of a geometry**</span></span>  
 [<span data-ttu-id="9860f-119">Reduce &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-119">Reduce &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/reduce-geometry-data-type)  
  
 <span data-ttu-id="9860f-120">**Per creare la struttura convessa di una geometria**</span><span class="sxs-lookup"><span data-stu-id="9860f-120">**To create the convex hull of a geometry**</span></span>  
 [<span data-ttu-id="9860f-121">STConvexHull &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-121">STConvexHull &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stconvexhull-geometry-data-type)  
  
 <span data-ttu-id="9860f-122">**Per creare una geometria dall'intersezione di due geometrie**</span><span class="sxs-lookup"><span data-stu-id="9860f-122">**To create a geometry from the intersection of two geometries**</span></span>  
 [<span data-ttu-id="9860f-123">STIntersection &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-123">STIntersection &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersection-geometry-data-type)  
  
 <span data-ttu-id="9860f-124">**Per creare una geometria dall'unione di due geometrie**</span><span class="sxs-lookup"><span data-stu-id="9860f-124">**To create a geometry from the union of two geometries**</span></span>  
 [<span data-ttu-id="9860f-125">STUnion &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-125">STUnion &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stunion-geometry-data-type)  
  
 <span data-ttu-id="9860f-126">**Per creare una geometria dai punti in cui una non si sovrappone all'altra**</span><span class="sxs-lookup"><span data-stu-id="9860f-126">**To create a geometry from the points where one geometry does not overlap another**</span></span>  
 [<span data-ttu-id="9860f-127">STDifference &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-127">STDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdifference-geometry-data-type)  
  
 <span data-ttu-id="9860f-128">**Per creare una geometria dai punti in cui due geometrie non si sovrappongono**</span><span class="sxs-lookup"><span data-stu-id="9860f-128">**To create a geometry from the points where two geometries do not overlap**</span></span>  
 [<span data-ttu-id="9860f-129">STSymDifference &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-129">STSymDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stsymdifference-geometry-data-type)  
  
 <span data-ttu-id="9860f-130">**Per creare un'istanza Point arbitraria che giace su una geometria esistente**</span><span class="sxs-lookup"><span data-stu-id="9860f-130">**To create an arbitrary Point instance that lies on an existing geometry**</span></span>  
 [<span data-ttu-id="9860f-131">STPointOnSurface &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-131">STPointOnSurface &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="9860f-132">Costruzione di un'istanza geometry da un input WKT (well-known text)</span><span class="sxs-lookup"><span data-stu-id="9860f-132">Constructing a geometry Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="9860f-133">Il tipo di dati `geometry` fornisce molti metodi predefiniti che generano una geometria dalla rappresentazione WKT OGC (Open Geospatial Consortium).</span><span class="sxs-lookup"><span data-stu-id="9860f-133">The `geometry` data type provides several built-in methods that generate a geometry from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="9860f-134">Lo standard WKT è una stringa di testo che consente lo scambio di dati geometrici in formato testuale.</span><span class="sxs-lookup"><span data-stu-id="9860f-134">The WKT standard is a text string that allows geometry data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="9860f-135">**Per costruire qualsiasi tipo di istanza geometry da input WKT**</span><span class="sxs-lookup"><span data-stu-id="9860f-135">**To construct any type of geometry instance from WKT input**</span></span>  
 [<span data-ttu-id="9860f-136">STGeomFromText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-136">STGeomFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type)  
  
 [<span data-ttu-id="9860f-137">Parse &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-137">Parse &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/parse-geometry-data-type)  
  
 <span data-ttu-id="9860f-138">**Per costruire un'istanza di geometria Point dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="9860f-138">**To construct a geometry Point instance from WKT input**</span></span>  
 [<span data-ttu-id="9860f-139">STPointFromText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-139">STPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="9860f-140">**Per costruire un'istanza MultiPoint di tipo geometry da un input WKT**</span><span class="sxs-lookup"><span data-stu-id="9860f-140">**To construct a geometry MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="9860f-141">STMPointFromText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-141">STMPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="9860f-142">**Per costruire un'istanza LineString di tipo geometry da un input WKT**</span><span class="sxs-lookup"><span data-stu-id="9860f-142">**To construct a geometry LineString instance from WKT input**</span></span>  
 [<span data-ttu-id="9860f-143">STLineFromText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-143">STLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="9860f-144">**Per costruire un'istanza MultiLineString di tipo geometry da un input WKT**</span><span class="sxs-lookup"><span data-stu-id="9860f-144">**To construct a geometry MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="9860f-145">STMLineFromText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-145">STMLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="9860f-146">**Per costruire un'istanza Polygon di tipo geometry da un input WKT**</span><span class="sxs-lookup"><span data-stu-id="9860f-146">**To construct a geometry Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="9860f-147">STPolyFromText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-147">STPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="9860f-148">**Per costruire un'istanza MultiPolygon di tipo geometry da un input WKT**</span><span class="sxs-lookup"><span data-stu-id="9860f-148">**To construct a geometry MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="9860f-149">STMPolyFromText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-149">STMPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="9860f-150">**Per costruire un'istanza GeometryCollection di tipo geometry da un input WKT**</span><span class="sxs-lookup"><span data-stu-id="9860f-150">**To construct a geometry GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="9860f-151">STGeomCollFromText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-151">STGeomCollFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromtext-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="9860f-152">Costruzione di un'istanza geometry da un input WKB (well-known binary)</span><span class="sxs-lookup"><span data-stu-id="9860f-152">Constructing a geometry Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="9860f-153">WKB è un formato binario definito da OGC (Open Geospatial Consortium) che consente di scambiare i dati `geometry` tra un'applicazione client e un database SQL.</span><span class="sxs-lookup"><span data-stu-id="9860f-153">WKB is a binary format specified by the Open Geospatial Consortium (OGC) that permits `geometry` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="9860f-154">Le funzioni seguenti accettano input WKB per costruire le geometrie:</span><span class="sxs-lookup"><span data-stu-id="9860f-154">The following functions accept WKB input to construct geometries:</span></span>  
  
 <span data-ttu-id="9860f-155">**Per costruire qualsiasi tipo di istanza geometry da un input WKB**</span><span class="sxs-lookup"><span data-stu-id="9860f-155">**To construct any type of geometry instance from WKB input**</span></span>  
 [<span data-ttu-id="9860f-156">STGeomFromWKB &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-156">STGeomFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromwkb-geometry-data-type)  
  
 <span data-ttu-id="9860f-157">**Per costruire un'istanza Point di tipo geometry da un input WKB**</span><span class="sxs-lookup"><span data-stu-id="9860f-157">**To construct a geometry Point instance from WKB input**</span></span>  
 [<span data-ttu-id="9860f-158">STPointFromWKB &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-158">STPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="9860f-159">**Per costruire un'istanza MultiPoint di tipo geometry da un input WKB**</span><span class="sxs-lookup"><span data-stu-id="9860f-159">**To construct a geometry MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="9860f-160">STMPointFromWKB &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-160">STMPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="9860f-161">**Per costruire un'istanza LineString di tipo geometry da un input WKB**</span><span class="sxs-lookup"><span data-stu-id="9860f-161">**To construct a geometry LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="9860f-162">STLineFromWKB &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-162">STLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="9860f-163">**Per costruire un'istanza MultiLineString di tipo geometry da un input WKB**</span><span class="sxs-lookup"><span data-stu-id="9860f-163">**To construct a geometry MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="9860f-164">STMLineFromWKB &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-164">STMLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="9860f-165">**Per costruire un'istanza Polygon di tipo geometry da un input WKB**</span><span class="sxs-lookup"><span data-stu-id="9860f-165">**To construct a geometry Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="9860f-166">STPolyFromWKB &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-166">STPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="9860f-167">**Per costruire un'istanza MultiPolygon di tipo geometry da un input WKB**</span><span class="sxs-lookup"><span data-stu-id="9860f-167">**To construct a geometry MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="9860f-168">STMPolyFromWKB &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-168">STMPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="9860f-169">**Per costruire un'istanza GeometryCollection di tipo geometry da un input WKB**</span><span class="sxs-lookup"><span data-stu-id="9860f-169">**To construct a geometry GeometryCollection instance from WKB input**</span></span>  
 [<span data-ttu-id="9860f-170">STGeomCollFromWKB &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-170">STGeomCollFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromwkb-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="9860f-171">Costruzione di un'istanza geometry da un input di testo GML</span><span class="sxs-lookup"><span data-stu-id="9860f-171">Constructing a geometry Instance from GML Text Input</span></span>  
 <span data-ttu-id="9860f-172">Il `geometry` tipo di dati fornisce un metodo che genera un' `geometry` istanza da GML, una rappresentazione XML di oggetti geometrici.</span><span class="sxs-lookup"><span data-stu-id="9860f-172">The `geometry` data type provides a method that generates a `geometry` instance from GML, an XML representation of geometric objects.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9860f-173">supporta un subset di GML.</span><span class="sxs-lookup"><span data-stu-id="9860f-173">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="9860f-174">**Per costruire qualsiasi tipo di istanza geometry da un input GML**</span><span class="sxs-lookup"><span data-stu-id="9860f-174">**To construct any type of geometry instance from GML input**</span></span>  
 [<span data-ttu-id="9860f-175">GeomFromGml &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-175">GeomFromGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/geomfromgml-geometry-data-type)  
  
  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geometry-instance"></a><a name="returning"></a> <span data-ttu-id="9860f-176">Restituzione di WKT e WKB da un'istanza geometry</span><span class="sxs-lookup"><span data-stu-id="9860f-176">Returning Well-Known Text and Well-Known Binary from a geometry Instance</span></span>  
 <span data-ttu-id="9860f-177">È possibile utilizzare i metodi seguenti per restituire il formato WKT o WKB di un'istanza `geometry`:</span><span class="sxs-lookup"><span data-stu-id="9860f-177">You can use the following methods to return either the WKT or WKB format of a `geometry` instance:</span></span>  
  
 <span data-ttu-id="9860f-178">**Per restituire la rappresentazione WKT di un'istanza geometry**</span><span class="sxs-lookup"><span data-stu-id="9860f-178">**To return the WKT representation of a geometry instance**</span></span>  
 [<span data-ttu-id="9860f-179">STAsText &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-179">STAsText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stastext-geometry-data-type)  
  
 [<span data-ttu-id="9860f-180">ToString &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-180">ToString &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/tostring-geometry-data-type)  
  
 <span data-ttu-id="9860f-181">**Per restituire la rappresentazione WKT di un'istanza geometry, con qualsiasi valore Z e M.**</span><span class="sxs-lookup"><span data-stu-id="9860f-181">**To return the WKT representation of a geometry instance including any Z and M values**</span></span>  
 [<span data-ttu-id="9860f-182">AsTextZM &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-182">AsTextZM &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/astextzm-geometry-data-type)  
  
 <span data-ttu-id="9860f-183">**Per restituire la rappresentazione WKB di un'istanza geometry**</span><span class="sxs-lookup"><span data-stu-id="9860f-183">**To return the WKB representation of a geometry instance**</span></span>  
 [<span data-ttu-id="9860f-184">STAsBinary &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-184">STAsBinary &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stasbinary-geometry-data-type)  
  
 <span data-ttu-id="9860f-185">**Per restituire la rappresentazione GML di un'istanza geometry**</span><span class="sxs-lookup"><span data-stu-id="9860f-185">**To return a GML representation of a geometry instance**</span></span>  
 [<span data-ttu-id="9860f-186">AsGml &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-186">AsGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/asgml-geometry-data-type)  
  
  
  
##  <a name="querying-the-properties-and-behaviors-of-geometry-instances"></a><a name="querying"></a> <span data-ttu-id="9860f-187">Esecuzione di query sulle proprietà e i comportamenti delle istanze geometry</span><span class="sxs-lookup"><span data-stu-id="9860f-187">Querying the Properties and Behaviors of geometry Instances</span></span>  
 <span data-ttu-id="9860f-188">Tutte le `geometry` istanze hanno un certo numero di proprietà che possono essere recuperate tramite metodi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibili in.</span><span class="sxs-lookup"><span data-stu-id="9860f-188">All `geometry` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="9860f-189">Negli argomenti seguenti vengono definiti le proprietà e i comportamenti dei tipi di geometria, nonché i metodi per l'esecuzione di query per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="9860f-189">The following topics define the properties and behaviors of geometry types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="9860f-190">Informazioni sulla validità, sul tipo di istanza e su GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="9860f-190">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="9860f-191">Dopo aver costruito un'istanza `geometry`, è possibile utilizzare i metodi seguenti per determinare se essa è corretta, per restituire il tipo di istanza o, se si tratta di un'istanza di raccolta, per restituire un'istanza `geometry` specifica.</span><span class="sxs-lookup"><span data-stu-id="9860f-191">Once a `geometry` instance is constructed, you can use the following methods to determine if it is well-formed, return the instance type, or, if it is a collection instance, return a specific `geometry` instance.</span></span>  
  
 <span data-ttu-id="9860f-192">**Per restituire il tipo di istanza di una geometria**</span><span class="sxs-lookup"><span data-stu-id="9860f-192">**To return the instance type of a geometry**</span></span>  
 [<span data-ttu-id="9860f-193">STGeometryType &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-193">STGeometryType &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeometrytype-geometry-data-type)  
  
 <span data-ttu-id="9860f-194">**Per determinare se una geometria è un tipo di istanza specificato**</span><span class="sxs-lookup"><span data-stu-id="9860f-194">**To determine if a geometry is a given instance type**</span></span>  
 [<span data-ttu-id="9860f-195">InstanceOf &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-195">InstanceOf &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/instanceof-geometry-data-type)  
  
 <span data-ttu-id="9860f-196">**Per determinare se un'istanza geometry è corretta per il tipo di istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-196">**To determine if a geometry instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="9860f-197">STIsValid &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-197">STIsValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)  
  
 <span data-ttu-id="9860f-198">**Per convertire un'istanza geometry in un'istanza geometry corretta con un tipo di istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-198">**To convert a geometry instance to a well-formed geometry instance with an instance type**</span></span>  
 [<span data-ttu-id="9860f-199">MakeValid &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-199">MakeValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type)  
  
 <span data-ttu-id="9860f-200">**Per restituire il numero delle geometrie in un'istanza GeometryCollection**</span><span class="sxs-lookup"><span data-stu-id="9860f-200">**To return the number of geometries in a geometry collection instance**</span></span>  
 [<span data-ttu-id="9860f-201">STNumGeometries &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-201">STNumGeometries &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumgeometries-geometry-data-type)  
  
 <span data-ttu-id="9860f-202">Per restituire una specifica geometria in un'istanza GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="9860f-202">To return a specific geometry in a geometry collection instance</span></span>  
 <span data-ttu-id="9860f-203">[STGeometryN &#40;tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (tipo di dati geometry)</span><span class="sxs-lookup"><span data-stu-id="9860f-203">[STGeometryN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (geometry Data type)</span></span>  
  
  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="9860f-204">Numero di punti</span><span class="sxs-lookup"><span data-stu-id="9860f-204">Number of Points</span></span>  
 <span data-ttu-id="9860f-205">Tutte le istanze non vuote `geometry` sono costituite da *punti*.</span><span class="sxs-lookup"><span data-stu-id="9860f-205">All nonempty `geometry` instances are comprised of *points*.</span></span> <span data-ttu-id="9860f-206">Tali punti rappresentano le coordinate X e Y del piano su cui vengono tracciate le geometrie.</span><span class="sxs-lookup"><span data-stu-id="9860f-206">These points represent the X- and Y-coordinates of the plane on which the geometries are drawn.</span></span> <span data-ttu-id="9860f-207">Il tipo di dati `geometry` offre numerosi metodi predefiniti per l'esecuzione di query sui punti di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9860f-207">`geometry` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="9860f-208">**Per restituire il numero di punti che comprendono un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-208">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="9860f-209">STNumPoints &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-209">STNumPoints &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type)  
  
 <span data-ttu-id="9860f-210">**Per restituire un punto specifico in un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-210">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="9860f-211">STPointN</span><span class="sxs-lookup"><span data-stu-id="9860f-211">STPointN</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="9860f-212">**Per restituire un punto arbitrario che si trova in un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-212">**To return an arbitrary point that lies on an instance**</span></span>  
 [<span data-ttu-id="9860f-213">STPointOnSurface</span><span class="sxs-lookup"><span data-stu-id="9860f-213">STPointOnSurface</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
 <span data-ttu-id="9860f-214">**Per restituire il punto di inizio di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-214">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="9860f-215">STStartPoint</span><span class="sxs-lookup"><span data-stu-id="9860f-215">STStartPoint</span></span>](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type)  
  
 <span data-ttu-id="9860f-216">**Per restituire il punto di fine di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-216">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="9860f-217">STEndpoint</span><span class="sxs-lookup"><span data-stu-id="9860f-217">STEndpoint</span></span>](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type)  
  
 <span data-ttu-id="9860f-218">**Per restituire la coordinata X di un'istanza Point**</span><span class="sxs-lookup"><span data-stu-id="9860f-218">**To return the X-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="9860f-219">STX &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-219">STX &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stx-geometry-data-type)  
  
 <span data-ttu-id="9860f-220">**Per restituire la coordinata Y di un'istanza Point**</span><span class="sxs-lookup"><span data-stu-id="9860f-220">**To return the Y-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="9860f-221">STY</span><span class="sxs-lookup"><span data-stu-id="9860f-221">STY</span></span>](/sql/t-sql/spatial-geometry/sty-geometry-data-type)  
  
 <span data-ttu-id="9860f-222">**Per restituire il punto centrale geometrico di un'istanza Polygon, CurvePolygon o MultiPolygon**</span><span class="sxs-lookup"><span data-stu-id="9860f-222">**To return the geometric center point of a Polygon, CurvePolygon, or MultiPolygon instance**</span></span>  
 [<span data-ttu-id="9860f-223">STCentroid</span><span class="sxs-lookup"><span data-stu-id="9860f-223">STCentroid</span></span>](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type)  
  
  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="9860f-224">Dimensione</span><span class="sxs-lookup"><span data-stu-id="9860f-224">Dimension</span></span>  
 <span data-ttu-id="9860f-225">Un'istanza `geometry` non vuota può essere a 0, 1 o 2 dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9860f-225">A nonempty `geometry` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="9860f-226">Le istanze `geometries` senza dimensioni, ad esempio `Point` e `MultiPoint` non dispongono di lunghezza o area.</span><span class="sxs-lookup"><span data-stu-id="9860f-226">Zero-dimensional `geometries`, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="9860f-227">Gli oggetti unidimensionali, ad esempio `LineString, CircularString, CompoundCurve` e `MultiLineString`, dispongono della lunghezza.</span><span class="sxs-lookup"><span data-stu-id="9860f-227">One-dimensional objects, such as `LineString, CircularString, CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="9860f-228">Le istanze bidimensionali, ad esempio `Polygon`, `CurvePolygon` e `MultiPolygon`, dispongono di area e lunghezza.</span><span class="sxs-lookup"><span data-stu-id="9860f-228">Two-dimensional instances, such as `Polygon`, `CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="9860f-229">Per le istanze vuote verrà indicata una dimensione di -1 e per `GeometryCollection` verrà indicata un'area dipendente dai tipi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="9860f-229">Empty instances will report a dimension of -1, and a `GeometryCollection` will report an area dependent on the types of its contents.</span></span>  
  
 <span data-ttu-id="9860f-230">**Per restituire la dimensione di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-230">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="9860f-231">STDimension</span><span class="sxs-lookup"><span data-stu-id="9860f-231">STDimension</span></span>](/sql/t-sql/spatial-geometry/stdimension-geometry-data-type)  
  
 <span data-ttu-id="9860f-232">**Per restituire la lunghezza di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-232">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="9860f-233">STLength</span><span class="sxs-lookup"><span data-stu-id="9860f-233">STLength</span></span>](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)  
  
 <span data-ttu-id="9860f-234">**Per restituire l'area di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-234">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="9860f-235">STArea</span><span class="sxs-lookup"><span data-stu-id="9860f-235">STArea</span></span>](/sql/t-sql/spatial-geometry/starea-geometry-data-type)  
  
  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="9860f-236">Vuoto</span><span class="sxs-lookup"><span data-stu-id="9860f-236">Empty</span></span>  
 <span data-ttu-id="9860f-237">Un'istanza *vuota* non `geometry` contiene punti.</span><span class="sxs-lookup"><span data-stu-id="9860f-237">An *empty*`geometry` instance does not have any points.</span></span> <span data-ttu-id="9860f-238">La lunghezza delle istanze `LineString, CircularString`, `CompoundCurve` e `MultiLineString` vuote è pari a zero.</span><span class="sxs-lookup"><span data-stu-id="9860f-238">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is zero.</span></span> <span data-ttu-id="9860f-239">L'area delle istanze `Polygon`, `CurvePolygon` e `MultiPolygon` vuote è pari a 0.</span><span class="sxs-lookup"><span data-stu-id="9860f-239">The area of empty `Polygon`, `CurvePolygon`, and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="9860f-240">**Per determinare se un'istanza è vuota**</span><span class="sxs-lookup"><span data-stu-id="9860f-240">**To determine if an instance is empty**</span></span>  
 <span data-ttu-id="9860f-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="9860f-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span></span>  
  
  
  
###  <a name="simple"></a><a name="simple"></a> <span data-ttu-id="9860f-242">Simple</span><span class="sxs-lookup"><span data-stu-id="9860f-242">Simple</span></span>  
 <span data-ttu-id="9860f-243">Affinché un `geometry` dell'istanza sia *semplice*, deve soddisfare entrambi questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="9860f-243">For a `geometry` of the instance to be *simple*, it must meet both of these requirements:</span></span>  
  
-   <span data-ttu-id="9860f-244">Ogni figura dell'istanza non deve intersecarsi, salvo agli endpoint.</span><span class="sxs-lookup"><span data-stu-id="9860f-244">Each figure of the instance must not intersect itself, except at its endpoints.</span></span>  
  
-   <span data-ttu-id="9860f-245">Le figure dell'istanza non possono intersecarsi tra di loro in un punto non esistente in entrambi i loro limiti.</span><span class="sxs-lookup"><span data-stu-id="9860f-245">No two figures of the instance can intersect each other at a point that is not in both of their boundaries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9860f-246">Le geometrie vuote sono sempre semplici.</span><span class="sxs-lookup"><span data-stu-id="9860f-246">Empty geometries are always simple.</span></span>  
  
 <span data-ttu-id="9860f-247">**Per determinare se un'istanza è semplice**</span><span class="sxs-lookup"><span data-stu-id="9860f-247">**To determine if an instance is simple**</span></span>  
 <span data-ttu-id="9860f-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="9860f-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span></span>  
  
  
  
###  <a name="boundary-interior-and-exterior"></a><a name="boundary"></a> <span data-ttu-id="9860f-249">Limite interno ed esterno</span><span class="sxs-lookup"><span data-stu-id="9860f-249">Boundary, Interior, and Exterior</span></span>  
 <span data-ttu-id="9860f-250">L' *interno* di un' `geometry` istanza è lo spazio occupato dall'istanza e l' *esterno* è lo spazio non occupato.</span><span class="sxs-lookup"><span data-stu-id="9860f-250">The *interior* of a `geometry` instance is the space occupied by the instance, and the *exterior* is the space not occupied it.</span></span>  
  
 <span data-ttu-id="9860f-251">Il*limite* è definito da OGC come segue:</span><span class="sxs-lookup"><span data-stu-id="9860f-251">*Boundary* is defined by the OGC as follows:</span></span>  
  
-   <span data-ttu-id="9860f-252">Le istanze `Point` e `MultiPoint` non hanno un limite.</span><span class="sxs-lookup"><span data-stu-id="9860f-252">`Point` and `MultiPoint` instances do not have a boundary.</span></span>  
  
-   <span data-ttu-id="9860f-253">I limiti `LineString` e `MultiLineString` sono formati dai punti di inizio e di fine, rimuovendo quelli che si hanno per un numero di volte pari.</span><span class="sxs-lookup"><span data-stu-id="9860f-253">`LineString` and `MultiLineString` boundaries are formed by the start points and end points, removing those that occur an even number of times.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 1, 0 0, 1 0, 0 1), (1 1, 1 0))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="9860f-254">Il limite di un'istanza `Polygon` o `MultiPolygon` è il set dei suoi anelli.</span><span class="sxs-lookup"><span data-stu-id="9860f-254">The boundary of a `Polygon` or `MultiPolygon` instance is the set of its rings.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0), (1 1, 1 2, 2 2, 2 1, 1 1))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="9860f-255">**Per restituire il limite di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-255">**To return the boundary of an instance**</span></span>  
 [<span data-ttu-id="9860f-256">STBoundary</span><span class="sxs-lookup"><span data-stu-id="9860f-256">STBoundary</span></span>](/sql/t-sql/spatial-geometry/stboundary-geometry-data-type)  
  
  
  
###  <a name="envelope"></a><a name="envelope"></a> <span data-ttu-id="9860f-257">Envelope</span><span class="sxs-lookup"><span data-stu-id="9860f-257">Envelope</span></span>  
 <span data-ttu-id="9860f-258">La *busta* di un' `geometry` istanza, nota anche come *riquadro delimitatore*, è il rettangolo allineato all'asse formato dalle coordinate minime e massime (X, Y) dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="9860f-258">The *envelope* of a `geometry` instance, also known as the *bounding box*, is the axis-aligned rectangle formed by the minimum and maximum (X,Y) coordinates of the instance.</span></span>  
  
 <span data-ttu-id="9860f-259">**Per restituire l'envelope di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-259">**To return the envelope of an instance**</span></span>  
 [<span data-ttu-id="9860f-260">STEnvelope</span><span class="sxs-lookup"><span data-stu-id="9860f-260">STEnvelope</span></span>](/sql/t-sql/spatial-geometry/stenvelope-geometry-data-type)  
  
  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="9860f-261">Chiusura</span><span class="sxs-lookup"><span data-stu-id="9860f-261">Closure</span></span>  
 <span data-ttu-id="9860f-262">Un'istanza *chiusa* `geometry` è una figura i cui punti di inizio e di fine sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="9860f-262">A *closed*`geometry` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="9860f-263">Le istanze `Polygon` sono considerate chiuse.</span><span class="sxs-lookup"><span data-stu-id="9860f-263">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="9860f-264">Le istanze `Point` non sono considerate chiuse.</span><span class="sxs-lookup"><span data-stu-id="9860f-264">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="9860f-265">Un anello è un'istanza `LineString` semplice chiusa.</span><span class="sxs-lookup"><span data-stu-id="9860f-265">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="9860f-266">**Per determinare se un'istanza è chiusa**</span><span class="sxs-lookup"><span data-stu-id="9860f-266">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="9860f-267">STIsClosed</span><span class="sxs-lookup"><span data-stu-id="9860f-267">STIsClosed</span></span>](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)  
  
 <span data-ttu-id="9860f-268">**Per determinare se un'istanza è un anello**</span><span class="sxs-lookup"><span data-stu-id="9860f-268">**To determine if an instance is a ring**</span></span>  
 [<span data-ttu-id="9860f-269">STIsRing</span><span class="sxs-lookup"><span data-stu-id="9860f-269">STIsRing</span></span>](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)  
  
 <span data-ttu-id="9860f-270">**Per restituire l'anello esterno di un'istanza Polygon**</span><span class="sxs-lookup"><span data-stu-id="9860f-270">**To return the exterior ring of a Polygon instance**</span></span>  
 [<span data-ttu-id="9860f-271">STExteriorRing</span><span class="sxs-lookup"><span data-stu-id="9860f-271">STExteriorRing</span></span>](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type)  
  
 <span data-ttu-id="9860f-272">**Per restituire il numero di anelli interni in un'istanza Polygon**</span><span class="sxs-lookup"><span data-stu-id="9860f-272">**To return the number of interior rings in a Polygon**</span></span>  
 [<span data-ttu-id="9860f-273">STNumInteriorRing</span><span class="sxs-lookup"><span data-stu-id="9860f-273">STNumInteriorRing</span></span>](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type)  
  
 <span data-ttu-id="9860f-274">**Per restituire un anello interno specificato di un'istanza Polygon**</span><span class="sxs-lookup"><span data-stu-id="9860f-274">**To return a specified interior ring of a Polygon**</span></span>  
 [<span data-ttu-id="9860f-275">STInteriorRingN</span><span class="sxs-lookup"><span data-stu-id="9860f-275">STInteriorRingN</span></span>](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type)  
  
  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="9860f-276">Identificatore SRID</span><span class="sxs-lookup"><span data-stu-id="9860f-276">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="9860f-277">L'identificatore SRID specifica in quale sistema di coordinate è rappresentata l'istanza `geometry`.</span><span class="sxs-lookup"><span data-stu-id="9860f-277">The spatial reference ID (SRID) is an identifier specifying which coordinate system the `geometry` instance is represented in.</span></span> <span data-ttu-id="9860f-278">Due istanze con identificatori SRID diversi non possono essere confrontate.</span><span class="sxs-lookup"><span data-stu-id="9860f-278">Two instances with different SRIDs are incomparable.</span></span>  
  
 <span data-ttu-id="9860f-279">**Per impostare o restituire l'identificatore SRID di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="9860f-279">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="9860f-280">STSrid</span><span class="sxs-lookup"><span data-stu-id="9860f-280">STSrid</span></span>](/sql/t-sql/spatial-geometry/stsrid-geometry-data-type)  
  
 <span data-ttu-id="9860f-281">Questa proprietà può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="9860f-281">This property can be modified.</span></span>  
  
  
  
##  <a name="determining-relationships-between-geometry-instances"></a><a name="rel"></a> <span data-ttu-id="9860f-282">Determinazione delle relazioni esistenti tra istanze geometry</span><span class="sxs-lookup"><span data-stu-id="9860f-282">Determining Relationships between geometry Instances</span></span>  
 <span data-ttu-id="9860f-283">Il tipo di dati `geometry` offre molti metodi predefiniti che è possibile utilizzare per determinare relazioni tra due istanze `geometry`.</span><span class="sxs-lookup"><span data-stu-id="9860f-283">The `geometry` data type provides many built-in methods you can use to determine relationships between two `geometry` instances.</span></span>  
  
 <span data-ttu-id="9860f-284">**Per determinare se due istanze includono lo stesso punto impostato**</span><span class="sxs-lookup"><span data-stu-id="9860f-284">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="9860f-285">STEquals</span><span class="sxs-lookup"><span data-stu-id="9860f-285">STEquals</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="9860f-286">**Per determinare se due istanze sono disgiunte**</span><span class="sxs-lookup"><span data-stu-id="9860f-286">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="9860f-287">STDisjoint</span><span class="sxs-lookup"><span data-stu-id="9860f-287">STDisjoint</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="9860f-288">**Per determinare se due istanze si intersecano**</span><span class="sxs-lookup"><span data-stu-id="9860f-288">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="9860f-289">STIntersects</span><span class="sxs-lookup"><span data-stu-id="9860f-289">STIntersects</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="9860f-290">**Per determinare se due istanze entrano in contatto**</span><span class="sxs-lookup"><span data-stu-id="9860f-290">**To determine if two instances touch**</span></span>  
 [<span data-ttu-id="9860f-291">STTouches</span><span class="sxs-lookup"><span data-stu-id="9860f-291">STTouches</span></span>](/sql/t-sql/spatial-geometry/sttouches-geometry-data-type)  
  
 <span data-ttu-id="9860f-292">**Per determinare se due istanze si sovrappongono**</span><span class="sxs-lookup"><span data-stu-id="9860f-292">**To determine if two instances overlap**</span></span>  
 [<span data-ttu-id="9860f-293">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="9860f-293">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="9860f-294">**Per determinare se due istanze si incrociano**</span><span class="sxs-lookup"><span data-stu-id="9860f-294">**To determine if two instances cross**</span></span>  
 [<span data-ttu-id="9860f-295">STCrosses</span><span class="sxs-lookup"><span data-stu-id="9860f-295">STCrosses</span></span>](/sql/t-sql/spatial-geometry/stcrosses-geometry-data-type)  
  
 <span data-ttu-id="9860f-296">**Per determinare se un'istanza è all'interno dell'altra**</span><span class="sxs-lookup"><span data-stu-id="9860f-296">**To determine if one instance is within another**</span></span>  
 [<span data-ttu-id="9860f-297">STWithin</span><span class="sxs-lookup"><span data-stu-id="9860f-297">STWithin</span></span>](/sql/t-sql/spatial-geometry/stwithin-geometry-data-type)  
  
 <span data-ttu-id="9860f-298">**Per determinare se un'istanza contiene l'altra**</span><span class="sxs-lookup"><span data-stu-id="9860f-298">**To determine if one instance contains another**</span></span>  
 [<span data-ttu-id="9860f-299">STContains</span><span class="sxs-lookup"><span data-stu-id="9860f-299">STContains</span></span>](/sql/t-sql/spatial-geometry/stcontains-geometry-data-type)  
  
 <span data-ttu-id="9860f-300">**Per determinare se un'istanza si sovrappone all'altra**</span><span class="sxs-lookup"><span data-stu-id="9860f-300">**To determine if one instance overlaps another**</span></span>  
 [<span data-ttu-id="9860f-301">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="9860f-301">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="9860f-302">**Per determinare se due istanze sono collegate a livello spaziale**</span><span class="sxs-lookup"><span data-stu-id="9860f-302">**To determine if two instances are spatially related**</span></span>  
 [<span data-ttu-id="9860f-303">STRelate</span><span class="sxs-lookup"><span data-stu-id="9860f-303">STRelate</span></span>](/sql/t-sql/spatial-geometry/strelate-geometry-data-type)  
  
 <span data-ttu-id="9860f-304">**Per determinare la distanza più breve tra punti in due geometrie**</span><span class="sxs-lookup"><span data-stu-id="9860f-304">**To determine the shortest distance between points in two geometries**</span></span>  
 [<span data-ttu-id="9860f-305">STDistance</span><span class="sxs-lookup"><span data-stu-id="9860f-305">STDistance</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
  
  
##  <a name="geometry-instances-default-to-zero-srid"></a><a name="defaultsrid"></a> <span data-ttu-id="9860f-306">Istanze geometry con SRID zero per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="9860f-306">geometry Instances Default to Zero SRID</span></span>  
 <span data-ttu-id="9860f-307">L'identificatore SRID predefinito per le istanze `geometry` in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è 0.</span><span class="sxs-lookup"><span data-stu-id="9860f-307">The default SRID for `geometry` instances in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 0.</span></span> <span data-ttu-id="9860f-308">Con i dati spaziali `geometry` lo specifico identificatore SRID dell'istanza spaziale non deve eseguire i calcoli. Di conseguenza le istanze possono risiedere nello spazio planare indefinito.</span><span class="sxs-lookup"><span data-stu-id="9860f-308">With `geometry` spatial data, the specific SRID of the spatial instance is not required to perform calculations; thus, instances can reside in undefined planar space.</span></span> <span data-ttu-id="9860f-309">Per indicare lo spazio planare indefinito nei calcoli di metodi del tipo di dati `geometry`, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilizza SRID 0.</span><span class="sxs-lookup"><span data-stu-id="9860f-309">To indicate undefined planar space in the calculations of `geometry` data type methods, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses SRID 0.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="9860f-310">Esempi</span><span class="sxs-lookup"><span data-stu-id="9860f-310">Examples</span></span>  
 <span data-ttu-id="9860f-311">Nei due esempi seguenti viene illustrato come aggiungere ed eseguire query su dati di tipo geometry.</span><span class="sxs-lookup"><span data-stu-id="9860f-311">The following two examples show how to add and query geometry data.</span></span>  
  
-   <span data-ttu-id="9860f-312">Nel primo esempio viene creata una tabella con una colonna di identità e una colonna `geometry``GeomCol1`.</span><span class="sxs-lookup"><span data-stu-id="9860f-312">The first example creates a table with an identity column and a `geometry` column `GeomCol1`.</span></span> <span data-ttu-id="9860f-313">Una terza colonna effettua il rendering della colonna `geometry` nella rappresentazione Well-Known Text (WKT) OGC (Open Geospatial Consortium) e utilizza il metodo `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="9860f-313">A third column renders the `geometry` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="9860f-314">Vengono quindi inserite due righe: in una riga è contenuta un'istanza `LineString` di `geometry`e in una seconda è contenuta un'istanza `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="9860f-314">Two rows are then inserted: one row contains a `LineString` instance of `geometry`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeomCol1 geometry,   
        GeomCol2 AS GeomCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('LINESTRING (100 100, 20 180, 180 180)', 0));  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('POLYGON ((0 0, 150 0, 150 150, 0 150, 0 0))', 0));  
    GO  
    ```  
  
-   <span data-ttu-id="9860f-315">Nel secondo esempio viene utilizzato il metodo `STIntersection()` per restituire i punti in cui si intersecano le due istanze `geometry` inserite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9860f-315">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geometry` instances intersect.</span></span>  
  
    ```  
    DECLARE @geom1 geometry;  
    DECLARE @geom2 geometry;  
    DECLARE @result geometry;  
  
    SELECT @geom1 = GeomCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geom2 = GeomCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geom1.STIntersection(@geom2);  
    SELECT @result.STAsText();  
    ```  
  
  
  
## <a name="see-also"></a><span data-ttu-id="9860f-316">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9860f-316">See Also</span></span>  
 [<span data-ttu-id="9860f-317">Dati spaziali &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9860f-317">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
