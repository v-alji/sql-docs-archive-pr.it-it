---
title: Elemento Name per Table (DTA) | Microsoft Docs
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
ms.assetid: 422a755f-ee52-4863-b1aa-f4ef1b8fd0bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8fa8481cf8990fb63995abcb6300cd9a352c859a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635309"
---
# <a name="name-element-for-table-dta"></a><span data-ttu-id="2ad51-102">Elemento Name per Table (DTA)</span><span class="sxs-lookup"><span data-stu-id="2ad51-102">Name Element for Table (DTA)</span></span>
  <span data-ttu-id="2ad51-103">Specifica il nome di una tabella da ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="2ad51-103">Specifies a table name for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad51-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ad51-104">Syntax</span></span>  
  
```  
  
<Schema>  
    <Table>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="2ad51-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="2ad51-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="2ad51-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="2ad51-106">Characteristic</span></span>|<span data-ttu-id="2ad51-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ad51-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2ad51-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="2ad51-108">**Data type and length**</span></span>|<span data-ttu-id="2ad51-109">`string`, tra 1 e 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="2ad51-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="2ad51-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="2ad51-110">**Default value**</span></span>|<span data-ttu-id="2ad51-111">No.</span><span class="sxs-lookup"><span data-stu-id="2ad51-111">None.</span></span>|  
|<span data-ttu-id="2ad51-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="2ad51-112">**Occurrence**</span></span>|<span data-ttu-id="2ad51-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2ad51-113">Required.</span></span> <span data-ttu-id="2ad51-114">Una volta per ogni elemento `Table`.</span><span class="sxs-lookup"><span data-stu-id="2ad51-114">Once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="2ad51-115">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="2ad51-115">Element Relationships</span></span>  
  
|<span data-ttu-id="2ad51-116">Relazione</span><span class="sxs-lookup"><span data-stu-id="2ad51-116">Relationship</span></span>|<span data-ttu-id="2ad51-117">Elementi</span><span class="sxs-lookup"><span data-stu-id="2ad51-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="2ad51-118">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="2ad51-118">**Parent element**</span></span>|[<span data-ttu-id="2ad51-119">Elemento Table per Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="2ad51-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="2ad51-120">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="2ad51-120">**Child elements**</span></span>|<span data-ttu-id="2ad51-121">No.</span><span class="sxs-lookup"><span data-stu-id="2ad51-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2ad51-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ad51-122">Example</span></span>  
 <span data-ttu-id="2ad51-123">Per un esempio d'uso, vedere [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="2ad51-123">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad51-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ad51-124">See Also</span></span>  
 [<span data-ttu-id="2ad51-125">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="2ad51-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
