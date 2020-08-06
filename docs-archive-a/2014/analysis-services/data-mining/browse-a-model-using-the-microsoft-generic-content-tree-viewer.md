---
title: Esplorare un modello utilizzando Microsoft Generic Content Tree Viewer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining model content, viewing
ms.assetid: 4a5f7c51-c704-4214-b05d-21cf735e6d96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90d47262a09060a11020e50b3724753799d2d188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637535"
---
# <a name="browse-a-model-using-the-microsoft-generic-content-tree-viewer"></a><span data-ttu-id="f7b63-102">Visualizzare un modello utilizzando Microsoft Generic Content Tree Viewer</span><span class="sxs-lookup"><span data-stu-id="f7b63-102">Browse a Model Using the Microsoft Generic Content Tree Viewer</span></span>
  <span data-ttu-id="f7b63-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer visualizza informazioni dettagliate sui modelli individuati dall'algoritmo di data mining e fornisce anche l'accesso a varie statistiche generate durante il processo di analisi.</span><span class="sxs-lookup"><span data-stu-id="f7b63-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Mining Model Content Viewer provides detailed information about the patterns found by the mining algorithm, and also provides access to various statistics generated during the analysis process.</span></span> <span data-ttu-id="f7b63-104">La quantità e il tipo di informazioni variano a seconda dell'algoritmo utilizzato, ma è possibile includere le categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7b63-104">The amount and type of information depends on the algorithm that was used, but can include the following categories:</span></span>  
  
-   <span data-ttu-id="f7b63-105">Segmenti di dati e relative caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="f7b63-105">Segments of data, and their characteristics.</span></span>  
  
-   <span data-ttu-id="f7b63-106">Statistiche descrittive su ogni gruppo o sull'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="f7b63-106">Descriptive statistics about each group or about the whole set of data.</span></span>  
  
-   <span data-ttu-id="f7b63-107">Numero di rami o nodi figlio in un albero.</span><span class="sxs-lookup"><span data-stu-id="f7b63-107">The number of branches or child nodes in a tree.</span></span>  
  
-   <span data-ttu-id="f7b63-108">Calcoli, ad esempio varianza e media, relativi a un cluster o a un intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="f7b63-108">Calculations, such as variance and mean, for a cluster or a whole set of data.</span></span>  
  
 <span data-ttu-id="f7b63-109">La visualizzazione di queste informazioni consente di interpretare in modo più efficace i risultati dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="f7b63-109">Viewing this information can help you better understand the results of your analysis.</span></span> <span data-ttu-id="f7b63-110">È inoltre possibile identificare le modalità per ottimizzare il modello e quindi ripeterne il training.</span><span class="sxs-lookup"><span data-stu-id="f7b63-110">You can also identify ways to fine-tune, and then retrain, your model.</span></span> <span data-ttu-id="f7b63-111">In alternativa, è possibile decidere di ripetere il training utilizzando un algoritmo diverso.</span><span class="sxs-lookup"><span data-stu-id="f7b63-111">Or, you might decide to retrain by using a different algorithm.</span></span>  
  
## <a name="viewing-mining-model-content"></a><span data-ttu-id="f7b63-112">Visualizzazione del contenuto di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="f7b63-112">Viewing Mining Model Content</span></span>  
 <span data-ttu-id="f7b63-113">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer vengono visualizzati elementi quali colonne, regole, proprietà, attributi, nodi e altro contenuto dal *set di righe dello schema relativo al contenuto* del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="f7b63-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Viewer displays the columns, rules, properties, attributes, nodes, and other content from the *content schema rowset* of the mining model.</span></span> <span data-ttu-id="f7b63-114">Il set di righe dello schema relativo al contenuto è un framework generico per la presentazione di informazioni dettagliate sul contenuto di un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="f7b63-114">The content schema rowset is a generic framework for presenting detailed information about the content of a data mining model.</span></span>  
  
 <span data-ttu-id="f7b63-115">Queste informazioni dettagliate sono contenute in una tabella HTML che rappresenta gli schemi, i cluster o gli alberi del modello come nodi.</span><span class="sxs-lookup"><span data-stu-id="f7b63-115">This detailed information is contained in an HTML table that represents the patterns, clusters, or trees in the model as nodes.</span></span> <span data-ttu-id="f7b63-116">È possibile fare clic su ogni nodo ed espanderlo per visualizzare più dettagli, ad esempio le formule o il conteggio di valori distinti per un attributo numerico.</span><span class="sxs-lookup"><span data-stu-id="f7b63-116">You can click on each node and expand it to see more detail, such as the formulas or the count of distinct values for a numeric attribute.</span></span> <span data-ttu-id="f7b63-117">È anche possibile esplorare le relazioni padre-figlio tra i nodi.</span><span class="sxs-lookup"><span data-stu-id="f7b63-117">You can also explore the child-parent relationships among the nodes.</span></span>  
  
 <span data-ttu-id="f7b63-118">Per altre informazioni sul significato generale dei termini usato nel contenuto di un modello di data mining, vedere [Contenuto del modello di data mining &#40;Analysis Services - Data mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f7b63-118">For more information about the general meaning of the terms used in the mining model content, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span> <span data-ttu-id="f7b63-119">In questo argomento sono inoltre contenuti i collegamenti a informazioni sul contenuto del modello di data mining per tipi di modelli specifici.</span><span class="sxs-lookup"><span data-stu-id="f7b63-119">The topic also contains links to information about mining model content for specific types of models.</span></span> <span data-ttu-id="f7b63-120">Poiché ogni tipo di modello di data mining contiene informazioni specifiche dell'algoritmo e degli schemi trovati nei dati, si consiglia di consultare l'argomento di riferimento tecnico per ogni tipo di modello per comprendere pienamente ogni tipo di modello.</span><span class="sxs-lookup"><span data-stu-id="f7b63-120">Each type of mining model contains information that is highly specific to the algorithm and the patterns found in the data, so we recommend that you consult the technical reference topic for each model type in order to fully understand each model type.</span></span>  
  
## <a name="querying-mining-model-content"></a><span data-ttu-id="f7b63-121">Esecuzione di query sul contenuto di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="f7b63-121">Querying Mining Model Content</span></span>  
 <span data-ttu-id="f7b63-122">Le stesse informazioni fornite in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer sono anche disponibili eseguendo una query sul modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="f7b63-122">The same information that is provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer is also available by querying the mining model.</span></span> <span data-ttu-id="f7b63-123">È possibile creare query sul contenuto del modello di data mining tramite istruzioni DMX (Data Mining Extension).</span><span class="sxs-lookup"><span data-stu-id="f7b63-123">You can create queries against mining model content by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="f7b63-124">Ad esempio, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]è possibile eseguire una query sul contenuto tramite l'istruzione DMX seguente:</span><span class="sxs-lookup"><span data-stu-id="f7b63-124">For example, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can run a content query by executing the following DMX statement:</span></span>  
  
```  
SELECT * FROM [<mining model name>].CONTENT  
```  
  
 <span data-ttu-id="f7b63-125">Per altre informazioni, vedere [Query di data mining](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f7b63-125">For more information, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b63-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7b63-126">See Also</span></span>  
 <span data-ttu-id="f7b63-127">[Microsoft Generic Content Tree Viewer &#40;data mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f7b63-127">[Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span></span>  
 [<span data-ttu-id="f7b63-128">Algoritmi di data mining &#40;Analysis Services - Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="f7b63-128">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
  
