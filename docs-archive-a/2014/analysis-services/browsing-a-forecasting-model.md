---
title: Esplorazione di un modello di previsione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- forecasting [data mining]
- mining models, viewing
- mining model, time series
- time series [data mining]
ms.assetid: ad35a528-1949-4048-8678-3b9760c1c88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d0b188c4ed6fba9bc5b1082725b17c99081c1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625819"
---
# <a name="browsing-a-forecasting-model"></a><span data-ttu-id="1f3f9-102">Esplorazione di un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="1f3f9-102">Browsing a Forecasting Model</span></span>
  <span data-ttu-id="1f3f9-103">Quando si apre un modello di previsione utilizzando **Sfoglia**, il modello viene visualizzato in un visualizzatore interattivo, simile al Visualizzatore modello Time Series in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f3f9-103">When you open a forecasting model using **Browse**, the model is displayed in an interactive viewer, similar to the time series model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="1f3f9-104">Il visualizzatore consente di esplorare le tendenze, confrontare le serie, creare stime e ottenere informazioni sul modello e sui dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-104">The viewer helps you explore trends, compare series, create predictions, and get information about the model and the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="1f3f9-105">Esplorare il modello</span><span class="sxs-lookup"><span data-stu-id="1f3f9-105">Explore the Model</span></span>  
 <span data-ttu-id="1f3f9-106">Il visualizzatore **Browse** per i modelli di previsione fornisce una visualizzazione del grafico che mostra le tendenze nel tempo e consente di creare stime e una vista modello, che rappresenta le serie temporali come albero delle decisioni o albero di regressione.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-106">The **Browse** viewer for forecasting models provides a chart view, which shows the trends over time and lets you create predictions, and a model view, which represents the time series as a decision tree or a regression tree.</span></span>  
  
