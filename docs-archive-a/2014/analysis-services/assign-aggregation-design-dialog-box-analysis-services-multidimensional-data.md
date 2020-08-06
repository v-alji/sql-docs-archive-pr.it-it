---
title: Finestra di dialogo Assegna progettazione aggregazioni (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.copyaggregationdesign.f1
ms.assetid: 50c26cb1-c294-4f17-8b9e-435fdbd4806d
author: minewiskan
ms.author: owend
ms.openlocfilehash: dfc4f7a0847373360a79ddda366ad7aa3f02c5de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625924"
---
# <a name="assign-aggregation-design-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="4a26a-102">Finestra di dialogo Assegna progettazione aggregazioni (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="4a26a-102">Assign Aggregation Design Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="4a26a-103">Usare la finestra di dialogo **Assegna progettazione aggregazioni** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per assegnare le progettazioni delle aggregazioni a una o più partizioni di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4a26a-103">Use the **Assign Aggregation Design** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to assign aggregation designs to one or more destination partitions.</span></span> <span data-ttu-id="4a26a-104">Per visualizzare la finestra di dialogo **Assegna progettazione aggregazioni** fare clic con il pulsante destro del mouse su una partizione o aggregazione in **Esplora oggetti** e quindi scegliere **Assegna progettazione aggregazioni**.</span><span class="sxs-lookup"><span data-stu-id="4a26a-104">You can display the **Assign Aggregation Design** dialog box by right-clicking a partition or aggregation design in **Object Explorer** and selecting **Assign Aggregation Design**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4a26a-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4a26a-105">Options</span></span>  
  
|<span data-ttu-id="4a26a-106">Termine</span><span class="sxs-lookup"><span data-stu-id="4a26a-106">Term</span></span>|<span data-ttu-id="4a26a-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="4a26a-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="4a26a-108">**Progettazioni aggregazioni**</span><span class="sxs-lookup"><span data-stu-id="4a26a-108">**Aggregation designs**</span></span>|<span data-ttu-id="4a26a-109">Selezionare una progettazione aggregazioni da assegnare a una o più partizioni di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4a26a-109">Select an aggregation design to assign to one or more destination partitions.</span></span>|  
|<span data-ttu-id="4a26a-110">**Partizioni di destinazione**</span><span class="sxs-lookup"><span data-stu-id="4a26a-110">**Destination partitions**</span></span>|<span data-ttu-id="4a26a-111">Consente di selezionare le partizioni alle quali assegnare la progettazione aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="4a26a-111">Select the partitions to which to assign the aggregation design.</span></span> <span data-ttu-id="4a26a-112">Per specificare le partizioni di destinazione viene utilizzata la griglia seguente:</span><span class="sxs-lookup"><span data-stu-id="4a26a-112">The following grid is used to specify destination partitions:</span></span><br /><br /> <span data-ttu-id="4a26a-113">\<check box>: Selezionare o deselezionare la casella di controllo nell'intestazione di colonna per includere o escludere tutte le partizioni elencate come partizioni di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4a26a-113">\<check box>: Select or clear the check box in the column header to include or exclude all listed partitions as destination partitions.</span></span> <span data-ttu-id="4a26a-114">Selezionare o deselezionare la casella di controllo accanto a una partizione per includerla o escluderla come partizione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4a26a-114">Select or clear a check box next to a partition to include or exclude that partition as a destination partition.</span></span><br /><br /> <span data-ttu-id="4a26a-115">**Partition**: Visualizza il nome della partizione.</span><span class="sxs-lookup"><span data-stu-id="4a26a-115">**Partition**: Displays the name of the partition.</span></span><br /><br /> <span data-ttu-id="4a26a-116">**Origine**: consente di visualizzare la tabella o la query di origine per la partizione.</span><span class="sxs-lookup"><span data-stu-id="4a26a-116">**Source**: Displays the source table or query for the partition.</span></span><br /><br /> <span data-ttu-id="4a26a-117">**Progettazione aggregazioni**: consente di visualizzare il nome della progettazione delle aggregazioni esistente per la partizione.</span><span class="sxs-lookup"><span data-stu-id="4a26a-117">**Aggregation Design**: Displays the name of the existing aggregation design for the partition.</span></span>|  
|<span data-ttu-id="4a26a-118">**Nascondi partizioni con progettazioni aggregazioni**</span><span class="sxs-lookup"><span data-stu-id="4a26a-118">**Hide partitions with aggregation designs**</span></span>|<span data-ttu-id="4a26a-119">Selezionare per mostrare solo le partizioni che non hanno progettazioni aggregazioni assegnate.</span><span class="sxs-lookup"><span data-stu-id="4a26a-119">Select to show only the partitions that do not have aggregation designs assigned to them.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a26a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a26a-120">See Also</span></span>  
 [<span data-ttu-id="4a26a-121">Aggregations and Aggregation Designs</span><span class="sxs-lookup"><span data-stu-id="4a26a-121">Aggregations and Aggregation Designs</span></span>](multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
