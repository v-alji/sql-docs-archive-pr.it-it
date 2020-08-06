---
title: Introduzione a DiffGram in SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotations [SQLXML]
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: 1902d67f-baf3-46e6-a36c-b24b5ba6f8ea
author: rothja
ms.author: jroth
ms.openlocfilehash: e57d87d064ace47247f342ed002b162b920e627f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629296"
---
# <a name="introduction-to-diffgrams-in-sqlxml-40"></a><span data-ttu-id="ed03d-102">Introduzione ai DiffGram in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="ed03d-102">Introduction to DiffGrams in SQLXML 4.0</span></span>
  <span data-ttu-id="ed03d-103">In questo argomento viene fornita una breve introduzione ai DiffGram.</span><span class="sxs-lookup"><span data-stu-id="ed03d-103">This topic provides a brief introduction to DiffGrams.</span></span>  
  
## <a name="diffgram-format"></a><span data-ttu-id="ed03d-104">Formato DiffGram</span><span class="sxs-lookup"><span data-stu-id="ed03d-104">DiffGram Format</span></span>  
 <span data-ttu-id="ed03d-105">Il formato DiffGram generale è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ed03d-105">This is the general DiffGram format:</span></span>  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
   <DataInstance>  
      ...  
   </DataInstance>  
   [<diffgr:before>  
        ...  
   </diffgr:before>]  
  
   [<diffgr:errors>  
        ...  
   </diffgr:errors>]  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="ed03d-106">Il formato DiffGram è costituito dai blocchi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed03d-106">The DiffGram format consists of these blocks:</span></span>  
  
 **\<DataInstance>**  
 <span data-ttu-id="ed03d-107">Il nome di questo elemento, **DataInstance**, viene usato a scopo di spiegazione in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="ed03d-107">The name of this element, **DataInstance**, is used for explanation purposes in this documentation.</span></span> <span data-ttu-id="ed03d-108">Se, ad esempio, il DiffGram è stato generato da un set di dati nel .NET Framework, il valore della proprietà **Name** del set di dati verrebbe utilizzato come nome di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ed03d-108">For example, if the DiffGram were generated from a dataset in the .NET Framework, the value of the **Name** property of the dataset would be used as the name of this element.</span></span> <span data-ttu-id="ed03d-109">Questo blocco contiene tutti i dati rilevanti dopo la modifica, inclusi eventualmente i dati che non sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="ed03d-109">This block contains all relevant data after the change, possibly including data that has not been modified.</span></span> <span data-ttu-id="ed03d-110">La logica di elaborazione DiffGram ignora gli elementi in questo blocco per i quali non è specificato l'attributo **diffgr: hasChanges** .</span><span class="sxs-lookup"><span data-stu-id="ed03d-110">The DiffGram processing logic ignores the elements in this block for which the **diffgr:hasChanges** attribute is not specified.</span></span>  
  
 **\<diffgr:before>**  
 <span data-ttu-id="ed03d-111">Questo blocco facoltativo contiene le istanze dei record originali (elementi) che devono essere aggiornate o eliminate.</span><span class="sxs-lookup"><span data-stu-id="ed03d-111">This optional block contains the original record instances (elements) that must be updated or deleted.</span></span> <span data-ttu-id="ed03d-112">Tutte le tabelle di database modificate (aggiornate o eliminate) dal DiffGram devono essere visualizzate come elementi di livello superiore nel **\<before>** blocco.</span><span class="sxs-lookup"><span data-stu-id="ed03d-112">All the database tables being modified (updated or deleted) by the DiffGram must appear as top-level elements in the **\<before>** block.</span></span>  
  
 **\<diffgr:errors>**  
 <span data-ttu-id="ed03d-113">Questo blocco facoltativo viene ignorato dalla logica di elaborazione DiffGram.</span><span class="sxs-lookup"><span data-stu-id="ed03d-113">This optional block is ignored by the DiffGram processing logic.</span></span>  
  
