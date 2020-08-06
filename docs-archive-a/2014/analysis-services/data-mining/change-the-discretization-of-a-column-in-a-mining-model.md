---
title: Modificare la discretizzazione di una colonna in un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- discretization [Analysis Services]
- mining structures [Analysis Services], how-to topics
- discretized columns [data mining]
- bucketing problems [Analysis Services]
ms.assetid: 3c49862b-595d-4fa4-b890-e2e1bde1d74f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b20d6428afac5c1492fdc74aafd4d0c010159d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636486"
---
# <a name="change-the-discretization-of-a-column-in-a-mining-model"></a><span data-ttu-id="17862-102">Modificare la discretizzazione di una colonna in un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="17862-102">Change the Discretization of a Column in a Mining Model</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="17862-103">discretizzazione automaticamente i valori, ovvero i dati vengono collocati in una colonna numerica, in determinati scenari.</span><span class="sxs-lookup"><span data-stu-id="17862-103">automatically discretizes values-that is to say, it bins data in numeric column-in certain scenarios.</span></span> <span data-ttu-id="17862-104">Se, ad esempio, i dati includono dati numerici continui e si crea un modello di albero delle decisioni, ogni colonna di dati continui verrà automaticamente inserita in contenitori, a seconda della distribuzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="17862-104">For example, if your data contains continuous numeric data and you create a decision tree model, each column of continuous data will be automatically binned, depending on the distribution of the data.</span></span> <span data-ttu-id="17862-105">Se si desidera determinare il metodo di discretizzazione dei dati, è necessario modificare le proprietà nella colonna della struttura di data mining che controlla la modalità di utilizzo dei dati del modello.</span><span class="sxs-lookup"><span data-stu-id="17862-105">If you want to control how the data is discretized, you must change the properties on the mining structure column that control how the data is used in the model.</span></span>  
  
 <span data-ttu-id="17862-106">Per informazioni generali su come impostare le proprietà in un modello di data mining, vedere [Colonne del modello di data mining](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="17862-106">For general information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-display-the-properties-for-a-mining-model-column"></a><span data-ttu-id="17862-107">Per visualizzare le proprietà per una colonna del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="17862-107">To display the properties for a mining model column</span></span>  
  
1.  <span data-ttu-id="17862-108">Nella scheda **Modelli di data mining** di Progettazione modelli di data mining fare clic con il pulsante destro del mouse sull'intestazione di colonna che contiene il nome del modello di data mining o sulla riga della griglia che contiene il nome dell'algoritmo di data mining, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="17862-108">In the **Mining Models** tab in Data Mining Designer, right-click the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
     <span data-ttu-id="17862-109">Nella finestra **Proprietà** vengono visualizzate le proprietà associate all'intero modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="17862-109">The **Properties** window displays the properties that are associated with the mining model as a whole.</span></span>  
  
2.  <span data-ttu-id="17862-110">Nella colonna **Struttura** a sinistra dello schermo fare clic sulla colonna contenente i dati numerici continui che si desidera discretizzare.</span><span class="sxs-lookup"><span data-stu-id="17862-110">In the **Structure** column near the left side of the screen, click the column that contains the continuous numeric data you want to discretize.</span></span>  
  
     <span data-ttu-id="17862-111">La finestra **Proprietà** viene modificata per visualizzare solo le proprietà associate alla colonna.</span><span class="sxs-lookup"><span data-stu-id="17862-111">The **Properties** window changes to display just the properties associated with that column.</span></span>  
  
### <a name="to-change-the-discretization-method"></a><span data-ttu-id="17862-112">Per modificare il metodo di discretizzazione</span><span class="sxs-lookup"><span data-stu-id="17862-112">To change the discretization method</span></span>  
  
1.  <span data-ttu-id="17862-113">Nella finestra **Proprietà data mining** fare clic sulla casella di testo accanto a **contenuto**e selezionare nell' `Discretized` elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="17862-113">In the **Mining Properties** window, click the text box next to **Content**, and select `Discretized` from the dropdown list.</span></span>  
  
     <span data-ttu-id="17862-114">Nella finestra <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> e <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> sono ora abilitate.</span><span class="sxs-lookup"><span data-stu-id="17862-114">The <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> properties are now enabled.</span></span>  
  
2.  <span data-ttu-id="17862-115">Nella finestra **Proprietà** fare clic sulla casella di testo accanto a <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> e selezionare uno dei valori seguenti: `Automatic` , `EqualAreas` o `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="17862-115">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationMethod%2A> and select one of the following values: `Automatic`, `EqualAreas`, or `Cluster`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="17862-116">Se l'utilizzo della colonna è impostato su `Ignore` , la finestra **Proprietà** per la colonna è vuota.</span><span class="sxs-lookup"><span data-stu-id="17862-116">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="17862-117">Il nuovo valore diventerà effettivo quando si seleziona un elemento diverso nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="17862-117">The new value will take effect when you select a different element in the designer.</span></span>  
  
3.  <span data-ttu-id="17862-118">Nella scheda **Proprietà** fare clic sulla casella di testo accanto a <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> e digitare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="17862-118">In the **Properties** window, click the text box next to <xref:Microsoft.AnalysisServices.ScalarMiningStructureColumn.DiscretizationBucketCount%2A> and type a numeric value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="17862-119">Se si modificano queste proprietà, è necessario rielaborare la struttura, insieme ai modelli che dovranno utilizzare la nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="17862-119">If you change these properties, the structure must be reprocessed, along with any models that you want to use the new setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17862-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17862-120">See Also</span></span>  
 [<span data-ttu-id="17862-121">Attività e procedure relative al modello di data mining</span><span class="sxs-lookup"><span data-stu-id="17862-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
