---
title: Definizione ed esplorazione degli indicatori KPI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 648b9a02-1278-4f11-b940-6f0de6a4042d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44febe6c6c5d432f0cdee43e8eaaa3401c54a2c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714720"
---
# <a name="defining-and-browsing-kpis"></a><span data-ttu-id="84c4e-102">Definizione ed esplorazione dei KPI</span><span class="sxs-lookup"><span data-stu-id="84c4e-102">Defining and Browsing KPIs</span></span>
  <span data-ttu-id="84c4e-103">Per definire gli indicatori di prestazioni chiave (KPI), è innanzitutto necessario definire un nome per l'indicatore KPI e il gruppo di misure a cui è associato.</span><span class="sxs-lookup"><span data-stu-id="84c4e-103">To define key performance indicators (KPIs), you first define a KPI name and the measure group to which the KPI is associated.</span></span> <span data-ttu-id="84c4e-104">Un indicatore KPI può essere associato a tutti i gruppi di misure o a un unico gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="84c4e-104">A KPI can be associated with all measure groups or with a single measure group.</span></span> <span data-ttu-id="84c4e-105">In seguito è possibile definire gli elementi seguenti dell'indicatore KPI:</span><span class="sxs-lookup"><span data-stu-id="84c4e-105">You then define the following elements of the KPI:</span></span>

-   <span data-ttu-id="84c4e-106">L'espressione valore</span><span class="sxs-lookup"><span data-stu-id="84c4e-106">The value expression</span></span>

     <span data-ttu-id="84c4e-107">Un'espressione valore è una misura fisica, ad esempio Vendite, una misura calcolata, ad esempio Profitto, o un calcolo definito all'interno dell'indicatore KPI utilizzando un'espressione MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="84c4e-107">A value expression is a physical measure such as Sales, a calculated measure such as Profit, or a calculation that is defined within the KPI by using a Multidimensional Expressions (MDX) expression.</span></span>

-   <span data-ttu-id="84c4e-108">L'espressione obiettivo</span><span class="sxs-lookup"><span data-stu-id="84c4e-108">The goal expression</span></span>

     <span data-ttu-id="84c4e-109">Un'espressione obiettivo è un valore, o un'espressione MDX che restituisce un valore, che definisce l'obiettivo della misura definita dall'espressione valore.</span><span class="sxs-lookup"><span data-stu-id="84c4e-109">A goal expression is a value, or an MDX expression that resolves to a value, that defines the target for the measure that the value expression defines.</span></span> <span data-ttu-id="84c4e-110">Ad esempio, un'espressione obiettivo potrebbe essere l'importo di aumento delle vendite o dei profitti che i responsabili di un'azienda desiderano ottenere.</span><span class="sxs-lookup"><span data-stu-id="84c4e-110">For example, a goal expression could be the amount by which the business managers of a company want to increase sales or profit.</span></span>

-   <span data-ttu-id="84c4e-111">L'espressione stato</span><span class="sxs-lookup"><span data-stu-id="84c4e-111">The status expression</span></span>

     <span data-ttu-id="84c4e-112">Un'espressione stato è un'espressione MDX utilizzata da [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] per valutare lo stato corrente dell'espressione valore rispetto all'espressione obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-112">A status expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current status of the value expression compared to the goal expression.</span></span> <span data-ttu-id="84c4e-113">Un'espressione obiettivo è un valore normalizzato compreso tra -1 e +1, dove -1 significa pessimo e +1 significa eccellente.</span><span class="sxs-lookup"><span data-stu-id="84c4e-113">A goal expression is a normalized value in the range of -1 to +1, where -1 is very bad, and +1 is very good.</span></span> <span data-ttu-id="84c4e-114">L'espressione stato viene visualizzata su un diagramma che consente di determinare facilmente lo stato dell'espressione valore rispetto all'espressione obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-114">The status expression displays a graphic to help you easily determine the status of the value expression compared to the goal expression.</span></span>

