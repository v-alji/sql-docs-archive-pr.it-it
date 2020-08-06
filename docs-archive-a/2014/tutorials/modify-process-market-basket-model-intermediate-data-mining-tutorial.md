---
title: Modifica ed elaborazione del modello Market Basket (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b6019413-aebd-4ff7-831a-644572ad88b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 369de98e944c5ccf5d06ef61eaa16c06bb864e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623669"
---
# <a name="modifying-and-processing-the-market-basket-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="81c06-102">Modifica ed elaborazione del modello Market Basket (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="81c06-102">Modifying and Processing the Market Basket Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="81c06-103">Prima di elaborare il modello di data mining di associazione creato, è necessario modificare i valori predefiniti di due parametri, ovvero *supporto* e *probabilità*.</span><span class="sxs-lookup"><span data-stu-id="81c06-103">Before you process the association mining model that you created, you must change the default values of two of the parameters: *Support* and *Probability*.</span></span>  
  
-   <span data-ttu-id="81c06-104">Il *supporto* definisce la percentuale di case in cui deve esistere una regola prima che venga considerata valida.</span><span class="sxs-lookup"><span data-stu-id="81c06-104">*Support* defines the percentage of cases in which a rule must exist before it is considered valid.</span></span> <span data-ttu-id="81c06-105">Sarà necessario specificare che la regola deve essere presente almeno nell'1% dei case.</span><span class="sxs-lookup"><span data-stu-id="81c06-105">You will specify that a rule must be found in at least 1 percent of cases.</span></span>  
  
-   <span data-ttu-id="81c06-106">La *probabilità* definisce la probabilità che un'associazione debba essere considerata valida.</span><span class="sxs-lookup"><span data-stu-id="81c06-106">*Probability* defines how likely an association must be before it is considered valid.</span></span> <span data-ttu-id="81c06-107">Verrà presa in considerazione ogni associazione con almeno il 10% di probabilità.</span><span class="sxs-lookup"><span data-stu-id="81c06-107">You will consider any association with a probability of at least 10 percent.</span></span>  
  
 <span data-ttu-id="81c06-108">Per ulteriori informazioni sugli effetti dell'aumento o della riduzione del supporto e della probabilità, vedere [riferimento tecnico per l'algoritmo Microsoft Association](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="81c06-108">For more information about the effects of increasing or decreasing support and probability, see [Microsoft Association Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="81c06-109">Dopo aver definito la struttura e i parametri per il modello di data mining **Association** , il modello viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="81c06-109">After you have defined the structure and parameters for the **Association** mining model, you will process the model.</span></span>  
  
### <a name="to-adjust-the-parameters-of-the-association-model"></a><span data-ttu-id="81c06-110">Per adattare i parametri del modello Association</span><span class="sxs-lookup"><span data-stu-id="81c06-110">To adjust the parameters of the Association model</span></span>  
  
1.  <span data-ttu-id="81c06-111">Aprire la scheda **modelli di data mining** di progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="81c06-111">Open the **Mining Models** tab of Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="81c06-112">Fare clic con il pulsante destro del mouse sulla colonna **Association** nella griglia nella finestra di progettazione e selezionare **Imposta parametri algoritmo per aprire la finestra di dialogo parametri algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="81c06-112">Right-click the **Association** column in the grid in the designer and select **Set Algorithm Parameters to open the Algorithm Parameters** dialog box.</span></span>  
  
3.  <span data-ttu-id="81c06-113">Nella colonna **valore** della finestra di dialogo **parametri algoritmo** impostare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="81c06-113">In the **Value** column of the **Algorithm Parameters** dialog box, set the following parameters:</span></span>  
  
     <span data-ttu-id="81c06-114">MINIMUM_PROBABILITY = 0,1</span><span class="sxs-lookup"><span data-stu-id="81c06-114">MINIMUM_PROBABILITY = 0.1</span></span>  
  
     <span data-ttu-id="81c06-115">MINIMUM_SUPPORT = 0,01</span><span class="sxs-lookup"><span data-stu-id="81c06-115">MINIMUM_SUPPORT = 0.01</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-process-the-mining-model"></a><span data-ttu-id="81c06-116">Per elaborare il modello di data mining</span><span class="sxs-lookup"><span data-stu-id="81c06-116">To process the mining model</span></span>  
  
1.  <span data-ttu-id="81c06-117">**Mining Model** [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Scegliere **Elabora struttura di data mining e tutti i modelli** dal menu modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="81c06-117">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models.**</span></span>  
  
2.  <span data-ttu-id="81c06-118">Quando si chiede se si desidera compilare e distribuire il progetto, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="81c06-118">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
     <span data-ttu-id="81c06-119">Verrà visualizzata la finestra di dialogo **Elabora struttura di data mining-Association** .</span><span class="sxs-lookup"><span data-stu-id="81c06-119">The **Process Mining Structure - Association** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="81c06-120">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="81c06-120">Click **Run**.</span></span>  
  
     <span data-ttu-id="81c06-121">Verrà visualizzata la finestra di dialogo **stato** elaborazione per visualizzare le informazioni sull'elaborazione del modello.</span><span class="sxs-lookup"><span data-stu-id="81c06-121">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="81c06-122">L'elaborazione della nuova struttura e del nuovo modello potrebbe richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="81c06-122">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="81c06-123">Al termine dell'elaborazione, fare clic su **Chiudi** per uscire dalla finestra di dialogo **stato** elaborazione.</span><span class="sxs-lookup"><span data-stu-id="81c06-123">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="81c06-124">Fare di nuovo clic su **Chiudi per chiudere** la finestra di dialogo **Elabora struttura di data mining-Association** .</span><span class="sxs-lookup"><span data-stu-id="81c06-124">Click **Close** again to exit the **Process Mining Structure - Association** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="81c06-125">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="81c06-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="81c06-126">Esplorazione dei modelli Market basket &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="81c06-126">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="81c06-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81c06-127">See Also</span></span>  
 [<span data-ttu-id="81c06-128">Requisiti e considerazioni sull'elaborazione &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="81c06-128">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
