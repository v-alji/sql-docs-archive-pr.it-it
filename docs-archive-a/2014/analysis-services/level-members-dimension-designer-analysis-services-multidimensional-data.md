---
title: Livello e membri (scheda Esplorazione, Progettazione dimensioni) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.browsertab.levelsandmembers.f1
ms.assetid: 3f61e384-5b4e-4480-a7ed-b408de2fdea7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 21680f00b82b5410e2c7a67122fdcfeb78c999dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727264"
---
# <a name="level-and-members-browser-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="b7623-102">Livello e membri (scheda Esplorazione, Progettazione dimensioni) (Analysis Services – Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="b7623-102">Level and Members (Browser Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b7623-103">Utilizzare questo riquadro per visualizzare i membri della gerarchia e della lingua attualmente selezionate.</span><span class="sxs-lookup"><span data-stu-id="b7623-103">Use this pane to browse the members of the currently selected hierarchy and language.</span></span> <span data-ttu-id="b7623-104">Per selezionare una gerarchia o una lingua da visualizzare, utilizzare le opzioni **Gerarchia** e **Lingua** nel riquadro **Barra degli strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b7623-104">To select a hierarchy or language to browse, use the **Hierarchy** and **Language** options on the **Toolbar** pane.</span></span> <span data-ttu-id="b7623-105">Per altre informazioni sul riquadro Barra degli strumenti, vedere [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b7623-105">For more information about the Toolbar pane, see [Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="writeback-mode"></a><span data-ttu-id="b7623-106">Modalità writeback</span><span class="sxs-lookup"><span data-stu-id="b7623-106">Writeback Mode</span></span>  
 <span data-ttu-id="b7623-107">La funzionalità di questo riquadro cambia se la modalità writeback è abilitata.</span><span class="sxs-lookup"><span data-stu-id="b7623-107">The functionality of this pane changes if writeback mode is enabled.</span></span> <span data-ttu-id="b7623-108">Per abilitare la modalità writeback la dimensione selezionata deve essere abilitata per la scrittura, ovvero la proprietà `WriteEnabled` della dimensione deve essere impostata su True, e la dimensione deve essere distribuita a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7623-108">The selected dimension must be write-enabled (in other words, the `WriteEnabled` property of the dimension must be set to true) and the dimension must be deployed to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance in order to enable writeback mode.</span></span>  
  
 <span data-ttu-id="b7623-109">Per abilitare la modalità writeback, è possibile selezionare **Writeback** nel riquadro **Barra degli strumenti** oppure fare clic con il pulsante destro del mouse nel riquadro dei livelli e dei membri \*\*\*\* e scegliere **Writeback** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b7623-109">To enable writeback mode, you can either select **Writeback** from the **Toolbar** pane, or right-click the **Level and Members** pane and select **Writeback** from the context menu.</span></span>  
  
 <span data-ttu-id="b7623-110">Se la modalità writeback è abilitata è possibile eseguire le azioni aggiuntive seguenti nel riquadro dei livelli e dei membri \*\*\*\* :</span><span class="sxs-lookup"><span data-stu-id="b7623-110">If writeback mode is enabled, you can perform the following additional actions in the **Level and Members** pane:</span></span>  
  
|<span data-ttu-id="b7623-111">Azioni</span><span class="sxs-lookup"><span data-stu-id="b7623-111">To do</span></span>|<span data-ttu-id="b7623-112">Attività svolte</span><span class="sxs-lookup"><span data-stu-id="b7623-112">Perform</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="b7623-113">Creare membri di pari livello e membri figlio nella gerarchia selezionata.</span><span class="sxs-lookup"><span data-stu-id="b7623-113">Create sibling and child members within the selected hierarchy.</span></span>|<span data-ttu-id="b7623-114">Fare clic con il pulsante destro del mouse sul membro selezionato e scegliere **Crea elemento di pari livello**, per creare un membro di pari livello, o **Crea elemento figlio**, per creare un membro figlio, dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="b7623-114">Right-click the selected member and select either **Create Sibling**, to create a sibling member, or **Create Child**, to create a child member, from the context menu.</span></span>|  
|<span data-ttu-id="b7623-115">Spostare un membro selezionato a un livello superiore o inferiore della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="b7623-115">Move a selected member up or down the hierarchy.</span></span>|<span data-ttu-id="b7623-116">Trascinare il membro selezionato sul membro padre o figlio corretto, oppure fare clic su **Aumenta rientro** o su **Riduci rientro** nel riquadro **Barra degli strumenti** per spostare il membro selezionato a un livello superiore o inferiore della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="b7623-116">Either drag the selected member to the appropriate parent or child member, or click **Increase Indent** or **Decrease Indent** on the **Toolbar** pane to move the selected member up or down the levels of the hierarchy.</span></span>|  
|<span data-ttu-id="b7623-117">Rinominare un membro selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7623-117">Rename a selected member.</span></span>|<span data-ttu-id="b7623-118">Fare clic con il pulsante destro del mouse sul membro selezionato e scegliere **Rinomina**. In alternativa, fare clic su un membro già selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7623-118">Either right-click the selected member and select **Rename**, or click an already-selected member.</span></span>|  
|<span data-ttu-id="b7623-119">Modificare i valori delle proprietà dei membri.</span><span class="sxs-lookup"><span data-stu-id="b7623-119">Edit member property values</span></span>|<span data-ttu-id="b7623-120">Fare doppio clic sul valore della proprietà selezionata del membro selezionato per modificare tale valore.</span><span class="sxs-lookup"><span data-stu-id="b7623-120">Double-click the value in the selected member property for the selected member to edit the value.</span></span>|  
  
