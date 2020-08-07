---
title: Elaborare un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], processing
ms.assetid: c2204472-c500-47a5-9afa-7ce2ca78b233
author: minewiskan
ms.author: owend
ms.openlocfilehash: c2fed5d72c677dc175f4c9681096d1859b30d829
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718948"
---
# <a name="process-a-mining-model"></a><span data-ttu-id="ab140-102">Elaborare un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="ab140-102">Process a Mining Model</span></span>
  <span data-ttu-id="ab140-103">La scheda Modelli di data mining di Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]consente di elaborare un modello di data mining specifico associato a una struttura di data mining oppure tutti i modelli associati alla struttura.</span><span class="sxs-lookup"><span data-stu-id="ab140-103">In the Mining Models tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can either process a specific mining model that is associated with a mining structure or you can process all the models that are associated with the structure.</span></span>  
  
 <span data-ttu-id="ab140-104">È possibile elaborare un modello di data mining utilizzando gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab140-104">You can process a mining model by using the following tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
 <span data-ttu-id="ab140-105">Inoltre, è possibile utilizzare un comando di elaborazione XMLA.</span><span class="sxs-lookup"><span data-stu-id="ab140-105">You can also use an XMLA Process command.</span></span> <span data-ttu-id="ab140-106">Per ulteriori informazioni, vedere [strumenti e approcci per l'elaborazione di &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ab140-106">For more information, see  [Tools and Approaches for Processing &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span></span>  
  
### <a name="process-a-single-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="ab140-107">Elaborare un singolo modello di data mining utilizzando SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="ab140-107">Process a single mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="ab140-108">Nella scheda **Modelli di data mining** di Progettazione modelli di data mining selezionare un modello di data mining in una o più colonne di modelli nella griglia.</span><span class="sxs-lookup"><span data-stu-id="ab140-108">On the **Mining Models** tab of Data Mining Designer, select a mining model from the one or more columns of models in the grid.</span></span>  
  
2.  <span data-ttu-id="ab140-109">Scegliere **Elabora modello** dal menu **Modello di data mining**.</span><span class="sxs-lookup"><span data-stu-id="ab140-109">On the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="ab140-110">Se sono state apportate modifiche alla struttura di data mining, prima di elaborare il modello verrà richiesto di ridistribuire la struttura.</span><span class="sxs-lookup"><span data-stu-id="ab140-110">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the model.</span></span> <span data-ttu-id="ab140-111">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ab140-111">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="ab140-112">Nella finestra di dialogo **Elabora modello \<model> di data mining-** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ab140-112">In the **Processing Mining Model - \<model>** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="ab140-113">Verrà visualizzata la finestra di dialogo **Stato elaborazione** contenente informazioni sull'elaborazione dei modelli.</span><span class="sxs-lookup"><span data-stu-id="ab140-113">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
4.  <span data-ttu-id="ab140-114">Al termine dell'elaborazione del modello, fare clic su **Chiudi** nella finestra di dialogo **Stato elaborazione** .</span><span class="sxs-lookup"><span data-stu-id="ab140-114">After the model has successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="ab140-115">Fare clic su **Chiudi** nella finestra di dialogo **Elabora modello di \<model> data mining-** .</span><span class="sxs-lookup"><span data-stu-id="ab140-115">Click **Close** in the **Processing Mining Model - \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="ab140-116">Tramite questa procedura sono stati elaborati solo la struttura di data mining e il modello di data mining associato.</span><span class="sxs-lookup"><span data-stu-id="ab140-116">Only the mining structure and the selected mining model have been processed.</span></span>  
  
### <a name="process-all-mining-models-that-are-associated-with-a-mining-structure"></a><span data-ttu-id="ab140-117">Elaborare tutti i modelli di data mining associati a una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="ab140-117">Process all mining models that are associated with a mining structure</span></span>  
  
1.  <span data-ttu-id="ab140-118">Nella scheda **Modelli di data mining** di Progettazione modelli di data mining scegliere **Elabora struttura di data mining e tutti i modelli** dal menu **Modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="ab140-118">On the **Mining Models** tab of Data Mining Designer, select **Process Mining Structure and All Models** from the **Mining Model** menu.</span></span>  
  
2.  <span data-ttu-id="ab140-119">Se sono state apportate modifiche alla struttura di data mining, prima di elaborare i modelli verrà richiesto di ridistribuire la struttura.</span><span class="sxs-lookup"><span data-stu-id="ab140-119">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="ab140-120">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ab140-120">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="ab140-121">Nella finestra di dialogo **Elabora struttura \<structure> di data mining-** fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ab140-121">In the **Processing Mining Structure - \<structure>** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="ab140-122">Verrà visualizzata la finestra di dialogo **Stato elaborazione** contenente informazioni sull'elaborazione dei modelli.</span><span class="sxs-lookup"><span data-stu-id="ab140-122">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
5.  <span data-ttu-id="ab140-123">Al termine dell'elaborazione dei modelli, fare clic su **Chiudi** nella finestra di dialogo **Stato elaborazione** .</span><span class="sxs-lookup"><span data-stu-id="ab140-123">After the models have successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
6.  <span data-ttu-id="ab140-124">Nella finestra di dialogo \*\*elaborazione \<model> \*\* fare clic su **Chiudi** .</span><span class="sxs-lookup"><span data-stu-id="ab140-124">Click **Close** in the **Processing \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="ab140-125">Tramite questa procedura sono stati elaborati la struttura di data mining e tutti i modelli di data mining associati.</span><span class="sxs-lookup"><span data-stu-id="ab140-125">The mining structure and all the associated mining models have been processed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab140-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab140-126">See Also</span></span>  
 [<span data-ttu-id="ab140-127">Attività e procedure relative al modello di data mining</span><span class="sxs-lookup"><span data-stu-id="ab140-127">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
