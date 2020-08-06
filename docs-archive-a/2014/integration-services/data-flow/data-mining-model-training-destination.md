---
title: Destinazione Training modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingmodeltrainingdest.f1
helpviewer_keywords:
- destinations [Integration Services], Data Mining Model Training
- Data Mining Model Training destination
- mining models [Analysis Services], training
- training mining models
ms.assetid: 6bc8cbe2-46af-4f7b-93d6-86779313c9d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e101a7e374f16b12b3a5aa30a49dbecd2632f06f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629536"
---
# <a name="data-mining-model-training-destination"></a><span data-ttu-id="fbfc8-102">Training modello di data mining - destinazione</span><span class="sxs-lookup"><span data-stu-id="fbfc8-102">Data Mining Model Training Destination</span></span>
  <span data-ttu-id="fbfc8-103">La destinazione Training modello di data mining consente di eseguire il training dei modelli di data mining passando i dati ricevuti dalla destinazione agli algoritmi dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-103">The Data Mining Model Training destination trains data mining models by passing the data that the destination receives through the data mining model algorithms.</span></span> <span data-ttu-id="fbfc8-104">È possibile eseguire il training di più modelli di data mining con una singola destinazione, se i modelli sono compilati in base alla stessa struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-104">Multiple data mining models can be trained by one destination if the models are built on the same data mining structure.</span></span> <span data-ttu-id="fbfc8-105">Per altre informazioni, vedere [Colonne della struttura di data mining](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) e [Colonne del modello di data mining](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span><span class="sxs-lookup"><span data-stu-id="fbfc8-105">For more information, see [Mining Structure Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-structure-columns) and [Mining Model Columns](https://docs.microsoft.com/analysis-services/data-mining/mining-model-columns).</span></span>  
  
## <a name="configuration-of-the-data-mining-model-training-destination"></a><span data-ttu-id="fbfc8-106">Configurazione della destinazione Training modello di data mining</span><span class="sxs-lookup"><span data-stu-id="fbfc8-106">Configuration of the Data Mining Model Training Destination</span></span>  
 <span data-ttu-id="fbfc8-107">Se una colonna livello case della struttura di destinazione e i modelli compilati sulla struttura presentano il tipo di contenuto KEY TIME o KEY SEQUENCE, i dati di input devono essere ordinati in base a questa colonna.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-107">If a case level column of the target structure and the models built on the structure has the content type KEY TIME or KEY SEQUENCE, the input data must be sorted on that column.</span></span> <span data-ttu-id="fbfc8-108">I modelli compilati utilizzando l'algoritmo Microsoft Time Series, ad esempio, hanno tipo di contenuto KEY TIME.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-108">For example, models built using the Microsoft Time Series algorithm use the content type KEY TIME.</span></span> <span data-ttu-id="fbfc8-109">Se i dati di input non sono ordinati, non sarà possibile elaborare il modello.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-109">If input data is not sorted, the processing of the model may fail.</span></span> <span data-ttu-id="fbfc8-110">Se sono necessari dati ordinati, sarà possibile inserire una trasformazione Ordinamento in un punto precedente del flusso di dati per ordinare i dati.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-110">If the data requires sorting, you can use a Sort transformation earlier in the data flow to sort the data.</span></span> <span data-ttu-id="fbfc8-111">Questo non è vale per le colonne con tipo di contenuto KEY.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-111">This requirement does not apply to columns with the KEY content type.</span></span> <span data-ttu-id="fbfc8-112">Per altre informazioni, vedere [Tipi di contenuto &#40;Data mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) e [Trasformazione ordinamento](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="fbfc8-112">For more information, see [Content Types &#40;Data Mining&#41;](https://docs.microsoft.com/analysis-services/data-mining/content-types-data-mining) and [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbfc8-113">L'input della destinazione Training modello di data mining deve essere ordinato.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-113">The input to the Data Mining Model training destination must be sorted.</span></span> <span data-ttu-id="fbfc8-114">Per ordinare i dati è possibile includere una trasformazione Ordinamento in un punto a monte della destinazione Training modello di data mining nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-114">To sort the data, you can include a Sort destination upstream from the Data Mining Model Training destination in the data flow.</span></span> <span data-ttu-id="fbfc8-115">Per altre informazioni, vedere [Trasformazione ordinamento](transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="fbfc8-115">For more information, see [Sort Transformation](transformations/sort-transformation.md).</span></span>  
  
 <span data-ttu-id="fbfc8-116">Questa destinazione include un input e nessun output.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-116">This destination has one input and no output.</span></span>  
  
 <span data-ttu-id="fbfc8-117">La destinazione Training modello di data mining usa una gestione connessione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per connettersi al progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o all'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che contiene la struttura e i modelli di data mining di cui eseguire il training.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-117">The Data Mining Model Training destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models that the destination trains.</span></span> <span data-ttu-id="fbfc8-118">Per altre informazioni, vedere [Gestione connessione Analysis Services](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fbfc8-118">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="fbfc8-119">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fbfc8-120">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor training modelli di data mining** , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbfc8-120">For more information about the properties that you can set in the **Data Mining Model Training Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fbfc8-121">Editor training modelli di data mining &#40;scheda Connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="fbfc8-121">Data Mining Model Training Editor &#40;Connection Tab&#41;</span></span>](../data-mining-model-training-editor-connection-tab.md)  
  
-   [<span data-ttu-id="fbfc8-122">Editor training modelli di data mining &#40;scheda Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="fbfc8-122">Data Mining Model Training Editor &#40;Columns Tab&#41;</span></span>](../data-mining-model-training-editor-columns-tab.md)  
  
 <span data-ttu-id="fbfc8-123">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="fbfc8-124">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbfc8-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="fbfc8-125">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="fbfc8-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="fbfc8-126">Proprietà personalizzate della destinazione Training modello di data mining</span><span class="sxs-lookup"><span data-stu-id="fbfc8-126">Data Mining Model Training Destination Custom Properties</span></span>](data-mining-model-training-destination-custom-properties.md)  
  
 <span data-ttu-id="fbfc8-127">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="fbfc8-127">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
