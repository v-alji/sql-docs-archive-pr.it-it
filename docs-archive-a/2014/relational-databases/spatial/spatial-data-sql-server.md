---
title: Dati spaziali (SQL Server) | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server], spatial storage design
- planar spatial data [SQL Server], designing
- spatial data types [SQL Server]
- geodetic spatial data [SQL Server]
- geometry data type [SQL Server], spatial storage design
- spatial storage [SQL Server]
- geodetic spatial data [SQL Server], designing
ms.assetid: 41a132a1-09e2-4426-b9df-225270cb8e15
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4d491420a9eca7c35b89b254a03381c6467c834c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637164"
---
# <a name="spatial-data-sql-server"></a><span data-ttu-id="6cce5-102">Dati spaziali (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6cce5-102">Spatial Data (SQL Server)</span></span>
  <span data-ttu-id="6cce5-103">I dati spaziali rappresentano informazioni sulla posizione fisica e sulla forma degli oggetti geometrici.</span><span class="sxs-lookup"><span data-stu-id="6cce5-103">Spatial data represents information about the physical location and shape of geometric objects.</span></span> <span data-ttu-id="6cce5-104">Questi oggetti possono essere dei punti oppure oggetti più complessi, come ad esempio paesi, strade o laghi.</span><span class="sxs-lookup"><span data-stu-id="6cce5-104">These objects can be point locations or more complex objects such as countries, roads, or lakes.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6cce5-105">supporta due tipi di dati spaziali: il tipo di dati `geometry` e il tipo di dati `geography`.</span><span class="sxs-lookup"><span data-stu-id="6cce5-105">supports two spatial data types: the `geometry` data type and the `geography` data type.</span></span>  
  
-   <span data-ttu-id="6cce5-106">Questo tipo `geometry` rappresenta i dati in un sistema di coordinate euclideo (piano).</span><span class="sxs-lookup"><span data-stu-id="6cce5-106">The `geometry` type represents data in a Euclidean (flat) coordinate system.</span></span>  
  
-   <span data-ttu-id="6cce5-107">Il tipo `geography` rappresenta i dati in un sistema di coordinate di tipo terra rotonda.</span><span class="sxs-lookup"><span data-stu-id="6cce5-107">The `geography` type represents data in a round-earth coordinate system.</span></span>  
  
 <span data-ttu-id="6cce5-108">Entrambi i tipi di dati sono implementati come tipi di dati Common Language Runtime (CLR) .NET in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cce5-108">Both data types are implemented as .NET common language runtime (CLR) data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6cce5-109">Per una descrizione dettagliata ed esempi delle nuove funzionalità spaziali di [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], scaricare il white paper [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)(Nuove funzionalità spaziali in SQL Server 2012).</span><span class="sxs-lookup"><span data-stu-id="6cce5-109">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="6cce5-110">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="6cce5-110">Related Tasks</span></span>  
 [<span data-ttu-id="6cce5-111">Creazione, costruzione e query di istanze geometry</span><span class="sxs-lookup"><span data-stu-id="6cce5-111">Create, Construct, and Query geometry Instances</span></span>](create-construct-and-query-geometry-instances.md)  
 <span data-ttu-id="6cce5-112">Vengono descritti i metodi da utilizzare con le istanze del tipo di dati geometry.</span><span class="sxs-lookup"><span data-stu-id="6cce5-112">Describes the methods that you can use with instances of the geometry data type.</span></span>  
  
 [<span data-ttu-id="6cce5-113">Creare, costruire ed eseguire query di istanze geografiche</span><span class="sxs-lookup"><span data-stu-id="6cce5-113">Create, Construct, and Query geography Instances</span></span>](create-construct-and-query-geography-instances.md)  
 <span data-ttu-id="6cce5-114">Vengono descritti i metodi che è possibile utilizzare con istanze del tipo di dati geography.</span><span class="sxs-lookup"><span data-stu-id="6cce5-114">Describes the methods that you can use with instances of the geography data type.</span></span>  
  
 [<span data-ttu-id="6cce5-115">Query dei dati spaziali per Nearest Neighbor</span><span class="sxs-lookup"><span data-stu-id="6cce5-115">Query Spatial Data for Nearest Neighbor</span></span>](query-spatial-data-for-nearest-neighbor.md)  
 <span data-ttu-id="6cce5-116">Viene descritto il modello di query utilizzato per trovare gli oggetti spaziali più vicini a un oggetto spaziale specifico.</span><span class="sxs-lookup"><span data-stu-id="6cce5-116">Describes the common query pattern that is used to find the closest spatial objects to a specific spatial object.</span></span>  
  
 [<span data-ttu-id="6cce5-117">Creazione, modifica ed eliminazione di indici spaziali</span><span class="sxs-lookup"><span data-stu-id="6cce5-117">Create, Modify, and Drop Spatial Indexes</span></span>](create-modify-and-drop-spatial-indexes.md)  
 <span data-ttu-id="6cce5-118">Fornisce informazioni sulla creazione, la modifica e il rilascio di un indice spaziale.</span><span class="sxs-lookup"><span data-stu-id="6cce5-118">Provides information about creating, altering, and dropping a spatial index.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="6cce5-119">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="6cce5-119">Related Content</span></span>  
 [<span data-ttu-id="6cce5-120">Panoramica dei tipi di dati spaziali</span><span class="sxs-lookup"><span data-stu-id="6cce5-120">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
 <span data-ttu-id="6cce5-121">Sono stati introdotti i tipi di dati spaziali.</span><span class="sxs-lookup"><span data-stu-id="6cce5-121">Introduces the spatial data types.</span></span>  
  
-   [<span data-ttu-id="6cce5-122">Point</span><span class="sxs-lookup"><span data-stu-id="6cce5-122">Point</span></span>](point.md)  
  
-   [<span data-ttu-id="6cce5-123">LineString</span><span class="sxs-lookup"><span data-stu-id="6cce5-123">LineString</span></span>](linestring.md)  
  
-   [<span data-ttu-id="6cce5-124">CircularString</span><span class="sxs-lookup"><span data-stu-id="6cce5-124">CircularString</span></span>](circularstring.md)  
  
-   [<span data-ttu-id="6cce5-125">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="6cce5-125">CompoundCurve</span></span>](compoundcurve.md)  
  
-   [<span data-ttu-id="6cce5-126">Polygon</span><span class="sxs-lookup"><span data-stu-id="6cce5-126">Polygon</span></span>](polygon.md)  
  
-   [<span data-ttu-id="6cce5-127">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="6cce5-127">CurvePolygon</span></span>](curvepolygon.md)  
  
-   [<span data-ttu-id="6cce5-128">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="6cce5-128">MultiPoint</span></span>](multipoint.md)  
  
-   [<span data-ttu-id="6cce5-129">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="6cce5-129">MultiLineString</span></span>](multilinestring.md)  
  
-   [<span data-ttu-id="6cce5-130">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="6cce5-130">MultiPolygon</span></span>](multipolygon.md)  
  
-   [<span data-ttu-id="6cce5-131">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="6cce5-131">GeometryCollection</span></span>](geometrycollection.md)  
  
 [<span data-ttu-id="6cce5-132">Panoramica degli indici spaziali</span><span class="sxs-lookup"><span data-stu-id="6cce5-132">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
 <span data-ttu-id="6cce5-133">Sono stati introdotti indici spaziali e vengono descritti gli schemi a mosaico.</span><span class="sxs-lookup"><span data-stu-id="6cce5-133">Introduces spatial indexes and describes tessellation and tessellation schemes.</span></span>  
  
  
