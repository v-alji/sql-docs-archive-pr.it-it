---
title: Creare un alias per una colonna del modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- mining models [Analysis Services], columns
- column names [Analysis Services]
ms.assetid: c80ebe66-a8f8-4f24-9fe8-8288de9d13bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 908c0a8d8caa810badf4b82dc3dd3f411d09f323
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625034"
---
# <a name="create-an-alias-for-a-model-column"></a><span data-ttu-id="863db-102">Creare un alias per una colonna di un modello</span><span class="sxs-lookup"><span data-stu-id="863db-102">Create an Alias for a Model Column</span></span>
  <span data-ttu-id="863db-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]è possibile creare un alias per una colonna di un modello.</span><span class="sxs-lookup"><span data-stu-id="863db-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can create an alias for a model column.</span></span> <span data-ttu-id="863db-104">Questa funzione può risultare utile quando il nome della struttura di data mining è troppo lungo o quando si desidera scegliere un nome più descrittivo del contenuto della colonna o del relativo utilizzo nel modello.</span><span class="sxs-lookup"><span data-stu-id="863db-104">This might be useful when the mining structure name is too long to easily work with, or when you want to rename the column to be more descriptive of its contents or usage in the model.</span></span> <span data-ttu-id="863db-105">Se ad esempio si crea una copia di una colonna di una struttura e quindi si discretizza la colonna in modo diverso per un determinato modello, è possibile rinominarla per riflettere più accuratamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="863db-105">For example, if you make a copy of a structure column and then discretize the column differently for a particular model, you can rename the column to reflect the content more accurately.</span></span>  
  
 <span data-ttu-id="863db-106">Per creare un alias per una colonna di un modello, usare il riquadro **Proprietà** e impostare la proprietà [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) della colonna.</span><span class="sxs-lookup"><span data-stu-id="863db-106">To create an alias for a model column, you use the **Properties** pane and set the [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) property of the column.</span></span>  
  
 <span data-ttu-id="863db-107">Nella scheda **Modelli di data mining** di Progettazione data mining l'alias viene visualizzato racchiuso tra parentesi accanto all'etichetta di utilizzo della colonna.</span><span class="sxs-lookup"><span data-stu-id="863db-107">On the **Mining Models** tab of Data Mining Designer, the alias appears enclosed in parentheses next to the column usage label.</span></span>  
  
 <span data-ttu-id="863db-108">Per informazioni su come impostare le proprietà di un modello di data mining, vedere [Colonne del modello di data mining](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="863db-108">For information about how to set the properties of a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-add-an-alias-to-a-mining-model-column"></a><span data-ttu-id="863db-109">Per aggiungere un alias a una colonna di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="863db-109">To add an alias to a mining model column</span></span>  
  
1.  <span data-ttu-id="863db-110">Nella scheda **Modelli di data mining** di Progettazione modelli di data mining fare clic con il pulsante destro del mouse sulla cella del modello di data mining per la colonna che si vuole modificare e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="863db-110">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the mining model for the mining column that you want to change, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="863db-111">Nella finestra **Proprietà** sul lato destro dello schermo fare clic sulla cella accanto alla proprietà Name ed eliminare il valore corrente.</span><span class="sxs-lookup"><span data-stu-id="863db-111">In the **Properties** window on the right side of the screen, click the cell next to the Name property and delete the current value.</span></span> <span data-ttu-id="863db-112">Digitare un nuovo nome per la colonna.</span><span class="sxs-lookup"><span data-stu-id="863db-112">Type a new name for the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="863db-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="863db-113">See Also</span></span>  
 <span data-ttu-id="863db-114">[Attività e procedure relative al modello di data mining](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="863db-114">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="863db-115">Proprietà dei modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="863db-115">Mining Model Properties</span></span>](mining-model-properties.md)  
  
  
