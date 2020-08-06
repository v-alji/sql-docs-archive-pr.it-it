---
title: Elemento OnlineIndexOperation (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- OnlineIndexOperation element
ms.assetid: 7c5614cd-09aa-4a59-9591-347aa7d36473
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48943c1b31d7a0a24ae939050d44494476e50034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635308"
---
# <a name="onlineindexoperation-element-dta"></a><span data-ttu-id="a695b-102">Elemento OnlineIndexOperation (DTA)</span><span class="sxs-lookup"><span data-stu-id="a695b-102">OnlineIndexOperation Element (DTA)</span></span>
  <span data-ttu-id="a695b-103">Specifica se è possibile creare online gli indici, le viste indicizzate o le partizioni consigliate da Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="a695b-103">Specifies whether the indexes, indexed views, or partitions that Database Engine Tuning Advisor recommends can be created online.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a695b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a695b-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <OnlineIndexOperation>...</OnlineIndexOperation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="a695b-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="a695b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="a695b-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="a695b-106">Characteristic</span></span>|<span data-ttu-id="a695b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a695b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a695b-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="a695b-108">**Data type and length**</span></span>|<span data-ttu-id="a695b-109">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="a695b-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="a695b-110">**Valori consentiti**</span><span class="sxs-lookup"><span data-stu-id="a695b-110">**Allowed values**</span></span>|<span data-ttu-id="a695b-111">**OFF**</span><span class="sxs-lookup"><span data-stu-id="a695b-111">**OFF**</span></span><br /> <span data-ttu-id="a695b-112">Le strutture di progettazione fisica indicate non possono essere create online.</span><span class="sxs-lookup"><span data-stu-id="a695b-112">No recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="a695b-113">**ON**</span><span class="sxs-lookup"><span data-stu-id="a695b-113">**ON**</span></span><br /> <span data-ttu-id="a695b-114">Tutte le strutture di progettazione fisica indicate possono essere create online.</span><span class="sxs-lookup"><span data-stu-id="a695b-114">All recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="a695b-115">**MIXED**</span><span class="sxs-lookup"><span data-stu-id="a695b-115">**MIXED**</span></span><br /> <span data-ttu-id="a695b-116">Ottimizzazione guidata motore di database indica le strutture di progettazione fisica che possono essere create online quando possibile.</span><span class="sxs-lookup"><span data-stu-id="a695b-116">Database Engine Tuning Advisor attempts to recommend physical design structures that can be created online when possible.</span></span><br /><br /> <span data-ttu-id="a695b-117">Con questo elemento utilizzare solo uno di questi valori.</span><span class="sxs-lookup"><span data-stu-id="a695b-117">Use one of these values with this element.</span></span> <span data-ttu-id="a695b-118">Se si creano indici online, la parola chiave **ONLINE = ON** viene aggiunta alla relativa definizione di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a695b-118">If indexes are created online, the keyword **ONLINE = ON** is appended to its object definition.</span></span>|  
|<span data-ttu-id="a695b-119">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="a695b-119">**Default value**</span></span>|<span data-ttu-id="a695b-120">No.</span><span class="sxs-lookup"><span data-stu-id="a695b-120">None.</span></span>|  
|<span data-ttu-id="a695b-121">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="a695b-121">**Occurrence**</span></span>|<span data-ttu-id="a695b-122">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a695b-122">Optional.</span></span> <span data-ttu-id="a695b-123">Se utilizzato, può essere utilizzato una sola volta per l'elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="a695b-123">If used, can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="a695b-124">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="a695b-124">Element Relationships</span></span>  
  
|<span data-ttu-id="a695b-125">Relazione</span><span class="sxs-lookup"><span data-stu-id="a695b-125">Relationship</span></span>|<span data-ttu-id="a695b-126">Elementi</span><span class="sxs-lookup"><span data-stu-id="a695b-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="a695b-127">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="a695b-127">**Parent element**</span></span>|[<span data-ttu-id="a695b-128">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a695b-128">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="a695b-129">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="a695b-129">**Child elements**</span></span>|<span data-ttu-id="a695b-130">No.</span><span class="sxs-lookup"><span data-stu-id="a695b-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a695b-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="a695b-131">Example</span></span>  
 <span data-ttu-id="a695b-132">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML semplice &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a695b-132">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a695b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a695b-133">See Also</span></span>  
 [<span data-ttu-id="a695b-134">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="a695b-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
