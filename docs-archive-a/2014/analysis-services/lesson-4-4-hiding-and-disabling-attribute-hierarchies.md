---
title: Nascondere e disabilitare le gerarchie degli attributi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095039c2-7104-414c-a9a6-327b03ce79df
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc043c68d2a83424a14707799fd90bf893abc12d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726312"
---
# <a name="hiding-and-disabling-attribute-hierarchies"></a><span data-ttu-id="63bd4-102">Come nascondere e disabilitare le gerarchie degli attributi</span><span class="sxs-lookup"><span data-stu-id="63bd4-102">Hiding and Disabling Attribute Hierarchies</span></span>
  <span data-ttu-id="63bd4-103">Per impostazione predefinita, una gerarchia dell'attributo viene creata per ogni attributo di una dimensione e ogni gerarchia è disponibile per il dimensionamento dei dati delle tabelle dei fatti.</span><span class="sxs-lookup"><span data-stu-id="63bd4-103">By default, an attribute hierarchy is created for every attribute in a dimension, and each hierarchy is available for dimensioning fact data.</span></span> <span data-ttu-id="63bd4-104">Questa gerarchia include un livello Totale e un livello di dettaglio contenente tutti i membri della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="63bd4-104">This hierarchy consists of an "All" level and a detail level containing all members of the hierarchy.</span></span> <span data-ttu-id="63bd4-105">Come illustrato in precedenza, è possibile organizzare gli attributi in gerarchie definite dall'utente per offrire percorsi di navigazione in un cubo.</span><span class="sxs-lookup"><span data-stu-id="63bd4-105">As you have already learned, you can organize attributes into user-defined hierarchies to provide navigation paths in a cube.</span></span> <span data-ttu-id="63bd4-106">In alcuni casi è possibile disabilitare o nascondere determinati attributi o le rispettive gerarchie.</span><span class="sxs-lookup"><span data-stu-id="63bd4-106">Under certain circumstances, you may want to disable or hide some attributes and their hierarchies.</span></span> <span data-ttu-id="63bd4-107">Alcuni attributi, ad esempio i numeri della previdenza sociale o il codice fiscale, le retribuzioni, le date di nascita e le informazioni di accesso non sono attributi in base ai quali gli utenti dimensionano le informazioni sul cubo.</span><span class="sxs-lookup"><span data-stu-id="63bd4-107">For example, certain attributes such as social security numbers or national identification numbers, pay rates, birth dates, and login information are not attributes by which users will dimension cube information.</span></span> <span data-ttu-id="63bd4-108">Queste informazioni vengono invece generalmente visualizzate come dettagli di un particolare membro dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="63bd4-108">Instead, this information is generally only viewed as details of a particular attribute member.</span></span> <span data-ttu-id="63bd4-109">È possibile nascondere queste gerarchie degli attributi lasciando gli attributi visibili come proprietà del membro di un attributo specifico.</span><span class="sxs-lookup"><span data-stu-id="63bd4-109">You may want to hide these attribute hierarchies, leaving the attributes visible only as member properties of a specific attribute.</span></span> <span data-ttu-id="63bd4-110">È inoltre possibile rendere visibili i membri di altri attributi, come ad esempio i nomi dei clienti o i codici postali, solo quando vengono visualizzati tramite una gerarchia utente anziché indipendentemente tramite una gerarchia dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="63bd4-110">You may also want to make members of other attributes, such as customer names or postal codes, visible only when they are viewed through a user hierarchy instead of independently through an attribute hierarchy.</span></span> <span data-ttu-id="63bd4-111">Ciò può essere determinato dal numero dei membri distinti nella gerarchia dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="63bd4-111">One reason to do so may be the sheer number of distinct members in the attribute hierarchy.</span></span> <span data-ttu-id="63bd4-112">Per migliorare le prestazioni di elaborazione, è infine consigliabile disabilitare le gerarchie degli attributi non utilizzate dagli utenti a fini di esplorazione.</span><span class="sxs-lookup"><span data-stu-id="63bd4-112">Finally, to improve processing performance, you should disable attribute hierarchies that users will not use for browsing.</span></span>

 <span data-ttu-id="63bd4-113">Il valore della proprietà **AttributeHierarchyEnabled** determina se viene creata una gerarchia dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="63bd4-113">The value of the **AttributeHierarchyEnabled** property determines whether an attribute hierarchy is created.</span></span> <span data-ttu-id="63bd4-114">Se la proprietà è impostata su **False**, la gerarchia dell'attributo non viene creata e l'attributo non rappresenta un livello nella gerarchia utente; la gerarchia dell'attributo esiste solo come proprietà del membro.</span><span class="sxs-lookup"><span data-stu-id="63bd4-114">If this property is set to **False**, the attribute hierarchy is not created and the attribute cannot be used as a level in a user hierarchy; the attribute hierarchy exists as a member property only.</span></span> <span data-ttu-id="63bd4-115">È tuttavia possibile utilizzare una gerarchia dell'attributo disabilitata per ordinare i membri di un altro attributo.</span><span class="sxs-lookup"><span data-stu-id="63bd4-115">However, a disabled attribute hierarchy can still be used to order the members of another attribute.</span></span> <span data-ttu-id="63bd4-116">Se il valore della proprietà **AttributeHierarchyEnabled** è impostato su **True**, il valore della proprietà **AttributeHierarchyVisible** determina se la gerarchia dell'attributo è visibile indipendentemente dall'uso in una gerarchia definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="63bd4-116">If the value of the **AttributeHierarchyEnabled** property is set to **True**, the value of the **AttributeHierarchyVisible** property determines whether the attribute hierarchy is visible independent of its use in a user-defined hierarchy.</span></span>

 <span data-ttu-id="63bd4-117">Quando viene abilitata una gerarchia dell'attributo, è possibile specificare i valori delle tre proprietà aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="63bd4-117">When an attribute hierarchy is enabled, you may want to specify values for the following three additional properties:</span></span>

