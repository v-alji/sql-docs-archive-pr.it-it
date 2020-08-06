---
title: Specifica di un set di dati di testing per la struttura (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75cd508f-b126-418b-848d-3c4c3e6c303f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c1430706a0ec2cd3ddc0eaee18d7001d05fefae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623660"
---
# <a name="specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial"></a><span data-ttu-id="82606-102">Specifica di un set di dati di testing per la struttura (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="82606-102">Specifying a Testing Data Set for the Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="82606-103">Nelle schermate finali della Creazione guidata modello di data mining si suddivideranno i dati in un set di testing e un set di training.</span><span class="sxs-lookup"><span data-stu-id="82606-103">In the final few screens of the Data Mining Wizard you will split your data into a testing set and a training set.</span></span> <span data-ttu-id="82606-104">Si assegnerà quindi un nome alla struttura e si abiliterà il drill-through sul modello.</span><span class="sxs-lookup"><span data-stu-id="82606-104">You will then name your structure and enable drillthrough on the model.</span></span>  
  
## <a name="specifying-a-testing-set"></a><span data-ttu-id="82606-105">Specifica di un set di testing</span><span class="sxs-lookup"><span data-stu-id="82606-105">Specifying a Testing Set</span></span>  
 <span data-ttu-id="82606-106">La separazione dei dati in set di training e set di testing durante la creazione di una struttura di data mining consente di determinare facilmente l'accuratezza dei modelli di data mining che verranno creati successivamente.</span><span class="sxs-lookup"><span data-stu-id="82606-106">Separating data into training and testing sets when you create a mining structure makes it possible to easily assess the accuracy of the mining models that you create later.</span></span> <span data-ttu-id="82606-107">Per ulteriori informazioni sui set di testing, vedere [Training and testing data set](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="82606-107">For more information on testing sets, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-specify-the-testing-set"></a><span data-ttu-id="82606-108">Per specificare il set di testing</span><span class="sxs-lookup"><span data-stu-id="82606-108">To specify the testing set</span></span>  
  
1.  <span data-ttu-id="82606-109">Nella pagina **Crea set di testing** , per la **percentuale di dati per il testing**, lasciare il valore predefinito `30` .</span><span class="sxs-lookup"><span data-stu-id="82606-109">On the **Create Testing Set** page, for **Percentage of data for testing**, leave the default value of `30`.</span></span>  
  
2.  <span data-ttu-id="82606-110">Per il **numero massimo di case nel set di dati di testing**, digitare `1000` .</span><span class="sxs-lookup"><span data-stu-id="82606-110">For **Maximum number of cases in testing data set**, type `1000`.</span></span>  
  
3.  <span data-ttu-id="82606-111">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82606-111">Click **Next**.</span></span>  
  
## <a name="specifying-drillthrough"></a><span data-ttu-id="82606-112">Specifica del drill-through</span><span class="sxs-lookup"><span data-stu-id="82606-112">Specifying Drillthrough</span></span>  
 <span data-ttu-id="82606-113">Il drill-through può essere abilitato sui modelli e sulle strutture.</span><span class="sxs-lookup"><span data-stu-id="82606-113">Drillthrough can be enabled on models and on structures.</span></span> <span data-ttu-id="82606-114">La casella di controllo in questa finestra di dialogo abilita il drill-through nel modello denominato.</span><span class="sxs-lookup"><span data-stu-id="82606-114">The checkbox in this dialog box enables drillthrough on the named model.</span></span> <span data-ttu-id="82606-115">Dopo l'elaborazione del modello sarà possibile recuperare le informazioni dettagliate dai dati di training utilizzati per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="82606-115">After the model has been processed,  you will be able to retrieve detailed information from the training data that were used to create the model.</span></span>  
  
 <span data-ttu-id="82606-116">Se anche la struttura di data mining sottostante è stata configurata per consentire il drill-through, è possibile recuperare informazioni dettagliate dai case del modello e dalla struttura di data mining, comprese le colonne non incluse nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="82606-116">If the underlying mining structure has also been configured to allow drillthrough, you can retrieve detailed information from both the model cases and the mining structure, including columns that were not included in the mining model.</span></span> <span data-ttu-id="82606-117">Per altre informazioni, vedere [Query drill-through &#40;Data mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="82606-117">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-name-the-model-and-structure-and-specify-drillthrough"></a><span data-ttu-id="82606-118">Per assegnare un nome al modello e alla struttura e specificare il drill-through</span><span class="sxs-lookup"><span data-stu-id="82606-118">To name the model and structure and specify drillthrough</span></span>  
  
1.  <span data-ttu-id="82606-119">Nella pagina **Completamento procedura guidata** Digitare in **Nome struttura di data mining** `Targeted Mailing` .</span><span class="sxs-lookup"><span data-stu-id="82606-119">On the **Completing the Wizard** page, in **Mining structure name**, type `Targeted Mailing`.</span></span>  
  
2.  <span data-ttu-id="82606-120">In **nome modello di data mining**Digitare `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="82606-120">In **Mining model name**, type `TM_Decision_Tree`.</span></span>  
  
3.  <span data-ttu-id="82606-121">Selezionare la casella di controllo **Consenti drill-through** .</span><span class="sxs-lookup"><span data-stu-id="82606-121">Select the **Allow drill through** check box.</span></span>  
  
4.  <span data-ttu-id="82606-122">Esaminare il riquadro di **Anteprima** .</span><span class="sxs-lookup"><span data-stu-id="82606-122">Review the **Preview** pane.</span></span> <span data-ttu-id="82606-123">Si noti che vengono visualizzate solo le colonne selezionate come **chiave**, **input** o **stimabile** .</span><span class="sxs-lookup"><span data-stu-id="82606-123">Notice that only those columns selected as **Key**, **Input** or **Predictable** are shown.</span></span> <span data-ttu-id="82606-124">Le altre colonne selezionate (ad esempio, AddressLine1) non vengono utilizzate per la compilazione del modello, ma saranno disponibili nella struttura sottostante e possono essere sottoposte a query una volta che il modello viene elaborato e distribuito.</span><span class="sxs-lookup"><span data-stu-id="82606-124">The other columns you selected (e.g., AddressLine1) are not used for building the model but will be available in the underlying structure, and can be queried after the model is processed and deployed.</span></span>  
  
5.  <span data-ttu-id="82606-125">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="82606-125">Click **Finish**.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="82606-126">Attività precedente della lezione</span><span class="sxs-lookup"><span data-stu-id="82606-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="82606-127">Impostazione del tipo di dati e del tipo di contenuto &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="82606-127">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="82606-128">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="82606-128">Next Lesson</span></span>  
 [<span data-ttu-id="82606-129">Lezione 3: Aggiunta ed elaborazione di modelli</span><span class="sxs-lookup"><span data-stu-id="82606-129">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="82606-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82606-130">See Also</span></span>  
 <span data-ttu-id="82606-131">[Abilitare il drill-through per un modello di data mining](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="82606-131">[Enable Drillthrough for a Mining Model](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span></span>  
 <span data-ttu-id="82606-132">[Query drill-through &#40;&#41;di data mining](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="82606-132">[Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="82606-133">Specificare i dati di training &#40;creazione guidata modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="82606-133">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](../../2014/analysis-services/specify-the-training-data-data-mining-wizard.md)  
  
  
