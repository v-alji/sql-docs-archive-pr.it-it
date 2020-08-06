---
title: Proprietà delle dimensioni del database | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- metadata [Analysis Services]
- dimensions [Analysis Services], characteristics
- properties [Analysis Services], dimensions
ms.assetid: 075548ef-08a3-413c-8ee0-4a074c276fcc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 504e190f4c513a8c999c4d7d7ab9eaabb83298c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635241"
---
# <a name="database-dimension-properties"></a><span data-ttu-id="fc3ad-102">Proprietà delle dimensioni del database</span><span class="sxs-lookup"><span data-stu-id="fc3ad-102">Database Dimension Properties</span></span>
  <span data-ttu-id="fc3ad-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] le caratteristiche di una dimensione sono definite dai metadati per la dimensione, in base alle impostazioni di varie proprietà della dimensione e agli attributi o alle gerarchie contenute nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the characteristics of a dimension are defined by the metadata for the dimension, based on the settings of various dimension properties, and on the attributes or hierarchies that are contained by the dimension.</span></span> <span data-ttu-id="fc3ad-104">Nella tabella seguente vengono descritte le proprietà delle dimensioni in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc3ad-104">The following table describes the dimension properties in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="fc3ad-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fc3ad-105">Property</span></span>|<span data-ttu-id="fc3ad-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc3ad-106">Description</span></span>|  
|--------------|-----------------|  
|`AttributeAllMemberName`|<span data-ttu-id="fc3ad-107">Specifica il nome del membro Totale per gli attributi in una dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-107">Specifies the name of the All member for attributes in a dimension.</span></span>|  
|`Collation`|<span data-ttu-id="fc3ad-108">Determina le regole di confronto utilizzate dalla dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-108">Determines the collation used by the dimension.</span></span>|  
|`CurrentStorageMode`|<span data-ttu-id="fc3ad-109">Contiene la modalità di archiviazione corrente per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-109">Contains the current storage mode for the dimension.</span></span>|  
|`DependsOnDimension`|<span data-ttu-id="fc3ad-110">Contiene l'ID di un'altra dimensione da cui dipende la dimensione, se presente.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-110">Contains the ID of another dimension on which the dimension depends, if any.</span></span>|  
|`Description`|<span data-ttu-id="fc3ad-111">Contiene la descrizione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-111">Contains the description of the dimension.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="fc3ad-112">Impostazioni configurabili per la gestione degli errori, relative alla gestione di chiavi duplicate, chiavi sconosciute, limiti di errore, azione da intraprendere in caso di rilevamento di un errore, file di log degli errori e gestione della chiave Null.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-112">Configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`ID`|<span data-ttu-id="fc3ad-113">Contiene l'identificatore univoco (ID) della dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-113">Contains the unique identifier (ID) of the dimension.</span></span>|  
|`Language`|<span data-ttu-id="fc3ad-114">Specifica la lingua predefinita per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-114">Specifies the default language for the dimension.</span></span>|  
|`MdxMissingMemberMode`|<span data-ttu-id="fc3ad-115">Determina la modalità di gestione dei membri mancanti per le istruzioni MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="fc3ad-115">Determines how missing members are handled for Multidimensional Expressions (MDX) statements.</span></span>|  
|`MiningModelID`|<span data-ttu-id="fc3ad-116">Contiene l'ID del modello di data mining a cui è associata la dimensione di data mining.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-116">Contains the ID of the mining model with which the data mining dimension is associated.</span></span> <span data-ttu-id="fc3ad-117">Questa proprietà è applicabile solo se la dimensione è una dimensione di un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-117">This property is applicable only if the dimension is a mining model dimension.</span></span>|  
|`Name`|<span data-ttu-id="fc3ad-118">Specifica il nome della dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-118">Specifies the name of the dimension.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="fc3ad-119">Definisce le impostazioni di memorizzazione nella cache attiva per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-119">Defines the proactive cache settings for the dimension.</span></span>|  
|`ProcessingGroup`|<span data-ttu-id="fc3ad-120">Specifica il gruppo di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-120">Specifies the processing group.</span></span> <span data-ttu-id="fc3ad-121">I valori sono ByAttribute o ByTable.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-121">Values are ByAttribute or ByTable.</span></span> <span data-ttu-id="fc3ad-122">Il valore predefinito è `ByAttribute`.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-122">Default is `ByAttribute`.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="fc3ad-123">Indica se in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] l'indicizzazione e l'aggregazione devono venire eseguite durante o dopo l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-123">Indicates whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should index and aggregate during or after processing.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="fc3ad-124">Determina la priorità di elaborazione della dimensione durante le operazioni in background, ad esempio clustering, indicizzazione o aggregazione lenta.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-124">Determines the processing priority of the dimension during background operations such as lazy aggregation, indexing, or clustering.</span></span>|  
|`Source`|<span data-ttu-id="fc3ad-125">Identifica la vista origine dati a cui è associata la dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-125">Identifies the data source view to which the dimension is bound.</span></span>|  
|`StorageMode`|<span data-ttu-id="fc3ad-126">Determina la modalità di archiviazione per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-126">Determines the storage mode for the dimension.</span></span>|  
|`Type`|<span data-ttu-id="fc3ad-127">Specifica il tipo della dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-127">Specifies the type of the dimension.</span></span>|  
|`UnknownMember`|<span data-ttu-id="fc3ad-128">Indica se il membro sconosciuto è visibile.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-128">Indicates whether the unknown member is visible.</span></span>|  
|`UnknownMemberName`|<span data-ttu-id="fc3ad-129">Specifica la didascalia, nella lingua predefinita della dimensione, per il membro sconosciuto della dimensione.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-129">Specifies the caption, in the default language of the dimension, for the unknown member of the dimension.</span></span>|  
|`WriteEnabled`|<span data-ttu-id="fc3ad-130">Indica se i writeback della dimensione sono disponibili, in base alle autorizzazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="fc3ad-130">Indicates whether dimension writebacks are available (subject to security permissions).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="fc3ad-131">Per ulteriori informazioni sull'impostazione dei valori per le proprietà ErrorConfiguration e UnknownMember in caso di utilizzo di valori null e di altri problemi di integrità dei dati, vedere [gestione di problemi di integrità dei dati in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="fc3ad-131">For more information about setting values for the ErrorConfiguration and UnknownMember properties when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3ad-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc3ad-132">See Also</span></span>  
 <span data-ttu-id="fc3ad-133">[Attributi e gerarchie di attributi](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="fc3ad-133">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="fc3ad-134">[Gerarchie utente](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="fc3ad-134">[User Hierarchies](user-hierarchies.md) </span></span>  
 <span data-ttu-id="fc3ad-135">[Relazioni tra dimensioni](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="fc3ad-135">[Dimension Relationships](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 [<span data-ttu-id="fc3ad-136">Dimensioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="fc3ad-136">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
