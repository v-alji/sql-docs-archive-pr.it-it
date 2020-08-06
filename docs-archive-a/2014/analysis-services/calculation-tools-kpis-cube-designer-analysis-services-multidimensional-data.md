---
title: Strumenti di calcolo (scheda KPI, Progettazione cubi) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpisview.calculationtoolspane.f1
ms.assetid: c030c725-7763-4c23-9988-4b274a88fc31
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bb8470173b0a413795fb7b5e3213bb50aa8ee43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625785"
---
# <a name="calculation-tools-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="38d8b-102">Strumenti di calcolo (scheda KPI, Progettazione cubi) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="38d8b-102">Calculation Tools (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="38d8b-103">Usare il riquadro **Strumenti di calcolo** della scheda **KPI** in Progettazione cubi per esaminare i metadati, le funzioni e i modelli disponibili per gli indicatori di prestazioni chiave (KPI).</span><span class="sxs-lookup"><span data-stu-id="38d8b-103">Use the **Calculation Tools** pane on the **KPIs** tab in Cube Designer to explore metadata, functions, and templates available for use in Key Performance Indicators (KPIs).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38d8b-104">Questo riquadro viene visualizzato solo in visualizzazione Form.</span><span class="sxs-lookup"><span data-stu-id="38d8b-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="38d8b-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="38d8b-105">Options</span></span>  
 <span data-ttu-id="38d8b-106">**Metadata**</span><span class="sxs-lookup"><span data-stu-id="38d8b-106">**Metadata**</span></span>  
 <span data-ttu-id="38d8b-107">Consente di visualizzare i metadati relativi al cubo selezionato.</span><span class="sxs-lookup"><span data-stu-id="38d8b-107">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="38d8b-108">Trascinare un elemento selezionato nel riquadro **Editor form KPI** per includere la sintassi MDX (Multidimensional Expression) per questo elemento in corrispondenza del percorso specificato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="38d8b-108">Drag a selected element to the **KPI Form Editor** pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="38d8b-109">**Funzioni**</span><span class="sxs-lookup"><span data-stu-id="38d8b-109">**Functions**</span></span>  
 <span data-ttu-id="38d8b-110">Consente di visualizzare le funzioni disponibili per espressioni e condizioni.</span><span class="sxs-lookup"><span data-stu-id="38d8b-110">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="38d8b-111">Trascinare un elemento selezionato nel riquadro **Editor form KPI** per includere la sintassi MDX per questo elemento in corrispondenza della posizione specificata nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="38d8b-111">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38d8b-112">In modalità progetto, tramite la finestra di dialogo **Strumenti di calcolo** è possibile leggere le informazioni relative all'opzione da un file XML denominato MDXFunctions.xml, incluso in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38d8b-112">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="38d8b-113">In modalità online, le informazioni relative all'opzione vengono recuperate dal set di righe dello schema MDSCHEMA_FUNCTIONS relativo all'istanza.</span><span class="sxs-lookup"><span data-stu-id="38d8b-113">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="38d8b-114">**Modelli**</span><span class="sxs-lookup"><span data-stu-id="38d8b-114">**Templates**</span></span>  
 <span data-ttu-id="38d8b-115">Consente di visualizzare i modelli predefiniti disponibili per gli indicatori KPI.</span><span class="sxs-lookup"><span data-stu-id="38d8b-115">Displays the predefined templates available for KPIs.</span></span>  
  
 <span data-ttu-id="38d8b-116">Trascinare un elemento selezionato nel riquadro **Editor form KPI** per includere la sintassi MDX per questo elemento in corrispondenza della posizione specificata nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="38d8b-116">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="38d8b-117">Menu di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="38d8b-117">Context Menu</span></span>  
 <span data-ttu-id="38d8b-118">Nel menu di scelta rapida che viene visualizzato quando si fa clic con il pulsante destro del mouse su un elemento del riquadro **Strumenti di calcolo** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38d8b-118">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="38d8b-119">**Copia**</span><span class="sxs-lookup"><span data-stu-id="38d8b-119">**Copy**</span></span>  
 <span data-ttu-id="38d8b-120">Selezionare questa opzione per copiare negli Appunti l'elemento specificato in **Metadati** o **Funzioni** .</span><span class="sxs-lookup"><span data-stu-id="38d8b-120">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38d8b-121"> Questa opzione non viene visualizzata se si seleziona **Modelli** .</span><span class="sxs-lookup"><span data-stu-id="38d8b-121">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38d8b-122"> Questa opzione è disabilitata se non è possibile copiare il membro selezionato, ad esempio la cartella **Set** di una dimensione visualizzata in **Metadati** o la cartella del gruppo di funzioni relativa alla funzione visualizzata in **Funzioni**.</span><span class="sxs-lookup"><span data-stu-id="38d8b-122">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="38d8b-123">**Filtra membri**</span><span class="sxs-lookup"><span data-stu-id="38d8b-123">**Filter Members**</span></span>  
 <span data-ttu-id="38d8b-124">Selezionare questa opzione per visualizzare la finestra di dialogo **Filtra membri** e filtrare i membri visualizzati per l'elemento selezionato in **Metadati**.</span><span class="sxs-lookup"><span data-stu-id="38d8b-124">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="38d8b-125">Per altre informazioni sulla finestra di dialogo **Filtra membri** vedere [Finestra di dialogo Filtra membri &#40;Analysis Services - Dati multidimensionali&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="38d8b-125">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38d8b-126"> Questa opzione viene visualizzata solo se si seleziona **Metadati** .</span><span class="sxs-lookup"><span data-stu-id="38d8b-126">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38d8b-127"> Questa opzione è attivata solo se si seleziona un livello per un attributo in **Metadati**.</span><span class="sxs-lookup"><span data-stu-id="38d8b-127">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="38d8b-128">**Aggiungi modello**</span><span class="sxs-lookup"><span data-stu-id="38d8b-128">**Add Template**</span></span>  
 <span data-ttu-id="38d8b-129">Selezionare questa opzione per aggiungere un nuovo membro calcolato, set denominato o comando script in base al modello selezionato nello script del cubo e visualizzare il riquadro **Editor form KPI** in visualizzazione Form.</span><span class="sxs-lookup"><span data-stu-id="38d8b-129">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **KPI Form Editor** in form view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38d8b-130"> Questa opzione viene visualizzata solo se si seleziona **Metadati** .</span><span class="sxs-lookup"><span data-stu-id="38d8b-130">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d8b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38d8b-131">See Also</span></span>  
 <span data-ttu-id="38d8b-132">[Progettazione cubi &#40;Analysis Services-Dati multidimensionali&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="38d8b-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="38d8b-133">[Indicatori KPI &#40;Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="38d8b-133">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="38d8b-134">[Barra degli strumenti &#40;scheda KPI, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="38d8b-134">[Toolbar &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="38d8b-135">[Libreria KPI &#40;scheda KPI, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="38d8b-135">[KPI Organizer &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="38d8b-136">[Editor form KPI &#40;scheda KPI, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="38d8b-136">[KPI Form Editor &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="38d8b-137">Visualizzatore KPI &#40;scheda KPI, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="38d8b-137">KPI Browser &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpi-browser-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)  
  
  
