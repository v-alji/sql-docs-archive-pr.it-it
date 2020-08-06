---
title: Elemento Name per schema (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 014e4854-fed2-454b-8557-5f7c5bb6b17a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 678a6d58b35b25be2aed6d91fcae7ceb2640bdcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719187"
---
# <a name="name-element-for-schema-dta"></a><span data-ttu-id="948fa-102">Elemento Name per Schema (DTA)</span><span class="sxs-lookup"><span data-stu-id="948fa-102">Name Element for Schema (DTA)</span></span>
  <span data-ttu-id="948fa-103">Contiene il nome dello schema.</span><span class="sxs-lookup"><span data-stu-id="948fa-103">Contains name of the schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="948fa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="948fa-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here  
    <Schema>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="948fa-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="948fa-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="948fa-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="948fa-106">Characteristic</span></span>|<span data-ttu-id="948fa-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="948fa-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="948fa-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="948fa-108">**Data type and length**</span></span>|<span data-ttu-id="948fa-109">`string`, tra 1 e 255 caratteri</span><span class="sxs-lookup"><span data-stu-id="948fa-109">`string`, between 1 and 255 characters</span></span>|  
|<span data-ttu-id="948fa-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="948fa-110">**Default value**</span></span>|<span data-ttu-id="948fa-111">No.</span><span class="sxs-lookup"><span data-stu-id="948fa-111">None.</span></span>|  
|<span data-ttu-id="948fa-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="948fa-112">**Occurrence**</span></span>|<span data-ttu-id="948fa-113">Obbligatorio una sola volta per elemento **Schema** .</span><span class="sxs-lookup"><span data-stu-id="948fa-113">Required once per **Schema** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="948fa-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="948fa-114">Element Relationships</span></span>  
  
|<span data-ttu-id="948fa-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="948fa-115">Relationship</span></span>|<span data-ttu-id="948fa-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="948fa-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="948fa-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="948fa-117">**Parent element**</span></span>|[<span data-ttu-id="948fa-118">Elemento Schema per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="948fa-118">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="948fa-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="948fa-119">**Child elements**</span></span>|<span data-ttu-id="948fa-120">No.</span><span class="sxs-lookup"><span data-stu-id="948fa-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="948fa-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="948fa-121">Example</span></span>  
 <span data-ttu-id="948fa-122">Per un esempio di utilizzo di questo elemento, vedere [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="948fa-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="948fa-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="948fa-123">See Also</span></span>  
 [<span data-ttu-id="948fa-124">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="948fa-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
