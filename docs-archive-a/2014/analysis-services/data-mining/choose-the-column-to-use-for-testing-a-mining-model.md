---
title: Scegliere la colonna da utilizzare per il test di un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], predictable mining columns
- Mining Accuracy Chart [Analysis Services], columns
- predictable mining columns [Analysis Services]
ms.assetid: c6a8f23a-da21-4f31-9521-99460d624649
author: minewiskan
ms.author: owend
ms.openlocfilehash: 326a7084600695d95d3a132f633041e9abad045b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630164"
---
# <a name="choose-the-column-to-use-for-testing-a-mining-model"></a><span data-ttu-id="5f3c1-102">Scegliere la colonna da utilizzare per il test di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="5f3c1-102">Choose the Column to Use for Testing a Mining Model</span></span>
  <span data-ttu-id="5f3c1-103">Prima di poter misurare l'accuratezza di un modello di data mining, è necessario decidere quale risultato si desidera valutare.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-103">Before you can measure the accuracy of a mining model, you must decide which outcome it is that you want to assess.</span></span> <span data-ttu-id="5f3c1-104">La maggior parte dei modelli di data mining richiede che si scelga almeno una colonna da utilizzare come attributo stimabile quando si crea il modello.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-104">Most data mining models require that you choose at least one column to use as the predictable attribute when you create the model.</span></span> <span data-ttu-id="5f3c1-105">Pertanto, quando si testa l'accuratezza del modello, è in genere necessario selezionare quell'attributo da testare.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-105">Therefore, when you test the accuracy of the model, you generally must select that attribute to test.</span></span>  
  
 <span data-ttu-id="5f3c1-106">Nell'elenco seguente vengono descritte alcune considerazioni aggiuntive relative alla scelta dell'attributo stimabile da utilizzare nel test:</span><span class="sxs-lookup"><span data-stu-id="5f3c1-106">The following list describes some additional considerations for choosing the predictable attribute to use in testing:</span></span>  
  
-   <span data-ttu-id="5f3c1-107">Alcuni tipi di modelli di data mining possono prevedere più attributi, ad esempio reti neurali, che consentono di esplorare le relazioni tra molti attributi.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-107">Some types of data mining models can predict multiple attributes-such as neural networks, which can explore the relationships between many attributes.</span></span>  
  
-   <span data-ttu-id="5f3c1-108">Altri tipi di modelli di data mining, ad esempio i modelli di clustering, non dispongono necessariamente di un attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-108">Other types of mining models-such as clustering models-do not necessarily have a predictable attribute.</span></span> <span data-ttu-id="5f3c1-109">Non è possibile testare i modelli di clustering a meno che non dispongano di un attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-109">Clustering models cannot be tested unless they have a predictable attribute.</span></span>  
  
-   <span data-ttu-id="5f3c1-110">Per creare un grafico a dispersione o misurare l'accuratezza di un modello di regressione è necessario scegliere un attributo stimabile continuo come risultato.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-110">To create a scatter plot or measure the accuracy of a regression model requires that you choose a continuous predictable attribute as the outcome.</span></span> <span data-ttu-id="5f3c1-111">In questo caso, non è possibile specificare un valore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-111">In that case, you cannot specify a target value.</span></span> <span data-ttu-id="5f3c1-112">Se si crea qualsiasi grafico diverso da un grafico a dispersione, anche la colonna della struttura di data mining sottostante deve avere un tipo di contenuto **Discreto** o **Discretizzato**.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-112">If you are creating anything other than a scatter plot, the underlying mining structure column must also have a content type of **Discrete** or **Discretized**.</span></span>  
  
-   <span data-ttu-id="5f3c1-113">Se si sceglie un attributo discreto come risultato stimabile, è anche possibile specificare un valore di destinazione oppure lasciare vuoto il campo **Valore stima** .</span><span class="sxs-lookup"><span data-stu-id="5f3c1-113">If you choose a discrete attribute as the predictable outcome, you can also specify a target value, or you can leave the **Predict Value** field blank.</span></span> <span data-ttu-id="5f3c1-114">Se si include un **valore di stima**, il grafico misurerà solo l'efficacia del modello alla stima del valore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-114">If you include a **Predict Value**, the chart will measure only the model's effectiveness at predicting the target value.</span></span> <span data-ttu-id="5f3c1-115">Se non si specifica un risultato di destinazione, il modello viene misurato per l'accuratezza alla stima di tutti i risultati.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-115">If you do not specify a target outcome, the model is measured for its accuracy in predicting all outcomes.</span></span>  
  
