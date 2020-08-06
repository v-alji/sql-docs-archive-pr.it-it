---
title: Eseguire una query sui parametri utilizzati per creare un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: ce7719e0-6127-4d9c-a753-0e0a3db065e1
author: minewiskan
ms.author: owend
ms.openlocfilehash: a3802a0d70579f613accbe6abd310da909751b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717027"
---
# <a name="query-the-parameters-used-to-create-a-mining-model"></a><span data-ttu-id="317a4-102">Eseguire query sui parametri utilizzati per creare un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="317a4-102">Query the Parameters Used to Create a Mining Model</span></span>
  <span data-ttu-id="317a4-103">La composizione di un modello di data mining non è interessata solo dai case di training, ma anche dai parametri impostati alla creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="317a4-103">The composition of a mining model is affected not only by the training cases, but by the parameters that were set when the model was created.</span></span> <span data-ttu-id="317a4-104">Pertanto, è possibile recuperare le impostazioni dei parametri di un modello esistente per comprendere meglio il comportamento dello stesso.</span><span class="sxs-lookup"><span data-stu-id="317a4-104">Therefore, you might find it useful to retrieve the parameter settings of an existing model to better understand the behavior of the model.</span></span> <span data-ttu-id="317a4-105">Il recupero dei parametri può essere utile anche per documentare una determinata versione del modello.</span><span class="sxs-lookup"><span data-stu-id="317a4-105">Retrieving parameters is also useful when documenting a particular version of that model.</span></span>  
  
 <span data-ttu-id="317a4-106">Per trovare i parametri utilizzati alla creazione del modello, creare una query su uno dei set di righe dello schema del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="317a4-106">To find the parameters that were used when the model was created, you create a query against one of the mining model schema rowsets.</span></span> <span data-ttu-id="317a4-107">In [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]questi set di righe dello schema sono esposti come set di viste di sistema su cui è possibile eseguire query in modo semplice usando la sintassi Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="317a4-107">In [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], these schema rowsets are exposed as a set of system views that you can query easily by using Transact-SQL syntax.</span></span> <span data-ttu-id="317a4-108">In questa procedura viene descritto come creare una query che restituisce i parametri utilizzati per creare il modello di data mining specificato.</span><span class="sxs-lookup"><span data-stu-id="317a4-108">This procedure describes how to create a query that returns the parameters that were used to create the specified mining model.</span></span>  
  
### <a name="to-open-a-query-window-for-a-schema-rowset-query"></a><span data-ttu-id="317a4-109">Per aprire una finestra Query per una query sul set di righe dello schema</span><span class="sxs-lookup"><span data-stu-id="317a4-109">To open a Query window for a schema rowset query</span></span>  
  
1.  <span data-ttu-id="317a4-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire l'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contenente il modello su cui eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="317a4-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the model you want to query.</span></span>  
  
2.  <span data-ttu-id="317a4-111">Fare clic con il pulsante destro del mouse sul nome dell'istanza, scegliere **Nuova query**, quindi **DMX**.</span><span class="sxs-lookup"><span data-stu-id="317a4-111">Right-click the instance name, select **New Query**, and then select **DMX**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="317a4-112"> È anche possibile creare una query su un modello di data mining tramite il modello **MDX** .</span><span class="sxs-lookup"><span data-stu-id="317a4-112">You can also create a query against a data mining model by using the **MDX** template.</span></span>  
  
3.  <span data-ttu-id="317a4-113">Se l'istanza contiene più database, selezionare quello che contiene il modello su cui eseguire la query dall'elenco **Database disponibili** nella barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="317a4-113">If the instance contains multiple databases, select the database that contains the model you want to query from the **Available Databases** list in the toolbar.</span></span>  
  
### <a name="to-return-model-parameters-for-an-existing-mining-model"></a><span data-ttu-id="317a4-114">Per restituire i parametri di un modello di data mining esistente</span><span class="sxs-lookup"><span data-stu-id="317a4-114">To return model parameters for an existing mining model</span></span>  
  
1.  <span data-ttu-id="317a4-115">Nel riquadro Query DMX digitare o incollare il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="317a4-115">In the DMX query pane, type or paste the following text:</span></span>  
  
    ```  
    SELECT MINING_PARAMETERS  
    FROM $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = ''  
    ```  
  
2.  <span data-ttu-id="317a4-116">In Esplora oggetti selezionare il modello di data mining desiderato, quindi trascinarlo nel riquadro Query DMX, tra le virgolette singole.</span><span class="sxs-lookup"><span data-stu-id="317a4-116">In Object Explorer, select the mining model you want, and then drag it into the DMX Query pane, between the single quotation marks.</span></span>  
  
3.  <span data-ttu-id="317a4-117">Premere F5 oppure fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="317a4-117">Press F5, or click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="317a4-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="317a4-118">Example</span></span>  
 <span data-ttu-id="317a4-119">Nel codice seguente viene restituito un elenco dei parametri utilizzati per creare il modello di data mining compilato nell' [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="317a4-119">The following code returns a list of the parameters that were used to create the mining model that you build in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="317a4-120">Questi parametri includono i valori espliciti relativi alle impostazioni predefinite utilizzate dai servizi di data mining disponibili dai provider nel server.</span><span class="sxs-lookup"><span data-stu-id="317a4-120">These parameters include the explicit values for any defaults used by the mining services available from providers on the server.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
 <span data-ttu-id="317a4-121">Nell'esempio di codice vengono restituiti i parametri seguenti per il modello di clustering:</span><span class="sxs-lookup"><span data-stu-id="317a4-121">The code example returns the following parameters for the clustering model:</span></span>  
  
 <span data-ttu-id="317a4-122">Risultati dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="317a4-122">eExample Results:</span></span>  
  
 <span data-ttu-id="317a4-123">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="317a4-123">MINING_PARAMETERS</span></span>  
  
 <span data-ttu-id="317a4-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span><span class="sxs-lookup"><span data-stu-id="317a4-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="317a4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="317a4-125">See Also</span></span>  
 <span data-ttu-id="317a4-126">[Attività e procedure relative alle query di data mining](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="317a4-126">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="317a4-127">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="317a4-127">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
