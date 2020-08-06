---
title: Destinazione elaborazione partizione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partitionprocessingdest.f1
helpviewer_keywords:
- partitions [Analysis Services], processing
- Partition Processing destination [Integration Services]
- destinations [Integration Services], Partition Processing
ms.assetid: 36c592ff-3f78-4a58-b496-31c1c8eee131
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d32306328f7a0575e55397d5209b4767d0cf1bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626178"
---
# <a name="partition-processing-destination"></a><span data-ttu-id="bfc64-102">Destinazione elaborazione partizione</span><span class="sxs-lookup"><span data-stu-id="bfc64-102">Partition Processing Destination</span></span>
  <span data-ttu-id="bfc64-103">La destinazione Elaborazione partizione consente di caricare ed elaborare una partizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfc64-103">The Partition Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partition.</span></span> <span data-ttu-id="bfc64-104">Per altre informazioni sulle partizioni, vedere [Partizioni &#40;Analysis Services - Dati multidimensionali&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="bfc64-104">For more information about partitions, see [Partitions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="bfc64-105">La destinazione elaborazione partizione include le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfc64-105">The Partition Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="bfc64-106">Opzioni per l'esecuzione di elaborazioni incrementali, complete o di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="bfc64-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="bfc64-107">Configurazione degli errori, per specificare se l'elaborazione deve ignorare gli errori o arrestarsi dopo un numero di errori specificato.</span><span class="sxs-lookup"><span data-stu-id="bfc64-107">Error configuration, to specify whether processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="bfc64-108">Mapping di colonne di input a colonne di partizione.</span><span class="sxs-lookup"><span data-stu-id="bfc64-108">Mapping of input columns to partition columns.</span></span>  
  
 <span data-ttu-id="bfc64-109">Per altre informazioni sull'elaborazione degli oggetti [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vedere [Opzioni e impostazioni di elaborazione &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="bfc64-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bfc64-110">Le attività qui descritte non si applicano ai modelli tabulari di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="bfc64-110">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="bfc64-111">Non è possibile eseguire il mapping di colonne di input a colonne di partizione per i modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="bfc64-111">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="bfc64-112">È possibile utilizzare invece l'attività Esegui DDL Analysis Services [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) per elaborare la partizione.</span><span class="sxs-lookup"><span data-stu-id="bfc64-112">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](../control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="configuration-of-the-partition-processing-destination"></a><span data-ttu-id="bfc64-113">Configurazione della destinazione Elaborazione partizione</span><span class="sxs-lookup"><span data-stu-id="bfc64-113">Configuration of the Partition Processing Destination</span></span>  
 <span data-ttu-id="bfc64-114">Nella destinazione Elaborazione partizione viene usata una gestione connessione di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per connettersi al progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o all'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che contiene le partizioni e i cubi elaborati dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="bfc64-114">The Partition Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the cubes and partitions the destination processes.</span></span> <span data-ttu-id="bfc64-115">Per altre informazioni, vedere [Gestione connessione Analysis Services](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="bfc64-115">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="bfc64-116">Questa destinazione include un input.</span><span class="sxs-lookup"><span data-stu-id="bfc64-116">This destination has one input.</span></span> <span data-ttu-id="bfc64-117">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="bfc64-117">It does not support an error output.</span></span>  
  
 <span data-ttu-id="bfc64-118">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="bfc64-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="bfc64-119">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor destinazione elaborazione partizione** , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfc64-119">For more information about the properties that you can set in the Partition Processing **Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="bfc64-120">Editor destinazione elaborazione partizione &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="bfc64-120">Partition Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../partition-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="bfc64-121">Editor destinazione elaborazione partizione &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="bfc64-121">Partition Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../partition-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="bfc64-122">Editor destinazione elaborazione partizione &#40;pagina Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="bfc64-122">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../partition-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="bfc64-123">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="bfc64-123">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="bfc64-124">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfc64-124">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="bfc64-125">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="bfc64-125">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="bfc64-126">Proprietà personalizzate della destinazione elaborazione partizione</span><span class="sxs-lookup"><span data-stu-id="bfc64-126">Partition Processing Destination Custom Properties</span></span>](partition-processing-destination-custom-properties.md)  
  
 <span data-ttu-id="bfc64-127">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="bfc64-127">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
