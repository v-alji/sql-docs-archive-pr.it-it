---
title: Finestra di dialogo origine partizione (dati multidimensionali Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionsourcedialog.f1
ms.assetid: c414dabe-9bad-49b7-9a3c-dfca87fef92b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6732e8f00dc0d01e0d3b708794a1d9c497ae4cf5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711067"
---
# <a name="partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="3ede5-102">Finestra di dialogo Origine partizione (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="3ede5-102">Partition Source Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3ede5-103">Usare la finestra di dialogo \*\*Origine partizione[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in \*\* per specificare l'origine dei dati di una tabella dei fatti per una partizione.</span><span class="sxs-lookup"><span data-stu-id="3ede5-103">Use the **Partition Source** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to specify the source of fact table data for a partition.</span></span> <span data-ttu-id="3ede5-104">Per visualizzare la finestra di dialogo **Origine partizione** , è possibile:</span><span class="sxs-lookup"><span data-stu-id="3ede5-104">You can display the **Partition Source** dialog box by:</span></span>  
  
-   <span data-ttu-id="3ede5-105">Fare clic sul pulsante **...** in una cella della griglia **Partizioni** di un gruppo di misure selezionato nel riquadro **Gruppi di misure** della scheda **Partizioni** in Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="3ede5-105">Clicking the **...** button on a cell from the **Partitions** grid of a selected measure group in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="3ede5-106">Fare clic sul pulsante **...** nel valore della proprietà **Origine** di un oggetto **Partizione** nella finestra **Proprietà** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ede5-106">Clicking the **...** button on the **Source** property value of a **Partition** object in the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="3ede5-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3ede5-107">Options</span></span>  
  
|<span data-ttu-id="3ede5-108">Opzione</span><span class="sxs-lookup"><span data-stu-id="3ede5-108">Option</span></span>|<span data-ttu-id="3ede5-109">Definizione</span><span class="sxs-lookup"><span data-stu-id="3ede5-109">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="3ede5-110">**Tipo di binding**</span><span class="sxs-lookup"><span data-stu-id="3ede5-110">**Binding type**</span></span>|<span data-ttu-id="3ede5-111">Consente di selezionare il tipo di associazione da utilizzare per l'origine della partizione specificata.</span><span class="sxs-lookup"><span data-stu-id="3ede5-111">Select the binding type to use for the source of the specified partition.</span></span> <span data-ttu-id="3ede5-112">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ede5-112">The following options are available:</span></span><br /><br /> <span data-ttu-id="3ede5-113">**Associazione tabella**: selezionare questa indicazione per visualizzare il riquadro dei **Dettagli dell'associazione di tabella** e indicare che la partizione è associata al contenuto di una tabella in un'origine dati o in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="3ede5-113">**Table binding**: Select to display the **Table Binding Detail** pane and indicate that the partition is bound to the contents of a table in a data source or data source view.</span></span> <span data-ttu-id="3ede5-114">Per altre informazioni sul riquadro **Dettagli dell'associazione di tabella**, vedere [Dettagli dell'associazione di tabella &#40;Finestra di dialogo origine partizione&#41; &#40;Analysis Services - Dati multidimensionali&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="3ede5-114">For more information about the **Table Binding Detail** pane, see [Table Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="3ede5-115">**Dettagli**: selezionare questa indicazione per visualizzare il riquadro dei **Dettagli dell'associazione di query** e indicare che la partizione è associata al contenuto di una query eseguita su un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3ede5-115">**Detail**: Select to display the **Query Binding Detail** pane and indicate that the partition is bound to the contents of a query executed on a data source.</span></span> <span data-ttu-id="3ede5-116">Per altre informazioni sul riquadro **Dettagli dell'associazione di query**, vedere [Dettagli dell'associazione di query &#40;Finestra di dialogo origine partizione&#41; &#40;Analysis Services - Dati multidimensionali&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="3ede5-116">For more information about the **Query Binding Detail** pane, see [Query Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="3ede5-117">**Dettaglio**</span><span class="sxs-lookup"><span data-stu-id="3ede5-117">**Detail**</span></span>|<span data-ttu-id="3ede5-118">Consente di visualizzare la finestra di dialogo **Dettagli dell'associazione di tabella** o **Dettagli dell'associazione di query** , a seconda del valore dell'opzione **Tipo di associazione** .</span><span class="sxs-lookup"><span data-stu-id="3ede5-118">Displays either the **Table Binding Detail** dialog box or the **Query Binding Detail** dialog box, depending on the value of the **Binding type** option.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ede5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ede5-119">See Also</span></span>  
 <span data-ttu-id="3ede5-120">[Partizioni &#40;Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3ede5-120">[Partitions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3ede5-121">Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="3ede5-121">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