-   <span data-ttu-id="84c4e-115">L'espressione tendenza</span><span class="sxs-lookup"><span data-stu-id="84c4e-115">The trend expression</span></span>

     <span data-ttu-id="84c4e-116">Un'espressione tendenza è un'espressione MDX utilizzata da [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] per valutare la tendenza corrente dell'espressione valore rispetto all'espressione obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-116">A trend expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current trend of the value expression compared to the goal expression.</span></span> <span data-ttu-id="84c4e-117">L'espressione tendenza consente all'utente aziendale di determinare rapidamente se l'espressione valore sta migliorando o peggiorando relativamente all'espressione obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-117">The trend expression helps the business user to quickly determine whether the value expression is becoming better or worse relative to the goal expression.</span></span> <span data-ttu-id="84c4e-118">È possibile associare uno dei vari diagrammi all'espressione tendenza per consentire agli utenti aziendali di comprendere rapidamente la tendenza.</span><span class="sxs-lookup"><span data-stu-id="84c4e-118">You can associate one of several graphics with the trend expression to help business users be able to quickly understand the trend.</span></span>

 <span data-ttu-id="84c4e-119">Oltre a definire questi elementi per un indicatore KPI è possibile definire diverse proprietà di un indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="84c4e-119">In addition to these elements that you define for a KPI, you also define several properties of a KPI.</span></span> <span data-ttu-id="84c4e-120">Tali proprietà includono una cartella di visualizzazione, un KPI padre se l'indicatore KPI viene calcolato da altri KPI, il membro temporale corrente, se presente, il peso del KPI, se presente, e una descrizione del KPI.</span><span class="sxs-lookup"><span data-stu-id="84c4e-120">These properties include a display folder, a parent KPI if the KPI is computed from other KPIs, the current time member if there is one, the weight of the KPI if it has one, and a description of the KPI.</span></span>

> [!NOTE]
>  <span data-ttu-id="84c4e-121">Per altri esempi di indicatori KPI vedere quelli disponibili nella scheda Modelli nel riquadro Strumenti di calcolo oppure nel data warehouse di esempio **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-121">For more examples of KPIs, see the KPI examples on the Templates tab in the Calculation Tools pane or in the examples in the **Adventure Works DW 2012** sample data warehouse.</span></span> <span data-ttu-id="84c4e-122">Per altre informazioni su come installare questo database, vedere [Installare dati di esempio e progetti per l'esercitazione di modellazione multidimensionale di Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="84c4e-122">For more information about how to install this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

 <span data-ttu-id="84c4e-123">Nelle attività di questa lezione si definiranno gli indicatori KPI nel progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial, quindi si esplorerà il cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial utilizzando tali KPI.</span><span class="sxs-lookup"><span data-stu-id="84c4e-123">In the task in this lesson, you define  KPIs in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, and you then browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube by using these KPIs.</span></span> <span data-ttu-id="84c4e-124">Verranno definiti gli indicatori KPI seguenti:</span><span class="sxs-lookup"><span data-stu-id="84c4e-124">You will define the following KPIs:</span></span>

-   <span data-ttu-id="84c4e-125">Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="84c4e-125">Reseller Revenue</span></span>

     <span data-ttu-id="84c4e-126">Questo KPI viene utilizzato per misurare il confronto tra le vendite effettive del rivenditore e gli obiettivi di vendita per le vendite rivenditore, la prossimità delle vendite all'obiettivo e la tendenza al raggiungimento dell'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-126">This KPI is used to measure how actual reseller sales compare to sales quotas for reseller sales, how close the sales are to the goal, and what the trend is toward reaching the goal.</span></span>

-   <span data-ttu-id="84c4e-127">Product Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="84c4e-127">Product Gross Profit Margin</span></span>

     <span data-ttu-id="84c4e-128">Questo KPI viene utilizzato per stabilire la distanza del margine di profitto lordo relativo a ogni categoria di prodotto rispetto a un determinato obiettivo, nonché per individuare la tendenza verso il raggiungimento dell'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-128">This KPI is used to determine how close the gross profit margin is for each product category to a specified goal for each product category, and also to determine the trend toward reaching this goal.</span></span>

