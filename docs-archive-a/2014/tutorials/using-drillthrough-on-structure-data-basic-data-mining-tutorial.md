---
title: Utilizzo del drill-through sui dati della struttura (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a693979c-0564-4d6d-b35d-cbbc8f350469
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 49a1ced27150676def541548f47a90a3f847c8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623626"
---
# <a name="using-drillthrough-on-structure-data-basic-data-mining-tutorial"></a><span data-ttu-id="2969f-102">Utilizzo del drill-through sui dati della struttura (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="2969f-102">Using Drillthrough on Structure Data (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="2969f-103">Nell'ambito della campagna pubblicitaria, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] sta inviando un mailer a potenziali clienti nella 34-40 età demografica.</span><span class="sxs-lookup"><span data-stu-id="2969f-103">As part of their advertising campaign, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] is sending a mailer to potential customers in the 34-40 age demographic.</span></span> <span data-ttu-id="2969f-104">Il reparto marketing ha deciso di inviare il mailer anche ai clienti che hanno acquistato biciclette da [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] più di cinque anni fa.</span><span class="sxs-lookup"><span data-stu-id="2969f-104">The marketing department has decided that they would also like to send the mailer to the customers who purchased bikes from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] more than five years ago.</span></span> <span data-ttu-id="2969f-105">In questa lezione verranno identificati i clienti con le biciclette meno recenti e saranno recuperate le relative informazioni di contatto.</span><span class="sxs-lookup"><span data-stu-id="2969f-105">In this lesson you will identify customers with older bikes and retrieve their contact information.</span></span> <span data-ttu-id="2969f-106">Queste informazioni non sono incluse nel modello, ma sono incluse nella struttura.</span><span class="sxs-lookup"><span data-stu-id="2969f-106">This information is not included in the model, but is included in the structure.</span></span> <span data-ttu-id="2969f-107">Per recuperare le informazioni di contatto, prima ci si assicurerà che il drill-through sia abilitato per la struttura, quindi si utilizzerà il drill-through per ottenere i nomi e gli indirizzi dei clienti di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2969f-107">To retrieve the contact information you will first ensure that drillthrough is enabled for the structure and then you will use drillthrough to reveal the names and addresses of the targeted customers.</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="2969f-108">Per abilitare il drill-through su un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="2969f-108">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="2969f-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , nella scheda **modelli** di data mining di progettazione modelli di data mining, fare clic con il pulsante destro del mouse sul modello di **TM_Decision_Tree** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2969f-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the **TM_Decision_Tree** model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2969f-110">Nella finestra Proprietà fare clic su **AllowDrillthrough**e selezionare **True**.</span><span class="sxs-lookup"><span data-stu-id="2969f-110">In the Properties windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="2969f-111">Nella scheda Modelli di data mining fare clic con il pulsante destro del mouse sul modello e scegliere **Elabora modello**.</span><span class="sxs-lookup"><span data-stu-id="2969f-111">In the Mining Models tab, right-click the model, and select **Process Model**.</span></span>  
  
 <span data-ttu-id="2969f-112">Per ulteriori informazioni, vedere [query drill-through &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="2969f-112">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
### <a name="to-view-drillthrough-data-from-a-mining-model"></a><span data-ttu-id="2969f-113">Per visualizzare i dati del drill-through da un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="2969f-113">To view drillthrough data from a mining model</span></span>  
  
1.  <span data-ttu-id="2969f-114">In Progettazione modelli di data mining fare clic sulla scheda **Visualizzatore modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="2969f-114">In Data Mining Designer, click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="2969f-115">Selezionare il modello di **TM_Decision_Tree** nell'elenco **modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="2969f-115">Select the **TM_Decision_Tree** model from the **Mining Model** list.</span></span>  
  
3.  <span data-ttu-id="2969f-116">Modificare il valore di **sfondo** in `1` .</span><span class="sxs-lookup"><span data-stu-id="2969f-116">Change the **Background** value to `1`.</span></span> <span data-ttu-id="2969f-117">In questo modo, verrà visualizzata solo la parte del modello correlata ai clienti che hanno acquistato biciclette.</span><span class="sxs-lookup"><span data-stu-id="2969f-117">By doing this, you show only the part of the model that is related to customer who bought bikes.</span></span>  
  
4.  <span data-ttu-id="2969f-118">Selezionare il Visualizzatore Microsoft Decision Trees dall'elenco **Visualizzatore** .</span><span class="sxs-lookup"><span data-stu-id="2969f-118">Select the Microsoft Tree viewer from the **Viewer** list.</span></span> <span data-ttu-id="2969f-119">In questo modo verrà eseguito l'aggiornamento del visualizzatore con le nuove condizioni di filtro.</span><span class="sxs-lookup"><span data-stu-id="2969f-119">This will force the viewer to refresh with the new filter conditions.</span></span> <span data-ttu-id="2969f-120">Individuare quindi il nodo **Age >= 34 e <41** , quindi fare clic con il pulsante destro del mouse sul nodo.</span><span class="sxs-lookup"><span data-stu-id="2969f-120">Then, locate the **Age >=34 and <41** node and right-click the node.</span></span>  
  
5.  <span data-ttu-id="2969f-121">Scegliere **Drill-through**, quindi **Colonne struttura e modello** per aprire la finestra **Drill-through** .</span><span class="sxs-lookup"><span data-stu-id="2969f-121">Select **Drill Through**, and then select **Model and Structure Columns** to open the **Drill Through** window.</span></span>  
  
6.  <span data-ttu-id="2969f-122">Scorrere fino alla colonna **Structure.Date First Purchase** per visualizzare le date di acquisto delle biciclette meno recenti.</span><span class="sxs-lookup"><span data-stu-id="2969f-122">Scroll to the **Structure.Date First Purchase** column to view the purchase dates for the older bikes.</span></span>  
  
7.  <span data-ttu-id="2969f-123">Per copiare i dati negli Appunti, fare clic con il pulsante destro del mouse su qualsiasi riga nella tabella e selezionare **Copia tutto**.</span><span class="sxs-lookup"><span data-stu-id="2969f-123">To copy the data to the Clipboard, right-click any row in the table, and select **Copy All**.</span></span>  
  
 <span data-ttu-id="2969f-124">È stata completata l'esercitazione di base sul data mining.</span><span class="sxs-lookup"><span data-stu-id="2969f-124">Congratulations, you have completed the basic data mining tutorial.</span></span> <span data-ttu-id="2969f-125">Dopo avere familiarizzato con l'utilizzo degli strumenti di data mining, si consiglia di completare anche l'esercitazione intermedia sul data mining, in cui viene illustrato come creare modelli per le previsioni, le analisi degli acquisti e il clustering delle sequenze.</span><span class="sxs-lookup"><span data-stu-id="2969f-125">Now that you are comfortable using the data mining tools, we recommend that you also complete the intermediate data mining tutorial, which demonstrates how to create models for forecasting, market basket analysis, and sequence clustering.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="2969f-126">Attività precedente della lezione</span><span class="sxs-lookup"><span data-stu-id="2969f-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="2969f-127">Creazione di stime &#40;Esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="2969f-127">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2969f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2969f-128">See Also</span></span>  
 [<span data-ttu-id="2969f-129">Creare una query di stima utilizzando Generatore query di stima</span><span class="sxs-lookup"><span data-stu-id="2969f-129">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
