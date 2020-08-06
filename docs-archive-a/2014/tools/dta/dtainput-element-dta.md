---
title: Elemento DTAInput (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAInput element
ms.assetid: 40c19abf-ded5-43de-be96-5b43b1b81b03
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7d2ff380a4ae1595e50aae472efc5fb4ac72efe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712676"
---
# <a name="dtainput-element-dta"></a><span data-ttu-id="5784c-102">Elemento DTAInput (DTA)</span><span class="sxs-lookup"><span data-stu-id="5784c-102">DTAInput Element (DTA)</span></span>
  <span data-ttu-id="5784c-103">Contiene la definizione dell'input XML per Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="5784c-103">Contains the definition of XML input for Database Engine Tuning Advisor.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5784c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5784c-104">Syntax</span></span>  
  
```  
  
<DTAXML>  
    <DTAInput>  
    ...code removed here...  
    </DTAInput>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="5784c-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="5784c-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="5784c-106">Caratteristiche</span><span class="sxs-lookup"><span data-stu-id="5784c-106">Characteristics</span></span>|<span data-ttu-id="5784c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5784c-107">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="5784c-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="5784c-108">**Data type and length**</span></span>|<span data-ttu-id="5784c-109">No.</span><span class="sxs-lookup"><span data-stu-id="5784c-109">None.</span></span>|  
|<span data-ttu-id="5784c-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="5784c-110">**Default value**</span></span>|<span data-ttu-id="5784c-111">No.</span><span class="sxs-lookup"><span data-stu-id="5784c-111">None.</span></span>|  
|<span data-ttu-id="5784c-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="5784c-112">**Occurrence**</span></span>|<span data-ttu-id="5784c-113">Facoltativo una volta per ogni elemento **DTAXML** .</span><span class="sxs-lookup"><span data-stu-id="5784c-113">Optional once per **DTAXML** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="5784c-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="5784c-114">Element Relationships</span></span>  
  
|<span data-ttu-id="5784c-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="5784c-115">Relationship</span></span>|<span data-ttu-id="5784c-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="5784c-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="5784c-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="5784c-117">**Parent element**</span></span>|[<span data-ttu-id="5784c-118">Elemento DTAXML &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="5784c-118">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)|  
|<span data-ttu-id="5784c-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="5784c-119">**Child elements**</span></span>|[<span data-ttu-id="5784c-120">Elemento Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="5784c-120">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="5784c-121">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="5784c-121">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)<br /><br /> [<span data-ttu-id="5784c-122">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="5784c-122">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)<br /><br /> [<span data-ttu-id="5784c-123">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="5784c-123">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="5784c-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5784c-124">Remarks</span></span>  
 <span data-ttu-id="5784c-125">Questo è l'elemento radice della gerarchia dello schema di input di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="5784c-125">This element is the root of the Database Engine Tuning Advisor input schema hierarchy.</span></span> <span data-ttu-id="5784c-126">L'input in Ottimizzazione guidata motore di database può essere costituito da argomenti che specificano i server di cui si desidera ottimizzare i database, i carichi di lavoro, le opzioni di ottimizzazione o una configurazione specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5784c-126">Input to Database Engine Tuning Advisor can be arguments that specify the servers whose databases you want to tune, workloads, tuning options, or a user-specified configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5784c-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="5784c-127">Example</span></span>  
 <span data-ttu-id="5784c-128">Per un esempio d'uso dell'elemento **DTAInput**, vedere [Esempio di file di input XML semplice &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="5784c-128">For a usage example of the **DTAInput** element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5784c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5784c-129">See Also</span></span>  
 [<span data-ttu-id="5784c-130">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="5784c-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
