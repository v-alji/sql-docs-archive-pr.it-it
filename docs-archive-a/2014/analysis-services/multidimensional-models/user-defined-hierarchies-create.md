---
title: Creare gerarchie definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined hierarchies [Analysis Services]
ms.assetid: 16715b85-0630-4a8e-99b0-c0d213cade26
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e870a2b20125132342db1845689b7c2481d623
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715771"
---
# <a name="create-user-defined-hierarchies"></a><span data-ttu-id="eb89c-102">Creare gerarchie definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="eb89c-102">Create User-Defined Hierarchies</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="eb89c-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]consente di creare gerarchie definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="eb89c-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lets you create user-defined hierarchies.</span></span> <span data-ttu-id="eb89c-104">Una gerarchia è una raccolta di livelli basata su attributi.</span><span class="sxs-lookup"><span data-stu-id="eb89c-104">A hierarchy is a collection of levels based on attributes.</span></span> <span data-ttu-id="eb89c-105">Ad esempio, la gerarchia temporale potrebbe includere i livelli Anno, Trimestre, Mese, Settimana e Giorno.</span><span class="sxs-lookup"><span data-stu-id="eb89c-105">For example, a time hierarchy might contain the Year, Quarter, Month, Week, and Day levels.</span></span> <span data-ttu-id="eb89c-106">In alcune gerarchie, ogni attributo del membro comprende in modo univoco l'attributo del membro che si trova ad un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="eb89c-106">In some hierarchies, each member attribute uniquely implies the member attribute above it.</span></span> <span data-ttu-id="eb89c-107">A questo talvolta si fa riferimento come gerarchia naturale.</span><span class="sxs-lookup"><span data-stu-id="eb89c-107">This is sometimes referred to as a natural hierarchy.</span></span> <span data-ttu-id="eb89c-108">Una gerarchia può essere utilizzata dagli utenti finali per esplorare i dati del cubo.</span><span class="sxs-lookup"><span data-stu-id="eb89c-108">A hierarchy can be used by end users to browse cube data.</span></span> <span data-ttu-id="eb89c-109">Definire gerarchie utilizzando il riquadro Gerarchie di Progettazione Dimensioni in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb89c-109">Define hierarchies by using the Hierarchies pane of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="eb89c-110">Quando si crea una gerarchia definita dall'utente, è possibile che la gerarchia sia *incompleta*.</span><span class="sxs-lookup"><span data-stu-id="eb89c-110">When you create a user-defined hierarchy, the hierarchy might become *ragged*.</span></span> <span data-ttu-id="eb89c-111">In una gerarchia incompleta, il membro padre logico di almeno un membro non si trova nel livello immediatamente superiore rispetto al membro stesso.</span><span class="sxs-lookup"><span data-stu-id="eb89c-111">A ragged hierarchy is where the logical parent member of at least one member is not in the level immediately above the member.</span></span> <span data-ttu-id="eb89c-112">Se si ha una gerarchia incompleta, ci sono impostazioni che controllano se i membri mancanti sono visibili e come visualizzare i membri mancanti.</span><span class="sxs-lookup"><span data-stu-id="eb89c-112">If you have a ragged hierarchy, there are settings that control whether the missing members are visible and how to display the missing members.</span></span> <span data-ttu-id="eb89c-113">Per altre informazioni, vedere [Gerarchie incomplete](user-defined-hierarchies-ragged-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="eb89c-113">For more information, see [Ragged Hierarchies](user-defined-hierarchies-ragged-hierarchies.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb89c-114">Per altre informazioni su problemi di prestazioni legati alla progettazione e alla configurazione delle gerarchie definite dall'utente, vedere la [Guida alle prestazioni di SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="eb89c-114">For more information about performance issues related to the design and configuration of user-defined hierarchies, see the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb89c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb89c-115">See Also</span></span>  
 <span data-ttu-id="eb89c-116">[Proprietà gerarchia utente](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span><span class="sxs-lookup"><span data-stu-id="eb89c-116">[User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span></span>  
 <span data-ttu-id="eb89c-117">[Proprietà livello &#91;pavimentate su&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span><span class="sxs-lookup"><span data-stu-id="eb89c-117">[Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span></span>  
 [<span data-ttu-id="eb89c-118">Gerarchia padre-figlio</span><span class="sxs-lookup"><span data-stu-id="eb89c-118">Parent-Child Hierarchy</span></span>](parent-child-dimension.md)  
  
  
