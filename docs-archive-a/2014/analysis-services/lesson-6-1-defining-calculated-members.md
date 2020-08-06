---
title: Definizione dei membri calcolati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 07f13e1c-0b20-4f9e-ad62-c438983f2785
author: minewiskan
ms.author: owend
ms.openlocfilehash: f2a054356613ebf3d4cf825c1fa4c238a5362ec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627491"
---
# <a name="defining-calculated-members"></a><span data-ttu-id="f4276-102">Definizione dei membri calcolati</span><span class="sxs-lookup"><span data-stu-id="f4276-102">Defining Calculated Members</span></span>
  <span data-ttu-id="f4276-103">I membri calcolati sono membri di una dimensione o di un gruppo di misure definiti in base a una combinazione di dati del cubo, di operatori aritmetici, di numeri e di funzioni.</span><span class="sxs-lookup"><span data-stu-id="f4276-103">Calculated members are members of a dimension or a measure group that are defined based on a combination of cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="f4276-104">È possibile ad esempio creare un membro calcolato che calcoli la somma di due misure fisiche del cubo.</span><span class="sxs-lookup"><span data-stu-id="f4276-104">For example, you can create a calculated member that calculates the sum of two physical measures in the cube.</span></span> <span data-ttu-id="f4276-105">Le definizioni dei membri calcolati vengono archiviate nei cubi, ma i loro valori vengono calcolati in fase di query.</span><span class="sxs-lookup"><span data-stu-id="f4276-105">Calculated member definitions are stored in cubes, but their values are calculated at query time.</span></span>  
  
 <span data-ttu-id="f4276-106">Per creare un membro calcolato, usare il comando **Nuovo membro calcolato** nella scheda **Calcoli** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="f4276-106">To create a calculated member, use the **New Calculated Member** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="f4276-107">È possibile creare un membro calcolato all'interno di qualsiasi dimensione, inclusa la dimensione di tipo misure.</span><span class="sxs-lookup"><span data-stu-id="f4276-107">You can create a calculated member within any dimension, including the measures dimension.</span></span> <span data-ttu-id="f4276-108">È anche possibile inserire un membro calcolato in una cartella di visualizzazione nella finestra di dialogo **Proprietà calcolo** .</span><span class="sxs-lookup"><span data-stu-id="f4276-108">You can also place a calculated member within a display folder in the **Calculation Properties** dialog box.</span></span> <span data-ttu-id="f4276-109">Per altre informazioni, vedere [Calcoli](multidimensional-models-olap-logical-cube-objects/calculations.md), [Calcoli nei modelli multidimensionali](multidimensional-models/calculations-in-multidimensional-models.md)e [Creare membri calcolati](multidimensional-models/create-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="f4276-109">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), [Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md), and [Create Calculated Members](multidimensional-models/create-calculated-members.md).</span></span>  
  
 <span data-ttu-id="f4276-110">Nelle procedure descritte in questo argomento vengono definite misure calcolate per consentire agli utenti di visualizzare i rapporti tra la percentuale di margine di profitto lordo e le vendite per le vendite Internet, le vendite rivenditore e tutte le vendite.</span><span class="sxs-lookup"><span data-stu-id="f4276-110">In the tasks in this topic, you define calculated measures to let users view the gross profit margin percentage and sales ratios for Internet sales, reseller sales, and for all sales.</span></span>  
  
## <a name="defining-calculations-to-aggregate-physical-measures"></a><span data-ttu-id="f4276-111">Definizione di calcoli per aggregare le misure fisiche</span><span class="sxs-lookup"><span data-stu-id="f4276-111">Defining Calculations to Aggregate Physical Measures</span></span>  
  
