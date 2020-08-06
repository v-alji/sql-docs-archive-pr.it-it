---
title: Creazione di un modello Sequence Clustering correlato (Esercitazione intermedia sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1fb4f5bc-1756-45ca-9cd7-411a8c5992a9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d015ed8a9887cb6164020806bf4136f58629ad11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719139"
---
# <a name="creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="2c88d-102">Creazione di un modello Sequence Clustering correlato (Esercitazione intermedia sul data mining)</span><span class="sxs-lookup"><span data-stu-id="2c88d-102">Creating a Related Sequence Clustering Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="2c88d-103">Tramite l'esplorazione del modello Sequence Clustering sono stati individuati altri attributi, quali Region e Income, in grado di influire in modo significativo sui modelli. Per comprendere meglio le sequenze, verrà pertanto creato un modello Sequence Clustering correlato e verranno rimossi gli attributi relativi ai dati demografici dei clienti.</span><span class="sxs-lookup"><span data-stu-id="2c88d-103">Through your exploration of the sequence clustering model, you learned that other attributes such as Region or Income have a strong effect on the models; therefore, to understand the sequences better, you will create a related sequence clustering model and remove the attributes related to customer demographics.</span></span>  
  
 <span data-ttu-id="2c88d-104">In questa attività verrà creata una copia del modello Sequence Clustering regionale, quindi verranno rimosse dal modello tutte le colonne non correlate direttamente alle sequenze.</span><span class="sxs-lookup"><span data-stu-id="2c88d-104">In this task, you will create a copy of the regional sequence clustering model, and then remove from the model any columns that are not directly related to the sequences.</span></span>  
  
 <span data-ttu-id="2c88d-105">Il nuovo modello conterrà esattamente le stesse colonne del modello di data mining sul quale è basato.</span><span class="sxs-lookup"><span data-stu-id="2c88d-105">The new model will contain all the same columns as the mining model on which it is based.</span></span> <span data-ttu-id="2c88d-106">Non è tuttavia necessario rimuovere le colonne dalla struttura di data mining, ma è sufficiente specificare che il nuovo modello di data mining ignora tali colonne.</span><span class="sxs-lookup"><span data-stu-id="2c88d-106">However, you do not need to remove the columns from the mining structure, only specify that the new mining model ignore the columns.</span></span>  
  
### <a name="to-make-a-copy-of-the-sequence-clustering-model"></a><span data-ttu-id="2c88d-107">Per creare una copia del modello Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="2c88d-107">To make a copy of the sequence clustering model</span></span>  
  
1.  <span data-ttu-id="2c88d-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Progettazione modelli di data mining di fare clic sulla scheda **modelli di data mining** .</span><span class="sxs-lookup"><span data-stu-id="2c88d-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in the Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="2c88d-109">Fare clic con il pulsante destro del mouse sul modello che si desidera copiare e scegliere **nuovo modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="2c88d-109">Right-click the model you want to copy, and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="2c88d-110">Nella finestra di dialogo **nuovo modello di data mining** Digitare un nome di modello e selezionare Microsoft `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="2c88d-110">In the **New Mining Model** dialog box, type a model name, and select Microsoft `Sequence Clustering`.</span></span>  
  
     <span data-ttu-id="2c88d-111">Per questa esercitazione, digitare il nome `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="2c88d-111">For this tutorial, type the name `Sequence Clustering`.</span></span>  
  
4.  <span data-ttu-id="2c88d-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c88d-112">Click **OK**.</span></span>  
  
### <a name="to-remove-columns-from-the-mining-model"></a><span data-ttu-id="2c88d-113">Per rimuovere le colonne dal modello di data mining</span><span class="sxs-lookup"><span data-stu-id="2c88d-113">To remove columns from the mining model</span></span>  
  
1.  <span data-ttu-id="2c88d-114">Nella scheda **modello di data mining** , nella colonna relativa al nuovo modello denominato Sequence Clustering, fare clic sulla riga dell'attributo **Income Group** e selezionare **Ignora**.</span><span class="sxs-lookup"><span data-stu-id="2c88d-114">In the **Mining Model** tab, in the column for the new model named Sequence Clustering, click the row for the **Income Group** attribute, and select **Ignore**.</span></span>  
  
2.  <span data-ttu-id="2c88d-115">Ripetere questo passaggio per l' **area**dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="2c88d-115">Repeat this step for the attribute **Region**.</span></span>  
  
3.  <span data-ttu-id="2c88d-116">Fare clic sul segno più accanto al nome della tabella, **v Assoc Seq Line Items**, per espandere la tabella e visualizzare le colonne della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="2c88d-116">Click the plus sign next to the table name, **v Assoc Seq Line Items**, to expand the table and view the columns from the nested table.</span></span>  
  
     <span data-ttu-id="2c88d-117">Il nuovo modello dovrebbe ora contenere solo le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c88d-117">The new model should have only the following columns:</span></span>  
  
     <span data-ttu-id="2c88d-118">**NumberKey ordine**</span><span class="sxs-lookup"><span data-stu-id="2c88d-118">**Order NumberKey**</span></span>  
  
     <span data-ttu-id="2c88d-119">**Chiave numero di riga**</span><span class="sxs-lookup"><span data-stu-id="2c88d-119">**Line Number Key**</span></span>  
  
     <span data-ttu-id="2c88d-120">**Stima modello**</span><span class="sxs-lookup"><span data-stu-id="2c88d-120">**Model Predict**</span></span>  
  
### <a name="to-process-the-new-sequence-clustering-model"></a><span data-ttu-id="2c88d-121">Per elaborare il nuovo modello Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="2c88d-121">To process the new sequence clustering model</span></span>  
  
1.  <span data-ttu-id="2c88d-122">Nella scheda **modello di data mining** fare clic con il pulsante destro del mouse sul nuovo modello denominato `Sequence Clustering` e scegliere **Elabora modello**.</span><span class="sxs-lookup"><span data-stu-id="2c88d-122">In the **Mining Model** tab, right-click the new model named `Sequence Clustering`, and select **Process Model**.</span></span>  
  
     <span data-ttu-id="2c88d-123">Poiché il nuovo il modello di data mining semplificato è basato su una struttura che è già stata elaborata, non è necessario rielaborare la struttura.</span><span class="sxs-lookup"><span data-stu-id="2c88d-123">Because the new simplified mining model is based on a structure that has already been processed, you do not need to reprocess the structure.</span></span> <span data-ttu-id="2c88d-124">È sufficiente elaborare il nuovo modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="2c88d-124">You can process just the new mining model.</span></span>  
  
2.  <span data-ttu-id="2c88d-125">Fare clic su **Sì** per distribuire il progetto data mining aggiornato al server.</span><span class="sxs-lookup"><span data-stu-id="2c88d-125">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
3.  <span data-ttu-id="2c88d-126">Nella finestra di dialogo **Elabora modello di data mining** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2c88d-126">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="2c88d-127">Fare clic su **Chiudi** per chiudere la finestra di dialogo **Stato elaborazione** , quindi fare di nuovo clic su **Chiudi** nella finestra di dialogo **Elabora modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="2c88d-127">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2c88d-128">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="2c88d-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2c88d-129">Creazione di stime in un modello Sequence Clustering &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="2c88d-129">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2c88d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c88d-130">See Also</span></span>  
 [<span data-ttu-id="2c88d-131">Requisiti e considerazioni sull'elaborazione &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="2c88d-131">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
