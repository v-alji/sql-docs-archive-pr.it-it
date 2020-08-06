---
title: Creazione di query drill-through tramite DMX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42c896ee-e5ee-4017-b66e-31d1fe66d369
author: minewiskan
ms.author: owend
ms.openlocfilehash: 618732bfe48f7b1fe777f7841d686b07877d10ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635270"
---
# <a name="create-drillthrough-queries-using-dmx"></a><span data-ttu-id="c55a0-102">Creare query drill-through tramite DMX</span><span class="sxs-lookup"><span data-stu-id="c55a0-102">Create Drillthrough Queries using DMX</span></span>
  <span data-ttu-id="c55a0-103">Per tutti i modelli che supportano il drill-through, è possibile recuperare i dati del case e della struttura creando una query DMX in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o in qualsiasi altro client che supporta DMX.</span><span class="sxs-lookup"><span data-stu-id="c55a0-103">For all models that support drillthrough, you can retrieve case data and structure data by creating a DMX query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any other client that supports DMX.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="c55a0-104">Per visualizzare i dati, è necessario aver abilitato il drill-through e disporre delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="c55a0-104">To view the data, drillthrough must have been enabled, and you must have the necessary permissions.</span></span>  
  
## <a name="specifying-drillthrough-options"></a><span data-ttu-id="c55a0-105">Impostazione delle opzioni di drill-through</span><span class="sxs-lookup"><span data-stu-id="c55a0-105">Specifying Drillthrough Options</span></span>  
 <span data-ttu-id="c55a0-106">La sintassi generale per il recupero di case del modello e di case della struttura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="c55a0-106">The general syntax is for retrieving model cases and structure cases is as follows:</span></span>  
  
```  
SELECT <model column list>, StructureColumn('<structure column name') FROM <modelname>.CASES  
```  
  
 <span data-ttu-id="c55a0-107">Per altre informazioni sull'utilizzo di query DMX per restituire dati del case, vedere [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) e [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span><span class="sxs-lookup"><span data-stu-id="c55a0-107">For additional information about using DMX queries to return case data, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) and [SELECT FROM &#60;structure&#62;.CASES](/sql/dmx/select-from-structure-cases).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c55a0-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="c55a0-108">Examples</span></span>  
 <span data-ttu-id="c55a0-109">La query DMX seguente restituisce i dati del case relativi a una serie di prodotti specifica da un modello Time Series.</span><span class="sxs-lookup"><span data-stu-id="c55a0-109">The following DMX query returns the case data for a specific product series, from a time series model.</span></span> <span data-ttu-id="c55a0-110">La query restituisce anche la colonna `Amount` che non viene utilizzata nel modello, ma risulta disponibile nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="c55a0-110">The query also returns the column `Amount`, which was not used in the model but is available in the mining structure.</span></span>  
  
```  
SELECT [DateSeries], [Model Region], Quantity, StructureColumn('Amount') AS [M200 Pacific Amount]  
FROM Forecasting.CASES  
WHERE [Model Region] = 'M200 Pacific'  
```  
  
 <span data-ttu-id="c55a0-111">In questo esempio viene utilizzato un alias per rinominare la colonna della struttura.</span><span class="sxs-lookup"><span data-stu-id="c55a0-111">Note that in this example, an alias has been used to rename the structure column.</span></span> <span data-ttu-id="c55a0-112">Se non si assegna un alias alla colonna della struttura, la colonna viene restituita con il nome 'Expression'.</span><span class="sxs-lookup"><span data-stu-id="c55a0-112">If you do not assign an alias to the structure column, the column is returned with the name 'Expression'.</span></span> <span data-ttu-id="c55a0-113">Si tratta del comportamento predefinito per tutte le colonne senza nome.</span><span class="sxs-lookup"><span data-stu-id="c55a0-113">This is the default behavior for all unnamed columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55a0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c55a0-114">See Also</span></span>  
 <span data-ttu-id="c55a0-115">[Query drill-through &#40;&#41;di data mining](drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c55a0-115">[Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="c55a0-116">Drill-through sulle strutture di data mining</span><span class="sxs-lookup"><span data-stu-id="c55a0-116">Drillthrough on Mining Structures</span></span>](drillthrough-on-mining-structures.md)  
  
  
