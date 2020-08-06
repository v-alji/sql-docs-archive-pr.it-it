---
title: Creazione di una query singleton in Progettazione modelli di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton queries [Analysis Services]
- Mining Model Prediction [Analysis Services], singleton queries
ms.assetid: 6cdca8a0-cf16-46eb-a652-0bff820625ab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07491924dbcf0bd35d049e6a7c290d49becfb45d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625038"
---
# <a name="create-a-singleton-query-in-the-data-mining-designer"></a><span data-ttu-id="0df18-102">Creare una query singleton in Progettazione modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="0df18-102">Create a Singleton Query in the Data Mining Designer</span></span>
  <span data-ttu-id="0df18-103">Una query singleton è utile quando si desidera creare una stima per un singolo case.</span><span class="sxs-lookup"><span data-stu-id="0df18-103">A singleton query is useful if you want to create a prediction for a single case.</span></span> <span data-ttu-id="0df18-104">Per altre informazioni sulle query singleton, vedere [Query di data mining](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0df18-104">For more information about singleton queries, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
 <span data-ttu-id="0df18-105">Nella scheda **Stima modello di data mining** della Progettazione modelli di data mining è possibile creare diversi tipi di query.</span><span class="sxs-lookup"><span data-stu-id="0df18-105">In the **Mining Model Prediction** tab of Data Mining Designer, you can create many different types of queries.</span></span> <span data-ttu-id="0df18-106">È possibile creare una query utilizzando la finestra di progettazione oppure digitando istruzioni Data Mining Extensions (DMX).</span><span class="sxs-lookup"><span data-stu-id="0df18-106">You can create a query by using the designer, or by typing Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="0df18-107">È anche possibile iniziare con la finestra di progettazione e modificare la query creata cambiando le istruzioni DMX o aggiungendo una clausola WHERE o ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="0df18-107">You can also start with the designer and modify the query that it creates by changing the DMX statements, or by adding a WHERE or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="0df18-108">Per passare dalla visualizzazione della progettazione della query alla visualizzazione del testo della query e viceversa, fare clic sul primo pulsante nella barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="0df18-108">To switch between the query design view and the query text view, click the first button on the toolbar.</span></span> <span data-ttu-id="0df18-109">Tramite la visualizzazione del testo della query è possibile visualizzare il codice DMX creato dal generatore delle query di stima.</span><span class="sxs-lookup"><span data-stu-id="0df18-109">When you are in the query text view, you can view the DMX code that Prediction Query Builder creates.</span></span> <span data-ttu-id="0df18-110">È inoltre possibile eseguire la query, modificarla ed eseguire la query modificata.</span><span class="sxs-lookup"><span data-stu-id="0df18-110">You can also run the query, modify the query, and run the modified query.</span></span> <span data-ttu-id="0df18-111">La query modificata, tuttavia, non viene mantenuta se si torna alla visualizzazione della progettazione della query</span><span class="sxs-lookup"><span data-stu-id="0df18-111">However, the modified query is not persisted if you switch back to the query design view.</span></span>  
  
 <span data-ttu-id="0df18-112">Nel codice seguente viene illustrato un esempio di query singleton confrontato al modello di invio mirato di messaggi di posta elettronica, TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="0df18-112">The following code shows an example of a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT [Bike Buyer], PredictProbability([Bike Buyer]) as ProbableBuyer  
FROM [TM_Decision_Tree]  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="0df18-113">Nei passaggi seguenti viene descritta la creazione della query di stima.</span><span class="sxs-lookup"><span data-stu-id="0df18-113">The following steps explain how to create this prediction query.</span></span>  
  
### <a name="to-create-a-singleton-query-by-using-the-data-mining-designer"></a><span data-ttu-id="0df18-114">Per creare una query singleton utilizzando la Progettazione modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="0df18-114">To create a singleton query by using the Data Mining Designer</span></span>  
  
1.  <span data-ttu-id="0df18-115">Fare clic sulla scheda **Stima modello di data mining** in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="0df18-115">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="0df18-116">Fare clic su **Seleziona modello** nella tabella **Modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="0df18-116">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="0df18-117">Verrà visualizzata la finestra di dialogo **Seleziona modello di data mining** , in cui sono indicate tutte le strutture di data mining presenti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="0df18-117">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
     <span data-ttu-id="0df18-118">Selezionare il modello che si desidera utilizzare per creare la stima.</span><span class="sxs-lookup"><span data-stu-id="0df18-118">Select the model that you want to use for creating a prediction.</span></span>  
  
     <span data-ttu-id="0df18-119">Ad esempio, per creare il codice di esempio mostrato all'inizio di questo argomento, selezionare TM_Decision_Tree, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0df18-119">For example, to create the sample code shown at the start of this topic, select TM_Decision_Tree, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0df18-120">Fare clic su **Query singleton** sulla barra degli strumenti della scheda **Stima modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="0df18-120">Click **Singleton query** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="0df18-121">Nella scheda verrà visualizzata la tabella **Input query singleton** sulle cui colonne viene eseguito il mapping automaticamente alle colonne della tabella **Modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="0df18-121">The **Singleton Query Input** table appears on the tab, with the columns automatically mapped to the columns in the **Mining Model** table.</span></span>  
  
4.  <span data-ttu-id="0df18-122">Nella tabella **Input query singleton** selezionare nella colonna **Valore** i valori adatti a descrivere il caso per creare una stima.</span><span class="sxs-lookup"><span data-stu-id="0df18-122">On the **Singleton Query Input** table, select values in the **Value** column to describe the case for which you want to create a prediction.</span></span>  
  
     <span data-ttu-id="0df18-123">Ad esempio, selezionare **2** per **Number Children at Home**e quindi digitare `45` per **Age**.</span><span class="sxs-lookup"><span data-stu-id="0df18-123">For example, select **2** for **Number Children At Home**, and then type `45` for **Age**.</span></span>  
  
5.  <span data-ttu-id="0df18-124">Trascinare una colonna stimabile dalla tabella **modello di data mining** alla colonna **origine** nella parte inferiore della scheda. Facoltativamente, è possibile digitare un alias per la colonna.</span><span class="sxs-lookup"><span data-stu-id="0df18-124">Drag a predictable column from the **Mining Model** table to the **Source** column at the bottom of the tab. Optionally, you can type an alias for the column.</span></span>  
  
     <span data-ttu-id="0df18-125">Ad esempio, trascinare **Bike Buyer** nella colonna **Origine** .</span><span class="sxs-lookup"><span data-stu-id="0df18-125">For example, drag **Bike Buyer** to the **Source** column.</span></span>  
  
6.  <span data-ttu-id="0df18-126">Aggiungere eventuali funzionalità aggiuntive alla query selezionando **Funzione di stima** o **Espressione personalizzata** nell'elenco a discesa nella colonna **Origine** .</span><span class="sxs-lookup"><span data-stu-id="0df18-126">Add any additional functions to the query by selecting **Prediction Function** or **Custom Expression** from the drop-down list in the **Source** column.</span></span>  
  
     <span data-ttu-id="0df18-127">Ad esempio, fare clic su **Funzione di stima**e selezionare **PredictProbability**.</span><span class="sxs-lookup"><span data-stu-id="0df18-127">For example, click **Prediction Function**, and select **PredictProbability**.</span></span>  
  
7.  <span data-ttu-id="0df18-128">Fare clic su **Criteri/Argomento** nella riga **PredictProbability** e digitare il nome della colonna da stimare e facoltativamente un valore specifico da stimare.</span><span class="sxs-lookup"><span data-stu-id="0df18-128">Click **Criteria/Argument** in the **PredictProbability** row, and type the name of the column to predict, and optionally a specific value to predict.</span></span>  
  
     <span data-ttu-id="0df18-129">Ad esempio digitare `[Bike Buyer], 1`.</span><span class="sxs-lookup"><span data-stu-id="0df18-129">For example, type `[Bike Buyer], 1`.</span></span>  
  
8.  <span data-ttu-id="0df18-130">Fare clic sulla casella **Alias** nella riga **PredictProbability** e digitare un nome per fare riferimento alla nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="0df18-130">Click the **Alias** box in the **PredictProbability** row, and type a name to refer to the new column.</span></span>  
  
     <span data-ttu-id="0df18-131">Ad esempio digitare `ProbableBuyer`.</span><span class="sxs-lookup"><span data-stu-id="0df18-131">For example, type `ProbableBuyer`.</span></span>  
  
9. <span data-ttu-id="0df18-132">Fare clic su **Passa alla visualizzazione dei risultati della query** sulla barra degli strumenti della scheda **Stima modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="0df18-132">Click **Switch to query result view** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="0df18-133">Verrà visualizzata una nuova schermata con il risultato della query.</span><span class="sxs-lookup"><span data-stu-id="0df18-133">A new screen opens to show the result of the query.</span></span> <span data-ttu-id="0df18-134">Per visualizzare l'istruzione DMX appena creata, fare clic su **SQL**.</span><span class="sxs-lookup"><span data-stu-id="0df18-134">To view the DMX statement that you just created, click **SQL**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df18-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0df18-135">See Also</span></span>  
 [<span data-ttu-id="0df18-136">Query di stima &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="0df18-136">Prediction Queries &#40;Data Mining&#41;</span></span>](prediction-queries-data-mining.md)  
  
  
