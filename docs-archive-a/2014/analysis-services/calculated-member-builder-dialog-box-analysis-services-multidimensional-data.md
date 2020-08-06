---
title: Finestra di dialogo Generatore membri calcolati (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.calculatedmemberbuilderdialog.f1
ms.assetid: 73b89a9f-f403-4ab8-99f7-e3ceb870c260
author: minewiskan
ms.author: owend
ms.openlocfilehash: 240e2f2471bf77c403119fd51278a975badc8358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625799"
---
# <a name="calculated-member-builder-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="ced2e-102">Finestra di dialogo Generatore membri calcolati (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="ced2e-102">Calculated Member Builder Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ced2e-103">Utilizzare la finestra di dialogo **Generatore membri calcolati** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per compilare un membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="ced2e-103">Use the **Calculated Member Builder** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to build a calculated member.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ced2e-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ced2e-104">Options</span></span>  
  
|<span data-ttu-id="ced2e-105">Termine</span><span class="sxs-lookup"><span data-stu-id="ced2e-105">Term</span></span>|<span data-ttu-id="ced2e-106">Definizione</span><span class="sxs-lookup"><span data-stu-id="ced2e-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="ced2e-107">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ced2e-107">**Name**</span></span>|<span data-ttu-id="ced2e-108">Consente di digitare il nome del membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="ced2e-108">Type the name of the calculated member.</span></span>|  
|<span data-ttu-id="ced2e-109">**Gerarchia padre**</span><span class="sxs-lookup"><span data-stu-id="ced2e-109">**Parent Hierarchy**</span></span>|<span data-ttu-id="ced2e-110">Consente di selezionare la gerarchia in cui creare il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="ced2e-110">Select the hierarchy in which to create the calculated member.</span></span>|  
|<span data-ttu-id="ced2e-111">**Membro padre**</span><span class="sxs-lookup"><span data-stu-id="ced2e-111">**Parent Member**</span></span>|<span data-ttu-id="ced2e-112">Questa opzione è abilitata se si seleziona una gerarchia padre, diversa dalla dimensione `Measures`, che include più di un livello.</span><span class="sxs-lookup"><span data-stu-id="ced2e-112">This option is enabled if you select a parent hierarchy (other than the `Measures` dimension) that has more than one level.</span></span> <span data-ttu-id="ced2e-113">Fare clic sul pulsante con i puntini di sospensione (**...**) per selezionare un membro padre.</span><span class="sxs-lookup"><span data-stu-id="ced2e-113">Click the ellipsis (**...**) button to select a parent member.</span></span> <span data-ttu-id="ced2e-114">Il membro padre determina la posizione del membro calcolato nella struttura della dimensione.</span><span class="sxs-lookup"><span data-stu-id="ced2e-114">The parent member determines the location of the calculated member in the dimension structure.</span></span>|  
|<span data-ttu-id="ced2e-115">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="ced2e-115">**Expression**</span></span>|<span data-ttu-id="ced2e-116">Consente di digitare l'espressione MDX da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ced2e-116">Type the MDX expression that will be used.</span></span>|  
|<span data-ttu-id="ced2e-117">**Controllo**</span><span class="sxs-lookup"><span data-stu-id="ced2e-117">**Check**</span></span>|<span data-ttu-id="ced2e-118">Fare clic su **Controlla** per verificare l'espressione MDX definita in **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-118">Click **Check** to test the MDX expression defined in **Expression**.</span></span>|  
|<span data-ttu-id="ced2e-119">**Metadata**</span><span class="sxs-lookup"><span data-stu-id="ced2e-119">**Metadata**</span></span>|<span data-ttu-id="ced2e-120">Visualizza i metadati relativi all'oggetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] corrente che è possibile includere nell'espressione MDX definita in **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-120">Displays metadata for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object that can be included in the MDX expression defined in **Expression**.</span></span><br /><br /> <span data-ttu-id="ced2e-121">È possibile copiare la sintassi MDX per l'elemento selezionato facendo clic con il pulsante destro del mouse sull'elemento e scegliendo **Copia**oppure trascinando l'elemento selezionato in **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-121">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
|<span data-ttu-id="ced2e-122">**Funzioni**</span><span class="sxs-lookup"><span data-stu-id="ced2e-122">**Functions**</span></span>|<span data-ttu-id="ced2e-123">Consente di visualizzare le funzioni MDX disponibili per l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] corrente.</span><span class="sxs-lookup"><span data-stu-id="ced2e-123">Displays the available MDX functions for the current [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="ced2e-124">Gli elementi elencati sono recuperati dal set di righe dello schema MDSCHEMA_FUNCTIONS.</span><span class="sxs-lookup"><span data-stu-id="ced2e-124">The items listed are retrieved from the MDSCHEMA_FUNCTIONS schema rowset.</span></span><br /><br /> <span data-ttu-id="ced2e-125">È possibile copiare la sintassi MDX per l'elemento selezionato facendo clic con il pulsante destro del mouse sull'elemento e scegliendo **Copia**oppure trascinando l'elemento selezionato in **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="ced2e-125">You can copy the MDX syntax for the selected item by right-clicking the item and selecting **Copy**, or by dragging the selected item to **Expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ced2e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ced2e-126">See Also</span></span>  
 [<span data-ttu-id="ced2e-127">Guida di riferimento a MDX &#40;Multidimensional Expressions&#41;</span><span class="sxs-lookup"><span data-stu-id="ced2e-127">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