-   [<span data-ttu-id="1f3f9-107">Visualizzazione grafico</span><span class="sxs-lookup"><span data-stu-id="1f3f9-107">Chart view</span></span>](#bkmk_charts)  
  
-   [<span data-ttu-id="1f3f9-108">Visualizzazione modello</span><span class="sxs-lookup"><span data-stu-id="1f3f9-108">Model view</span></span>](#bkmk_Model)  
  
 <span data-ttu-id="1f3f9-109">Per sperimentare un modello di previsione, è possibile utilizzare i dati di esempio nella scheda previsioni della cartella di lavoro dei dati di esempio e compilare un modello Time Series utilizzando la [procedura guidata previsione &#40;componenti aggiuntivi Data mining per excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) sulla barra multifunzione **Data** mining o gli [strumenti di analisi tabelle &#40;per Excel&#41;](forecast-table-analysis-tools-for-excel.md) nella barra multifunzione **analizza** .</span><span class="sxs-lookup"><span data-stu-id="1f3f9-109">To experiment with a forecasting model, you can use the sample data on the Forecast tab of the sample data workbook, and build a time series model using the [Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) in the **Data Mining** ribbon, or [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) in the **Analyze** ribbon.</span></span>  
  
###  <a name="chart"></a><a name="bkmk_charts"></a><span data-ttu-id="1f3f9-110">Grafico</span><span class="sxs-lookup"><span data-stu-id="1f3f9-110">Chart</span></span>  
 <span data-ttu-id="1f3f9-111">Nella scheda **grafico** viene visualizzata la tendenza nella serie di dati nel corso del tempo, insieme ai valori stimati.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-111">The **Chart** tab displays the trend in your data series over time, together with the predicted values.</span></span> <span data-ttu-id="1f3f9-112">L'asse verticale del grafico rappresenta i valori della serie, mentre l'asse orizzontale rappresenta il tempo.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-112">The vertical axis of the chart represents the values of the series, and the horizontal axis represents time.</span></span>  
  
##### <a name="explore-the-forecasting-chart"></a><span data-ttu-id="1f3f9-113">Esplorare il grafico di previsione</span><span class="sxs-lookup"><span data-stu-id="1f3f9-113">Explore the forecasting chart</span></span>  
  
1.  <span data-ttu-id="1f3f9-114">Questo modello contiene più serie temporali, ma per semplificare il grafico, è possibile visualizzare una singola serie o solo alcune serie correlate.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-114">This model contains multiple time series, but to simplify the chart, you can display a single series, or just a few related series.</span></span>  
  
     <span data-ttu-id="1f3f9-115">![stime cronologiche in un modello di previsione](media/dm13-forecast-chart-historicpredictions.gif "stime cronologiche in un modello di previsione")</span><span class="sxs-lookup"><span data-stu-id="1f3f9-115">![historical predictions in the forecasting model](media/dm13-forecast-chart-historicpredictions.gif "historical predictions in the forecasting model")</span></span>  
  
     <span data-ttu-id="1f3f9-116">Utilizzare le caselle di controllo per selezionare la previsione solo per l'America del nord e solo per l'importo delle vendite.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-116">Use the check boxes to select the forecast for just North America, and just for sales Amount.</span></span>  
  
2.  <span data-ttu-id="1f3f9-117">Fare clic su **passaggi stima** e digitare un nuovo valore per controllare il numero di valori temporali futuri che si desidera visualizzare nel grafico.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-117">Click **Prediction Steps** and type a new value to control how many future time values you want to see in the chart.</span></span>  
  
     <span data-ttu-id="1f3f9-118">Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-118">The default is 5.</span></span>  
  
3.  <span data-ttu-id="1f3f9-119">Fare clic su un punto qualsiasi della riga, cronologica o futura, per visualizzare i valori esatti per quel punto nel tempo, visualizzati in **Legenda data mining**.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-119">Click any point in the line, either historical or future, to see the exact values for that point in time, displayed in the **Mining Legend**.</span></span>  
  
4.  <span data-ttu-id="1f3f9-120">Nel grafico vengono visualizzati sia i dati cronologici che i dati futuri.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-120">The chart displays both historical and future data.</span></span> <span data-ttu-id="1f3f9-121">Si noti la linea punteggiata con uno sfondo ombreggiato.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-121">Note the dotted line, with a shaded background.</span></span> <span data-ttu-id="1f3f9-122">Questi valori sono stime future, basate sul modello.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-122">These values are the future predictions, based on the model.</span></span>  
  
     <span data-ttu-id="1f3f9-123">I dati cronologici (utilizzati per compilare il modello) vengono mostrati sul lato sinistro del grafico.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-123">The historical data (which you used to build the model) is shown in the left side of the chart.</span></span>  
  
5.  <span data-ttu-id="1f3f9-124">Selezionare l'opzione **Mostra stime cronologiche** per ottenere un senso per la stabilità della serie temporale.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-124">Select the **Show historic predictions** option to get a sense for the stability of the time series.</span></span>  
  
     <span data-ttu-id="1f3f9-125">![previsione per una singola serie nel modello](media/dm13-forecast-chart-singleseries.gif "previsione per una singola serie nel modello")</span><span class="sxs-lookup"><span data-stu-id="1f3f9-125">![forecasts for a single series in the model](media/dm13-forecast-chart-singleseries.gif "forecasts for a single series in the model")</span></span>  
  
     <span data-ttu-id="1f3f9-126">Le stime cronologiche sono valori stimati basati sulla serie a quel determinato punto che vengono confrontati con i valori cronologici effettivi.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-126">Historical predictions are values predicted based on the series to that point, which are compared to actual historical values.</span></span> <span data-ttu-id="1f3f9-127">Se la linea punteggiata (contenente i valori stimati) si differenzia dalla linea continua (i valori effettivi), significa che la prima parte della serie forse non rappresenta una stima accurata dei valori successivi.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-127">If the dotted line (with the predicted values) is far apart from the solid line (the actual values), it means the first part of the series perhaps does not accurately predict the later values.</span></span> <span data-ttu-id="1f3f9-128">Potrebbero essere necessari più dati o potrebbe semplicemente essere un indicatore di volatilità nel ciclo.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-128">You might need more data, or it might simply be an indicator of volatility in the cycle.</span></span>  
  
6.  <span data-ttu-id="1f3f9-129">Selezionare l'opzione **Mostra deviazioni** per visualizzare le barre di errore nel grafico.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-129">Select the **Show Deviations** option to display error bars in the chart.</span></span>  
  
     <span data-ttu-id="1f3f9-130">Le barre di errore consentono di valutare visivamente la variabilità delle stime.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-130">The error bars let you visually assess the variability of the predictions.</span></span> <span data-ttu-id="1f3f9-131">La qualità delle stime varia a seconda dei dati di origine, ma quando si aumenta il numero di intervalli per la stima, dovrebbe essere visualizzato un aumento costante delle deviazioni.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-131">The quality of predictions varies depending on your source data, but as you increase the number of prediction steps, you should see the deviations steadily increase.</span></span>  
  
 <span data-ttu-id="1f3f9-132">**Suggerimenti**</span><span class="sxs-lookup"><span data-stu-id="1f3f9-132">**Tips**</span></span>  
  
-   <span data-ttu-id="1f3f9-133">Per abilitare o disabilitare la visualizzazione di **Legenda data mining**, fare clic con il pulsante destro del mouse su qualsiasi punto del grafico.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-133">To toggle display of the **Mining Legend**, right-click any point in the chart.</span></span>  
  
     <span data-ttu-id="1f3f9-134">È possibile visualizzare un intervallo di tempo specifico facendo clic sul grafico, trascinando una selezione temporale all'interno del grafico, quindi facendo di nuovo clic per ingrandire l'intervallo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-134">You can view a specific time range by clicking the chart, dragging a time selection across the chart, and then clicking again to zoom in on the selected range.</span></span>  
  
-   <span data-ttu-id="1f3f9-135">Per ottenere una copia del grafico corrente, fare clic su **copia in Excel**, quindi fare clic su un foglio di lavoro in Excel.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-135">To get a copy of the current chart, click **Copy to Excel**, then click a worksheet in Excel.</span></span> <span data-ttu-id="1f3f9-136">Viene inserito un elemento grafico nel foglio tramite tutte le opzioni che erano state impostate, inclusa una legenda.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-136">A graphic is inserted in the sheet using all the options you had set, including a legend.</span></span>  
  
     <span data-ttu-id="1f3f9-137">Tuttavia, questo grafico è statico, pertanto non è possibile modificare la legenda né visualizzare i dati sottostanti; Se è necessaria una visualizzazione grafico più interattiva, usare i [visualizzatori di Visio](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="1f3f9-137">However, this graphic is static so you cannot edit the legend or view the underlying data; if you need a more interactive chart view, use the [Visio viewers](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span></span>  
  
-   <span data-ttu-id="1f3f9-138">Fare clic su **ABS** nella barra dei menu del visualizzatore per passare tra le curve assolute e relative.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-138">Click **Abs** in the viewer menu bar to toggle between absolute and relative curves.</span></span>  
  
     <span data-ttu-id="1f3f9-139">Questa opzione è utile se il grafico contiene più modelli, ma la scala dei dati di ogni modello è molto diversa.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-139">This option is useful if your chart contains multiple models, but the scale of the data for each model is very different.</span></span>  
  
     <span data-ttu-id="1f3f9-140">Ad esempio, se gli archivi dell'area Pacifico sono nuovi e le vendite sono basse e se vengono utilizzati valori assoluti, la linea che mostra le vendite dell'area Pacifico potrebbe risultare piatta, rendendo difficile la visualizzazione delle modifiche effettive, mentre gli altri modelli vengono visualizzati in una scala più normale.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-140">For example, if the Pacific region stores were new and sales were low, and if absolute values are used, the line showing Pacific sales might appear flat, making it difficult to see actual changes, whereas the other models would be displayed at a more normal scale.</span></span>  
  
     <span data-ttu-id="1f3f9-141">Passando alla vista in cui vengono utilizzati valori relativi, è possibile normalizzare la scala di modelli diversi e visualizzare le differenze come percentuale delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-141">By switching the view to use relative values, you can normalize the scale of different models, and display differences as a percent of change.</span></span> <span data-ttu-id="1f3f9-142">Quando le modifiche sono relative a ogni modello, possono essere visualizzate nello stesso grafico senza una distorsione significativa.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-142">When change is relative to each model, they can be displayed in the same graph without significant distortion.</span></span>  
  
 [<span data-ttu-id="1f3f9-143">Esplorazione del modello</span><span class="sxs-lookup"><span data-stu-id="1f3f9-143">Explore the Model</span></span>](#bkmk_Top)  
  
###  <a name="model"></a><a name="bkmk_Model"></a><span data-ttu-id="1f3f9-144">Modello</span><span class="sxs-lookup"><span data-stu-id="1f3f9-144">Model</span></span>  
 <span data-ttu-id="1f3f9-145">Un modello di previsione può anche essere rappresentato come albero delle decisioni o, se la serie è principalmente lineare, modello di regressione.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-145">A forecasting model can also be represented as a decision tree, or, if the series is mostly linear, a regression model.</span></span>  
  
 <span data-ttu-id="1f3f9-146">Ad esempio, in questo modello esiste una differenza nella formula di regressione basata su una determinata condizione, pertanto l'albero si divide in due rami, ognuno con una formula di regressione diversa.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-146">For example, in this model, there is a difference in the regression formula based on a certain condition, so the tree splits into two branches, each with a different regression formula.</span></span>  
  
 <span data-ttu-id="1f3f9-147">![Filtro di una singola serie nel modello di previsione](media/dm13-forecast-model-northamerica.gif "Filtro di una singola serie nel modello di previsione")</span><span class="sxs-lookup"><span data-stu-id="1f3f9-147">![Filter single series in the forecasting model](media/dm13-forecast-model-northamerica.gif "Filter single series in the forecasting model")</span></span>  
  
##### <a name="explore-the-forecasting-model-as-a-tree"></a><span data-ttu-id="1f3f9-148">Esplorare il modello di previsione come un albero</span><span class="sxs-lookup"><span data-stu-id="1f3f9-148">Explore the forecasting model as a tree</span></span>  
  
1.  <span data-ttu-id="1f3f9-149">Fare clic sull'elenco a discesa **albero** e scegliere un modello da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-149">Click the **Tree** dropdown list and choose a model to display.</span></span>  
  
     <span data-ttu-id="1f3f9-150">Per ogni attributo stimabile viene visualizzato un nodo di regressione o un albero separato.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-150">A separate tree or regression node is displayed for each predictable attribute.</span></span> <span data-ttu-id="1f3f9-151">Ad esempio, se i dati contengono le vendite per l'Europa, l'America del nord e il Pacifico, sono presenti tre modelli diversi, uno per ogni serie di dati.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-151">For example, if your data contains sales for Europe, North America, and the Pacific, there would three different models, one for each data series.</span></span>  
  
2.  <span data-ttu-id="1f3f9-152">Trascinare il dispositivo di scorrimento **Mostra livello** per filtrare i livelli inferiori dell'albero e concentrarsi sulle divisioni più importanti.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-152">Drag the **Show Level** slider to filter out lower levels of the tree, and focus on the most important splits.</span></span>  
  
3.  <span data-ttu-id="1f3f9-153">Fare clic su ogni nodo per visualizzare alcune statistiche descrittive in **Legenda data mining**.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-153">Click each node to view some descriptive statistics in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="1f3f9-154">Quando si posiziona il mouse su un nodo, vengono visualizzate anche le stesse statistiche nella descrizione comando e la formula completa che descrive tale nodo.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-154">As you pause over a node with the mouse, a ToolTip also displays the same statistics, as well as the full formula describing that node.</span></span>  
  
4.  <span data-ttu-id="1f3f9-155">Se si desidera copiare le informazioni in **Legenda data mining**, fare clic con il pulsante destro del mouse su **Legenda data mining**, selezionare **copia**, quindi fare clic all'interno del foglio di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-155">If you want to copy the information in the **Mining Legend**, right-click the **Mining Legend**, select **Copy**, and click inside your Excel worksheet.</span></span> <span data-ttu-id="1f3f9-156">L'opzione **copia in Excel** copia il grafo, non le statistiche.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-156">The **Copy to Excel** option copies the graph, not the statistics.</span></span>  
  
 [<span data-ttu-id="1f3f9-157">Esplorazione del modello</span><span class="sxs-lookup"><span data-stu-id="1f3f9-157">Explore the Model</span></span>](#bkmk_Top)  
  
## <a name="see-also"></a><span data-ttu-id="1f3f9-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f3f9-158">See Also</span></span>  
 [<span data-ttu-id="1f3f9-159">Esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="1f3f9-159">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
