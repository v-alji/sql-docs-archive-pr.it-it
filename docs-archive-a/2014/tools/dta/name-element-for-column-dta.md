---
title: Elemento Name per Column (DTA) | Microsoft Docs
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
ms.assetid: f93b61de-01fe-4237-ada4-f1e481550564
author: stevestein
ms.author: sstein
ms.openlocfilehash: fad3d9a86a7c5db6b6a7503dc90b5a1540e3618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711311"
---
# <a name="name-element-for-column-dta"></a><span data-ttu-id="8a491-102">Elemento Name per Column (DTA)</span><span class="sxs-lookup"><span data-stu-id="8a491-102">Name Element for Column (DTA)</span></span>
  <span data-ttu-id="8a491-103">Specifica il nome di una colonna dell'indice in una configurazione specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8a491-103">Specifies the name for an index column in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a491-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a491-104">Syntax</span></span>  
  
```  
  
<Index>  
    <Column>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="8a491-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="8a491-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="8a491-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="8a491-106">Characteristic</span></span>|<span data-ttu-id="8a491-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a491-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8a491-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="8a491-108">**Data type and length**</span></span>|<span data-ttu-id="8a491-109">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="8a491-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="8a491-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="8a491-110">**Default value**</span></span>|<span data-ttu-id="8a491-111">No.</span><span class="sxs-lookup"><span data-stu-id="8a491-111">None.</span></span>|  
|<span data-ttu-id="8a491-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="8a491-112">**Occurrence**</span></span>|<span data-ttu-id="8a491-113">Obbligatorio una sola volta per ogni elemento `Column`.</span><span class="sxs-lookup"><span data-stu-id="8a491-113">Required once for each `Column` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="8a491-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="8a491-114">Element Relationships</span></span>  
  
|<span data-ttu-id="8a491-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="8a491-115">Relationship</span></span>|<span data-ttu-id="8a491-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="8a491-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="8a491-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="8a491-117">**Parent element**</span></span>|[<span data-ttu-id="8a491-118">Elemento Column per Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="8a491-118">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)|  
|<span data-ttu-id="8a491-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="8a491-119">**Child elements**</span></span>|<span data-ttu-id="8a491-120">No.</span><span class="sxs-lookup"><span data-stu-id="8a491-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a491-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a491-121">Example</span></span>  
 <span data-ttu-id="8a491-122">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="8a491-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a491-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a491-123">See Also</span></span>  
 [<span data-ttu-id="8a491-124">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="8a491-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
