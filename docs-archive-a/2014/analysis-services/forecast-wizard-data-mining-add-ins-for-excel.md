---
title: Procedura guidata previsione (componenti aggiuntivi Data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- forecasting [data mining]
- time series [data mining]
ms.assetid: c5b33f75-42d4-4598-89e7-94815c142ce6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c3fae97bf1c36154d8ae378840014f2fb997afd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625678"
---
# <a name="forecast-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="b4778-102">Procedura guidata Previsione (componenti aggiuntivi Data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="b4778-102">Forecast Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="b4778-103">![Procedura guidata Associazione sulla barra multifunzione Data mining](media/dmc-forecast.gif "Procedura guidata Associazione sulla barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="b4778-103">![Associate wizard in Data Mining ribbon](media/dmc-forecast.gif "Associate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="b4778-104">La procedura guidata Previsione consente di stimare i valori in una serie temporale</span><span class="sxs-lookup"><span data-stu-id="b4778-104">The Forecast wizard helps you predict values in a time series.</span></span> <span data-ttu-id="b4778-105">e utilizza l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series, ovvero un algoritmo di regressione per la stima di colonne continue, ad esempio le vendite di prodotti.</span><span class="sxs-lookup"><span data-stu-id="b4778-105">The Forecast wizard uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm, which is a regression algorithm for use in predicting continuous columns, such as product sales.</span></span>  
  
 <span data-ttu-id="b4778-106">Ogni modello di previsione deve contenere una serie del case, ossia la colonna che distingue i punti di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="b4778-106">Each forecasting model must contain a case series, which is the column that distinguishes between points in a sequence.</span></span> <span data-ttu-id="b4778-107">Se ad esempio si utilizzano dati cronologici per prevedere le vendite in un periodo di diversi mesi, utilizzare una colonna contenente una serie di date come serie del case.</span><span class="sxs-lookup"><span data-stu-id="b4778-107">For example, if you are using historical data to forecast sales over a period of several months, you would use a column containing a series of dates as the case series.</span></span>  
  
 <span data-ttu-id="b4778-108">È possibile creare stime da un modello di previsione senza fornire i nuovi dati di input.</span><span class="sxs-lookup"><span data-stu-id="b4778-108">You can create predictions from a forecasting model without providing new input data.</span></span>  
  
 <span data-ttu-id="b4778-109">Lo strumento di [analisi delle tabelle &#40;per excel&#41;](forecast-table-analysis-tools-for-excel.md) , nella barra multifunzione **analizza** consente inoltre di creare modelli di previsione, ma è meno personalizzabile e può utilizzare solo i dati nelle tabelle di Excel.</span><span class="sxs-lookup"><span data-stu-id="b4778-109">The [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) tool, in the **Analyze** ribbon, also lets you create forecasting models, but it is less customizable and can only use data in Excel tables.</span></span>  
  
## <a name="using-the-forecast-wizard"></a><span data-ttu-id="b4778-110">Utilizzo della procedura guidata Previsione</span><span class="sxs-lookup"><span data-stu-id="b4778-110">Using the Forecast Wizard</span></span>  
  
1.  <span data-ttu-id="b4778-111">Sulla barra multifunzione **data mining** fare clic su **previsione**.</span><span class="sxs-lookup"><span data-stu-id="b4778-111">In the **Data Mining** ribbon, click **Forecast**.</span></span>  
  
2.  <span data-ttu-id="b4778-112">In **selezione dati di origine**scegliere la tabella di Excel, l'intervallo o l'origine dati esterna da utilizzare come input.</span><span class="sxs-lookup"><span data-stu-id="b4778-112">In the **Select Source Data**, choose the Excel table, range, or external data source to use as inputs.</span></span>  
  
     <span data-ttu-id="b4778-113">Se si utilizza un'origine dati esterna, è possibile definire viste o query personalizzate e salvarle come origine dati di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4778-113">If you use an external data source, you can define custom view or queries and save it as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="b4778-114">Nella pagina **previsione** , per **timestamp**, selezionare una colonna contenente un valore numerico univoco (inclusi i valori di data e ora) che può essere utilizzata come serie di casi.</span><span class="sxs-lookup"><span data-stu-id="b4778-114">On the **Forecasting** page, for **Time stamp**, select a column that contains unique numeric value (this includes date and time values) that can be used as the case series.</span></span> <span data-ttu-id="b4778-115">L'origine dati deve essere ordinata in ordine crescente in base a questa colonna.</span><span class="sxs-lookup"><span data-stu-id="b4778-115">The data source must be sorted in ascending order by this column.</span></span>  
  
     <span data-ttu-id="b4778-116">Se i dati non includono colonne di questo tipo, è possibile usare l'opzione \<no time stamp> .</span><span class="sxs-lookup"><span data-stu-id="b4778-116">If your data does not have such a column, you can use the option \<no time stamp>.</span></span> <span data-ttu-id="b4778-117">Nella procedura guidata verrà aggiunta una colonna di ordinamento univoca per i dati di input; pertanto, è necessario assicurarsi che i dati vengano ordinati nel modo desiderato prima di eseguire la procedura guidata e di scegliere questa opzione.</span><span class="sxs-lookup"><span data-stu-id="b4778-117">The wizard will add a unique order column for the input data; therefore, you must make sure that the data is sorted the way you want before running the wizard and choosing this option.</span></span>  
  
4.  <span data-ttu-id="b4778-118">Facoltativamente, è possibile fare clic su **parametri** e personalizzare il comportamento del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="b4778-118">Optionally, you can click **Parameters** and customize the behavior of the mining model.</span></span>  
  
     <span data-ttu-id="b4778-119">I modelli di previsione supportano diversi algoritmi:</span><span class="sxs-lookup"><span data-stu-id="b4778-119">Forecasting models support several different algorithms:</span></span>  
  
    -   <span data-ttu-id="b4778-120">ARIMA</span><span class="sxs-lookup"><span data-stu-id="b4778-120">ARIMA</span></span>  
  
    -   <span data-ttu-id="b4778-121">ARTXP (un tipo di modello di regressione)</span><span class="sxs-lookup"><span data-stu-id="b4778-121">ARTXP (a type of regression model)</span></span>  
  
    -   <span data-ttu-id="b4778-122">ARTXP e ARIMA combinati</span><span class="sxs-lookup"><span data-stu-id="b4778-122">ARTXP and ARIMA combined</span></span>  
  
     <span data-ttu-id="b4778-123">Per informazioni sulle differenze, vedere [riferimento tecnico per l'algoritmo Microsoft Time Series](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b4778-123">For information about the differences, see [Microsoft Time Series Algorithm Technical Reference](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
     <span data-ttu-id="b4778-124">È inoltre possibile aggiungere hint di periodicità, specificare le opzioni di anti-aliasing e personalizzare le opzioni di regressione per il modello.</span><span class="sxs-lookup"><span data-stu-id="b4778-124">You can also add periodicity hints, specify smoothing options, and customize regression options for the model.</span></span>  
  
5.  <span data-ttu-id="b4778-125">Nella pagina **fine** specificare un nome descrittivo per il set di dati e il modello, quindi impostare le opzioni seguenti che consentono di controllare la modalità di utilizzo del modello finito:</span><span class="sxs-lookup"><span data-stu-id="b4778-125">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="b4778-126">**Esplora modello**.</span><span class="sxs-lookup"><span data-stu-id="b4778-126">**Browse model**.</span></span> <span data-ttu-id="b4778-127">Quando questa opzione è selezionata, non appena viene completata l'elaborazione del modello da parte della procedura guidata, viene aperta una finestra **Esplora** che consente di esplorare i risultati.</span><span class="sxs-lookup"><span data-stu-id="b4778-127">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="b4778-128">Il contenuto del visualizzatore dipende dal tipo di modello compilato.</span><span class="sxs-lookup"><span data-stu-id="b4778-128">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="b4778-129">Per altre informazioni, vedere [esplorazione di un modello di previsione](browsing-a-forecasting-model.md).</span><span class="sxs-lookup"><span data-stu-id="b4778-129">For more information, see [Browsing a Forecasting Model](browsing-a-forecasting-model.md).</span></span>  
  
    -   <span data-ttu-id="b4778-130">**Abilitare il drill-through**.</span><span class="sxs-lookup"><span data-stu-id="b4778-130">**Enable drillthrough**.</span></span> <span data-ttu-id="b4778-131">Selezionare questa opzione per visualizzare i dati sottostanti dal modello finito.</span><span class="sxs-lookup"><span data-stu-id="b4778-131">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="b4778-132">Questa opzione è disponibile solo se si compila un modello Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="b4778-132">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="b4778-133">**Usa modello temporaneo**.</span><span class="sxs-lookup"><span data-stu-id="b4778-133">**Use temporary model**.</span></span> <span data-ttu-id="b4778-134">Se si seleziona questa opzione, il modello non verrà salvato nel server.</span><span class="sxs-lookup"><span data-stu-id="b4778-134">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="b4778-135">I modelli temporanei vengono eliminati quando si chiude Excel.</span><span class="sxs-lookup"><span data-stu-id="b4778-135">Temporary models are deleted when you close Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="b4778-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4778-136">Requirements</span></span>  
 <span data-ttu-id="b4778-137">I dati devono includere almeno una colonna che può essere utilizzata come serie temporale.</span><span class="sxs-lookup"><span data-stu-id="b4778-137">Your data should include at least one column that can be used as the time series.</span></span> <span data-ttu-id="b4778-138">I valori in questa colonna devono essere univoci e continui, ovvero non devono essere presenti gap.</span><span class="sxs-lookup"><span data-stu-id="b4778-138">The values in this column should be unique and continuous - that is, there should be no gaps.</span></span> <span data-ttu-id="b4778-139">Prima di eseguire la procedura guidata, ordinare i dati in base alle colonna della serie temporale in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="b4778-139">Before running the wizard, sort the data by the time series column in ascending order.</span></span>  
  
 <span data-ttu-id="b4778-140">Se i dati non includono una colonna della data o dell'ora, è possibile assegnare una serie numerica arbitraria o crearne una mediante la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b4778-140">If your data does not include a time or date column, you can assign an arbitrary numeric series, or let the wizard create one.</span></span> <span data-ttu-id="b4778-141">Se si crea la colonna di ordinamento della serie, verificare che le altre colonne vengano ordinate nell'ordine desiderato prima di avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b4778-141">F you let the wizard create the series order column, make sure the other columns are sorted in the worder you want them before starting the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4778-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4778-142">See Also</span></span>  
 <span data-ttu-id="b4778-143">[Creazione di un modello di data mining](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="b4778-143">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="b4778-144">[Strumenti di analisi tabelle di previsione &#40;per Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="b4778-144">[Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="b4778-145">Esplorazione di un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="b4778-145">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
  