## <a name="defining-the-reseller-revenue-kpi"></a><span data-ttu-id="84c4e-129">Definizione del KPI Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="84c4e-129">Defining the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="84c4e-130">Aprire Progettazione cubi per il cubo di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial e fare clic sulla scheda **KPI** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-130">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **KPIs** tab.</span></span>

     <span data-ttu-id="84c4e-131">La scheda **KPI** include diversi riquadri.</span><span class="sxs-lookup"><span data-stu-id="84c4e-131">The **KPIs** tab includes several panes.</span></span> <span data-ttu-id="84c4e-132">Sul lato sinistro della scheda si trovano il riquadro **Libreria KPI** e il riquadro **Strumenti di calcolo** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-132">On the left side of the tab are the **KPI Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="84c4e-133">Il riquadro di visualizzazione posto nella parte intermedia della scheda contiene i dettagli relativi all'indicatore KPI selezionato nel riquadro **Libreria KPI** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-133">The display pane in the middle of the tab contains the details of the KPI that is selected in the **KPI Organizer** pane.</span></span>

     <span data-ttu-id="84c4e-134">Nella figura seguente viene illustrata la scheda **KPI** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="84c4e-134">The following image shows the **KPIs** tab of Cube Designer.</span></span>

     <span data-ttu-id="84c4e-135">![Scheda KPI di Progettazione cubi](../../2014/tutorials/media/l7-kpi-1.gif "Scheda KPI di Progettazione cubi")</span><span class="sxs-lookup"><span data-stu-id="84c4e-135">![KPIs tab of Cube Designer](../../2014/tutorials/media/l7-kpi-1.gif "KPIs tab of Cube Designer")</span></span>

2.  <span data-ttu-id="84c4e-136">Fare clic sul pulsante **Nuovo indicatore KPI** sulla barra degli strumenti della scheda **KPI** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-136">On the toolbar of the **KPIs** tab, click the **New KPI** button.</span></span>

     <span data-ttu-id="84c4e-137">Verrà visualizzato un modello KPI vuoto nel riquadro di visualizzazione, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="84c4e-137">A blank KPI template appears in the display pane, as shown in the following image.</span></span>

     <span data-ttu-id="84c4e-138">![Modello di indicatore KPI vuoto nel riquadro di visualizzazione](../../2014/tutorials/media/l7-kpi-2.gif "Modello di indicatore KPI vuoto nel riquadro di visualizzazione")</span><span class="sxs-lookup"><span data-stu-id="84c4e-138">![Blank KPI template in display pane](../../2014/tutorials/media/l7-kpi-2.gif "Blank KPI template in display pane")</span></span>

3.  <span data-ttu-id="84c4e-139">Nella casella **nome** Digitare `Reseller Revenue` e quindi selezionare **Reseller Sales** nell'elenco **gruppo di misure associato** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-139">In the **Name** box, type `Reseller Revenue`, and then select **Reseller Sales** in the **Associated measure group** list.</span></span>

4.  <span data-ttu-id="84c4e-140">Nella scheda **Metadati** del riquadro **Strumenti di calcolo** , espandere **Misure**e **Vendite rivenditore**e quindi trascinare la misura **Reseller Sales-Sales Amount** nella casella **Espressione valore** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-140">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Reseller Sales**, and then drag the **Reseller Sales-Sales Amount** measure to the **Value Expression** box.</span></span>

5.  <span data-ttu-id="84c4e-141">Nella scheda **Metadati** del riquadro **Strumenti di calcolo** , espandere **Misure**e **Sales Quotas**e trascinare la misura **Quote vendite** nella casella **Espressione obiettivo** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-141">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Sales Quotas**, and then drag the **Sales Amount Quota** measure to the **Goal Expression** box.</span></span>

