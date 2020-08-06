---
title: Elemento filegroup per index (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Filegroup element [DTA]
ms.assetid: 7078d2fb-fa77-44fc-beb3-c095088fcb85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ed8ea723d6c0798b93e16411ee47d6e956c6c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720658"
---
# <a name="filegroup-element-for-index-dta"></a><span data-ttu-id="4b6cb-102">Elemento Filegroup per Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="4b6cb-102">Filegroup Element for Index (DTA)</span></span>
  <span data-ttu-id="4b6cb-103">Specifica il filegroup in cui creare l'indice per una configurazione specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4b6cb-103">Specifies the filegroup on which the index is to be created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b6cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b6cb-104">Syntax</span></span>  
  
```  
  
<Index>  
  <Name>...</Name>  
  <Column>  
    <Name>...</Name>  
  <Filegroup>...</Filegroup>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="4b6cb-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="4b6cb-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="4b6cb-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="4b6cb-106">Characteristic</span></span>|<span data-ttu-id="4b6cb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b6cb-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4b6cb-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="4b6cb-108">**Data type and length**</span></span>|<span data-ttu-id="4b6cb-109">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="4b6cb-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="4b6cb-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="4b6cb-110">**Default value**</span></span>|<span data-ttu-id="4b6cb-111">No.</span><span class="sxs-lookup"><span data-stu-id="4b6cb-111">None.</span></span>|  
|<span data-ttu-id="4b6cb-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="4b6cb-112">**Occurrence**</span></span>|<span data-ttu-id="4b6cb-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="4b6cb-113">Optional.</span></span> <span data-ttu-id="4b6cb-114">È possibile utilizzarlo una volta per ogni elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="4b6cb-114">Can use once for each `Index` element.</span></span> <span data-ttu-id="4b6cb-115">Questo elemento non può essere utilizzato se per l'elemento `PartitionScheme` sono specificati gli elementi `PartitionColumn` e `Index`.</span><span class="sxs-lookup"><span data-stu-id="4b6cb-115">This element cannot be used if the `PartitionScheme` and `PartitionColumn` elements are specified for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="4b6cb-116">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="4b6cb-116">Element Relationships</span></span>  
  
|<span data-ttu-id="4b6cb-117">Relazione</span><span class="sxs-lookup"><span data-stu-id="4b6cb-117">Relationship</span></span>|<span data-ttu-id="4b6cb-118">Elementi</span><span class="sxs-lookup"><span data-stu-id="4b6cb-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="4b6cb-119">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="4b6cb-119">**Parent element**</span></span>|[<span data-ttu-id="4b6cb-120">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4b6cb-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="4b6cb-121">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="4b6cb-121">**Child elements**</span></span>|<span data-ttu-id="4b6cb-122">No.</span><span class="sxs-lookup"><span data-stu-id="4b6cb-122">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4b6cb-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b6cb-123">Example</span></span>  
 <span data-ttu-id="4b6cb-124">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="4b6cb-124">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6cb-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b6cb-125">See Also</span></span>  
 [<span data-ttu-id="4b6cb-126">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="4b6cb-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
