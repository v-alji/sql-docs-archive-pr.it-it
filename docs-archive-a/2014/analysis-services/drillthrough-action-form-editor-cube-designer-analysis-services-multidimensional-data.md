---
title: Editor dei form delle azioni drill-through (scheda azioni, Progettazione cubi) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.actionexpression.drillthroughaction.f1
ms.assetid: 225fd818-b5ea-494f-b67b-66e09798274a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 546448bd05f3af45b7093acb2dbb9d1e1a8f1bd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636456"
---
# <a name="drillthrough-action-form-editor-actions-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="e26f8-102">Editor dei form delle azioni drill-through (scheda Azioni, Progettazione cubi) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="e26f8-102">Drillthrough Action Form Editor (Actions Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e26f8-103">Usare il riquadro dell' **editor dei form delle azioni drill-through** nella scheda **Azioni** di Progettazione cubi per modificare l'azione drill-through selezionata nel riquadro **Libreria azioni** .</span><span class="sxs-lookup"><span data-stu-id="e26f8-103">Use the **Drillthrough Action Form Editor** pane on the **Actions** tab in Cube Designer to modify the drillthrough action selected in the **Action Organizer** pane.</span></span> <span data-ttu-id="e26f8-104">Per altre informazioni sulle azioni drill-through, vedere [Azioni &#40;Analysis Services - Dati multidimensionali&41#;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e26f8-104">For more information about drillthrough actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e26f8-105">Le azioni drill-through non eseguono più il drill-down nell'archivio di dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="e26f8-105">Drillthrough actions no longer drill down to the underlying data store.</span></span> <span data-ttu-id="e26f8-106">Le informazioni accessibili dalle azioni drill-through devono essere modellate all'interno del cubo utilizzando membri di dimensione o di gerarchia.</span><span class="sxs-lookup"><span data-stu-id="e26f8-106">The information that drillthrough actions access must be modeled within the cube by using dimension or hierarchy members.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e26f8-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e26f8-107">Options</span></span>  
 <span data-ttu-id="e26f8-108">**nome**</span><span class="sxs-lookup"><span data-stu-id="e26f8-108">**name**</span></span>  
 <span data-ttu-id="e26f8-109">Consente di digitare il nome dell'azione.</span><span class="sxs-lookup"><span data-stu-id="e26f8-109">Type the name of the action.</span></span>  
  
 <span data-ttu-id="e26f8-110">**Destinazione azione**</span><span class="sxs-lookup"><span data-stu-id="e26f8-110">**Action Target**</span></span>  
 <span data-ttu-id="e26f8-111">Espandere questa opzione per visualizzare la casella di riepilogo **Membri gruppo di misure** .</span><span class="sxs-lookup"><span data-stu-id="e26f8-111">Expand to view the **Measure group members** option.</span></span>  
  
 <span data-ttu-id="e26f8-112">**Membri gruppo di misure**</span><span class="sxs-lookup"><span data-stu-id="e26f8-112">**Measure group members**</span></span>  
 <span data-ttu-id="e26f8-113">Consente di selezionare il gruppo di misure al quale associare l'azione drill-through.</span><span class="sxs-lookup"><span data-stu-id="e26f8-113">Select the measure group to which the drillthrough action is to be associated.</span></span>  
  
 <span data-ttu-id="e26f8-114">**Condizione (facoltativa)**</span><span class="sxs-lookup"><span data-stu-id="e26f8-114">**Condition (Optional)**</span></span>  
 <span data-ttu-id="e26f8-115">Immettere l'espressione MDX (Multidimensional Expressions) che descrive una condizione facoltativa, usata in combinazione con l'opzione **Membri gruppo di misure**, che consente di limitare ulteriormente la disponibilità dell'azione.</span><span class="sxs-lookup"><span data-stu-id="e26f8-115">Enter the Multidimensional Expressions (MDX) expression that describes an optional condition, used in conjunction with **Measure group members**, which further restricts when the action is available.</span></span> <span data-ttu-id="e26f8-116">L'espressione deve restituire un valore booleano il quale, se è True, indica che l'azione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e26f8-116">The expression must return a Boolean value that, if true, indicates the action is available.</span></span>  
  
 <span data-ttu-id="e26f8-117">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="e26f8-117">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="e26f8-118">**Colonne drill-through**</span><span class="sxs-lookup"><span data-stu-id="e26f8-118">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="e26f8-119">Espandere questa opzione per visualizzare una griglia nella quale specificare gli attributi restituiti quando l'utente esegue l'azione.</span><span class="sxs-lookup"><span data-stu-id="e26f8-119">Expand to display a grid in which to indicate the attributes that are returned when the user runs this action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e26f8-120">È possibile selezionare più di una dimensione, ma non è possibile utilizzare più di una volta una dimensione in un'azione drill-through.</span><span class="sxs-lookup"><span data-stu-id="e26f8-120">You can select more than one dimension, but no dimension can be used more than once in a drillthrough action.</span></span>  
  
 <span data-ttu-id="e26f8-121">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="e26f8-121">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="e26f8-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="e26f8-122">Column</span></span>|<span data-ttu-id="e26f8-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e26f8-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e26f8-124">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="e26f8-124">**Dimensions**</span></span>|<span data-ttu-id="e26f8-125">Consente di selezionare la dimensione utilizzata per restituire l'attributo.</span><span class="sxs-lookup"><span data-stu-id="e26f8-125">Select the dimension from which the returned attribute is derived.</span></span> <span data-ttu-id="e26f8-126">Selezionare MEASURES per eseguire il drill-through sulle misure.</span><span class="sxs-lookup"><span data-stu-id="e26f8-126">Select MEASURES to drillthrough on measures.</span></span>|  
