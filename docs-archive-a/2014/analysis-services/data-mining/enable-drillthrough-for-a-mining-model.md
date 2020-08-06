---
title: Abilitare il drill-through per un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- drillthrough [Analysis Services]
ms.assetid: 4fa44f60-ef9a-4b59-98c0-c0baf1195c8e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6adfc389776f91132e527130f50f61c9783d9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624423"
---
# <a name="enable-drillthrough-for-a-mining-model"></a><span data-ttu-id="fcd28-102">Abilitare il drill-through per un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="fcd28-102">Enable Drillthrough for a Mining Model</span></span>
  <span data-ttu-id="fcd28-103">Se è stato abilitato il drill-through per un modello di data mining, quando si esplora il modello è possibile recuperare informazioni dettagliate sui case utilizzati per creare il modello.</span><span class="sxs-lookup"><span data-stu-id="fcd28-103">If you have enabled drillthrough for a mining model, when you browse the model you can retrieve detailed information about the cases that were used to create the model.</span></span> <span data-ttu-id="fcd28-104">Per visualizzare queste informazioni sono necessarie le autorizzazioni adeguate e la struttura deve essere stata già elaborata.</span><span class="sxs-lookup"><span data-stu-id="fcd28-104">To view this information, you must have the necessary permissions, and the structure must have already been processed.</span></span>  
  
 <span data-ttu-id="fcd28-105">**Autorizzazioni** Affinché possa effettuare il drill-through ai dati del modello o della struttura, l'utente deve essere membro di un ruolo che disponga di autorizzazioni [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) sul modello o sulla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="fcd28-105">**Permissions** For a user to drill through to either model data or structure data, the user must be a member of a role that has [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) permissions on the mining model or mining structure.</span></span> <span data-ttu-id="fcd28-106">Le autorizzazioni di drill-through vengono impostate separatamente per la struttura e per il modello.</span><span class="sxs-lookup"><span data-stu-id="fcd28-106">Drillthrough permissions are set separately on the structure and model.</span></span>  
  
-   <span data-ttu-id="fcd28-107">Le autorizzazioni drill-through sul modello consentono di eseguire il drill-through dal modello, anche se non si dispone di autorizzazioni sulla struttura.</span><span class="sxs-lookup"><span data-stu-id="fcd28-107">Drillthrough permissions on the model enable you to drill through from the model, even if you do not have permissions on the structure.</span></span>  
  
-   <span data-ttu-id="fcd28-108">Le autorizzazioni di drill-through per la struttura consentono di includere colonne della struttura nelle query di drill-through dal modello usando la funzione [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx).</span><span class="sxs-lookup"><span data-stu-id="fcd28-108">Drillthrough permissions on the structure provide the additional ability to include structure columns in drillthrough queries from the model, by using the [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx) function.</span></span> <span data-ttu-id="fcd28-109">È anche possibile eseguire una query sui test case e di training nella struttura usando l'istruzione SELECT... DA \<structure> . Sintassi CASEs.</span><span class="sxs-lookup"><span data-stu-id="fcd28-109">You can also query the training and test cases in the structure by using the SELECT... FROM \<structure>.CASES syntax.</span></span>  
  
 <span data-ttu-id="fcd28-110">**Memorizzazione nella cache di case di training** Il drill-through avviene mediante il recupero di informazioni sui case di training nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="fcd28-110">**Caching of training cases** Drillthrough works by retrieving information about the training cases in the mining structure.</span></span> <span data-ttu-id="fcd28-111">Queste informazioni vengono memorizzate nella cache quando la struttura viene elaborata.</span><span class="sxs-lookup"><span data-stu-id="fcd28-111">This information is cached when the structure is processed.</span></span> <span data-ttu-id="fcd28-112">Pertanto, se si sceglie di cancellare tutti i dati memorizzati nella cache impostando la proprietà <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> su `ClearAfterProcessing`, il drill-through non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="fcd28-112">Therefore, if you choose to clear all cached data by changing the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to `ClearAfterProcessing`, drillthrough will not work.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcd28-113">Se i case di training non sono stati memorizzati nella cache, è necessario impostare la proprietà <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> su **KeepTrainingCases** e rielaborare quindi il modello prima che sia possibile visualizzare i dati dei case.</span><span class="sxs-lookup"><span data-stu-id="fcd28-113">If the training cases have not been cached, you must change the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to **KeepTrainingCases** and then reprocess the model before you can view the case data.</span></span>  
  
 <span data-ttu-id="fcd28-114">Per altre informazioni, vedere [Query drill-through &#40;Data mining&#41;](drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="fcd28-114">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="fcd28-115">Per abilitare il drill-through su un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="fcd28-115">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="fcd28-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], nella scheda **Modelli di data mining** di Progettazione modelli di data mining fare clic con il pulsante destro del mouse sul nome del modello di data mining in cui si vuole abilitare il drill-through e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fcd28-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the name of the mining model on which you want to enable drillthrough, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="fcd28-117">Nelle finestre **Proprietà** fare clic su **AllowDrillThrough**e selezionare **true**.</span><span class="sxs-lookup"><span data-stu-id="fcd28-117">In the **Properties** windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="fcd28-118">Nella scheda **Modelli di data mining** fare clic con il pulsante destro del mouse sul modello e scegliere **Elabora modello**.</span><span class="sxs-lookup"><span data-stu-id="fcd28-118">In the **Mining Models** tab, right-click the model, and select **Process Model**.</span></span>  
  
### <a name="to-enable-caching-for-a-mining-structure"></a><span data-ttu-id="fcd28-119">Per attivare la memorizzazione nella cache per una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="fcd28-119">To enable caching for a mining structure</span></span>  
  
1.  <span data-ttu-id="fcd28-120">Nella scheda [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Struttura di data mining **di Progettazione modelli di data mining in** , fare clic con il pulsante destro del mouse sul nome della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="fcd28-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Structure** tab of Data Mining Designer, right-click the name of the mining structure.</span></span>  
  
2.  <span data-ttu-id="fcd28-121">Aprire la finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="fcd28-121">Open the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="fcd28-122">Nella finestra **Proprietà** individuare la proprietà **CacheMode** e selezionare **KeepTrainingCases** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fcd28-122">In the **Properties** window, locate the **CacheMode** property, and select **KeepTrainingCases** from the list.</span></span>  
  
4.  <span data-ttu-id="fcd28-123">Selezionare **Elabora** dal menu **Database**.</span><span class="sxs-lookup"><span data-stu-id="fcd28-123">On the **Database** menu, select **Process**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd28-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcd28-124">See Also</span></span>  
 [<span data-ttu-id="fcd28-125">Query drill-through &#40;Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="fcd28-125">Drillthrough Queries &#40;Data Mining&#41;</span></span>](drillthrough-queries-data-mining.md)  
  
  
