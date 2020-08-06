---
title: Selezione metodo di creazione (creazione guidata dimensione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensiondefinition.f1
ms.assetid: 291b0b2d-a03a-4df6-82f7-90ad92d4d1cf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6338a0bde7865482fb7a98d7ec36ba5a71feb806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712532"
---
# <a name="select-creation-method-dimension-wizard"></a><span data-ttu-id="3fce7-102">Seleziona metodo di creazione (Creazione guidata dimensione)</span><span class="sxs-lookup"><span data-stu-id="3fce7-102">Select Creation Method (Dimension Wizard)</span></span>
  <span data-ttu-id="3fce7-103">Usare la pagina **Seleziona metodo di creazione** per scegliere la modalità di creazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="3fce7-103">Use the **Select Creation Method** page to select how to create the dimension.</span></span>  
  
 <span data-ttu-id="3fce7-104">**Per aprire la Creazione guidata dimensione.**</span><span class="sxs-lookup"><span data-stu-id="3fce7-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="3fce7-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]fare clic con il pulsante destro del mouse sulla cartella **Dimensioni**in **Esplora soluzioni** per scegliere un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , quindi fare clic su **Nuova dimensione**.</span><span class="sxs-lookup"><span data-stu-id="3fce7-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3fce7-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3fce7-106">Options</span></span>  
 <span data-ttu-id="3fce7-107">**Utilizza una tabella esistente**</span><span class="sxs-lookup"><span data-stu-id="3fce7-107">**Use an existing table**</span></span>  
 <span data-ttu-id="3fce7-108">Creare una dimensione da una o più tabelle in un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3fce7-108">Create a dimension from one or more tables in a data source.</span></span> <span data-ttu-id="3fce7-109">Gli attributi disponibili per la dimensione dipenderanno dalla struttura dei dati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="3fce7-109">The attributes that are available for the dimension will depend on the structure of the data in the table.</span></span>  
  
 <span data-ttu-id="3fce7-110">Per altre informazioni, vedere [Creare una dimensione utilizzando una tabella esistente](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span><span class="sxs-lookup"><span data-stu-id="3fce7-110">For more information, see [Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span></span>  
  
 <span data-ttu-id="3fce7-111">**Genera una tabella dei tempi nell'origine dei dati**</span><span class="sxs-lookup"><span data-stu-id="3fce7-111">**Generate a time table in the data source**</span></span>  
 <span data-ttu-id="3fce7-112">Creare una tabella dei tempi nell'origine dei dati sottostanti, quindi utilizzare tale tabella per creare una dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="3fce7-112">Create a time table in the underlying data source and then use that table to create a time dimension.</span></span> <span data-ttu-id="3fce7-113">Utilizzare questa opzione quando non esiste tale tabella e non si vuole utilizzare uno script per crearne una.</span><span class="sxs-lookup"><span data-stu-id="3fce7-113">Use this option when no such table exists and you do not want to use a script to create one.</span></span> <span data-ttu-id="3fce7-114">La nuova tabella dei tempi conterrà i dati per l'intervallo di dati, gli attributi e i calendari specificati nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="3fce7-114">The new time table will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fce7-115">Per utilizzare questa opzione, si deve disporre delle autorizzazioni per creare gli oggetti nell'origine dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="3fce7-115">To use this option, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="3fce7-116">Se non si hanno le autorizzazioni per creare oggetti sull'origine dati, provare a usare in alternativa l'opzione **Genera una tabella dei tempi nel server** .</span><span class="sxs-lookup"><span data-stu-id="3fce7-116">If you do not have permission to create objects on the data source, try to use the **Generate a time table on the server** option instead.</span></span>  
  
 <span data-ttu-id="3fce7-117">Per altre informazioni, vedere [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md)(Creare una dimensione temporale generando una tabella dei tempi).</span><span class="sxs-lookup"><span data-stu-id="3fce7-117">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="3fce7-118">**Genera una tabella dei tempi nel server**</span><span class="sxs-lookup"><span data-stu-id="3fce7-118">**Generate a time table on the server**</span></span>  
 <span data-ttu-id="3fce7-119">Crea una tabella dei tempi direttamente nel server, quindi utilizzare tale tabella per creare una dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="3fce7-119">Create a time table directly on the server and then use that table to create a time dimension.</span></span> <span data-ttu-id="3fce7-120">Utilizzare questa opzione se non si dispone delle autorizzazioni per creare oggetti nell'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="3fce7-120">Use this option if you do not have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="3fce7-121">La nuova dimensione temporale conterrà i dati per l'intervallo di dati, gli attributi e i calendari che si specificano nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="3fce7-121">The new time dimension will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
 <span data-ttu-id="3fce7-122">Per altre informazioni, vedere [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md)(Creare una dimensione temporale generando una tabella dei tempi).</span><span class="sxs-lookup"><span data-stu-id="3fce7-122">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="3fce7-123">**Genera una tabella diversa dalla tabella dei tempi nell'origine dati**</span><span class="sxs-lookup"><span data-stu-id="3fce7-123">**Generate a non-time table in the data source**</span></span>  
 <span data-ttu-id="3fce7-124">Progetta la dimensione senza un'origine dati relazionale sottostante, quindi genera lo schema necessario per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3fce7-124">Design the dimension without an underlying relational data source, and then generate the necessary schema for the data source.</span></span> <span data-ttu-id="3fce7-125">Questo approccio è noto come modellizzazione dall'alto in basso.</span><span class="sxs-lookup"><span data-stu-id="3fce7-125">This approach is known as top-down modeling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fce7-126">Per utilizzare questa opzione, si deve disporre delle autorizzazioni per creare gli oggetti nell'origine dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="3fce7-126">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="3fce7-127">È possibile compilare la dimensione con o senza un modello.</span><span class="sxs-lookup"><span data-stu-id="3fce7-127">You can build the dimension with or without a template.</span></span> <span data-ttu-id="3fce7-128">Per creare la dimensione con un modello, selezionare il modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="3fce7-128">To build the dimension with a template, select the template from the **Template** list.</span></span>  
  
 <span data-ttu-id="3fce7-129">Per altre informazioni, vedere [Creare una dimensione generando una tabella non temporale nell'origine dati](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="3fce7-129">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span></span>  
  
 <span data-ttu-id="3fce7-130">**Modello**</span><span class="sxs-lookup"><span data-stu-id="3fce7-130">**Template**</span></span>  
 <span data-ttu-id="3fce7-131">Selezionare il modello che si desidera utilizzare per creare la dimensione.</span><span class="sxs-lookup"><span data-stu-id="3fce7-131">Select the template that you want to use to create the dimension.</span></span> <span data-ttu-id="3fce7-132">I modelli offrono un set completo di definizioni di attributi e gerarchie orientate ad applicazioni aziendali specifiche.</span><span class="sxs-lookup"><span data-stu-id="3fce7-132">Templates provide a complete set of attribute and hierarchy definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fce7-133">Questa opzione è disponibile solo quando l'opzione **Genera una tabella diversa dalla tabella dei tempi nell'origine dati** è stata selezionata.</span><span class="sxs-lookup"><span data-stu-id="3fce7-133">This option is only available when the **Generate a non-time table in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fce7-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fce7-134">See Also</span></span>  
 <span data-ttu-id="3fce7-135">[Guida sensibile al contesto della creazione guidata dimensione](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3fce7-135">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="3fce7-136">[Dimensioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3fce7-136">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3fce7-137">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="3fce7-137">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
