---
title: Configurare le proprietà delle misure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- additivity [Analysis Services]
- ID property
- ErrorConfiguration property
- AggregateFunction property
- DisplayFolder property
- IgnoreUnrelatedDimensions property
- FormatString property
- Description property
- semiadditive
- properties [Analysis Services], measure groups
- aggregate functions [Analysis Services]
- DataType property
- ProcessingMode property
- MeasureExpression property
- AggregationPrefix property
- Visible property
- properties [Analysis Services], measures
- StorageLocation property
- StorageMode property
- formats [Analysis Services], measures
- Source property
- aggregations [Analysis Services], measures
- measures [Analysis Services], properties
- nonadditive [Analysis Services]
- Name property
- measures [Analysis Services], display formats
- ProcessingPriority property
- measure groups [Analysis Services], properties
- Type property
- ProactiveCaching property
ms.assetid: e9031078-c4f5-4986-b0c9-4d064b622ab7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ca291a5181fdb3f7a88845431d61ffd7a1034eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721968"
---
# <a name="configure-measure-properties"></a><span data-ttu-id="3dc89-102">Configurare le proprietà delle misure</span><span class="sxs-lookup"><span data-stu-id="3dc89-102">Configure Measure Properties</span></span>
  <span data-ttu-id="3dc89-103">Le proprietà delle misure consentono di definirne il funzionamento e di controllare il modo in cui vengono visualizzate agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3dc89-103">Measures have properties that enable you to define how the measures function and to control how the measures appear to users.</span></span>  
  
 <span data-ttu-id="3dc89-104">È possibile impostare proprietà in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] durante la creazione o la modifica di un cubo o una misura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-104">You can set properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] when creating or editing a cube or measure.</span></span> <span data-ttu-id="3dc89-105">Queste proprietà possono essere impostate anche a livello di programmazione mediante MDX o AMO.</span><span class="sxs-lookup"><span data-stu-id="3dc89-105">You can also set them programmatically, using MDX or AMO.</span></span> <span data-ttu-id="3dc89-106">Per informazioni dettagliate, vedere [Creare misure e gruppi di misure nei modelli multidimensionali](create-measures-and-measure-groups-in-multidimensional-models.md) o [Istruzione CREATE MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) o [Programmazione di oggetti di base OLAP in AMO](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="3dc89-106">See [Create Measures and Measure Groups in Multidimensional Models](create-measures-and-measure-groups-in-multidimensional-models.md) or [CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) or [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects) for details.</span></span>  
  
## <a name="measure-properties"></a><span data-ttu-id="3dc89-107">Proprietà delle misure</span><span class="sxs-lookup"><span data-stu-id="3dc89-107">Measure Properties</span></span>  
 <span data-ttu-id="3dc89-108">Le misure ereditano alcune proprietà dal gruppo di misure di cui sono membri, a meno che tali proprietà non vengano sostituite a livello di misura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-108">Measures inherit certain properties from the measure group of which they are a member, unless those properties are overridden at the measure level.</span></span> <span data-ttu-id="3dc89-109">Le proprietà delle misure ne determinano la modalità di aggregazione, il tipo di dati, il nome visualizzato dall'utente, la cartella di visualizzazione in cui appariranno, la stringa di formato, l'espressione, la colonna di origine sottostante e la visibilità da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="3dc89-109">Measure properties determine how a measure is aggregated, its data type, the name that is displayed to the user, the display folder in which the measure will appear, its format string, any measure expression, the underlying source column, and its visibility to users.</span></span>  
  
