---
title: Elaborazione di modelli nella struttura di mailing diretto (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d8233bb-117e-4563-9302-8a5a8ad1fae2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b8fb7b9f601f351520c3f611cc3c520614ed8ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714924"
---
# <a name="processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="12202-102">Elaborazione di modelli nella struttura di mailing diretto (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="12202-102">Processing Models in the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="12202-103">Per poter esplorare o utilizzare i modelli di data mining creati, è necessario distribuire il progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ed elaborare la struttura e i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="12202-103">Before you can browse or work with the mining models that you have created, you must deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span>  
  
-   <span data-ttu-id="12202-104">La *distribuzione* invia il progetto a un server e crea qualsiasi oggetto in tale progetto nel server.</span><span class="sxs-lookup"><span data-stu-id="12202-104">*Deploying* sends the project to a server and creates any objects in that project on the server.</span></span>  
  
-   <span data-ttu-id="12202-105">L' *elaborazione* popola [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] gli oggetti con dati provenienti da origini dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="12202-105">*Processing* populates [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects with data from relational data sources.</span></span>  
  
 <span data-ttu-id="12202-106">Per utilizzare i modelli, è innanzitutto necessario distribuirli ed elaborarli.</span><span class="sxs-lookup"><span data-stu-id="12202-106">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="12202-107">Inoltre, quando si apportano modifiche al modello, ad esempio se si aggiungono nuovi dati, è necessario ridistribuire e rielaborare i modelli.</span><span class="sxs-lookup"><span data-stu-id="12202-107">Also, when you make any changes to the model, such as adding new data, you must redeploy and reprocess the models.</span></span>  
  
## <a name="ensuring-consistency-with-holdoutseed"></a><span data-ttu-id="12202-108">Verifica della coerenza con HoldoutSeed</span><span class="sxs-lookup"><span data-stu-id="12202-108">Ensuring Consistency with HoldoutSeed</span></span>  
 <span data-ttu-id="12202-109">Quando si distribuisce un progetto e si elaborano la struttura e i modelli, singole righe nella struttura dei dati vengono assegnate ai set di training o di testing sulla base di un valore di inizializzazione numerico.</span><span class="sxs-lookup"><span data-stu-id="12202-109">When you deploy a project and process the structure and models, individual rows in your data structure are assigned to either the training set or testing set based on a numerical seed value.</span></span> <span data-ttu-id="12202-110">Per impostazione predefinita, il valore di inizializzazione numerico viene calcolato in base agli attributi della struttura dei dati.</span><span class="sxs-lookup"><span data-stu-id="12202-110">By default, the numerical seed value is computed based on attributes of the data structure.</span></span> <span data-ttu-id="12202-111">Tuttavia, se si modificano alcuni aspetti del modello, il valore di inizializzazione può cambiare determinando risultati lievemente diversi.</span><span class="sxs-lookup"><span data-stu-id="12202-111">However, if you ever change some aspects of your model, the seed value would change, leading to subtly different results.</span></span> <span data-ttu-id="12202-112">Pertanto, per garantire che i risultati corrispondano a quelli descritti in questo articolo, verrà assegnato arbitrariamente un valore di *inizializzazione* di un dato di lavoro fisso `12` .</span><span class="sxs-lookup"><span data-stu-id="12202-112">Therefore, in order to ensure that your results are the same as described here, we will arbitrarily assign a fixed *holdout seed* of `12`.</span></span> <span data-ttu-id="12202-113">Il valore di inizializzazione dei dati di controllo viene utilizzato per inizializzare l'algoritmo di campionamento e garantisce che i dati vengano partizionati approssimativamente nello stesso modo per tutte le strutture di data mining e i relativi modelli.</span><span class="sxs-lookup"><span data-stu-id="12202-113">The holdout seed is used to initialize the sampling algorithm, and ensures that the data is partitioned in roughly the same way for all mining structures and their models.</span></span>  
  
 <span data-ttu-id="12202-114">Questo valore non influisce sul numero di case nel set di training, ma garantisce semplicemente che venga utilizzato lo stesso metodo di partizionamento ogni volta che si compila il modello.</span><span class="sxs-lookup"><span data-stu-id="12202-114">This value does not affect the number of cases in the training set; it simply ensures that the same partitioning method will be used each time you build the model.</span></span>  
  
 <span data-ttu-id="12202-115">Per ulteriori informazioni sul valore di inizializzazione di [controllo, vedere set di dati di training e di testing](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="12202-115">For more information on holdout seed, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-set-the-holdout-seed"></a><span data-ttu-id="12202-116">Per impostare il valori di inizializzazione di controllo</span><span class="sxs-lookup"><span data-stu-id="12202-116">To set the Holdout Seed</span></span>  
  
1.  <span data-ttu-id="12202-117">Fare clic sulla scheda **struttura** di data mining o modelli di data mining in progettazione **modelli** di data mining in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12202-117">Click on the **Mining Structure** tab or the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="12202-118">**Targeted Mailing MiningStructure** viene visualizzato nel riquadro **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="12202-118">**Targeted Mailing MiningStructure** displays in the **Properties** pane.</span></span>  
  
2.  <span data-ttu-id="12202-119">Verificare che il riquadro **Proprietà** sia aperto premendo **F4**.</span><span class="sxs-lookup"><span data-stu-id="12202-119">Ensure that the **Properties** pane is open by pressing **F4**.</span></span>  
  
3.  <span data-ttu-id="12202-120">Verificare che **CacheMode** sia impostato su **KeepTrainingCases**.</span><span class="sxs-lookup"><span data-stu-id="12202-120">Ensure that **CacheMode** is set to **KeepTrainingCases**.</span></span>  
  
4.  <span data-ttu-id="12202-121">Immettere `12` per **HoldoutSeed**.</span><span class="sxs-lookup"><span data-stu-id="12202-121">Enter `12` for **HoldoutSeed**.</span></span>  
  
## <a name="deploying-and-processing-the-models"></a><span data-ttu-id="12202-122">Distribuzione ed elaborazione dei modelli</span><span class="sxs-lookup"><span data-stu-id="12202-122">Deploying and Processing the Models</span></span>  
 <span data-ttu-id="12202-123">In Progettazione modelli di data mining è possibile decidere quali oggetti elaborare, a seconda dell'ambito delle modifiche apportate al modello o ai dati sottostanti:</span><span class="sxs-lookup"><span data-stu-id="12202-123">In Data Mining Designer, you can decide which objects to process, depending on the scope of changes you've made to your model or the underlying data:</span></span>  
  
 <span data-ttu-id="12202-124">Per questa attività, poiché i dati e i modelli sono nuovi, sarà necessario elaborare contemporaneamente la struttura e tutti i modelli.</span><span class="sxs-lookup"><span data-stu-id="12202-124">For this task, because the data and the models are new, you will process the structure and all the models at the same time.</span></span>  
  
#### <a name="to-deploy-the-project-and-process-all-the-mining-models"></a><span data-ttu-id="12202-125">Per distribuire il progetto ed elaborare tutti i modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="12202-125">To deploy the project and process all the mining models</span></span>  
  
1.  <span data-ttu-id="12202-126">Scegliere **Elabora struttura di data mining e tutti i modelli**dal menu **modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="12202-126">In the **Mining Model** menu, select **Process Mining Structure and All Models**.</span></span>  
  
     <span data-ttu-id="12202-127">Se sono state apportate modifiche alla struttura, prima di elaborare i modelli verrà richiesto di compilare e distribuire il progetto.</span><span class="sxs-lookup"><span data-stu-id="12202-127">If you made changes to the structure, you will be prompted to build and deploy the project before processing the models.</span></span> <span data-ttu-id="12202-128">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="12202-128">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="12202-129">Fare clic su **Esegui** nella finestra di dialogo **Elabora struttura di data mining-Targeted Mailing** .</span><span class="sxs-lookup"><span data-stu-id="12202-129">Click **Run** in the **Processing Mining Structure - Targeted Mailing** dialog box.</span></span>  
  
     <span data-ttu-id="12202-130">Verrà aperta la finestra di dialogo **Stato elaborazione** in cui vengono visualizzate informazioni sull'elaborazione dei modelli.</span><span class="sxs-lookup"><span data-stu-id="12202-130">The **Process Progress** dialog box opens to display the details of model processing.</span></span> <span data-ttu-id="12202-131">L'elaborazione dei modelli potrebbe richiedere tempi lunghi, a seconda del computer in uso.</span><span class="sxs-lookup"><span data-stu-id="12202-131">Model processing might take some time, depending on your computer.</span></span>  
  
3.  <span data-ttu-id="12202-132">Fare clic su **Chiudi** nella finestra di dialogo **Stato elaborazione** dopo che l'elaborazione dei modelli è stata completata.</span><span class="sxs-lookup"><span data-stu-id="12202-132">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="12202-133">Fare clic su **Chiudi** nella finestra di dialogo **Elabora struttura di \<structure> data mining-** .</span><span class="sxs-lookup"><span data-stu-id="12202-133">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="12202-134">Attività precedente della lezione</span><span class="sxs-lookup"><span data-stu-id="12202-134">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="12202-135">Aggiunta di nuovi modelli alla struttura Targeted Mailing &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="12202-135">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="12202-136">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="12202-136">Next Lesson</span></span>  
 [<span data-ttu-id="12202-137">Lezione 4: esplorazione dei modelli di mailing diretto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="12202-137">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="12202-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12202-138">See Also</span></span>  
 [<span data-ttu-id="12202-139">Requisiti e considerazioni sull'elaborazione &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="12202-139">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
