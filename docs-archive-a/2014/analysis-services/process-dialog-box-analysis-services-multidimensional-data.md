---
title: Finestra di dialogo elabora (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processdialog.f1
ms.assetid: c065248c-9001-4f0c-928f-9c59eccb618b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 369c121713894bba9b2ce6c40aa2869de49eaa72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725040"
---
# <a name="process-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="ca609-102">Finestra di dialogo Elabora (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="ca609-102">Process Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ca609-103">Utilizzare la finestra di dialogo **Elabora** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per elaborare oggetti di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca609-103">Use the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to process [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects.</span></span> <span data-ttu-id="ca609-104">Per visualizzare la finestra di dialogo **Elabora** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , è possibile:</span><span class="sxs-lookup"><span data-stu-id="ca609-104">You can display the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] by:</span></span>  
  
-   <span data-ttu-id="ca609-105">Fare clic con il pulsante destro del mouse su una struttura di data mining, una dimensione, un cubo o un progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in **Esplora soluzioni** e scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="ca609-105">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, cube, dimension, or mining structure in **Solution Explorer** and selecting **Process**.</span></span>  
  
-   <span data-ttu-id="ca609-106">Selezionare **Elabora** dalla barra degli strumenti in qualsiasi pagina di **Progettazione cubi**o di **Progettazione dimensioni**oppure nelle pagine **Struttura di dati mining** e **Modelli di dati mining** di **Progettazione modelli di dati mining**.</span><span class="sxs-lookup"><span data-stu-id="ca609-106">Selecting **Process** from the toolbar on every page of **Cube Designer**, every page of **Dimension Designer**, or the **Mining Structure** and **Mining Models** pages of **Data Mining Model Designer**.</span></span>  
  
-   <span data-ttu-id="ca609-107">Fare clic con il pulsante destro del mouse su un modello di data mining nella pagina **Modelli di data mining** di **Progettazione modelli di data mining** e scegliere **Elabora struttura di data mining e tutti i modelli** o **Elabora modello**.</span><span class="sxs-lookup"><span data-stu-id="ca609-107">Right-clicking a mining model in the **Mining Models** page of **Data Mining Model Designer** and selecting **Process Mining Structure and All Models** or **Process Model**.</span></span>  
  
 <span data-ttu-id="ca609-108">Per visualizzare la finestra di dialogo **Elabora** in **SQL Server Management Studio** , è possibile:</span><span class="sxs-lookup"><span data-stu-id="ca609-108">You can display the **Process** dialog box in **SQL Server Management Studio** by:</span></span>  
  
-   <span data-ttu-id="ca609-109">Fare clic con il pulsante destro del mouse su un modello di data mining, una struttura di data mining, una dimensione, una partizione, un gruppo di misure, un cubo o un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in **Esplora oggetti** e scegliere **Elabora**.</span><span class="sxs-lookup"><span data-stu-id="ca609-109">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, cube, measure group, partition, dimension, mining structure, or mining model in **Object Explorer** and selecting **Process**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ca609-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ca609-110">Options</span></span>  
 <span data-ttu-id="ca609-111">**Elenco oggetti**</span><span class="sxs-lookup"><span data-stu-id="ca609-111">**Object list**</span></span>  
 <span data-ttu-id="ca609-112">Consente di selezionare gli oggetti di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] da elaborare, nonché le opzioni di elaborazione e le impostazioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="ca609-112">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects to be processed and the processing options and settings to be applied.</span></span> <span data-ttu-id="ca609-113">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca609-113">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="ca609-114">**nome oggetto**</span><span class="sxs-lookup"><span data-stu-id="ca609-114">**Object Name**</span></span>  
 <span data-ttu-id="ca609-115">Consente di visualizzare il nome dell'oggetto da elaborare.</span><span class="sxs-lookup"><span data-stu-id="ca609-115">Displays the name of the object to be processed.</span></span> <span data-ttu-id="ca609-116">L'icona a sinistra del nome indica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="ca609-116">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="ca609-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ca609-117">**Type**</span></span>  
 <span data-ttu-id="ca609-118">Consente di visualizzare il tipo dell'oggetto da elaborare.</span><span class="sxs-lookup"><span data-stu-id="ca609-118">Displays the type of the object to be processed.</span></span>  
  
 <span data-ttu-id="ca609-119">**Opzioni elaborazione**</span><span class="sxs-lookup"><span data-stu-id="ca609-119">**Process Options**</span></span>  
 <span data-ttu-id="ca609-120">Consente di selezionare il tipo di elaborazione da eseguire sull'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="ca609-120">Select the type of processing to perform on the selected object.</span></span> <span data-ttu-id="ca609-121">Per ulteriori informazioni sulle opzioni di elaborazione disponibili, vedere [elaborazione di oggetti del modello multidimensionale](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ca609-121">For more information about available processing options, see [Multidimensional Model Object Processing](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
 <span data-ttu-id="ca609-122">**Impostazioni**</span><span class="sxs-lookup"><span data-stu-id="ca609-122">**Settings**</span></span>  
 <span data-ttu-id="ca609-123">Consente di visualizzare il collegamento ipertestuale **Configura** al momento della selezione di **Elaborazione incrementale** in **Opzioni elaborazione** per cubi, gruppi di misure o partizioni.</span><span class="sxs-lookup"><span data-stu-id="ca609-123">Displays the **Configure** hyperlink when you choose **Process Incremental** in **Process Options** for cubes, measure groups, or partitions.</span></span> <span data-ttu-id="ca609-124">Per aprire la finestra di dialogo **Aggiornamento incrementale** , fare clic su **Configura** .</span><span class="sxs-lookup"><span data-stu-id="ca609-124">Click **Configure** to launch the **Incremental Update** dialog box.</span></span> <span data-ttu-id="ca609-125">Per altre informazioni sulla finestra di dialogo **Aggiornamento incrementale**, vedere [Finestra di dialogo Aggiornamento incrementale &#40;Analysis Services - Dati multidimensionali&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ca609-125">For more information about the **Incremental Update** dialog box, see [Incremental Update Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ca609-126">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="ca609-126">**Remove**</span></span>  
 <span data-ttu-id="ca609-127">Fare clic su questo pulsante per rimuovere gli elementi selezionati da **Elenco oggetti**.</span><span class="sxs-lookup"><span data-stu-id="ca609-127">Click to remove the selected items from **Object list**.</span></span>  
  
 <span data-ttu-id="ca609-128">**Analisi di impatto**</span><span class="sxs-lookup"><span data-stu-id="ca609-128">**Impact Analysis**</span></span>  
 <span data-ttu-id="ca609-129">Fare clic su questo pulsante per aprire la finestra di dialogo **Analisi di impatto** e visualizzare gli oggetti interessati dall'attività di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="ca609-129">Click to open the **Impact Analysis** dialog box and display the objects that will be affected by the processing task.</span></span> <span data-ttu-id="ca609-130">Per altre informazioni sulla finestra di dialogo **Analisi di impatto**, vedere [Finestra di dialogo Analisi di impatto &#40;Analysis Services - Dati multidimensionali&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ca609-130">For more information about the **Impact Analysis** dialog box, see [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca609-131">Questa opzione è disabilitata quando si seleziona l'opzione **Elabora oggetti interessati** nella finestra di dialogo **Cambia impostazioni** .</span><span class="sxs-lookup"><span data-stu-id="ca609-131">This option is disabled when the **Process affected objects** option is selected in the **Change Settings** dialog box.</span></span>  
  
 <span data-ttu-id="ca609-132">**Modifica impostazioni**</span><span class="sxs-lookup"><span data-stu-id="ca609-132">**Change Settings**</span></span>  
 <span data-ttu-id="ca609-133">Fare clic su questo pulsante per aprire la finestra di dialogo **Cambia impostazioni** e modificare le impostazioni che controllano l'elaborazione degli oggetti selezionati, incluse quelle relative a writeback, elaborazione batch ed errori di chiave della dimensione.</span><span class="sxs-lookup"><span data-stu-id="ca609-133">Click to open the **Change Settings** dialog box and change the settings that govern processing of the selected objects, including batch processing settings, writeback settings, and dimension key error settings.</span></span> <span data-ttu-id="ca609-134">Per altre informazioni sulla finestra di dialogo **Cambia impostazioni**, vedere [Finestra di dialogo Cambia impostazioni &#40;Analysis Services - Dati multidimensionali&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ca609-134">For more information about the **Change Settings** dialog box, see [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ca609-135">**Esegui**</span><span class="sxs-lookup"><span data-stu-id="ca609-135">**Run**</span></span>  
 <span data-ttu-id="ca609-136">Fare clic su questo pulsante per elaborare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="ca609-136">Click to process the objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca609-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca609-137">See Also</span></span>  
 <span data-ttu-id="ca609-138">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ca609-138">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ca609-139">Finestra di dialogo Stato elaborazione &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="ca609-139">Process Progress Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-progress-dialog-box-analysis-services-multidimensional-data.md)  
  
  