|<span data-ttu-id="3dc89-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3dc89-110">Property</span></span>|<span data-ttu-id="3dc89-111">Definizione</span><span class="sxs-lookup"><span data-stu-id="3dc89-111">Definition</span></span>|  
|--------------|----------------|  
|`AggregateFunction`|<span data-ttu-id="3dc89-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3dc89-112">Required.</span></span> <span data-ttu-id="3dc89-113">Determina la modalità di aggregazione delle misure.</span><span class="sxs-lookup"><span data-stu-id="3dc89-113">Determines how measures are aggregated.</span></span> <span data-ttu-id="3dc89-114">`Sum`è l'aggregazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3dc89-114">`Sum` is the default aggregation.</span></span> <span data-ttu-id="3dc89-115">Per altre informazioni, vedere [Utilizzare le funzioni di aggregazione](use-aggregate-functions.md) per una descrizione di ogni funzione.</span><span class="sxs-lookup"><span data-stu-id="3dc89-115">For more information, see [Use Aggregate Functions](use-aggregate-functions.md) for a description of each function.</span></span>|  
|`DataType`|<span data-ttu-id="3dc89-116">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3dc89-116">Required.</span></span> <span data-ttu-id="3dc89-117">Specifica il tipo di dati della colonna della tabella dei fatti sottostante a cui è associata la misura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-117">Specifies the data type of the column in the underlying fact table to which the measure is bound.</span></span> <span data-ttu-id="3dc89-118">Per impostazione predefinita, questo valore viene ereditato dalla colonna di origine.</span><span class="sxs-lookup"><span data-stu-id="3dc89-118">This value is inherited from the source column by default.</span></span>|  
|`Description`|<span data-ttu-id="3dc89-119">Fornisce una descrizione della misura, che può essere esposta in applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="3dc89-119">Provides a description of the measure, which may be exposed in client applications.</span></span>|  
|`DisplayFolder`|<span data-ttu-id="3dc89-120">Specifica la cartella in cui verrà visualizzata la misura quando gli utenti si connettono al cubo.</span><span class="sxs-lookup"><span data-stu-id="3dc89-120">Specifies the folder in which the measure will appear when users connect to the cube.</span></span> <span data-ttu-id="3dc89-121">Quando in un cubo sono presenti numerose misure, è possibile usare le cartelle di visualizzazione per categorizzare le misure e migliorare l'esplorazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3dc89-121">When a cube has many measures, you can use display folders to categorize the measures and improve the user browsing experience.</span></span>|  
|`FormatString`|<span data-ttu-id="3dc89-122">È possibile selezionare il formato in cui gli utenti visualizzeranno i valori della misura utilizzando la proprietà `FormatString` della misura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-122">You can select the format that is used to display measure values to users by using the `FormatString` property of the measure.</span></span><br /><br /> <span data-ttu-id="3dc89-123">Anche se in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]è disponibile un elenco di formati di visualizzazione, è possibile specificare formati aggiuntivi non inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3dc89-123">Although a list of display formats is provided in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can specify many additional formats that are not in the list.</span></span> <span data-ttu-id="3dc89-124">È possibile specificare qualsiasi formato denominato o definito dall'utente che risulti valido in Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3dc89-124">You can specify any named or user-defined format that is valid in Microsoft Visual Basic.</span></span>|  
|`ID`|<span data-ttu-id="3dc89-125">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3dc89-125">Required.</span></span> <span data-ttu-id="3dc89-126">Visualizza l'identificatore univoco (ID) della misura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-126">Displays the unique identifier (ID) of the measure.</span></span> <span data-ttu-id="3dc89-127">Questa proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-127">This property is read-only.</span></span>|  
|`MeasureExpression`|<span data-ttu-id="3dc89-128">Specifica un'espressione MDX vincolata che definisce il valore della misura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-128">Specifies a constrained MDX expression defining the value of the measure.</span></span> <span data-ttu-id="3dc89-129">L'espressione viene valutata a livello foglia prima dell'aggregazione e consente la ponderazione di un valore,</span><span class="sxs-lookup"><span data-stu-id="3dc89-129">The expression is evaluated at the leaf level before being aggregated, and allows for weighting of a value.</span></span> <span data-ttu-id="3dc89-130">ad esempio in una conversione valuta in cui un importo di vendita viene ponderato in base al tasso di cambio.</span><span class="sxs-lookup"><span data-stu-id="3dc89-130">For example, in currency conversion where a sales amount is weighted by the exchange rate.</span></span>|  
|`Name`|<span data-ttu-id="3dc89-131">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3dc89-131">Required.</span></span> <span data-ttu-id="3dc89-132">Specifica il nome della misura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-132">Specifies the name of the measure.</span></span>|  
|`Source`|<span data-ttu-id="3dc89-133">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3dc89-133">Required.</span></span> <span data-ttu-id="3dc89-134">Specifica la colonna nella vista origine dati a cui è associata la misura.</span><span class="sxs-lookup"><span data-stu-id="3dc89-134">Specifies the column in the data source view to which the measure is bound.</span></span> <span data-ttu-id="3dc89-135">Vedere [Origini dati e associazioni &#40;SSAS - multidimensionale&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="3dc89-135">See [Data Sources and Bindings &#40;SSAS Multidimensional&#41;](data-sources-and-bindings-ssas-multidimensional.md).</span></span>|  
|`Visible`|<span data-ttu-id="3dc89-136">Determina la visibilità della misura nelle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="3dc89-136">Determines the visibility of the measure in client applications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3dc89-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dc89-137">See Also</span></span>  
 <span data-ttu-id="3dc89-138">[Configurare le proprietà del gruppo di misure](configure-measure-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="3dc89-138">[Configure Measure Group Properties](configure-measure-group-properties.md) </span></span>  
 [<span data-ttu-id="3dc89-139">Modifica delle misure</span><span class="sxs-lookup"><span data-stu-id="3dc89-139">Modifying Measures</span></span>](../lesson-3-1-modifying-measures.md)  
  
  
