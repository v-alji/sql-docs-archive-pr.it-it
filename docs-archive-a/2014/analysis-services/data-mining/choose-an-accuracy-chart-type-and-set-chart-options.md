---
title: Scegliere un tipo di grafico di accuratezza e impostare le opzioni del grafico | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services]
- mining models [Analysis Services], validating
- classification accuracy [data mining]
- accuracy testing [data mining]
ms.assetid: bd24dd4a-624f-478a-9c94-b1361e857680
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33c2b5e8a1e228a86328ef6df1b636742d3614ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627558"
---
# <a name="choose-an-accuracy-chart-type-and-set-chart-options"></a><span data-ttu-id="67cbb-102">Scegliere un tipo di grafico di accuratezza e impostare le opzioni del grafico</span><span class="sxs-lookup"><span data-stu-id="67cbb-102">Choose an Accuracy Chart Type and Set Chart Options</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="67cbb-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]in sono disponibili più metodi per determinare la validità dei modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="67cbb-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides multiple methods for determining the validity of your mining models.</span></span> <span data-ttu-id="67cbb-104">Il tipo di grafico di accuratezza che è possibile creare per ogni modello o struttura dipende dai fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="67cbb-104">The type of accuracy chart that you can create for each model or structure depends on these factors:</span></span>  
  
-   <span data-ttu-id="67cbb-105">Tipo di algoritmo utilizzato per creare il modello</span><span class="sxs-lookup"><span data-stu-id="67cbb-105">The type of algorithm that was used to create the model</span></span>  
  
-   <span data-ttu-id="67cbb-106">Tipo di dati dell'attributo stimabile</span><span class="sxs-lookup"><span data-stu-id="67cbb-106">The data type of the predictable attribute</span></span>  
  
-   <span data-ttu-id="67cbb-107">Numero di attributi stimabili per le misurazioni</span><span class="sxs-lookup"><span data-stu-id="67cbb-107">The number of predictable attributes to measure</span></span>  
  
 <span data-ttu-id="67cbb-108">In questo argomento viene fornita una panoramica dei diversi grafici di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="67cbb-108">This topic provides an overview of the different accuracy charts.</span></span>  
  
 <span data-ttu-id="67cbb-109">**Nota** I grafici e le relative definizioni non vengono salvati.</span><span class="sxs-lookup"><span data-stu-id="67cbb-109">**Note** Charts and their definitions are not saved.</span></span> <span data-ttu-id="67cbb-110">Se si chiude la finestra che contiene un grafico, questo dovrà essere creato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="67cbb-110">If you close the window that contains a chart, you must create the chart again.</span></span>  
  
## <a name="accuracy-chart-types"></a><span data-ttu-id="67cbb-111">Tipi di grafici di accuratezza</span><span class="sxs-lookup"><span data-stu-id="67cbb-111">Accuracy Chart Types</span></span>  
 <span data-ttu-id="67cbb-112">A seconda del tipo di grafico scelto, è possibile configurare opzioni, esplorare il grafico o copiare quest'ultimo negli Appunti e utilizzare i dati in Excel.</span><span class="sxs-lookup"><span data-stu-id="67cbb-112">Depending on the chart type that you choose, you have the ability to further configure options, to browse the chart, or copy the chart to the Clipboard and work with the data in Excel.</span></span>  
  
#### <a name="lift-chart"></a><span data-ttu-id="67cbb-113">Grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="67cbb-113">Lift chart</span></span>  
 <span data-ttu-id="67cbb-114">Dopo avere configurato le opzioni per i modelli e i dati di testing, fare clic sulla scheda **Grafico di accuratezza** per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="67cbb-114">After you have configured the options for the models and the testing data, click the **Lift Chart** tab to view the results.</span></span> <span data-ttu-id="67cbb-115">È inoltre possibile copiare il grafico negli Appunti o visualizzare i dettagli di singole linee di tendenza o punti dati in Legenda data mining.</span><span class="sxs-lookup"><span data-stu-id="67cbb-115">You can also copy the chart to the Clipboard, or view details of individual trend lines or data points in the Mining Legend.</span></span>  
  
