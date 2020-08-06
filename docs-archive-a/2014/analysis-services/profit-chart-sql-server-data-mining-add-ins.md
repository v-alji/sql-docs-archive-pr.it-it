---
title: Grafico profitti (componenti aggiuntivi Data mining SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- accuracy chart
- profit chart
- mining models, charting
- mining models, testing
ms.assetid: 5c902543-4da9-4db3-99d5-4ce04c43d7ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 030e511047b816543c12c81bdab307e599bbc5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629003"
---
# <a name="profit-chart-sql-server-data-mining-add-ins"></a><span data-ttu-id="565eb-102">Grafico profitti (componenti aggiuntivi Data mining di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="565eb-102">Profit Chart (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="565eb-103">![Pulsante Grafico profitti sulla barra multifunzione Data mining](media/dmc-profitchart.gif "Pulsante Grafico profitti sulla barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="565eb-103">![Profit Chart button in Data Mining ribbon](media/dmc-profitchart.gif "Profit Chart button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="565eb-104">Un grafico dei profitti consente di visualizzare l'aumento dei profitti stimato associato all'utilizzo di un modello di data mining al fine di determinare i clienti che devono essere contattati in uno scenario aziendale.</span><span class="sxs-lookup"><span data-stu-id="565eb-104">A profit chart displays the estimated profit increase that is associated with using a mining model to determine which customers a company should contact in a business scenario.</span></span> <span data-ttu-id="565eb-105">L'asse Y del grafico rappresenta i profitti, mentre l'asse X rappresenta la percentuale della popolazione contattata dall'azienda.</span><span class="sxs-lookup"><span data-stu-id="565eb-105">The Y-axis of the chart represents the profit, while the X-axis represents the percentage of the population that the company contacted.</span></span> <span data-ttu-id="565eb-106">Un grafico dei profitti tipico mostra un incremento dei profitti fino a un punto specifico, dopo il quale i profitti diminuiscono con l'aumentare della popolazione contattata.</span><span class="sxs-lookup"><span data-stu-id="565eb-106">A typical profit chart shows an increase in profits up to a point, after which profits decrease as more of the population is contacted.</span></span>  
  
## <a name="configuring-the-profit-chart"></a><span data-ttu-id="565eb-107">Configurazione del grafico dei profitti</span><span class="sxs-lookup"><span data-stu-id="565eb-107">Configuring the Profit Chart</span></span>  
 <span data-ttu-id="565eb-108">Mentre il grafico di accuratezza consente solo di valutare la probabilità che le stime siano o meno esatte, il grafico dei profitti incorpora una conoscenza reale delle conseguenze di un'azione intrapresa sulla base di una stima.</span><span class="sxs-lookup"><span data-stu-id="565eb-108">Whereas the accuracy chart assesses only the probability that predictions are right or wrong, the profit chart incorporates real-world knowledge about the consequences of taking action on a prediction.</span></span> <span data-ttu-id="565eb-109">Questo risultato si ottiene prendendo in considerazione i fattori seguenti, da specificare quando si esegue la procedura guidata:</span><span class="sxs-lookup"><span data-stu-id="565eb-109">This is achieved by taking into account the following factors, which you specify when you run the wizard:</span></span>  
  
-   <span data-ttu-id="565eb-110">**Popolazione**</span><span class="sxs-lookup"><span data-stu-id="565eb-110">**Population**</span></span>  
  
     <span data-ttu-id="565eb-111">Numero di case nel set di dati utilizzato per la creazione del grafico di accuratezza,</span><span class="sxs-lookup"><span data-stu-id="565eb-111">The number of cases in the dataset that is being used to create the lift chart.</span></span> <span data-ttu-id="565eb-112">ad esempio il numero di potenziali clienti.</span><span class="sxs-lookup"><span data-stu-id="565eb-112">For example, the number of potential customers.</span></span>  
  
-   <span data-ttu-id="565eb-113">**Costo fisso**</span><span class="sxs-lookup"><span data-stu-id="565eb-113">**Fixed Cost**</span></span>  
  
     <span data-ttu-id="565eb-114">Costi fissi associati al problema aziendale.</span><span class="sxs-lookup"><span data-stu-id="565eb-114">The fixed cost that is associated with the business problem.</span></span> <span data-ttu-id="565eb-115">Nel caso di una soluzione per il mailing diretto, i costi non dipendono da variabili quali il numero di chiamate telefoniche effettuate o il numero di mailing promozionali inviati.</span><span class="sxs-lookup"><span data-stu-id="565eb-115">If this were for a targeted mailing solution, the cost would not depend on variables such as the number of telephone calls made or the number of promotional mailings sent.</span></span>  
  
-   <span data-ttu-id="565eb-116">**Costo individuale**</span><span class="sxs-lookup"><span data-stu-id="565eb-116">**Individual Cost**</span></span>  
  
     <span data-ttu-id="565eb-117">Costi extra in aggiunta ai costi fissi che possono essere associati al contatto di ogni cliente,</span><span class="sxs-lookup"><span data-stu-id="565eb-117">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="565eb-118">relativi ad esempio a mailing promozionali o a chiamate telefoniche.</span><span class="sxs-lookup"><span data-stu-id="565eb-118">For example, promotional mailings or telephone calls.</span></span>  
  
-   <span data-ttu-id="565eb-119">**Ricavi per singolo utente**</span><span class="sxs-lookup"><span data-stu-id="565eb-119">**Revenue Per Individual**</span></span>  
  
     <span data-ttu-id="565eb-120">Importo dei ricavi associati a ogni vendita effettuata.</span><span class="sxs-lookup"><span data-stu-id="565eb-120">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="using-the-profit-chart-wizard"></a><span data-ttu-id="565eb-121">Utilizzo della procedura guidata Grafico profitti</span><span class="sxs-lookup"><span data-stu-id="565eb-121">Using the Profit Chart Wizard</span></span>  
 <span data-ttu-id="565eb-122">Per creare un grafico dei profitti, è necessario fare riferimento a un modello di data mining esistente.</span><span class="sxs-lookup"><span data-stu-id="565eb-122">To create a profit chart, you must reference an existing data mining model.</span></span> <span data-ttu-id="565eb-123">È possibile esplorare i modelli per trovare un modello che corrisponda ai dati facendo clic su **Gestisci modelli** o **Sfoglia** per visualizzare i dettagli relativi all'algoritmo utilizzato e alle colonne del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="565eb-123">You can browse models to find a model that matches your data by clicking **Manage Models** or **Browse** to see details about the algorithm that was used and the columns in the mining model.</span></span>  
  
 <span data-ttu-id="565eb-124">Per ulteriori informazioni, vedere [esplorazione di modelli in Excel &#40;SQL Server componenti aggiuntivi Data mining&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) e [gestire modelli &#40;SQL Server componenti aggiuntivi Data mining&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="565eb-124">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) and [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
#### <a name="to-create-a-profit-chart"></a><span data-ttu-id="565eb-125">Per creare un grafico dei profitti</span><span class="sxs-lookup"><span data-stu-id="565eb-125">To create a profit chart</span></span>  
  
1.  <span data-ttu-id="565eb-126">Selezionare un modello esistente.</span><span class="sxs-lookup"><span data-stu-id="565eb-126">Select an existing model.</span></span>  
  
2.  <span data-ttu-id="565eb-127">Specificare la colonna di cui si desidera eseguire la stima e un valore di destinazione, se appropriato.</span><span class="sxs-lookup"><span data-stu-id="565eb-127">Specify the column that you want to predict, and a target value, if appropriate.</span></span>  
  
3.  <span data-ttu-id="565eb-128">Selezionare i dati di origine, ovvero i dati da passare al modello per creare una stima.</span><span class="sxs-lookup"><span data-stu-id="565eb-128">Select the source data, which means the data you will pass through the model in order to create a prediction.</span></span> <span data-ttu-id="565eb-129">Tali dati non devono essere quelli utilizzati per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="565eb-129">This should not be the same data that you used to create the model.</span></span>  
  
4.  <span data-ttu-id="565eb-130">Eseguire il mapping delle colonne dei nuovi dati di origine alle colonne utilizzate nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="565eb-130">Map the columns in the new (source) date to the columns used in the data mining model.</span></span> <span data-ttu-id="565eb-131">Viene automaticamente eseguito il mapping delle colonne con nomi simili.</span><span class="sxs-lookup"><span data-stu-id="565eb-131">If the column names are similar, the wizard will automatically map them.</span></span>  
  
5.  <span data-ttu-id="565eb-132">Immettere le informazioni sui costi richieste dalla procedura guidata, ovvero i costi fissi, i costi singolo contatto, la popolazione e i ricavi previsti.</span><span class="sxs-lookup"><span data-stu-id="565eb-132">Enter the cost information required by the wizard: the fixed cost, individual cost, the population, and the revenue expected.</span></span>  
  
6.  <span data-ttu-id="565eb-133">Facoltativamente, è possibile immettere una serie progressiva di costi (fare clic sul pulsante Sfoglia **(...)** ).</span><span class="sxs-lookup"><span data-stu-id="565eb-133">Optionally, you can enter a graduated series of costs (click the browse **(...)** button).</span></span> <span data-ttu-id="565eb-134">Poiché ad esempio un'azione di mailing può diventare meno costosa aumentando il numero di unità inviate, è possibile immettere un costo diverso a seconda del numero di unità e i costi verranno adattati automaticamente per ogni dimensione del campione.</span><span class="sxs-lookup"><span data-stu-id="565eb-134">For example, a mailing might become cheaper as you increase the number of items that are sent, so you can enter a different cost depending on the number of items, and the wizard will automatically adjust the costs for each sample size.</span></span>  
  
7.  <span data-ttu-id="565eb-135">Verrà creato un grafico contenente l'analisi costi-benefici per il modello.</span><span class="sxs-lookup"><span data-stu-id="565eb-135">The wizard creates a chart that includes the cost-benefit analysis for the model.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="565eb-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="565eb-136">Requirements</span></span>  
 <span data-ttu-id="565eb-137">Per la stima di un valore numerico discreto, è necessario selezionare il valore di destinazione esatto per cui eseguire la stima.</span><span class="sxs-lookup"><span data-stu-id="565eb-137">If you are predicting a discrete numeric value, you must select the exact target value to predict.</span></span>  
  
## <a name="understanding-the-profit-chart"></a><span data-ttu-id="565eb-138">Informazioni sul grafico dei profitti</span><span class="sxs-lookup"><span data-stu-id="565eb-138">Understanding the Profit Chart</span></span>  
 <span data-ttu-id="565eb-139">Il grafico dei profitti contiene una linea verticale grigia, che è possibile spostare facendo clic su un punto del grafico.</span><span class="sxs-lookup"><span data-stu-id="565eb-139">The profit chart contains a gray vertical line, which you can move by clicking a location in the chart.</span></span> <span data-ttu-id="565eb-140">In **Legenda data mining** vengono visualizzati un punteggio, la popolazione corretta e la probabilità di stima associata alla posizione della linea grigia sul grafico.</span><span class="sxs-lookup"><span data-stu-id="565eb-140">The **Mining Legend** displays a score, the population correct, and the predict probability that are associated with the location of the gray line on the chart.</span></span> <span data-ttu-id="565eb-141">Se si seleziona il punto massimo di profitti nel grafico tramite la linea grigia, è possibile utilizzare il valore della probabilità di stima al fine di determinare una soglia di probabilità per contattare un cliente.</span><span class="sxs-lookup"><span data-stu-id="565eb-141">If you select the maximum point of profits in the chart by using the gray line, you can use the predict probability value to determine a probability threshold for contacting a customer.</span></span>  
  
 <span data-ttu-id="565eb-142">Se ad esempio il picco della curva dei profitti corrisponde al 55% della popolazione e la probabilità di stima associata è pari al 20%, per raggiungere i profitti massimi è consigliabile contattare solo i clienti la cui risposta viene stimata con una probabilità del 20% o superiore.</span><span class="sxs-lookup"><span data-stu-id="565eb-142">For example, if the peak of the profit curve is at 55 percent of the population and the associated predict probability is 20 percent, this indicates that to achieve maximum profits you should only contact those customers whose response is predicted with a 20 percent or greater probability.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565eb-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="565eb-143">See Also</span></span>  
 [<span data-ttu-id="565eb-144">Convalida di modelli e utilizzo di modelli per la stima &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="565eb-144">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
