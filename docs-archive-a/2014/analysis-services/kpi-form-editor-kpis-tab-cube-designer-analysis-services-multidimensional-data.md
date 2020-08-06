---
title: Editor form KPI (scheda KPI, Progettazione cubi) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpidefinitionpane.f1
ms.assetid: 45c6453a-bbe2-4ca5-836e-c7ef11cfcb65
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c88d6fcec60634f37ddad8b6d0f5cb2124fa1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625655"
---
# <a name="kpi-form-editor-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="56daf-102">Editor form KPI (scheda KPI, Progettazione cubi) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="56daf-102">KPI Form Editor (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="56daf-103">Usare il riquadro **Editor form KPI** della scheda **KPI** in Progettazione cubi per creare o modificare l'indicatore di prestazioni chiave (KPI) selezionato.</span><span class="sxs-lookup"><span data-stu-id="56daf-103">Use the **KPI Form Editor** pane on the **KPIs** tab in Cube Designer to create or modify the selected Key Performance Indicator (KPI).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56daf-104">Questo riquadro viene visualizzato solo in visualizzazione Form.</span><span class="sxs-lookup"><span data-stu-id="56daf-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="56daf-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="56daf-105">Options</span></span>  
 <span data-ttu-id="56daf-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="56daf-106">**Name**</span></span>  
 <span data-ttu-id="56daf-107">Consente di digitare il nome dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-107">Type the name of the KPI.</span></span>  
  
 <span data-ttu-id="56daf-108">**Gruppo di misure associato**</span><span class="sxs-lookup"><span data-stu-id="56daf-108">**Associated measure group**</span></span>  
 <span data-ttu-id="56daf-109">Consente di selezionare il gruppo di misure associato all'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-109">Select the measure group associated with the KPI.</span></span> <span data-ttu-id="56daf-110">Queste informazioni possono essere utilizzate dall'applicazione client per determinare quali dimensioni sono disponibili quando l'utente visualizza l'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-110">The client application can use this information to determine which dimensions are available when the user browses this KPI.</span></span>  
  
 <span data-ttu-id="56daf-111">**Espressione valore**</span><span class="sxs-lookup"><span data-stu-id="56daf-111">**Value Expression**</span></span>  
 <span data-ttu-id="56daf-112">Espandere questa casella per visualizzare o modificare l'espressione MDX (Multidimensional Expression) per il valore dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-112">Expand to view or edit the Multidimensional Expressions (MDX) expression for the value of the KPI.</span></span>  
  
 <span data-ttu-id="56daf-113">Digitare l'espressione MDX che restituisce il valore dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-113">Type the MDX expression that returns the value of the KPI.</span></span>  
  
 <span data-ttu-id="56daf-114">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="56daf-114">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56daf-115">**Espressione obiettivo**</span><span class="sxs-lookup"><span data-stu-id="56daf-115">**Goal Expression**</span></span>  
 <span data-ttu-id="56daf-116">Espandere questa casella per visualizzare o modificare l'espressione MDX per il valore obiettivo dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-116">Expand to view or edit the MDX expression for the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="56daf-117">Digitare l'espressione MDX che restituisce il valore obiettivo dell'indicatore KPI quando questo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="56daf-117">Type the MDX expression that returns the goal value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="56daf-118">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="56daf-118">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56daf-119">**Status**</span><span class="sxs-lookup"><span data-stu-id="56daf-119">**Status**</span></span>  
 <span data-ttu-id="56daf-120">Espandere questa casella per visualizzare le opzioni **Icona stato** ed **Espressione stato** .</span><span class="sxs-lookup"><span data-stu-id="56daf-120">Expand to view the **Status graphic** and **Status expression** options.</span></span>  
  
 <span data-ttu-id="56daf-121">**Icona stato**</span><span class="sxs-lookup"><span data-stu-id="56daf-121">**Status graphic**</span></span>  
 <span data-ttu-id="56daf-122">Consente di selezionare l'icona che deve essere utilizzata dall'applicazione client per rappresentare graficamente il valore di stato.</span><span class="sxs-lookup"><span data-stu-id="56daf-122">Select the graphic to be used by the client application to represent the status value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56daf-123">L'applicazione client può supportare l'icona selezionata o sostituirla con un'alternativa adatta.</span><span class="sxs-lookup"><span data-stu-id="56daf-123">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="56daf-124">**Espressione stato**</span><span class="sxs-lookup"><span data-stu-id="56daf-124">**Status expression**</span></span>  
 <span data-ttu-id="56daf-125">Consente di digitare l'espressione MDX che restituisce il valore di stato dell'indicatore KPI quando questo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="56daf-125">Type the MDX expression that returns the status value of the KPI when the KPI is run.</span></span>  
  
 <span data-ttu-id="56daf-126">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="56daf-126">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56daf-127">È consigliabile che questa espressione restituisca un numero decimale compreso tra-1 e 1.</span><span class="sxs-lookup"><span data-stu-id="56daf-127">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="56daf-128">Un numero minore rappresenta una situazione negativa, mentre numero maggiore rappresenta una situazione positiva.</span><span class="sxs-lookup"><span data-stu-id="56daf-128">A lower number represents a negative situation, while a higher number represents a positive situation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56daf-129">I valori inferiori a-1 e superiori a 1 sono possibili ma non possono essere interpretati correttamente da applicazioni client di terze parti.</span><span class="sxs-lookup"><span data-stu-id="56daf-129">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="56daf-130">**Tendenza**</span><span class="sxs-lookup"><span data-stu-id="56daf-130">**Trend**</span></span>  
 <span data-ttu-id="56daf-131">Espandere questa casella per visualizzare le opzioni **Icona tendenza** ed **Espressione tendenza** .</span><span class="sxs-lookup"><span data-stu-id="56daf-131">Expand to view the **Trend graphic** and **Trend expression** options.</span></span>  
  
 <span data-ttu-id="56daf-132">**Icona tendenza**</span><span class="sxs-lookup"><span data-stu-id="56daf-132">**Trend graphic**</span></span>  
 <span data-ttu-id="56daf-133">Consente di selezionare l'icona che deve essere utilizzata dall'applicazione client per rappresentare graficamente il valore di tendenza.</span><span class="sxs-lookup"><span data-stu-id="56daf-133">Select the graphic to be used by the client application to represent the trend value in graphical form.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56daf-134">L'applicazione client può supportare l'icona selezionata o sostituirla con un'alternativa adatta.</span><span class="sxs-lookup"><span data-stu-id="56daf-134">The client application can support the selected graphic or replace it with an appropriate alternative.</span></span>  
  
 <span data-ttu-id="56daf-135">**Espressione tendenza**</span><span class="sxs-lookup"><span data-stu-id="56daf-135">**Trend expression**</span></span>  
 <span data-ttu-id="56daf-136">Consente di digitare l'espressione MDX che restituisce il valore di tendenza dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-136">Type the MDX expression that returns the trend value of the KPI.</span></span>  
  
 <span data-ttu-id="56daf-137">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="56daf-137">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56daf-138">L'espressione di tendenza può essere basata su qualsiasi criterio temporale adatto al contesto aziendale.</span><span class="sxs-lookup"><span data-stu-id="56daf-138">The trend expression can be based on any time-based criteria that makes sense in a given business context.</span></span> <span data-ttu-id="56daf-139">È consigliabile che questa espressione restituisca un numero decimale compreso tra-1 e 1.</span><span class="sxs-lookup"><span data-stu-id="56daf-139">It is recommended that this expression returns a decimal number between -1 and 1.</span></span> <span data-ttu-id="56daf-140">Un numero minore rappresenta una tendenza negativa nel tempo, mentre un numero maggiore rappresenta una tendenza positiva nel tempo.</span><span class="sxs-lookup"><span data-stu-id="56daf-140">A lower number represents a negative trend over time; a higher number represents a positive trend over time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56daf-141">I valori inferiori a-1 e superiori a 1 sono possibili ma non possono essere interpretati correttamente da applicazioni client di terze parti.</span><span class="sxs-lookup"><span data-stu-id="56daf-141">Values below -1 and above 1 are possible but may not be interpreted correctly by third-party client applications.</span></span>  
  
 <span data-ttu-id="56daf-142">**Proprietà aggiuntive**</span><span class="sxs-lookup"><span data-stu-id="56daf-142">**Additional Properties**</span></span>  
 <span data-ttu-id="56daf-143">Espandere questa casella per visualizzare le opzioni **Cartella di visualizzazione**, **KPI padre**, **Membro temporale corrente**, **Peso**e **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="56daf-143">Expand to view the **Display folder**, **Parent KPI**, **Current time member**, **Weight**, and **Description** options.</span></span>  
  
 <span data-ttu-id="56daf-144">**Cartella di visualizzazione**</span><span class="sxs-lookup"><span data-stu-id="56daf-144">**Display folder**</span></span>  
 <span data-ttu-id="56daf-145">Consente di digitare la categorizzazione dell'indicatore KPI che deve essere utilizzata dall'applicazione client per la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="56daf-145">Type the categorization of the KPI for use by the client application for display purposes.</span></span>  
  
 <span data-ttu-id="56daf-146">Usare una barra rovesciata (\\) per separare i nomi delle cartelle in una cartella di visualizzazione e il punto e virgola (;) per separare più cartelle di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="56daf-146">Use a backward slash (\\) to separate folder names in a display folder and a semicolon (;) to separate multiple display folders.</span></span> <span data-ttu-id="56daf-147">Ad esempio digitare `Category\Goal\Scientific;Category\Goal\Metric`.</span><span class="sxs-lookup"><span data-stu-id="56daf-147">For example, type `Category\Goal\Scientific;Category\Goal\Metric`.</span></span>  
  
 <span data-ttu-id="56daf-148">**KPI padre**</span><span class="sxs-lookup"><span data-stu-id="56daf-148">**Parent KPI**</span></span>  
 <span data-ttu-id="56daf-149">Consente di selezionare un indicatore KPI esistente sotto il quale categorizzare gli indicatori KPI che devono essere utilizzati dall'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="56daf-149">Select an existing KPI under which to categorize the KPI for use by the client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56daf-150">Se questa opzione è impostata su un indicatore KPI esistente, l'opzione **Cartella di visualizzazione** viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="56daf-150">If this option is set to an existing KPI, **Display folder** is ignored.</span></span>  
  
 <span data-ttu-id="56daf-151">**Membro temporale corrente**</span><span class="sxs-lookup"><span data-stu-id="56daf-151">**Current time member**</span></span>  
 <span data-ttu-id="56daf-152">Consente di digitare l'espressione MDX che restituisce il membro che identifica il contesto temporale dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-152">Type the MDX expression that returns the member that identifies the temporal context of the KPI.</span></span>  
  
 <span data-ttu-id="56daf-153">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="56daf-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56daf-154">L'espressione MDX deve restituire il nome univoco di un membro all'interno di una dimensione temporale associata al gruppo di misure specificato in **Gruppo di misure associato**.</span><span class="sxs-lookup"><span data-stu-id="56daf-154">The MDX expression must return the unique name of a member within a time dimension associated with the measure group specified in **Associated measure group**.</span></span>  
  
 <span data-ttu-id="56daf-155">**Weight**</span><span class="sxs-lookup"><span data-stu-id="56daf-155">**Weight**</span></span>  
 <span data-ttu-id="56daf-156">Espandere questa casella per visualizzare o modificare l'espressione MDX per il fattore di ponderazione dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-156">Expand to view or edit the MDX expression for the weighting factor of the KPI.</span></span>  
  
 <span data-ttu-id="56daf-157">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="56daf-157">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="56daf-158">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="56daf-158">**Description**</span></span>  
 <span data-ttu-id="56daf-159">Consente di digitare una descrizione facoltativa dell'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="56daf-159">Type the optional description of the KPI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56daf-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56daf-160">See Also</span></span>  
 [<span data-ttu-id="56daf-161">Indicatori KPI &#40;Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="56daf-161">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
