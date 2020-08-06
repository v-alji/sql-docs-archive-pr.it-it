---
title: Proprietà percorso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- paths [Integration Services], properties
ms.assetid: 89b1e347-9579-4f6b-af74-c6519ea08eea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ca263b866fb6d5d7ceb6352f708f387d79cad4f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624800"
---
# <a name="path-properties"></a><span data-ttu-id="aafae-102">Proprietà del percorso</span><span class="sxs-lookup"><span data-stu-id="aafae-102">Path Properties</span></span>
  <span data-ttu-id="aafae-103">Gli oggetti flusso di dati nel [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] modello a oggetti hanno proprietà comuni e proprietà personalizzate a livello di componente, input e output e colonne di input e colonne di output.</span><span class="sxs-lookup"><span data-stu-id="aafae-103">The data flow objects in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model have common properties and custom properties at the level of the component, inputs and outputs, and input columns and output columns.</span></span> <span data-ttu-id="aafae-104">Molte proprietà hanno valori di sola lettura assegnati in fase di esecuzione dal motore del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="aafae-104">Many properties have read-only values that are assigned at run time by the data flow engine.</span></span>  
  
 <span data-ttu-id="aafae-105">In questo argomento vengono elencate e descritte le proprietà personalizzate dei percorsi che connettono gli oggetti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="aafae-105">This topic lists and describes the custom properties of the paths that connect data flow objects.</span></span>  
  
## <a name="path-properties"></a><span data-ttu-id="aafae-106">Proprietà del percorso</span><span class="sxs-lookup"><span data-stu-id="aafae-106">Path Properties</span></span>  
 <span data-ttu-id="aafae-107">Nel modello a oggetti [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] un percorso che connette componenti nel flusso di dati implementa l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="aafae-107">In the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model, a path that connects components in the data flow implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> interface.</span></span>  
  
 <span data-ttu-id="aafae-108">Nella tabella seguente vengono descritte le proprietà configurabili dei percorsi in un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="aafae-108">The following table describes the configurable properties of the paths in a data flow.</span></span> <span data-ttu-id="aafae-109">Inoltre, il motore del flusso di dati assegna valori a proprietà di sola lettura aggiuntive che non sono elencate qui.</span><span class="sxs-lookup"><span data-stu-id="aafae-109">The data flow engine also assigns values to additional read-only properties that are not listed here.</span></span>  
  
|<span data-ttu-id="aafae-110">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="aafae-110">Property name</span></span>|<span data-ttu-id="aafae-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="aafae-111">Data Type</span></span>|<span data-ttu-id="aafae-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aafae-112">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="aafae-113">PathAnnotation</span><span class="sxs-lookup"><span data-stu-id="aafae-113">PathAnnotation</span></span>|<span data-ttu-id="aafae-114">Integer (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="aafae-114">Integer (enumeration)</span></span>|<span data-ttu-id="aafae-115">Un valore che indica se un'annotazione deve essere visualizzata con il percorso sulla superficie dell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="aafae-115">A value that indicates whether an annotation should be displayed with the path on the designer surface.</span></span> <span data-ttu-id="aafae-116">I valori possibili sono `AsNeeded`, `SourceName`, `PathName` e `Never`.</span><span class="sxs-lookup"><span data-stu-id="aafae-116">The possible values are `AsNeeded`, `SourceName`, `PathName`, and `Never`.</span></span> <span data-ttu-id="aafae-117">Il valore predefinito è `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="aafae-117">The default value is `AsNeeded`.</span></span>|  
|<span data-ttu-id="aafae-118">DestinationName</span><span class="sxs-lookup"><span data-stu-id="aafae-118">DestinationName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100>|<span data-ttu-id="aafae-119">L'input associato al percorso.</span><span class="sxs-lookup"><span data-stu-id="aafae-119">The input associated with the path.</span></span>|  
|<span data-ttu-id="aafae-120">SourceName</span><span class="sxs-lookup"><span data-stu-id="aafae-120">SourceName</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100>|<span data-ttu-id="aafae-121">L'output associato al percorso.</span><span class="sxs-lookup"><span data-stu-id="aafae-121">The output associated with the path.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aafae-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aafae-122">See Also</span></span>  
 <span data-ttu-id="aafae-123">[Percorsi in Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="aafae-123">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="aafae-124">[Proprietà comuni](../../2014/integration-services/common-properties.md) </span><span class="sxs-lookup"><span data-stu-id="aafae-124">[Common Properties](../../2014/integration-services/common-properties.md) </span></span>  
 <span data-ttu-id="aafae-125">[Proprietà personalizzate della trasformazione](data-flow/transformations/transformation-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="aafae-125">[Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md) </span></span>  
 [<span data-ttu-id="aafae-126">Proprietà del flusso di dati che è possibile impostare tramite espressioni</span><span class="sxs-lookup"><span data-stu-id="aafae-126">Data Flow Properties that Can Be Set by Using Expressions</span></span>](../../2014/integration-services/data-flow-properties-that-can-be-set-by-using-expressions.md)  
  
  
