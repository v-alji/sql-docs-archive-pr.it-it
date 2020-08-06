---
title: Funzionalità di Analysis Services sospese in SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, backward compatibility
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
- discontinued functionality [Analysis Services]
- unsupported features [Analysis Services]
ms.assetid: 39406be1-9819-4629-9c29-b32fb20bab2e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5414344eb65c907593c9077ee2ba5610b8b397c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637493"
---
# <a name="discontinued-analysis-services-functionality-in-sql-server-2014"></a><span data-ttu-id="9a69e-102">Funzionalità di Analysis Services non più utilizzate in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="9a69e-102">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>
  <span data-ttu-id="9a69e-103">In questo argomento vengono descritte le funzionalità di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] non più disponibili in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a69e-103">This topic describes [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] features that are no longer available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
## <a name="discontinued-features-in-sssql14"></a><span data-ttu-id="9a69e-104">Funzionalità non più disponibili in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a69e-104">Discontinued Features in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
  
|<span data-ttu-id="9a69e-105">Category</span><span class="sxs-lookup"><span data-stu-id="9a69e-105">Category</span></span>|<span data-ttu-id="9a69e-106">Funzionalità deprecata</span><span class="sxs-lookup"><span data-stu-id="9a69e-106">Deprecated feature</span></span>|<span data-ttu-id="9a69e-107">Sostituzione</span><span class="sxs-lookup"><span data-stu-id="9a69e-107">Replacement</span></span>|  
|--------------|------------------------|-----------------|  
|<span data-ttu-id="9a69e-108">Cubi locali</span><span class="sxs-lookup"><span data-stu-id="9a69e-108">Local cubes</span></span>|<span data-ttu-id="9a69e-109">Proprietà della stringa di connessione InsertInto</span><span class="sxs-lookup"><span data-stu-id="9a69e-109">InsertInto connection string property</span></span>|<span data-ttu-id="9a69e-110">La sintassi della stringa di connessione originale per il popolamento di cubi locali viene sostituita dall'istruzione Create Global Cube.</span><span class="sxs-lookup"><span data-stu-id="9a69e-110">Original connection string syntax for populating local cubes is replaced by the Create Global Cube statement.</span></span> <span data-ttu-id="9a69e-111">Per ulteriori informazioni, vedere [istruzione CREATE GLOBAL CUBE &#40;&#41;MDX ](/sql/mdx/mdx-data-definition-create-global-cube).</span><span class="sxs-lookup"><span data-stu-id="9a69e-111">For more information, see [CREATE GLOBAL CUBE Statement  &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span></span>|  
|<span data-ttu-id="9a69e-112">Cubi locali</span><span class="sxs-lookup"><span data-stu-id="9a69e-112">Local cubes</span></span>|<span data-ttu-id="9a69e-113">Proprietà della stringa di connessione CreateCube</span><span class="sxs-lookup"><span data-stu-id="9a69e-113">CreateCube connection string property</span></span>|<span data-ttu-id="9a69e-114">La sintassi della stringa di connessione originale per il popolamento di cubi locali viene sostituita dall'istruzione Create Global Cube.</span><span class="sxs-lookup"><span data-stu-id="9a69e-114">Original connection string syntax for populating local cubes is replaced by the Create Global Cube statement.</span></span> <span data-ttu-id="9a69e-115">Per ulteriori informazioni, vedere [istruzione CREATE GLOBAL CUBE &#40;&#41;MDX ](/sql/mdx/mdx-data-definition-create-global-cube).</span><span class="sxs-lookup"><span data-stu-id="9a69e-115">For more information, see [CREATE GLOBAL CUBE Statement  &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube).</span></span>|  
|<span data-ttu-id="9a69e-116">Data Mining</span><span class="sxs-lookup"><span data-stu-id="9a69e-116">Data Mining</span></span>|<span data-ttu-id="9a69e-117">SQL Server 2000 PMML</span><span class="sxs-lookup"><span data-stu-id="9a69e-117">SQL Server 2000 PMML</span></span>|<span data-ttu-id="9a69e-118">Tramite la funzionalità SQL Server 2000 PMML veniva prodotto un formato di PMML con estensioni proprietarie per supportare funzionalità univoche fornite da algoritmi di Data mining non disponibili nella specifica PMML.</span><span class="sxs-lookup"><span data-stu-id="9a69e-118">The SQL Server 2000 PMML feature produced a form of PMML that had proprietary extensions to support unique features provided by Data Mining algorithms that were not available in the PMML specification.</span></span> <span data-ttu-id="9a69e-119">In SQL Server 2005, tramite Analysis Services è stato effettuare l'aggiornamento della funzionalità PMML allo standard più recente PMML 2.1.</span><span class="sxs-lookup"><span data-stu-id="9a69e-119">In SQL Server 2005, Analysis Services updated the PMML feature to the newer PMML 2.1 standard.</span></span> <span data-ttu-id="9a69e-120">Di conseguenza, le estensioni proprietarie aggiunte in SQL Server 2000 non sono più necessarie, sebbene siano ancora supportate in questa versione.</span><span class="sxs-lookup"><span data-stu-id="9a69e-120">As a result, the proprietary extensions added in SQL Server 2000 are no longer needed, although they are still supported in this release.</span></span>|  
|<span data-ttu-id="9a69e-121">Istruzione MDX</span><span class="sxs-lookup"><span data-stu-id="9a69e-121">MDX Statement</span></span>|<span data-ttu-id="9a69e-122">Istruzione Create Action</span><span class="sxs-lookup"><span data-stu-id="9a69e-122">Create Action statement</span></span>|<span data-ttu-id="9a69e-123">Questa istruzione è stata inclusa per compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="9a69e-123">This statement is included for backwards compatibility.</span></span> <span data-ttu-id="9a69e-124">Viene sostituita dall'oggetto Azione.</span><span class="sxs-lookup"><span data-stu-id="9a69e-124">It is replaced by the Action object.</span></span> <span data-ttu-id="9a69e-125">Per ulteriori informazioni su come creare azioni nelle versioni recenti di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , vedere [azioni &#40;Analysis Services-&#41;di dati multidimensionali ](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="9a69e-125">For more information about how to create actions in recent versions of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="discontinued-features-in-previous-releases"></a><span data-ttu-id="9a69e-126">Funzionalità non più supportate delle versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="9a69e-126">Discontinued Features in Previous Releases</span></span>  
 <span data-ttu-id="9a69e-127">La Migrazione guidata, utilizzata per la migrazione dei database di SQL Server 2000 Analysis Services a versioni più recenti non è più disponibile in quanto SQL Server 2000 non è più supportato.</span><span class="sxs-lookup"><span data-stu-id="9a69e-127">Migration Wizard, used to migrate SQL Server 2000 Analysis Services databases to newer versions, is discontinued because SQL Server 2000 is no longer supported.</span></span>  
  
 <span data-ttu-id="9a69e-128">Anche la libreria DSO (Decision Support Objects), che forniva compatibilità con i database di SQL Server 2000 Analysis Services non è più disponibile e non fa più parte di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9a69e-128">Decision Support Objects (DSO) library that provided compatibility with SQL Server 2000 Analysis Services databases is also discontinued and no longer part of SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a69e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a69e-129">See Also</span></span>  
 [<span data-ttu-id="9a69e-130">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="9a69e-130">Analysis Services Backward Compatibility</span></span>](analysis-services-backward-compatibility.md)  
  
  
