---
title: Configurare le proprietà della relazione tra attributi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- flexible relationships (Analysis Services)
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
- properties [Analysis Services], attribute relationships
- rigid relationships (Analysis Services)
ms.assetid: fce511af-66d7-42fc-bb3a-6c516f16b10e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 241fa2af16377fd2cacf657ec6f99c5ca4bd0c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624418"
---
# <a name="configure-attribute-relationship-properties"></a><span data-ttu-id="70647-102">Configurare le proprietà della relazione tra attributi</span><span class="sxs-lookup"><span data-stu-id="70647-102">Configure Attribute Relationship Properties</span></span>
  <span data-ttu-id="70647-103">Nella tabella seguente vengono elencate e descritte le proprietà di una relazione tra attributi.</span><span class="sxs-lookup"><span data-stu-id="70647-103">The following table lists and describes the properties of an attribute relationship.</span></span>  
  
|<span data-ttu-id="70647-104">Proprietà</span><span class="sxs-lookup"><span data-stu-id="70647-104">Property</span></span>|<span data-ttu-id="70647-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70647-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="70647-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="70647-106">Attribute</span></span>|<span data-ttu-id="70647-107">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="70647-107">Contains the name of the attribute.</span></span>|  
|<span data-ttu-id="70647-108">Cardinalità</span><span class="sxs-lookup"><span data-stu-id="70647-108">Cardinality</span></span>|<span data-ttu-id="70647-109">Indica la cardinalità della relazione.</span><span class="sxs-lookup"><span data-stu-id="70647-109">Indicates the cardinality of the relationship.</span></span> <span data-ttu-id="70647-110">Il valore è Many per una relazione molti-a-uno e One per una relazione uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="70647-110">Values are Many, for a many to one relationship, or One, for a one to one relationship.</span></span> <span data-ttu-id="70647-111">Il valore predefinito è Many.</span><span class="sxs-lookup"><span data-stu-id="70647-111">Default value is Many.</span></span> <span data-ttu-id="70647-112">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] la proprietà Cardinality non ha alcun effetto. il suo utilizzo è riservato per un'implementazione futura.</span><span class="sxs-lookup"><span data-stu-id="70647-112">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the cardinality property has no effect - its use is reserved for a future implementation.</span></span>|  
|<span data-ttu-id="70647-113">Nome</span><span class="sxs-lookup"><span data-stu-id="70647-113">Name</span></span>|<span data-ttu-id="70647-114">Nome descrittivo dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="70647-114">Contains the friendly name of the attribute.</span></span>|  
|<span data-ttu-id="70647-115">RelationshipType</span><span class="sxs-lookup"><span data-stu-id="70647-115">RelationshipType</span></span>|<span data-ttu-id="70647-116">Indica se le relazioni tra membri cambiano nel tempo.</span><span class="sxs-lookup"><span data-stu-id="70647-116">Indicates whether member relationships change over time.</span></span> <span data-ttu-id="70647-117">Il valore di questa proprietà è Rigid se le relazioni tra membri non cambiano nel tempo o Flexible in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="70647-117">Values are Rigid, which means that relationships between members do not change over time, or Flexible, which means that relationships between members change over time.</span></span> <span data-ttu-id="70647-118">Il valore predefinito è Flexible.</span><span class="sxs-lookup"><span data-stu-id="70647-118">Default is Flexible.</span></span> <span data-ttu-id="70647-119">Se si definisce una relazione flessibile, le aggregazioni verranno eliminate e ricalcolate come parte di un aggiornamento incrementale. Non verranno invece eliminate se vengono aggiunti solo nuovi membri.</span><span class="sxs-lookup"><span data-stu-id="70647-119">If you define a relationship as flexible, aggregations are dropped and recomputed as part of an incremental update (they will not be dropped if only new members are added).</span></span> <span data-ttu-id="70647-120">Se viene definita una relazione rigida, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] consente di mantenere le aggregazioni quando la dimensione viene aggiornata in modo incrementale.</span><span class="sxs-lookup"><span data-stu-id="70647-120">If you define a relationship as rigid, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retains aggregations when the dimension is incrementally updated.</span></span> <span data-ttu-id="70647-121">Se una relazione definita rigida viene modificata, in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] verrà generato un errore durante l'aggiornamento incrementale.</span><span class="sxs-lookup"><span data-stu-id="70647-121">If a relationship that is defined as rigid actually changes, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generates an error during incremental processing.</span></span> <span data-ttu-id="70647-122">L'impostazione corretta delle relazioni e delle rispettive proprietà determina un miglioramento delle prestazioni durante l'esecuzione di query e i processi di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="70647-122">Specifying the appropriate relationships and relationship properties increases query and processing performance.</span></span>|  
|<span data-ttu-id="70647-123">Visible</span><span class="sxs-lookup"><span data-stu-id="70647-123">Visible</span></span>|<span data-ttu-id="70647-124">Determina la visibilità della relazione tra attributi.</span><span class="sxs-lookup"><span data-stu-id="70647-124">Determines the visibility of the attribute relationship.</span></span> <span data-ttu-id="70647-125">Il valore è True o False.</span><span class="sxs-lookup"><span data-stu-id="70647-125">Values are True or False.</span></span> <span data-ttu-id="70647-126">Il valore predefinito è true.</span><span class="sxs-lookup"><span data-stu-id="70647-126">Default is True.</span></span>|  
  
  
