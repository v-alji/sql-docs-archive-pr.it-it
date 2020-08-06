---
title: Cubo di origine slice (creazione guidata modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.slicesourcecube.f1
ms.assetid: 16485608-d3b9-49ee-8baa-948038cdd7ec
author: minewiskan
ms.author: owend
ms.openlocfilehash: 762248d4c2a268ac36b0dfa3ffeba20123017017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721803"
---
# <a name="slice-source-cube-data-mining-wizard"></a><span data-ttu-id="fff4a-102">Sezionamento cubo di origine (Creazione guidata modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="fff4a-102">Slice Source Cube (Data Mining Wizard)</span></span>
  <span data-ttu-id="fff4a-103">È possibile utilizzare la finestra di dialogo **Sezionamento cubo di origine** per limitare i dati utilizzati per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="fff4a-103">You can use the **Slice Source Cube** dialog box to restrict the data used to train the model.</span></span> <span data-ttu-id="fff4a-104">In genere un cubo contiene i dati correlati a molti attributi e dimensioni diversi, ad esempio tutti i negozi, tutte le aree e tutti i prodotti.</span><span class="sxs-lookup"><span data-stu-id="fff4a-104">Typically a cube contains data related to many different dimensions and attributes, such as all stores, all regions, and all products.</span></span> <span data-ttu-id="fff4a-105">Poiché non è pratico eseguire il training di un modello su un numero illimitato di combinazioni di attributi, utilizzare questa finestra di dialogo per scegliere un set specifico da utilizzare per il training di un modello.</span><span class="sxs-lookup"><span data-stu-id="fff4a-105">It is not practical to train a model on unlimited combinations of attributes, so you use this dialog box to choose a specific set to use in training a model.</span></span>  
  
 <span data-ttu-id="fff4a-106">Ad esempio, nel cubo AdventureWorks è possibile sezionare per una linea di prodotti, un'area o un anno specifico per ottenere una parte dei dati.</span><span class="sxs-lookup"><span data-stu-id="fff4a-106">For example, in the AdventureWorks cube, you might slice by a particular product line, region, or year, to get a portion of the data.</span></span>  
  
 <span data-ttu-id="fff4a-107">Se non si ha familiarità con le sezioni e con i cubi, è consigliabile consultare questi articoli:</span><span class="sxs-lookup"><span data-stu-id="fff4a-107">If you are unfamiliar with slices and cubes, we recommend that you review these articles:</span></span>  
  
-   [<span data-ttu-id="fff4a-108">Impostare la proprietà Slice della partizione &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fff4a-108">Set the Partition Slice Property &#40;Analysis Services&#41;</span></span>](multidimensional-models/set-the-partition-slice-property-analysis-services.md)  
  
-   [<span data-ttu-id="fff4a-109">Creare e gestire una partizione locale &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fff4a-109">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](multidimensional-models/create-and-manage-a-local-partition-analysis-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="fff4a-110">Si noti che le funzioni MDX dinamiche, ad esempio [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) o [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function) non sono supportate nella proprietà Slice per le partizioni.</span><span class="sxs-lookup"><span data-stu-id="fff4a-110">Note that dynamic MDX functions (such as [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) or [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) are not supported in the Slice property for partitions.</span></span> <span data-ttu-id="fff4a-111">È necessario definire la sezione usando tuple esplicite o riferimenti ai membri.</span><span class="sxs-lookup"><span data-stu-id="fff4a-111">You must define the slice by using explicit tuples or member references.</span></span>  
>   
>  <span data-ttu-id="fff4a-112">Ad esempio, anziché usare [: &#40;intervallo&#41; &#40;&#41;MDX](/sql/mdx/range-mdx) per definire un intervallo, è necessario enumerare ogni membro in base agli anni specifici.</span><span class="sxs-lookup"><span data-stu-id="fff4a-112">For example, rather than using  [: &#40;Range&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) to define a range, you would need to enumerate each member by the specific years.</span></span>  
>   
>  <span data-ttu-id="fff4a-113">Se occorre definire una sezione complessa, è consigliabile definire le tuple nella sezione mediante uno script XMLA Alter.</span><span class="sxs-lookup"><span data-stu-id="fff4a-113">If you need to define a complex slice, we recommend that you define the tuples in the slice by using an XMLA Alter script.</span></span> <span data-ttu-id="fff4a-114">È quindi possibile usare lo strumento da riga di comando ascmd o l'attività [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) di SSIS per eseguire lo script e creare il set di membri specificato immediatamente prima dell'elaborazione della partizione.</span><span class="sxs-lookup"><span data-stu-id="fff4a-114">Then, you can use either the ascmd command-line tool or the SSIS [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) to run the script and create the specified set of members immediately before you process the partition.</span></span>  
  
 <span data-ttu-id="fff4a-115">**Per altre informazioni:** [Creazione guidata modello di data mining &#40;Analysis Services - Data mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md) e [Creare una struttura di data mining relazionale](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="fff4a-115">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="fff4a-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fff4a-116">Options</span></span>  
 <span data-ttu-id="fff4a-117">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="fff4a-117">**Dimension**</span></span>  
 <span data-ttu-id="fff4a-118">Consente di selezionare la dimensione che si desidera sezionare.</span><span class="sxs-lookup"><span data-stu-id="fff4a-118">Select the dimension that you want to slice.</span></span>  
  
 <span data-ttu-id="fff4a-119">**Gerarchia**</span><span class="sxs-lookup"><span data-stu-id="fff4a-119">**Hierarchy**</span></span>  
 <span data-ttu-id="fff4a-120">Consente di selezionare la gerarchia che si desidera sezionare.</span><span class="sxs-lookup"><span data-stu-id="fff4a-120">Select the hierarchy that you want to slice.</span></span> <span data-ttu-id="fff4a-121">È possibile scegliere qualsiasi livello di una gerarchia, ma gli attributi utilizzati nel modello saranno valido solo al livello selezionato.</span><span class="sxs-lookup"><span data-stu-id="fff4a-121">You can choose any level of a hierarchy, but the attributes used in the model will be only at the level that you choose.</span></span>  
  
 <span data-ttu-id="fff4a-122">Se ad esempio si sceglie la gerarchia Geography e si seleziona Country come livello, non è possibile compilare un modello che utilizza City come attributi.</span><span class="sxs-lookup"><span data-stu-id="fff4a-122">For example, if you choose the Geography hierarchy, and select Country as the level, you cannot build a model that uses City as the attributes.</span></span> <span data-ttu-id="fff4a-123">Viceversa, se si sceglie City come livello della gerarchia in base a cui eseguire il sezionamento, non è possibile creare un modello di data mining basato su Country.</span><span class="sxs-lookup"><span data-stu-id="fff4a-123">Conversely, if you choose City as the level of the hierarchy on which to slice, you cannot create a mining model based on Country.</span></span>  
  
 <span data-ttu-id="fff4a-124">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="fff4a-124">**Operator**</span></span>  
 <span data-ttu-id="fff4a-125">Selezionare l'operatore da utilizzare per la compilazione di un'espressione di sezione.</span><span class="sxs-lookup"><span data-stu-id="fff4a-125">Select the operator to use in building a slice expression.</span></span>  
  
 <span data-ttu-id="fff4a-126">Se ad esempio si sceglie geography come gerarchia, è possibile selezionare operator = e quindi digitare "Europe" come filtro per ottenere solo i dati del cubo per l'Europa.</span><span class="sxs-lookup"><span data-stu-id="fff4a-126">For example, if you chose Geography as the hierarchy, you could select the operator = and then type "Europe" as the filter, to get cube data for Europe only.</span></span>  
  
 <span data-ttu-id="fff4a-127">**Espressione filtro**</span><span class="sxs-lookup"><span data-stu-id="fff4a-127">**Filter Expression**</span></span>  
 <span data-ttu-id="fff4a-128">Digitare un'espressione da utilizzare come criterio per filtrare il cubo in base alla dimensione selezionata.</span><span class="sxs-lookup"><span data-stu-id="fff4a-128">Type an expression to use as a criterion when filtering the cube on the selected dimension.</span></span>  
  
 <span data-ttu-id="fff4a-129">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="fff4a-129">**Parameters**</span></span>  
 <span data-ttu-id="fff4a-130">Questa opzione non è utilizzata per i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="fff4a-130">This option is not used for data mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff4a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fff4a-131">See Also</span></span>  
 <span data-ttu-id="fff4a-132">[Completamento della procedura guidata &#40;creazione guidata modello di data mining&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="fff4a-132">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="fff4a-133">[Guida sensibile al contesto della creazione guidata modello di data mining &#40;Analysis Services-&#41;di data mining](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="fff4a-133">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="fff4a-134">Impostazione utilizzo colonne modello di data mining &#40;creazione guidata modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="fff4a-134">Specify Mining Model Column Usage &#40;Data Mining Wizard&#41;</span></span>](specify-mining-model-column-usage-data-mining-wizard.md)  
  
  
