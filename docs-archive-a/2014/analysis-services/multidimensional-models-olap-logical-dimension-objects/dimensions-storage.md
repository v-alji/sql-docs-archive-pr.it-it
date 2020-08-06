---
title: Archiviazione dimensioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], storage
- storing data [Analysis Services]
- storage [Analysis Services], dimensions
- relational OLAP
- multidimensional OLAP
- MOLAP
- storing data [Analysis Services], dimensions
- ROLAP
ms.assetid: 8d74b932-2174-4e1f-8414-636455880b6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa68ebcfa8f4136bcd4a131842c852665ee9851
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712592"
---
# <a name="dimension-storage"></a><span data-ttu-id="8c981-102">Archiviazione di dimensioni</span><span class="sxs-lookup"><span data-stu-id="8c981-102">Dimension Storage</span></span>
  <span data-ttu-id="8c981-103">Le dimensioni in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supportano due modalità di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="8c981-103">Dimensions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support two storage modes:</span></span>  
  
-   <span data-ttu-id="8c981-104">OLAP relazionale (ROLAP)</span><span class="sxs-lookup"><span data-stu-id="8c981-104">Relational OLAP (ROLAP)</span></span>  
  
-   <span data-ttu-id="8c981-105">OLAP multidimensionale (MOLAP)</span><span class="sxs-lookup"><span data-stu-id="8c981-105">Multidimensional OLAP (MOLAP)</span></span>  
  
 <span data-ttu-id="8c981-106">La modalità di archiviazione determina la posizione e la forma dei dati di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="8c981-106">The storage mode determines the location and form of a dimension's data.</span></span> <span data-ttu-id="8c981-107">MOLAP è la modalità di archiviazione predefinita per le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8c981-107">MOLAP is the default storage mode for dimensions.</span></span> <span data-ttu-id="8c981-108">**Argomenti correlati:**[elaborazione e modalità di archiviazione delle partizioni](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span><span class="sxs-lookup"><span data-stu-id="8c981-108">**Related topics:**[Partition Storage Modes and Processing](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span></span>  
  
## <a name="molap"></a><span data-ttu-id="8c981-109">MOLAP</span><span class="sxs-lookup"><span data-stu-id="8c981-109">MOLAP</span></span>  
 <span data-ttu-id="8c981-110">I dati per una dimensione che utilizza la modalità MOLAP vengono archiviati in una struttura multidimensionale nell'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c981-110">Data for a dimension that uses MOLAP is stored in a multidimensional structure in the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="8c981-111">Tale struttura multidimensionale viene creata e popolata durante l'elaborazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="8c981-111">This multidimensional structure is created and populated when the dimension is processed.</span></span> <span data-ttu-id="8c981-112">Le dimensioni MOLAP garantiscono prestazioni di esecuzione delle query migliori rispetto alle dimensioni ROLAP.</span><span class="sxs-lookup"><span data-stu-id="8c981-112">MOLAP dimensions provide better query performance than ROLAP dimensions.</span></span>  
  
## <a name="rolap"></a><span data-ttu-id="8c981-113">ROLAP</span><span class="sxs-lookup"><span data-stu-id="8c981-113">ROLAP</span></span>  
 <span data-ttu-id="8c981-114">I dati per una dimensione che utilizza la modalità ROLAP vengono effettivamente archiviati nelle tabelle utilizzate per definire la dimensione.</span><span class="sxs-lookup"><span data-stu-id="8c981-114">Data for a dimension that uses ROLAP is actually stored in the tables used to define the dimension.</span></span> <span data-ttu-id="8c981-115">La modalità ROLAP può essere utilizzata per supportare dimensioni grandi senza duplicare quantità di dati elevate, a spese, però, delle prestazioni di esecuzione delle query.</span><span class="sxs-lookup"><span data-stu-id="8c981-115">The ROLAP storage mode can be used to support large dimensions without duplicating large amounts of data, but at the expense of query performance.</span></span> <span data-ttu-id="8c981-116">Poiché la dimensione si basa direttamente sulle tabelle della vista origine dati utilizzata per definire la dimensione, la modalità di archiviazione ROLAP supporta inoltre l'elaborazione OLAP in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="8c981-116">Because the dimension relies directly on the tables in the data source view used to define the dimension, the ROLAP storage mode also supports real-time OLAP.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8c981-117">Se una dimensione utilizza la modalità di archiviazione ROLAP ed è inclusa in un cubo che utilizza l'archiviazione MOLAP, qualsiasi modifica dello schema nella tabella di origine deve essere seguita dall'immediata elaborazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="8c981-117">If a dimension uses the ROLAP storage mode and the dimension is included in a cube that uses MOLAP storage, any schema changes to its source table must be followed by immediate processing of the cube.</span></span> <span data-ttu-id="8c981-118">In caso contrario, i risultati delle query eseguite sui cubi potrebbero essere inconsistenti.</span><span class="sxs-lookup"><span data-stu-id="8c981-118">Failure to do this may result in inconsistent results when querying the cube.</span></span> <span data-ttu-id="8c981-119">**Argomento correlato:**[automatizzare Analysis Services attività amministrative con SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="8c981-119">**Related topic:**[Automate Analysis Services Administrative Tasks with SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c981-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c981-120">See Also</span></span>  
 [<span data-ttu-id="8c981-121">Elaborazione e modalità di archiviazione delle partizioni</span><span class="sxs-lookup"><span data-stu-id="8c981-121">Partition Storage Modes and Processing</span></span>](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
  