## <a name="diffgram-annotations"></a><span data-ttu-id="ed03d-114">Annotazioni DiffGram</span><span class="sxs-lookup"><span data-stu-id="ed03d-114">DiffGram Annotations</span></span>  
 <span data-ttu-id="ed03d-115">Queste annotazioni sono definite nello spazio dei nomi DiffGram **"urn: schemas-microsoft-com: XML-DiffGram-01"**:</span><span class="sxs-lookup"><span data-stu-id="ed03d-115">These annotations are defined in the DiffGram namespace **"urn:schemas-microsoft-com:xml-diffgram-01"**:</span></span>  
  
 <span data-ttu-id="ed03d-116">**id**</span><span class="sxs-lookup"><span data-stu-id="ed03d-116">**id**</span></span>  
 <span data-ttu-id="ed03d-117">Questo attributo viene usato per associare gli elementi nei **\<before>** **\<DataInstance>** blocchi e.</span><span class="sxs-lookup"><span data-stu-id="ed03d-117">This attribute is used to pair the elements in the **\<before>** and the **\<DataInstance>** blocks.</span></span>  
  
 <span data-ttu-id="ed03d-118">**hasChanges**</span><span class="sxs-lookup"><span data-stu-id="ed03d-118">**hasChanges**</span></span>  
 <span data-ttu-id="ed03d-119">Per un'operazione di inserimento o aggiornamento, il DiffGram deve specificare questo attributo con il valore **inserito** o **modificato**.</span><span class="sxs-lookup"><span data-stu-id="ed03d-119">For an insert or an update operation, the DiffGram must specify this attribute with the value **inserted** or **modified**.</span></span> <span data-ttu-id="ed03d-120">Se questo attributo non è presente, l'elemento corrispondente in **\<DataInstance>** viene ignorato dalla logica di elaborazione e non vengono eseguiti aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ed03d-120">If this attribute is not present, the corresponding element in the **\<DataInstance>** is ignored by the processing logic and no updates are performed.</span></span> <span data-ttu-id="ed03d-121">Per esempi funzionanti, vedere [esempi di DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ed03d-121">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="ed03d-122">**parentID**</span><span class="sxs-lookup"><span data-stu-id="ed03d-122">**parentID**</span></span>  
 <span data-ttu-id="ed03d-123">Questo attributo viene utilizzato per specificare relazioni padre-figlio tra gli elementi nel DiffGram.</span><span class="sxs-lookup"><span data-stu-id="ed03d-123">This attribute is used to specify parent-child relationships among the elements in the DiffGram.</span></span> <span data-ttu-id="ed03d-124">Questo attributo viene visualizzato solo nel \<before> blocco.</span><span class="sxs-lookup"><span data-stu-id="ed03d-124">This attribute appears only in the \<before> block.</span></span> <span data-ttu-id="ed03d-125">e viene utilizzato da SQLXML durante l'applicazione di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ed03d-125">It is used by SQLXML when applying updates.</span></span> <span data-ttu-id="ed03d-126">La relazione padre-figlio viene utilizzata per determinare l'ordine in cui gli elementi vengono elaborati nel DiffGram.</span><span class="sxs-lookup"><span data-stu-id="ed03d-126">The parent-child relationship is used in determining the order in which the elements in the DiffGram are processed.</span></span>  
  
## <a name="understanding-the-diffgram-processing-logic"></a><span data-ttu-id="ed03d-127">Informazioni sulla logica di elaborazione DiffGram</span><span class="sxs-lookup"><span data-stu-id="ed03d-127">Understanding the DiffGram Processing Logic</span></span>  
 <span data-ttu-id="ed03d-128">La logica di elaborazione DiffGram utilizza determinate regole per stabilire se un'operazione è di inserimento, aggiornamento o eliminazione.</span><span class="sxs-lookup"><span data-stu-id="ed03d-128">The DiffGram processing logic uses certain rules to determine whether an operation is an insert, update, or delete operation.</span></span> <span data-ttu-id="ed03d-129">Tali regole sono descritte nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ed03d-129">These rules are described in the following table.</span></span>  
  
