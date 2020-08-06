---
title: Elemento database per Configuration (DTA) | Microsoft Docs
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
ms.assetid: e91ba243-6cc9-457a-8f5a-134f3c71ae69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 69ce1a0ac9912907f6d22916dd6243621e0778db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711335"
---
# <a name="database-element-for-configuration-dta"></a><span data-ttu-id="077ff-102">Elemento Database per Configuration (DTA)</span><span class="sxs-lookup"><span data-stu-id="077ff-102">Database Element for Configuration (DTA)</span></span>
  <span data-ttu-id="077ff-103">Specifica il database sul quale l'Ottimizzazione guidata motore di database eseguirà la valutazione della configurazione ipotetica indicata dall'elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="077ff-103">Specifies the database against which you want the Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="077ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="077ff-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="077ff-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="077ff-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="077ff-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="077ff-106">Characteristic</span></span>|<span data-ttu-id="077ff-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="077ff-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="077ff-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="077ff-108">**Data type and length**</span></span>|<span data-ttu-id="077ff-109">No.</span><span class="sxs-lookup"><span data-stu-id="077ff-109">None.</span></span>|  
|<span data-ttu-id="077ff-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="077ff-110">**Default value**</span></span>|<span data-ttu-id="077ff-111">No.</span><span class="sxs-lookup"><span data-stu-id="077ff-111">None.</span></span>|  
|<span data-ttu-id="077ff-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="077ff-112">**Occurrence**</span></span>|<span data-ttu-id="077ff-113">Obbligatorio una o più volte per elemento `Server`.</span><span class="sxs-lookup"><span data-stu-id="077ff-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="077ff-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="077ff-114">Element Relationships</span></span>  
  
|<span data-ttu-id="077ff-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="077ff-115">Relationship</span></span>|<span data-ttu-id="077ff-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="077ff-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="077ff-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="077ff-117">**Parent element**</span></span>|[<span data-ttu-id="077ff-118">Elemento Server per Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="077ff-118">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
|<span data-ttu-id="077ff-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="077ff-119">**Child elements**</span></span>|[<span data-ttu-id="077ff-120">Elemento Name per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="077ff-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="077ff-121">Elemento Schema per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="077ff-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="077ff-122">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="077ff-122">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="077ff-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="077ff-123">Remarks</span></span>  
 <span data-ttu-id="077ff-124">Questo elemento appartiene al nome **DatabaseTypecomplexType** nell'XML Schema di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="077ff-124">This element is of the **DatabaseTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="077ff-125">Questo elemento `Database` non deve essere confuso con l'elemento il cui padre di livello radice è l'elemento `Server` presente all'inizio del file di input XML.</span><span class="sxs-lookup"><span data-stu-id="077ff-125">Do not confuse this `Database` element with the one whose root parent is the `Server` element, which occurs at the top of the XML input file.</span></span> <span data-ttu-id="077ff-126">Per altre informazioni, vedere [Elemento Database per Server &#40;DTA&#41;](database-element-for-server-dta.md).</span><span class="sxs-lookup"><span data-stu-id="077ff-126">For more information, see [Database Element for Server &#40;DTA&#41;](database-element-for-server-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="077ff-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="077ff-127">Example</span></span>  
 <span data-ttu-id="077ff-128">Per un esempio di utilizzo di questo `Database` elemento, vedere [esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="077ff-128">For a usage example of this `Database` element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="077ff-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="077ff-129">See Also</span></span>  
 [<span data-ttu-id="077ff-130">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="077ff-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
