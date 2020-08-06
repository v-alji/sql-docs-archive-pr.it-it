---
title: Identificatori SRID (Spatial Reference Identifier) | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Spatial Reference Identifiers (SRIDs)
- geodetic spatial data [SQL Server], identifiers
- SRID
ms.assetid: 0612658a-7d1b-4178-bdc2-42b914ea31a7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 15db59b43731b9a39ff4bef78e3a6cb6929e9b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629761"
---
# <a name="spatial-reference-identifiers-srids"></a><span data-ttu-id="a08f4-102">identificatori SRID (Spatial Reference Identifier)</span><span class="sxs-lookup"><span data-stu-id="a08f4-102">Spatial Reference Identifiers (SRIDs)</span></span>
  <span data-ttu-id="a08f4-103">Ogni istanza spaziale ha un identificatore SRID.</span><span class="sxs-lookup"><span data-stu-id="a08f4-103">Each spatial instance has a spatial reference identifier (SRID).</span></span> <span data-ttu-id="a08f4-104">L'identificatore SRID corrisponde a un sistema di riferimento spaziale basato sullo specifico ellissoide utilizzato per il mapping terra piatta o terra rotonda.</span><span class="sxs-lookup"><span data-stu-id="a08f4-104">The SRID corresponds to a spatial reference system based on the specific ellipsoid used for either flat-earth mapping or round-earth mapping.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a08f4-105">Per una descrizione dettagliata e alcuni esempi delle funzionalità spaziali introdotte in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], tra cui un nuovo SRID, scaricare il white paper [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)(Nuove funzionalità spaziali in SQL Server 2012).</span><span class="sxs-lookup"><span data-stu-id="a08f4-105">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including a new SRID, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="a08f4-106">Una colonna spaziale può contenere oggetti con identificatori SRID.</span><span class="sxs-lookup"><span data-stu-id="a08f4-106">A spatial column can contain objects with different SRIDs.</span></span> <span data-ttu-id="a08f4-107">Tuttavia, solo le istanze spaziali con lo stesso identificatore SRID possono essere utilizzate se si eseguono operazioni con i metodi dei dati spaziali [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sui dati.</span><span class="sxs-lookup"><span data-stu-id="a08f4-107">However, only spatial instances with the same SRID can be used when performing operations with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data methods on your data.</span></span> <span data-ttu-id="a08f4-108">Il risultato di qualsiasi metodo spaziale derivato da due istanze dei dati spaziali è valido solo se quelle istanze hanno lo stesso identificatore SRID, basato sulla stessa unità di misura, data e proiezione utilizzata per determinare le coordinate delle istanze.</span><span class="sxs-lookup"><span data-stu-id="a08f4-108">The result of any spatial method derived from two spatial data instances is valid only if those instances have the same SRID that is based on the same unit of measurement, datum, and projection used to determine the coordinates of the instances.</span></span> <span data-ttu-id="a08f4-109">Le unità di misura più comuni di un identificatore SRID sono metri o metri quadrati.</span><span class="sxs-lookup"><span data-stu-id="a08f4-109">The most common units of measurement of a SRID are meters or square meters.</span></span>  
  
 <span data-ttu-id="a08f4-110">Se due istanze spaziali non hanno lo stesso SRID, i risultati di un metodo tipo dati `geometry` o `geography` utilizzati nelle istanze restituiranno NULL.</span><span class="sxs-lookup"><span data-stu-id="a08f4-110">If two spatial instances do not have the same SRID, the results from a `geometry` or `geography` Data Type method used on the instances will return NULL.</span></span> <span data-ttu-id="a08f4-111">Ad esempio, affinché il seguente termine di predicato restituisca un risultato non NULL, le due istanze `geometry`, `geometry1` e `geometry2` devono avere stesso identificatore SRID:</span><span class="sxs-lookup"><span data-stu-id="a08f4-111">For example, for the following predicate term to return a non-NULL result, the two `geometry` instances, `geometry1` and `geometry2`, must have the same SRID:</span></span>  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  <span data-ttu-id="a08f4-112">Il sistema SRID è definito dallo standard [European Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) , un set di standard sviluppato per cartografia, rilevamenti e archiviazione dei dati geodetici.</span><span class="sxs-lookup"><span data-stu-id="a08f4-112">The spatial reference identification system is defined by the [European Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) standard, which is a set of standards developed for cartography, surveying, and geodetic data storage.</span></span> <span data-ttu-id="a08f4-113">Questo standard è di proprietà di Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span><span class="sxs-lookup"><span data-stu-id="a08f4-113">This standard is owned by the Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08f4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a08f4-114">See Also</span></span>  
 [<span data-ttu-id="a08f4-115">Panoramica dei tipi di dati spaziali</span><span class="sxs-lookup"><span data-stu-id="a08f4-115">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
