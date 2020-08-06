---
title: Elemento database per server (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9a48d255898eff6bd780f8edf2c8d2da7229b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711332"
---
# <a name="database-element-for-server-dta"></a><span data-ttu-id="90b0c-102">Elemento Database per Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="90b0c-102">Database Element for Server (DTA)</span></span>
  <span data-ttu-id="90b0c-103">Specifica il database che si desidera ottimizzare in uno specifico server.</span><span class="sxs-lookup"><span data-stu-id="90b0c-103">Specifies the database you want to tune on a specific server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90b0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90b0c-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="90b0c-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="90b0c-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="90b0c-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="90b0c-106">Characteristic</span></span>|<span data-ttu-id="90b0c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90b0c-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="90b0c-108">Tipo di dati e lunghezza</span><span class="sxs-lookup"><span data-stu-id="90b0c-108">Data type and length</span></span>|<span data-ttu-id="90b0c-109">No.</span><span class="sxs-lookup"><span data-stu-id="90b0c-109">None.</span></span>|  
|<span data-ttu-id="90b0c-110">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="90b0c-110">Default value</span></span>|<span data-ttu-id="90b0c-111">No.</span><span class="sxs-lookup"><span data-stu-id="90b0c-111">None.</span></span>|  
|<span data-ttu-id="90b0c-112">Occorrenza</span><span class="sxs-lookup"><span data-stu-id="90b0c-112">Occurrence</span></span>|<span data-ttu-id="90b0c-113">Obbligatorio una o più volte per elemento `Server`.</span><span class="sxs-lookup"><span data-stu-id="90b0c-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="90b0c-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="90b0c-114">Element Relationships</span></span>  
  
|<span data-ttu-id="90b0c-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="90b0c-115">Relationship</span></span>|<span data-ttu-id="90b0c-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="90b0c-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="90b0c-117">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="90b0c-117">Parent element</span></span>|[<span data-ttu-id="90b0c-118">Elemento Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="90b0c-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="90b0c-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="90b0c-119">Child elements</span></span>|[<span data-ttu-id="90b0c-120">Elemento Name per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="90b0c-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="90b0c-121">Elemento Schema per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="90b0c-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="90b0c-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="90b0c-122">Remarks</span></span>  
 <span data-ttu-id="90b0c-123">Questo elemento appartiene al nome **DatabaseDetailsTypecomplexType** nell'XML Schema di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="90b0c-123">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="90b0c-124">Questo elemento `Database` non deve essere confuso con quello il cui padre radice è l'elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="90b0c-124">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="90b0c-125">Per altre informazioni, vedere [Elemento Database per Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="90b0c-125">For more information, see [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90b0c-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="90b0c-126">Example</span></span>  
 <span data-ttu-id="90b0c-127">Per un esempio di utilizzo dell' `Database` elemento, vedere [elemento server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="90b0c-127">For a usage example of the `Database` element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b0c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90b0c-128">See Also</span></span>  
 [<span data-ttu-id="90b0c-129">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="90b0c-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
