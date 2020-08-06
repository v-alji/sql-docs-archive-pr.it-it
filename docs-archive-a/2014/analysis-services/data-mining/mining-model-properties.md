---
title: Proprietà modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- data mining [Analysis Services], properties
- columns [data mining], properties
- Data Mining Designer
- properties [data mining]
ms.assetid: c5194619-8b31-42be-a95f-585711462945
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb086f4a978ca96de8e6fc99f889f718247629af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635865"
---
# <a name="mining-model-properties"></a><span data-ttu-id="ea008-102">Proprietà dei modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="ea008-102">Mining Model Properties</span></span>
  <span data-ttu-id="ea008-103">I modelli di data mining dispongono dei tipi seguenti di proprietà:</span><span class="sxs-lookup"><span data-stu-id="ea008-103">Mining models have the following kinds of properties:</span></span>  
  
-   <span data-ttu-id="ea008-104">Proprietà ereditate dalla struttura di data mining tramite cui vengono definiti il tipo di dati e il tipo di contenuto dei dati utilizzati dal modello</span><span class="sxs-lookup"><span data-stu-id="ea008-104">Properties that are inherited from the mining structure that define the data type and content type of the data used by the model;</span></span>  
  
-   <span data-ttu-id="ea008-105">Proprietà correlate all'algoritmo utilizzato per creare il modello di data mining, inclusi eventuali parametri del cliente</span><span class="sxs-lookup"><span data-stu-id="ea008-105">Properties that are related to the algorithm used to create the mining model, including any customer parameters;</span></span>  
  
-   <span data-ttu-id="ea008-106">Proprietà che definiscono un filtro sul modello utilizzato per eseguire il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ea008-106">Properties that define a filter on the model used to train the model.</span></span>  
  
 <span data-ttu-id="ea008-107">Le proprietà di un modello di data mining vengono definite inizialmente quando si crea il modello; è tuttavia possibile modificare la maggior parte delle proprietà in un secondo momento, inclusi i parametri dell'algoritmo, i filtri e le proprietà di utilizzo delle colonne.</span><span class="sxs-lookup"><span data-stu-id="ea008-107">The properties of a mining model are initially defined when you create the model; however, you can alter most properties later, including the algorithm parameters, filters, and column usage properties.</span></span> <span data-ttu-id="ea008-108">Tramite la scheda **Modelli di data mining** di Progettazione modelli di data mining, AMO o XMLA è possibile modificare le proprietà dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-108">You change properties by using the **Mining Models** tab of Data Mining Designer, or by using AMO or XMLA.</span></span>  
  
 <span data-ttu-id="ea008-109">Quando si modifica qualsiasi proprietà di un modello, è necessario rielaborare quest'ultimo in modo che vi vengano implementate le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ea008-109">Whenever you change any property of a model, you must reprocess the model for the changes to be reflected in the model.</span></span> <span data-ttu-id="ea008-110">La rielaborazione è necessaria anche se la modifica riguarda solo i metadati, ad esempio l'aggiunta di un alias o di una descrizione di colonna.</span><span class="sxs-lookup"><span data-stu-id="ea008-110">Reprocessing is required even if the change only involves metadata, such as adding a column alias or description.</span></span>  
  
## <a name="properties-of-models"></a><span data-ttu-id="ea008-111">Proprietà dei modelli</span><span class="sxs-lookup"><span data-stu-id="ea008-111">Properties of Models</span></span>  
 <span data-ttu-id="ea008-112">Nella tabella seguente vengono descritte le proprietà specifiche dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-112">The following table describes the properties that are specific to mining models.</span></span> <span data-ttu-id="ea008-113">Esistono inoltre proprietà che è possibile impostare su singole colonne di data mining</span><span class="sxs-lookup"><span data-stu-id="ea008-113">Additionally, there are properties that you can set on individual columns in the mining</span></span>  
  
|<span data-ttu-id="ea008-114">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ea008-114">Property</span></span>|<span data-ttu-id="ea008-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea008-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ea008-116">**Algoritmo**</span><span class="sxs-lookup"><span data-stu-id="ea008-116">**Algorithm**</span></span>|<span data-ttu-id="ea008-117">Imposta il tipo di algoritmo per il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-117">Sets the algorithm type for the mining model.</span></span>|  
|<span data-ttu-id="ea008-118">**AlgorithmParameters**</span><span class="sxs-lookup"><span data-stu-id="ea008-118">**AlgorithmParameters**</span></span>|<span data-ttu-id="ea008-119">Imposta i valori dei parametri di algoritmo disponibili per ogni tipo di algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ea008-119">Sets values for algorithm parameters that are available for each algorithm type.</span></span>|  
|<span data-ttu-id="ea008-120">**Filter**</span><span class="sxs-lookup"><span data-stu-id="ea008-120">**Filter**</span></span>|<span data-ttu-id="ea008-121">Imposta un filtro che viene applicato ai dati utilizzati per il training e il test del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-121">Sets a filter that is applied to the data that is used for training and testing the mining model.</span></span> <span data-ttu-id="ea008-122">La definizione del filtro è archiviata con il modello e può essere utilizzata facoltativamente quando si creano query di stima oppure per testare l'accuratezza del modello.</span><span class="sxs-lookup"><span data-stu-id="ea008-122">The filter definition is stored with the model and can be used optionally when you create prediction queries, or when you test the accuracy of the model.</span></span><br /><br /> <span data-ttu-id="ea008-123">Il filtro del modello non è facoltativo quando si esegue il training del modello.</span><span class="sxs-lookup"><span data-stu-id="ea008-123">The model filter is not optional when training the model.</span></span>|  
|<span data-ttu-id="ea008-124">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ea008-124">**Name**</span></span>|<span data-ttu-id="ea008-125">Imposta il nome del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-125">Sets the name of the mining model.</span></span>|  
|<span data-ttu-id="ea008-126">**AllowDrillThrough**</span><span class="sxs-lookup"><span data-stu-id="ea008-126">**AllowDrillThrough**</span></span>|<span data-ttu-id="ea008-127">Specifica se nel modello di data mining è consentito il drill-through.</span><span class="sxs-lookup"><span data-stu-id="ea008-127">Specifies whether drill through is enabled on the mining model.</span></span>|  
  
