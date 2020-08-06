---
title: Aggiungere o eliminare una gerarchia definita dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], adding
- removing hierarchies
- adding hierarchies
- deleting hierarchies
- hierarchies [Analysis Services], removing
ms.assetid: 953818b4-9543-4c01-bb20-1d45ec6dfb91
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20404a1d93d57221eb830366392eb90600f26c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630098"
---
# <a name="add-or-delete-a-user-defined-hierarchy"></a><span data-ttu-id="f9286-102">Aggiungere o eliminare una gerarchia definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="f9286-102">Add or Delete a User-Defined Hierarchy</span></span>
  <span data-ttu-id="f9286-103">È possibile aggiungere o rimuovere una gerarchia definita dall'utente in una dimensione nella scheda **Struttura dimensione** di Progettazione dimensioni in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9286-103">You add a user-defined hierarchy to or remove a user-defined hierarchy from a dimension on the **Dimension Structure** tab in Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f9286-104">Quando si aggiunge una gerarchia definita dall'utente, questa non risulta disponibile per gli utenti finché non ne viene creata un'istanza in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e non viene elaborata la dimensione.</span><span class="sxs-lookup"><span data-stu-id="f9286-104">When you add a user-defined hierarchy, it is not available to users until it is instantiated in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the dimension is processed.</span></span> <span data-ttu-id="f9286-105">Per ulteriori informazioni, vedere [database modello multidimensionale &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) e [elaborazione di oggetti del modello multidimensionale](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="f9286-105">For more information, see [Multidimensional Model Databases &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) and [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-add-a-user-defined-hierarchy-to-a-dimension"></a><span data-ttu-id="f9286-106">Per aggiungere una gerarchia definita dall'utente a una dimensione</span><span class="sxs-lookup"><span data-stu-id="f9286-106">To add a user-defined hierarchy to a dimension</span></span>  
  
1.  <span data-ttu-id="f9286-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto appropriato di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , quindi aprire la dimensione che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f9286-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the appropriate [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then open the dimension with which you want to work.</span></span>  
  
     <span data-ttu-id="f9286-108">La dimensione viene aperta nella scheda **Struttura dimensione** di Progettazione dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f9286-108">The dimension opens in Dimension Designer on the **Dimension Structure** tab.</span></span>  
  
2.  <span data-ttu-id="f9286-109">Trascinare l'attributo che si vuole usare nella gerarchia definita dall'utente dal riquadro **Attributi** al riquadro **Gerarchie** .</span><span class="sxs-lookup"><span data-stu-id="f9286-109">From the **Attributes** pane, drag an attribute that you want to use in the user-defined hierarchy to the **Hierarchies** pane.</span></span>  
  
3.  <span data-ttu-id="f9286-110">Trascinare ulteriori attributi per formare i livelli della gerarchia definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f9286-110">Drag additional attributes to form levels in the user-defined hierarchy.</span></span>  
  
     <span data-ttu-id="f9286-111">L'ordine nel quale sono elencati gli attributi è determinante.</span><span class="sxs-lookup"><span data-stu-id="f9286-111">The order in which attributes are listed in the hierarchy is important.</span></span> <span data-ttu-id="f9286-112">Ad esempio, in una gerarchia temporale, gli anni devono essere visualizzati più in alto dei giorni nell'elenco della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="f9286-112">For example, in a time hierarchy, years should appear higher in the hierarchy list than days.</span></span>  
  
4.  <span data-ttu-id="f9286-113">Facoltativamente, riorganizzare i livelli della gerarchia definita dall'utente trascinandoli nelle posizioni corrette.</span><span class="sxs-lookup"><span data-stu-id="f9286-113">Optionally, rearrange the levels in the user-defined hierarchy by dragging them to the correct positions.</span></span>  
  
5.  <span data-ttu-id="f9286-114">Facoltativamente, modificare le proprietà della gerarchia definita dall'utente o dei relativi livelli.</span><span class="sxs-lookup"><span data-stu-id="f9286-114">Optionally, modify properties of the user-defined hierarchy or its levels.</span></span>  
  
     <span data-ttu-id="f9286-115">Può essere ad esempio utile specificare un nome per la gerarchia definita dall'utente, rinominarne uno o più livelli e definire un nome personalizzato per il livello Totale.</span><span class="sxs-lookup"><span data-stu-id="f9286-115">For example, you might want to specify a name for the user-defined hierarchy, rename one or more of its levels, and define a custom name for the All level.</span></span> <span data-ttu-id="f9286-116">Per ulteriori informazioni, vedere [proprietà della gerarchia utente](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md)e [proprietà del livello &#91;pavimentate su&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f9286-116">For more information, see [User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md), and [Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f9286-117">Per impostazione predefinita, una gerarchia definita dall'utente è solo un percorso che consente agli utenti di eseguire il drill-down delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="f9286-117">By default, a user-defined hierarchy is just a path that enables users to drill down for information.</span></span> <span data-ttu-id="f9286-118">Se esistono relazioni tra i livelli, tuttavia, è possibile incrementare le prestazioni di esecuzione delle query configurando relazioni tra attributi per i livelli.</span><span class="sxs-lookup"><span data-stu-id="f9286-118">However, if relationships exist between levels, you can increase query performance by configuring attribute relationships between levels.</span></span> <span data-ttu-id="f9286-119">Per altre informazioni, vedere [Relazioni tra attributi](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) e [Definire relazioni tra attributi](attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="f9286-119">For more information, see [Attribute Relationships](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) and [Define Attribute Relationships](attribute-relationships-define.md).</span></span>  
  
### <a name="to-remove-a-user-defined-hierarchy-from-a-dimension"></a><span data-ttu-id="f9286-120">Per rimuovere una gerarchia definita dall'utente da una dimensione</span><span class="sxs-lookup"><span data-stu-id="f9286-120">To remove a user-defined hierarchy from a dimension</span></span>  
  
-   <span data-ttu-id="f9286-121">Nella scheda **Struttura dimensione** fare clic sulla gerarchia definita dall'utente che si vuole rimuovere nel riquadro **Gerarchie** .</span><span class="sxs-lookup"><span data-stu-id="f9286-121">On the **Dimension Structure** tab, click the user-defined hierarchy that you want to remove in the **Hierarchies** pane.</span></span> <span data-ttu-id="f9286-122">Fare clic su **Elimina**sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="f9286-122">On the toolbar, click **Delete**.</span></span>  
  
     - <span data-ttu-id="f9286-123">- oppure -</span><span class="sxs-lookup"><span data-stu-id="f9286-123">or -</span></span>  
  
-   <span data-ttu-id="f9286-124">Fare clic con il pulsante destro del mouse sulla gerarchia definita dall'utente che si vuole rimuovere nel riquadro **Gerarchie** e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f9286-124">Right-click the user-defined hierarchy that you want to remove in the **Hierarchies** pane and then click **Delete**.</span></span>  
  
     - <span data-ttu-id="f9286-125">- oppure -</span><span class="sxs-lookup"><span data-stu-id="f9286-125">or -</span></span>  
  
-   <span data-ttu-id="f9286-126">Trascinare la gerarchia definita dall'utente al di fuori dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f9286-126">Drag the user-defined hierarchy off of the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9286-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9286-127">See Also</span></span>  
 <span data-ttu-id="f9286-128">[Gerarchie utente](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="f9286-128">[User Hierarchies](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span></span>  
 [<span data-ttu-id="f9286-129">Creare gerarchie definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="f9286-129">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
  
  