1.  <span data-ttu-id="f4276-112">Aprire Progettazione cubi per il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial e fare clic sulla scheda **Calcoli** .</span><span class="sxs-lookup"><span data-stu-id="f4276-112">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="f4276-113">Si noti il comando predefinito CALCULATE nel riquadro **Calculation Expressions** (Espressioni di calcolo) e nel riquadro **Libreria script** .</span><span class="sxs-lookup"><span data-stu-id="f4276-113">Notice the default CALCULATE command in the **Calculation Expressions** pane and in the **Script Organizer** pane.</span></span> <span data-ttu-id="f4276-114">Tale comando specifica che le misure del cubo devono essere aggregate in base al valore specificato dalle corrispondenti proprietà AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="f4276-114">This command specifies that the measures in the cube should be aggregated according to the value that is specified by their AggregateFunction properties.</span></span> <span data-ttu-id="f4276-115">I valori di misura vengono generalmente sommati, ma possono essere contati o aggregati in altro modo.</span><span class="sxs-lookup"><span data-stu-id="f4276-115">Measure values are generally summed, but may also be counted or aggregated in some other manner.</span></span>  
  
     <span data-ttu-id="f4276-116">Nella figura seguente viene illustrata la scheda **Calcoli** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="f4276-116">The following image shows the **Calculations** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="f4276-117">![Scheda Calcoli di Progettazione cubi](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Scheda Calcoli di Progettazione cubi")</span><span class="sxs-lookup"><span data-stu-id="f4276-117">![Calculations tab of Cube Designer](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Calculations tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="f4276-118">Fare clic su **Nuovo membro calcolato** sulla barra degli strumenti della scheda **Calcoli**.</span><span class="sxs-lookup"><span data-stu-id="f4276-118">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="f4276-119">Verrà visualizzato un nuovo modulo nel riquadro **Calculation Expressions** (Espressioni di calcolo), all'interno del quale è possibile definire le proprietà del nuovo membro calcolato.</span><span class="sxs-lookup"><span data-stu-id="f4276-119">A new form appears in the **Calculation Expressions** pane within which you define the properties of this new calculated member.</span></span> <span data-ttu-id="f4276-120">Il nuovo membro verrà visualizzato anche nel riquadro **Libreria script** .</span><span class="sxs-lookup"><span data-stu-id="f4276-120">The new member also appears in the **Script Organizer** pane.</span></span>  
  
     <span data-ttu-id="f4276-121">Nella figura seguente viene illustrato il modulo visualizzato nel riquadro **Calculation Expressions** (Espressioni di calcolo) quando si fa clic su **Nuovo membro calcolato**.</span><span class="sxs-lookup"><span data-stu-id="f4276-121">The following image shows the form that appears in the **Calculation Expressions** pane when you click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="f4276-122">![Form del riquadro Espressioni di calcolo](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Form del riquadro Espressioni di calcolo")</span><span class="sxs-lookup"><span data-stu-id="f4276-122">![Calculation Expressions pane form](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Calculation Expressions pane form")</span></span>  
  
3.  <span data-ttu-id="f4276-123">Nella casella **nome** modificare il nome della misura calcolata in `[Total Sales Amount]` .</span><span class="sxs-lookup"><span data-stu-id="f4276-123">In the **Name** box, change the name of the calculated measure to `[Total Sales Amount]`.</span></span>  
  
     <span data-ttu-id="f4276-124">Se il nome di un membro calcolato contiene uno spazio, tale nome deve essere racchiuso tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="f4276-124">If the name of a calculated member contains a space, the calculated member name must be enclosed in square brackets.</span></span>  
  
     <span data-ttu-id="f4276-125">Si noti che, nell'elenco **Gerarchia padre** viene creato per impostazione predefinita un nuovo membro calcolato nella dimensione **Measures** .</span><span class="sxs-lookup"><span data-stu-id="f4276-125">Notice in the **Parent hierarchy** list that, by default, a new calculated member is created in the **Measures** dimension.</span></span> <span data-ttu-id="f4276-126">Un membro calcolato nella dimensione Measures viene spesso definito misura calcolata.</span><span class="sxs-lookup"><span data-stu-id="f4276-126">A calculated member in the Measures dimension is also frequently called a calculated measure.</span></span>  
  
4.  <span data-ttu-id="f4276-127">Nella scheda **Metadati** del riquadro **Strumenti di calcolo** della scheda **Calcoli** espandere **Measures** e poi **Internet Sales** per visualizzare i metadati per il gruppo di misure **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="f4276-127">On the **Metadata** tab in the **Calculation Tools** pane of the **Calculations** tab, expand **Measures** and then expand **Internet Sales** to view the metadata for the **Internet Sales** measure group.</span></span>  
  
     <span data-ttu-id="f4276-128">Gli elementi di metadati possono essere trascinati dal riquadro **Strumenti di calcolo** nella casella **Espressione** ed è quindi possibile aggiungere operatori e altri elementi per creare espressioni MDX (Multidimensional Expression).</span><span class="sxs-lookup"><span data-stu-id="f4276-128">You can drag metadata elements from the **Calculation Tools** pane into the **Expression** box and then add operators and other elements to create Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="f4276-129">In alternativa è possibile digitare l'espressione MDX direttamente nella casella **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="f4276-129">Alternatively, you can type the MDX expression directly into the **Expression** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f4276-130">Se non è possibile visualizzare i metadati nel riquadro **Strumenti di calcolo** , fare clic su **Riconnetti** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="f4276-130">If you cannot view any metadata in the **Calculation Tools** pane, click **Reconnect** on the toolbar.</span></span> <span data-ttu-id="f4276-131">Se questo sistema non funziona, può essere necessario elaborare il cubo o avviare l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4276-131">If this does not work, you may have to process the cube or start the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="f4276-132">Trascinare **Internet Sales-Sales Amount** dalla scheda **Metadati** nel riquadro **Strumenti di calcolo** alla casella **Espressione** nel riquadro **Calculation Expressions** (Espressioni di calcolo).</span><span class="sxs-lookup"><span data-stu-id="f4276-132">Drag **Internet Sales-Sales Amount** from the **Metadata** tab in the **Calculation Tools** pane into the **Expression** box in the **Calculation Expressions** pane.</span></span>  
  
6.  <span data-ttu-id="f4276-133">Nella casella **Espressione** digitare un segno più (`+`) dopo **[Measures].[Internet Sales-Sales Amount]**.</span><span class="sxs-lookup"><span data-stu-id="f4276-133">In the **Expression** box, type a plus sign (`+`) after **[Measures].[Internet Sales-Sales Amount]**.</span></span>  
  
7.  <span data-ttu-id="f4276-134">Nella scheda **Metadati** del riquadro **Strumenti di calcolo** , espandere **Vendite rivenditore**e trascinare **Reseller Sales-Sales Amount** nella casella **Espressione** del riquadro **Calculation Expressions** (Espressioni di calcolo) dopo il segno più (+).</span><span class="sxs-lookup"><span data-stu-id="f4276-134">On the **Metadata** tab in the **Calculation Tools** pane, expand **Reseller Sales**, and then drag **Reseller Sales-Sales Amount** into the **Expression** box in the **Calculation Expressions** pane after the plus sign (+).</span></span>  
  
8.  <span data-ttu-id="f4276-135">Nell'elenco **stringa formato** selezionare **"valuta".**</span><span class="sxs-lookup"><span data-stu-id="f4276-135">In the **Format string** list, select **"Currency".**</span></span>  
  
9. <span data-ttu-id="f4276-136">Nell'elenco **Gestione NON EMPTY** selezionare le caselle di controllo corrispondenti a **Internet Sales-Sales Amount** e **Reseller Sales-Sales Amount**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4276-136">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f4276-137">Le misure specificate nell'elenco **Gestione NON EMPTY** vengono usate per risolvere query NON VUOTE in MDX.</span><span class="sxs-lookup"><span data-stu-id="f4276-137">The measures you specify in the **Non-empty behavior** list are used to resolve NON EMPTY queries in MDX.</span></span> <span data-ttu-id="f4276-138">Quando si specifica una o più misure nell'elenco \*\*Gestione NON EMPTY[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], \*\* tratta i membri calcolati come vuoti se tutte le misure specificate sono vuote.</span><span class="sxs-lookup"><span data-stu-id="f4276-138">When you specify one or more measures in the **Non-empty behavior** list, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] treats the calculated member as empty if all the specified measures are empty.</span></span> <span data-ttu-id="f4276-139">Se la proprietà \*\*Gestione NON EMPTY[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] è vuota, \*\* deve valutare il membro calcolato stesso per determinare se è vuoto.</span><span class="sxs-lookup"><span data-stu-id="f4276-139">If the **Non-empty behavior** property is blank, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] must evaluate the calculated member itself to determine whether the member is empty.</span></span>  
  
     <span data-ttu-id="f4276-140">Nella figura seguente viene illustrato il riquadro **Calculation Expressions** (Espressioni di calcolo) popolato con le impostazione specificate nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="f4276-140">The following image shows the **Calculation Expressions** pane populated with the settings that you specified in the previous steps.</span></span>  
  
     <span data-ttu-id="f4276-141">![Riquadro Espressioni di calcolo compilato](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Riquadro Espressioni di calcolo compilato")</span><span class="sxs-lookup"><span data-stu-id="f4276-141">![Populated Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Populated Calculation Expressions pane")</span></span>  
  
10. <span data-ttu-id="f4276-142">Sulla barra degli strumenti della scheda **Calcoli** fare clic su **Visualizzazione Script**e controllare lo script di calcolo nel riquadro **Calculation Expressions** (Espressioni di calcolo).</span><span class="sxs-lookup"><span data-stu-id="f4276-142">On the toolbar of the **Calculations** tab, click **Script View**, and then review the calculation script in the **Calculation Expressions** pane.</span></span>  
  
     <span data-ttu-id="f4276-143">Si noti che il nuovo calcolo viene aggiunto all'espressione CALCULATE iniziale e che ogni singolo calcolo è separato da punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="f4276-143">Notice that the new calculation is added to the initial CALCULATE expression; each individual calculation is separated by a semicolon.</span></span> <span data-ttu-id="f4276-144">Si noti inoltre che viene visualizzato un commento all'inizio dello script di calcolo.</span><span class="sxs-lookup"><span data-stu-id="f4276-144">Notice also that a comment appears at the beginning of the calculation script.</span></span> <span data-ttu-id="f4276-145">È consigliabile aggiungere commenti nello script di calcolo per i gruppi di calcoli per consentire agli sviluppatori di comprendere script di calcolo complessi.</span><span class="sxs-lookup"><span data-stu-id="f4276-145">Adding comments within the calculation script for groups of calculations is a good practice, to help you and other developers understand complex calculation scripts.</span></span>  
  
11. <span data-ttu-id="f4276-146">Aggiungere una nuova riga nello script di calcolo dopo il comando **Calculate;** e prima dello script di calcolo appena aggiunto, poi aggiungere il testo seguente allo script su una riga a sé stante:</span><span class="sxs-lookup"><span data-stu-id="f4276-146">Add a new line in the calculation script after the **Calculate;** command and before the newly added calculation script, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to aggregate Internet Sales and Reseller Sales measures */  
    ```  
  
     <span data-ttu-id="f4276-147">La figura seguente illustra gli script di calcolo che saranno visualizzati nel riquadro **Calculation Expressions** (Espressioni di calcolo) a questo punto dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="f4276-147">The following image shows the calculation scripts as they should appear in the **Calculation Expressions** pane at this point in the tutorial.</span></span>  
  
     <span data-ttu-id="f4276-148">![Script nel riquadro Espressioni di calcolo](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Script nel riquadro Espressioni di calcolo")</span><span class="sxs-lookup"><span data-stu-id="f4276-148">![Scripts in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts in Calculation Expressions pane")</span></span>  
  
12. <span data-ttu-id="f4276-149">Sulla barra degli strumenti della scheda **calcoli** fare clic su **visualizzazione form**, verificare che `[Total Sales Amount]` sia selezionato nel riquadro **Libreria script** , quindi fare clic su **nuovo membro calcolato**.</span><span class="sxs-lookup"><span data-stu-id="f4276-149">On the toolbar of the **Calculations** tab, click **Form View**, verify that `[Total Sales Amount]` is selected in the **Script Organizer** pane, and then click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="f4276-150">Modificare il nome del nuovo membro calcolato in `[Total Product Cost]` , quindi creare l'espressione seguente nella casella **espressione** :</span><span class="sxs-lookup"><span data-stu-id="f4276-150">Change the name of this new calculated member to `[Total Product Cost]`, and then create the following expression in the **Expression** box:</span></span>  
  
    ```  
    [Measures].[Internet Sales-Total Product Cost] + [Measures].[Reseller Sales-Total Product Cost]  
    ```  
  
14. <span data-ttu-id="f4276-151">Nell'elenco **Stringa formato** selezionare **"Currency"**.</span><span class="sxs-lookup"><span data-stu-id="f4276-151">In the **Format string** list, select **"Currency"**.</span></span>  
  
15. <span data-ttu-id="f4276-152">Nell'elenco **Gestione NON EMPTY** selezionare le caselle di controllo corrispondenti a **Internet Sales-Total Product Cost** e **Reseller Sales-Total Product Cost**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4276-152">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Total Product Cost** and **Reseller Sales-Total Product Cost**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f4276-153">Sono stati definiti ora due membri calcolati, entrambi visibili nel riquadro **Libreria script** .</span><span class="sxs-lookup"><span data-stu-id="f4276-153">You have now defined two calculated members, both of which are visible in the **Script Organizer** pane.</span></span> <span data-ttu-id="f4276-154">Tali membri calcolati possono essere utilizzati da altri calcoli definiti successivamente nello script di calcolo.</span><span class="sxs-lookup"><span data-stu-id="f4276-154">These calculated members can be used by other calculations that you define later in the calculation script.</span></span> <span data-ttu-id="f4276-155">È possibile visualizzare la definizione di qualsiasi membro calcolato selezionandolo nel riquadro **Libreria script** . La definizione del membro calcolato verrà visualizzata nel riquadro **Calculation Expressions** (Espressioni di calcolo) in Visualizzazione Form.</span><span class="sxs-lookup"><span data-stu-id="f4276-155">You can view the definition of any calculated member by selecting the calculated member in the **Script Organizer** pane; the definition of the calculated member will appear in the **Calculation Expressions** pane in the Form view.</span></span> <span data-ttu-id="f4276-156">I membri calcolati appena definiti non verranno visualizzati nel riquadro **Strumenti di calcolo** finché tali oggetti non sono stati distribuiti.</span><span class="sxs-lookup"><span data-stu-id="f4276-156">Newly defined calculated members will not appear in the **Calculation Tools** pane until these objects have been deployed.</span></span> <span data-ttu-id="f4276-157">Non è necessaria alcuna elaborazione per i calcoli.</span><span class="sxs-lookup"><span data-stu-id="f4276-157">Calculations do not require processing.</span></span>  
  
## <a name="defining-gross-profit-margin-calculations"></a><span data-ttu-id="f4276-158">Definizione dei calcoli del margine di profitto lordo</span><span class="sxs-lookup"><span data-stu-id="f4276-158">Defining Gross Profit Margin Calculations</span></span>  
  
1.  <span data-ttu-id="f4276-159">Verificare che `[Total Product Cost]` sia selezionato nel riquadro **Libreria script** , quindi fare clic su **nuovo membro calcolato** nella barra degli strumenti della scheda **calcoli** .</span><span class="sxs-lookup"><span data-stu-id="f4276-159">Verify that `[Total Product Cost]` is selected in the **Script Organizer** pane, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
2.  <span data-ttu-id="f4276-160">Nella casella **nome** modificare il nome della nuova misura calcolata in `[Internet GPM]` .</span><span class="sxs-lookup"><span data-stu-id="f4276-160">In the **Name** box, change the name of this new calculated measure to `[Internet GPM]`.</span></span>  
  
3.  <span data-ttu-id="f4276-161">Nella casella **Espressione** creare l'espressione MDX seguente:</span><span class="sxs-lookup"><span data-stu-id="f4276-161">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Internet Sales-Sales Amount] -   
    [Measures].[Internet Sales-Total Product Cost]) /  
    [Measures].[Internet Sales-Sales Amount]  
    ```  
  
4.  <span data-ttu-id="f4276-162">Nell'elenco **Stringa formato** selezionare **"Percent"**.</span><span class="sxs-lookup"><span data-stu-id="f4276-162">In the **Format string** list, select **"Percent"**.</span></span>  
  
5.  <span data-ttu-id="f4276-163">Nell'elenco **Gestione NON EMPTY** selezionare la casella di controllo corrispondente a **Internet Sales-Sales Amount**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4276-163">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="f4276-164">Fare clic su **Nuovo membro calcolato** sulla barra degli strumenti della scheda **Calcoli**.</span><span class="sxs-lookup"><span data-stu-id="f4276-164">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
7.  <span data-ttu-id="f4276-165">Nella casella **nome** modificare il nome della nuova misura calcolata in `[Reseller GPM]` .</span><span class="sxs-lookup"><span data-stu-id="f4276-165">In the **Name** box, change the name of this new calculated measure to `[Reseller GPM]`.</span></span>  
  
8.  <span data-ttu-id="f4276-166">Nella casella **Espressione** creare l'espressione MDX seguente:</span><span class="sxs-lookup"><span data-stu-id="f4276-166">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Reseller Sales-Sales Amount] -   
    [Measures].[Reseller Sales-Total Product Cost]) /  
    [Measures].[Reseller Sales-Sales Amount]  
    ```  
  
9. <span data-ttu-id="f4276-167">Nell'elenco **Stringa formato** selezionare **"Percent"**.</span><span class="sxs-lookup"><span data-stu-id="f4276-167">In the **Format string** list, select **"Percent"**.</span></span>  
  
10. <span data-ttu-id="f4276-168">Nell'elenco **Gestione NON EMPTY** selezionare la casella di controllo corrispondente a **Reseller Sales-Sales Amount**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4276-168">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="f4276-169">Fare clic su **Nuovo membro calcolato** sulla barra degli strumenti della scheda **Calcoli**.</span><span class="sxs-lookup"><span data-stu-id="f4276-169">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
12. <span data-ttu-id="f4276-170">Nella casella **nome** modificare il nome della misura calcolata in `[Total GPM]` .</span><span class="sxs-lookup"><span data-stu-id="f4276-170">In the **Name** box, change the name of this calculated measure to `[Total GPM]`.</span></span>  
  
13. <span data-ttu-id="f4276-171">Nella casella **Espressione** creare l'espressione MDX seguente:</span><span class="sxs-lookup"><span data-stu-id="f4276-171">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Total Sales Amount] -   
    [Measures].[Total Product Cost]) /  
    [Measures].[Total Sales Amount]  
    ```  
  
     <span data-ttu-id="f4276-172">Si noti che il membro calcolato fa riferimento ad altri membri calcolati.</span><span class="sxs-lookup"><span data-stu-id="f4276-172">Notice that this calculated member is referencing other calculated members.</span></span> <span data-ttu-id="f4276-173">Poiché tale membro verrà calcolato dopo i membri calcolati a cui fa riferimento, si tratta di un membro calcolato valido.</span><span class="sxs-lookup"><span data-stu-id="f4276-173">Because this calculated member will be calculated after the calculated members that it references, this is a valid calculated member.</span></span>  
  
