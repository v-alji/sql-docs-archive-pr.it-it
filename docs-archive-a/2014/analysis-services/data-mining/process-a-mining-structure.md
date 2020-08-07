---
title: Elaborare una struttura di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], processing
ms.assetid: 4162f33e-c23f-4293-8905-271781e45fa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d25a927ae61ee5ffadf4ca21073a1c04cdb542
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718959"
---
# <a name="process-a-mining-structure"></a><span data-ttu-id="38d62-102">Elaborare una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="38d62-102">Process a Mining Structure</span></span>
  <span data-ttu-id="38d62-103">Per poter esplorare o utilizzare i modelli di data mining associati a una struttura di data mining, è necessario distribuire il progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ed elaborare la struttura e i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="38d62-103">Before you can browse or work with the mining models that are associated with a mining structure, you have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span> <span data-ttu-id="38d62-104">Inoltre, se si apporta una modifica alla struttura o ai modelli di data mining, verrà richiesto di eseguire di nuovo la distribuzione e l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="38d62-104">Also, if you make a change to the mining structure or mining models, you will be prompted to redeploy and process them.</span></span> <span data-ttu-id="38d62-105">L'elaborazione della struttura nella scheda **Struttura di data mining** di Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] comporta l'elaborazione di tutti i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="38d62-105">Processing the structure in the **Mining Structure** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] processes all the associated models.</span></span>  
  
 <span data-ttu-id="38d62-106">È possibile elaborare una struttura di data mining utilizzando gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="38d62-106">You can process a mining structure by using these tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   <span data-ttu-id="38d62-107">XMLA: comando Process</span><span class="sxs-lookup"><span data-stu-id="38d62-107">XMLA: Process command</span></span>  
  
 <span data-ttu-id="38d62-108">Per informazioni sull'elaborazione di singoli modelli, vedere [Elaborare un modello di data mining](process-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="38d62-108">For information about how to process individual models, see [Process a Mining Model](process-a-mining-model.md).</span></span>  
  
### <a name="to-process-a-mining-structure-and-all-associated-mining-models-using-sql-server-data-tools"></a><span data-ttu-id="38d62-109">Per elaborare una struttura di data mining e tutti i modelli di data mining associati utilizzando gli strumenti dati di SQL Server</span><span class="sxs-lookup"><span data-stu-id="38d62-109">To process a mining structure and all associated mining models using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="38d62-110">Scegliere la voce di menu **Modello di data mining** , quindi **Elabora struttura di data mining e tutti i modelli** in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38d62-110">Select **Process Mining Structure and All Models** from the **Mining Model** menu item in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
     <span data-ttu-id="38d62-111">Se sono state apportate modifiche alla struttura, prima di elaborare i modelli verrà richiesto di ridistribuire la struttura.</span><span class="sxs-lookup"><span data-stu-id="38d62-111">If you made changes to the structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="38d62-112">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="38d62-112">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="38d62-113">Fare clic su **Esegui** nella finestra di dialogo **Elabora struttura di \<structure> data mining-** .</span><span class="sxs-lookup"><span data-stu-id="38d62-113">Click **Run** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
     <span data-ttu-id="38d62-114">Verrà aperta la finestra di dialogo **Stato elaborazione** in cui vengono visualizzate informazioni sull'elaborazione dei modelli.</span><span class="sxs-lookup"><span data-stu-id="38d62-114">The **Process Progress** dialog box opens to display the details of model processing.</span></span>  
  
3.  <span data-ttu-id="38d62-115">Fare clic su **Chiudi** nella finestra di dialogo **Stato elaborazione** dopo che l'elaborazione dei modelli è stata completata.</span><span class="sxs-lookup"><span data-stu-id="38d62-115">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="38d62-116">Fare clic su **Chiudi** nella finestra di dialogo **Elabora struttura di \<structure> data mining-** .</span><span class="sxs-lookup"><span data-stu-id="38d62-116">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d62-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38d62-117">See Also</span></span>  
 [<span data-ttu-id="38d62-118">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="38d62-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
