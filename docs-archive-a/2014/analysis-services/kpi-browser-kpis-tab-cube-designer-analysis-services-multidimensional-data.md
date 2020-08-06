---
title: Visualizzatore KPI (scheda KPI, Progettazione cubi) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpibrowserpane.f1
ms.assetid: 2f61bde6-e6ec-4511-8645-c272374014ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 591dfb7c27842e365b78484153dbbde3713b452e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625658"
---
# <a name="kpi-browser-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="ed014-102">Visualizzatore KPI (scheda KPI, Progettazione cubi) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="ed014-102">KPI Browser (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ed014-103">Usare il riquadro **Visualizzatore KPI** della scheda **KPI** in Progettazione cubi per visualizzare e testare i risultati degli indicatori di prestazioni chiave (KPI).</span><span class="sxs-lookup"><span data-stu-id="ed014-103">Use the **KPI Browser** pane on the **KPIs** tab in Cube Designer to view and test the results of Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="ed014-104">Prima di eseguire l' [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] esplorazione, gli indicatori KPI devono essere prima distribuiti in un' [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] istanza di.</span><span class="sxs-lookup"><span data-stu-id="ed014-104">KPIs must first be deployed to a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance before browsing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed014-105">Questo riquadro viene visualizzato solo nella visualizzazione Esplorazione.</span><span class="sxs-lookup"><span data-stu-id="ed014-105">This pane is displayed only in browser view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ed014-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ed014-106">Options</span></span>  
 <span data-ttu-id="ed014-107">**Griglia del sottocubo**</span><span class="sxs-lookup"><span data-stu-id="ed014-107">**Subcube grid**</span></span>  
 <span data-ttu-id="ed014-108">Usare questa opzione per definire un sottocubo e limitare i risultati degli indicatori KPI da visualizzare nel riquadro **Risultati** .</span><span class="sxs-lookup"><span data-stu-id="ed014-108">Use to define a subcube and restrict the results of the KPIs to be displayed in the **Results** pane.</span></span> <span data-ttu-id="ed014-109">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed014-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="ed014-110">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="ed014-110">**Dimension**</span></span>  
 <span data-ttu-id="ed014-111">Consente di selezionare la dimensione alla quale viene applicato il filtro.</span><span class="sxs-lookup"><span data-stu-id="ed014-111">Select the dimension to which this filter applies.</span></span>  
  
 <span data-ttu-id="ed014-112">**Gerarchia**</span><span class="sxs-lookup"><span data-stu-id="ed014-112">**Hierarchy**</span></span>  
 <span data-ttu-id="ed014-113">Consente di selezionare la gerarchia alla quale viene applicato il filtro.</span><span class="sxs-lookup"><span data-stu-id="ed014-113">Select the hierarchy to which this filter applies.</span></span>  
  
 <span data-ttu-id="ed014-114">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="ed014-114">**Operator**</span></span>  
 <span data-ttu-id="ed014-115">Consente di selezionare l'operatore che definisce il modo in cui l'espressione contenuta in **Espressione filtro** viene applicata alla gerarchia selezionata.</span><span class="sxs-lookup"><span data-stu-id="ed014-115">Select the operator that defines how the expression in **Filter Expression** is applied to the selected hierarchy.</span></span> <span data-ttu-id="ed014-116">Nella tabella seguente vengono descritti gli operatori disponibili.</span><span class="sxs-lookup"><span data-stu-id="ed014-116">The following table describes the available operators.</span></span>  
  