14. <span data-ttu-id="f4276-174">Nell'elenco **Stringa formato** selezionare **"Percent"**.</span><span class="sxs-lookup"><span data-stu-id="f4276-174">In the **Format string** list, select **"Percent"**.</span></span>  
  
15. <span data-ttu-id="f4276-175">Nell'elenco **Gestione NON EMPTY** selezionare le caselle di controllo corrispondenti a **Internet Sales-Sales Amount** e **Reseller Sales-Sales Amount**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4276-175">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="f4276-176">Fare clic su **Visualizzazione Script** sulla barra degli strumenti della scheda **Calcoli** e controllare i tre calcoli appena aggiunti allo script di calcolo.</span><span class="sxs-lookup"><span data-stu-id="f4276-176">On the toolbar of the **Calculations** tab, click **Script View** and review the three calculations you just added to the calculation script.</span></span>  
  
17. <span data-ttu-id="f4276-177">Aggiungere una nuova riga nello script di calcolo immediatamente prima del `[Internet GPM]` calcolo, quindi aggiungere il testo seguente allo script su una riga a se stante:</span><span class="sxs-lookup"><span data-stu-id="f4276-177">Add a new line in the calculation script immediately before the `[Internet GPM]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate gross profit margin */  
    ```  
  
     <span data-ttu-id="f4276-178">Nella figura seguente viene illustrato il riquadro **Espressioni** con i tre nuovi calcoli.</span><span class="sxs-lookup"><span data-stu-id="f4276-178">The following image shows the **Expressions** pane with the three new calculations.</span></span>  
  
     <span data-ttu-id="f4276-179">![Nuovi calcoli nel riquadro Espressioni di calcolo](../../2014/tutorials/media/l6-calculatedmembers-05.gif "Nuovi calcoli nel riquadro Espressioni di calcolo")</span><span class="sxs-lookup"><span data-stu-id="f4276-179">![New calculations in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-05.gif "New calculations in Calculation Expressions pane")</span></span>  
  
