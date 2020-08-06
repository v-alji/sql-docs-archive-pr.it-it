---
title: Elemento DiagnosticInformation (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose], diagnosticinformation element
- diagnosticinformation element
- ssbdiagnose
ms.assetid: 0cfda544-542c-4cf4-86d2-8031c91b10f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92d76a065c24ddc1fc8d85989ed3202308571951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625959"
---
# <a name="diagnosticinformation-element-ssbdiagnose"></a><span data-ttu-id="ad002-102">Elemento DiagnosticInformation (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="ad002-102">DiagnosticInformation Element (ssbdiagnose)</span></span>
  <span data-ttu-id="ad002-103">L'elemento **DiagnosticInformation** contiene tutti gli elementi che segnalano le informazioni di diagnostica rilevate dall'utilità.</span><span class="sxs-lookup"><span data-stu-id="ad002-103">The **DiagnosticInformation** element contains all elements that report the diagnostic information found by the utility.</span></span> <span data-ttu-id="ad002-104">**DiagnosticInformation** è l'elemento radice di un file di output XML **ssbdiagnostic** .</span><span class="sxs-lookup"><span data-stu-id="ad002-104">**DiagnosticInformation** is the root element of a **ssbdiagnostic** XML output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad002-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad002-105">Syntax</span></span>  
  
```  
  
<DiagnosticInformation>   
    ...   
</DiagnosticInformation>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="ad002-106">Attributi elemento</span><span class="sxs-lookup"><span data-stu-id="ad002-106">Element Attributes</span></span>  
  
|<span data-ttu-id="ad002-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="ad002-107">Attribute</span></span>|<span data-ttu-id="ad002-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad002-108">Description</span></span>|  
|---------------|-----------------|  
|`None`|<span data-ttu-id="ad002-109">N/D</span><span class="sxs-lookup"><span data-stu-id="ad002-109">N/A</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="ad002-110">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="ad002-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="ad002-111">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="ad002-111">Characteristic</span></span>|<span data-ttu-id="ad002-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad002-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ad002-113">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="ad002-113">**Data type and length**</span></span>|<span data-ttu-id="ad002-114">No.</span><span class="sxs-lookup"><span data-stu-id="ad002-114">None.</span></span>|  
|<span data-ttu-id="ad002-115">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="ad002-115">**Default value**</span></span>|<span data-ttu-id="ad002-116">No.</span><span class="sxs-lookup"><span data-stu-id="ad002-116">None.</span></span>|  
|<span data-ttu-id="ad002-117">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="ad002-117">**Occurrence**</span></span>|<span data-ttu-id="ad002-118">Una volta per file di output XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="ad002-118">Once per **ssbdiagnose** XML output file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="ad002-119">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="ad002-119">Element Relationships</span></span>  
  
|<span data-ttu-id="ad002-120">Relazione</span><span class="sxs-lookup"><span data-stu-id="ad002-120">Relationship</span></span>|<span data-ttu-id="ad002-121">Elementi</span><span class="sxs-lookup"><span data-stu-id="ad002-121">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="ad002-122">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="ad002-122">**Parent element**</span></span>|<span data-ttu-id="ad002-123">No.</span><span class="sxs-lookup"><span data-stu-id="ad002-123">None.</span></span>|  
|<span data-ttu-id="ad002-124">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="ad002-124">**Child elements**</span></span>|[<span data-ttu-id="ad002-125">Elemento Banner &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="ad002-125">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)<br /><br /> [<span data-ttu-id="ad002-126">Elemento Issue &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="ad002-126">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)|  
  
## <a name="remarks"></a><span data-ttu-id="ad002-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ad002-127">Remarks</span></span>  
 <span data-ttu-id="ad002-128">Per ulteriori informazioni sugli spazi dei nomi XML, vedere [Spazi dei nomi in un documento XML](https://go.microsoft.com/fwlink/?LinkId=7341) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="ad002-128">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad002-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad002-129">See Also</span></span>  
 [<span data-ttu-id="ad002-130">Utilità ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="ad002-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