6.  <span data-ttu-id="84c4e-142">Verificare che nell'elenco **Indicatore di stato** sia selezionata l'opzione **Misuratore** e quindi digitare l'espressione MDX seguente nella casella **Espressione stato** :</span><span class="sxs-lookup"><span data-stu-id="84c4e-142">Verify that **Gauge** is selected in the **Status indicator** list, and then type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
     When 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.95
       Then 1
     When
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")<.95
       And 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.85
       Then 0
      Else-1
    End
    ```

     <span data-ttu-id="84c4e-143">Questa espressione MDX rappresenta la base di valutazione del processo di raggiungimento dell'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-143">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span> <span data-ttu-id="84c4e-144">Se in questa espressione MDX le vendite rivenditore sono superiori all'85 percento dell'obiettivo viene utilizzato un valore 0 per popolare il diagramma scelto.</span><span class="sxs-lookup"><span data-stu-id="84c4e-144">In this MDX expression, if actual reseller sales are more than 85 percent of the goal, a value of 0 is used to populate the chosen graphic.</span></span> <span data-ttu-id="84c4e-145">Poiché il diagramma scelto è un misuratore, l'indicatore di misura al suo interno si troverà in posizione intermedia tra il livello superiore e il livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="84c4e-145">Because a gauge is the chosen graphic, the pointer in the gauge will be half-way between empty and full.</span></span> <span data-ttu-id="84c4e-146">Se le vendite rivenditore effettive superano il 90 percento, l'indicatore di misura del misuratore si troverà a tre quarti tra il livello superiore e il livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="84c4e-146">If actual reseller sales are more the 90 percent, the pointer on the gauge will be three-fourths of the way between empty and full.</span></span>

7.  <span data-ttu-id="84c4e-147">Verificare che nell'elenco **Indicatore di tendenza** sia selezionata l'opzione **Freccia standard** e quindi digitare l'espressione seguente nella casella **Espressione tendenza** :</span><span class="sxs-lookup"><span data-stu-id="84c4e-147">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following expression in the **Trend expression** box:</span></span>

    ```
    Case
     When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
     When  (
      KpiValue("Reseller Revenue") - 
       (KpiValue("Reseller Revenue"), 
        ParallelPeriod
         ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
          /
          (KpiValue ("Reseller Revenue"),
           ParallelPeriod
            ([Date].[Calendar Date].[Calendar Year],1,
             [Date].[Calendar Date].CurrentMember)))
           >=.02
      Then 1
       When(
        KpiValue("Reseller Revenue") - 
         (KpiValue ( "Reseller Revenue" ),
          ParallelPeriod
           ([Date].[Calendar Date].[Calendar Year],1,
            [Date].[Calendar Date].CurrentMember))
           /
            (KpiValue("Reseller Revenue"),
             ParallelPeriod
              ([Date].[Calendar Date].[Calendar Year],1,
                [Date].[Calendar Date].CurrentMember)))
            <=.02
      Then -1
       Else 0
    End
    ```

     <span data-ttu-id="84c4e-148">Questa espressione MDX rappresenta la base di valutazione della tendenza verso il raggiungimento dell'obiettivo definito.</span><span class="sxs-lookup"><span data-stu-id="84c4e-148">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-reseller-revenue-kpi"></a><span data-ttu-id="84c4e-149">Esplorazione del cubo utilizzando l'indicatore KPI Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="84c4e-149">Browsing the Cube by Using the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="84c4e-150">Nel menu **Compila** di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]scegliere **Distribuisci Analysis Service Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-150">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="84c4e-151">Dopo che la distribuzione è stata completata, fare clic su **Visualizzazione Esplorazione** nella barra degli strumenti della scheda **KPI** e fare clic su **Riconnetti**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-151">When deployment has successfully completed, on the toolbar of the **KPIs** tab, click the **Browser View** button, and then click **Reconnect**.</span></span>

     <span data-ttu-id="84c4e-152">I misuratori di stato e di tendenza vengono visualizzati nel riquadro **Visualizzatore KPI** per le vendite rivenditore basate sui valori del membro predefinito di ogni dimensione, unitamente al valore relativo al valore e all'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-152">The status and trend gauges are displayed in the **KPI Browser** pane for reseller sales based on the values for the default member of each dimension, together with the value for the value and the goal.</span></span> <span data-ttu-id="84c4e-153">Il membro predefinito di ogni dimensione è il membro Totale del livello Totale, perché non sono stati definiti altri membri di altre dimensioni come membro predefinito.</span><span class="sxs-lookup"><span data-stu-id="84c4e-153">The default member of each dimension is the All member of the All level, because you have not defined any other member of any dimension as the default member.</span></span>

3.  <span data-ttu-id="84c4e-154">Nel riquadro Filtro selezionare **Sales Territory** nell'elenco **Dimensione** , selezionare **Sales Territories** nell'elenco **Gerarchia** , selezionare **Uguale a** nell'elenco **Operatore** , selezionare la casella di controllo **America del Nord** nell'elenco **Espressione filtro** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-154">In the filter pane, select **Sales Territory** in the **Dimension** list, select **Sales Territories** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **North America** check box in the **Filter Expression** list, and then click **OK**.</span></span>

4.  <span data-ttu-id="84c4e-155">Nella riga successiva del riquadro **Filtro** selezionare **Date** nell'elenco **Dimensione** , selezionare **Calendar Date** nell'elenco **Gerarchia** , selezionare **Uguale a** nell'elenco **Operatore** , selezionare la casella di controllo **Q3 CY 2007** nell'elenco **Espressione filtro** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-155">In the next row in the **Filter** pane, select **Date** in the **Dimension** list, select **Calendar Date** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **Q3 CY 2007** check box in the **Filter Expression** list, and then click **OK**.</span></span>

5.  <span data-ttu-id="84c4e-156">Fare clic in un punto qualsiasi del riquadro **Visualizzatore KPI** per aggiornare i valori di **Reseller Revenue KPI**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-156">Click anywhere in the **KPI Browser** pane to update the values for the **Reseller Revenue KPI**.</span></span>

     <span data-ttu-id="84c4e-157">Si noti che le sezioni **Valore**, **Obiettivo**e **Stato** dell'indicatore KPI riflettono i valori del nuovo periodo temporale.</span><span class="sxs-lookup"><span data-stu-id="84c4e-157">Notice that the **Value**, **Goal**, and **Status** sections of the KPI reflect the values for the new time period</span></span>

## <a name="defining-the-product-gross-profit-margin-kpi"></a><span data-ttu-id="84c4e-158">Definizione dell'indicatore KPI Product Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="84c4e-158">Defining the Product Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="84c4e-159">Fare clic sul pulsante **Visualizzazione Form** nella barra degli strumenti della scheda **KPI** e fare clic sul pulsante **Nuovo indicatore KPI** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-159">Click the **Form View** button on the toolbar of the **KPIs** tab, and then click the **New KPI** button.</span></span>

2.  <span data-ttu-id="84c4e-160">Nella casella **nome** Digitare `Product Gross Profit Margin` , quindi verificare che **\<All>** venga visualizzato nell'elenco gruppo di **misure associato** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-160">In the **Name** box, type `Product Gross Profit Margin`, and then verify that **\<All>** appears in the **Associated measure group** list.</span></span>

3.  <span data-ttu-id="84c4e-161">Nella scheda **Metadati** del riquadro **Strumenti di calcolo** trascinare la misura **Total GPM** nella casella **Espressione valore** .</span><span class="sxs-lookup"><span data-stu-id="84c4e-161">In the **Metadata** tab in the **Calculation Tools** pane, drag the **Total GPM** measure to the **Value Expression** box.</span></span>

4.  <span data-ttu-id="84c4e-162">Nella casella **Espressione obiettivo** digitare l'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="84c4e-162">In the **Goal Expression** box, type the following expression:</span></span>

    ```
    Case
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Accessories]
        Then .40                 
        When [Product].[Category].CurrentMember 
          Is [Product].[Category].[Bikes]
        Then .12                
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Clothing]
        Then .20
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Components]
        Then .10
        Else .12            
    End
    ```

5.  <span data-ttu-id="84c4e-163">Nell'elenco **Indicatore di stato** selezionare l'opzione **Cilindro**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-163">In the **Status indicator** list, select **Cylinder**.</span></span>

6.  <span data-ttu-id="84c4e-164">Digitare l'espressione MDX seguente nella casella **Espressione stato** :</span><span class="sxs-lookup"><span data-stu-id="84c4e-164">Type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .90
        Then 1
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) <  .90
             And 
             KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .80
        Then 0
        Else -1
    End
    ```

     <span data-ttu-id="84c4e-165">Questa espressione MDX rappresenta la base di valutazione del processo di raggiungimento dell'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="84c4e-165">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span>

