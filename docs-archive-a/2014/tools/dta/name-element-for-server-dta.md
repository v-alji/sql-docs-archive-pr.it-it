---
title: Elemento Name per server (DTA) | Microsoft Docs
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
ms.assetid: 4c94754d-6d62-4357-8ce7-f107ebf90c71
author: stevestein
ms.author: sstein
ms.openlocfilehash: 202258c3c87f8a35d1ee30b19880f5e9423fa394
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635312"
---
# <a name="name-element-for-server-dta"></a><span data-ttu-id="2f475-102">Elemento Name per Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="2f475-102">Name Element for Server (DTA)</span></span>
  <span data-ttu-id="2f475-103">Contiene il nome del server in cui si trovano i database che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="2f475-103">Contains the name of the server where the databases you want to tune reside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f475-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f475-104">Syntax</span></span>  
  
```  
  
...code removed here...  
<Server>  
    <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="2f475-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="2f475-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="2f475-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="2f475-106">Characteristic</span></span>|<span data-ttu-id="2f475-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f475-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2f475-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="2f475-108">**Data type and length**</span></span>|<span data-ttu-id="2f475-109">`string`, tra 1 e 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2f475-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="2f475-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="2f475-110">**Default value**</span></span>|<span data-ttu-id="2f475-111">No.</span><span class="sxs-lookup"><span data-stu-id="2f475-111">None.</span></span>|  
|<span data-ttu-id="2f475-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="2f475-112">**Occurrence**</span></span>|<span data-ttu-id="2f475-113">Obbligatorio una sola volta per elemento **Server** .</span><span class="sxs-lookup"><span data-stu-id="2f475-113">Required once per **Server** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="2f475-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="2f475-114">Element Relationships</span></span>  
  
|<span data-ttu-id="2f475-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="2f475-115">Relationship</span></span>|<span data-ttu-id="2f475-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="2f475-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="2f475-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="2f475-117">**Parent element**</span></span>|[<span data-ttu-id="2f475-118">Elemento Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="2f475-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="2f475-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="2f475-119">**Child elements**</span></span>|<span data-ttu-id="2f475-120">No.</span><span class="sxs-lookup"><span data-stu-id="2f475-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f475-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f475-121">Example</span></span>  
 <span data-ttu-id="2f475-122">Per un esempio di utilizzo di questo elemento **Name** , vedere [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="2f475-122">For an example of how this **Name** element is used, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f475-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f475-123">See Also</span></span>  
 [<span data-ttu-id="2f475-124">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="2f475-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
