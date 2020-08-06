---
title: Convalida di modelli e utilizzo di modelli per la stima (componenti aggiuntivi Data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, validating
- mining models, charting
- validation [data mining]
- mining models, testing
ms.assetid: e245ac1f-1230-48e9-9091-e70b131aa2a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1dd4f9bab977a90579076b824d2c0aa525c84af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626911"
---
# <a name="validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel"></a><span data-ttu-id="c9089-102">Convalida e utilizzo dei modelli per le stime (componenti aggiuntivi Data Mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="c9089-102">Validating Models and Using Models for Prediction (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="c9089-103">Il test e la convalida del modello rappresentano un passaggio importante del processo di data mining.</span><span class="sxs-lookup"><span data-stu-id="c9089-103">Testing and validating your model is an important step in the data mining process.</span></span> <span data-ttu-id="c9089-104">Prima di distribuire i modelli in un ambiente di produzione, è fondamentale conoscerne l'efficacia in caso di applicazione a dati reali.</span><span class="sxs-lookup"><span data-stu-id="c9089-104">You must know how well your mining models perform against real data before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="c9089-105">I componenti aggiuntivi Data mining includono strumenti che consentono di testare i modelli compilati e di creare stime e indicazioni utilizzando i modelli.</span><span class="sxs-lookup"><span data-stu-id="c9089-105">The Data Mining Add-ins include tools that help you test the models you built, and create predictions and recommendations using the models.</span></span>  
  
## <a name="accuracy-chart"></a><span data-ttu-id="c9089-106">Grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="c9089-106">Accuracy Chart</span></span>  
 <span data-ttu-id="c9089-107">La procedura guidata **grafico di accuratezza** consente di creare una query di stima e di valutare le prestazioni di un modello di data mining creando un grafico di accuratezza o un grafico a dispersione.</span><span class="sxs-lookup"><span data-stu-id="c9089-107">The **Accuracy Chart** wizard helps you create a prediction query and assess the performance of a data mining model by creating a lift chart or scatter plot chart.</span></span> <span data-ttu-id="c9089-108">I grafici di accuratezza consentono di distinguere modelli quasi identici presenti in una struttura e di determinare quale sia il modello in grado di offrire le stime più accurate.</span><span class="sxs-lookup"><span data-stu-id="c9089-108">The lift chart helps distinguish between models in a structure that are almost the same, to help you determine which model provides the best predictions.</span></span>  
  
 [<span data-ttu-id="c9089-109">Grafico di accuratezza &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c9089-109">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
## <a name="classification-matrix"></a><span data-ttu-id="c9089-110">Matrice di classificazione</span><span class="sxs-lookup"><span data-stu-id="c9089-110">Classification Matrix</span></span>  
 <span data-ttu-id="c9089-111">La procedura guidata **matrice di classificazione** consente di creare una query di stima per valutare le prestazioni di un modello di classificazione.</span><span class="sxs-lookup"><span data-stu-id="c9089-111">The **Classification Matrix** wizard helps you create a prediction query to assess the performance of a classification model.</span></span> <span data-ttu-id="c9089-112">L'output è rappresentato da un grafico di riepilogo delle stime accurate e non accurate eseguite dal modello.</span><span class="sxs-lookup"><span data-stu-id="c9089-112">The output is a chart that summarizes both accurate and inaccurate predictions made by the model.</span></span> <span data-ttu-id="c9089-113">Tale matrice è uno strumento estremamente utile in quanto mostra non soltanto la frequenza dei valori stimati correttamente dal modello, ma anche i valori che il modello stima con maggiore frequenza in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="c9089-113">The matrix is a valuable tool because it not only shows how frequently the model correctly predicted a value, but also shows which values the model most frequently predicted incorrectly.</span></span>  
  
 [<span data-ttu-id="c9089-114">Matrice di classificazione &#40;SQL Server i componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c9089-114">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
## <a name="profit-chart"></a><span data-ttu-id="c9089-115">Grafico profitti</span><span class="sxs-lookup"><span data-stu-id="c9089-115">Profit Chart</span></span>  
 <span data-ttu-id="c9089-116">La procedura guidata **grafico dei profitti** consente di valutare i vantaggi derivanti dall'utilizzo di un modello di data mining e di valutare i costi di falsi positivi e falsi negativi</span><span class="sxs-lookup"><span data-stu-id="c9089-116">The **Profit Chart** wizard helps you weigh the benefits of using a data mining model and assess the costs of both false positives and false negatives</span></span>  
  
 <span data-ttu-id="c9089-117">Questo tipo di grafico misura l'accuratezza della stima del modello e incorpora i costi unitari e totali specificati.</span><span class="sxs-lookup"><span data-stu-id="c9089-117">This chart type measures the prediction accuracy of the model and incorporates unit and overall costs that you specify.</span></span>  
  
 <span data-ttu-id="c9089-118">[Grafico dei profitti &#40;SQL Server i componenti aggiuntivi Data Mining&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c9089-118">[Profit Chart &#40;SQL Server Data Mining Add-ins&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="cross-validation"></a><span data-ttu-id="c9089-119">Convalida incrociata</span><span class="sxs-lookup"><span data-stu-id="c9089-119">Cross-Validation</span></span>  
 <span data-ttu-id="c9089-120">La convalida incrociata è una tecnica consolidata di data mining utilizzata per valutare la validità di un set di dati e l'accuratezza di un modello di data mining nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="c9089-120">Cross-validation is an established technique in the data mining community for assessing the validity of a data set and the accuracy of a mining model on that data set.</span></span> <span data-ttu-id="c9089-121">Consente di dividere un set di dati in subset e quindi di creare in modo iterativo modelli in ogni subset e di eseguirne il training e il testing.</span><span class="sxs-lookup"><span data-stu-id="c9089-121">It divides a set of data into subsets, and then iteratively creates, trains, and tests models on each subset.</span></span>  
  
 <span data-ttu-id="c9089-122">La procedura guidata **convalida incrociata** consente di specificare il numero di riduzioni per cui dividere i dati, quindi fornisce un report di convalida incrociata che descrive statisticamente le differenze tra queste sezioni incrociate.</span><span class="sxs-lookup"><span data-stu-id="c9089-122">The **Cross-Validation** wizard lets you specify the number of folds to divide your data by, and then provides a cross-validation report that statistically describes the differences among these cross-sections.</span></span> <span data-ttu-id="c9089-123">In base al report, è possibile determinare se il modello è efficace per tutti i dati di training o se è appropriato per un particolare subset.</span><span class="sxs-lookup"><span data-stu-id="c9089-123">From this you can determine whether the model performs well on all training data, or might be skewed to a particular subset.</span></span>  
  
 [<span data-ttu-id="c9089-124">Convalida incrociata &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c9089-124">Cross-Validation &#40;SQL Server Data Mining Add-ins&#41;</span></span>](cross-validation-sql-server-data-mining-add-ins.md)  
  
## <a name="query-wizard"></a><span data-ttu-id="c9089-125">Procedura guidata Query</span><span class="sxs-lookup"><span data-stu-id="c9089-125">Query Wizard</span></span>  
 <span data-ttu-id="c9089-126">La procedura guidata **query** è uno strumento interattivo che consente di compilare una query di stima.</span><span class="sxs-lookup"><span data-stu-id="c9089-126">The **Query** wizard is an interactive tool that helps you build a prediction query.</span></span> <span data-ttu-id="c9089-127">Le query rappresentano il modo in cui vengono generare indicazioni, previsioni future e così via.</span><span class="sxs-lookup"><span data-stu-id="c9089-127">Queries are how you generate recommendations, future forecasts, and so forth.</span></span>  
  
 <span data-ttu-id="c9089-128">Nella procedura guidata **query** è possibile selezionare un modello e quindi fornire dati di input, come singoli valori o da una tabella o un intervallo, e la procedura guidata consente di selezionare le colonne da restituire.</span><span class="sxs-lookup"><span data-stu-id="c9089-128">In the **Query** wizard, you pick a model, and then provide input data, either as single values or from a table or range, and the wizard helps you select columns to output.</span></span> <span data-ttu-id="c9089-129">È inoltre possibile aggiungere le funzioni alla query per generare i punteggi di probabilità e altre statistiche utili.</span><span class="sxs-lookup"><span data-stu-id="c9089-129">You can also add functions to your query to generate probability scores and other useful statistics.</span></span>  
  
 [<span data-ttu-id="c9089-130">&#40;di query SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c9089-130">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
## <a name="advanced-query-editor"></a><span data-ttu-id="c9089-131">Editor avanzato query</span><span class="sxs-lookup"><span data-stu-id="c9089-131">Advanced Query Editor</span></span>  
 <span data-ttu-id="c9089-132">L' **editor di query avanzato** è un set interattivo di finestre di dialogo che consente di compilare tutti i tipi di istruzioni DMX, dall'esecuzione di query personalizzate per la creazione e il training di nuovi modelli, l'eliminazione di modelli o la creazione di nuovi set di dati.</span><span class="sxs-lookup"><span data-stu-id="c9089-132">The **Advanced Query Editor** is an interactive set of dialog boxes that helps you build all kinds of DMX statements, anything from running custom queries to creating and training new models, deleting models, or creating new data sets.</span></span>  
  
 [<span data-ttu-id="c9089-133">Editor avanzato query di data mining</span><span class="sxs-lookup"><span data-stu-id="c9089-133">Advanced Data Mining Query Editor</span></span>](advanced-data-mining-query-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="c9089-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9089-134">See Also</span></span>  
 <span data-ttu-id="c9089-135">[Esplorazione e pulizia dei dati](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="c9089-135">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="c9089-136">[Creazione di un modello di data mining](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="c9089-136">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="c9089-137">Distribuzione e scalabilità di modelli di data mining &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c9089-137">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