7.  <span data-ttu-id="84c4e-166">Verificare che nell'elenco **Indicatore di tendenza** sia selezionata l'opzione **Freccia standard** , quindi digitare l'espressione MDX seguente nella casella **Espressione tendenza** :</span><span class="sxs-lookup"><span data-stu-id="84c4e-166">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following MDX expression in the **Trend expression** box:</span></span>

    ```
    Case
    When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
       When VBA!Abs
        (
          KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            ) /
            (
              KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            )  
          ) <=.02
      Then 0
      When KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[ Calendar Date].[ Calendar Year],
               1,
               [Date].[ Calendar Date].CurrentMember
             )
           ) /
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[Calendar Date].[Calendar Year],
               1,
               [Date].[Calendar Date].CurrentMember
             )
           )  >.02
      Then 1
      Else -1
    End
    ```

     <span data-ttu-id="84c4e-167">Questa espressione MDX rappresenta la base di valutazione della tendenza verso il raggiungimento dell'obiettivo definito.</span><span class="sxs-lookup"><span data-stu-id="84c4e-167">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-total-gross-profit-margin-kpi"></a><span data-ttu-id="84c4e-168">Esplorazione del cubo utilizzando l'indicatore KPI Total Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="84c4e-168">Browsing the Cube by Using the Total Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="84c4e-169">Scegliere **Distribuisci Analysis Services Tutorial** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-169">On the **Build** menu, click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="84c4e-170">Quando la distribuzione ha avuto esito positivo, fare clic su **Riconnetti** nella barra degli strumenti della scheda **KPI** e scegliere **Visualizzazione Esplorazione**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-170">When deployment has successfully completed, click **Reconnect** on the toolbar of the **KPIs** tab, and then click **Browser View**.</span></span>

     <span data-ttu-id="84c4e-171">`Product Gross Profit Margin`Viene visualizzato l'indicatore KPI e viene visualizzato il valore KPI per **Q3 CY 2007** e il **America del Nord** Sales Territory.</span><span class="sxs-lookup"><span data-stu-id="84c4e-171">The `Product Gross Profit Margin` KPI appears and displays the KPI value for **Q3 CY 2007** and the **North America** sales territory.</span></span>

3.  <span data-ttu-id="84c4e-172">Nel riquadro **Filtro** selezionare **Product** nell'elenco **Dimensione** , selezionare **Category** nell'elenco **Gerarchia** , selezionare **Uguale a** nell'elenco **Operatore** , quindi selezionare **Bikes** nell'elenco **Espressione filtro** e infine fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84c4e-172">In the **Filter** pane, select **Product** in the **Dimension** list, select **Category** in the **Hierarchy** list, select **Equal** in the **Operator** list, and then select **Bikes** in the **Filter Expression** list, and then click **OK**.</span></span>

     <span data-ttu-id="84c4e-173">Verrà visualizzato il margine di profitto lordo per le biciclette vendute dai rivenditori in America del Nord nel terzo trimestre dell'anno di calendario 2007.</span><span class="sxs-lookup"><span data-stu-id="84c4e-173">The gross profit margin for the sale of Bikes by resellers in North America in Q3 CY 2007 appears.</span></span>

## <a name="next-lesson"></a><span data-ttu-id="84c4e-174">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="84c4e-174">Next Lesson</span></span>
 [<span data-ttu-id="84c4e-175">Lezione 8: Definizione di azioni</span><span class="sxs-lookup"><span data-stu-id="84c4e-175">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)


