---
title: Elemento Configuration (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Configuration element
ms.assetid: 1478e56f-57c4-4441-bac9-1ac91453839b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d11938d9a9a694f994a3ea977022a393cbae23d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711359"
---
# <a name="configuration-element-dta"></a><span data-ttu-id="56cf0-102">Elemento Configuration (DTA)</span><span class="sxs-lookup"><span data-stu-id="56cf0-102">Configuration Element (DTA)</span></span>
  <span data-ttu-id="56cf0-103">Definisce una configurazione specificata dall'utente costituita da strutture di progettazione fisica esistenti e ipotetiche da analizzare in Ottimizzazione guidata motore di database durante l'ottimizzazione di un carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="56cf0-103">Specifies a user-specified configuration consisting of existing and hypothetical physical design structures for the Database Engine Tuning Advisor to analyze when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56cf0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56cf0-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>...</Server>  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions  
    <Configuration [SpecificationMode="Relative" | "Absolute"]>  
    ...code removed here...  
    </Configuration>  
</DTAInput>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="56cf0-105">Attributi elemento</span><span class="sxs-lookup"><span data-stu-id="56cf0-105">Element Attributes</span></span>  
  
|<span data-ttu-id="56cf0-106">Attributo di configurazione</span><span class="sxs-lookup"><span data-stu-id="56cf0-106">Configuration Attribute</span></span>|<span data-ttu-id="56cf0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56cf0-107">Description</span></span>|  
|-----------------------------|-----------------|  
|`SpecificationMode`|<span data-ttu-id="56cf0-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="56cf0-108">Optional.</span></span> <span data-ttu-id="56cf0-109">Indica se Ottimizzazione guidata motore di database deve analizzare la configurazione specificata in relazione alla configurazione esistente corrente o come configurazione autonoma completamente nuova.</span><span class="sxs-lookup"><span data-stu-id="56cf0-109">Specifies whether Database Engine Tuning Advisor should analyze the specified configuration in relation to the current existing configuration, or as a completely new, standalone one.</span></span> <span data-ttu-id="56cf0-110">Usare un tipo di dati **string** per specificare questo attributo con uno dei valori consentiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="56cf0-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="56cf0-111">`Relative`:</span><span class="sxs-lookup"><span data-stu-id="56cf0-111">`Relative`:</span></span> <br />                  <span data-ttu-id="56cf0-112">Valuta la configurazione specificata in relazione alla configurazione esistente corrente delle strutture di progettazione fisica (indici, viste indicizzate, partizionamento) nel database sottoposto a ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="56cf0-112">Evaluates the specified configuration in relation to the current existing configuration of physical design structures (indexes, indexed views, partitioning) in the database that is being tuned.</span></span> <span data-ttu-id="56cf0-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="56cf0-113">For example:</span></span> <br />`<Configuration SpecificationMode="Relative">`<br /><br /> <span data-ttu-id="56cf0-114">`Absolute`:</span><span class="sxs-lookup"><span data-stu-id="56cf0-114">`Absolute`:</span></span> <br />                  <span data-ttu-id="56cf0-115">Valuta la configurazione specificata come configurazione autonoma.</span><span class="sxs-lookup"><span data-stu-id="56cf0-115">Evaluates the specified configuration as a standalone configuration.</span></span> <span data-ttu-id="56cf0-116">Se viene specificato Absolute, Ottimizzazione guidata motore di database non prende in considerazione la configurazione esistente.</span><span class="sxs-lookup"><span data-stu-id="56cf0-116">When Absolute is specified, Database Engine Tuning Advisor does not consider the existing configuration.</span></span> <span data-ttu-id="56cf0-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="56cf0-117">For example:</span></span><br />`<Configuration SpecificationMode="Absolute">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="56cf0-118">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="56cf0-118">Element Characteristics</span></span>  
  
|<span data-ttu-id="56cf0-119">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="56cf0-119">Characteristic</span></span>|<span data-ttu-id="56cf0-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56cf0-120">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="56cf0-121">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="56cf0-121">**Data type and length**</span></span>|<span data-ttu-id="56cf0-122">No.</span><span class="sxs-lookup"><span data-stu-id="56cf0-122">None.</span></span>|  
|<span data-ttu-id="56cf0-123">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="56cf0-123">**Default value**</span></span>|<span data-ttu-id="56cf0-124">No.</span><span class="sxs-lookup"><span data-stu-id="56cf0-124">None.</span></span>|  
|<span data-ttu-id="56cf0-125">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="56cf0-125">**Occurrence**</span></span>|<span data-ttu-id="56cf0-126">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="56cf0-126">Optional.</span></span> <span data-ttu-id="56cf0-127">È possibile utilizzarlo una volta per ogni elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="56cf0-127">Can use once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="56cf0-128">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="56cf0-128">Element Relationships</span></span>  
  
|<span data-ttu-id="56cf0-129">Relazione</span><span class="sxs-lookup"><span data-stu-id="56cf0-129">Relationship</span></span>|<span data-ttu-id="56cf0-130">Elementi</span><span class="sxs-lookup"><span data-stu-id="56cf0-130">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="56cf0-131">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="56cf0-131">**Parent element**</span></span>|[<span data-ttu-id="56cf0-132">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="56cf0-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="56cf0-133">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="56cf0-133">**Child elements**</span></span>|[<span data-ttu-id="56cf0-134">Elemento Server per Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="56cf0-134">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="56cf0-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="56cf0-135">Example</span></span>  
 <span data-ttu-id="56cf0-136">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="56cf0-136">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cf0-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56cf0-137">See Also</span></span>  
 [<span data-ttu-id="56cf0-138">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="56cf0-138">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