## <a name="defining-the-percent-of-total-calculations"></a><span data-ttu-id="f4276-180">Definizione della percentuale dei calcoli totali</span><span class="sxs-lookup"><span data-stu-id="f4276-180">Defining the Percent of Total Calculations</span></span>  
  
1.  <span data-ttu-id="f4276-181">Fare clic su **Visualizzazione Form** sulla barra degli strumenti della scheda **Calcoli**.</span><span class="sxs-lookup"><span data-stu-id="f4276-181">On the toolbar of the **Calculations** tab, click **Form View**.</span></span>  
  
2.  <span data-ttu-id="f4276-182">Nel riquadro **Libreria script** selezionare `[Total GPM]` , quindi fare clic su **nuovo membro calcolato** nella barra degli strumenti della scheda **calcoli** .</span><span class="sxs-lookup"><span data-stu-id="f4276-182">In the **Script Organizer** pane, select `[Total GPM]`, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="f4276-183">Facendo clic sull'ultimo membro calcolato nel riquadro **Libreria script** prima di selezionare **Nuovo membro calcolato** si garantisce che il nuovo membro calcolato venga immesso alla fine dello script.</span><span class="sxs-lookup"><span data-stu-id="f4276-183">Clicking the final calculated member in the **Script Organizer** pane before you click **New Calculated Member** guarantees that the new calculated member will be entered at the end of the script.</span></span> <span data-ttu-id="f4276-184">L'esecuzione degli script seguirà l'ordine visualizzato nel riquadro **Libreria script** .</span><span class="sxs-lookup"><span data-stu-id="f4276-184">Scripts execute in the order that they appear in the **Script Organizer** pane.</span></span>  
  
