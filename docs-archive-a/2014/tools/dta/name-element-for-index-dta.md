---
title: Elemento Name per index (DTA) | Microsoft Docs
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
ms.assetid: 2300e9cf-f0a8-49e6-b1f5-45ffe03ccb5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a878923a3d483fae5ad6b55421a2b286f15ceb29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724303"
---
# <a name="name-element-for-index-dta"></a><span data-ttu-id="47ae3-102">Elemento Name per Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="47ae3-102">Name Element for Index (DTA)</span></span>
  <span data-ttu-id="47ae3-103">Specifica un nome di un indice nella configurazione specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="47ae3-103">Specifies a name for an index in the user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ae3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47ae3-104">Syntax</span></span>  
  
```  
  
<Create>  
    <Index>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="47ae3-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="47ae3-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="47ae3-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="47ae3-106">Characteristic</span></span>|<span data-ttu-id="47ae3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47ae3-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="47ae3-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="47ae3-108">**Data type and length**</span></span>|<span data-ttu-id="47ae3-109">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="47ae3-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="47ae3-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="47ae3-110">**Default value**</span></span>|<span data-ttu-id="47ae3-111">No.</span><span class="sxs-lookup"><span data-stu-id="47ae3-111">None.</span></span>|  
|<span data-ttu-id="47ae3-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="47ae3-112">**Occurrence**</span></span>|<span data-ttu-id="47ae3-113">Obbligatorio una sola volta per ogni elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="47ae3-113">Required once for each `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="47ae3-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="47ae3-114">Element Relationships</span></span>  
  
|<span data-ttu-id="47ae3-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="47ae3-115">Relationship</span></span>|<span data-ttu-id="47ae3-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="47ae3-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="47ae3-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="47ae3-117">**Parent element**</span></span>|[<span data-ttu-id="47ae3-118">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="47ae3-118">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="47ae3-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="47ae3-119">**Child elements**</span></span>|<span data-ttu-id="47ae3-120">No.</span><span class="sxs-lookup"><span data-stu-id="47ae3-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="47ae3-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="47ae3-121">Example</span></span>  
 <span data-ttu-id="47ae3-122">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="47ae3-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ae3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47ae3-123">See Also</span></span>  
 [<span data-ttu-id="47ae3-124">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="47ae3-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