-   <span data-ttu-id="63bd4-118">**IsAggregatable**</span><span class="sxs-lookup"><span data-stu-id="63bd4-118">**IsAggregatable**</span></span>

     <span data-ttu-id="63bd4-119">Per impostazione predefinita, un livello (Totale) viene definito per tutte le gerarchie degli attributi.</span><span class="sxs-lookup"><span data-stu-id="63bd4-119">By default, an (All) level is defined for all attribute hierarchies.</span></span> <span data-ttu-id="63bd4-120">Per disabilitare questo livello per una gerarchia dell'attributo abilitata, impostare il valore della proprietà su **False**.</span><span class="sxs-lookup"><span data-stu-id="63bd4-120">To disable the (All) level for an enabled attribute hierarchy, set the value for this property to **False**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="63bd4-121">È possibile usare un attributo con la proprietà **IsAggregatable** impostata su False solo come radice di una gerarchia definita dall'utente ed è necessario che sia specificato un membro predefinito. In caso contrario, ne sceglierà uno automaticamente il motore [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63bd4-121">An attribute that has its **IsAggregatable** property set to false can only be used as the root of a user-defined hierarchy and must have a default member specified (otherwise, one will be chosen for you by the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] engine).</span></span>

-   <span data-ttu-id="63bd4-122">**AttributeHierarchyOrdered**</span><span class="sxs-lookup"><span data-stu-id="63bd4-122">**AttributeHierarchyOrdered**</span></span>

     <span data-ttu-id="63bd4-123">Per impostazione predefinita, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] consente di ordinare i membri delle gerarchie degli attributi attivati durante l'elaborazione; quindi i membri vengono archiviati in base al valore della proprietà **OrderBy** , ad esempio in base al nome o alla chiave.</span><span class="sxs-lookup"><span data-stu-id="63bd4-123">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] orders the members of enabled attribute hierarchies during processing, and then stores the members by the value of the **OrderBy** property, such as by Name or Key.</span></span> <span data-ttu-id="63bd4-124">Se non si desidera eseguire l'ordinamento, è possibile migliorare le prestazioni di elaborazione impostando il valore di questa proprietà su **False**.</span><span class="sxs-lookup"><span data-stu-id="63bd4-124">If you do not care about ordering, you can increase processing performance by setting the value of this property to **False**.</span></span>

