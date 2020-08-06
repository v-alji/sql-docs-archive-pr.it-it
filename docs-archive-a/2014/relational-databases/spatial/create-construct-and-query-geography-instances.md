---
title: Creare, costruire ed eseguire query di istanze geografiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server]
- geodetic data type [SQL Server]
- geography data type [SQL Server], about geography data type
ms.assetid: b585851e-d15b-411f-adeb-aeabeb777c0b
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: d744457cc517a6172cca96b27eae1f456deca24e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624565"
---
# <a name="create-construct-and-query-geography-instances"></a><span data-ttu-id="f29bc-102">Creare, Costruire e Istanze geografiche di Query</span><span class="sxs-lookup"><span data-stu-id="f29bc-102">Create, Construct, and Query geography Instances</span></span>
  <span data-ttu-id="f29bc-103">Il tipo di dati spaziali geografici, `geography`, rappresenta i dati in un sistema di coordinate terrestri.</span><span class="sxs-lookup"><span data-stu-id="f29bc-103">The geography spatial data type, `geography`, represents data in a round-earth coordinate system.</span></span> <span data-ttu-id="f29bc-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]è implementato come tipo di dati CLR (Common Language Runtime) .NET.</span><span class="sxs-lookup"><span data-stu-id="f29bc-104">This type is implemented as a .NET common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f29bc-105">Il tipo di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` consente di archiviare dati ellissoidali (terra rotonda), ad esempio coordinate di latitudine e longitudine GPS.</span><span class="sxs-lookup"><span data-stu-id="f29bc-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` data type stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>  
  
 <span data-ttu-id="f29bc-106">Il tipo `geography` è predefinito e disponibile in ogni database.</span><span class="sxs-lookup"><span data-stu-id="f29bc-106">The `geography` type is predefined and available in each database.</span></span> <span data-ttu-id="f29bc-107">È possibile creare colonne di tabella di tipo `geography` e utilizzare dati `geography` nello stesso modo in cui verrebbero utilizzati gli altri tipi forniti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="f29bc-107">You can create table columns of type `geography` and operate on `geography` data in the same manner as you would use other system-supplied types.</span></span>  
  
##  <a name="creating-or-constructing-a-new-geography-instance"></a><a name="creating"></a> <span data-ttu-id="f29bc-108">Creazione o costruzione di una nuova istanza geografica</span><span class="sxs-lookup"><span data-stu-id="f29bc-108">Creating or constructing a new geography instance</span></span>  
  