|<span data-ttu-id="ed014-117">Valore</span><span class="sxs-lookup"><span data-stu-id="ed014-117">Value</span></span>|<span data-ttu-id="ed014-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed014-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed014-119">**Uguale**</span><span class="sxs-lookup"><span data-stu-id="ed014-119">**Equal**</span></span>|<span data-ttu-id="ed014-120">I risultati sono limitati al set definito in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-120">The results are restricted to the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="ed014-121">**Diverso da**</span><span class="sxs-lookup"><span data-stu-id="ed014-121">**Not Equal**</span></span>|<span data-ttu-id="ed014-122">I risultati sono limitati ai membri esclusi dal set definito in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-122">The results are restricted to the members excluded by the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="ed014-123">**In**</span><span class="sxs-lookup"><span data-stu-id="ed014-123">**In**</span></span>|<span data-ttu-id="ed014-124">I risultati sono limitati al set denominato scelto in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-124">The results are restricted to the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="ed014-125">**Non incluso**</span><span class="sxs-lookup"><span data-stu-id="ed014-125">**Not In**</span></span>|<span data-ttu-id="ed014-126">I risultati sono limitati ai membri esclusi dal set denominato scelto in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-126">The results are restricted to the members excluded by the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="ed014-127">**Contiene**</span><span class="sxs-lookup"><span data-stu-id="ed014-127">**Contains**</span></span>|<span data-ttu-id="ed014-128">I risultati sono limitati ai membri i cui nomi contengono la stringa inclusa in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-128">The results are restricted to members whose member names contain the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="ed014-129">**Inizia con**</span><span class="sxs-lookup"><span data-stu-id="ed014-129">**Begins With**</span></span>|<span data-ttu-id="ed014-130">I risultati sono limitati ai membri i cui nomi iniziano con la stringa inclusa in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-130">The results are restricted to members whose member names begin with the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="ed014-131">**Intervallo (inclusivo)**</span><span class="sxs-lookup"><span data-stu-id="ed014-131">**Range (Inclusive)**</span></span>|<span data-ttu-id="ed014-132">I risultati sono limitati all'intervallo scelto in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-132">The results are restricted to the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="ed014-133">**Intervallo (esclusivo)**</span><span class="sxs-lookup"><span data-stu-id="ed014-133">**Range (Exclusive)**</span></span>|<span data-ttu-id="ed014-134">I risultati sono limitati ai membri esclusi dall'intervallo scelto in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-134">The results are restricted to the members excluded by the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="ed014-135">**MDX**</span><span class="sxs-lookup"><span data-stu-id="ed014-135">**MDX**</span></span>|<span data-ttu-id="ed014-136">I risultati sono limitati al set di espressioni MDX incluso in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="ed014-136">The results are restricted to the Multidimensional Expressions (MDX) expression set in **Filter Expression**.</span></span>|  
  
 <span data-ttu-id="ed014-137">**Espressione filtro**</span><span class="sxs-lookup"><span data-stu-id="ed014-137">**Filter Expression**</span></span>  
 <span data-ttu-id="ed014-138">Consente di digitare l'espressione che dovrà essere valutata da **Operatore**, che limita i risultati KPI da esplorare.</span><span class="sxs-lookup"><span data-stu-id="ed014-138">Type the expression that is to be evaluated by **Operator**, which restricts the KPI results to be browsed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed014-139">Questo campo rappresenta un elemento dinamico per l'immissione di dati, che cambia aspetto per riflettere i tipi di dati necessari per l'operatore selezionato.</span><span class="sxs-lookup"><span data-stu-id="ed014-139">This field is a dynamic data entry element, changing appearance to reflect the types of data necessary for the selected operator.</span></span>  
  
 <span data-ttu-id="ed014-140">**Griglia risultati**</span><span class="sxs-lookup"><span data-stu-id="ed014-140">**Results grid**</span></span>  
 <span data-ttu-id="ed014-141">Consente di visualizzare il valore valutato, l'obiettivo, lo stato e la tendenza per gli indicatori KPI, in base al filtro definito nella **Griglia filtri**.</span><span class="sxs-lookup"><span data-stu-id="ed014-141">Displays the evaluated value, goal, status, and trend for the KPIs, based on the filter defined in **Filter grid**.</span></span> <span data-ttu-id="ed014-142">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed014-142">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="ed014-143">**Visualizza struttura**</span><span class="sxs-lookup"><span data-stu-id="ed014-143">**Display Structure**</span></span>  
 <span data-ttu-id="ed014-144">Consente di visualizzare gli indicatori KPI contenuti nel cubo, organizzati gerarchicamente in base ai valori di **Cartella di visualizzazione** o di **KPI padre** per ogni indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="ed014-144">Displays the KPIs contained by the cube, hierarchically organized according to the **Display folder** or **Parent KPI** values for each KPI.</span></span>  
  
 <span data-ttu-id="ed014-145">**Valore**</span><span class="sxs-lookup"><span data-stu-id="ed014-145">**Value**</span></span>  
 <span data-ttu-id="ed014-146">Consente di visualizzare il valore dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="ed014-146">Displays the value of the KPI.</span></span>  
  
 <span data-ttu-id="ed014-147">**Obiettivo**</span><span class="sxs-lookup"><span data-stu-id="ed014-147">**Goal**</span></span>  
 <span data-ttu-id="ed014-148">Consente di visualizzare il valore dell'obiettivo dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="ed014-148">Displays the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="ed014-149">**Status**</span><span class="sxs-lookup"><span data-stu-id="ed014-149">**Status**</span></span>  
 <span data-ttu-id="ed014-150">Consente di visualizzare l'icona di stato dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="ed014-150">Displays the status graphic of the KPI.</span></span>  
  
 <span data-ttu-id="ed014-151">**Tendenza**</span><span class="sxs-lookup"><span data-stu-id="ed014-151">**Trend**</span></span>  
 <span data-ttu-id="ed014-152">Consente di visualizzare l'icona di tendenza dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="ed014-152">Displays the trend graphic of the KPI.</span></span>  
  
 <span data-ttu-id="ed014-153">**Weight**</span><span class="sxs-lookup"><span data-stu-id="ed014-153">**Weight**</span></span>  
 <span data-ttu-id="ed014-154">Consente di visualizzare il fattore di ponderazione dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="ed014-154">Displays the weight factor of the KPI.</span></span>  
  
 <span data-ttu-id="ed014-155">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ed014-155">**(Description)**</span></span>  
 <span data-ttu-id="ed014-156">Consente di visualizzare un'icona Informazioni se è disponibile una descrizione per un indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="ed014-156">Displays an information icon if a description is provided for a KPI.</span></span>  
  
 <span data-ttu-id="ed014-157">Fare passare il mouse sull'icona Informazioni per visualizzare una descrizione comando per l'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="ed014-157">Hover the mouse over the information icon to display a ToolTip containing the description for the KPI.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed014-158">Se viene generato un errore durante il calcolo di un indicatore KPI nell'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , questa opzione visualizza le informazioni associate all'errore.</span><span class="sxs-lookup"><span data-stu-id="ed014-158">If an error occurs while calculating a KPI on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, this option displays information associated with the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed014-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed014-159">See Also</span></span>  
 [<span data-ttu-id="ed014-160">Indicatori KPI &#40;Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="ed014-160">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
