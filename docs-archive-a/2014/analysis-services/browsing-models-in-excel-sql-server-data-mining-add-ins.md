---
title: Esplorazione di modelli in Excel (SQL Server componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- browse models
- mining models, viewing
ms.assetid: a8cca1d7-602a-449a-875c-99da564965bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: c992f1f61112478a85276b6596da0137ccd5c9be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625801"
---
# <a name="browsing-models-in-excel-sql-server-data-mining-add-ins"></a><span data-ttu-id="40187-102">Esplorazione di modelli in Excel (componenti aggiuntivi Data mining di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="40187-102">Browsing Models in Excel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="40187-103">![Pulsante Esplora modello sulla barra multifunzione Data mining](media/dmc-browse.gif "Pulsante Esplora modello sulla barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="40187-103">![Browse Model button in Data Mining ribbon](media/dmc-browse.gif "Browse Model button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="40187-104">L'esplorazione visiva del modello è generalmente il modo più veloce e facile per ottenere informazioni sulle regole e sulle relazioni individuate dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="40187-104">Visually exploring the model is usually the fastest and easiest way to get an understanding of the rules and relationships discovered by analysis.</span></span> <span data-ttu-id="40187-105">Utilizzando Client di data mining per Excel, è possibile esplorare i modelli temporanei creati durante la sessione corrente di Excel e quelli archiviati in un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40187-105">By using the Data Mining Client for Excel, you can browse both temporary models created during the current Excel session, and models stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="40187-106">Per esplorare un modello, è sufficiente selezionarlo insieme alla struttura associata in un elenco di modelli disponibili. Il componente aggiuntivo selezionerà automaticamente il visualizzatore più appropriato per l'algoritmo di data mining.</span><span class="sxs-lookup"><span data-stu-id="40187-106">To browse a model, you select a model and its associated structure from a list of available models, and the add-in automatically picks the viewer that is appropriate for that data mining algorithm.</span></span> <span data-ttu-id="40187-107">È possibile eseguire il drill-down nelle tendenze più interessanti, filtrare il modello di data mining completato e copiare grafici e dati in Excel o in Visio.</span><span class="sxs-lookup"><span data-stu-id="40187-107">You can drill into the most interesting trends, filter the completed data mining model, and copy graphs and data to Excel or to Visio.</span></span>  
  
## <a name="using-the-browse-model-wizard"></a><span data-ttu-id="40187-108">Utilizzo della procedura guidata Esplora modello</span><span class="sxs-lookup"><span data-stu-id="40187-108">Using the Browse Model Wizard</span></span>  
  
1.  <span data-ttu-id="40187-109">Fare clic sulla scheda **data mining** .</span><span class="sxs-lookup"><span data-stu-id="40187-109">Click the **Data Mining** tab.</span></span>  
  
2.  <span data-ttu-id="40187-110">Nel gruppo **utilizzo modelli** fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="40187-110">In the **Model Usage** group, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="40187-111">Nella finestra di dialogo **Seleziona modello** scegliere un modello di data mining dall'elenco e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="40187-111">In the **Select Model** dialog box, choose a mining model from the list, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="40187-112">La procedura guidata consente di aprire una finestra di **esplorazione** appropriata per il tipo di modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="40187-112">The wizard opens a **Browse** window that is appropriate for the type of model that you selected.</span></span>  
  
## <a name="list-of-data-mining-viewers"></a><span data-ttu-id="40187-113">Elenco dei visualizzatori di data mining</span><span class="sxs-lookup"><span data-stu-id="40187-113">List of Data Mining Viewers</span></span>  
 <span data-ttu-id="40187-114">A seconda dell'algoritmo di data mining usato durante la creazione del modello, la finestra di **esplorazione** sarà leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="40187-114">Depending on the data mining algorithm that you used when you created the model, the **Browse** window will look a bit different.</span></span> <span data-ttu-id="40187-115">Può includere grafici per consentire l'interpretazione dei risultati, legende contenenti dettagli aggiuntivi e controlli per l'interazione con i dati.</span><span class="sxs-lookup"><span data-stu-id="40187-115">It can include graphs to help interpret the results, legends that contain additional detail, and controls for interacting with the data.</span></span>  
  
 <span data-ttu-id="40187-116">Negli argomenti seguenti sono disponibili informazioni sulle procedure per l'utilizzo di ciascuno dei visualizzatori, inclusi suggerimenti per l'interpretazione dei grafici complessi, nonché istruzioni per la modifica, la copia o l'utilizzo dei risultati.</span><span class="sxs-lookup"><span data-stu-id="40187-116">The following topics provide guidance in how to use each of the viewers, including tips on interpreting the complex graphs, and how to change, copy, or work with the results.</span></span>  
  
 [<span data-ttu-id="40187-117">Esplorazione di un modello Association Rules</span><span class="sxs-lookup"><span data-stu-id="40187-117">Browsing an Association Rules Model</span></span>](browsing-an-association-rules-model.md)  
  
 [<span data-ttu-id="40187-118">Esplorazione di un modello di clustering</span><span class="sxs-lookup"><span data-stu-id="40187-118">Browsing a Clustering Model</span></span>](browsing-a-clustering-model.md)  
  
 [<span data-ttu-id="40187-119">Esplorazione di un modello Decision Trees</span><span class="sxs-lookup"><span data-stu-id="40187-119">Browsing a Decision Trees Model</span></span>](browsing-a-decision-trees-model.md)  
  
 [<span data-ttu-id="40187-120">Esplorazione di un modello di previsione</span><span class="sxs-lookup"><span data-stu-id="40187-120">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
 [<span data-ttu-id="40187-121">Esplorazione di un modello Naïve Bayes</span><span class="sxs-lookup"><span data-stu-id="40187-121">Browsing a Naive Bayes Model</span></span>](browsing-a-naive-bayes-model.md)  
  
 [<span data-ttu-id="40187-122">Esplorazione di un modello di rete neurale</span><span class="sxs-lookup"><span data-stu-id="40187-122">Browsing a Neural Network Model</span></span>](browsing-a-neural-network-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="40187-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40187-123">See Also</span></span>  
 <span data-ttu-id="40187-124">[Visualizzazione di modelli di data mining in Visio &#40;componenti aggiuntivi Data mining&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="40187-124">[Viewing Data Mining Models in Visio &#40;Data Mining Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="40187-125">Gestire i modelli &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="40187-125">Manage Models &#40;SQL Server Data Mining Add-ins&#41;</span></span>](manage-models-sql-server-data-mining-add-ins.md)  
  
  
