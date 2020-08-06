---
title: Elemento Table per schema (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Table element [DTA]
ms.assetid: a59e8319-05d1-47f3-af39-7d970ab8e7dc
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd444b1da99b22e0259dc1f50818c1763b7052ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720652"
---
# <a name="table-element-for-schema-dta"></a><span data-ttu-id="e04b9-102">Elemento Table per Schema (DTA)</span><span class="sxs-lookup"><span data-stu-id="e04b9-102">Table Element for Schema (DTA)</span></span>
  <span data-ttu-id="e04b9-103">Specifica la tabella per l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="e04b9-103">Specifies the table for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e04b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e04b9-104">Syntax</span></span>  
  
```  
  
<Schema>  
...code removed here...  
    <Table>...</Table>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="e04b9-105">Attributi elemento</span><span class="sxs-lookup"><span data-stu-id="e04b9-105">Element Attributes</span></span>  
  
|<span data-ttu-id="e04b9-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="e04b9-106">Attribute</span></span>|<span data-ttu-id="e04b9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e04b9-107">Description</span></span>|  
|---------------|-----------------|  
|`NumberOfRows`|<span data-ttu-id="e04b9-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e04b9-108">Optional.</span></span> <span data-ttu-id="e04b9-109">Valore intero che consente la simulazione di tabelle di diverse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e04b9-109">Integer that allows you to simulate tables of different sizes.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="e04b9-110">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="e04b9-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="e04b9-111">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="e04b9-111">Characteristic</span></span>|<span data-ttu-id="e04b9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e04b9-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e04b9-113">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="e04b9-113">**Data type and length**</span></span>|<span data-ttu-id="e04b9-114">**string**, tra 1 e 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="e04b9-114">**string**, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="e04b9-115">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="e04b9-115">**Default value**</span></span>|<span data-ttu-id="e04b9-116">No.</span><span class="sxs-lookup"><span data-stu-id="e04b9-116">None.</span></span>|  
|<span data-ttu-id="e04b9-117">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="e04b9-117">**Occurrence**</span></span>|<span data-ttu-id="e04b9-118">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e04b9-118">Optional.</span></span> <span data-ttu-id="e04b9-119">Elenca tutte le tabelle appropriate per il carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e04b9-119">List as many tables as appropriate for your workload.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="e04b9-120">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="e04b9-120">Element Relationships</span></span>  
  
|<span data-ttu-id="e04b9-121">Relazione</span><span class="sxs-lookup"><span data-stu-id="e04b9-121">Relationship</span></span>|<span data-ttu-id="e04b9-122">Elementi</span><span class="sxs-lookup"><span data-stu-id="e04b9-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="e04b9-123">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="e04b9-123">**Parent element**</span></span>|[<span data-ttu-id="e04b9-124">Elemento Schema per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="e04b9-124">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="e04b9-125">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="e04b9-125">**Child elements**</span></span>|[<span data-ttu-id="e04b9-126">Elemento Name per Table &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="e04b9-126">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="e04b9-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e04b9-127">Remarks</span></span>  
 <span data-ttu-id="e04b9-128">Se non si specifica un elemento `Table`, l'Ottimizzazione guidata motore di database considererà ottimizzabili tutte le tabelle contenute nel database specificato.</span><span class="sxs-lookup"><span data-stu-id="e04b9-128">If you do not specify a `Table` element, Database Engine Tuning Advisor will assume all tables on the specified database can be tuned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e04b9-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="e04b9-129">Example</span></span>  
 <span data-ttu-id="e04b9-130">Per un esempio d'uso, vedere [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="e04b9-130">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04b9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e04b9-131">See Also</span></span>  
 [<span data-ttu-id="e04b9-132">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="e04b9-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