###  <a name="creating-a-new-geography-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="f29bc-109">Creazione di una nuova istanza geografica da un'istanza esistente</span><span class="sxs-lookup"><span data-stu-id="f29bc-109">Creating a New geography Instance from an Existing Instance</span></span>  
 <span data-ttu-id="f29bc-110">Il tipo di dati `geography` offre molti metodi predefiniti che è possibile utilizzare per creare nuove istanze `geography` in base a quelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="f29bc-110">The `geography` data type provides numerous built-in methods you can use to create new `geography` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="f29bc-111">**Per creare un buffer relativo a una geografia**</span><span class="sxs-lookup"><span data-stu-id="f29bc-111">**To create a buffer around a geography**</span></span>  
 [<span data-ttu-id="f29bc-112">STBuffer &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-112">STBuffer &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stbuffer-geography-data-type)  
  
 <span data-ttu-id="f29bc-113">**Per creare un buffer relativo a una geografia, consentendo una certa tolleranza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-113">**To create a buffer around a geography, allowing for a tolerance**</span></span>  
 [<span data-ttu-id="f29bc-114">BufferWithTolerance &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-114">BufferWithTolerance &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/bufferwithtolerance-geography-data-type)  
  
 <span data-ttu-id="f29bc-115">**Per creare una geografia dall'intersezione di due istanze di geografia**</span><span class="sxs-lookup"><span data-stu-id="f29bc-115">**To create a geography from the intersection of two geography instances**</span></span>  
 [<span data-ttu-id="f29bc-116">STIntersection &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-116">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="f29bc-117">**Per creare una geografia dall'unione di due istanze di geografia**</span><span class="sxs-lookup"><span data-stu-id="f29bc-117">**To create a geography from the union of two geography instances**</span></span>  
 [<span data-ttu-id="f29bc-118">STUnion &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-118">STUnion &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stunion-geography-data-type)  
  
 <span data-ttu-id="f29bc-119">**Per creare una geografia partendo dai punti in cui una non si sovrappone all'altra**</span><span class="sxs-lookup"><span data-stu-id="f29bc-119">**To create a geography from the points where one geography does not overlap another**</span></span>  
 [<span data-ttu-id="f29bc-120">STDifference &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-120">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="f29bc-121">Costruzione di un'istanza geografica dall'input WKT (well-known text)</span><span class="sxs-lookup"><span data-stu-id="f29bc-121">Constructing a geography Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="f29bc-122">Il tipo di dati `geography` fornisce diversi metodi predefiniti che generano una geografia dalla rappresentazione WKT Open Geospatial Consortium (OGC).</span><span class="sxs-lookup"><span data-stu-id="f29bc-122">The `geography` data type provides several built-in methods that generate a geography from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="f29bc-123">Lo standard WKT è una stringa di testo che consente ai dati geografici di essere scambiati in formato testuale.</span><span class="sxs-lookup"><span data-stu-id="f29bc-123">The WKT standard is a text string that allows geography data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="f29bc-124">**Per costruire qualsiasi tipo di istanza geografica dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="f29bc-124">**To construct any type of geography instance from WKT input**</span></span>  
 [<span data-ttu-id="f29bc-125">STGeomFromText &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-125">STGeomFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)  
  
 [<span data-ttu-id="f29bc-126">Parse &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-126">Parse &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/parse-geography-data-type)  
  
 <span data-ttu-id="f29bc-127">**Per costruire un'istanza geografica Point dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="f29bc-127">**To construct a geography Point instance from WKT input**</span></span>  
 [<span data-ttu-id="f29bc-128">STPointFromText &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-128">STPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromtext-geography-data-type)  
  
 <span data-ttu-id="f29bc-129">**Per costruire un'istanza geografica MultiPoint dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="f29bc-129">**To construct a geography MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="f29bc-130">STMPointFromText &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-130">STMPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromtext-geography-data-type)  
  
 <span data-ttu-id="f29bc-131">**Per costruire un'istanza geografica LineString dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="f29bc-131">**To construct a geography LineString instance from WKT input**</span></span>  
 <span data-ttu-id="f29bc-132">STLineFromText (tipo di dati geography)</span><span class="sxs-lookup"><span data-stu-id="f29bc-132">STLineFromText (geography Data Type)</span></span>  
  
 <span data-ttu-id="f29bc-133">**Per costruire un'istanza geografica MultiLineString dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="f29bc-133">**To construct a geography MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="f29bc-134">STMLineFromText &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-134">STMLineFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromtext-geography-data-type)  
  
 <span data-ttu-id="f29bc-135">**Per costruire un'istanza geografica Polygon dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="f29bc-135">**To construct a geography Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="f29bc-136">STPolyFromText &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-136">STPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="f29bc-137">**Per costruire un'istanza geografica MultiPolygon dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="f29bc-137">**To construct a geography MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="f29bc-138">STMPolyFromText &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-138">STMPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="f29bc-139">**Per costruire un'istanza geografica GeometryCollection dall'input WKT**</span><span class="sxs-lookup"><span data-stu-id="f29bc-139">**To construct a geography GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="f29bc-140">STGeomCollFromText &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-140">STGeomCollFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomcollfromtext-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="f29bc-141">Costruzione di un'istanza geografica dall'input WKB (well-known binary)</span><span class="sxs-lookup"><span data-stu-id="f29bc-141">Constructing a geography Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="f29bc-142">WKB è un formato binario specificato da OGC che consente di scambiare dati `Geography` tra un'applicazione client e un database SQL.</span><span class="sxs-lookup"><span data-stu-id="f29bc-142">WKB is a binary format specified by the OGC that permits `Geography` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="f29bc-143">Le seguenti funzioni accettano l'input WKB per costruire le istanze geografiche:</span><span class="sxs-lookup"><span data-stu-id="f29bc-143">The following functions accept WKB input to construct geography instances:</span></span>  
  
 <span data-ttu-id="f29bc-144">**Per costruire qualsiasi tipo di istanza geografica dall'input WKB**</span><span class="sxs-lookup"><span data-stu-id="f29bc-144">**To construct any type of geography instance from WKB input**</span></span>  
 [<span data-ttu-id="f29bc-145">STGeomFromWKB &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-145">STGeomFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromwkb-geography-data-type)  
  
 <span data-ttu-id="f29bc-146">**Per costruire un'istanza geografica Point dall'input WKB**</span><span class="sxs-lookup"><span data-stu-id="f29bc-146">**To construct a geography Point instance from WKB input**</span></span>  
 [<span data-ttu-id="f29bc-147">STPointFromWKB &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-147">STPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="f29bc-148">**Per costruire un'istanza geografica MultiPoint dall'input WKB**</span><span class="sxs-lookup"><span data-stu-id="f29bc-148">**To construct a geography MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="f29bc-149">STMPointFromWKB &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-149">STMPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="f29bc-150">**Per costruire un'istanza geografica LineString dall'input WKB**</span><span class="sxs-lookup"><span data-stu-id="f29bc-150">**To construct a geography LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="f29bc-151">STLineFromWKB &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-151">STLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="f29bc-152">**Per costruire un'istanza geografica MultiLineString dall'input WKB**</span><span class="sxs-lookup"><span data-stu-id="f29bc-152">**To construct a geography MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="f29bc-153">STMLineFromWKB &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-153">STMLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="f29bc-154">**Per costruire un'istanza geografica Polygon dall'input WKB**</span><span class="sxs-lookup"><span data-stu-id="f29bc-154">**To construct a geography Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="f29bc-155">STPolyFromWKB &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-155">STPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="f29bc-156">**Per costruire un'istanza geografica MultiPolygon dall'input WKB**</span><span class="sxs-lookup"><span data-stu-id="f29bc-156">**To construct a geography MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="f29bc-157">STMPolyFromWKB &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-157">STMPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="f29bc-158">**Per costruire un'istanza geografica GeometryCollection dall'input WKB**</span><span class="sxs-lookup"><span data-stu-id="f29bc-158">**To construct a geography GeometryCollection instance from WKB input**</span></span>  
 <span data-ttu-id="f29bc-159">[STGeomCollFromWKB &#40;tipo di dati geography&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (tipo di dati geography)</span><span class="sxs-lookup"><span data-stu-id="f29bc-159">[STGeomCollFromWKB &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (geography Data Type)</span></span>  
  
###  <a name="constructing-a-geography-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="f29bc-160">Costruzione di un'istanza geografica dall'input di testo GML</span><span class="sxs-lookup"><span data-stu-id="f29bc-160">Constructing a geography Instance from GML Text Input</span></span>  
 <span data-ttu-id="f29bc-161">Il `geography` tipo di dati fornisce un metodo che genera un' `geography` istanza da GML, una rappresentazione XML di un' `geography` istanza.</span><span class="sxs-lookup"><span data-stu-id="f29bc-161">The `geography` data type provides a method that generates a `geography` instance from GML, an XML representation of a `geography` instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f29bc-162">supporta un subset di GML.</span><span class="sxs-lookup"><span data-stu-id="f29bc-162">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="f29bc-163">Per altre informazioni su Geography Markup Language (GML), vedere la specifica OGC [OGC Specifications, Geography Markup Language](https://go.microsoft.com/fwlink/?LinkId=93629)(Specifiche OGC, Geography Markup Language).</span><span class="sxs-lookup"><span data-stu-id="f29bc-163">For more information on Geography Markup Language, see the OGC Specification: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span></span>  
  
 <span data-ttu-id="f29bc-164">**Per costruire qualsiasi tipo di istanza geografica dall'input GML**</span><span class="sxs-lookup"><span data-stu-id="f29bc-164">**To construct any type of geography instance from GML input**</span></span>  
 [<span data-ttu-id="f29bc-165">GeomFromGML &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-165">GeomFromGML &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/geomfromgml-geography-data-type)  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geography-instance"></a><a name="returning"></a> <span data-ttu-id="f29bc-166">Restituzione di WKT e WKB da un'istanza geografica</span><span class="sxs-lookup"><span data-stu-id="f29bc-166">Returning Well-Known Text and Well-Known Binary from a geography Instance</span></span>  
 <span data-ttu-id="f29bc-167">È possibile utilizzare i metodi seguenti per restituire il formato WKT o WKB di un'istanza `geography`:</span><span class="sxs-lookup"><span data-stu-id="f29bc-167">You can use the following methods to return either the WKT or WKB format of a `geography` instance:</span></span>  
  
 <span data-ttu-id="f29bc-168">**Per restituire la rappresentazione WKT di un'istanza di geografia**</span><span class="sxs-lookup"><span data-stu-id="f29bc-168">**To return the WKT representation of a geography instance**</span></span>  
 [<span data-ttu-id="f29bc-169">STAsText &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-169">STAsText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stastext-geography-data-type)  
  
 [<span data-ttu-id="f29bc-170">ToString &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-170">ToString &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/tostring-geography-data-type)  
  
 <span data-ttu-id="f29bc-171">**Per restituire la rappresentazione WKT di un'istanza di geografia, con qualsiasi valore Z e M.**</span><span class="sxs-lookup"><span data-stu-id="f29bc-171">**To return the WKT representation of a geography instance including any Z and M values**</span></span>  
 [<span data-ttu-id="f29bc-172">AsTextZM &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-172">AsTextZM &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/astextzm-geography-data-type)  
  
 <span data-ttu-id="f29bc-173">**Per restituire la rappresentazione WKB di un'istanza geografica**</span><span class="sxs-lookup"><span data-stu-id="f29bc-173">**To return the WKB representation of a geography instance**</span></span>  
 [<span data-ttu-id="f29bc-174">STAsBinary &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-174">STAsBinary &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stasbinary-geography-data-type)  
  
 <span data-ttu-id="f29bc-175">**Per restituire la rappresentazione GML di un'istanza geografica**</span><span class="sxs-lookup"><span data-stu-id="f29bc-175">**To return a GML representation of a geography instance**</span></span>  
 [<span data-ttu-id="f29bc-176">AsGml &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-176">AsGml &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/asgml-geography-data-type)  
  
##  <a name="querying-the-properties-and-behaviors-of-geography-instances"></a><a name="query"></a> <span data-ttu-id="f29bc-177">Esecuzione di query sulle proprietà e i comportamenti delle istanze geografiche</span><span class="sxs-lookup"><span data-stu-id="f29bc-177">Querying the Properties and Behaviors of geography Instances</span></span>  
 <span data-ttu-id="f29bc-178">Tutte le `geography` istanze hanno un certo numero di proprietà che possono essere recuperate tramite metodi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibili in.</span><span class="sxs-lookup"><span data-stu-id="f29bc-178">All `geography` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="f29bc-179">Negli argomenti seguenti vengono definite le proprietà e i comportamenti dei tipi di geografia, nonché i metodi per l'esecuzione di query per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="f29bc-179">The following topics define the properties and behaviors of geography types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="f29bc-180">Informazioni sulla validità, sul tipo di istanza e su GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="f29bc-180">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="f29bc-181">Dopo aver costruito un'istanza `geography`, è possibile utilizzare i seguenti metodi per restituire il tipo di istanza oppure, se si tratta di un'istanza `GeometryCollection`, restituire un'istanza `geography` specifica.</span><span class="sxs-lookup"><span data-stu-id="f29bc-181">After a `geography` instance is constructed, you can use the following methods to return the instance type, or if it is a `GeometryCollection` instance, return a specific `geography` instance.</span></span>  
  
 <span data-ttu-id="f29bc-182">**Per restituire il tipo di istanza di una geografia**</span><span class="sxs-lookup"><span data-stu-id="f29bc-182">**To return the instance type of a geography**</span></span>  
 [<span data-ttu-id="f29bc-183">STGeometryType &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-183">STGeometryType &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeometrytype-geography-data-type)  
  
 <span data-ttu-id="f29bc-184">**Per determinare se una geografia è un tipo di istanza specificato**</span><span class="sxs-lookup"><span data-stu-id="f29bc-184">**To determine if a geography is a given instance type**</span></span>  
 [<span data-ttu-id="f29bc-185">InstanceOf &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-185">InstanceOf &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/instanceof-geography-data-type)  
  
 <span data-ttu-id="f29bc-186">**Per determinare se il formato di un'istanza di geografia è corretto per il tipo di istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-186">**To determine if a geography instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="f29bc-187">STNumGeometries &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-187">STNumGeometries &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumgeometries-geography-data-type)  
  
 <span data-ttu-id="f29bc-188">**Per restituire una specifica geografia in un'istanza GeometryCollection**</span><span class="sxs-lookup"><span data-stu-id="f29bc-188">**To return a specific geography in a GeometryCollection instance**</span></span>  
 <span data-ttu-id="f29bc-189">[STGeometryN &#40;tipo di dati geography&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (tipo di dati geography)</span><span class="sxs-lookup"><span data-stu-id="f29bc-189">[STGeometryN &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (geography Data Type)</span></span>  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="f29bc-190">Numero di punti</span><span class="sxs-lookup"><span data-stu-id="f29bc-190">Number of Points</span></span>  
 <span data-ttu-id="f29bc-191">Tutte le istanze non vuote `geography` sono costituite da *punti*.</span><span class="sxs-lookup"><span data-stu-id="f29bc-191">All nonempty `geography` instances are comprised of *points*.</span></span> <span data-ttu-id="f29bc-192">che rappresentano le coordinate di latitudine e longitudine terrestri sulle quali vengono tracciate le istanze `geography`.</span><span class="sxs-lookup"><span data-stu-id="f29bc-192">These points represent the latitude and longitude coordinates of the earth on which the `geography` instances are drawn.</span></span> <span data-ttu-id="f29bc-193">Il tipo di dati `geography` fornisce numerosi metodi predefiniti per l'esecuzione di query sui punti di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="f29bc-193">The data type `geography` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="f29bc-194">**Per restituire il numero di punti che comprendono un'istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-194">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="f29bc-195">STNumPoints &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-195">STNumPoints &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumpoints-geography-data-type)  
  
 <span data-ttu-id="f29bc-196">**Per restituire un punto specifico in un'istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-196">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="f29bc-197">STPointN &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-197">STPointN &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="f29bc-198">**Per restituire il punto di inizio di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-198">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="f29bc-199">STStartPoint &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-199">STStartPoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ststartpoint-geography-data-type)  
  
 <span data-ttu-id="f29bc-200">**Per restituire il punto di fine di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-200">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="f29bc-201">STEndpoint &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-201">STEndpoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stendpoint-geography-data-type)  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="f29bc-202">Dimensione</span><span class="sxs-lookup"><span data-stu-id="f29bc-202">Dimension</span></span>  
 <span data-ttu-id="f29bc-203">Un'istanza `geography` non vuota può essere a 0, 1 o 2 dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f29bc-203">A nonempty `geography` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="f29bc-204">Le istanze con dimensione zero `geography` , ad esempio `Point` e `MultiPoint` , non hanno lunghezza o area.</span><span class="sxs-lookup"><span data-stu-id="f29bc-204">Zero-dimensional `geography` instances, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="f29bc-205">Gli oggetti unidimensionali, ad esempio `LineString, CircularString`, `CompoundCurve` e `MultiLineString`, dispongono della lunghezza.</span><span class="sxs-lookup"><span data-stu-id="f29bc-205">One-dimensional objects, such as `LineString, CircularString`, `CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="f29bc-206">Le istanze bidimensionali, ad esempio `Polygon, CurvePolygon` e `MultiPolygon`, dispongono di area e lunghezza.</span><span class="sxs-lookup"><span data-stu-id="f29bc-206">Two-dimensional instances, such as `Polygon, CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="f29bc-207">Le istanze vuote indicano una dimensione di -1 e `GeometryCollection` indica le dimensioni massime del contenuto.</span><span class="sxs-lookup"><span data-stu-id="f29bc-207">Empty instances report a dimension of -1, and a `GeometryCollection` reports the maximum dimension of its contents.</span></span>  
  
 <span data-ttu-id="f29bc-208">**Per restituire la dimensione di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-208">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="f29bc-209">STDimension &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-209">STDimension &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdimension-geography-data-type)  
  
 <span data-ttu-id="f29bc-210">**Per restituire la lunghezza di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-210">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="f29bc-211">STLength &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-211">STLength &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlength-geography-data-type)  
  
 <span data-ttu-id="f29bc-212">**Per restituire l'area di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-212">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="f29bc-213">STArea &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-213">STArea &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/starea-geography-data-type)  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="f29bc-214">Vuoto</span><span class="sxs-lookup"><span data-stu-id="f29bc-214">Empty</span></span>  
 <span data-ttu-id="f29bc-215">Un'istanza *vuota* non `geography` contiene punti.</span><span class="sxs-lookup"><span data-stu-id="f29bc-215">An *empty*`geography` instance does not have any points.</span></span> <span data-ttu-id="f29bc-216">La lunghezza delle istanze vuote `LineString, CircularString`, `CompoundCurve` e `MultiLineString` è 0.</span><span class="sxs-lookup"><span data-stu-id="f29bc-216">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is 0.</span></span> <span data-ttu-id="f29bc-217">L'area delle istanze vuote `Polygon, CurvePolygon` and `MultiPolygon` è 0.</span><span class="sxs-lookup"><span data-stu-id="f29bc-217">The area of empty `Polygon, CurvePolygon` and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="f29bc-218">**Per determinare se un'istanza è vuota**</span><span class="sxs-lookup"><span data-stu-id="f29bc-218">**To determine if an instance is empty**</span></span>  
 [<span data-ttu-id="f29bc-219">STIsEmpty &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-219">STIsEmpty &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisempty-geography-data-type)  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="f29bc-220">Chiusura</span><span class="sxs-lookup"><span data-stu-id="f29bc-220">Closure</span></span>  
 <span data-ttu-id="f29bc-221">Un'istanza *chiusa* `geography` è una figura i cui punti di inizio e di fine sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="f29bc-221">A *closed*`geography` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="f29bc-222">Le istanze `Polygon` sono considerate chiuse.</span><span class="sxs-lookup"><span data-stu-id="f29bc-222">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="f29bc-223">Le istanze `Point` non sono considerate chiuse.</span><span class="sxs-lookup"><span data-stu-id="f29bc-223">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="f29bc-224">Un anello è un'istanza `LineString` semplice chiusa.</span><span class="sxs-lookup"><span data-stu-id="f29bc-224">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="f29bc-225">**Per determinare se un'istanza è chiusa**</span><span class="sxs-lookup"><span data-stu-id="f29bc-225">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="f29bc-226">STIsClosed &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-226">STIsClosed &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisclosed-geography-data-type)  
  
 <span data-ttu-id="f29bc-227">**Per restituire il numero di anelli in un'istanza Polygon**</span><span class="sxs-lookup"><span data-stu-id="f29bc-227">**To return the number of rings in a Polygon instance**</span></span>  
 [<span data-ttu-id="f29bc-228">NumRings &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-228">NumRings &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/numrings-geography-data-type)  
  
 <span data-ttu-id="f29bc-229">**Per restituire un anello specificato di un'istanza di geografia**</span><span class="sxs-lookup"><span data-stu-id="f29bc-229">**To return a specified ring of a geography instance**</span></span>  
 [<span data-ttu-id="f29bc-230">RingN &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-230">RingN &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ringn-geography-data-type)  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="f29bc-231">Identificatore SRID</span><span class="sxs-lookup"><span data-stu-id="f29bc-231">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="f29bc-232">L'identificatore SRID specifica in quale sistema di coordinate ellissoidali è rappresentata l'istanza `geography`.</span><span class="sxs-lookup"><span data-stu-id="f29bc-232">The spatial reference ID (SRID) is an identifier specifying which ellipsoidal coordinate system the `geography` instance is represented in.</span></span> <span data-ttu-id="f29bc-233">Non è possibile confrontare due istanze `geography` con identificatori SRID diversi.</span><span class="sxs-lookup"><span data-stu-id="f29bc-233">Two `geography` instances with different SRIDs cannot be compared.</span></span>  
  
 <span data-ttu-id="f29bc-234">**Per impostare o restituire l'identificatore SRID di un'istanza**</span><span class="sxs-lookup"><span data-stu-id="f29bc-234">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="f29bc-235">STSrid &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-235">STSrid &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsrid-geography-data-type)  
  
 <span data-ttu-id="f29bc-236">Questa proprietà può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="f29bc-236">This property can be modified.</span></span>  
  
##  <a name="determining-relationships-between-geography-instances"></a><a name="rel"></a> <span data-ttu-id="f29bc-237">Determinazione delle relazioni esistenti tra istanze geografiche</span><span class="sxs-lookup"><span data-stu-id="f29bc-237">Determining Relationships between geography Instances</span></span>  
 <span data-ttu-id="f29bc-238">Il tipo di dati `geography` offre molti metodi predefiniti che è possibile utilizzare per determinare relazioni tra due istanze `geography`.</span><span class="sxs-lookup"><span data-stu-id="f29bc-238">The `geography` data type provides many built-in methods you can use to determine relationships between two `geography` instances.</span></span>  
  
 <span data-ttu-id="f29bc-239">**Per determinare se due istanze includono lo stesso punto impostato**</span><span class="sxs-lookup"><span data-stu-id="f29bc-239">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="f29bc-240">STEquals &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-240">STEquals &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="f29bc-241">**Per determinare se due istanze sono disgiunte**</span><span class="sxs-lookup"><span data-stu-id="f29bc-241">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="f29bc-242">STDisjoint &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-242">STDisjoint &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="f29bc-243">**Per determinare se due istanze si intersecano**</span><span class="sxs-lookup"><span data-stu-id="f29bc-243">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="f29bc-244">STIntersects &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-244">STIntersects &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="f29bc-245">**Per determinare il punto o i punti in cui due istanze si intersecano**</span><span class="sxs-lookup"><span data-stu-id="f29bc-245">**To determine the point or points where two instances intersect**</span></span>  
 [<span data-ttu-id="f29bc-246">STIntersection &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-246">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="f29bc-247">**Per determinare la distanza più breve tra punti in due istanze di geografia**</span><span class="sxs-lookup"><span data-stu-id="f29bc-247">**To determine the shortest distance between points in two geography instances**</span></span>  
 [<span data-ttu-id="f29bc-248">STDistance &#40;tipo di dati geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-248">STDistance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
 <span data-ttu-id="f29bc-249">**Per determinare la differenza in termini di punti tra due istanze di geografia**</span><span class="sxs-lookup"><span data-stu-id="f29bc-249">**To determine the difference in points between two geography instances**</span></span>  
 [<span data-ttu-id="f29bc-250">STDifference &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-250">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
 <span data-ttu-id="f29bc-251">**Per dedurre la differenza simmetrica o i punti univoci di un'istanza geografica a confronto con un'altra**</span><span class="sxs-lookup"><span data-stu-id="f29bc-251">**To derive the symmetric difference, or unique points, of one geography instance compared with another instance**</span></span>  
 [<span data-ttu-id="f29bc-252">STSymDifference &#40;tipo di dati geography&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-252">STSymDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsymdifference-geography-data-type)  
  
##  <a name="geography-instances-must-use-supported-srid"></a><a name="supportedsrid"></a> <span data-ttu-id="f29bc-253">Le istanze geografiche devono utilizzare l'identificatore SRID supportato</span><span class="sxs-lookup"><span data-stu-id="f29bc-253">geography Instances Must Use Supported SRID</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f29bc-254">supporta gli identificatori SRID basati sugli standard EPSG.</span><span class="sxs-lookup"><span data-stu-id="f29bc-254">supports SRIDs based on the EPSG standards.</span></span> <span data-ttu-id="f29bc-255">È necessario utilizzare un identificatore SRID supportato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per le istanze `geography` se si eseguono calcoli o si utilizzano metodi con dati spaziali di geografia.</span><span class="sxs-lookup"><span data-stu-id="f29bc-255">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-supported SRID for `geography` instances must be used when performing calculations or using methods with geography spatial data.</span></span> <span data-ttu-id="f29bc-256">L'identificatore SRID deve corrispondere a uno di quelli visualizzati nella vista del catalogo **sys.spatial_reference_systems**</span><span class="sxs-lookup"><span data-stu-id="f29bc-256">The SRID must match one of the SRIDs displayed in the **sys.spatial_reference_systems** catalog view.</span></span> <span data-ttu-id="f29bc-257">Come indicato in precedenza, quando si eseguono i calcoli sui dati spaziali utilizzando il tipo di dati `geography` i risultati dipenderanno dal tipo di ellissoide utilizzato nella creazione dei dati, in quanto a ogni ellissoide è assegnato un identificatore SRID specifico.</span><span class="sxs-lookup"><span data-stu-id="f29bc-257">As mentioned previously, when you perform calculations on your spatial data using the `geography` data type, your results will depend on which ellipsoid was used in the creation of your data, as each ellipsoid is assigned a specific spatial reference identifier (SRID).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f29bc-258">utilizza l'identificatore predefinito SRID di 4326., che esegue il mapping al sistema di riferimento spaziale WHS 84 in caso si utilizzino metodi nelle istanze `geography`.</span><span class="sxs-lookup"><span data-stu-id="f29bc-258">uses the default SRID of 4326, which maps to the WGS 84 spatial reference system, when using methods on `geography` instances.</span></span> <span data-ttu-id="f29bc-259">Se si utilizzano dati da un sistema di riferimento spaziale diverso da WGS 84 (o SRID 4326), sarà necessario determinare lo specifico identificatore SRID per i dati spaziali geografici.</span><span class="sxs-lookup"><span data-stu-id="f29bc-259">If you use data from a spatial reference system other than WGS 84 (or SRID 4326), you will need to determine the specific SRID for your geography spatial data.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="f29bc-260">Esempi</span><span class="sxs-lookup"><span data-stu-id="f29bc-260">Examples</span></span>  
 <span data-ttu-id="f29bc-261">Negli esempi seguenti viene illustrato come aggiungere ed eseguire query su dati geography.</span><span class="sxs-lookup"><span data-stu-id="f29bc-261">The following examples show how to add and query geography data.</span></span>  
  
-   <span data-ttu-id="f29bc-262">Nel primo esempio viene creata una tabella con una colonna di identità e una colonna `geography``GeogCol1`.</span><span class="sxs-lookup"><span data-stu-id="f29bc-262">The first example creates a table with an identity column and a `geography` column `GeogCol1`.</span></span> <span data-ttu-id="f29bc-263">Una terza colonna effettua il rendering della colonna `geography` nella rappresentazione Well-Known Text (WKT) OGC (Open Geospatial Consortium) e utilizza il metodo `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="f29bc-263">A third column renders the `geography` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="f29bc-264">Vengono quindi inserite due righe: in una riga è contenuta un'istanza `LineString` di `geography`e in una seconda è contenuta un'istanza `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="f29bc-264">Two rows are then inserted: one row contains a `LineString` instance of `geography`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeogCol1 geography,   
        GeogCol2 AS GeogCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326));  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326));  
    GO  
    ```  
  
-   <span data-ttu-id="f29bc-265">Nel secondo esempio viene utilizzato il metodo `STIntersection()` per restituire i punti in cui si intersecano le due istanze `geography` inserite in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f29bc-265">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geography` instances intersect.</span></span>  
  
    ```  
    DECLARE @geog1 geography;  
    DECLARE @geog2 geography;  
    DECLARE @result geography;  
  
    SELECT @geog1 = GeogCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geog2 = GeogCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geog1.STIntersection(@geog2);  
    SELECT @result.STAsText();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f29bc-266">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f29bc-266">See Also</span></span>  
 [<span data-ttu-id="f29bc-267">Dati spaziali &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f29bc-267">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