-   <span data-ttu-id="5f3c1-116">Se si desidera includere più modelli e confrontarli in un singolo grafico di accuratezza, tutti i modelli devono utilizzare la stessa colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-116">If you want to include multiple models and compare them in a single accuracy chart, all models must use the same predictable column.</span></span>  
  
-   <span data-ttu-id="5f3c1-117">Quando si crea un report di convalida incrociata, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] analizza automaticamente tutti i modelli che includono lo stesso attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-117">When you create a cross-validation report, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will automatically analyze all models that have the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="5f3c1-118">Quando l'opzione **Sincronizza colonne e valori di stima**è selezionata, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] seleziona automaticamente le colonne stimabili che hanno gli stessi nomi e tipi di dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-118">When the option, **Synchronize Prediction columns and Values**, is selected, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatically chooses predictable columns that have the same names and matching data types.</span></span> <span data-ttu-id="5f3c1-119">Se le colonne non soddisfano questi criteri, è possibile disabilitare questa opzione e scegliere manualmente una colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-119">If your columns do not meet these criteria, you can turn off this option and manually choose a predictable column.</span></span> <span data-ttu-id="5f3c1-120">Potrebbe essere necessario eseguire questa operazione per il test del modello con un set di dati esterni che dispone di colonne diverse rispetto al modello.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-120">You might need to do this if you are testing the model with an external data set that has different columns than the model.</span></span> <span data-ttu-id="5f3c1-121">Se tuttavia si sceglie una colonna con il tipo di dati errato si verificherà un errore o si otterranno risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-121">However, if you choose a column with the wrong the type of data you will either get an error or bad results.</span></span>  
  
### <a name="specify-the-outcome-to-predict"></a><span data-ttu-id="5f3c1-122">Specificare il risultato da stimare</span><span class="sxs-lookup"><span data-stu-id="5f3c1-122">Specify the outcome to predict</span></span>  
  
1.  <span data-ttu-id="5f3c1-123">Fare doppio clic sulla struttura di data mining per aprirla in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-123">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="5f3c1-124">Selezionare la scheda **Grafico di accuratezza modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="5f3c1-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="5f3c1-125">Selezionare la scheda **Selezione input** .</span><span class="sxs-lookup"><span data-stu-id="5f3c1-125">Select the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="5f3c1-126">In **Nome colonna stimabile** nella scheda **Selezione input**selezionare una colonna stimabile per ogni modello incluso nel grafico.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-126">On the **Input Selection** tab, under **Predictable Column Name**, select a predictable column for each model that you include in the chart.</span></span>  
  
     <span data-ttu-id="5f3c1-127">Le colonne del modello di data mining disponibili nella casella **Nome colonna stimabile** sono limitate solo a quelle con il tipo di utilizzo impostato su **Stima** o **Solo stima**.</span><span class="sxs-lookup"><span data-stu-id="5f3c1-127">The mining model columns that are available in the **Predictable Column Name** box are only those with the usage type set to **Predict** or **Predict Only**.</span></span>  
  
5.  <span data-ttu-id="5f3c1-128">Se si vuole determinare il livello di accuratezza per un modello, è necessario selezionare un risultato specifico da misurare nell'elenco **Valore stima** .</span><span class="sxs-lookup"><span data-stu-id="5f3c1-128">If you want to determine the lift for a model, you must select a specific outcome value to measure, for by choosing from the **Predict Value** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3c1-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f3c1-129">See Also</span></span>  
 <span data-ttu-id="5f3c1-130">[Scegliere ed eseguire il mapping dei dati di test del modello](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="5f3c1-130">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="5f3c1-131">Scegliere un tipo di grafico di accuratezza e impostare le opzioni del grafico</span><span class="sxs-lookup"><span data-stu-id="5f3c1-131">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
