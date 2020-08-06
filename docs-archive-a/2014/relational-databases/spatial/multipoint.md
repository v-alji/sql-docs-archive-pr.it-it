---
title: MultiPoint | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPoint geometry subtype [SQL Server]
ms.assetid: 2aaab211-3aba-4dbd-90b7-095d997b1f62
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b741071b7986aceea4e49d4fde8293ef2c96fc2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637173"
---
# <a name="multipoint"></a><span data-ttu-id="cb497-102">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="cb497-102">MultiPoint</span></span>
  <span data-ttu-id="cb497-103">Un `MultiPoint` è una raccolta di zero o più punti.</span><span class="sxs-lookup"><span data-stu-id="cb497-103">A `MultiPoint` is a collection of zero or more points.</span></span> <span data-ttu-id="cb497-104">Il limite di un'istanza `MultiPoint` è vuoto.</span><span class="sxs-lookup"><span data-stu-id="cb497-104">The boundary of a `MultiPoint` instance is empty.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cb497-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="cb497-105">Examples</span></span>  
 <span data-ttu-id="cb497-106">Nell'esempio seguente è creata un'istanza `geometry MultiPoint` con SRID 23 e due punti: uno con le coordinate (2, 3), e l'altro con le coordinate (7, 8) e un valore Z di 9,5.</span><span class="sxs-lookup"><span data-stu-id="cb497-106">The following example creates a `geometry MultiPoint` instance with SRID 23 and two points: one point with the coordinates (2, 3), one point with the coordinates (7, 8), and a Z value of 9.5.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="cb497-107">Questa istanza `MultiPoint` può essere anche espressa utilizzando `STMPointFromText()` come mostrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cb497-107">This `MultiPoint` instance can also be expressed using `STMPointFromText()` as shown below.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STMPointFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="cb497-108">Nell'esempio seguente viene utilizzato il metodo `STGeometryN()` per recuperare una descrizione del primo punto nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="cb497-108">The following example uses the method `STGeometryN()` to retrieve a description of the first point in the collection.</span></span>  
  
```  
SELECT @g.STGeometryN(1).STAsText();  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb497-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb497-109">See Also</span></span>  
 <span data-ttu-id="cb497-110">[Punto](point.md) </span><span class="sxs-lookup"><span data-stu-id="cb497-110">[Point](point.md) </span></span>  
 [<span data-ttu-id="cb497-111">Dati spaziali &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cb497-111">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
