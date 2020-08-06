---
title: Esaminare l'utilizzo delle aggregazioni (progettazione guidata aggregazioni) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.aggregationdesignwizard.reviewusage.f1
ms.assetid: 107ee872-3df2-4931-b56c-af11e38f6745
author: minewiskan
ms.author: owend
ms.openlocfilehash: afbb02dae64f3f7ebd57065c3ff8a7d1e202dcf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625636"
---
# <a name="review-aggregation-usage-aggregation-design-wizard"></a><span data-ttu-id="1ac98-102">Controlla utilizzo aggregazioni (Progettazione guidata aggregazioni)</span><span class="sxs-lookup"><span data-stu-id="1ac98-102">Review Aggregation Usage (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="1ac98-103">Utilizzare la pagina **Controlla utilizzo aggregazioni** per configurare le impostazioni di utilizzo delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="1ac98-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1ac98-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1ac98-104">Options</span></span>  
 <span data-ttu-id="1ac98-105">**Default**</span><span class="sxs-lookup"><span data-stu-id="1ac98-105">**Default**</span></span>  
 <span data-ttu-id="1ac98-106">Selezionare per impostare l'impostazione di utilizzo delle aggregazioni per l'attributo su Predefinito.</span><span class="sxs-lookup"><span data-stu-id="1ac98-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="1ac98-107">Con questa impostazione, la progettazione applica una regola predefinita in base al tipo di attributo e di dimensione.</span><span class="sxs-lookup"><span data-stu-id="1ac98-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 `Full`  
 <span data-ttu-id="1ac98-108">Selezionare per impostare l'impostazione di utilizzo delle aggregazioni per l'attributo in `Full`.</span><span class="sxs-lookup"><span data-stu-id="1ac98-108">Select to set the aggregation usage setting for the attribute to `Full`.</span></span> <span data-ttu-id="1ac98-109">Con questa impostazione, ogni aggregazione per il cubo deve includere questo attributo o un attributo correlato che è a un livello inferiore nella catena dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="1ac98-109">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="1ac98-110">Evitare l'impostazione di utilizzo aggregazioni `Full` quando un attributo contiene molti membri.</span><span class="sxs-lookup"><span data-stu-id="1ac98-110">The `Full` aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="1ac98-111">Se specificata per più attributi o attributi che hanno molti membri, questa impostazione potrebbe impedire la progettazione delle aggregazioni a causa delle dimensioni eccessive.</span><span class="sxs-lookup"><span data-stu-id="1ac98-111">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="1ac98-112">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="1ac98-112">**None**</span></span>  
 <span data-ttu-id="1ac98-113">Selezionare per impostare l'impostazione di utilizzo delle aggregazioni per l'attributo in Nessuna.</span><span class="sxs-lookup"><span data-stu-id="1ac98-113">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="1ac98-114">Con questa impostazione nessuna aggregazione del cubo deve includere questo attributo.</span><span class="sxs-lookup"><span data-stu-id="1ac98-114">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 `Unrestricted`  
 <span data-ttu-id="1ac98-115">Selezionare per impostare l'impostazione di utilizzo delle aggregazioni per l'attributo in `Unrestricted`.</span><span class="sxs-lookup"><span data-stu-id="1ac98-115">Select to set the aggregation usage setting for the attribute to `Unrestricted`.</span></span> <span data-ttu-id="1ac98-116">Con questa impostazione non sono inserite restrizioni nella progettazione delle aggregazioni. Tuttavia, l'attributo ancora deve essere valutato per stabilire se è idoneo.</span><span class="sxs-lookup"><span data-stu-id="1ac98-116">By using this setting, no restrictions are put on the aggregation designer; however, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="1ac98-117">**Imposta come predefinito per tutti**</span><span class="sxs-lookup"><span data-stu-id="1ac98-117">**Set All to Default**</span></span>  
 <span data-ttu-id="1ac98-118">Selezionare per impostare le impostazioni  di utilizzo delle aggregazioni per tutti gli attributi su Predefinito.</span><span class="sxs-lookup"><span data-stu-id="1ac98-118">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ac98-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ac98-119">See Also</span></span>  
 <span data-ttu-id="1ac98-120">[Guida sensibile al contesto della progettazione guidata aggregazioni](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1ac98-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="1ac98-121">Procedure guidate di Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="1ac98-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
