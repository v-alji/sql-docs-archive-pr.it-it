---
title: Elaborazione del modello Sequence Clustering | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4a7545fd-37a3-4766-ad59-0946f1bd3524
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9975105fb6779e150e3a498bc87654d21292a1b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720460"
---
# <a name="processing-the-sequence-clustering-model"></a><span data-ttu-id="a499b-102">Elaborazione del modello Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="a499b-102">Processing the Sequence Clustering Model</span></span>
  <span data-ttu-id="a499b-103">Dopo avere creato una nuova struttura di data mining, è necessario distribuire le modifiche apportate alla soluzione di data mining e quindi elaborare la struttura.</span><span class="sxs-lookup"><span data-stu-id="a499b-103">After you create a new mining structure, you must deploy the changes that you made to the data mining solution, and then process the structure.</span></span> <span data-ttu-id="a499b-104">Al termine dell'elaborazione della nuova struttura e del modello di data mining, è possibile procedere all'esplorazione del modello.</span><span class="sxs-lookup"><span data-stu-id="a499b-104">After processing of both the new structure and the mining model is complete, you can browse the mining model.</span></span>  
  
 <span data-ttu-id="a499b-105">L'elaborazione è sempre necessaria quando si crea una nuova struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="a499b-105">Processing is always required when you create a new data mining structure.</span></span> <span data-ttu-id="a499b-106">Tuttavia, se si aggiunge un nuovo modello di data mining a una struttura esistente, è possibile elaborare solo tale modello.</span><span class="sxs-lookup"><span data-stu-id="a499b-106">However, if you add a new mining model to an existing structure, you can process just the mining model.</span></span> <span data-ttu-id="a499b-107">In questo scenario, poiché sono stati creati una nuova struttura e un nuovo modello di data mining, è necessario elaborarli entrambi.</span><span class="sxs-lookup"><span data-stu-id="a499b-107">In this scenario, because you have created a new mining structure and a new mining model, you must process both.</span></span>  
  
### <a name="to-process-the-mining-structure-and-model"></a><span data-ttu-id="a499b-108">Per elaborare la struttura e il modello di data mining</span><span class="sxs-lookup"><span data-stu-id="a499b-108">To process the mining structure and model</span></span>  
  
1.  <span data-ttu-id="a499b-109">**Mining Model** [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Scegliere **Elabora struttura di data mining e tutti i modelli**dal menu modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="a499b-109">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models**.</span></span>  
  
2.  <span data-ttu-id="a499b-110">Quando si chiede se si desidera compilare e distribuire il progetto, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a499b-110">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="a499b-111">Nella finestra di dialogo **Elabora struttura di data mining-sequenza clustering con area** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a499b-111">In the **Process Mining Structure - Sequence Clustering with Region** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="a499b-112">Verrà visualizzata la finestra di dialogo **stato** elaborazione per visualizzare le informazioni sull'elaborazione del modello.</span><span class="sxs-lookup"><span data-stu-id="a499b-112">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="a499b-113">L'elaborazione della nuova struttura e del nuovo modello potrebbe richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="a499b-113">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="a499b-114">Al termine dell'elaborazione, fare clic su **Chiudi** per uscire dalla finestra di dialogo **stato** elaborazione.</span><span class="sxs-lookup"><span data-stu-id="a499b-114">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="a499b-115">Fare di nuovo clic su **Chiudi per chiudere** la finestra di dialogo **Elabora struttura di data mining-Sequence Clustering con area** .</span><span class="sxs-lookup"><span data-stu-id="a499b-115">Click **Close** again to exit the **Process Mining Structure - Sequence Clustering with Region** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a499b-116">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="a499b-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a499b-117">Esplorazione del modello Sequence Clustering &#40;esercitazione intermedia sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a499b-117">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="a499b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a499b-118">See Also</span></span>  
 <span data-ttu-id="a499b-119">[Progettazione modelli di data mining](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="a499b-119">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 <span data-ttu-id="a499b-120">[Algoritmo Microsoft Sequence Clustering](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="a499b-120">[Microsoft Sequence Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md) </span></span>  
 [<span data-ttu-id="a499b-121">Requisiti e considerazioni sull'elaborazione &#40;data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a499b-121">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
