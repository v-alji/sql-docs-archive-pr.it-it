---
title: Elemento KeepExisting (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: cde9b3091b75f55e4b9c79137853fbd7d4e0daf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719230"
---
# <a name="keepexisting-element-dta"></a><span data-ttu-id="23930-102">Elemento KeepExisting (DTA)</span><span class="sxs-lookup"><span data-stu-id="23930-102">KeepExisting Element (DTA)</span></span>
  <span data-ttu-id="23930-103">Specifica le strutture di progettazione fisica (indici, viste indicizzate o partizionamento) che Ottimizzazione guidata motore di database deve mantenere quando genera l'indicazione.</span><span class="sxs-lookup"><span data-stu-id="23930-103">Specifies the physical design structures (indexes, indexed views, or partitioning) that Database Engine Tuning Advisor must retain when generating its recommendation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23930-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23930-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="23930-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="23930-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="23930-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="23930-106">Characteristic</span></span>|<span data-ttu-id="23930-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23930-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="23930-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="23930-108">**Data type and length**</span></span>|<span data-ttu-id="23930-109">`string`, limite della lunghezza imposto dal server.</span><span class="sxs-lookup"><span data-stu-id="23930-109">`string`, length limit enforced by the server.</span></span>|  
|<span data-ttu-id="23930-110">**Valori consentiti**</span><span class="sxs-lookup"><span data-stu-id="23930-110">**Allowed values**</span></span>|<span data-ttu-id="23930-111">**NONE**</span><span class="sxs-lookup"><span data-stu-id="23930-111">**NONE**</span></span><br /> <span data-ttu-id="23930-112">Nessuna struttura esistente.</span><span class="sxs-lookup"><span data-stu-id="23930-112">No existing structures.</span></span><br /><br /> <span data-ttu-id="23930-113">**ALL**</span><span class="sxs-lookup"><span data-stu-id="23930-113">**ALL**</span></span><br /> <span data-ttu-id="23930-114">Tutte le strutture esistenti.</span><span class="sxs-lookup"><span data-stu-id="23930-114">All existing structures.</span></span><br /><br /> <span data-ttu-id="23930-115">**ALIGNED**</span><span class="sxs-lookup"><span data-stu-id="23930-115">**ALIGNED**</span></span><br /> <span data-ttu-id="23930-116">Tutte le strutture con partizionamento allineato.</span><span class="sxs-lookup"><span data-stu-id="23930-116">All partition-aligned structures.</span></span><br /><br /> <span data-ttu-id="23930-117">**CL_IDX**</span><span class="sxs-lookup"><span data-stu-id="23930-117">**CL_IDX**</span></span><br /> <span data-ttu-id="23930-118">Tutti gli indici cluster nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="23930-118">All clustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="23930-119">**IDX**</span><span class="sxs-lookup"><span data-stu-id="23930-119">**IDX**</span></span><br /> <span data-ttu-id="23930-120">Tutti gli indici cluster e non cluster nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="23930-120">All clustered and nonclustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="23930-121">Utilizzare solo uno dei valori seguenti con questo elemento.</span><span class="sxs-lookup"><span data-stu-id="23930-121">Use only one of these values with this element.</span></span>|  
|<span data-ttu-id="23930-122">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="23930-122">**Default value**</span></span>|<span data-ttu-id="23930-123">No.</span><span class="sxs-lookup"><span data-stu-id="23930-123">None.</span></span>|  
|<span data-ttu-id="23930-124">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="23930-124">**Occurrence**</span></span>|<span data-ttu-id="23930-125">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="23930-125">Optional.</span></span> <span data-ttu-id="23930-126">Può essere utilizzato una sola volta per ogni elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="23930-126">Can use only once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="23930-127">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="23930-127">Element Relationships</span></span>  
  
|<span data-ttu-id="23930-128">Relazione</span><span class="sxs-lookup"><span data-stu-id="23930-128">Relationship</span></span>|<span data-ttu-id="23930-129">Elementi</span><span class="sxs-lookup"><span data-stu-id="23930-129">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="23930-130">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="23930-130">**Parent element**</span></span>|[<span data-ttu-id="23930-131">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="23930-131">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="23930-132">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="23930-132">**Child elements**</span></span>|<span data-ttu-id="23930-133">No.</span><span class="sxs-lookup"><span data-stu-id="23930-133">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23930-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="23930-134">Example</span></span>  
 <span data-ttu-id="23930-135">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML semplice &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="23930-135">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23930-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23930-136">See Also</span></span>  
 [<span data-ttu-id="23930-137">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="23930-137">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