-   <span data-ttu-id="63bd4-125">**AttributeHierarchyOptimizedState**</span><span class="sxs-lookup"><span data-stu-id="63bd4-125">**AttributeHierarchyOptimizedState**</span></span>

     <span data-ttu-id="63bd4-126">Per impostazione predefinita, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] consente di creare un indice per ogni gerarchia dell'attributo abilitata durante l'elaborazione in modo da migliorare le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="63bd4-126">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates an index for each enabled attribute hierarchy during processing, to improve query performance.</span></span> <span data-ttu-id="63bd4-127">Se non si intende utilizzare una gerarchia dell'attributo per la visualizzazione, è possibile migliorare le prestazioni di elaborazione impostando il valore di questa proprietà su **NotOptimized**.</span><span class="sxs-lookup"><span data-stu-id="63bd4-127">If you do not plan to use an attribute hierarchy for browsing, you can increase processing performance by setting the value of this property to **NotOptimized**.</span></span> <span data-ttu-id="63bd4-128">Se viene tuttavia utilizzata una gerarchia nascosta come attributo chiave per la dimensione, la creazione di un indice dei membri dell'attributo consentirà un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="63bd4-128">However, if you use a hidden hierarchy as the key attribute for the dimension, creating an index of the attribute members will still improve performance.</span></span>

 <span data-ttu-id="63bd4-129">Queste proprietà non si applicano se la gerarchia dell'attributo è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="63bd4-129">These properties do not apply if an attribute hierarchy is disabled.</span></span>

 <span data-ttu-id="63bd4-130">Nelle attività di questo argomento verranno illustrate le procedure per disabilitare i numeri della previdenza sociale e gli altri attributi della dimensione Employee che non verranno utilizzati per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="63bd4-130">In the tasks in this topic, you will disable social security numbers and other attributes in the Employee dimension that will not be used for browsing.</span></span> <span data-ttu-id="63bd4-131">Verranno quindi nascoste le gerarchie degli attributi relative al nome del cliente e al codice postale della dimensione Customer.</span><span class="sxs-lookup"><span data-stu-id="63bd4-131">You will then hide the customer name and postal code attribute hierarchies in the Customer dimension.</span></span> <span data-ttu-id="63bd4-132">Il numero elevato di membri dell'attributo di queste gerarchie determina un notevole rallentamento della visualizzazione indipendentemente dalla gerarchia utente.</span><span class="sxs-lookup"><span data-stu-id="63bd4-132">The large number of attribute members in these hierarchies will make browsing these hierarchies very slow independent of a user hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-employee-dimension"></a><span data-ttu-id="63bd4-133">Impostazione delle proprietà della gerarchia dell'attributo della dimensione Employee</span><span class="sxs-lookup"><span data-stu-id="63bd4-133">Setting Attribute Hierarchy Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="63bd4-134">Passare a Progettazione dimensioni per la dimensione Employee, quindi fare clic sulla scheda **Esplorazione** .</span><span class="sxs-lookup"><span data-stu-id="63bd4-134">Switch to Dimension Designer for the Employee dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="63bd4-135">Verificare che le seguenti gerarchie degli attributi vengano visualizzate nell'elenco **Gerarchia** :</span><span class="sxs-lookup"><span data-stu-id="63bd4-135">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="63bd4-136">**Base Rate**</span><span class="sxs-lookup"><span data-stu-id="63bd4-136">**Base Rate**</span></span>

    -   <span data-ttu-id="63bd4-137">**Birth Date**</span><span class="sxs-lookup"><span data-stu-id="63bd4-137">**Birth Date**</span></span>

    -   <span data-ttu-id="63bd4-138">**ID accesso**</span><span class="sxs-lookup"><span data-stu-id="63bd4-138">**Login ID**</span></span>

    -   <span data-ttu-id="63bd4-139">**Manager SSN**</span><span class="sxs-lookup"><span data-stu-id="63bd4-139">**Manager SSN**</span></span>

    -   <span data-ttu-id="63bd4-140">**SSN**</span><span class="sxs-lookup"><span data-stu-id="63bd4-140">**SSN**</span></span>

3.  <span data-ttu-id="63bd4-141">Passare alla scheda **Struttura dimensione** , quindi selezionare gli attributi seguenti nel riquadro **Attributi** .</span><span class="sxs-lookup"><span data-stu-id="63bd4-141">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane.</span></span> <span data-ttu-id="63bd4-142">Per selezionare più misure, fare clic su ognuna di esse tenendo premuto CTRL:</span><span class="sxs-lookup"><span data-stu-id="63bd4-142">You can select multiple measures by clicking each while holding down the CTRL key:</span></span>

    -   <span data-ttu-id="63bd4-143">**Base Rate**</span><span class="sxs-lookup"><span data-stu-id="63bd4-143">**Base Rate**</span></span>

    -   <span data-ttu-id="63bd4-144">**Birth Date**</span><span class="sxs-lookup"><span data-stu-id="63bd4-144">**Birth Date**</span></span>

    -   <span data-ttu-id="63bd4-145">**ID accesso**</span><span class="sxs-lookup"><span data-stu-id="63bd4-145">**Login ID**</span></span>

    -   <span data-ttu-id="63bd4-146">**Manager SSN**</span><span class="sxs-lookup"><span data-stu-id="63bd4-146">**Manager SSN**</span></span>

    -   <span data-ttu-id="63bd4-147">**SSN**</span><span class="sxs-lookup"><span data-stu-id="63bd4-147">**SSN**</span></span>

