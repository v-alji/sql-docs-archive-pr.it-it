---
title: Visualizzare o modificare i parametri dell'algoritmo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- algorithms [data mining]
- mining models [Analysis Services], algorithms
ms.assetid: 151b899b-c27a-4a09-bcf5-5c9f0ec24168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30719cd50e0c473cf2aab5d9689d27dff4f26343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627525"
---
# <a name="view-or-change-algorithm-parameters"></a><span data-ttu-id="65e71-102">Visualizzare o modificare i parametri dell'algoritmo</span><span class="sxs-lookup"><span data-stu-id="65e71-102">View or Change Algorithm Parameters</span></span>
  <span data-ttu-id="65e71-103">È possibile modificare i parametri forniti con gli algoritmi utilizzati per compilare modelli di data mining per personalizzare i risultati del modello.</span><span class="sxs-lookup"><span data-stu-id="65e71-103">You can change the parameters provided with the algorithms that you use to build data mining models to customize the results of the model.</span></span>  
  
 <span data-ttu-id="65e71-104">I parametri dell'algoritmo forniti in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cambiano molto più delle sole proprietà del modello: possono essere usati per modificare in modo sostanziale la modalità di elaborazione, raggruppamento e visualizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="65e71-104">The algorithm parameters provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] change much more than just properties on the model: they can be used to fundamentally alter the way that data is processed, grouped, and displayed.</span></span> <span data-ttu-id="65e71-105">Ad esempio, è possibile utilizzare i parametri dell'algoritmo per effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="65e71-105">For example, you can use algorithm parameters to do the following:</span></span>  
  
-   <span data-ttu-id="65e71-106">Modificare il metodo di analisi, ad esempio il metodo di clustering.</span><span class="sxs-lookup"><span data-stu-id="65e71-106">Change the method of analysis, such as the clustering method.</span></span>  
  
-   <span data-ttu-id="65e71-107">Controllare il comportamento di selezione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="65e71-107">Control feature selection behavior.</span></span>  
  
-   <span data-ttu-id="65e71-108">Specificare le dimensioni dei set di elementi o la probabilità delle regole.</span><span class="sxs-lookup"><span data-stu-id="65e71-108">Specify the size of itemsets or the probability of rules.</span></span>  
  
-   <span data-ttu-id="65e71-109">Controllare la diramazione e la profondità degli alberi delle decisioni.</span><span class="sxs-lookup"><span data-stu-id="65e71-109">Control branching and depth of decision trees.</span></span>  
  
-   <span data-ttu-id="65e71-110">Specificare un valore di inizializzazione o le dimensioni del set di dati di controllo interni utilizzato per la creazione del modello.</span><span class="sxs-lookup"><span data-stu-id="65e71-110">Specify a seed value or the size of the internal holdout set used for model creation.</span></span>  
  
 <span data-ttu-id="65e71-111">I parametri forniti per ogni algoritmo variano notevolmente; per un elenco dei parametri che è possibile impostare per ogni algoritmo, vedere gli argomenti di riferimento tecnici in questa sezione: [Algoritmi di data mining &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="65e71-111">The parameters provided for each algorithm vary greatly; for a list of the parameters that you can set for each algorithm, see the technical reference topics in this section: [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="change-an-algorithm-parameter"></a><span data-ttu-id="65e71-112">Modificare un parametro di un algoritmo</span><span class="sxs-lookup"><span data-stu-id="65e71-112">Change an algorithm parameter</span></span>  
  
1.  <span data-ttu-id="65e71-113">Nella scheda **Modelli di data mining** di Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare clic con il pulsante destro del mouse sul modello di data mining per il quale si vuole ottimizzare l'algoritmo e quindi scegliere **Imposta parametri algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="65e71-113">On the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the algorithm type of the mining model for which you want to tune the algorithm, and select **Set Algorithm Parameters**.</span></span>  
  
     <span data-ttu-id="65e71-114">Verrà visualizzata la finestra di dialogo **Parametri algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="65e71-114">The **Algorithm Parameters** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="65e71-115">Nella colonna **Valore** impostare un nuovo valore per l'algoritmo che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="65e71-115">In the **Value** column, set a new value for the algorithm that you want to change.</span></span>  
  
     <span data-ttu-id="65e71-116">Se non si immette un valore nella colonna **Valore** , in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] viene usato il valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="65e71-116">If you do not enter a value in the **Value** column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses the default parameter value.</span></span> <span data-ttu-id="65e71-117">La colonna **Intervallo** descrive i valori che è possibile immettere.</span><span class="sxs-lookup"><span data-stu-id="65e71-117">The **Range** column describes the possible values that you can enter.</span></span>  
  
3.  <span data-ttu-id="65e71-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="65e71-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="65e71-119">Il parametro dell'algoritmo viene impostato con il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="65e71-119">The algorithm parameter is set with the new value.</span></span> <span data-ttu-id="65e71-120">Le modifiche al parametro non verranno applicate al modello di data mining fino a quando non si rielabora il modello.</span><span class="sxs-lookup"><span data-stu-id="65e71-120">The parameter change will not be reflected in the mining model until you reprocess the model.</span></span>  
  
### <a name="view-the-parameters-used-in-an-existing-model"></a><span data-ttu-id="65e71-121">Visualizzare i parametri utilizzati in un modello esistente</span><span class="sxs-lookup"><span data-stu-id="65e71-121">View the parameters used in an existing model</span></span>  
  
1.  <span data-ttu-id="65e71-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aprire una finestra di query DMX.</span><span class="sxs-lookup"><span data-stu-id="65e71-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window.</span></span>  
  
2.  <span data-ttu-id="65e71-123">Digitare una query come la seguente:</span><span class="sxs-lookup"><span data-stu-id="65e71-123">Type a query like this one:</span></span>  
  
    ```  
    select MINING_PARAMETERS   
    from $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = '<model name>'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="65e71-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65e71-124">See Also</span></span>  
 [<span data-ttu-id="65e71-125">Attività e procedure relative al modello di data mining</span><span class="sxs-lookup"><span data-stu-id="65e71-125">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
