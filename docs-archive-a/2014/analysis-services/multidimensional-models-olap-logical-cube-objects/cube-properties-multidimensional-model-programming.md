---
title: Proprietà cubo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Collation property
- ID property
- ErrorConfiguration property
- cubes [Analysis Services], properties
- Description property
- DefaultMeasure property
- ProcessingMode property
- AggregationPrefix property
- EstimatedRows property
- Visible property
- StorageLocation property
- StorageMode property
- ScriptErrorHandlingMode property
- Source property
- ScriptCacheProcessingMode property
- Language property
- Name property
- properties [Analysis Services], cubes
- ProcessingPriority property
- ProactiveCaching property
ms.assetid: 72ca3387-620d-4473-8e23-7fe1f2b3d5bf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 27d4202774107795eaddf76c27e21010d534d977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625016"
---
# <a name="cube-properties"></a><span data-ttu-id="38fc2-102">Proprietà dei cubi</span><span class="sxs-lookup"><span data-stu-id="38fc2-102">Cube Properties</span></span>
  <span data-ttu-id="38fc2-103">I cubi dispongono di proprietà che è possibile impostare per influire sul funzionamento a livello di cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-103">Cubes have a number of properties that you can set to affect cube-wide behavior.</span></span> <span data-ttu-id="38fc2-104">Nella tabella seguente è disponibile un riepilogo di tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="38fc2-104">These properties are summarized in the following table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38fc2-105">Alcune proprietà vengono impostate automaticamente quando si crea il cubo e non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="38fc2-105">Some properties are set automatically when the cube is created and cannot be changed.</span></span>  
  
 <span data-ttu-id="38fc2-106">Per ulteriori informazioni su come impostare le proprietà del cubo, vedere [Progettazione cubi &#40;Analysis Services-&#41;di dati multidimensionali ](../cube-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="38fc2-106">For more information about how to set cube properties, see [Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](../cube-designer-analysis-services-multidimensional-data.md).</span></span>  
  
|<span data-ttu-id="38fc2-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="38fc2-107">Property</span></span>|<span data-ttu-id="38fc2-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38fc2-108">Description</span></span>|  
|--------------|-----------------|  
|`AggregationPrefix`|<span data-ttu-id="38fc2-109">Specifica il prefisso comune utilizzato per i nomi di aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="38fc2-109">Specifies the common prefix that is used for aggregation names.</span></span>|  
|`Collation`|<span data-ttu-id="38fc2-110">Specifica l'identificatore delle impostazioni locali (LCID) e il flag di confronto, separati da un carattere di sottolineatura, ad esempio Latin1_General_C1_AS.</span><span class="sxs-lookup"><span data-stu-id="38fc2-110">Specifies the locale identifier (LCID) and the comparison flag, separated by an underscore: for example, Latin1_General_C1_AS.</span></span>|  
|`DefaultMeasure`|<span data-ttu-id="38fc2-111">Contiene un'espressione MDX (Multidimensional Expression) che definisce la misura predefinita per il cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-111">Contains a Multidimensional Expressions (MDX) expression that defines the default measure for the cube.</span></span>|  
|`Description`|<span data-ttu-id="38fc2-112">Fornisce una descrizione del cubo, che può essere esposta in applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="38fc2-112">Provides a description of the cube, which may be exposed in client applications.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="38fc2-113">Contiene le impostazioni configurabili per la gestione degli errori, relative alla gestione di chiavi duplicate, chiavi sconosciute, limiti di errore, azione da intraprendere in caso di rilevamento di un errore, file di log degli errori e gestione della chiave Null.</span><span class="sxs-lookup"><span data-stu-id="38fc2-113">Contains configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`EstimatedRows`|<span data-ttu-id="38fc2-114">Specifica il numero di righe stimate nel cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-114">Specifies the number of estimated rows in the cube.</span></span>|  
|`ID`|<span data-ttu-id="38fc2-115">Contiene l'identificatore univoco (ID) del cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-115">Contains the unique identifier (ID) of the cube.</span></span>|  
|`Language`|<span data-ttu-id="38fc2-116">Specifica l'identificatore della lingua predefinita del cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-116">Specifies the default language identifier of the cube.</span></span>|  
|`Name`|<span data-ttu-id="38fc2-117">Specifica il nome descrittivo del cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-117">Specifies the user-friendly name of the cube.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="38fc2-118">Definisce le impostazioni di memorizzazione nella cache attiva per il cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-118">Defines proactive cache settings for the cube.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="38fc2-119">Indica se l'indicizzazione e l'aggregazione devono essere eseguite durante o dopo l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="38fc2-119">Indicates whether indexing and aggregating should occur during or after processing.</span></span> <span data-ttu-id="38fc2-120">Le opzioni sono **Regular** o `lazy` .</span><span class="sxs-lookup"><span data-stu-id="38fc2-120">Options are **regular** or `lazy`.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="38fc2-121">Determina la priorità di elaborazione del cubo durante operazioni in background, ad esempio indicizzazione e aggregazioni lente</span><span class="sxs-lookup"><span data-stu-id="38fc2-121">Determines the processing priority of the cube during background operations, such as lazy aggregations and indexing.</span></span> <span data-ttu-id="38fc2-122">Il valore predefinito è **0**.</span><span class="sxs-lookup"><span data-stu-id="38fc2-122">The default value is **0**.</span></span>|  
|`ScriptCacheProcessingMode`|<span data-ttu-id="38fc2-123">Indica se la cache script deve essere compilata durante o dopo l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="38fc2-123">Indicates whether the script cache should be built during or after processing.</span></span> <span data-ttu-id="38fc2-124">Le opzioni sono **Regular** e `lazy` .</span><span class="sxs-lookup"><span data-stu-id="38fc2-124">Options are **regular** and `lazy`.</span></span>|  
|`ScriptErrorHandlingMode`|<span data-ttu-id="38fc2-125">Determina la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="38fc2-125">Determines error handling.</span></span> <span data-ttu-id="38fc2-126">Le opzioni disponibili sono `IgnoreNone` o `IgnoreAll`.</span><span class="sxs-lookup"><span data-stu-id="38fc2-126">Options are `IgnoreNone` or `IgnoreAll`</span></span>|  
|`Source`|<span data-ttu-id="38fc2-127">Visualizza la vista origine dati utilizzata per il cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-127">Displays the data source view used for the cube.</span></span>|  
|`StorageLocation`|<span data-ttu-id="38fc2-128">Specifica il percorso di archiviazione nel file system per il cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-128">Specifies the file system storage location for the cube.</span></span> <span data-ttu-id="38fc2-129">Se non viene specificato alcun valore, il percorso viene ereditato dal database contenente l'oggetto del cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-129">If none is specified, the location is inherited from the database that contains the cube object.</span></span>|  
|`StorageMode`|<span data-ttu-id="38fc2-130">Specifica la modalità di archiviazione per il cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-130">Specifies the storage mode for the cube.</span></span> <span data-ttu-id="38fc2-131">I valori sono `MOLAP` , `ROLAP` o`HOLAP``.`</span><span class="sxs-lookup"><span data-stu-id="38fc2-131">Values are `MOLAP`, `ROLAP`, or `HOLAP``.`</span></span>|  
|`Visible`|<span data-ttu-id="38fc2-132">Determina la visibilità del cubo.</span><span class="sxs-lookup"><span data-stu-id="38fc2-132">Determines the visibility of the cube.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="38fc2-133">Per ulteriori informazioni sull'impostazione dei valori per la proprietà ErrorConfiguration quando si utilizzano valori null e altri problemi di integrità dei dati, vedere [gestione dei problemi di integrità dei dati in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="38fc2-133">For more information about setting values for the ErrorConfiguration property when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fc2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38fc2-134">See Also</span></span>  
 [<span data-ttu-id="38fc2-135">Caching attivo &#40;partizioni&#41;</span><span class="sxs-lookup"><span data-stu-id="38fc2-135">Proactive Caching &#40;Partitions&#41;</span></span>](partitions-proactive-caching.md)  
  
  