#### <a name="profit-chart"></a><span data-ttu-id="67cbb-116">Grafico profitti</span><span class="sxs-lookup"><span data-stu-id="67cbb-116">Profit Chart</span></span>  
 <span data-ttu-id="67cbb-117">Dopo avere configurato le opzioni per i modelli e i dati di testing, fare clic sulla scheda **Grafico di accuratezza** , selezionare **Grafico profitti** nell'elenco **Tipo di grafico** per impostare le opzioni del grafico dei profitti, quindi scegliere **OK** per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="67cbb-117">After you have configured the options for the models and the testing data, click the **Lift Chart** tab, select **Profit Chart** from the **Chart Type** list to set profit chart options, and then click **OK** to view the results.</span></span>  
  
 <span data-ttu-id="67cbb-118">È possibile utilizzare la finestra di dialogo **Impostazioni grafico profitti** tutte le volte che lo si desidera per provare diverse opzioni relative ai costi, quindi visualizzare di nuovo il grafico.</span><span class="sxs-lookup"><span data-stu-id="67cbb-118">You can use the **Profit Chart Settings** dialog box as many times as you want to try different cost options and redisplay the chart.</span></span> <span data-ttu-id="67cbb-119">Legenda data mining contiene informazioni dettagliate sui profitti stimati per ciascun modello.</span><span class="sxs-lookup"><span data-stu-id="67cbb-119">The Mining Legend contains detailed information about the estimated profit for each model.</span></span> <span data-ttu-id="67cbb-120">È inoltre possibile copiare il grafico e il contenuto di Legenda data mining negli Appunti per utilizzarli in Excel.</span><span class="sxs-lookup"><span data-stu-id="67cbb-120">You can also copy the chart and the contents of the Mining Legend to the Clipboard to work with it in Excel.</span></span>  
  
#### <a name="scatter-plot"></a><span data-ttu-id="67cbb-121">Grafico a dispersione</span><span class="sxs-lookup"><span data-stu-id="67cbb-121">Scatter Plot</span></span>  
 <span data-ttu-id="67cbb-122">Se è stato selezionato il tipo di modello appropriato, quando si fa clic sulla scheda **Grafico di accuratezza** il tipo di grafico viene automaticamente impostato su **Grafico a dispersione** e viene visualizzato un grafico a dispersione.</span><span class="sxs-lookup"><span data-stu-id="67cbb-122">If you have selected the appropriate type of model, when you click the **Lift Chart** tab, the chart type is automatically set to **Scatter Plot** and a scatter plot is displayed.</span></span> <span data-ttu-id="67cbb-123">Non è possibile effettuare altre operazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="67cbb-123">No further configuration is possible.</span></span> <span data-ttu-id="67cbb-124">È inoltre possibile copiare il grafico negli Appunti e incollarlo come elemento grafico in Excel o in un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="67cbb-124">You can also copy the chart to the Clipboard and paste the chart as a graphic into Excel or another application.</span></span>  
  
#### <a name="classification-matrix"></a><span data-ttu-id="67cbb-125">Matrice di classificazione</span><span class="sxs-lookup"><span data-stu-id="67cbb-125">Classification Matrix</span></span>  
 <span data-ttu-id="67cbb-126">Per una matrice di classificazione, usare la scheda **Selezione input** per scegliere i modelli e i dati di testing, quindi fare clic sulla scheda **Matrice di classificazione** per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="67cbb-126">For a classification matrix, use the **Input Selection** tab to choose the models and the testing data, and then click the **Classification Matrix** tab to view the results.</span></span>  
  
 <span data-ttu-id="67cbb-127">Il contenuto di una matrice di classificazione è lo stesso per tutti i tipi di modello e non può essere configurato.</span><span class="sxs-lookup"><span data-stu-id="67cbb-127">The contents of a classification matrix are the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="67cbb-128">È inoltre possibile copiare i dati del grafico negli Appunti e quindi utilizzarli in Excel.</span><span class="sxs-lookup"><span data-stu-id="67cbb-128">You can copy the data in the chart to the Clipboard and then work with it in Excel.</span></span>  
  
#### <a name="cross-validation-report"></a><span data-ttu-id="67cbb-129">Report Convalida incrociata</span><span class="sxs-lookup"><span data-stu-id="67cbb-129">Cross-Validation Report</span></span>  
 <span data-ttu-id="67cbb-130">Per un report di convalida incrociata, dopo aver selezionato una struttura di data mining o un modello di data mining in Esplora soluzioni, fare clic sulla scheda **Convalida incrociata** , configurare tutte le opzioni pertinenti, quindi fare clic su **Ottieni risultati** per generare il report.</span><span class="sxs-lookup"><span data-stu-id="67cbb-130">For a cross-validation report, after you have selected a mining structure or mining model in Solution Explorer, click the **Cross Validation** tab, configure all relevant options, and then click **Get Results** to generate the report.</span></span> <span data-ttu-id="67cbb-131">Non è possibile effettuare altre operazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="67cbb-131">No further configuration is possible.</span></span>  
  
 <span data-ttu-id="67cbb-132">Il formato del report di convalida incrociata è lo stesso per tutti i tipi di modello e non può essere configurato.</span><span class="sxs-lookup"><span data-stu-id="67cbb-132">The format of the cross-validation report is the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="67cbb-133">Il contenuto del report varia tuttavia in base al tipo di modello analizzato e al tipo di dati dell'attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="67cbb-133">However, the content of the report differs depending on the type of model that you are analyzing, and the data type of the predictable attribute.</span></span> <span data-ttu-id="67cbb-134">È inoltre possibile copiare i risultati del report negli Appunti e utilizzare i dati in Excel.</span><span class="sxs-lookup"><span data-stu-id="67cbb-134">You can also copy the results of the report to the Clipboard and work with the data in Excel.</span></span>  
  
  
