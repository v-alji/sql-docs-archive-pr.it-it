---
title: Colonne del modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining model columns
- columns [data mining]
- REGRESSOR column
- columns [data mining], modeling flags
- modeling flags [data mining]
- MODEL_EXISTENCE_ONLY column
- usage property [data mining]
ms.assetid: fab47643-5bfd-424e-a0f7-69e665db6bab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f936f3f4e0b8f65326e9a6e84f75e6f4e82657f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715887"
---
# <a name="mining-model-columns"></a><span data-ttu-id="31124-102">Colonne del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="31124-102">Mining Model Columns</span></span>
  <span data-ttu-id="31124-103">Un modello di data mining applica un algoritmo specifico ai dati rappresentati da una struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="31124-103">A data mining model applies a mining model algorithm to the data that is represented by a mining structure.</span></span> <span data-ttu-id="31124-104">Analogamente alla struttura, il modello di data mining contiene colonne.</span><span class="sxs-lookup"><span data-stu-id="31124-104">Like the mining structure, the mining model contains columns.</span></span> <span data-ttu-id="31124-105">Un modello di data mining è contenuto all'interno della struttura di data mining ed eredita tutti i valori delle proprietà definite dalla struttura.</span><span class="sxs-lookup"><span data-stu-id="31124-105">A mining model is contained within the mining structure, and inherits all the values of the properties that are defined by the mining structure.</span></span> <span data-ttu-id="31124-106">Nel modello possono essere utilizzate tutte le colonne contenute nella struttura di data mining o un subset delle colonne.</span><span class="sxs-lookup"><span data-stu-id="31124-106">The model can use all the columns that the mining structure contains or a subset of the columns.</span></span>  
  
 <span data-ttu-id="31124-107">In una colonna di un modello di data mining è possibile definire due informazioni aggiuntive, cioè utilizzo e flag di modellazione.</span><span class="sxs-lookup"><span data-stu-id="31124-107">You can define two additional pieces of information on a mining model column: usage, and modeling flags.</span></span>  
  
-   <span data-ttu-id="31124-108">**Usage** è una proprietà che definisce il modo in cui il modello usa la colonna.</span><span class="sxs-lookup"><span data-stu-id="31124-108">**Usage** is a property that defines how the model uses the column.</span></span> <span data-ttu-id="31124-109">Le colonne possono essere utilizzate come colonne di input, colonne chiave o colonne stimabili.</span><span class="sxs-lookup"><span data-stu-id="31124-109">Columns can be used as input columns, key columns, or predictable columns.</span></span>  
  
-   <span data-ttu-id="31124-110">I**flag di modellazione** offrono all'algoritmo altre informazioni sui dati definiti nella tabella del case per consentire la compilazione di un modello più preciso.</span><span class="sxs-lookup"><span data-stu-id="31124-110">**Modeling flags** provide the algorithm with additional information about the data that is defined in the case table, so that the algorithm can build a more accurate model.</span></span> <span data-ttu-id="31124-111">È possibile definire flag di modellazione a livello di programmazione usando il linguaggio DMX (Data Mining Extensions) o tramite **Progettazione modelli di data mining** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31124-111">You can define modeling flags programmatically by using the Data Mining Extensions (DMX) language, or in **Data Mining Designer** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="31124-112">Nell'elenco seguente vengono descritti i flag di modellazione che è possibile definire in una colonna di un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="31124-112">The following list describes the modeling flags that you can define on a mining model column.</span></span>  
  
 `MODEL_EXISTENCE_ONLY`  
 <span data-ttu-id="31124-113">Indica che la presenza dell'attributo è più importante rispetto ai valori nella colonna attributo.</span><span class="sxs-lookup"><span data-stu-id="31124-113">Indicates that the presence of the attribute is more important than the values that are in the attribute column.</span></span> <span data-ttu-id="31124-114">Si consideri, ad esempio, una tabella del case contenente un elenco di elementi ordinati associati a un cliente specifico.</span><span class="sxs-lookup"><span data-stu-id="31124-114">For example, consider a case table that contains a list of order items that are associated with a particular customer.</span></span> <span data-ttu-id="31124-115">I dati della tabella includono tipo di prodotto, ID e costo di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="31124-115">The table data includes the product type, ID, and cost of each item.</span></span> <span data-ttu-id="31124-116">Ai fini della modellazione, il fatto che il cliente abbia acquistato un determinato articolo potrebbe essere più importante rispetto al costo dell'articolo stesso.</span><span class="sxs-lookup"><span data-stu-id="31124-116">For modeling purposes, the fact that the customer purchased a particular order item may be more important than the cost of the order item itself.</span></span> <span data-ttu-id="31124-117">In questo caso, la colonna relativa al costo dovrebbe venire contrassegnata come `MODEL_EXISTENCE_ONLY`.</span><span class="sxs-lookup"><span data-stu-id="31124-117">In this case, the cost column should be marked as `MODEL_EXISTENCE_ONLY`.</span></span>  
  
 `REGRESSOR`  
 <span data-ttu-id="31124-118">Indica che l'algoritmo può utilizzare la colonna specificata nella formula di regressione degli algoritmi di regressione.</span><span class="sxs-lookup"><span data-stu-id="31124-118">Indicates that the algorithm can use the specified column in the regression formula of regression algorithms.</span></span> <span data-ttu-id="31124-119">Questo flag è supportato dagli algoritmi [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees e [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series.</span><span class="sxs-lookup"><span data-stu-id="31124-119">This flag is supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series algorithms.</span></span>  
  
 <span data-ttu-id="31124-120">Per altre informazioni sull'impostazione della proprietà di utilizzo e sulla definizione di flag di modellazione a livello di programmazione tramite DMX, vedere [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span><span class="sxs-lookup"><span data-stu-id="31124-120">For more information about setting the usage property and defining modeling flags programmatically with DMX, see [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span></span> <span data-ttu-id="31124-121">Per altre informazioni sull'impostazione della proprietà di utilizzo e sulla definizione di flag di modellazione in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vedere [Spostamento di oggetti di data mining](moving-data-mining-objects.md).</span><span class="sxs-lookup"><span data-stu-id="31124-121">For more information about setting the usage property and defining modeling flags in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Moving Data Mining Objects](moving-data-mining-objects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31124-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31124-122">See Also</span></span>  
 <span data-ttu-id="31124-123">[Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="31124-123">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="31124-124">[Strutture di data mining &#40;Analysis Services-&#41;di data mining](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="31124-124">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="31124-125">[Modificare le proprietà di un modello di data mining](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="31124-125">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="31124-126">[Escludere una colonna da un modello di data mining](exclude-a-column-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="31124-126">[Exclude a Column from a Mining Model](exclude-a-column-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="31124-127">Colonne della struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="31124-127">Mining Structure Columns</span></span>](mining-structure-columns.md)  
  
  
