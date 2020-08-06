---
title: Elemento TestServer (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TestServer element
ms.assetid: caa3547a-2cd5-47ad-ace2-a36752835cfe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d1f1fadf76a43caca262652254e8a778602183c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720657"
---
# <a name="testserver-element-dta"></a><span data-ttu-id="7b481-102">Elemento TestServer (DTA)</span><span class="sxs-lookup"><span data-stu-id="7b481-102">TestServer Element (DTA)</span></span>
  <span data-ttu-id="7b481-103">Indica il server di prova da utilizzare durante l'ottimizzazione di un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="7b481-103">Specifies the test server to use when tuning a production server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b481-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b481-104">Syntax</span></span>  
  
```  
  
<TuningOptions>  
  <TestServer>...</TestServer>  
   ...code removed here...  
</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="7b481-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="7b481-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="7b481-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="7b481-106">Characteristic</span></span>|<span data-ttu-id="7b481-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b481-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7b481-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="7b481-108">**Data type and length**</span></span>|<span data-ttu-id="7b481-109">**string**, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="7b481-109">**string**, unlimited length.</span></span>|  
|<span data-ttu-id="7b481-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="7b481-110">**Default value**</span></span>|<span data-ttu-id="7b481-111">No.</span><span class="sxs-lookup"><span data-stu-id="7b481-111">None.</span></span>|  
|<span data-ttu-id="7b481-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="7b481-112">**Occurrence**</span></span>|<span data-ttu-id="7b481-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7b481-113">Optional.</span></span> <span data-ttu-id="7b481-114">È possibile utilizzarlo una volta per ogni elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="7b481-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7b481-115">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="7b481-115">Element Relationships</span></span>  
  
|<span data-ttu-id="7b481-116">Relazione</span><span class="sxs-lookup"><span data-stu-id="7b481-116">Relationship</span></span>|<span data-ttu-id="7b481-117">Elementi</span><span class="sxs-lookup"><span data-stu-id="7b481-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7b481-118">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="7b481-118">**Parent element**</span></span>|[<span data-ttu-id="7b481-119">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="7b481-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="7b481-120">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="7b481-120">**Child elements**</span></span>|<span data-ttu-id="7b481-121">No.</span><span class="sxs-lookup"><span data-stu-id="7b481-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7b481-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b481-122">Example</span></span>  
 <span data-ttu-id="7b481-123">Per un esempio di utilizzo di questo elemento, vedere [Riduzione del carico di ottimizzazione del server di produzione](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span><span class="sxs-lookup"><span data-stu-id="7b481-123">For a usage example of this element, see [Reduce the Production Server Tuning Load](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b481-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b481-124">See Also</span></span>  
 [<span data-ttu-id="7b481-125">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="7b481-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
