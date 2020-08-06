---
title: Microsoft Generic Content Tree Viewer (data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.contentviewer.f1
ms.assetid: 751b4393-f6fd-48c1-bcef-bdca589ce34c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0dab06d6af8f2c5af029d9ce831f518faa4067e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724276"
---
# <a name="microsoft-generic-content-tree-viewer-data-mining"></a><span data-ttu-id="544a8-102">Microsoft Generic Content Tree Viewer (Data mining)</span><span class="sxs-lookup"><span data-stu-id="544a8-102">Microsoft Generic Content Tree Viewer (Data Mining)</span></span>
  <span data-ttu-id="544a8-103">In **Microsoft Generic Content Tree Viewer** vengono visualizzate informazioni dettagliate sul contenuto di un modello di data mining in un formato di tabella HTML standardizzato.</span><span class="sxs-lookup"><span data-stu-id="544a8-103">The **Microsoft Generic Content Tree Viewer** displays detailed information about the contents of a data mining mode in a standardized HTML table format.</span></span> <span data-ttu-id="544a8-104">Questa vista è utile poiché vengono esposti la struttura sottostante del modello, nonché i dettagli sui coefficienti, sulla distribuzione dei valori e così via.</span><span class="sxs-lookup"><span data-stu-id="544a8-104">This view is useful because it exposes the underlying structure of the model, as well details about coefficients, the distribution of values, and much more.</span></span>  
  
 <span data-ttu-id="544a8-105">Il contenuto effettivo visualizzato nella tabella varia a seconda dell'algoritmo utilizzato e possono essere inclusi colonne, regole, proprietà, attributi, nodi e formule.</span><span class="sxs-lookup"><span data-stu-id="544a8-105">The actual content displayed in the table varies depending on the algorithm that was used and might include columns, rules, properties, attributes, nodes, and formulas.</span></span> <span data-ttu-id="544a8-106">Per altre informazioni sul contenuto del modello e su come interpretare le informazioni per ogni tipo di modello, vedere [Contenuto del modello di data mining &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="544a8-106">For more information about model content, and how to interpret the information for each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="544a8-107">Per le informazioni fornite nel visualizzatore viene utilizzata una struttura comune basata sul set di righe dello schema relativo al contenuto per i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="544a8-107">The information that is displayed in the viewer uses a common structure that is based on the content schema rowset for mining models.</span></span> <span data-ttu-id="544a8-108">Tale set di righe è un framework generico per l'archiviazione degli schemi, delle statistiche e di altro contenuto di un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="544a8-108">The content schema rowset is a generic framework for storing patterns, statistics, and other contents of a data mining model.</span></span> <span data-ttu-id="544a8-109">Per un elenco delle colonne del set di righe dello schema di data mining per i modelli di data mining, vedere [Set di righe DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="544a8-109">For a list of the columns in the data mining schema rowset for mining models, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
## <a name="options"></a><span data-ttu-id="544a8-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="544a8-110">Options</span></span>  
 <span data-ttu-id="544a8-111">**Didascalia del nodo (ID univoco)**</span><span class="sxs-lookup"><span data-stu-id="544a8-111">**Node caption (Unique ID)**</span></span>  
 <span data-ttu-id="544a8-112">In questo riquadro viene visualizzato un elenco di tutti i nodi nel modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="544a8-112">This pane displays a list of all the nodes in the selected mining model.</span></span> <span data-ttu-id="544a8-113">La modalità di disposizione dei nodi nell'albero è diversa a seconda del tipo di modello visualizzato.</span><span class="sxs-lookup"><span data-stu-id="544a8-113">The way the nodes are arranged in the tree is different depending on the type of model you are viewing.</span></span>  
  
 <span data-ttu-id="544a8-114">È possibile fare clic su ogni nodo per visualizzare le relative informazioni dettagliate nel riquadro **Dettagli nodo** .</span><span class="sxs-lookup"><span data-stu-id="544a8-114">You can click each node to display details about the node in the **Node details** pane.</span></span>  
  
 <span data-ttu-id="544a8-115">**Dettagli nodo**</span><span class="sxs-lookup"><span data-stu-id="544a8-115">**Node details**</span></span>  
 <span data-ttu-id="544a8-116">Vengono visualizzate informazioni dettagliate sul contenuto del nodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="544a8-116">Displays detailed information about the content of the selected node.</span></span> <span data-ttu-id="544a8-117">In ogni nodo vengono archiviate le relative informazioni in un formato standardizzato, tuttavia il contenuto e il significato di ogni riga della tabella dipendono dal tipo di modello o di nodo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="544a8-117">Each node stores its information in a standardized format, but the contents and significance of each line of the table depends on the type of model or type of node that you are viewing.</span></span> <span data-ttu-id="544a8-118">Ad esempio, le informazioni archiviate per un nodo che rappresenta una regola in un modello di associazione sono diverse rispetto a quelle di un nodo che rappresenta un albero in un modello di albero delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="544a8-118">For example, the information stored for a node that represents a rule in an association model contains different information than a node that represents a tree in a decision trees model.</span></span>  
  
 <span data-ttu-id="544a8-119">Per informazioni su come interpretare le informazioni per un tipo di modello specifico, vedere [Contenuto del modello di data mining &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="544a8-119">For information about how to interpret the node information for a specific model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="544a8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="544a8-120">See Also</span></span>  
 <span data-ttu-id="544a8-121">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="544a8-121">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="544a8-122">[Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="544a8-122">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="544a8-123">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="544a8-123">Data Mining Queries</span></span>](data-mining/data-mining-queries.md)  
  
  
