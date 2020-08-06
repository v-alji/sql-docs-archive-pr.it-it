---
title: Elemento TuningTimeInMin (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningTimeInMin element
ms.assetid: 4973d9ac-20fd-4ac3-bc9f-5d60e39fdb7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4dae3fe4e9ac3126f43ec017c34d2bc548fda6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720621"
---
# <a name="tuningtimeinmin-element-dta"></a><span data-ttu-id="27278-102">Elemento TuningTimeInMin (DTA)</span><span class="sxs-lookup"><span data-stu-id="27278-102">TuningTimeInMin Element (DTA)</span></span>
  <span data-ttu-id="27278-103">Specifica la lunghezza massima di una sessione di ottimizzazione espressa in minuti.</span><span class="sxs-lookup"><span data-stu-id="27278-103">Specifies the maximum length of a tuning session in minutes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27278-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27278-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <TuningTimeInMin>...</TuningTimeInMin>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="27278-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="27278-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="27278-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="27278-106">Characteristic</span></span>|<span data-ttu-id="27278-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27278-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="27278-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="27278-108">**Data type and length**</span></span>|<span data-ttu-id="27278-109">`unsignedInt`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="27278-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="27278-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="27278-110">**Default value**</span></span>|<span data-ttu-id="27278-111">480 minuti (8 ore).</span><span class="sxs-lookup"><span data-stu-id="27278-111">480 minutes (8 hours).</span></span>|  
|<span data-ttu-id="27278-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="27278-112">**Occurrence**</span></span>|<span data-ttu-id="27278-113">Obbligatorio a meno che non sia stato specificato un valore per l'elemento `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="27278-113">Required unless a value has been specified for the `NumberOfEvents` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="27278-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="27278-114">Element Relationships</span></span>  
  
|<span data-ttu-id="27278-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="27278-115">Relationship</span></span>|<span data-ttu-id="27278-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="27278-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="27278-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="27278-117">**Parent element**</span></span>|[<span data-ttu-id="27278-118">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="27278-118">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="27278-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="27278-119">**Child elements**</span></span>|<span data-ttu-id="27278-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="27278-120">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27278-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="27278-121">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="27278-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27278-122">Description</span></span>  
 <span data-ttu-id="27278-123">Nell'esempio di codice seguente viene illustrato come impostare 12 ore come tempo di ottimizzazione massimo:</span><span class="sxs-lookup"><span data-stu-id="27278-123">The following code example shows how to set 12 hours as the maximum tuning time:</span></span>  
  
## <a name="code"></a><span data-ttu-id="27278-124">Codice</span><span class="sxs-lookup"><span data-stu-id="27278-124">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <TuningTimeInMin>720</TuningTimeInMin>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27278-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27278-125">See Also</span></span>  
 [<span data-ttu-id="27278-126">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="27278-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