## <a name="properties-of-model-columns"></a><span data-ttu-id="ea008-128">Proprietà delle colonne del modello</span><span class="sxs-lookup"><span data-stu-id="ea008-128">Properties of Model Columns</span></span>  
 <span data-ttu-id="ea008-129">È possibile impostare le proprietà specifiche del data mining elencate di seguito per ogni colonna di un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-129">You can set the following data mining-specific properties for each column in a mining model.</span></span> <span data-ttu-id="ea008-130">Le proprietà possono essere impostate su un valore diverso per ogni modello di data mining di una struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-130">You can set these properties to a different value for each mining model in a mining structure.</span></span>  
  
|<span data-ttu-id="ea008-131">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ea008-131">Property</span></span>|<span data-ttu-id="ea008-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea008-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ea008-133">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ea008-133">**Description**</span></span>|<span data-ttu-id="ea008-134">Viene descritto lo scopo della colonna di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-134">Describes the purpose of the mining column.</span></span>|  
|<span data-ttu-id="ea008-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ea008-135">**Name**</span></span>|<span data-ttu-id="ea008-136">Imposta il nome della colonna del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-136">Sets the name of the mining model column.</span></span> <span data-ttu-id="ea008-137">È possibile digitare un nuovo nome per fornire un alias per la colonna del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-137">You can type a new name, to provide an alias for the mining model column.</span></span>|  
|<span data-ttu-id="ea008-138">**ModelingFlags**</span><span class="sxs-lookup"><span data-stu-id="ea008-138">**ModelingFlags**</span></span>|<span data-ttu-id="ea008-139">Imposta i flag specifici dell'algoritmo per la colonna.</span><span class="sxs-lookup"><span data-stu-id="ea008-139">Sets any algorithm-specific flags for the column.</span></span>|  
|<span data-ttu-id="ea008-140">**SourceColumnID**</span><span class="sxs-lookup"><span data-stu-id="ea008-140">**SourceColumnID**</span></span>|<span data-ttu-id="ea008-141">Indica il nome della colonna della struttura di data mining su cui si basa la colonna del modello.</span><span class="sxs-lookup"><span data-stu-id="ea008-141">Indicates the name of the mining structure column on which the model column is based.</span></span><br /><br /> <span data-ttu-id="ea008-142">Questa proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ea008-142">This property is read-only.</span></span>|  
|<span data-ttu-id="ea008-143">**Utilizzo**</span><span class="sxs-lookup"><span data-stu-id="ea008-143">**Usage**</span></span>|<span data-ttu-id="ea008-144">Imposta la modalità di utilizzo della colonna nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ea008-144">Sets how the column will be used by the mining model.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea008-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea008-145">See Also</span></span>  
 <span data-ttu-id="ea008-146">[Colonne del modello di data mining](mining-model-columns.md) </span><span class="sxs-lookup"><span data-stu-id="ea008-146">[Mining Model Columns](mining-model-columns.md) </span></span>  
 <span data-ttu-id="ea008-147">[Strutture di data mining &#40;Analysis Services-&#41;di data mining](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ea008-147">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="ea008-148">[Attività e procedure relative al modello di data mining](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="ea008-148">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="ea008-149">[Modificare le proprietà di un modello di data mining](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="ea008-149">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="ea008-150">[Strumenti di data mining](data-mining-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ea008-150">[Data Mining Tools](data-mining-tools.md) </span></span>  
 <span data-ttu-id="ea008-151">[Creare una struttura di data mining relazionale](create-a-relational-mining-structure.md) </span><span class="sxs-lookup"><span data-stu-id="ea008-151">[Create a Relational Mining Structure](create-a-relational-mining-structure.md) </span></span>  
 [<span data-ttu-id="ea008-152">Creare un alias per una colonna di un modello</span><span class="sxs-lookup"><span data-stu-id="ea008-152">Create an Alias for a Model Column</span></span>](create-an-alias-for-a-model-column.md)  
  
  