## <a name="options"></a><span data-ttu-id="b7623-121">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b7623-121">Options</span></span>  
 <span data-ttu-id="b7623-122">**Livello corrente**</span><span class="sxs-lookup"><span data-stu-id="b7623-122">**Current level**</span></span>  
 <span data-ttu-id="b7623-123">Consente di visualizzare il livello a cui appartiene il membro attualmente selezionato in **Albero** .</span><span class="sxs-lookup"><span data-stu-id="b7623-123">Displays the level to which the currently selected member in **Tree** belongs.</span></span>  
  
 <span data-ttu-id="b7623-124">**Albero**</span><span class="sxs-lookup"><span data-stu-id="b7623-124">**Tree**</span></span>  
 <span data-ttu-id="b7623-125">Consente di visualizzare i membri della gerarchia e della lingua attualmente selezionate.</span><span class="sxs-lookup"><span data-stu-id="b7623-125">Displays the members of the currently selected hierarchy and language.</span></span>  
  
 <span data-ttu-id="b7623-126">Se le proprietà membro vengono selezionate dall'opzione **Proprietà membro** del riquadro Barra degli strumenti, ogni proprietà membro viene visualizzata come colonna.</span><span class="sxs-lookup"><span data-stu-id="b7623-126">If member properties are selected from the **Member Properties** option of the Toolbar pane, each member property is displayed as a column.</span></span>  
  
 <span data-ttu-id="b7623-127">Se la modalità writeback è abilitata, viene visualizzata una colonna per ogni colonna chiave associata all'attributo chiave nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="b7623-127">If writeback mode is enabled, one column for each key column associated with the key attribute in the dimension is displayed.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="b7623-128">Menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="b7623-128">Context Menu</span></span>  
 <span data-ttu-id="b7623-129">Le opzioni seguenti sono disponibili nel menu di scelta rapida visualizzato facendo clic con il pulsante destro del mouse su qualsiasi parte del riquadro dei livelli e dei membri \*\*\*\* per il membro selezionato:</span><span class="sxs-lookup"><span data-stu-id="b7623-129">The following options are available in the context menu displayed by right-clicking any part of the **Level and Members** pane for the selected member:</span></span>  
  
 <span data-ttu-id="b7623-130">**Crea elemento di pari livello**</span><span class="sxs-lookup"><span data-stu-id="b7623-130">**Create sibling**</span></span>  
 <span data-ttu-id="b7623-131">Consente di creare un nuovo membro allo stesso livello del membro selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7623-131">Creates a new member at the same level as the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-132">Questa opzione è disponibile solo se è selezionato un membro a un livello diverso dal livello Totale.</span><span class="sxs-lookup"><span data-stu-id="b7623-132">This option is enabled only if a member at a level other than the (All) level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-133">Questa opzione viene visualizzata solo se è abilitata la modalità writeback.</span><span class="sxs-lookup"><span data-stu-id="b7623-133">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="b7623-134">**Crea elemento figlio**</span><span class="sxs-lookup"><span data-stu-id="b7623-134">**Create child**</span></span>  
 <span data-ttu-id="b7623-135">Consente di creare un nuovo membro al livello immediatamente inferiore a quello del membro selezionato, come elemento figlio del membro selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7623-135">Creates a new member at the next lower level as the selected member, as a child of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-136">Questa opzione è disponibile solo se è selezionato un membro a un livello diverso da quello più basso.</span><span class="sxs-lookup"><span data-stu-id="b7623-136">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-137">Questa opzione viene visualizzata solo se è abilitata la modalità writeback.</span><span class="sxs-lookup"><span data-stu-id="b7623-137">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="b7623-138">**Taglia**</span><span class="sxs-lookup"><span data-stu-id="b7623-138">**Cut**</span></span>  
 <span data-ttu-id="b7623-139">Consente di copiare i membri selezionati negli Appunti e di rimuoverli dalla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="b7623-139">Copies the selected members to the clipboard and removes them from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-140">Questa opzione è disponibile solo se è selezionato un membro diverso dal membro Totale.</span><span class="sxs-lookup"><span data-stu-id="b7623-140">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-141">Questa opzione viene visualizzata solo se è abilitata la modalità writeback.</span><span class="sxs-lookup"><span data-stu-id="b7623-141">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="b7623-142">**Incolla**</span><span class="sxs-lookup"><span data-stu-id="b7623-142">**Paste**</span></span>  
 <span data-ttu-id="b7623-143">Consente di incollare i membri precedentemente rimossi usando **Taglia** immediatamente dopo il membro selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7623-143">Pastes members previously removed using **Cut** immediately after the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-144">Questa opzione viene visualizzata solo se è abilitata la modalità writeback.</span><span class="sxs-lookup"><span data-stu-id="b7623-144">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="b7623-145">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="b7623-145">**Delete**</span></span>  
 <span data-ttu-id="b7623-146">Consente di rimuovere i membri selezionati dalla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="b7623-146">Removes the selected members from the hierarchy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-147">Questa opzione è disponibile solo se è selezionato un membro diverso dal membro Totale.</span><span class="sxs-lookup"><span data-stu-id="b7623-147">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-148">Questa opzione viene visualizzata solo se è abilitata la modalità writeback.</span><span class="sxs-lookup"><span data-stu-id="b7623-148">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="b7623-149">**Rinominare**</span><span class="sxs-lookup"><span data-stu-id="b7623-149">**Rename**</span></span>  
 <span data-ttu-id="b7623-150">Selezionare questa opzione per modificare il nome del membro selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7623-150">Select to edit the name of the selected member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-151">Questa opzione è disponibile solo se è selezionato un membro diverso dal membro Totale.</span><span class="sxs-lookup"><span data-stu-id="b7623-151">This option is enabled only if a member other than the All member is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-152">Questa opzione viene visualizzata solo se è abilitata la modalità writeback.</span><span class="sxs-lookup"><span data-stu-id="b7623-152">This option is displayed only if writeback mode is enabled.</span></span>  
  
 <span data-ttu-id="b7623-153">**Filtra membri**</span><span class="sxs-lookup"><span data-stu-id="b7623-153">**Filter Members**</span></span>  
 <span data-ttu-id="b7623-154">Consente di visualizzare la finestra di dialogo **Filtra membri** e filtrare i membri visualizzati nel riquadro dei livelli e dei membri \*\*\*\* per la gerarchia selezionata.</span><span class="sxs-lookup"><span data-stu-id="b7623-154">Displays the **Filter Members** dialog box to filter members displayed in **Level and Members** for the selected hierarchy.</span></span> <span data-ttu-id="b7623-155">Per altre informazioni sulla finestra di dialogo **Filtra membri** vedere [Finestra di dialogo Filtra membri &#40;Analysis Services - Dati multidimensionali&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b7623-155">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="b7623-156">**Espandi tutto**</span><span class="sxs-lookup"><span data-stu-id="b7623-156">**Expand All**</span></span>  
 <span data-ttu-id="b7623-157">Consente di espandere tutti i membri contenuti in **Albero**.</span><span class="sxs-lookup"><span data-stu-id="b7623-157">Expands all members in **Tree**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7623-158">Questa opzione è disponibile solo se è selezionato un membro a un livello diverso da quello più basso.</span><span class="sxs-lookup"><span data-stu-id="b7623-158">This option is enabled only if a member at a level other than the lowest level is selected.</span></span>  
  
 <span data-ttu-id="b7623-159">**Comprimi tutto**</span><span class="sxs-lookup"><span data-stu-id="b7623-159">**Collapse All**</span></span>  
 <span data-ttu-id="b7623-160">Consente di comprimere tutti i membri contenuti in **Albero**.</span><span class="sxs-lookup"><span data-stu-id="b7623-160">Collapse all members in **Tree**.</span></span>  
  
 <span data-ttu-id="b7623-161">**Espandi membro**</span><span class="sxs-lookup"><span data-stu-id="b7623-161">**Expand Member**</span></span>  
 <span data-ttu-id="b7623-162">Consente di espandere il membro selezionato in **Albero**.</span><span class="sxs-lookup"><span data-stu-id="b7623-162">Expand the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="b7623-163">**Comprimi membro**</span><span class="sxs-lookup"><span data-stu-id="b7623-163">**Collapse Member**</span></span>  
 <span data-ttu-id="b7623-164">Consente di comprimere il membro selezionato in **Albero**.</span><span class="sxs-lookup"><span data-stu-id="b7623-164">Collapse the selected member in **Tree**.</span></span>  
  
 <span data-ttu-id="b7623-165">**Writeback**</span><span class="sxs-lookup"><span data-stu-id="b7623-165">**Writeback**</span></span>  
 <span data-ttu-id="b7623-166">Selezionare questa opzione per abilitare la modalità writeback.</span><span class="sxs-lookup"><span data-stu-id="b7623-166">Select to enable writeback mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7623-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7623-167">See Also</span></span>  
 <span data-ttu-id="b7623-168">[Barra degli strumenti &#40;scheda Esplorazione, Progettazione dimensioni&#41; &#40;Analysis Services Dati multidimensionali&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b7623-168">[Toolbar &#40;Browser Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b7623-169">Browser &#40;Progettazione dimensioni&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="b7623-169">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
