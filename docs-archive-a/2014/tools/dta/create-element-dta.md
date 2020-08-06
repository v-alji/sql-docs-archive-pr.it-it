---
title: Elemento Create (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Create element (DTA)
ms.assetid: 9d076c90-f933-45f4-b6d9-447793f6528b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 407f16c3898e56cd393e36c39ed799b83e0092ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711339"
---
# <a name="create-element-dta"></a><span data-ttu-id="d48d7-102">Create - elemento (DTA)</span><span class="sxs-lookup"><span data-stu-id="d48d7-102">Create Element (DTA)</span></span>
  <span data-ttu-id="d48d7-103">Contiene informazioni su indici, statistiche o strutture heap in una configurazione specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d48d7-103">Contains information about the indexes, statistics, or heap structures in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d48d7-104">Syntax</span></span>  
  
```  
  
<Recommendation>  
    <Create>  
    ...code removed here...  
    </Create>  
</Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="d48d7-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="d48d7-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="d48d7-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="d48d7-106">Characteristic</span></span>|<span data-ttu-id="d48d7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d48d7-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d48d7-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="d48d7-108">**Data type and length**</span></span>|<span data-ttu-id="d48d7-109">No.</span><span class="sxs-lookup"><span data-stu-id="d48d7-109">None.</span></span>|  
|<span data-ttu-id="d48d7-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="d48d7-110">**Default value**</span></span>|<span data-ttu-id="d48d7-111">No.</span><span class="sxs-lookup"><span data-stu-id="d48d7-111">None.</span></span>|  
|<span data-ttu-id="d48d7-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="d48d7-112">**Occurrence**</span></span>|<span data-ttu-id="d48d7-113">Obbligatorio una sola volta per ogni struttura di progettazione fisica, quali indici, statistiche o strutture heap.</span><span class="sxs-lookup"><span data-stu-id="d48d7-113">Required once for each physical design structure type (indexes, statistics, or heap structures).</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="d48d7-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="d48d7-114">Element Relationships</span></span>  
  
|<span data-ttu-id="d48d7-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="d48d7-115">Relationship</span></span>|<span data-ttu-id="d48d7-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="d48d7-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="d48d7-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="d48d7-117">**Parent element**</span></span>|[<span data-ttu-id="d48d7-118">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d48d7-118">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
|<span data-ttu-id="d48d7-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="d48d7-119">**Child elements**</span></span>|[<span data-ttu-id="d48d7-120">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="d48d7-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)<br /><br /> <span data-ttu-id="d48d7-121">`Statistics`Elemento (vedere [Ottimizzazione guidata motore di database XML Schema](https://schemas.microsoft.com/sqlserver/) per informazioni)</span><span class="sxs-lookup"><span data-stu-id="d48d7-121">`Statistics` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span><br /><br /> <span data-ttu-id="d48d7-122">`Heap`Elemento (vedere [Ottimizzazione guidata motore di database XML Schema](https://schemas.microsoft.com/sqlserver/) per informazioni)</span><span class="sxs-lookup"><span data-stu-id="d48d7-122">`Heap` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d48d7-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d48d7-123">Remarks</span></span>  
 <span data-ttu-id="d48d7-124">Questo elemento appartiene al nome **CreateTypecomplexType** nell'XML Schema dell'Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="d48d7-124">This element is of the **CreateTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="d48d7-125">Viene utilizzato per creare indici, statistiche e strutture heap per una configurazione specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d48d7-125">It is used to create indexes, statistics, and heap structures for a user-specified configuration.</span></span> <span data-ttu-id="d48d7-126">Questo elemento `Create` non deve essere confuso con altri tipi che è possibile utilizzare per creare viste (`CreateViewType`) o per il partizionamento (`CreatePType`).</span><span class="sxs-lookup"><span data-stu-id="d48d7-126">Do not confuse this `Create` element with the other types that can be used to create views (`CreateViewType`) or partitioning (`CreatePType`).</span></span> <span data-ttu-id="d48d7-127">Per informazioni su questi altri tipi di elemento, fare riferimento alla [Ottimizzazione guidata motore di database XML Schema](https://schemas.microsoft.com/sqlserver/) `Create` .</span><span class="sxs-lookup"><span data-stu-id="d48d7-127">Refer to the [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information about these other `Create` element types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d48d7-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="d48d7-128">Example</span></span>  
 <span data-ttu-id="d48d7-129">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="d48d7-129">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48d7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d48d7-130">See Also</span></span>  
 [<span data-ttu-id="d48d7-131">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="d48d7-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
