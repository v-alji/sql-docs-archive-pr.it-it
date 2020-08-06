---
title: 'Attività 9: aggiunta della trasformazione Unione input multipli per combinare record corretti e con correzione | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 24ba466d-a7d3-49e7-9111-b348399c9e58
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 83afb5ea9367660048fe36d00ab59d808da17b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726363"
---
# <a name="task-9-adding-union-all-transform-to-combine-correct-and-corrected-records"></a><span data-ttu-id="58c51-102">Attività 9: Aggiunta della trasformazione Unione input multipli a Combina record corretti e con correzione</span><span class="sxs-lookup"><span data-stu-id="58c51-102">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>
  <span data-ttu-id="58c51-103">In questa attività viene aggiunta la trasformazione Unione input multipli al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="58c51-103">In this task, you add the Union All Transform to the data flow.</span></span> <span data-ttu-id="58c51-104">La trasformazione Unione input multipli consente di combinare più input in un unico output.</span><span class="sxs-lookup"><span data-stu-id="58c51-104">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="58c51-105">Nello scenario attuale i record corretti e con correzione vengono combinati in un flusso.</span><span class="sxs-lookup"><span data-stu-id="58c51-105">In your scenario, it combine both Correct and Corrected records into one stream.</span></span>  
  
1.  <span data-ttu-id="58c51-106">Trascinare la trasformazione **Unione** input multipli dalla sezione **comune** della **casella degli strumenti SSIS** alla scheda flusso di **dati** e posizionarla in **Seleziona record corretti e con correzione**.</span><span class="sxs-lookup"><span data-stu-id="58c51-106">Drag-drop **Union All** Transform from **Common** section of the **SSIS Toolbox** to the **Data Flow** tab and place it under **Pick Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="58c51-107">Fare clic con il pulsante destro del mouse su **Union All** Transform nella scheda **flusso di dati** e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="58c51-107">Right-click **Union All** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="58c51-108">Digitare **Combina record corretti e con correzione**e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="58c51-108">Type **Combine Correct and Corrected Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="58c51-109">![Combina record corretti e con correzione](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combina record corretti e con correzione")</span><span class="sxs-lookup"><span data-stu-id="58c51-109">![Combine Correct and Corrected Reocrds](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combine Correct and Corrected Reocrds")</span></span>  
  
3.  <span data-ttu-id="58c51-110">Connettersi **selezionare i record corretti e corretti** per **combinare i record corretti e con correzione** nella scheda **flusso di dati** usando il connettore blu.</span><span class="sxs-lookup"><span data-stu-id="58c51-110">Connect **Pick Correct and Corrected Records** to **Combine Correct and Corrected Records** in the **Data Flow** tab by using the blue connector.</span></span> <span data-ttu-id="58c51-111">Verrà visualizzata la finestra di dialogo **Selezione output input** .</span><span class="sxs-lookup"><span data-stu-id="58c51-111">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="58c51-112">Nella finestra di dialogo **output di input** selezionare **Correggi** per l' **output** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="58c51-112">In the **Input Output** dialog box, select **Correct** for **Output** and click **OK**.</span></span>  
  
     <span data-ttu-id="58c51-113">![Finestra di dialogo Selezione input e output](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Finestra di dialogo Selezione input e output")</span><span class="sxs-lookup"><span data-stu-id="58c51-113">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="58c51-114">Spostare il connettore intitolato **Correct** a sinistra trascinando il punto alla fine del connettore verso sinistra.</span><span class="sxs-lookup"><span data-stu-id="58c51-114">Move the connector titled **Correct** to the left by dragging and dropping the dot at the end of the connector to left.</span></span>  
  
     <span data-ttu-id="58c51-115">![Connetti Correggi a Combina corretti e con correzione](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Connetti Correggi a Combina corretti e con correzione")</span><span class="sxs-lookup"><span data-stu-id="58c51-115">![Connect Correct to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Connect Correct to Combine Correct and Corrected")</span></span>  
  
6.  <span data-ttu-id="58c51-116">Se si seleziona la trasformazione seleziona **record corretti e con correzione** , verrà visualizzato un altro connettore blu.</span><span class="sxs-lookup"><span data-stu-id="58c51-116">If you select **Pick Correct and Corrected Records** transform, you should see another blue connector.</span></span> <span data-ttu-id="58c51-117">Trascinare il connettore blu per **combinare i record corretti e con correzione**.</span><span class="sxs-lookup"><span data-stu-id="58c51-117">Drag that blue connector to **Combine Correct and Corrected Records**.</span></span>  
  
     <span data-ttu-id="58c51-118">![Connetti Con correzione a Combina corretti e con correzione](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Connetti Con correzione a Combina corretti e con correzione")</span><span class="sxs-lookup"><span data-stu-id="58c51-118">![Connect Corrected to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Connect Corrected to Combine Correct and Corrected")</span></span>  
  
7.  <span data-ttu-id="58c51-119">Il titolo del **connettore** deve essere **corretto**.</span><span class="sxs-lookup"><span data-stu-id="58c51-119">This **connector** should be titled **Corrected**.</span></span> <span data-ttu-id="58c51-120">Poiché sono presenti solo due condizioni **corrette** e **corrette e una**condizione è già stata utilizzata, la finestra di dialogo **Selezione output input** non viene visualizzata questa volta.</span><span class="sxs-lookup"><span data-stu-id="58c51-120">Since you have only two conditions **Correct** and **Corrected**, and one condition was already used, the **Input Output Selection** dialog box is not displayed this time.</span></span> <span data-ttu-id="58c51-121">Se i collegamenti si sovrappongono, spostarne uno a sinistra e l'altro a destra trascinando il collegamento a sinistra o a destra.</span><span class="sxs-lookup"><span data-stu-id="58c51-121">If the connectors overlap, move one to left and the other one to right by dragging the connector to left or right.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="58c51-122">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="58c51-122">Next Step</span></span>  
 [<span data-ttu-id="58c51-123">Attività 10: Aggiunta della trasformazione Raggruppamento fuzzy per l'identificazione di duplicati</span><span class="sxs-lookup"><span data-stu-id="58c51-123">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>](../../2014/tutorials/task-10-adding-fuzzy-group-transform-to-identify-duplicates.md)  
  
  