4.  <span data-ttu-id="63bd4-148">Nella finestra Proprietà impostare il valore della proprietà **AttributeHierarchyEnabled** su **False** per gli attributi selezionati.</span><span class="sxs-lookup"><span data-stu-id="63bd4-148">In the Properties window, set the value of the **AttributeHierarchyEnabled** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="63bd4-149">Si noti che nel riquadro **Attributi** l'icona relativa a ogni attributo è cambiata per indicare che l'attributo non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="63bd4-149">Notice in the **Attributes** pane that the icon for each attribute has changed to indicate that the attribute is not enabled.</span></span>

     <span data-ttu-id="63bd4-150">Nella figura seguente viene illustrata la proprietà **AttributeHierarchyEnabled** impostata su False per gli attributi selezionati.</span><span class="sxs-lookup"><span data-stu-id="63bd4-150">The following image shows the **AttributeHierarchyEnabled** property set to False for the selected attributes.</span></span>

     <span data-ttu-id="63bd4-151">![Proprietà AttributeHierarchyEnabled impostata su False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "Proprietà AttributeHierarchyEnabled impostata su False")</span><span class="sxs-lookup"><span data-stu-id="63bd4-151">![AttributeHierarchyEnabled property set to False](../../2014/tutorials/media/l4-hierarchyenabled-1.gif "AttributeHierarchyEnabled property set to False")</span></span>

5.  <span data-ttu-id="63bd4-152">Scegliere **Distribuisci Analysis Services Tutorial** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="63bd4-152">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

6.  <span data-ttu-id="63bd4-153">Al termine dell'elaborazione, passare alla scheda **Esplorazione** , fare clic su **Riconnetti**, quindi tentare di visualizzare le gerarchie degli attributi modificati.</span><span class="sxs-lookup"><span data-stu-id="63bd4-153">When processing has successfully completed, switch to the **Browser** tab, click **Reconnect**, and then try to browse the modified attribute hierarchies.</span></span>

     <span data-ttu-id="63bd4-154">Si noti che i membri degli attributi modificati non sono disponibili per la visualizzazione come gerarchie degli attributi nell'elenco **Gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="63bd4-154">Notice that the members of the modified attributes are not available for browsing as attribute hierarchies in the **Hierarchy** list.</span></span> <span data-ttu-id="63bd4-155">Se si tenta di aggiungere una delle gerarchie degli attributi disabilitate come livello di una gerarchia utente, verrà generato un errore che indica che per partecipare a una gerarchia definita dall'utente è necessario che la gerarchia dell'attributo sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="63bd4-155">If you try to add one of the disabled attribute hierarchies as a level in a user hierarchy, you will receive an error notifying you that the attribute hierarchy must be enabled to participate in a user-defined hierarchy.</span></span>

## <a name="setting-attribute-hierarchy-properties-in-the-customer-dimension"></a><span data-ttu-id="63bd4-156">Impostazione delle proprietà della gerarchia dell'attributo della dimensione Customer</span><span class="sxs-lookup"><span data-stu-id="63bd4-156">Setting Attribute Hierarchy Properties in the Customer Dimension</span></span>

1.  <span data-ttu-id="63bd4-157">Passare a Progettazione dimensioni per la dimensione Customer, quindi fare clic sulla scheda **Esplorazione** .</span><span class="sxs-lookup"><span data-stu-id="63bd4-157">Switch to Dimension Designer for the Customer dimension, and then click the **Browser** tab.</span></span>

2.  <span data-ttu-id="63bd4-158">Verificare che le seguenti gerarchie degli attributi vengano visualizzate nell'elenco **Gerarchia** :</span><span class="sxs-lookup"><span data-stu-id="63bd4-158">Verify that the following attribute hierarchies appear in the **Hierarchy** list:</span></span>

    -   <span data-ttu-id="63bd4-159">**Nome completo**</span><span class="sxs-lookup"><span data-stu-id="63bd4-159">**Full Name**</span></span>

    -   <span data-ttu-id="63bd4-160">**CAP**</span><span class="sxs-lookup"><span data-stu-id="63bd4-160">**Postal Code**</span></span>

3.  <span data-ttu-id="63bd4-161">Passare alla scheda **Struttura dimensione** e quindi selezionare gli attributi nel riquadro **Attributi** utilizzando CTRL per selezionare più attributi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="63bd4-161">Switch to the **Dimension Structure** tab, and then select the following attributes in the **Attributes** pane by using the CTRL key to select multiple attributes at the same time:</span></span>

    -   <span data-ttu-id="63bd4-162">**Nome completo**</span><span class="sxs-lookup"><span data-stu-id="63bd4-162">**Full Name**</span></span>

    -   <span data-ttu-id="63bd4-163">**CAP**</span><span class="sxs-lookup"><span data-stu-id="63bd4-163">**Postal Code**</span></span>