3.  <span data-ttu-id="f4276-185">Modificare il nome del nuovo membro calcolato in `[Internet Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="f4276-185">Change the name of this new calculated member to `[Internet Sales Ratio to All Products]`.</span></span>  
  
4.  <span data-ttu-id="f4276-186">Digitare l'espressione seguente nella casella **Espressione** :</span><span class="sxs-lookup"><span data-stu-id="f4276-186">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Internet Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Internet Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Internet Sales-Sales Amount] )  
        End  
    ```  
  
     <span data-ttu-id="f4276-187">Questa espressione MDX calcola il contributo di ogni prodotto alle vendite Internet totali.</span><span class="sxs-lookup"><span data-stu-id="f4276-187">This MDX expression calculates the contribution to total Internet sales of each product.</span></span> <span data-ttu-id="f4276-188">L'istruzione Case combinata alla funzione IS EMPTY evita la generazione di un errore di divisione per zero quando le vendite di un prodotto corrispondono a zero.</span><span class="sxs-lookup"><span data-stu-id="f4276-188">The Case statement together with the IS EMPTY function ensures that a divide by zero error does not occur when a product has no sales.</span></span>  
  
5.  <span data-ttu-id="f4276-189">Nell'elenco **Stringa formato** selezionare **"Percent"**.</span><span class="sxs-lookup"><span data-stu-id="f4276-189">In the **Format string** list, select **"Percent"**.</span></span>  
  