|<span data-ttu-id="ed03d-130">Operazione</span><span class="sxs-lookup"><span data-stu-id="ed03d-130">Operation</span></span>|<span data-ttu-id="ed03d-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed03d-131">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed03d-132">Insert</span><span class="sxs-lookup"><span data-stu-id="ed03d-132">Insert</span></span>|<span data-ttu-id="ed03d-133">Un DiffGram indica un'operazione di inserimento quando un elemento viene visualizzato nel **\<DataInstance>** blocco ma non nel **\<before>** blocco corrispondente e viene specificato l'attributo **diffgr: hasChanges** (**diffgr: hasChanges = inserted**) nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="ed03d-133">A DiffGram indicates an insert operation when an element appears in the **\<DataInstance>** block but not in the corresponding **\<before>** block, and the **diffgr:hasChanges** attribute is specified (**diffgr:hasChanges=inserted**) on the element.</span></span> <span data-ttu-id="ed03d-134">In questo caso, il DiffGram inserisce nel database l'istanza del record specificata nel **\<DataInstance>** blocco.</span><span class="sxs-lookup"><span data-stu-id="ed03d-134">In this case, the DiffGram inserts the record instance that is specified in the **\<DataInstance>** block into the database.</span></span><br /><br /> <span data-ttu-id="ed03d-135">Se l'attributo **diffgr: hasChanges** non è specificato, l'elemento viene ignorato dalla logica di elaborazione e non viene eseguita alcuna operazione di inserimento.</span><span class="sxs-lookup"><span data-stu-id="ed03d-135">If the **diffgr:hasChanges** attribute is not specified, the element is ignored by the processing logic and no insert is performed.</span></span> <span data-ttu-id="ed03d-136">Per esempi funzionanti, vedere [esempi di DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ed03d-136">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>|  
|<span data-ttu-id="ed03d-137">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ed03d-137">Update</span></span>|<span data-ttu-id="ed03d-138">Il DiffGram indica un'operazione di aggiornamento quando è presente un elemento nel \<before> blocco per il quale è presente un elemento corrispondente nel **\<DataInstance>** blocco (ovvero, entrambi gli elementi hanno un attributo **diffgr: ID** con lo stesso valore) e l'attributo **diffgr: hasChanges** viene specificato con il valore **modificato** sull'elemento nel **\<DataInstance>** blocco.</span><span class="sxs-lookup"><span data-stu-id="ed03d-138">The DiffGram indicates an update operation when there is an element in the \<before> block for which there is a corresponding element in the **\<DataInstance>** block (that is, both elements have a **diffgr:id** attribute with same value) and the **diffgr:hasChanges** attribute is specified with the value **modified** on the element in the **\<DataInstance>** block.</span></span><br /><br /> <span data-ttu-id="ed03d-139">Se l'attributo **diffgr: hasChanges** non è specificato nell'elemento del **\<DataInstance>** blocco, la logica di elaborazione restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="ed03d-139">If the **diffgr:hasChanges** attribute is not specified on the element in the **\<DataInstance>** block, an error is returned by the processing logic.</span></span> <span data-ttu-id="ed03d-140">Per esempi funzionanti, vedere [esempi di DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ed03d-140">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="ed03d-141">Se nel blocco viene specificato **diffgr: parentID** **\<before>** , viene utilizzata la relazione padre-figlio degli elementi specificati da **parentID** per determinare l'ordine in cui vengono aggiornati i record.</span><span class="sxs-lookup"><span data-stu-id="ed03d-141">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are updated.</span></span>|  
|<span data-ttu-id="ed03d-142">Delete</span><span class="sxs-lookup"><span data-stu-id="ed03d-142">Delete</span></span>|<span data-ttu-id="ed03d-143">Un DiffGram indica un'operazione di eliminazione quando un elemento viene visualizzato nel **\<before>** blocco ma non nel **\<DataInstance>** blocco corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ed03d-143">A DiffGram indicates a delete operation when an element appears in the **\<before>** block but not in the corresponding **\<DataInstance>** block.</span></span> <span data-ttu-id="ed03d-144">In questo caso, il DiffGram elimina l'istanza del record specificata nel **\<before>** blocco dal database.</span><span class="sxs-lookup"><span data-stu-id="ed03d-144">In this case, the DiffGram deletes the record instance that is specified in the **\<before>** block from the database.</span></span> <span data-ttu-id="ed03d-145">Per esempi funzionanti, vedere [esempi di DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ed03d-145">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="ed03d-146">Se nel blocco viene specificato **diffgr: parentID** **\<before>** , viene utilizzata la relazione padre-figlio degli elementi specificati da **parentID** per determinare l'ordine in cui vengono eliminati i record.</span><span class="sxs-lookup"><span data-stu-id="ed03d-146">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are deleted.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="ed03d-147">Non è possibile passare parametri ai DiffGram.</span><span class="sxs-lookup"><span data-stu-id="ed03d-147">Parameters cannot be passed to DiffGrams.</span></span>  
  
  
