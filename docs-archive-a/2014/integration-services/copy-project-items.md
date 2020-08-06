---
title: Copia elementi progetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Integration Services], copying
- packages [Integration Services], copying
- copying data source views
- copying data sources
- copying packages
- data source views [Integration Services], copying
ms.assetid: 1606c54d-20f9-49f3-a4ef-caad83a772aa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3456209c467c3b8474e130181d02304911098d2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629541"
---
# <a name="copy-project-items"></a><span data-ttu-id="90bf3-102">Copia di elementi di progetto</span><span class="sxs-lookup"><span data-stu-id="90bf3-102">Copy Project Items</span></span>
  <span data-ttu-id="90bf3-103">Questo argomento descrive come copiare gli oggetti all'interno di un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o tra progetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90bf3-103">This topic describes how to copy objects within an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or between [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="90bf3-104">È anche possibile copiare oggetti tra gli altri tipi di progetti di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] e [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90bf3-104">You can also copy objects between the other types of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] projects, [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="90bf3-105">Per copiare tra progetti, il progetto deve far parte della stessa soluzione di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90bf3-105">To copy between projects, the project must be part of the same [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] solution.</span></span> <span data-ttu-id="90bf3-106">Per altre informazioni, vedere [Progetti di Integration Services &#40;SSIS&#41;](integration-services-ssis-projects-and-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="90bf3-106">For more information, see [Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md).</span></span>  
  
### <a name="to-copy-project-level-items"></a><span data-ttu-id="90bf3-107">Per copiare elementi a livello di progetto</span><span class="sxs-lookup"><span data-stu-id="90bf3-107">To copy project level items</span></span>  
  
1.  <span data-ttu-id="90bf3-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] aprire la soluzione o il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="90bf3-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or solution that you want to work with.</span></span>  
  
2.  <span data-ttu-id="90bf3-109">Espandere il progetto e la cartella contenente l'elemento da copiare.</span><span class="sxs-lookup"><span data-stu-id="90bf3-109">Expand the project and item folder to copy from.</span></span>  
  
3.  <span data-ttu-id="90bf3-110">Fare clic con il pulsante destro del mouse sull'elemento e scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="90bf3-110">Right-click the item and click **Copy**.</span></span>  
  
4.  <span data-ttu-id="90bf3-111">Fare clic con il pulsante destro del mouse sul progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in cui copiare l'elemento e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="90bf3-111">Right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to copy to and click **Paste**.</span></span>  
  
     <span data-ttu-id="90bf3-112">Gli elementi vengono copiati automaticamente nella cartella corretta.</span><span class="sxs-lookup"><span data-stu-id="90bf3-112">The items are automatically copied to the correct folder.</span></span> <span data-ttu-id="90bf3-113">Se gli elementi copiati nel progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] non sono pacchetti, verranno copiati nella cartella **Varie**.</span><span class="sxs-lookup"><span data-stu-id="90bf3-113">If you copy items to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that are not packages, the items are copied to the **Miscellaneous** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90bf3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90bf3-114">See Also</span></span>  
 <span data-ttu-id="90bf3-115">[Integration Services &#40;pacchetti&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="90bf3-115">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="90bf3-116">Copia di oggetti di pacchetto</span><span class="sxs-lookup"><span data-stu-id="90bf3-116">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
  