6.  <span data-ttu-id="f4276-190">Nell'elenco **Gestione NON EMPTY** selezionare la casella di controllo corrispondente a **Internet Sales-Sales Amount**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4276-190">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="f4276-191">Fare clic su **Nuovo membro calcolato** sulla barra degli strumenti della scheda **Calcoli**.</span><span class="sxs-lookup"><span data-stu-id="f4276-191">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
8.  <span data-ttu-id="f4276-192">Modificare il nome del membro calcolato in `[Reseller Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="f4276-192">Change the name of this calculated member to `[Reseller Sales Ratio to All Products]`.</span></span>  
  
9. <span data-ttu-id="f4276-193">Digitare l'espressione seguente nella casella **Espressione** :</span><span class="sxs-lookup"><span data-stu-id="f4276-193">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Reseller Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Reseller Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Reseller Sales-Sales Amount] )  
        End  
    ```  
  
10. <span data-ttu-id="f4276-194">Nell'elenco **Stringa formato** selezionare **"Percent"**.</span><span class="sxs-lookup"><span data-stu-id="f4276-194">In the **Format string** list, select **"Percent"**.</span></span>  
  
11. <span data-ttu-id="f4276-195">Nell'elenco **Gestione NON EMPTY** selezionare la casella di controllo corrispondente a **Reseller Sales-Sales Amount**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4276-195">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="f4276-196">Fare clic su **Nuovo membro calcolato** sulla barra degli strumenti della scheda **Calcoli**.</span><span class="sxs-lookup"><span data-stu-id="f4276-196">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="f4276-197">Modificare il nome del membro calcolato in `[Total Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="f4276-197">Change the name of this calculated member to `[Total Sales Ratio to All Products]`.</span></span>  
  