4.  <span data-ttu-id="63bd4-164">Nella finestra Proprietà impostare il valore della proprietà **AttributeHierarchyVisible** su **False** per gli attributi selezionati.</span><span class="sxs-lookup"><span data-stu-id="63bd4-164">In the Properties window, set the value of the **AttributeHierarchyVisible** property to **False** for the selected attributes.</span></span>

     <span data-ttu-id="63bd4-165">Poiché i membri di queste gerarchie degli attributi verranno utilizzati per dimensionare le tabelle dei fatti, l'ordinamento e l'ottimizzazione dei membri di queste gerarchie degli attributi determineranno un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="63bd4-165">Because the members of these attribute hierarchies will be used for dimensioning fact data, ordering and optimizing the members of these attribute hierarchies will improve performance.</span></span> <span data-ttu-id="63bd4-166">È pertanto consigliabile non modificare le proprietà di questi attributi.</span><span class="sxs-lookup"><span data-stu-id="63bd4-166">Therefore, the properties of these attributes should not be changed.</span></span>

     <span data-ttu-id="63bd4-167">La figura seguente illustra la proprietà **AttributeHierarchyVisible** impostata su False.</span><span class="sxs-lookup"><span data-stu-id="63bd4-167">The following image shows the **AttributeHierarchyVisible** property set to False.</span></span>

     <span data-ttu-id="63bd4-168">![Proprietà AttributeHierarchyVisible impostata su False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "Proprietà AttributeHierarchyVisible impostata su False")</span><span class="sxs-lookup"><span data-stu-id="63bd4-168">![AttributeHierarchyVisible property set to False](../../2014/tutorials/media/l4-hierarchyvisible-1.gif "AttributeHierarchyVisible property set to False")</span></span>

5.  <span data-ttu-id="63bd4-169">Trascinare l'attributo **Postal Code** dal riquadro **Attributi** nella gerarchia utente **Customer Geography** all'interno del riquadro **Gerarchie e livelli** immediatamente sotto il livello **City** .</span><span class="sxs-lookup"><span data-stu-id="63bd4-169">Drag the **Postal Code** attribute from the **Attributes** pane into the **Customer Geography** user hierarchy in the **Hierarchies and Levels** pane, immediately under the **City** level.</span></span>

     <span data-ttu-id="63bd4-170">Si noti che è possibile che un attributo nascosto diventi un livello in una gerarchia utente.</span><span class="sxs-lookup"><span data-stu-id="63bd4-170">Notice that a hidden attribute can still become a level in a user hierarchy.</span></span>

6.  <span data-ttu-id="63bd4-171">Scegliere **Distribuisci Analysis Services Tutorial** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="63bd4-171">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

7.  <span data-ttu-id="63bd4-172">Al termine delle operazioni di distribuzione, passare alla scheda **Esplorazione** per la dimensione Customer e quindi fare clic su **Riconnetti**.</span><span class="sxs-lookup"><span data-stu-id="63bd4-172">When deployment has successfully completed, switch to the **Browser** tab for the Customer dimension, and then click **Reconnect**.</span></span>

8.  <span data-ttu-id="63bd4-173">Provare a selezionare una delle gerarchie degli attributi modificati dall'elenco **Gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="63bd4-173">Try to select either of the modified attribute hierarchies from the **Hierarchy** list.</span></span>

     <span data-ttu-id="63bd4-174">Si noti che nessuna delle gerarchie degli attributi modificati viene visualizzata nell'elenco **Gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="63bd4-174">Notice that neither of the modified attribute hierarchies appears in the **Hierarchy** list.</span></span>

9. <span data-ttu-id="63bd4-175">Nell'elenco **Gerarchia** selezionare **Customer Geography**e quindi visualizzare tutti i livelli nel riquadro del visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="63bd4-175">In the **Hierarchy** list, select **Customer Geography**, and then browse each level in the browser pane.</span></span>

     <span data-ttu-id="63bd4-176">Si noti che i livelli nascosti, **Postal Code** e **Full Name**, sono visibili nella gerarchia definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="63bd4-176">Notice that the hidden levels, **Postal Code** and **Full Name**, are visible in the user-defined hierarchy.</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="63bd4-177">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="63bd4-177">Next Task in Lesson</span></span>
 [<span data-ttu-id="63bd4-178">Ordinamento dei membri dell'attributo in base a un attributo secondario</span><span class="sxs-lookup"><span data-stu-id="63bd4-178">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)


