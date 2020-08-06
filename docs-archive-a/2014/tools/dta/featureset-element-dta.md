---
title: Elemento Featuret (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d36c28b24a56ef2dcdf69578fb7e8c196306a416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722087"
---
# <a name="featureset-element-dta"></a><span data-ttu-id="41098-102">Elemento FeatureSet (DTA)</span><span class="sxs-lookup"><span data-stu-id="41098-102">FeatureSet Element (DTA)</span></span>
  <span data-ttu-id="41098-103">Contiene le strutture di progettazione fisica, ad esempio indici o viste indicizzate, che dovranno essere utilizzate da Ottimizzazione guidata motore di database durante l'analisi.</span><span class="sxs-lookup"><span data-stu-id="41098-103">Contains the physical design structures (indexes or indexed views) that you would like Database Engine Tuning Advisor to use during analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41098-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41098-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="41098-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="41098-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="41098-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="41098-106">Characteristic</span></span>|<span data-ttu-id="41098-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41098-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="41098-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="41098-108">**Data type and length**</span></span>|<span data-ttu-id="41098-109">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="41098-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="41098-110">**Valori consentiti**</span><span class="sxs-lookup"><span data-stu-id="41098-110">**Allowed values**</span></span>|<span data-ttu-id="41098-111">**IDX_IV**</span><span class="sxs-lookup"><span data-stu-id="41098-111">**IDX_IV**</span></span><br /> <span data-ttu-id="41098-112">Indici e viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="41098-112">Indexes and indexed views.</span></span><br /><br /> <span data-ttu-id="41098-113">**IDX**</span><span class="sxs-lookup"><span data-stu-id="41098-113">**IDX**</span></span><br /> <span data-ttu-id="41098-114">Solo indici.</span><span class="sxs-lookup"><span data-stu-id="41098-114">Indexes only.</span></span><br /><br /> <span data-ttu-id="41098-115">**IV**</span><span class="sxs-lookup"><span data-stu-id="41098-115">**IV**</span></span><br /> <span data-ttu-id="41098-116">Solo viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="41098-116">Indexed views only.</span></span><br /><br /> <span data-ttu-id="41098-117">**NCL_IDX**</span><span class="sxs-lookup"><span data-stu-id="41098-117">**NCL_IDX**</span></span><br /> <span data-ttu-id="41098-118">Solo indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="41098-118">Nonclustered indexes only.</span></span><br /><br /> <span data-ttu-id="41098-119">Con questo elemento utilizzare solo uno di questi valori.</span><span class="sxs-lookup"><span data-stu-id="41098-119">Use one of these values with this element.</span></span>|  
|<span data-ttu-id="41098-120">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="41098-120">**Default value**</span></span>|<span data-ttu-id="41098-121">**IDX**</span><span class="sxs-lookup"><span data-stu-id="41098-121">**IDX**</span></span>|  
|<span data-ttu-id="41098-122">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="41098-122">**Occurrence**</span></span>|<span data-ttu-id="41098-123">Obbligatorio una sola volta per ogni elemento `TuningOptions`, a meno che non venga utilizzato l'elemento `DropOnlyMode`.</span><span class="sxs-lookup"><span data-stu-id="41098-123">Required once for each `TuningOptions` element, unless the `DropOnlyMode` element is used.</span></span> <span data-ttu-id="41098-124">Se viene utilizzato `DropOnlyMode`, non sarà possibile utilizzare `FeatureSet`.</span><span class="sxs-lookup"><span data-stu-id="41098-124">If `DropOnlyMode` is used, you cannot use `FeatureSet`.</span></span> <span data-ttu-id="41098-125">Questi elementi si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="41098-125">These elements are mutually exclusive.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="41098-126">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="41098-126">Element Relationships</span></span>  
  
|<span data-ttu-id="41098-127">Relazione</span><span class="sxs-lookup"><span data-stu-id="41098-127">Relationship</span></span>|<span data-ttu-id="41098-128">Elementi</span><span class="sxs-lookup"><span data-stu-id="41098-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="41098-129">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="41098-129">**Parent element**</span></span>|[<span data-ttu-id="41098-130">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="41098-130">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="41098-131">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="41098-131">**Child elements**</span></span>|<span data-ttu-id="41098-132">No.</span><span class="sxs-lookup"><span data-stu-id="41098-132">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="41098-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="41098-133">Example</span></span>  
 <span data-ttu-id="41098-134">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML semplice &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="41098-134">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41098-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41098-135">See Also</span></span>  
 [<span data-ttu-id="41098-136">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="41098-136">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