14. <span data-ttu-id="f4276-198">Digitare l'espressione seguente nella casella **Espressione** :</span><span class="sxs-lookup"><span data-stu-id="f4276-198">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Total Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Total Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Total Sales Amount] )  
        End  
    ```  
  
15. <span data-ttu-id="f4276-199">Nell'elenco **Stringa formato** selezionare **"Percent"**.</span><span class="sxs-lookup"><span data-stu-id="f4276-199">In the **Format string** list, select **"Percent"**.</span></span>  
  
16. <span data-ttu-id="f4276-200">Nell'elenco **Gestione NON EMPTY** selezionare le caselle di controllo corrispondenti a **Internet Sales-Sales Amount** e **Reseller Sales-Sales Amount**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4276-200">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="f4276-201">Fare clic su **Visualizzazione Script** nella barra degli strumenti della scheda **Calcoli**e controllare i tre calcoli appena aggiunti allo script di calcolo.</span><span class="sxs-lookup"><span data-stu-id="f4276-201">On the toolbar of the **Calculations** tab, click **Script View**, and then review the three calculations that you just added to the calculation script.</span></span>  
  
18. <span data-ttu-id="f4276-202">Aggiungere una nuova riga nello script di calcolo immediatamente prima del `[Internet Sales Ratio to All Products]` calcolo, quindi aggiungere il testo seguente allo script su una riga a se stante:</span><span class="sxs-lookup"><span data-stu-id="f4276-202">Add a new line in the calculation script immediately before the `[Internet Sales Ratio to All Products]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate percentage of product to total product sales */  
    ```  
  
     <span data-ttu-id="f4276-203">È stato ora definito un totale di otto membri calcolati, visibili nel riquadro **Libreria script** in Visualizzazione Form.</span><span class="sxs-lookup"><span data-stu-id="f4276-203">You have now defined a total of eight calculated members, which are visible in the **Script Organizer** pane when you are in Form view.</span></span>  
  
## <a name="browsing-the-new-calculated-members"></a><span data-ttu-id="f4276-204">Esplorazione dei nuovi membri calcolati</span><span class="sxs-lookup"><span data-stu-id="f4276-204">Browsing the New Calculated Members</span></span>  
  
1.  <span data-ttu-id="f4276-205">Scegliere **Distribuisci Analysis Services Tutorial** dal menu [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]Compila **di**.</span><span class="sxs-lookup"><span data-stu-id="f4276-205">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="f4276-206">Dopo aver completato la distribuzione, passare alla scheda **Esplorazione** e fare clic sul pulsante **Riconnetti**.</span><span class="sxs-lookup"><span data-stu-id="f4276-206">When deployment has successfully completed, switch to the **Browser** tab, click **Reconnect**.</span></span>  
  
3.  <span data-ttu-id="f4276-207">Fare clic sull'icona di Excel, quindi su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="f4276-207">Click the Excel icon, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="f4276-208">Nel riquadro **Elenco campi tabella pivot** espandere la cartella **Valori** per visualizzare i nuovi membri calcolati nella dimensione Measures.</span><span class="sxs-lookup"><span data-stu-id="f4276-208">In the **PivotTable Field List** pane, expand **Values** folder to view the new calculated members in the Measures dimension.</span></span>  
  
5.  <span data-ttu-id="f4276-209">Trascinare **Total Sales Amount** nell'area Valori e controllare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f4276-209">Drag the **Total Sales Amount** to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="f4276-210">Trascinare le misure **Internet Sales-Sales Amount** e **Reseller Sales-Sales Amount** dai gruppi di misure **Internet Sales** e **Reseller Sales** nell'area Valori.</span><span class="sxs-lookup"><span data-stu-id="f4276-210">Drag **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount** measures from the **Internet Sales** and **Reseller Sales** measure groups to the Values area.</span></span>  
  
     <span data-ttu-id="f4276-211">Si noti che la misura **Total Sales Amount** è la somma della misura **Internet Sales-Sales Amount** e della misura **Reseller Sales-Sales Amount** .</span><span class="sxs-lookup"><span data-stu-id="f4276-211">Notice that the **Total Sales Amount** measure is the sum of the **Internet Sales-Sales Amount** measure and the **Reseller Sales-Sales Amount** measure.</span></span>  
  
6.  <span data-ttu-id="f4276-212">Aggiungere la gerarchia definita dall'utente **Product Categories** all'area filtro dell'area **Filtro report** e filtrare i dati in base a **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="f4276-212">Add the **Product Categories** user-defined hierarchy to the filter area of the **Report Filter** area, and then filter the data by **Mountain Bikes**.</span></span>  
  
     <span data-ttu-id="f4276-213">Si noti che la misura **Total Sales Amount** viene calcolata per la categoria **Mountain Bikes** delle vendite di prodotti in base alle misure **Internet Sales-Sales Amount** e **Reseller Sales-Sales Amount** per **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="f4276-213">Notice that the **Total Sales Amount** measure is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
7.  <span data-ttu-id="f4276-214">Aggiungere la gerarchia definita dall'utente **Date.Calendar Date** all'area Etichette di riga e controllare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f4276-214">Add the **Date.Calendar Date** user-defined hierarchy to the Row labels area, and then review the results.</span></span>  
  
     <span data-ttu-id="f4276-215">Si noti che la misura **Total Sales Amount** per ogni anno di calendario viene calcolata per la categoria **Mountain Bikes** delle vendite di prodotti in base alle misure **Internet Sales-Sales Amount** e **Reseller Sales-Sales Amount** per **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="f4276-215">Notice that the **Total Sales Amount** measure for each calendar year is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
8.  <span data-ttu-id="f4276-216">Aggiungere le misure **Total GPM**, **Internet GPM**e **Reseller GPM** all'area Valori e controllare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f4276-216">Add the **Total GPM**, **Internet GPM**, and **Reseller GPM** measures to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="f4276-217">Si noti che il margine di profitto lordo per le vendite rivenditore è notevolmente inferiore rispetto alle vendite Internet, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="f4276-217">Notice that the gross profit margin for reseller sales is significantly lower than for sales over the Internet, as shown in the following image.</span></span>  
  
     <span data-ttu-id="f4276-218">![Vendite dei rivenditori visualizzate nel riquadro dei dati](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Vendite dei rivenditori visualizzate nel riquadro dei dati")</span><span class="sxs-lookup"><span data-stu-id="f4276-218">![Data pane showing reseller sales](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Data pane showing reseller sales")</span></span>  
  
9. <span data-ttu-id="f4276-219">Aggiungere le misure **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**e **Reseller Sales Ratio to All Products** all'area Valori.</span><span class="sxs-lookup"><span data-stu-id="f4276-219">Add the **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**, and **Reseller Sales Ratio to All Products** measures to the Values area.</span></span>  
  
     <span data-ttu-id="f4276-220">Si noti che il rapporto tra le vendite delle mountain bike e le vendite di tutti i prodotti è aumentato nel tempo per le vendite Internet, ma diminuisce nel tempo per le vendite rivenditore</span><span class="sxs-lookup"><span data-stu-id="f4276-220">Notice that the ratio of the sales of mountain bikes to all products has increased over time for Internet sales, but is decreasing over time for reseller sales.</span></span> <span data-ttu-id="f4276-221">e che il rapporto tra le vendite di mountain bike e le vendite di tutti i prodotti è inferiore per le vendite rivenditore rispetto alle vendite Internet.</span><span class="sxs-lookup"><span data-stu-id="f4276-221">Notice also that the ratio of the sale of mountain bikes to all products is lower from sales through resellers than it is for sales over the Internet.</span></span>  
  
10. <span data-ttu-id="f4276-222">Cambiare il filtro da **Mountain Bikes** a **Bikes**e controllare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f4276-222">Change the filter from **Mountain Bikes** to **Bikes**, and review the results.</span></span>  
  
     <span data-ttu-id="f4276-223">Si noti che il margine di profitto lordo per tutte le bici vendute tramite rivenditori è negativo, perché le bici da turismo e da corsa vengono vendute in perdita.</span><span class="sxs-lookup"><span data-stu-id="f4276-223">Notice that the gross profit margin for all bikes sold through resellers is negative, because touring bikes and road bikes are being sold at a loss.</span></span>  
  
11. <span data-ttu-id="f4276-224">Cambiare il filtro in **Accessories**e controllare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f4276-224">Change the filter to **Accessories**, and then review the results.</span></span>  
  
     <span data-ttu-id="f4276-225">Si noti che la vendita di accessori aumenta nel tempo, ma che tali vendite rappresentano solo una piccola frazione delle vendite totali.</span><span class="sxs-lookup"><span data-stu-id="f4276-225">Notice that the sale of accessories is increasing over time, but that these sales make up only a small fraction of total sales.</span></span> <span data-ttu-id="f4276-226">Si noti inoltre che il margine di profitto lordo per le vendite di accessori è più alto rispetto a quello delle bici.</span><span class="sxs-lookup"><span data-stu-id="f4276-226">Notice also that the gross profit margin for sales of accessories is higher than for bikes.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f4276-227">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="f4276-227">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f4276-228">Definizione dei set denominati</span><span class="sxs-lookup"><span data-stu-id="f4276-228">Defining Named Sets</span></span>](lesson-6-2-defining-named-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="f4276-229">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4276-229">See Also</span></span>  
 <span data-ttu-id="f4276-230">[Calcoli](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="f4276-230">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="f4276-231">[Calcoli nei modelli multidimensionali](multidimensional-models/calculations-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="f4276-231">[Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="f4276-232">Creare membri calcolati</span><span class="sxs-lookup"><span data-stu-id="f4276-232">Create Calculated Members</span></span>](multidimensional-models/create-calculated-members.md)  
  
  
