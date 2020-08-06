---
title: Elemento schema per database (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Schema element
ms.assetid: d932e59c-953f-4ab4-934d-b6baf344835c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7653177878f3a832abd2d1ca266bc5feb17b9a29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625118"
---
# <a name="schema-element-for-database-dta"></a><span data-ttu-id="9a6ce-102">Elemento Schema per Database (DTA)</span><span class="sxs-lookup"><span data-stu-id="9a6ce-102">Schema Element for Database (DTA)</span></span>
  <span data-ttu-id="9a6ce-103">Specifica lo schema del database che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="9a6ce-103">Specifies the schema of the database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a6ce-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here...  
    <Schema>...</Schema>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="9a6ce-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="9a6ce-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="9a6ce-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="9a6ce-106">Characteristic</span></span>|<span data-ttu-id="9a6ce-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a6ce-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9a6ce-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="9a6ce-108">**Data type and length**</span></span>|<span data-ttu-id="9a6ce-109">No.</span><span class="sxs-lookup"><span data-stu-id="9a6ce-109">None.</span></span>|  
|<span data-ttu-id="9a6ce-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="9a6ce-110">**Default value**</span></span>|<span data-ttu-id="9a6ce-111">No.</span><span class="sxs-lookup"><span data-stu-id="9a6ce-111">None.</span></span>|  
|<span data-ttu-id="9a6ce-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="9a6ce-112">**Occurrence**</span></span>|<span data-ttu-id="9a6ce-113">Obbligatorio una sola volta per l'elemento **Database** specificato nell'elemento **Server** .</span><span class="sxs-lookup"><span data-stu-id="9a6ce-113">Required once for the **Database** element that is specified under the **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="9a6ce-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="9a6ce-114">Element Relationships</span></span>  
  
|<span data-ttu-id="9a6ce-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="9a6ce-115">Relationship</span></span>|<span data-ttu-id="9a6ce-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="9a6ce-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="9a6ce-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="9a6ce-117">**Parent element**</span></span>|[<span data-ttu-id="9a6ce-118">Elemento Database per Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="9a6ce-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="9a6ce-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="9a6ce-119">**Child elements**</span></span>|[<span data-ttu-id="9a6ce-120">Elemento Name per Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="9a6ce-120">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)<br /><br /> [<span data-ttu-id="9a6ce-121">Elemento Table per Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="9a6ce-121">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="9a6ce-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a6ce-122">Example</span></span>  
 <span data-ttu-id="9a6ce-123">Per un esempio di utilizzo di questo elemento, vedere [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="9a6ce-123">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6ce-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a6ce-124">See Also</span></span>  
 [<span data-ttu-id="9a6ce-125">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="9a6ce-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
