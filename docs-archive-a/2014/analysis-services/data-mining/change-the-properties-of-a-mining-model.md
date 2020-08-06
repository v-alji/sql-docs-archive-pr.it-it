---
title: Modificare le proprietà di un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- properties [data mining]
ms.assetid: aefaeb7f-d174-48d1-a188-0987a3b1196b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 395e6a4cb9c0f0dac0f0c717dfe0695033cad050
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624435"
---
# <a name="change-the-properties-of-a-mining-model"></a><span data-ttu-id="66e01-102">Modificare le proprietà di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="66e01-102">Change the Properties of a Mining Model</span></span>
  <span data-ttu-id="66e01-103">Alcune proprietà dei modelli di data mining si applicano all'intero modello, altre solo a singole colonne.</span><span class="sxs-lookup"><span data-stu-id="66e01-103">Some mining model properties apply to the model as a whole, and other model properties apply to individual columns.</span></span> <span data-ttu-id="66e01-104">Esempi di proprietà che si applicano all'intero modello sono la proprietà `Drillthrough`, che specifica se i dati del case devono essere disponibili per le query, e la proprietà `Description`.</span><span class="sxs-lookup"><span data-stu-id="66e01-104">Examples of properties that apply to the entire model would be the `Drillthrough` property, which specifies whether the case data should be available for querying, and the `Description` property.</span></span> <span data-ttu-id="66e01-105">Le proprietà che si applicano alle singole colonne sono `Usage` e `ModelingFlags`, che controllano il modo in cui i dati della colonna vengono utilizzati all'interno del modello.</span><span class="sxs-lookup"><span data-stu-id="66e01-105">Properties that apply to the column include `Usage` and `ModelingFlags`, which control how data in the column is used within the model.</span></span>  
  
 <span data-ttu-id="66e01-106">Le proprietà del modello seguenti sono associate a editor avanzati che è possibile utilizzare per creare espressioni o configurare proprietà più complesse.</span><span class="sxs-lookup"><span data-stu-id="66e01-106">The following model properties have advanced editors that you can use to create expressions or configure complex model properties.</span></span> <span data-ttu-id="66e01-107">Di seguito sono elencate queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="66e01-107">The following properties provide:</span></span>  
  
-   <span data-ttu-id="66e01-108">`Filter`Proprietà: apre la finestra di [dialogo filtro del set di dati o filtro modello](../data-set-filter-or-model-filter-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="66e01-108">`Filter` property: Opens the [Data Set Filter or Model Filter Dialog Box](../data-set-filter-or-model-filter-dialog-box.md).</span></span>  
  
-   <span data-ttu-id="66e01-109">`AlgorithmParameters`Proprietà: apre la finestra di [dialogo parametri algoritmo &#40;&#41;visualizzazione modelli di data mining ](../algorithm-parameters-dialog-box-mining-models-view.md).</span><span class="sxs-lookup"><span data-stu-id="66e01-109">`AlgorithmParameters` property: Opens the [Algorithm Parameters Dialog Box &#40;Mining Models View&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span></span>  
  
 <span data-ttu-id="66e01-110">Per informazioni su come impostare le proprietà in un modello di data mining, vedere [Colonne del modello di data mining](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="66e01-110">For information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model"></a><span data-ttu-id="66e01-111">Per modificare le proprietà di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="66e01-111">To change the properties of a mining model</span></span>  
  
1.  <span data-ttu-id="66e01-112">Nella scheda **Modelli di data mining** di Progettazione modelli di data mining fare clic con il pulsante destro del mouse sull'intestazione di colonna che contiene il nome del modello di data mining o sulla riga della griglia che contiene il nome dell'algoritmo di data mining e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="66e01-112">In the **Mining Models** tab in Data Mining Designer, right-click either the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="66e01-113">Nella finestra **Proprietà** a destra dello schermo evidenziare il valore corrispondente alla proprietà da modificare e quindi immettere il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="66e01-113">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
     <span data-ttu-id="66e01-114">Il nuovo valore diventerà effettivo quando si seleziona un elemento diverso nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="66e01-114">The new value will take effect when you select a different element in the designer.</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model-column"></a><span data-ttu-id="66e01-115">Per modificare le proprietà di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="66e01-115">To change the properties of a mining model column</span></span>  
  
1.  <span data-ttu-id="66e01-116">Nella scheda **Modelli di data mining** di Progettazione modelli di data mining fare clic con il pulsante destro del mouse sulla cella della griglia in corrispondenza dell'intersezione tra la colonna della struttura di data mining e il modello di data mining e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="66e01-116">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the grid at the intersection of the mining structure column and the mining model, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="66e01-117">Nella finestra **Proprietà** a destra dello schermo evidenziare il valore corrispondente alla proprietà da modificare e quindi immettere il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="66e01-117">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="66e01-118">Se l'utilizzo della colonna è impostato su `Ignore` , la finestra **Proprietà** per la colonna è vuota.</span><span class="sxs-lookup"><span data-stu-id="66e01-118">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="66e01-119">Il nuovo valore diventerà effettivo quando si seleziona un elemento diverso nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="66e01-119">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e01-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66e01-120">See Also</span></span>  
 [<span data-ttu-id="66e01-121">Attività e procedure relative al modello di data mining</span><span class="sxs-lookup"><span data-stu-id="66e01-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
