---
title: Generatore MDX (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.mdxbuilderdialof.f1
helpviewer_keywords:
- MDX Builder dialog box
ms.assetid: fecbf093-65ea-4e1b-b637-f04876f1cb0f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 391f4abe953184470be60cca41d53ee20e965423
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629648"
---
# <a name="mdx-builder-analysis-services---multidimensional-data"></a><span data-ttu-id="7edcd-102">Generatore MDX (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="7edcd-102">MDX Builder (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="7edcd-103">Usare la finestra di dialogo **Generatore MDX** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] o in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per compilare un'espressione MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="7edcd-103">Use the **MDX Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to build a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="7edcd-104">Per visualizzare la finestra di dialogo **Generatore MDX** , fare clic sul pulsante con i puntini di sospensione (**...**) **per l'opzione** **Consenti lettura del contenuto del cubo** , l'opzione **Consenti lettura del contenuto delle celle** per la sicurezza della cella o l'opzione **Consenti lettura e scrittura del contenuto del cubo** nella pagina **dati cella** di **Progettazione ruoli**.</span><span class="sxs-lookup"><span data-stu-id="7edcd-104">You can display the **MDX Builder** dialog box by clicking the **Edit MDX** ellipsis button (**...**) for the **Allow reading of cube content** option, the **Allow reading of cell content contingent on cell security** option, or the **Allow reading and writing of cube content** option on the **Cell Data** page of **Role Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7edcd-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7edcd-105">Options</span></span>  
  
|<span data-ttu-id="7edcd-106">Termine</span><span class="sxs-lookup"><span data-stu-id="7edcd-106">Term</span></span>|<span data-ttu-id="7edcd-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="7edcd-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="7edcd-108">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="7edcd-108">**Expression**</span></span>|<span data-ttu-id="7edcd-109">Consente di digitare l'espressione MDX da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7edcd-109">Type the MDX expression to be used.</span></span>|  
|<span data-ttu-id="7edcd-110">**Controllo**</span><span class="sxs-lookup"><span data-stu-id="7edcd-110">**Check**</span></span>|<span data-ttu-id="7edcd-111">Fare clic su **Controlla** per verificare l'espressione MDX definita in **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="7edcd-111">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="7edcd-112">**Metadata**</span><span class="sxs-lookup"><span data-stu-id="7edcd-112">**Metadata**</span></span>|<span data-ttu-id="7edcd-113">Visualizza i metadati relativi all'oggetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] corrente che è possibile includere nell'espressione MDX definita in **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="7edcd-113">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="7edcd-114">È possibile copiare la sintassi MDX relativa all'elemento selezionato facendo clic con il pulsante destro del mouse sull'elemento e scegliendo **Copia** dal menu di scelta rapida oppure trascinando l'elemento selezionato in **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="7edcd-114">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="7edcd-115">**Funzioni**</span><span class="sxs-lookup"><span data-stu-id="7edcd-115">**Functions**</span></span>|<span data-ttu-id="7edcd-116">Consente di visualizzare le funzioni MDX disponibili per l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] corrente.</span><span class="sxs-lookup"><span data-stu-id="7edcd-116">Displays available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="7edcd-117">Gli elementi elencati sono recuperati dal set di righe dello schema MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="7edcd-117">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="7edcd-118">È possibile copiare la sintassi MDX relativa all'elemento selezionato facendo clic con il pulsante destro del mouse sull'elemento e scegliendo **Copia** dal menu di scelta rapida oppure trascinando l'elemento selezionato in **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="7edcd-118">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy** from the context menu, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7edcd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7edcd-119">See Also</span></span>  
 <span data-ttu-id="7edcd-120">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="7edcd-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 <span data-ttu-id="7edcd-121">[Dati delle celle &#40;Progettazione ruoli&#41; &#40;Analysis Services Dati multidimensionali&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="7edcd-121">[Cell Data &#40;Role Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](https://msdn.microsoft.com/library/ms177279(v=sql.120).aspx)</span></span>  
  
  
