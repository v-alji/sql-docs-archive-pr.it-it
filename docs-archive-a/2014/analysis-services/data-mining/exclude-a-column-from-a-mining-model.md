---
title: Escludere una colonna da un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- excluding mining model columns
- mining models [Analysis Services], columns
- columns [data mining], excluding
ms.assetid: 404fe5fe-3ba2-4b9b-8780-0d02343d467f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30affebc143184c6287858f60b5d4f5d089c322a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626979"
---
# <a name="exclude-a-column-from-a-mining-model"></a><span data-ttu-id="fb31c-102">Escludere una colonna da un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="fb31c-102">Exclude a Column from a Mining Model</span></span>
  <span data-ttu-id="fb31c-103">Quando si crea un nuovo modello di data mining, potrebbe non essere necessario utilizzare tutte le colonne presenti nella struttura di data mining su cui il modello è basato.</span><span class="sxs-lookup"><span data-stu-id="fb31c-103">When you create a new mining model, you may not want to use all the columns that exist in the mining structure on which the model is based.</span></span> <span data-ttu-id="fb31c-104">Ad esempio, è possibile che sia stata aggiunta una colonna nome cliente per il drill-through, ma non si desidera utilizzarla per la modellazione.</span><span class="sxs-lookup"><span data-stu-id="fb31c-104">For example, you might have added a customer name column for drillthrough, but don't want to use it for modeling.</span></span> <span data-ttu-id="fb31c-105">In alternativa, è possibile decidere di creare più copie di una colonna con discretizzazioni diverse e utilizzare solo una delle copie in ogni modello e ignorare il resto.</span><span class="sxs-lookup"><span data-stu-id="fb31c-105">Or, you might decide to create multiple copies of a column with different discretizations, and use only one of the copies in each model, and ignore the rest.</span></span> <span data-ttu-id="fb31c-106">È anche possibile aggiungere in modo selettivo le colonne di input in molti modelli diversi per capire come la variabile aggiunta influisce sulla colonna di output.</span><span class="sxs-lookup"><span data-stu-id="fb31c-106">You could also selectively add input columns in several different models to see how the added variable affects the output column.</span></span>  
  
 <span data-ttu-id="fb31c-107">Non è necessario creare una nuova struttura di data mining per ogni combinazione di colonne; è semplicemente possibile contrassegnare una colonna come non utilizzata in un determinato modello.</span><span class="sxs-lookup"><span data-stu-id="fb31c-107">You do not need to create a new mining structure for each combination of columns; instead, you can simply flag a column as not being used in a particular model.</span></span>  
  
### <a name="to-exclude-a-column-from-a-mining-model"></a><span data-ttu-id="fb31c-108">Per escludere una colonna da un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="fb31c-108">To exclude a column from a mining model</span></span>  
  
1.  <span data-ttu-id="fb31c-109">Nella scheda **Modelli di data mining** di Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]selezionare la cella corrispondente alla colonna che si desidera escludere, nel modello di data mining appropriato.</span><span class="sxs-lookup"><span data-stu-id="fb31c-109">In the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the cell that corresponds to the column you want to exclude, under the appropriate mining model.</span></span>  
  
2.  <span data-ttu-id="fb31c-110">Selezionare **Ignora** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fb31c-110">Select **Ignore** from the drop-down list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb31c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb31c-111">See Also</span></span>  
 [<span data-ttu-id="fb31c-112">Attività e procedure relative al modello di data mining</span><span class="sxs-lookup"><span data-stu-id="fb31c-112">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
