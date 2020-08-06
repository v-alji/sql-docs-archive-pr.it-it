---
title: Impostazione tipo di dati e contenuto delle colonne (creazione guidata modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0634be64-4c38-4381-9b19-fe9a5889306c
author: minewiskan
ms.author: owend
ms.openlocfilehash: e22f46808877391376f721bcab55ea4fd9074186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627425"
---
# <a name="specify-column-content-and-data-type-data-mining-wizard"></a><span data-ttu-id="ac93e-102">Impostazione tipo di contenuto e dati delle colonne (Creazione guidata modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="ac93e-102">Specify Column Content and Data Type (Data Mining Wizard)</span></span>
  <span data-ttu-id="ac93e-103">Usare la pagina **Impostazione tipo di contenuto e dati delle colonne** per specificare l'uso e il tipo di dati di ogni colonna selezionata nella pagina precedente della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="ac93e-103">Use the **Specify Column Content and Data Type** page to specify the usage and data type for each column that you selected on the previous page of the wizard.</span></span> <span data-ttu-id="ac93e-104">Per ignorare la colonna, fare clic su **Indietro** per tornare alla pagina **Impostazione dati di training**e deselezionare tutte le caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="ac93e-104">If you want to ignore the column, click **Back** to return to the page **Specify the Training Data**, and clear all checkboxes.</span></span>  
  
 <span data-ttu-id="ac93e-105">L'utilizzo di una colonna indica l'utilizzo dei dati nel modello.</span><span class="sxs-lookup"><span data-stu-id="ac93e-105">The usage of a column indicates how the data will be used in the model.</span></span> <span data-ttu-id="ac93e-106">Una colonna può essere utilizzata come una chiave per identificare una serie, come un valore di input da utilizzare nelle analisi o come valore da stimare.</span><span class="sxs-lookup"><span data-stu-id="ac93e-106">A column can be used as a key to identify a series, as an input value to use in analysis, or as the value that you want to predict.</span></span> <span data-ttu-id="ac93e-107">Le colonne possono essere utilizzate sia per la stima che per l'input.</span><span class="sxs-lookup"><span data-stu-id="ac93e-107">Columns can be used for both prediction and input.</span></span>  
  
 <span data-ttu-id="ac93e-108">Il tipo di dati specifica dettagli aggiuntivi sul tipo di dati contenuto nella colonna e sull'utilizzo dei dati durante il training.</span><span class="sxs-lookup"><span data-stu-id="ac93e-108">The data type specifies additional detail about the type of data that is contained in the column, and how the data will be used during training.</span></span> <span data-ttu-id="ac93e-109">Alcuni tipi di contenuto richiedono un tipo di dati specifico e viceversa.</span><span class="sxs-lookup"><span data-stu-id="ac93e-109">Some content types require a specific data type, and vice versa.</span></span> <span data-ttu-id="ac93e-110">Potrebbe anche essere necessario specificare un particolare tipo di dati a seconda dell'algoritmo utilizzato durante la creazione del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ac93e-110">You might also need to specify a particular data type depending on the algorithm that you use when you create a mining model.</span></span> <span data-ttu-id="ac93e-111">Per informazioni sui tipi di contenuto e i tipi di dati nei modelli e nelle strutture di data mining, vedere [Tipi di contenuto &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ac93e-111">For information about content types and data types in mining models and structures, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="ac93e-112">**Per altre informazioni:** [Strutture di data mining &#40;Analysis Services - Data mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Colonne del modello di data mining](data-mining/mining-model-columns.md), [Creazione guidata modello di data mining &#40;Analysis Services - Data mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Creare una struttura di data mining relazionale](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="ac93e-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac93e-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ac93e-113">Options</span></span>  
 <span data-ttu-id="ac93e-114">**Struttura modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="ac93e-114">**Mining model structure**</span></span>  
 <span data-ttu-id="ac93e-115">Consente di visualizzare le colonne dalle viste e dalle tabelle nidificate selezionate nella pagina precedente della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="ac93e-115">Displays the columns from the views and nested tables that you selected on the previous page of the wizard.</span></span>  
  
 <span data-ttu-id="ac93e-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ac93e-116">**Columns**</span></span>  
 <span data-ttu-id="ac93e-117">Consente di visualizzare l'elenco delle colonne.</span><span class="sxs-lookup"><span data-stu-id="ac93e-117">Lists the columns.</span></span>  
  
 <span data-ttu-id="ac93e-118">**Tipo di contenuto**</span><span class="sxs-lookup"><span data-stu-id="ac93e-118">**Content type**</span></span>  
 <span data-ttu-id="ac93e-119">Consente di specificare il tipo di contenuto della colonna</span><span class="sxs-lookup"><span data-stu-id="ac93e-119">Specify the content type for the column.</span></span> <span data-ttu-id="ac93e-120">Se nella pagina precedente della procedura guidata è stato specificato che la colonna è una chiave, sono disponibili i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ac93e-120">If you specified that the column is a key on the previous page of the wizard, the following values are available:</span></span>  
  
|<span data-ttu-id="ac93e-121">Opzione</span><span class="sxs-lookup"><span data-stu-id="ac93e-121">Option</span></span>|<span data-ttu-id="ac93e-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac93e-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ac93e-123">Chiave</span><span class="sxs-lookup"><span data-stu-id="ac93e-123">Key</span></span>|<span data-ttu-id="ac93e-124">Consente di specificare che la colonna contiene un identificatore univoco per la serie di casi.</span><span class="sxs-lookup"><span data-stu-id="ac93e-124">Specify that the column contains a unique identifier for the case series.</span></span>|  
|<span data-ttu-id="ac93e-125">Key Sequence</span><span class="sxs-lookup"><span data-stu-id="ac93e-125">Key Sequence</span></span>|<span data-ttu-id="ac93e-126">Consente di specificare che la colonna contiene un identificatore di sequenza.</span><span class="sxs-lookup"><span data-stu-id="ac93e-126">Specify that the column contains a sequence identifier.</span></span>|  
|<span data-ttu-id="ac93e-127">Chiave temporale</span><span class="sxs-lookup"><span data-stu-id="ac93e-127">Key Time</span></span>|<span data-ttu-id="ac93e-128">Consente di specificare che la colonna contiene una data o un altro numero continuo univoco utilizzato per identificare una data o una serie temporale.</span><span class="sxs-lookup"><span data-stu-id="ac93e-128">Specify that the column contains a date or other unique continuous number that is used to identify a date or time series.</span></span>|  
  
 <span data-ttu-id="ac93e-129">Se si seleziona la colonna come colonna non chiave, sono disponibili i seguenti valori a seconda del tipo di dati:</span><span class="sxs-lookup"><span data-stu-id="ac93e-129">If you selected the column as a non-key column, the following values are available, depending on the data type:</span></span>  
  
|<span data-ttu-id="ac93e-130">Opzione</span><span class="sxs-lookup"><span data-stu-id="ac93e-130">Option</span></span>|<span data-ttu-id="ac93e-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac93e-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ac93e-132">Continua</span><span class="sxs-lookup"><span data-stu-id="ac93e-132">Continuous</span></span>|<span data-ttu-id="ac93e-133">Consente di specificare che la colonna contiene valori numerici continui.</span><span class="sxs-lookup"><span data-stu-id="ac93e-133">Specify that the column contains continuous numeric values.</span></span>|  
|<span data-ttu-id="ac93e-134">Discretizzato</span><span class="sxs-lookup"><span data-stu-id="ac93e-134">Discretized</span></span>|<span data-ttu-id="ac93e-135">Consente di specificare che la colonna contiene valori numerici discretizzati o che possono essere trattati come valori discreti.</span><span class="sxs-lookup"><span data-stu-id="ac93e-135">Specify that the column contains numeric values that either have been discretized, or can be treated as discrete values.</span></span>|  
|<span data-ttu-id="ac93e-136">Discrete</span><span class="sxs-lookup"><span data-stu-id="ac93e-136">Discrete</span></span>|<span data-ttu-id="ac93e-137">Consente di specificare che la colonna contiene testo o altri valori non numerici.</span><span class="sxs-lookup"><span data-stu-id="ac93e-137">Specify that the column contains text or other nonnumeric values.</span></span>|  
  
 <span data-ttu-id="ac93e-138">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="ac93e-138">**Data type**</span></span>  
 <span data-ttu-id="ac93e-139">Consente di specificare il tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="ac93e-139">Specify the data type for the column.</span></span>  
  
 <span data-ttu-id="ac93e-140">Sono disponibili i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ac93e-140">The following values are available:</span></span>  
  
-   `Boolean`  
  
-   `Date`  
  
-   `Double`  
  
-   `Long`  
  
-   `Text`  
  
 <span data-ttu-id="ac93e-141">**Detect**</span><span class="sxs-lookup"><span data-stu-id="ac93e-141">**Detect**</span></span>  
 <span data-ttu-id="ac93e-142">Consente di analizzare un esempio di dati in tutte le colonne numeriche.</span><span class="sxs-lookup"><span data-stu-id="ac93e-142">Analyze a sample of data in all numeric columns.</span></span> <span data-ttu-id="ac93e-143">Consente di sostituire i valori **Tipo di contenuto** con un tipo di contenuto consigliato.</span><span class="sxs-lookup"><span data-stu-id="ac93e-143">Replaces specified **Content Type** values with a recommended content type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac93e-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac93e-144">See Also</span></span>  
 <span data-ttu-id="ac93e-145">[Guida sensibile al contesto della creazione guidata modello di data mining &#40;Analysis Services-&#41;di data mining](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ac93e-145">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="ac93e-146">[Suggerisci colonne correlate &#40;creazione guidata modello di data mining&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="ac93e-146">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="ac93e-147">[Impostazione tipi di tabella &#40;creazione guidata modello di data mining&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="ac93e-147">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="ac93e-148">Specificare il tipo di dati e il contenuto della colonna &#40;creazione guidata modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="ac93e-148">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
