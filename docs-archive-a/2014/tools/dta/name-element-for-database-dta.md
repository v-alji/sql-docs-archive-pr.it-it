---
title: Elemento Name per database (DTA) | Microsoft Docs
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
ms.assetid: e871c4fa-3b57-46cf-b4f8-e3be86f92dc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: c692e31b9175bf05dcfb0504ea79e98cbb82f36b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711299"
---
# <a name="name-element-for-database-dta"></a><span data-ttu-id="b20e5-102">Elemento Name per Database (DTA)</span><span class="sxs-lookup"><span data-stu-id="b20e5-102">Name Element for Database (DTA)</span></span>
  <span data-ttu-id="b20e5-103">Specifica il nome del database che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="b20e5-103">Specifies the name of a database that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b20e5-104">Syntax</span></span>  
  
```  
  
<Server>  
    <Database>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b20e5-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="b20e5-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="b20e5-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="b20e5-106">Characteristic</span></span>|<span data-ttu-id="b20e5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b20e5-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b20e5-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="b20e5-108">**Data type and length**</span></span>|<span data-ttu-id="b20e5-109">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="b20e5-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="b20e5-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="b20e5-110">**Default value**</span></span>|<span data-ttu-id="b20e5-111">No.</span><span class="sxs-lookup"><span data-stu-id="b20e5-111">None.</span></span>|  
|<span data-ttu-id="b20e5-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="b20e5-112">**Occurrence**</span></span>|<span data-ttu-id="b20e5-113">Obbligatorio una volta per ogni elemento di `Database`.</span><span class="sxs-lookup"><span data-stu-id="b20e5-113">Required once per `Database` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b20e5-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="b20e5-114">Element Relationships</span></span>  
  
|<span data-ttu-id="b20e5-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="b20e5-115">Relationship</span></span>|<span data-ttu-id="b20e5-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="b20e5-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b20e5-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="b20e5-117">**Parent element**</span></span>|[<span data-ttu-id="b20e5-118">Elemento Database per Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b20e5-118">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
|<span data-ttu-id="b20e5-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="b20e5-119">**Child elements**</span></span>|<span data-ttu-id="b20e5-120">No.</span><span class="sxs-lookup"><span data-stu-id="b20e5-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b20e5-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="b20e5-121">Example</span></span>  
 <span data-ttu-id="b20e5-122">Per un esempio di utilizzo di questo elemento, vedere [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b20e5-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b20e5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b20e5-123">See Also</span></span>  
 [<span data-ttu-id="b20e5-124">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="b20e5-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
