---
title: Elemento banner (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- banner element
- XML output file format [ssbdiagnose], banner element
- ssbdiagnose
ms.assetid: cc6cd49a-acf0-4cfb-8c6a-554692b89de2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13238ac4ef1745dea4fbf3392484ac6137c09df1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726404"
---
# <a name="banner-element-ssbdiagnose"></a><span data-ttu-id="5b411-102">Elemento Banner (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="5b411-102">Banner Element (ssbdiagnose)</span></span>
  <span data-ttu-id="5b411-103">Identifica l'utilità che ha generato il file di output XML di **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="5b411-103">Identifies which utility generated the **ssbdiagnose** output XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b411-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b411-104">Syntax</span></span>  
  
```  
  
<Banner  
    title="..."   
    product="..."   
    version="..." />  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="5b411-105">Attributi elemento</span><span class="sxs-lookup"><span data-stu-id="5b411-105">Element Attributes</span></span>  
  
|<span data-ttu-id="5b411-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="5b411-106">Attribute</span></span>|<span data-ttu-id="5b411-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b411-107">Description</span></span>|  
|---------------|-----------------|  
|`title`|<span data-ttu-id="5b411-108">Identifica l'utilità che ha generato il file di output XML di **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="5b411-108">Identifies the utility that generated the **ssbdiagnose** XML output file.</span></span>|  
|`product`|<span data-ttu-id="5b411-109">Identifica il prodotto che ha generato il file di output XML di **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="5b411-109">Identifies the product that generated the **ssbdiagnose** XML output file.</span></span>|  
|`version`|<span data-ttu-id="5b411-110">Identifica la versione dell'utilità che ha generato il file XML di output.</span><span class="sxs-lookup"><span data-stu-id="5b411-110">Identifies which version of the utility generated the XML output file.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="5b411-111">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="5b411-111">Element Characteristics</span></span>  
  
|<span data-ttu-id="5b411-112">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="5b411-112">Characteristic</span></span>|<span data-ttu-id="5b411-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b411-113">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5b411-114">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="5b411-114">**Data type and length**</span></span>|<span data-ttu-id="5b411-115">No.</span><span class="sxs-lookup"><span data-stu-id="5b411-115">None.</span></span>|  
|<span data-ttu-id="5b411-116">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="5b411-116">**Default value**</span></span>|<span data-ttu-id="5b411-117">No.</span><span class="sxs-lookup"><span data-stu-id="5b411-117">None.</span></span>|  
|<span data-ttu-id="5b411-118">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="5b411-118">**Occurrence**</span></span>|<span data-ttu-id="5b411-119">Una volta per ogni file di output XML di **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="5b411-119">Occurs once per **ssbdiagnose** output XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="5b411-120">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="5b411-120">Element Relationships</span></span>  
  
|<span data-ttu-id="5b411-121">Relazione</span><span class="sxs-lookup"><span data-stu-id="5b411-121">Relationship</span></span>|<span data-ttu-id="5b411-122">Elementi</span><span class="sxs-lookup"><span data-stu-id="5b411-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="5b411-123">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="5b411-123">**Parent element**</span></span>|[<span data-ttu-id="5b411-124">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="5b411-124">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="5b411-125">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="5b411-125">**Child elements**</span></span>|<span data-ttu-id="5b411-126">No.</span><span class="sxs-lookup"><span data-stu-id="5b411-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5b411-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b411-127">Example</span></span>  
 <span data-ttu-id="5b411-128">Di seguito viene riportato un esempio di un elemento Banner.</span><span class="sxs-lookup"><span data-stu-id="5b411-128">This is an example of a banner element.</span></span>  
  
```  
<Banner title="Service Broker Diagnostics Utility" product="Microsoft SQL Server" version="10.0.1073.0" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b411-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b411-129">See Also</span></span>  
 [<span data-ttu-id="5b411-130">Utilità ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="5b411-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
