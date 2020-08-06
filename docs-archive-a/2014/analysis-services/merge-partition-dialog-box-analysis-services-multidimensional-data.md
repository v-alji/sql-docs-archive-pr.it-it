---
title: Finestra di dialogo Unisci partizione (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.mergepartition.f1
ms.assetid: 1c94e250-ee18-4f98-b112-985f6346102a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1978c187bfb5097d286f78650b5bda6645c7a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636451"
---
# <a name="merge-partition-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="2166f-102">Finestra di dialogo Unisci partizione (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="2166f-102">Merge Partition Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="2166f-103">Utilizzare la finestra di dialogo **Unisci partizione** in **SQL Server Management Studio** per unire le partizioni relative a un gruppo di misure in un cubo.</span><span class="sxs-lookup"><span data-stu-id="2166f-103">Use the **Merge Partition** dialog box in **SQL Server Management Studio** to merge partitions for a measure group in a cube.</span></span> <span data-ttu-id="2166f-104">Per visualizzare la finestra di dialogo **Unisci partizione** , è possibile fare clic con il pulsante destro del mouse sulla cartella Partizioni o su una partizione in **Esplora oggetti** e quindi scegliere **Unisci partizioni** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="2166f-104">You can display the **Merge Partition** dialog box by right-clicking the Partitions folder or a partition in **Object Explorer** and selecting **Merge Partitions** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2166f-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2166f-105">Options</span></span>  
 <span data-ttu-id="2166f-106">**Server**</span><span class="sxs-lookup"><span data-stu-id="2166f-106">**Server**</span></span>  
 <span data-ttu-id="2166f-107">Consente di selezionare il nome dell'istanza di Analysis Services contenente la partizione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2166f-107">Select the name of the Analysis Services instance that contains the target partition.</span></span>  
  
 <span data-ttu-id="2166f-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2166f-108">**Name**</span></span>  
 <span data-ttu-id="2166f-109">Consente di selezionare il nome di una partizione esistente da utilizzare come partizione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2166f-109">Select the name of an existing partition to use as the target partition.</span></span>  
  
 <span data-ttu-id="2166f-110">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="2166f-110">**Folder**</span></span>  
 <span data-ttu-id="2166f-111">Visualizza il nome della cartella contenente la partizione di destinazione se la partizione selezionata in Nome non utilizza la cartella predefinita relativa all'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2166f-111">Displays the name of the folder that contains the target partition, if the partition selected in Name does not use the default folder for the Analysis Services instance.</span></span>  
  
 <span data-ttu-id="2166f-112">**Partizioni di origine**</span><span class="sxs-lookup"><span data-stu-id="2166f-112">**Source Partitions**</span></span>  
 <span data-ttu-id="2166f-113">Consente di visualizzare una griglia contenente le partizioni di origine che è possibile unire alla partizione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2166f-113">Displays a grind containing the source partitions that can be merged into the target partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2166f-114">È possibile unire solo le partizioni incluse nello stesso gruppo di misure che condividono la medesima struttura di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="2166f-114">Only partitions in the same measure group that share the same aggregation design can be merged.</span></span>  
  
 <span data-ttu-id="2166f-115">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="2166f-115">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="2166f-116">Colonna</span><span class="sxs-lookup"><span data-stu-id="2166f-116">Column</span></span>|<span data-ttu-id="2166f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2166f-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2166f-118">**Merge**</span><span class="sxs-lookup"><span data-stu-id="2166f-118">**Merge**</span></span>|<span data-ttu-id="2166f-119">Consente di unire la partizione di origine alla partizione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2166f-119">Select to merge the source partition into the target partition.</span></span>|  
|<span data-ttu-id="2166f-120">**Nome partizione**</span><span class="sxs-lookup"><span data-stu-id="2166f-120">**Partition Name**</span></span>|<span data-ttu-id="2166f-121">Visualizza il nome della partizione di origine.</span><span class="sxs-lookup"><span data-stu-id="2166f-121">Displays the name of the source partition.</span></span>|  
|<span data-ttu-id="2166f-122">**Ultima elaborazione**</span><span class="sxs-lookup"><span data-stu-id="2166f-122">**Last Processed**</span></span>|<span data-ttu-id="2166f-123">Visualizza la data e l'ora dell'ultima elaborazione della partizione di origine.</span><span class="sxs-lookup"><span data-stu-id="2166f-123">Displays the date and time at which the source partition was last processed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2166f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2166f-124">See Also</span></span>  
 <span data-ttu-id="2166f-125">[Partizioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2166f-125">[Partitions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="2166f-126">Unire partizioni in Analysis Services &#40;SSAS - Multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="2166f-126">Merge Partitions in Analysis Services &#40;SSAS - Multidimensional&#41;</span></span>](multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md)  
  
  
