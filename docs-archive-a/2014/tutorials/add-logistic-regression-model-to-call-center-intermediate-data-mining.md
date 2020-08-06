---
title: Aggiunta di un modello di regressione logistica alla struttura del Call Center (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 97abb77a-346c-44fa-8959-688dee1af6a8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7d0100313d1ea5a1af5f729249bc2d743a730222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720561"
---
# <a name="adding-a-logistic-regression-model-to-the-call-center-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="96b95-102">Aggiunta di un modello di regressione logistica alla struttura del call center (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="96b95-102">Adding a Logistic Regression Model to the Call Center Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="96b95-103">Oltre ad analizzare i fattori che potrebbero influire sul funzionamento del call center, è inoltre necessario fornire alcuni consigli specifici su come il personale può migliorare la qualità del servizio.</span><span class="sxs-lookup"><span data-stu-id="96b95-103">In addition to analyzing the factors that might affect call center operations, you were also asked to provide some specific recommendations on how the staff can improve service quality.</span></span> <span data-ttu-id="96b95-104">In questa attività verrà utilizzata la stessa struttura di data mining utilizzata per compilare il modello esplorativo e verrà aggiunto un modello di data mining che sarà utilizzato per la creazione di stime.</span><span class="sxs-lookup"><span data-stu-id="96b95-104">In this task, you will use the same mining structure that you used to build the exploratory model and add a mining model that will be used for creating predictions.</span></span>  
  
 <span data-ttu-id="96b95-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] un modello di regressione logistica è basato sull'algoritmo Microsoft Neural Network e pertanto fornisce la stessa flessibilità e le funzionalità di un modello di rete neurale.</span><span class="sxs-lookup"><span data-stu-id="96b95-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a logistic regression model is based on the neural networks algorithm, and therefore provides the same flexibility and power as a neural network model.</span></span> <span data-ttu-id="96b95-106">La regressione logistica è tuttavia particolarmente appropriata per stimare risultati binari.</span><span class="sxs-lookup"><span data-stu-id="96b95-106">However, logistic regression is particularly well-suited for predicting binary outcomes.</span></span>  
  
 <span data-ttu-id="96b95-107">Per questo scenario si utilizzerà la stessa struttura di data mining utilizzata per il modello di rete neurale.</span><span class="sxs-lookup"><span data-stu-id="96b95-107">For this scenario, you will use the same mining structure that you used for the neural network model.</span></span> <span data-ttu-id="96b95-108">Il nuovo modello verrà tuttavia personalizzato per soddisfare le esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="96b95-108">However, you will customize the new model to target your business questions.</span></span> <span data-ttu-id="96b95-109">Si desidera migliorare la qualità del servizio e determinare quanti operatori esperti sono necessari, pertanto si configurerà il modello per stimare tali valori.</span><span class="sxs-lookup"><span data-stu-id="96b95-109">You are interested in improving service quality and determining how many experienced operators you need, so you will set up your model to predict those values.</span></span>  
  
 <span data-ttu-id="96b95-110">Per assicurarsi che i tutti i modelli basati sui dati del call center siano il più possibile simili, si utilizzerà lo stesso valore di inizializzazione precedente.</span><span class="sxs-lookup"><span data-stu-id="96b95-110">To ensure that all the models based on the call center data are as similar as possible, you will use the same seed value as before.</span></span> <span data-ttu-id="96b95-111">L'impostazione del parametro del valore di inizializzazione assicura che il modello elabori i dati dallo stesso punto iniziale e riduca le variazioni causate dagli elementi nei dati.</span><span class="sxs-lookup"><span data-stu-id="96b95-111">Setting the seed parameter ensures that the model processes the data from the same starting point, and minimizes variations caused by artifacts in the data.</span></span>  
  
### <a name="to-add-a-new-mining-model-to-the-call-center-mining-structure"></a><span data-ttu-id="96b95-112">Per aggiungere un nuovo modello di data mining alla struttura di data mining del call center</span><span class="sxs-lookup"><span data-stu-id="96b95-112">To add a new mining model to the call center mining structure</span></span>  
  
1.  <span data-ttu-id="96b95-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Esplora soluzioni fare clic con il pulsante destro del mouse sulla struttura di data mining **Call Center**e scegliere **Apri finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="96b95-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, right-click the mining structure, **Call Center Binned**, and select **Open Designer**.</span></span>  
  
2.  <span data-ttu-id="96b95-114">In Progettazione modelli di data mining fare clic sulla scheda **modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="96b95-114">In Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="96b95-115">Fare clic su **Crea un modello di data mining correlato**.</span><span class="sxs-lookup"><span data-stu-id="96b95-115">Click **Create a related mining model**.</span></span>  
  
4.  <span data-ttu-id="96b95-116">Nella finestra di dialogo **nuovo modello di data mining** Digitare per **nome modello** `Call Center - LR` .</span><span class="sxs-lookup"><span data-stu-id="96b95-116">In the **New Mining Model** dialog box, for **Model name**, type `Call Center - LR`.</span></span>  <span data-ttu-id="96b95-117">Per **Nome algoritmo**selezionare **regressione logistica Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="96b95-117">For **Algorithm name**, select **Microsoft Logistic Regression**.</span></span>  
  
5.  <span data-ttu-id="96b95-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96b95-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="96b95-119">Il nuovo modello di data mining viene visualizzato nella scheda **modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="96b95-119">The new mining model is displayed in the **Mining Models** tab.</span></span>  
  
### <a name="to-customize-the-logistic-regression-model"></a><span data-ttu-id="96b95-120">Per personalizzare il modello di regressione logistica</span><span class="sxs-lookup"><span data-stu-id="96b95-120">To customize the logistic regression model</span></span>  
  
1.  <span data-ttu-id="96b95-121">Nella colonna per il nuovo modello di data mining, `Call Center - LR` lasciare fact callcenter ID come chiave.</span><span class="sxs-lookup"><span data-stu-id="96b95-121">In the column for the new mining model, `Call Center - LR`, leave Fact CallCenter ID as the key.</span></span>  
  
2.  <span data-ttu-id="96b95-122">Modificare il valore di ServiceGrade e di Level Two Operators in **Predict**.</span><span class="sxs-lookup"><span data-stu-id="96b95-122">Change the value of ServiceGrade and Level Two Operators to **Predict**.</span></span>  
  
     <span data-ttu-id="96b95-123">Queste colonne verranno utilizzate sia per la stima che per l'input.</span><span class="sxs-lookup"><span data-stu-id="96b95-123">These columns will be used both as input and for prediction.</span></span> <span data-ttu-id="96b95-124">In sostanza, si creano due modelli separati basati sugli stessi dati: uno che stima il numero di operatori e uno che stima il livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="96b95-124">In essence, you are creating two separate models on the same data: one that predicts the number of operators, and one that predicts the service grade.</span></span>  
  
3.  <span data-ttu-id="96b95-125">Modificare tutte le altre colonne in **input**.</span><span class="sxs-lookup"><span data-stu-id="96b95-125">Change all other columns to **Input**.</span></span>  
  
### <a name="to-specify-the-seed-and-process-the-models"></a><span data-ttu-id="96b95-126">Per specificare il valore di inizializzazione ed elaborare i modelli</span><span class="sxs-lookup"><span data-stu-id="96b95-126">To specify the seed and process the models</span></span>  
  
1.  <span data-ttu-id="96b95-127">Nella scheda **modello di data mining** fare clic con il pulsante destro del mouse sulla colonna per il modello denominato Call Center-LR, quindi scegliere **Imposta parametri algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="96b95-127">In the **Mining Model** tab, right-click the column for the model named Call Center - LR, and select **Set Algorithm Parameters**.</span></span>  
  
2.  <span data-ttu-id="96b95-128">Nella riga relativa al parametro HOLDOUT_SEED fare clic sulla cella vuota in **valore**, quindi digitare `1` .</span><span class="sxs-lookup"><span data-stu-id="96b95-128">In the row for the HOLDOUT_SEED parameter, click the empty cell under **Value**, and type `1`.</span></span> <span data-ttu-id="96b95-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96b95-129">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="96b95-130">Il valore scelto come valore di inizializzazione non è importante, a condizione che si utilizzi lo stesso valore di inizializzazione per tutti i modelli correlati.</span><span class="sxs-lookup"><span data-stu-id="96b95-130">The value that you choose as the seed does not matter, as long as you use the same seed for all related models.</span></span>  
  
3.  <span data-ttu-id="96b95-131">Scegliere **Elabora struttura di data mining e tutti i modelli**dal menu **modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="96b95-131">In the **Mining Models** menu, select **Process Mining Structure and All Models**.</span></span> <span data-ttu-id="96b95-132">Fare clic su **Sì** per distribuire il progetto data mining aggiornato al server.</span><span class="sxs-lookup"><span data-stu-id="96b95-132">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
4.  <span data-ttu-id="96b95-133">Nella finestra di dialogo **Elabora modello di data mining** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="96b95-133">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
5.  <span data-ttu-id="96b95-134">Fare clic su **Chiudi** per chiudere la finestra di dialogo **Stato elaborazione** , quindi fare di nuovo clic su **Chiudi** nella finestra di dialogo **Elabora modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="96b95-134">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="96b95-135">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="96b95-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="96b95-136">Creazione di stime per i modelli di Call Center &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="96b95-136">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="96b95-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96b95-137">See Also</span></span>  
 [<span data-ttu-id="96b95-138">Requisiti e considerazioni sull'elaborazione &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="96b95-138">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
