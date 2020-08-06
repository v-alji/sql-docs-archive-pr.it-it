---
title: Elemento EventString (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- EventString element
ms.assetid: f76c37b4-2f6e-4274-8ee2-87e89d98e8a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 981cd0be06fd0972426fcb2fa67b0c4143cf9178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722107"
---
# <a name="eventstring-element-dta"></a><span data-ttu-id="a39b9-102">Elemento EventString (DTA)</span><span class="sxs-lookup"><span data-stu-id="a39b9-102">EventString Element (DTA)</span></span>
  <span data-ttu-id="a39b9-103">Specifica il carico di lavoro di uno script [!INCLUDE[tsql](../../includes/tsql-md.md)] direttamente nel file di input XML.</span><span class="sxs-lookup"><span data-stu-id="a39b9-103">Specifies a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload directly in the XML input file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a39b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a39b9-104">Syntax</span></span>  
  
```  
  
<Workload>  
    <EventString Weight="...">  
    ...code removed here...  
    </EventString>  
</Workload>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="a39b9-105">Attributi elemento</span><span class="sxs-lookup"><span data-stu-id="a39b9-105">Element Attributes</span></span>  
  
|<span data-ttu-id="a39b9-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="a39b9-106">Attribute</span></span>|<span data-ttu-id="a39b9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a39b9-107">Description</span></span>|  
|---------------|-----------------|  
|`Weight`|<span data-ttu-id="a39b9-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a39b9-108">Optional.</span></span> <span data-ttu-id="a39b9-109">Specifica il fattore di ponderazione, o fattore di importanza, della query per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="a39b9-109">Specifies the query weight factor (a factor of importance) for the specified event.</span></span> <span data-ttu-id="a39b9-110">Per specificare il fattore di ponderazione, utilizzare un tipo di dati `float`.</span><span class="sxs-lookup"><span data-stu-id="a39b9-110">Use a `float` data type to specify the weight.</span></span> <span data-ttu-id="a39b9-111">Ad esempio, `Weight`="100.01".</span><span class="sxs-lookup"><span data-stu-id="a39b9-111">For example, `Weight`="100.01".</span></span> <span data-ttu-id="a39b9-112">Il valore minimo che è possibile specificare per `Weight` è "0".</span><span class="sxs-lookup"><span data-stu-id="a39b9-112">The minimum value you can specify for `Weight` is "0".</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="a39b9-113">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="a39b9-113">Element Characteristics</span></span>  
  
|<span data-ttu-id="a39b9-114">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="a39b9-114">Characteristic</span></span>|<span data-ttu-id="a39b9-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a39b9-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a39b9-116">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="a39b9-116">**Data type and length**</span></span>|<span data-ttu-id="a39b9-117">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="a39b9-117">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="a39b9-118">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="a39b9-118">**Default value**</span></span>|<span data-ttu-id="a39b9-119">No.</span><span class="sxs-lookup"><span data-stu-id="a39b9-119">None.</span></span>|  
|<span data-ttu-id="a39b9-120">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="a39b9-120">**Occurrence**</span></span>|<span data-ttu-id="a39b9-121">Obbligatorio una sola volta se non viene specificato un altro tipo di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a39b9-121">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="a39b9-122">È necessario specificare un elemento figlio `EventString`, `File` o `Database` per l'elemento padre `Workload`, ma è possibile utilizzare un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="a39b9-122">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="a39b9-123">Se ad esempio si specifica un carico di lavoro con l'elemento `EventString`, non sarà possibile specificare anche un carico di lavoro con l'elemento `File` nello stesso file di input XML.</span><span class="sxs-lookup"><span data-stu-id="a39b9-123">For example, if you specify a workload with the `EventString` element, then you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="a39b9-124">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="a39b9-124">Element Relationships</span></span>  
  
|<span data-ttu-id="a39b9-125">Relazione</span><span class="sxs-lookup"><span data-stu-id="a39b9-125">Relationship</span></span>|<span data-ttu-id="a39b9-126">Elementi</span><span class="sxs-lookup"><span data-stu-id="a39b9-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="a39b9-127">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="a39b9-127">**Parent element**</span></span>|[<span data-ttu-id="a39b9-128">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="a39b9-128">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="a39b9-129">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="a39b9-129">**Child elements**</span></span>|<span data-ttu-id="a39b9-130">No.</span><span class="sxs-lookup"><span data-stu-id="a39b9-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a39b9-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="a39b9-131">Example</span></span>  
 <span data-ttu-id="a39b9-132">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con carico di lavoro inline &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="a39b9-132">For a usage example of this element, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md) .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a39b9-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a39b9-133">See Also</span></span>  
 [<span data-ttu-id="a39b9-134">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="a39b9-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
