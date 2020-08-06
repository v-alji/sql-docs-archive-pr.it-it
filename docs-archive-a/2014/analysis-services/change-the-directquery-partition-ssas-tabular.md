---
title: Modificare la partizione DirectQuery (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9df1e66-dd23-41b4-95eb-af110d10eda4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 43d14785f72d9bfe6406e2b81d3f1b97e9b7cc2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626413"
---
# <a name="change-the-directquery-partition-ssas-tabular"></a><span data-ttu-id="ad944-102">Modificare la partizione DirectQuery (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="ad944-102">Change the DirectQuery Partition (SSAS Tabular)</span></span>
  <span data-ttu-id="ad944-103">Poiché è possibile designare come partizione DirectQuery solo una partizione di una tabella, per impostazione predefinita in Analysis Services viene utilizzata la prima partizione creata nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ad944-103">Because only one partition in a table can be designated as the DirectQuery partition, by default, Analysis Services uses the first partition that was created in the table.</span></span> <span data-ttu-id="ad944-104">Durante la creazione del progetto di modello, è possibile modificare la partizione DirectQuery tramite la finestra di dialogo Gestione partizioni di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad944-104">During model project authoring, you can change the DirectQuery partition by using the Partition Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ad944-105">Per i modelli distribuiti, tale partizione può essere modificata tramite [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad944-105">For deployed models, you can change the DirectQuery partition by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="change-the-directquery-partition-for-a-tabular-model-project"></a><span data-ttu-id="ad944-106">Modificare la partizione DirectQuery per un progetto di modello tabulare</span><span class="sxs-lookup"><span data-stu-id="ad944-106">Change the DirectQuery partition for a tabular model project</span></span>  
  
1.  <span data-ttu-id="ad944-107">In Progettazione modelli di [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]fare clic sulla tabella (scheda) in cui è contenuta la tabella partizionata.</span><span class="sxs-lookup"><span data-stu-id="ad944-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in the model designer, click on the table (tab) that contains the partitioned table.</span></span>  
  
2.  <span data-ttu-id="ad944-108">Fare clic sul menu **Tabella** , quindi scegliere **Partizioni**.</span><span class="sxs-lookup"><span data-stu-id="ad944-108">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="ad944-109">In **Gestione partizioni**nel nome della partizione attualmente designata come partizione DirectQuery è contenuto il prefisso **(DirectQuery)** .</span><span class="sxs-lookup"><span data-stu-id="ad944-109">In **Partition Manager**, the partition that is the current Direct Query partition in indicated by the prefix **(DirectQuery)** on the partition name.</span></span>  
  
     <span data-ttu-id="ad944-110">Selezionare una partizione diversa dall'elenco **Partizioni** , quindi fare clic su **Imposta come DirectQuery**.</span><span class="sxs-lookup"><span data-stu-id="ad944-110">Select a different partition from the **Partitions** list, and then click **Set as DirectQuery**.</span></span> <span data-ttu-id="ad944-111">Il pulsante **Imposta come DirectQuery** non è abilitato quando è selezionata la partizione DirectQuery corrente e non è visibile se il modello non è stato abilitato per la modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="ad944-111">The **Set as DirectQuery** button is not enabled when the current DirectQuery partition is selected, and is not visible if the model has not been enabled for Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="ad944-112">Se necessario, modificare le opzioni di elaborazione, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad944-112">If necessary, change the processing options, and then click **OK**.</span></span>  
  
### <a name="change-the-directquery-partition-for-a-deployed-tabular-model"></a><span data-ttu-id="ad944-113">Modificare la partizione DirectQuery per un modello tabulare distribuito</span><span class="sxs-lookup"><span data-stu-id="ad944-113">Change the DirectQuery partition for a deployed tabular model</span></span>  
  
1.  <span data-ttu-id="ad944-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]aprire il database modello in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="ad944-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the model database in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="ad944-115">Espandere il nodo **Tabelle** , fare clic con il pulsante destro del mouse sulla tabella partizionata e selezionare **Partizioni**.</span><span class="sxs-lookup"><span data-stu-id="ad944-115">Expand the **Tables** node, then right-click the partitioned table, and then select **Partitions**.</span></span>  
  
     <span data-ttu-id="ad944-116">Nel nome della partizione designata per l'utilizzo nella modalità DirectQuery è contenuto il prefisso (DirectQuery).</span><span class="sxs-lookup"><span data-stu-id="ad944-116">The partition that is designated for use with DirectQuery mode has the prefix (DirectQuery) on the partition name.</span></span>  
  
3.  <span data-ttu-id="ad944-117">Per cambiare la partizione, fare clic sull'icona della barra degli strumenti **DirectQuery** per aprire la finestra di dialogo **Imposta partizione DirectQuery** .</span><span class="sxs-lookup"><span data-stu-id="ad944-117">To change to a different partition, click the **Direct Query** toolbar icon to open the **Set DirectQuery Partition** dialog box.</span></span> <span data-ttu-id="ad944-118">L'icona della barra degli strumenti DirectQuery non è disponibile per i modelli che non sono stati abilitati per DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="ad944-118">The DirectQuery toolbar icon is not available on models that have not been enabled for Direct Query.</span></span>  
  
4.  <span data-ttu-id="ad944-119">Scegliere una partizione diversa dall'elenco a discesa **Nome partizione** e modificare le opzioni di elaborazione sulla partizione, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ad944-119">Choose a different partition from the **Partition Name** dropdown list, and then change processing options on the partition if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad944-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad944-120">See Also</span></span>  
 [<span data-ttu-id="ad944-121">Partizioni &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="ad944-121">Partitions &#40;SSAS Tabular&#41;</span></span>](tabular-models/partitions-ssas-tabular.md)  
  
  
