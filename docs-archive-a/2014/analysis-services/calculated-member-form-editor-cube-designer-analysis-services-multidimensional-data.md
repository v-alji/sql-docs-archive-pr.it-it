---
title: Editor form membro calcolato (scheda calcoli, Progettazione cubi) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationexpression.calculatedmember.f1
ms.assetid: f7719b9e-b1e6-4792-90a6-30d9d8eb1196
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dd45ece03fd81e0e7356e7bdcd0ec8dc53287bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625797"
---
# <a name="calculated-member-form-editor-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="0704b-102">Editor form membro calcolato (scheda Calcoli, Progettazione cubi) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="0704b-102">Calculated Member Form Editor (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="0704b-103">Il riquadro **Editor form membro calcolato** nella scheda **Calcoli** di Progettazione cubi consente di creare o modificare un membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-103">Use the **Calculated Member Form Editor** pane on the **Calculations** tab in Cube Designer to create or modify a calculated member.</span></span>  
  
 <span data-ttu-id="0704b-104">**Nota** Questo riquadro viene visualizzato solo nella visualizzazione Form.</span><span class="sxs-lookup"><span data-stu-id="0704b-104">**Note** This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0704b-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0704b-105">Options</span></span>  
 <span data-ttu-id="0704b-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0704b-106">**Name**</span></span>  
 <span data-ttu-id="0704b-107">Consente di digitare il nome del membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-107">Type the name of the calculated member.</span></span>  
  
 <span data-ttu-id="0704b-108">**Proprietà padre**</span><span class="sxs-lookup"><span data-stu-id="0704b-108">**Parent Properties**</span></span>  
 <span data-ttu-id="0704b-109">Espandere la finestra per visualizzare le opzioni **Gerarchia padre**, **Membro padre**e **Cambia** .</span><span class="sxs-lookup"><span data-stu-id="0704b-109">Expand to view the **Parent hierarchy**, **Parent member**, and **Change** options.</span></span>  
  
 <span data-ttu-id="0704b-110">**Gerarchia padre**</span><span class="sxs-lookup"><span data-stu-id="0704b-110">**Parent hierarchy**</span></span>  
 <span data-ttu-id="0704b-111">Consente di selezionare la dimensione e la gerarchia nel cubo selezionato che dovrà includere il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-111">Select the dimension and hierarchy in the selected cube that is to include the calculated member.</span></span> <span data-ttu-id="0704b-112">Selezionare MEASURES per definire una misura calcolata.</span><span class="sxs-lookup"><span data-stu-id="0704b-112">Select MEASURES to define a calculated measure.</span></span>  
  
 <span data-ttu-id="0704b-113">**Membro padre**</span><span class="sxs-lookup"><span data-stu-id="0704b-113">**Parent member**</span></span>  
 <span data-ttu-id="0704b-114">Consente di selezionare il membro sotto cui verrà visualizzato il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-114">Select the member beneath which the calculated member is to appear.</span></span>  
  
 <span data-ttu-id="0704b-115">**Nota** Questa opzione è disponibile se **Gerarchia padre** specifica una gerarchia diversa da MEASURES.</span><span class="sxs-lookup"><span data-stu-id="0704b-115">**Note** This option is available if **Parent hierarchy** specifies a hierarchy other than MEASURES.</span></span>  
  
 <span data-ttu-id="0704b-116">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="0704b-116">**Change**</span></span>  
 <span data-ttu-id="0704b-117">Selezionare questa opzione per visualizzare la finestra di dialogo **Seleziona membro padre** e scegliere un membro per **Membro padre**.</span><span class="sxs-lookup"><span data-stu-id="0704b-117">Select to display the **Select Parent Member** dialog box and choose a member for **Parent member**.</span></span> <span data-ttu-id="0704b-118">Per altre informazioni sulla finestra di dialogo **Seleziona membro padre**, vedere [Finestra di dialogo Seleziona membro padre &#40;Analysis Services - Dati multidimensionali&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="0704b-118">For more information about the **Select Parent Member** dialog box, see [Select Parent Member Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="0704b-119">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="0704b-119">**Expression**</span></span>  
 <span data-ttu-id="0704b-120">Espandere la finestra per visualizzare o modificare l'espressione MDX per il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-120">Expand to view or edit the Multidimensional Expressions (MDX) expression for the calculated member.</span></span>  
  
 <span data-ttu-id="0704b-121">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="0704b-121">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0704b-122">È consigliabile che questa espressione restituisca una stringa o un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="0704b-122">It is recommended that this expression evaluate to a string or to a numeric value.</span></span>  
  
 <span data-ttu-id="0704b-123">**Proprietà aggiuntive**</span><span class="sxs-lookup"><span data-stu-id="0704b-123">**Additional Properties**</span></span>  
 <span data-ttu-id="0704b-124">Espandere la finestra per visualizzare le opzioni **Stringa di formato**, **Visibile**, **Gestione NON EMPTY**, **Espressioni colori**ed **Espressioni caratteri** .</span><span class="sxs-lookup"><span data-stu-id="0704b-124">Expand to view the **Format string**, **Visible**, **Non-empty behavior**, **Color Expressions**, and **Font Expressions** options.</span></span>  
  
 <span data-ttu-id="0704b-125">**Stringa di formato**</span><span class="sxs-lookup"><span data-stu-id="0704b-125">**Format string**</span></span>  
 <span data-ttu-id="0704b-126">Consente di digitare la stringa di formato MDX utilizzata per formattare il valore restituito dal membro calcolato oppure di selezionare una stringa di formato predefinita.</span><span class="sxs-lookup"><span data-stu-id="0704b-126">Type the MDX format string used to format the value returned by the calculated member, or select a predefined format string.</span></span>  
  
 <span data-ttu-id="0704b-127">Per altre informazioni sulle stringhe di formato MDX, vedere [Contenuto di FORMAT_STRING &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span><span class="sxs-lookup"><span data-stu-id="0704b-127">For more information about MDX format strings, see [FORMAT_STRING Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span></span>  
  
 <span data-ttu-id="0704b-128">**Visibile**</span><span class="sxs-lookup"><span data-stu-id="0704b-128">**Visible**</span></span>  
 <span data-ttu-id="0704b-129">Selezionare **True** per consentire la visualizzazione del membro calcolato alle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="0704b-129">Select **True** to allow the calculated member to be visible to client applications.</span></span>  
  
 <span data-ttu-id="0704b-130">**Comportamento non vuoto**</span><span class="sxs-lookup"><span data-stu-id="0704b-130">**Non-empty behavior**</span></span>  
 <span data-ttu-id="0704b-131">Consente di selezionare il nome della misura utilizzata per risolvere le query NON EMPTY in formato MDX per il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-131">Select the name of the measure used to resolve NON EMPTY queries in MDX for the calculated member.</span></span> <span data-ttu-id="0704b-132">Se la proprietà **Gestione NON EMPTY** è vuota, il membro calcolato dovrà essere valutato più volte per determinare se un membro è vuoto.</span><span class="sxs-lookup"><span data-stu-id="0704b-132">If the **Non Empty Behavior** property is blank, the calculated member must be evaluated repeatedly to determine if a member is empty.</span></span> <span data-ttu-id="0704b-133">Se la proprietà **Gestione NON EMPTY** contiene il nome di una misura, il membro calcolato verrà considerato vuoto nel caso in cui la misura specificata sia vuota.</span><span class="sxs-lookup"><span data-stu-id="0704b-133">If the **Non Empty Behavior** property contains the name of a measure, the calculated member is treated as empty if the specified measure is empty.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0704b-134">Questa proprietà è deprecata.</span><span class="sxs-lookup"><span data-stu-id="0704b-134">This property is deprecated.</span></span> <span data-ttu-id="0704b-135">Evitare di impostarla.</span><span class="sxs-lookup"><span data-stu-id="0704b-135">Avoid setting it.</span></span> <span data-ttu-id="0704b-136">Per informazioni dettagliate, vedere [deprecated Analysis Services features in SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) .</span><span class="sxs-lookup"><span data-stu-id="0704b-136">See [Deprecated Analysis Services Features in SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) for details.</span></span>  
  
 <span data-ttu-id="0704b-137">**Espressioni colori**</span><span class="sxs-lookup"><span data-stu-id="0704b-137">**Color Expressions**</span></span>  
 <span data-ttu-id="0704b-138">Espandere la finestra per visualizzare le opzioni **Colore primo piano** e **Colore sfondo** .</span><span class="sxs-lookup"><span data-stu-id="0704b-138">Expand to view the **Fore color** and **Back color** options.</span></span>  
  
 <span data-ttu-id="0704b-139">**Colore primo piano**</span><span class="sxs-lookup"><span data-stu-id="0704b-139">**Fore color**</span></span>  
 <span data-ttu-id="0704b-140">Consente di digitare l'espressione MDX che offre il colore di primo piano del membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-140">Type the MDX expression that provides the foreground color of the calculated member.</span></span>  
  
 <span data-ttu-id="0704b-141">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="0704b-141">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0704b-142">Fare clic sul pulsante di selezione del colore per visualizzare la finestra di dialogo **Colore** e inserire il valore RGB (Red-Green-Blue) relativo a un colore specificato nell'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="0704b-142">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="0704b-143">Per altre informazioni sui valori RGB, vedere [Contenuto di FORE_COLOR e BACK_COLOR &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="0704b-143">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="0704b-144">**Colore sfondo**</span><span class="sxs-lookup"><span data-stu-id="0704b-144">**Back color**</span></span>  
 <span data-ttu-id="0704b-145">Consente di digitare l'espressione MDX che offre il colore di sfondo del membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-145">Type the MDX expression that provides the background color of the calculated member.</span></span>  
  
 <span data-ttu-id="0704b-146">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="0704b-146">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0704b-147">Fare clic sul pulsante di selezione del colore per visualizzare la finestra di dialogo **Colore** e inserire il valore RGB (Red-Green-Blue) relativo a un colore specificato nell'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="0704b-147">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="0704b-148">Per altre informazioni sui valori RGB, vedere [Contenuto di FORE_COLOR e BACK_COLOR &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="0704b-148">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="0704b-149">**Espressioni caratteri**</span><span class="sxs-lookup"><span data-stu-id="0704b-149">**Font Expressions**</span></span>  
 <span data-ttu-id="0704b-150">Espandere la finestra per visualizzare le opzioni **Tipo carattere**, **Dimensione carattere**e **Flag carattere** .</span><span class="sxs-lookup"><span data-stu-id="0704b-150">Expand to view the **Font name**, **Font size**, and **Font flags** options.</span></span>  
  
 <span data-ttu-id="0704b-151">**Nome carattere**</span><span class="sxs-lookup"><span data-stu-id="0704b-151">**Font name**</span></span>  
 <span data-ttu-id="0704b-152">Consente di digitare l'espressione MDX che offre il nome del carattere utilizzato per il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-152">Type the MDX expression that provides the name of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="0704b-153">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="0704b-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0704b-154">Fare clic sul pulsante di selezione del carattere per visualizzare la finestra di dialogo **Carattere** e inserire i valori di proprietà relativi a un carattere specificato nell'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="0704b-154">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="0704b-155">Per altre informazioni sui valori delle proprietà, vedere [Creazione e utilizzo di valori di proprietà &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="0704b-155">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="0704b-156">**Dimensioni del carattere**</span><span class="sxs-lookup"><span data-stu-id="0704b-156">**Font size**</span></span>  
 <span data-ttu-id="0704b-157">Consente di digitare l'espressione MDX che offre le dimensioni del carattere utilizzato per il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-157">Type the MDX expression that provides the size of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="0704b-158">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="0704b-158">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0704b-159">Fare clic sul pulsante di selezione del carattere per visualizzare la finestra di dialogo **Carattere** e inserire i valori di proprietà relativi a un carattere specificato nell'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="0704b-159">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="0704b-160">Per altre informazioni sui valori delle proprietà, vedere [Creazione e utilizzo di valori di proprietà &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="0704b-160">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="0704b-161">**Flag carattere**</span><span class="sxs-lookup"><span data-stu-id="0704b-161">**Font flags**</span></span>  
 <span data-ttu-id="0704b-162">Consente di digitare l'espressione MDX che offre il valore bitmap contenente i flag, quali sottolineato o grassetto, del carattere utilizzato per il membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="0704b-162">Type the MDX expression that provides the bitmapped value containing the font flags, such as underline or bold, of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="0704b-163">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="0704b-163">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="0704b-164">Fare clic sul pulsante di selezione del carattere per visualizzare la finestra di dialogo **Carattere** e inserire i valori di proprietà relativi a un carattere specificato nell'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="0704b-164">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="0704b-165">Per altre informazioni sui valori delle proprietà, vedere [Creazione e utilizzo di valori di proprietà &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="0704b-165">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0704b-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0704b-166">See Also</span></span>  
 <span data-ttu-id="0704b-167">[Calcoli](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="0704b-167">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="0704b-168">[Creazione di membri calcolati](multidimensional-models/create-calculated-members.md) </span><span class="sxs-lookup"><span data-stu-id="0704b-168">[Create Calculated Members](multidimensional-models/create-calculated-members.md) </span></span>  
 <span data-ttu-id="0704b-169">[Progettazione cubi &#40;Analysis Services-Dati multidimensionali&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0704b-169">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0704b-170">[Calcoli &#40;Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0704b-170">[Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0704b-171">[Barra degli strumenti &#40;scheda calcoli, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0704b-171">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0704b-172">[Libreria script &#40;scheda calcoli, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0704b-172">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0704b-173">[Strumenti di calcolo &#40;scheda calcoli, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0704b-173">[Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="0704b-174">[Editor form set denominato &#40;scheda calcoli, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0704b-174">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="0704b-175">Editor di script &#40;scheda calcoli, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="0704b-175">Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
