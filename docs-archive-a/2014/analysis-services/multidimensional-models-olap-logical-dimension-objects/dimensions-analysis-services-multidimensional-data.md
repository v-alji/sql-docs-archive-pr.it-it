---
title: Dimensioni (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- OLAP objects [Analysis Services], dimensions
- dimensions [Analysis Services]
- Analysis Services objects, dimensions
ms.assetid: 2b114135-2572-4479-8c81-3ccf0cfeb9f7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e0e15d4f74c2c6cec06edaf692199e48534c7e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723196"
---
# <a name="dimensions-analysis-services---multidimensional-data"></a><span data-ttu-id="e9a83-102">Dimensioni (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="e9a83-102">Dimensions (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e9a83-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] le dimensioni sono un componente fondamentale dei cubi.</span><span class="sxs-lookup"><span data-stu-id="e9a83-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], dimensions are a fundamental component of cubes.</span></span> <span data-ttu-id="e9a83-104">Le dimensioni consentono di organizzare i dati in relazione a un'area di interesse per gli utenti, ad esempio relativa a clienti, archivi o dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e9a83-104">Dimensions organize data with relation to an area of interest, such as customers, stores, or employees, to users.</span></span> <span data-ttu-id="e9a83-105">Le dimensioni di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] includono attributi corrispondenti a colonne nelle tabelle delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e9a83-105">Dimensions in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contain attributes that correspond to columns in dimension tables.</span></span> <span data-ttu-id="e9a83-106">Questi attributi consistono in gerarchie degli attributi e possono essere organizzati in strutture gerarchiche definite dall'utente oppure possono essere definite come gerarchie padre-figlio basate su colonne nella tabella delle dimensioni sottostante.</span><span class="sxs-lookup"><span data-stu-id="e9a83-106">These attributes appear as attribute hierarchies and can be organized into user-defined hierarchies, or can be defined as parent-child hierarchies based on columns in the underlying dimension table.</span></span> <span data-ttu-id="e9a83-107">Queste gerarchie sono utilizzate per organizzare le misure incluse in un cubo.</span><span class="sxs-lookup"><span data-stu-id="e9a83-107">Hierarchies are used to organize measures that are contained in a cube.</span></span> <span data-ttu-id="e9a83-108">Negli argomenti seguenti viene fornita una panoramica di dimensioni, attributi e gerarchie.</span><span class="sxs-lookup"><span data-stu-id="e9a83-108">The following topics provide an overview of dimensions, attributes, and hierarchies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9a83-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e9a83-109">In This Section</span></span>  
  
|<span data-ttu-id="e9a83-110">Argomento</span><span class="sxs-lookup"><span data-stu-id="e9a83-110">Topic</span></span>|<span data-ttu-id="e9a83-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9a83-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e9a83-112">Introduzione alle dimensioni &#40;Analysis Services - Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="e9a83-112">Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="e9a83-113">Offre una panoramica dei concetti di base sulle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e9a83-113">Provides an overview of dimension concepts.</span></span>|  
|[<span data-ttu-id="e9a83-114">Attributi e gerarchie di attributi</span><span class="sxs-lookup"><span data-stu-id="e9a83-114">Attributes and Attribute Hierarchies</span></span>](attributes-and-attribute-hierarchies.md)|<span data-ttu-id="e9a83-115">Descrive gli attributi e le gerarchie degli attributi.</span><span class="sxs-lookup"><span data-stu-id="e9a83-115">Describes attributes and attribute hierarchies.</span></span>|  
|[<span data-ttu-id="e9a83-116">Gerarchie definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="e9a83-116">User Hierarchies</span></span>](user-hierarchies.md)|<span data-ttu-id="e9a83-117">Descrive le gerarchie di attributi definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e9a83-117">Describes user-defined hierarchies of attributes.</span></span>|  
|[<span data-ttu-id="e9a83-118">Dimensioni abilitate per la scrittura</span><span class="sxs-lookup"><span data-stu-id="e9a83-118">Write-Enabled Dimensions</span></span>](write-enabled-dimensions.md)|<span data-ttu-id="e9a83-119">Descrive le dimensioni abilitate per la scrittura.</span><span class="sxs-lookup"><span data-stu-id="e9a83-119">Describes write-enabled dimensions.</span></span>|  
|[<span data-ttu-id="e9a83-120">Traduzioni delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="e9a83-120">Dimension Translations</span></span>](dimension-translations.md)|<span data-ttu-id="e9a83-121">Descrive le traduzioni dei metadati delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e9a83-121">Describes translations of dimension meta data.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9a83-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9a83-122">See Also</span></span>  
 <span data-ttu-id="e9a83-123">[Dimensioni nei modelli multidimensionali](../multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="e9a83-123">[Dimensions in Multidimensional Models](../multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="e9a83-124">Oggetti Cube &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="e9a83-124">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
  
