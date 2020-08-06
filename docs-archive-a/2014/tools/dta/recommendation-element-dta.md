---
title: Elemento Recommendation (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Recommendation element
ms.assetid: 679ea535-865a-4633-a4d3-5b3090515158
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4eb54a106d67f0217a2604b2d08754d0d2c0765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625119"
---
# <a name="recommendation-element-dta"></a><span data-ttu-id="bbfdc-102">Elemento Recommendation (DTA)</span><span class="sxs-lookup"><span data-stu-id="bbfdc-102">Recommendation Element (DTA)</span></span>
  <span data-ttu-id="bbfdc-103">Contiene informazioni sugli indici ipotetici che fanno parte di una configurazione specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="bbfdc-103">Contains information about the hypothetical indexes that are part of a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbfdc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bbfdc-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    ...code removed here...  
    <Table>  
      <Name>...</Name>  
      <Recommendation>  
      ...code removed here...  
      </Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="bbfdc-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="bbfdc-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="bbfdc-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="bbfdc-106">Characteristic</span></span>|<span data-ttu-id="bbfdc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbfdc-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bbfdc-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="bbfdc-108">**Data type and length**</span></span>|<span data-ttu-id="bbfdc-109">No.</span><span class="sxs-lookup"><span data-stu-id="bbfdc-109">None.</span></span>|  
|<span data-ttu-id="bbfdc-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="bbfdc-110">**Default value**</span></span>|<span data-ttu-id="bbfdc-111">No.</span><span class="sxs-lookup"><span data-stu-id="bbfdc-111">None.</span></span>|  
|<span data-ttu-id="bbfdc-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="bbfdc-112">**Occurrence**</span></span>|<span data-ttu-id="bbfdc-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bbfdc-113">Optional.</span></span> <span data-ttu-id="bbfdc-114">È possibile utilizzarlo una volta per ogni elemento `Table`.</span><span class="sxs-lookup"><span data-stu-id="bbfdc-114">Can use once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="bbfdc-115">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="bbfdc-115">Element Relationships</span></span>  
  
|<span data-ttu-id="bbfdc-116">Relazione</span><span class="sxs-lookup"><span data-stu-id="bbfdc-116">Relationship</span></span>|<span data-ttu-id="bbfdc-117">Elementi</span><span class="sxs-lookup"><span data-stu-id="bbfdc-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="bbfdc-118">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="bbfdc-118">**Parent element**</span></span>|[<span data-ttu-id="bbfdc-119">Elemento Table per Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="bbfdc-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="bbfdc-120">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="bbfdc-120">**Child elements**</span></span>|[<span data-ttu-id="bbfdc-121">Elemento Create &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="bbfdc-121">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)<br /><br /> <span data-ttu-id="bbfdc-122">Elemento `Drop`.</span><span class="sxs-lookup"><span data-stu-id="bbfdc-122">`Drop` element.</span></span> <span data-ttu-id="bbfdc-123">Per ulteriori informazioni, vedere l' [XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="bbfdc-123">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbfdc-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bbfdc-124">Remarks</span></span>  
 <span data-ttu-id="bbfdc-125">Questo elemento appartiene al nome **RecommendationTypecomplexType** nell'XML Schema dell'Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="bbfdc-125">This element is of the **RecommendationTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="bbfdc-126">Viene utilizzato per specificare indici per una configurazione ipotetica.</span><span class="sxs-lookup"><span data-stu-id="bbfdc-126">It is used to specify indexes for a hypothetical configuration.</span></span> <span data-ttu-id="bbfdc-127">Questo elemento `Recommendation` non deve essere confuso con altri tipi che è possibile utilizzare per specificare il partizionamento (`RecommendationPType`) o le viste (`RecommendationViewType`).</span><span class="sxs-lookup"><span data-stu-id="bbfdc-127">Do not confuse this `Recommendation` element with the other types that can be used to specify partitioning (`RecommendationPType`) or views (`RecommendationViewType`).</span></span> <span data-ttu-id="bbfdc-128">Per informazioni su questi altri `Recommendation` tipi di elemento, vedere l' [XML Schema di ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="bbfdc-128">For information about these other `Recommendation` element types, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbfdc-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbfdc-129">Example</span></span>  
 <span data-ttu-id="bbfdc-130">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="bbfdc-130">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbfdc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbfdc-131">See Also</span></span>  
 [<span data-ttu-id="bbfdc-132">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="bbfdc-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
