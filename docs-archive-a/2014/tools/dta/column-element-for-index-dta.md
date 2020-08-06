---
title: Elemento Column per index (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Column element
ms.assetid: ba9fac20-26bd-4333-940e-842c15241b46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67853dc7d1193d3a0f80e56023846bc55a20bdaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711363"
---
# <a name="column-element-for-index-dta"></a><span data-ttu-id="53e14-102">Elemento Column per Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="53e14-102">Column Element for Index (DTA)</span></span>
  <span data-ttu-id="53e14-103">Specifica le colonne sulle quali viene creato l'indice per una configurazione specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="53e14-103">Specifies the columns on which the index is created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53e14-104">Syntax</span></span>  
  
```  
  
<Create>  
  <Index>  
    <Name>...</Name>  
    <Column [Type | SortOrder]>  
     ...code removed here...  
     </Column>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="53e14-105">Attributi elemento</span><span class="sxs-lookup"><span data-stu-id="53e14-105">Element Attributes</span></span>  
  
|<span data-ttu-id="53e14-106">Attributo della colonna</span><span class="sxs-lookup"><span data-stu-id="53e14-106">Column Attribute</span></span>|<span data-ttu-id="53e14-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53e14-107">Description</span></span>|  
|----------------------|-----------------|  
|`Type`|<span data-ttu-id="53e14-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="53e14-108">Optional.</span></span> <span data-ttu-id="53e14-109">Specifica il tipo di colonna dell'indice.</span><span class="sxs-lookup"><span data-stu-id="53e14-109">Specifies the index column type.</span></span> <span data-ttu-id="53e14-110">Usare un tipo di dati **string** per specificare questo attributo con uno dei valori consentiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="53e14-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="53e14-111">`KeyColumn`:</span><span class="sxs-lookup"><span data-stu-id="53e14-111">`KeyColumn`:</span></span><br />                  <span data-ttu-id="53e14-112">Specifica che alla colonna viene fatto riferimento mediante una chiave di indice.</span><span class="sxs-lookup"><span data-stu-id="53e14-112">Specifies that the column is referenced by an index key.</span></span> <span data-ttu-id="53e14-113">Per impostare questo attributo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="53e14-113">Use the following syntax to set this attribute:</span></span><br />`<Column Type="KeyColumn">`<br /><span data-ttu-id="53e14-114">Per altre informazioni sulle colonne chiave, vedere [Descrizione di indici cluster e non cluster](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="53e14-114">For more information about key columns, see [Clustered and Nonclustered Indexes Described](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span></span><br /><br /> <span data-ttu-id="53e14-115">`IncludedColumn`: Specifica che la colonna è una colonna inclusa, anziché una colonna chiave.</span><span class="sxs-lookup"><span data-stu-id="53e14-115">`IncludedColumn`: Specifies that the column is an included column (instead of a key column).</span></span> <span data-ttu-id="53e14-116">Per impostare questo attributo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="53e14-116">Use the following syntax to set this attribute:</span></span><br />`<Column Type="IncludedColumn">`<br /><span data-ttu-id="53e14-117">Per altre informazioni sulle colonne incluse, vedere [Creare indici con colonne incluse](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="53e14-117">For more information about included columns, see [Create Indexes with Included Columns](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span></span>|  
|`SortOrder`|<span data-ttu-id="53e14-118">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="53e14-118">Optional.</span></span> <span data-ttu-id="53e14-119">Specifica l'ordinamento della colonna.</span><span class="sxs-lookup"><span data-stu-id="53e14-119">Specifies the sorting order of the column.</span></span> <span data-ttu-id="53e14-120">Usare un tipo di dati **string** per specificare un ordinamento **"Ascending"** o **"Descending"** come segue:</span><span class="sxs-lookup"><span data-stu-id="53e14-120">Use a **string** data type to specify either an **"Ascending"** or **"Descending"** sorting order as follows:</span></span><br /><br /> `<Column SortOrder="Ascending">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="53e14-121">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="53e14-121">Element Characteristics</span></span>  
  
|<span data-ttu-id="53e14-122">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="53e14-122">Characteristic</span></span>|<span data-ttu-id="53e14-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53e14-123">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="53e14-124">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="53e14-124">**Data type and length**</span></span>|<span data-ttu-id="53e14-125">No.</span><span class="sxs-lookup"><span data-stu-id="53e14-125">None.</span></span>|  
|<span data-ttu-id="53e14-126">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="53e14-126">**Default value**</span></span>|<span data-ttu-id="53e14-127">No.</span><span class="sxs-lookup"><span data-stu-id="53e14-127">None.</span></span>|  
|<span data-ttu-id="53e14-128">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="53e14-128">**Occurrence**</span></span>|<span data-ttu-id="53e14-129">È possibile specificare un massimo di 1024 colonne per l'elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="53e14-129">Can specify up to 1024 columns for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="53e14-130">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="53e14-130">Element Relationships</span></span>  
  
|<span data-ttu-id="53e14-131">Relazione</span><span class="sxs-lookup"><span data-stu-id="53e14-131">Relationship</span></span>|<span data-ttu-id="53e14-132">Elementi</span><span class="sxs-lookup"><span data-stu-id="53e14-132">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="53e14-133">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="53e14-133">**Parent element**</span></span>|[<span data-ttu-id="53e14-134">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="53e14-134">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="53e14-135">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="53e14-135">**Child elements**</span></span>|[<span data-ttu-id="53e14-136">Elemento Name per Column &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="53e14-136">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="53e14-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="53e14-137">Example</span></span>  
 <span data-ttu-id="53e14-138">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="53e14-138">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e14-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53e14-139">See Also</span></span>  
 [<span data-ttu-id="53e14-140">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="53e14-140">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