|<span data-ttu-id="e26f8-127">**Colonne restituite**</span><span class="sxs-lookup"><span data-stu-id="e26f8-127">**Return Columns**</span></span>|<span data-ttu-id="e26f8-128">Consente di selezionare l'attributo o la misura dalla dimensione selezionata da restituire all'esecuzione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="e26f8-128">Select the attribute or measure from the selected dimension to be returned when the action is run.</span></span>|  
  
 <span data-ttu-id="e26f8-129">**Proprietà aggiuntive**</span><span class="sxs-lookup"><span data-stu-id="e26f8-129">**Additional Properties**</span></span>  
 <span data-ttu-id="e26f8-130">Espandere questa opzione per visualizzare le opzioni **Impostazione predefinita**, **Numero massimo di righe**, **Chiamata**, **Applicazione**, **Descrizione**, **Didascalia**e **Didascalia MDX** .</span><span class="sxs-lookup"><span data-stu-id="e26f8-130">Expand to view the **Default**, **Maximum rows**, **Invocation**, **Application**, **Description**, **Caption**, and **Caption Is MDX** options.</span></span>  
  
 <span data-ttu-id="e26f8-131">**Default**</span><span class="sxs-lookup"><span data-stu-id="e26f8-131">**Default**</span></span>  
 <span data-ttu-id="e26f8-132">Selezionare **True** per includere l'azione drill-through attuale come azione predefinita. In caso contrario selezionare **False**.</span><span class="sxs-lookup"><span data-stu-id="e26f8-132">Select **True** to include this drillthrough action as a default drillthrough action, otherwise, select **False**.</span></span>  
  
 <span data-ttu-id="e26f8-133">Se la `RETURN` clausola viene omessa da un' `DRILLTHROUGH` istruzione MDX eseguita da un'applicazione client, l' [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] istanza di valuta tutte le azioni drill-through predefinite ed esegue la prima azione drill-through predefinita che restituisce un set non vuoto.</span><span class="sxs-lookup"><span data-stu-id="e26f8-133">If the `RETURN` clause is omitted from an MDX `DRILLTHROUGH` statement executed by a client application, the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance evaluates all default drillthrough actions and runs the first default drillthrough action that returns a non-empty set.</span></span> <span data-ttu-id="e26f8-134">Per ulteriori informazioni sull'istruzione MDX `DRILLTHROUGH` , vedere [istruzione drill-through &#40;&#41;MDX ](/sql/mdx/mdx-data-manipulation-drillthrough).</span><span class="sxs-lookup"><span data-stu-id="e26f8-134">For more information about the MDX `DRILLTHROUGH` statement, see [DRILLTHROUGH Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-drillthrough).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e26f8-135">Questa opzione viene utilizzata per garantire la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="e26f8-135">This option is used for backwards compatibility purposes.</span></span>  
  
 <span data-ttu-id="e26f8-136">**Numero massimo di righe**</span><span class="sxs-lookup"><span data-stu-id="e26f8-136">**Maximum rows**</span></span>  
 <span data-ttu-id="e26f8-137">Consente di digitare il numero massimo di righe che devono essere restituite dall'azione drill-through.</span><span class="sxs-lookup"><span data-stu-id="e26f8-137">Type the maximum number of rows to be returned by the drillthrough action.</span></span> <span data-ttu-id="e26f8-138">Se si imposta questa opzione a zero o a un valore vuoto l'azione drill-through restituirà all'applicazione client tutte le righe recuperate.</span><span class="sxs-lookup"><span data-stu-id="e26f8-138">Setting this option to zero or an empty value indicates that the drillthrough action returns all rows retrieved by the action to the client application.</span></span>  
  
 <span data-ttu-id="e26f8-139">**Chiamata**</span><span class="sxs-lookup"><span data-stu-id="e26f8-139">**Invocation**</span></span>  
 <span data-ttu-id="e26f8-140">Consente di selezionare l'impostazione che indica quando eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="e26f8-140">Select the setting that indicates when the action should be carried out.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e26f8-141">Questa opzione costituisce solo un'indicazione per un'applicazione client relativa al momento in cui eseguire un'azione e non controlla direttamente la chiamata dell'azione.</span><span class="sxs-lookup"><span data-stu-id="e26f8-141">This option only provides a recommendation to a client application as to when to execute an action, and does not directly control the invocation of the action.</span></span>  
  
 <span data-ttu-id="e26f8-142">Nella tabella seguente vengono descritte le impostazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="e26f8-142">The following table describes the available settings.</span></span>  
  
|<span data-ttu-id="e26f8-143">Valore</span><span class="sxs-lookup"><span data-stu-id="e26f8-143">Value</span></span>|<span data-ttu-id="e26f8-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e26f8-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e26f8-145">Batch</span><span class="sxs-lookup"><span data-stu-id="e26f8-145">Batch</span></span>|<span data-ttu-id="e26f8-146">L'azione deve essere eseguita come parte di un'operazione batch o di un'attività di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e26f8-146">The action should run as part of a batch operation or an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] task.</span></span>|  
|<span data-ttu-id="e26f8-147">Interattività</span><span class="sxs-lookup"><span data-stu-id="e26f8-147">Interactive</span></span>|<span data-ttu-id="e26f8-148">L'azione viene eseguita in seguito alla chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e26f8-148">The action runs when the user invokes the action.</span></span>|  
|<span data-ttu-id="e26f8-149">Su apertura</span><span class="sxs-lookup"><span data-stu-id="e26f8-149">On Open</span></span>|<span data-ttu-id="e26f8-150">L'azione viene eseguita quando il cubo viene aperto per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="e26f8-150">The action runs when the cube is first opened.</span></span>|  
  
 <span data-ttu-id="e26f8-151">**Applicazione**</span><span class="sxs-lookup"><span data-stu-id="e26f8-151">**Application**</span></span>  
 <span data-ttu-id="e26f8-152">Consente di digitare il nome dell'applicazione che può eseguire l'azione drill-through.</span><span class="sxs-lookup"><span data-stu-id="e26f8-152">Type the name of the application that can execute the drillthrough action.</span></span>  
  
 <span data-ttu-id="e26f8-153">È inoltre possibile utilizzare questa opzione per identificare l'applicazione client che utilizza con maggiore frequenza questa azione, oltre a visualizzare icone appropriate accanto all'azione in un menu a comparsa.</span><span class="sxs-lookup"><span data-stu-id="e26f8-153">You can also use this option to identify which client application most commonly uses this action, as well as to display appropriate icons next to the action in a pop-up menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e26f8-154">Questa opzione costituisce solo un'indicazione per un'applicazione client relativa a quale client deve eseguire un'azione e non controlla direttamente l'accesso all'azione.</span><span class="sxs-lookup"><span data-stu-id="e26f8-154">This option only provides a recommendation to a client application as to what client application should execute an action, and does not directly control access to the action.</span></span> <span data-ttu-id="e26f8-155">Nelle applicazioni devono essere nascoste le azioni associate ad altre applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="e26f8-155">Client applications should hide any actions that are associated with other client applications.</span></span>  
  
 <span data-ttu-id="e26f8-156">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e26f8-156">**Description**</span></span>  
 <span data-ttu-id="e26f8-157">Consente di digitare la descrizione facoltativa dell'azione.</span><span class="sxs-lookup"><span data-stu-id="e26f8-157">Type the optional description of the action.</span></span>  
  
 <span data-ttu-id="e26f8-158">**Sottotitolo**</span><span class="sxs-lookup"><span data-stu-id="e26f8-158">**Caption**</span></span>  
 <span data-ttu-id="e26f8-159">Consente di digitare la didascalia da visualizzare per l'azione nell'applicazione client se l'opzione **Didascalia MDX** è impostata su **False**.</span><span class="sxs-lookup"><span data-stu-id="e26f8-159">Type the caption to be displayed for the action in the client application if **Caption Is MDX** is set to **False**.</span></span>  
  
 <span data-ttu-id="e26f8-160">Consente di digitare l'espressione MDX che restituisce una stringa per la didascalia se l'opzione **Didascalia MDX** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="e26f8-160">Type the Multidimensional Expressions (MDX) expression that returns a string for the caption if **Caption Is MDX** is set to **True**.</span></span>  
  
 <span data-ttu-id="e26f8-161">**Didascalia MDX**</span><span class="sxs-lookup"><span data-stu-id="e26f8-161">**Caption Is MDX**</span></span>  
 <span data-ttu-id="e26f8-162">Selezionare **False** per indicare che **Didascalia** contiene una stringa letterale che rappresenta una didascalia da visualizzare per l'azione nell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="e26f8-162">Select **False** to indicate that **Caption** contains a literal string representing a caption to be displayed for the action in the client application.</span></span>  
  
 <span data-ttu-id="e26f8-163">Selezionare **True** per indicare che **Didascalia** contiene un'espressione MDX che restituisce una stringa che rappresenta una didascalia da visualizzare per l'azione nell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="e26f8-163">Select **True** to indicate that **Caption** contains an MDX expression that returns a string representing a caption to be displayed for the action in the client application.</span></span> <span data-ttu-id="e26f8-164">L'espressione MDX deve essere risolta prima che l'azione venga restituita all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="e26f8-164">The MDX expression must be resolved before the action is returned to the client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26f8-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e26f8-165">See Also</span></span>  
 <span data-ttu-id="e26f8-166">[Espressioni multidimensionali &#40;riferimento&#41; MDX](/sql/mdx/multidimensional-expressions-mdx-reference) </span><span class="sxs-lookup"><span data-stu-id="e26f8-166">[Multidimensional Expressions &#40;MDX&#41; Reference](/sql/mdx/multidimensional-expressions-mdx-reference) </span></span>  
 <span data-ttu-id="e26f8-167">[Azioni &#40;Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e26f8-167">[Actions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e26f8-168">[Barra degli strumenti &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e26f8-168">[Toolbar &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e26f8-169">[Libreria azioni &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e26f8-169">[Action Organizer &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e26f8-170">[Strumenti di calcolo &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e26f8-170">[Calculation Tools &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e26f8-171">[Editor dei form delle azioni &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e26f8-171">[Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e26f8-172">Editor dei form delle azioni report &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="e26f8-172">Report Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](report-action-form-editor-cube-designer-analysis-services-multidimensional-data.md)  
  
  
