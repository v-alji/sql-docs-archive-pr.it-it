---
title: Elemento TuningOptions (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningOptions element
ms.assetid: 58a22ba1-8e03-411f-bd46-85e4540f217a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fab1c55c9d036424142b2692e8335ea65c22340
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720622"
---
# <a name="tuningoptions-element-dta"></a><span data-ttu-id="d0dd8-102">Elemento TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="d0dd8-102">TuningOptions Element (DTA)</span></span>
  <span data-ttu-id="d0dd8-103">Contiene le opzioni di ottimizzazione per una specifica sessione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-103">Contains the tuning options for a specific tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0dd8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0dd8-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="d0dd8-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="d0dd8-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="d0dd8-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="d0dd8-106">Characteristic</span></span>|<span data-ttu-id="d0dd8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0dd8-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d0dd8-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="d0dd8-108">**Data type and length**</span></span>|<span data-ttu-id="d0dd8-109">No.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-109">None.</span></span>|  
|<span data-ttu-id="d0dd8-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="d0dd8-110">**Default value**</span></span>|<span data-ttu-id="d0dd8-111">No.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-111">None.</span></span>|  
|<span data-ttu-id="d0dd8-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="d0dd8-112">**Occurrence**</span></span>|<span data-ttu-id="d0dd8-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-113">Optional.</span></span> <span data-ttu-id="d0dd8-114">Se utilizzato, può essere utilizzato una sola volta per ogni elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-114">If used, can only be used once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="d0dd8-115">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="d0dd8-115">Element Relationships</span></span>  
  
|<span data-ttu-id="d0dd8-116">Relazione</span><span class="sxs-lookup"><span data-stu-id="d0dd8-116">Relationship</span></span>|<span data-ttu-id="d0dd8-117">Elementi</span><span class="sxs-lookup"><span data-stu-id="d0dd8-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="d0dd8-118">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="d0dd8-118">**Parent element**</span></span>|[<span data-ttu-id="d0dd8-119">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-119">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="d0dd8-120">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="d0dd8-120">**Child elements**</span></span>|<span data-ttu-id="d0dd8-121">Elemento `ReportSet`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-121">`ReportSet` element.</span></span> <span data-ttu-id="d0dd8-122">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d0dd8-122">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="d0dd8-123">Elemento `TuningLogTable`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-123">`TuningLogTable` element.</span></span> <span data-ttu-id="d0dd8-124">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d0dd8-124">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="d0dd8-125">Elemento `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-125">`NumberOfEvents` element.</span></span> <span data-ttu-id="d0dd8-126">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d0dd8-126">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> [<span data-ttu-id="d0dd8-127">Elemento TuningTimeInMin &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-127">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)<br /><br /> [<span data-ttu-id="d0dd8-128">Elemento StorageBoundInMB &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-128">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)<br /><br /> <span data-ttu-id="d0dd8-129">Elemento `MaxKeyColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-129">`MaxKeyColumnsInIndex` element.</span></span> <span data-ttu-id="d0dd8-130">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d0dd8-130">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="d0dd8-131">Elemento `MaxColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-131">`MaxColumnsInIndex` element.</span></span> <span data-ttu-id="d0dd8-132">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d0dd8-132">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="d0dd8-133">Elemento `MinPercentageImprovement`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-133">`MinPercentageImprovement` element.</span></span> <span data-ttu-id="d0dd8-134">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100)</span><span class="sxs-lookup"><span data-stu-id="d0dd8-134">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100)</span></span><br /><br /> [<span data-ttu-id="d0dd8-135">Elemento TestServer &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-135">TestServer Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="d0dd8-136">Elemento FeatureSet &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-136">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="d0dd8-137">Elemento Partitioning &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-137">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> [<span data-ttu-id="d0dd8-138">Elemento DropOnlyMode &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-138">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)<br /><br /> [<span data-ttu-id="d0dd8-139">Elemento KeepExisting &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-139">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)<br /><br /> [<span data-ttu-id="d0dd8-140">Elemento OnlineIndexOperation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-140">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)<br /><br /> [<span data-ttu-id="d0dd8-141">Elemento DatabaseToConnect &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-141">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)<br /><br /> <span data-ttu-id="d0dd8-142">Elemento `IgnoreConstantsInWorkload`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-142">`IgnoreConstantsInWorkload` element.</span></span> <span data-ttu-id="d0dd8-143">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d0dd8-143">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="d0dd8-144">Elemento `RetainShellDB`.</span><span class="sxs-lookup"><span data-stu-id="d0dd8-144">`RetainShellDB` element.</span></span> <span data-ttu-id="d0dd8-145">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="d0dd8-145">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0dd8-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0dd8-146">Example</span></span>  
 <span data-ttu-id="d0dd8-147">Per esempi dell' `TuningOptions` elemento, vedere esempi di [file di Input XML &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="d0dd8-147">For examples of the `TuningOptions` element, see the [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0dd8-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0dd8-148">See Also</span></span>  
 [<span data-ttu-id="d0dd8-149">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="d0dd8-149">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
