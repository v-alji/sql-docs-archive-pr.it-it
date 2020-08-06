---
title: Elemento server per Configuration (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: da9ff870-9cfd-42fe-994b-7b9292681f7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88182cdad2e7313f0910a106ee37d727d840bfed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635301"
---
# <a name="server-element-for-configuration-dta"></a><span data-ttu-id="3708d-102">Elemento Server per Configuration (DTA)</span><span class="sxs-lookup"><span data-stu-id="3708d-102">Server Element for Configuration (DTA)</span></span>
  <span data-ttu-id="3708d-103">Contiene le informazioni per l'identificazione del server in cui si desidera che Ottimizzazione guidata motore di database esegua la valutazione della configurazione ipotetica indicata dall'elemento `Configuration`).</span><span class="sxs-lookup"><span data-stu-id="3708d-103">Contains the identifying information for the server where you want Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3708d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3708d-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    <Server>  
...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="3708d-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="3708d-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="3708d-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="3708d-106">Characteristic</span></span>|<span data-ttu-id="3708d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3708d-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3708d-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="3708d-108">**Data type and length**</span></span>|<span data-ttu-id="3708d-109">No.</span><span class="sxs-lookup"><span data-stu-id="3708d-109">None.</span></span>|  
|<span data-ttu-id="3708d-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="3708d-110">**Default value**</span></span>|<span data-ttu-id="3708d-111">No.</span><span class="sxs-lookup"><span data-stu-id="3708d-111">None.</span></span>|  
|<span data-ttu-id="3708d-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="3708d-112">**Occurrence**</span></span>|<span data-ttu-id="3708d-113">Obbligatorio una volta per ogni elemento di `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="3708d-113">Required once per `Configuration` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3708d-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="3708d-114">Element Relationships</span></span>  
  
|<span data-ttu-id="3708d-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="3708d-115">Relationship</span></span>|<span data-ttu-id="3708d-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="3708d-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3708d-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="3708d-117">**Parent element**</span></span>|[<span data-ttu-id="3708d-118">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3708d-118">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
|<span data-ttu-id="3708d-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="3708d-119">**Child elements**</span></span>|[<span data-ttu-id="3708d-120">Elemento Name per Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3708d-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="3708d-121">Elemento Database per Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3708d-121">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="3708d-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3708d-122">Remarks</span></span>  
 <span data-ttu-id="3708d-123">È possibile specificare un solo `Server` elemento per l' `Configuration` elemento.</span><span class="sxs-lookup"><span data-stu-id="3708d-123">You can specify only one `Server` element for the `Configuration` element.</span></span> <span data-ttu-id="3708d-124">Questo elemento appartiene al Name **ServerTypecomplexType** nell' [XML Schema dell'ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="3708d-124">This element is of the **ServerTypecomplexType** name in the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span> <span data-ttu-id="3708d-125">Questo elemento `Server` non deve essere confuso con l'elemento figlio di `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="3708d-125">Do not confuse this `Server` element with the one that is the child of the `DTAInput` element.</span></span> <span data-ttu-id="3708d-126">Per altre informazioni, vedere [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3708d-126">For more information, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3708d-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="3708d-127">Example</span></span>  
 <span data-ttu-id="3708d-128">Per un esempio di utilizzo, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3708d-128">For a usage example, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3708d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3708d-129">See Also</span></span>  
 [<span data-ttu-id="3708d-130">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="3708d-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
