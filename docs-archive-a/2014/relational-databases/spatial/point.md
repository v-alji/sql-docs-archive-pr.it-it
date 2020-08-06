---
title: Punto | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Point geometry subtype [SQL Server]
- geometry data type [SQL Server], spatial data
ms.assetid: 2a596ec4-8b2f-4962-bcb4-e5c8f77edad5
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4b12069d84e00738e3ddac8c414f33903f4f0999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637169"
---
# <a name="point"></a><span data-ttu-id="234bb-102">Point</span><span class="sxs-lookup"><span data-stu-id="234bb-102">Point</span></span>
  <span data-ttu-id="234bb-103">Nei dati spaziali [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un `Point` è un oggetto senza dimensioni che rappresenta una sola posizione e può contenere valori Z (innalzamento) e M (misura).</span><span class="sxs-lookup"><span data-stu-id="234bb-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data, a `Point` is a 0-dimensional object representing a single location and may contain Z (elevation) and M (measure) values.</span></span>  
  
## <a name="geography-data-type"></a><span data-ttu-id="234bb-104">Tipo di dati geography</span><span class="sxs-lookup"><span data-stu-id="234bb-104">Geography Data Type</span></span>  
 <span data-ttu-id="234bb-105">Il tipo Punto del tipo di dati geography rappresenta una singola posizione in cui *Lat* indica la latitudine e *Long* la longitudine.</span><span class="sxs-lookup"><span data-stu-id="234bb-105">The Point type for the geography data type represents a single location where *Lat* represents latitude and *Long* represents longitude.</span></span> <span data-ttu-id="234bb-106">I valori di latitudine e longitudine vengono misurati in gradi.</span><span class="sxs-lookup"><span data-stu-id="234bb-106">The values for latitude and longitude are measured in degrees.</span></span> <span data-ttu-id="234bb-107">I valori della latitudine sono compresi sempre nell'intervallo [-90, 90], quelli al di fuori genereranno un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="234bb-107">Values for latitude always lie in the interval [-90, 90], and values that are inputted outside this range will throw an exception.</span></span> <span data-ttu-id="234bb-108">I valori della longitudine sono compresi sempre nell'intervallo [-180, 180], quelli al fuori, per rientrare in tale intervallo, vengono arrotondati.</span><span class="sxs-lookup"><span data-stu-id="234bb-108">Values for longitude always lie in the interval (-180, 180], and values inputted outside this range are wrapped around to fit in this range.</span></span> <span data-ttu-id="234bb-109">Ad esempio, se il valore immesso per la longitudine è 190, verrà arrotondato a -170.</span><span class="sxs-lookup"><span data-stu-id="234bb-109">For example, if 190 is inputted for longitude, then it will be wrapped to the value -170.</span></span> <span data-ttu-id="234bb-110">*SRID* rappresenta l'ID di riferimento spaziale dell'istanza **geography** da restituire.</span><span class="sxs-lookup"><span data-stu-id="234bb-110">*SRID* represents the spatial reference ID of the **geography** instance that you wish to return.</span></span>  
  
## <a name="geometry-data-type"></a><span data-ttu-id="234bb-111">Tipo di dati geometry</span><span class="sxs-lookup"><span data-stu-id="234bb-111">Geometry Data Type</span></span>  
 <span data-ttu-id="234bb-112">Il tipo Punto per il tipo di dati geometry rappresenta una singola posizione in cui *X* e *Y* rappresentano rispettivamente le coordinate X e Y del punto generato.</span><span class="sxs-lookup"><span data-stu-id="234bb-112">The Point type for the geometry data type represents a single location where *X* represents the X-coordinate of the Point being generated and *Y* represents the Y-coordinate of the Point being generated.</span></span> <span data-ttu-id="234bb-113">*SRID* rappresenta l'ID di riferimento spaziale dell'istanza **geometry** da restituire.</span><span class="sxs-lookup"><span data-stu-id="234bb-113">*SRID* represents the spatial reference ID of the **geometry** instance that you wish to return.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="234bb-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="234bb-114">Examples</span></span>  
 <span data-ttu-id="234bb-115">L'esempio seguente illustra come creare un'istanza `geometry Point`che rappresenta il punto (3, 4) con un SRID pari a 0.</span><span class="sxs-lookup"><span data-stu-id="234bb-115">The following example creates a `geometry Point`instance representing the point (3, 4) with an SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT (3 4)', 0);  
```  
  
 <span data-ttu-id="234bb-116">L'esempio successivo illustra come creare un'istanza `geometry``Point` che rappresenta il punto (3, 4) con un valore Z (innalzamento) pari a 7, un valore M (misura) pari a 2,5 e SRID predefinito a 0.</span><span class="sxs-lookup"><span data-stu-id="234bb-116">The next example creates a `geometry``Point` instance representing the point (3, 4) with a Z (elevation) value of 7, an M (measure) value of 2.5, and the default SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 7 2.5)');  
```  
  
 <span data-ttu-id="234bb-117">L'esempio finale restituisce i valori X, Y, Z e M per l'istanza `geometry``Point` .</span><span class="sxs-lookup"><span data-stu-id="234bb-117">The final example returns the X, Y, Z, and M values for the `geometry``Point` instance.</span></span>  
  
```  
SELECT @g.STX;  
SELECT @g.STY;  
SELECT @g.Z;  
SELECT @g.M;  
```  
  
 <span data-ttu-id="234bb-118">I valori Z e M possono essere specificati in modo esplicito come NULL, così come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="234bb-118">Z and M values may be explicitly specified as NULL, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 NULL NULL)');  
```  
  
## <a name="see-also"></a><span data-ttu-id="234bb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="234bb-119">See Also</span></span>  
 <span data-ttu-id="234bb-120">[MultiPoint](multipoint.md) </span><span class="sxs-lookup"><span data-stu-id="234bb-120">[MultiPoint](multipoint.md) </span></span>  
 <span data-ttu-id="234bb-121">[Tipo di dati STX &#40;Geometry&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="234bb-121">[STX &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span></span>  
 <span data-ttu-id="234bb-122">[STY &#40;Tipo di dati geometry&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="234bb-122">[STY &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span></span>  
 [<span data-ttu-id="234bb-123">Dati spaziali &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="234bb-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
