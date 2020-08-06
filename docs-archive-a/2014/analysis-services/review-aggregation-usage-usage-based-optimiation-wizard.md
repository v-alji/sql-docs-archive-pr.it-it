---
title: Esaminare l'utilizzo delle aggregazioni (procedura guidata basata basata sull'utilizzo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.reviewaggregationusage.f1
ms.assetid: 49ce2094-c4dc-4e46-8cef-c17c5db084ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ef9f900e64858515db226d1f9b864874a4ba827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625635"
---
# <a name="review-aggregation-usage-usage-based-optimiation-wizard"></a><span data-ttu-id="19ddf-102">Controlla utilizzo aggregazioni (Ottimizzazione guidata basata sulle statistiche di utilizzo)</span><span class="sxs-lookup"><span data-stu-id="19ddf-102">Review Aggregation Usage (Usage-Based Optimiation Wizard)</span></span>
  <span data-ttu-id="19ddf-103">Utilizzare la pagina **Controlla utilizzo aggregazioni** per configurare le impostazioni di utilizzo delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="19ddf-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="19ddf-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="19ddf-104">Options</span></span>  
 <span data-ttu-id="19ddf-105">**Default**</span><span class="sxs-lookup"><span data-stu-id="19ddf-105">**Default**</span></span>  
 <span data-ttu-id="19ddf-106">Selezionare per impostare l'impostazione di utilizzo delle aggregazioni per l'attributo su Predefinito.</span><span class="sxs-lookup"><span data-stu-id="19ddf-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="19ddf-107">Con questa impostazione, la progettazione applica una regola predefinita in base al tipo di attributo e di dimensione.</span><span class="sxs-lookup"><span data-stu-id="19ddf-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 <span data-ttu-id="19ddf-108">**Completo**</span><span class="sxs-lookup"><span data-stu-id="19ddf-108">**Full**</span></span>  
 <span data-ttu-id="19ddf-109">Selezionare per impostare l'impostazione di utilizzo delle aggregazioni per l'attributo in Completa.</span><span class="sxs-lookup"><span data-stu-id="19ddf-109">Select to set the aggregation usage setting for the attribute to Full.</span></span> <span data-ttu-id="19ddf-110">Con questa impostazione, ogni aggregazione per il cubo deve includere questo attributo o un attributo correlato che è a un livello inferiore nella catena dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="19ddf-110">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="19ddf-111">Evitare l'impostazione di utilizzo aggregazioni Completa quando un attributo contiene molti membri.</span><span class="sxs-lookup"><span data-stu-id="19ddf-111">The Full aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="19ddf-112">Se specificata per più attributi o attributi che hanno molti membri, questa impostazione potrebbe impedire la progettazione delle aggregazioni a causa delle dimensioni eccessive.</span><span class="sxs-lookup"><span data-stu-id="19ddf-112">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="19ddf-113">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="19ddf-113">**None**</span></span>  
 <span data-ttu-id="19ddf-114">Selezionare per impostare l'impostazione di utilizzo delle aggregazioni per l'attributo in Nessuna.</span><span class="sxs-lookup"><span data-stu-id="19ddf-114">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="19ddf-115">Con questa impostazione nessuna aggregazione del cubo deve includere questo attributo.</span><span class="sxs-lookup"><span data-stu-id="19ddf-115">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 <span data-ttu-id="19ddf-116">**Illimitato**</span><span class="sxs-lookup"><span data-stu-id="19ddf-116">**Unrestricted**</span></span>  
 <span data-ttu-id="19ddf-117">Selezionare per impostare l'impostazione di utilizzo delle aggregazioni per l'attributo su Senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="19ddf-117">Select to set the aggregation usage setting for the attribute to Unrestricted.</span></span> <span data-ttu-id="19ddf-118">Con questa impostazione non sono inserite restrizioni nella progettazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="19ddf-118">By using this setting, no restrictions are put on the aggregation designer.</span></span> <span data-ttu-id="19ddf-119">Tuttavia, l'attributo ancora deve essere valutato per stabilire se è idoneo.</span><span class="sxs-lookup"><span data-stu-id="19ddf-119">However, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="19ddf-120">**Imposta come predefinito per tutti**</span><span class="sxs-lookup"><span data-stu-id="19ddf-120">**Set All to Default**</span></span>  
 <span data-ttu-id="19ddf-121">Selezionare per impostare le impostazioni  di utilizzo delle aggregazioni per tutti gli attributi su Predefinito.</span><span class="sxs-lookup"><span data-stu-id="19ddf-121">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ddf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19ddf-122">See Also</span></span>  
 <span data-ttu-id="19ddf-123">[Guida sensibile al contesto della progettazione guidata aggregazioni](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="19ddf-123">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="19ddf-124">Procedure guidate di Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="19ddf-124">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
