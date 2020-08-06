---
title: Finestra di dialogo parametri algoritmo (visualizzazione modelli di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.models.algorithmparameters.f1
helpviewer_keywords:
- Algorithm Parameters dialog box
ms.assetid: 57f9f6f8-8ca4-4a6e-8f18-85f0571b7060
author: minewiskan
ms.author: owend
ms.openlocfilehash: 303d8b5bd3437690c65873e106a94cf2ce8eb9f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625927"
---
# <a name="algorithm-parameters-dialog-box-mining-models-view"></a><span data-ttu-id="d0d2a-102">Finestra di dialogo Parametri algoritmo (visualizzazione Modelli di data mining)</span><span class="sxs-lookup"><span data-stu-id="d0d2a-102">Algorithm Parameters Dialog Box (Mining Models View)</span></span>
  <span data-ttu-id="d0d2a-103">Usare la finestra di dialogo **Parametri algoritmo** per modificare i parametri dell'algoritmo specifici per il modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-103">Use the **Algorithm Parameters** dialog box to adjust algorithm parameters that are specific to the selected model.</span></span> <span data-ttu-id="d0d2a-104">Quando si modifica un parametro dell'algoritmo, i risultati del modello di data mining di solito cambiano.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-104">When you change an algorithm parameter, you will usually change the results of the mining model.</span></span> <span data-ttu-id="d0d2a-105">L'influenza che ogni parametro ha sui risultati dipende dall'algoritmo utilizzato e dai dati.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-105">The way that each parameter affects the results depends on the algorithm you are using, and on your data.</span></span> <span data-ttu-id="d0d2a-106">Per altre informazioni, vedere [Personalizzare struttura e modelli di data mining](data-mining/customize-mining-models-and-structure.md).</span><span class="sxs-lookup"><span data-stu-id="d0d2a-106">For more information, see [Customize Mining Models and Structure](data-mining/customize-mining-models-and-structure.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d0d2a-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d0d2a-107">Options</span></span>  
 <span data-ttu-id="d0d2a-108">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="d0d2a-108">**Parameters**</span></span>  
 <span data-ttu-id="d0d2a-109">Consente di visualizzare l'elenco dei parametri disponibili per il modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-109">Lists the parameters that are available for the selected mining model.</span></span>  
  
 <span data-ttu-id="d0d2a-110">Di seguito vengono descritte le colonne disponibili.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-110">The following list describes the available columns.</span></span>  
  
|<span data-ttu-id="d0d2a-111">Colonna</span><span class="sxs-lookup"><span data-stu-id="d0d2a-111">Column</span></span>|<span data-ttu-id="d0d2a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0d2a-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d0d2a-113">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="d0d2a-113">**Parameter**</span></span>|<span data-ttu-id="d0d2a-114">Indica il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-114">List the name of the parameter.</span></span>|  
|<span data-ttu-id="d0d2a-115">**Valore**</span><span class="sxs-lookup"><span data-stu-id="d0d2a-115">**Value**</span></span>|<span data-ttu-id="d0d2a-116">Immettere un valore solo se si desidera modificare quello predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-116">Enter a value only if you want to change the default value of the parameter.</span></span>|  
|<span data-ttu-id="d0d2a-117">**Default**</span><span class="sxs-lookup"><span data-stu-id="d0d2a-117">**Default**</span></span>|<span data-ttu-id="d0d2a-118">Indica il valore predefinito del parametro usato dall'algoritmo se non si specifica un valore nella colonna **Valore** .</span><span class="sxs-lookup"><span data-stu-id="d0d2a-118">List the default value of the parameter that the algorithm will use if you do not supply a value in the **Value** column.</span></span>|  
|<span data-ttu-id="d0d2a-119">**Range**</span><span class="sxs-lookup"><span data-stu-id="d0d2a-119">**Range**</span></span>|<span data-ttu-id="d0d2a-120">Indica l'intervallo di valori che è possibile immettere nella colonna **Valore** .</span><span class="sxs-lookup"><span data-stu-id="d0d2a-120">List the range of possible values that you can enter into the **Value** column.</span></span> <span data-ttu-id="d0d2a-121">Gli intervalli possono essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0d2a-121">The ranges can be one of the following:</span></span><br /><br /> <span data-ttu-id="d0d2a-122">Elenco discreto, ad esempio 1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="d0d2a-122">A discrete list, such as 1, 2, 3</span></span><br /><br /> <span data-ttu-id="d0d2a-123">Un intervallo inclusivo, ad esempio [0, 100]</span><span class="sxs-lookup"><span data-stu-id="d0d2a-123">An inclusive range, such as [0, 100]</span></span><br /><br /> <span data-ttu-id="d0d2a-124">Intervallo esclusivo, ad esempio (0,...)</span><span class="sxs-lookup"><span data-stu-id="d0d2a-124">An exclusive range, such as (0,...)</span></span><br /><br /> <span data-ttu-id="d0d2a-125">Combinazione, ad esempio [0,...)</span><span class="sxs-lookup"><span data-stu-id="d0d2a-125">A combination, such as [0,...)</span></span>|  
  
 <span data-ttu-id="d0d2a-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d0d2a-126">**Description**</span></span>  
 <span data-ttu-id="d0d2a-127">Descrive il parametro selezionato nell'elenco **Parametri** .</span><span class="sxs-lookup"><span data-stu-id="d0d2a-127">Describes the selected parameter in the **Parameters** list.</span></span>  
  
 <span data-ttu-id="d0d2a-128">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="d0d2a-128">**Add**</span></span>  
 <span data-ttu-id="d0d2a-129">Consente di aggiungere all'elenco ulteriori parametri specifici per l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-129">Click to add additional, algorithm specific-parameters to the list.</span></span> <span data-ttu-id="d0d2a-130">Dopo l'aggiunta del parametro, è possibile immetterne il nome corretto nella colonna **Parametro** e specificare un valore nella colonna **Valore** .</span><span class="sxs-lookup"><span data-stu-id="d0d2a-130">After adding the parameter, you can enter the correct name in the **Parameter** column and provide a value in the **Value** column.</span></span>  
  
 <span data-ttu-id="d0d2a-131">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="d0d2a-131">**Remove**</span></span>  
 <span data-ttu-id="d0d2a-132">Consente di eliminare un parametro personalizzato dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-132">Click to delete a custom parameter from the list.</span></span>  
  
 <span data-ttu-id="d0d2a-133">Se si elimina dall'elenco uno dei parametri dell'algoritmo standard di Analysis Services, il parametro verrà ancora utilizzato nel modello, ma con i valori predefiniti per quel parametro.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-133">If you delete one of the standard Analysis Services algorithm parameters from the list, the parameter will still be used in the model, but with the default values for that parameter.</span></span> <span data-ttu-id="d0d2a-134">Il parametro non è eliminato in modo permanente e verrà visualizzato la volta successiva che si apre la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d0d2a-134">The parameter is not permanently deleted and will appear the next time that you open the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d2a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0d2a-135">See Also</span></span>  
 <span data-ttu-id="d0d2a-136">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d0d2a-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="d0d2a-137">[Visualizzazione modelli di data mining &#40;Progettazione modelli di data mining&#41;](mining-models-view-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="d0d2a-137">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="d0d2a-138">Spostamento di oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="d0d2a-138">Moving Data Mining Objects</span></span>](data-mining/moving-data-mining-objects.md)  
  
  
