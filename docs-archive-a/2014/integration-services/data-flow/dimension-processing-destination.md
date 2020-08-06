---
title: Destinazione elaborazione dimensione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimensionprocessingdest.f1
helpviewer_keywords:
- Dimension Processing destination
- loading dimensions
- destinations [Integration Services], Dimension Processing
- dimensions [Analysis Services], processing
ms.assetid: 4c49bb95-7259-42f4-a785-bb6aaf5f8566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61cde87ac4fa5fcb1352491d787674447dd404b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626198"
---
# <a name="dimension-processing-destination"></a><span data-ttu-id="826e7-102">destinazione elaborazione dimensione</span><span class="sxs-lookup"><span data-stu-id="826e7-102">Dimension Processing Destination</span></span>
  <span data-ttu-id="826e7-103">La destinazione elaborazione dimensione consente di caricare ed elaborare una dimensione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="826e7-103">The Dimension Processing destination loads and processes an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimension.</span></span> <span data-ttu-id="826e7-104">Per altre informazioni sulle dimensioni, vedere [Dimensioni &#40;Analysis Services - Dati multidimensionali&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span><span class="sxs-lookup"><span data-stu-id="826e7-104">For more information about dimensions, see [Dimensions &#40;Analysis Services - Multidimensional Data&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data).</span></span>  
  
 <span data-ttu-id="826e7-105">La destinazione elaborazione dimensione include le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="826e7-105">The Dimension Processing destination includes the following features:</span></span>  
  
-   <span data-ttu-id="826e7-106">Opzioni per l'esecuzione di elaborazioni incrementali, complete o di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="826e7-106">Options to perform incremental, full, or update processing.</span></span>  
  
-   <span data-ttu-id="826e7-107">Configurazione degli errori, per specificare se l'elaborazione della dimensione deve ignorare gli errori o arrestarsi dopo un numero di errori specificato.</span><span class="sxs-lookup"><span data-stu-id="826e7-107">Error configuration, to specify whether dimension processing ignores errors or stops after a specified number of errors.</span></span>  
  
-   <span data-ttu-id="826e7-108">Mapping di colonne di input a colonne nelle tabelle delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="826e7-108">Mapping of input columns to columns in dimension tables.</span></span>  
  
 <span data-ttu-id="826e7-109">Per altre informazioni sull'elaborazione degli oggetti [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vedere [Opzioni e impostazioni di elaborazione &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="826e7-109">For more information about processing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Processing Options and Settings &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/processing-options-and-settings-analysis-services).</span></span>  
  
## <a name="configuration-of-the-dimension-processing-destination"></a><span data-ttu-id="826e7-110">Configurazione della destinazione Elaborazione dimensione</span><span class="sxs-lookup"><span data-stu-id="826e7-110">Configuration of the Dimension Processing Destination</span></span>  
 <span data-ttu-id="826e7-111">La destinazione Elaborazione dimensione utilizza una gestione connessione di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per connettersi al progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o all'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che contiene le dimensioni elaborate dalla destinazione.</span><span class="sxs-lookup"><span data-stu-id="826e7-111">The Dimension Processing destination uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the dimensions the destination processes.</span></span> <span data-ttu-id="826e7-112">Per altre informazioni, vedere [Gestione connessione Analysis Services](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="826e7-112">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="826e7-113">Questa destinazione include un input.</span><span class="sxs-lookup"><span data-stu-id="826e7-113">This destination has one input.</span></span> <span data-ttu-id="826e7-114">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="826e7-114">It does not support an error output.</span></span>  
  
 <span data-ttu-id="826e7-115">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="826e7-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="826e7-116">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor destinazione elaborazione dimensione** , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="826e7-116">For more information about the properties that you can set in the **Dimension Processing Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="826e7-117">Editor destinazione elaborazione dimensione &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="826e7-117">Dimension Processing Destination Editor &#40;Connection Manager Page&#41;</span></span>](../dimension-processing-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="826e7-118">Editor destinazione elaborazione dimensione &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="826e7-118">Dimension Processing Destination Editor &#40;Mappings Page&#41;</span></span>](../dimension-processing-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="826e7-119">Editor destinazione elaborazione dimensione &#40;pagina Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="826e7-119">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../dimension-processing-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="826e7-120">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="826e7-120">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="826e7-121">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di programmazione, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="826e7-121">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="826e7-122">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="826e7-122">Common Properties</span></span>](../common-properties.md)  
  
 <span data-ttu-id="826e7-123">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="826e7-123">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826e7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="826e7-124">See Also</span></span>  
 <span data-ttu-id="826e7-125">[Flusso di dati](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="826e7-125">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="826e7-126">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="826e7-126">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
