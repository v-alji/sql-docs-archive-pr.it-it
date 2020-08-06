---
title: Editor trasformazione aggregazione (scheda Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.aggregationtransformation.advanced.f1
helpviewer_keywords:
- Aggregate Transformation Editor
ms.assetid: 186a9736-2554-40a0-9cb2-877a8db5fde8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb3742a83f363f74004a5aac0eefc589ee2a5be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626236"
---
# <a name="aggregate-transformation-editor-advanced-tab"></a><span data-ttu-id="bb69d-102">Editor trasformazione Aggregazione (scheda Avanzate)</span><span class="sxs-lookup"><span data-stu-id="bb69d-102">Aggregate Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="bb69d-103">Usare la scheda **Avanzate** della finestra di dialogo **Editor trasformazione Aggregazione** per impostare le proprietà dei componenti, specificare le aggregazioni, nonché impostare le proprietà delle colonne di input e output.</span><span class="sxs-lookup"><span data-stu-id="bb69d-103">Use the **Advanced** tab of the **Aggregate Transformation Editor** dialog box to set component properties, specify aggregations, and set properties of input and output columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb69d-104">Le opzioni per il conteggio delle chiavi, la scala delle chiavi, il conteggio delle chiavi distinct e la scala delle chiavi distinct vengono applicate a livello di componente quando vengono specificate nella scheda **Avanzate** , a livello di output quando vengono specificate nella sezione delle opzioni avanzate della scheda **Aggregazioni** e a livello di colonna quando vengono specificate nell'elenco delle colonne nella parte inferiore della scheda **Aggregazioni** .</span><span class="sxs-lookup"><span data-stu-id="bb69d-104">The options for key count, key scale, distinct key count, and distinct key scale apply at the component level when specified on the **Advanced** tab, at the output level when specified in the advanced display of the **Aggregations** tab, and at the column level when specified in the column list at the bottom of the **Aggregations** tab.</span></span>  
>   
>  <span data-ttu-id="bb69d-105">Nella trasformazione Aggregazione **Chiavi** e **Scala chiavi** fanno riferimento al numero di gruppi che dovrebbero risultare da un'operazione **Group by** .</span><span class="sxs-lookup"><span data-stu-id="bb69d-105">In the Aggregate transformation, **Keys** and **Keys scale** refer to the number of groups that are expected to result from a **Group by** operation.</span></span> <span data-ttu-id="bb69d-106">**Chiavi conteggio valori distinct** e **Scala conteggio valori distinct** fanno riferimento al numero di valori distinct che dovrebbero risultare da un'operazione **Distinct count** .</span><span class="sxs-lookup"><span data-stu-id="bb69d-106">**Count distinct keys** and **Count distinct scale** refer to the number of distinct values that are expected to result from a **Distinct count** operation.</span></span>  
  
 <span data-ttu-id="bb69d-107">Per altre informazioni sulla trasformazione Aggregazione, vedere [Trasformazione Aggregazione](data-flow/transformations/aggregate-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="bb69d-107">To learn more about the Aggregate transformation, see [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb69d-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bb69d-108">Options</span></span>  
 <span data-ttu-id="bb69d-109">**Scala chiavi**</span><span class="sxs-lookup"><span data-stu-id="bb69d-109">**Keys scale**</span></span>  
 <span data-ttu-id="bb69d-110">Consente di specificare facoltativamente il numero approssimativo di chiavi previste dall'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="bb69d-110">Optionally specify the approximate number of keys that the aggregation expects.</span></span> <span data-ttu-id="bb69d-111">La trasformazione utilizza tale informazione per ottimizzare la dimensione iniziale della cache.</span><span class="sxs-lookup"><span data-stu-id="bb69d-111">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="bb69d-112">Per impostazione predefinita, il valore di questa opzione è **Non specificata**.</span><span class="sxs-lookup"><span data-stu-id="bb69d-112">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="bb69d-113">Se vengono specificate sia **Scala chiavi** sia **Numero di chiavi**, **Numero di chiavi** ha priorità.</span><span class="sxs-lookup"><span data-stu-id="bb69d-113">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
|<span data-ttu-id="bb69d-114">Valore</span><span class="sxs-lookup"><span data-stu-id="bb69d-114">Value</span></span>|<span data-ttu-id="bb69d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb69d-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb69d-116">Non specificata</span><span class="sxs-lookup"><span data-stu-id="bb69d-116">Unspecified</span></span>|<span data-ttu-id="bb69d-117">La proprietà **Scala chiavi** non viene usata.</span><span class="sxs-lookup"><span data-stu-id="bb69d-117">The **Keys scale** property is not used.</span></span>|  
|<span data-ttu-id="bb69d-118">Basso</span><span class="sxs-lookup"><span data-stu-id="bb69d-118">Low</span></span>|<span data-ttu-id="bb69d-119">L'aggregazione può scrivere circa 500.000 chiavi.</span><span class="sxs-lookup"><span data-stu-id="bb69d-119">Aggregation can write approximately 500,000 keys.</span></span>|  
|<span data-ttu-id="bb69d-120">Media</span><span class="sxs-lookup"><span data-stu-id="bb69d-120">Medium</span></span>|<span data-ttu-id="bb69d-121">L'aggregazione può scrivere circa 5.000.000 di chiavi.</span><span class="sxs-lookup"><span data-stu-id="bb69d-121">Aggregation can write approximately 5,000,000 keys.</span></span>|  
|<span data-ttu-id="bb69d-122">Alta</span><span class="sxs-lookup"><span data-stu-id="bb69d-122">High</span></span>|<span data-ttu-id="bb69d-123">L'aggregazione può scrivere oltre 25.000.000 di chiavi.</span><span class="sxs-lookup"><span data-stu-id="bb69d-123">Aggregation can write more than 25,000,000 keys.</span></span>|  
  
 <span data-ttu-id="bb69d-124">**Numero di chiavi**</span><span class="sxs-lookup"><span data-stu-id="bb69d-124">**Number of keys**</span></span>  
 <span data-ttu-id="bb69d-125">Consente di specificare facoltativamente il numero esatto di chiavi previste dall'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="bb69d-125">Optionally specify the exact number of keys that the aggregation expects.</span></span> <span data-ttu-id="bb69d-126">La trasformazione utilizza tale informazione per ottimizzare la dimensione iniziale della cache.</span><span class="sxs-lookup"><span data-stu-id="bb69d-126">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="bb69d-127">Se vengono specificate sia **Scala chiavi** sia **Numero di chiavi**, **Numero di chiavi** ha priorità.</span><span class="sxs-lookup"><span data-stu-id="bb69d-127">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
 <span data-ttu-id="bb69d-128">**Scala conteggio valori distinct**</span><span class="sxs-lookup"><span data-stu-id="bb69d-128">**Count distinct scale**</span></span>  
 <span data-ttu-id="bb69d-129">È possibile specificare il numero approssimativo di valori distinct che l'aggregazione può scrivere.</span><span class="sxs-lookup"><span data-stu-id="bb69d-129">Optionally specify the approximate number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="bb69d-130">Per impostazione predefinita, il valore di questa opzione è **Non specificata**.</span><span class="sxs-lookup"><span data-stu-id="bb69d-130">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="bb69d-131">Se vengono specificate sia **Scala conteggio valori distinct** sia **Chiavi conteggio valori distinct**, **Numero di chiavi** ha priorità.</span><span class="sxs-lookup"><span data-stu-id="bb69d-131">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
|<span data-ttu-id="bb69d-132">Valore</span><span class="sxs-lookup"><span data-stu-id="bb69d-132">Value</span></span>|<span data-ttu-id="bb69d-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb69d-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb69d-134">Non specificata</span><span class="sxs-lookup"><span data-stu-id="bb69d-134">Unspecified</span></span>|<span data-ttu-id="bb69d-135">La proprietà CountDistinctScale non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="bb69d-135">The CountDistinctScale property is not used.</span></span>|  
|<span data-ttu-id="bb69d-136">Basso</span><span class="sxs-lookup"><span data-stu-id="bb69d-136">Low</span></span>|<span data-ttu-id="bb69d-137">L'aggregazione può scrivere circa 500.000 valori distinct.</span><span class="sxs-lookup"><span data-stu-id="bb69d-137">Aggregation can write approximately 500,000 distinct values.</span></span>|  
|<span data-ttu-id="bb69d-138">Media</span><span class="sxs-lookup"><span data-stu-id="bb69d-138">Medium</span></span>|<span data-ttu-id="bb69d-139">L'aggregazione può scrivere circa 5.000.000 di valori distinct.</span><span class="sxs-lookup"><span data-stu-id="bb69d-139">Aggregation can write approximately 5,000,000 distinct values.</span></span>|  
|<span data-ttu-id="bb69d-140">Alta</span><span class="sxs-lookup"><span data-stu-id="bb69d-140">High</span></span>|<span data-ttu-id="bb69d-141">L'aggregazione può scrivere oltre 25.000.000 di valori distinct.</span><span class="sxs-lookup"><span data-stu-id="bb69d-141">Aggregation can write more than 25,000,000 distinct values.</span></span>|  
  
 <span data-ttu-id="bb69d-142">**Chiavi conteggio valori distinct**</span><span class="sxs-lookup"><span data-stu-id="bb69d-142">**Count distinct keys**</span></span>  
 <span data-ttu-id="bb69d-143">È possibile specificare il numero esatto di valori distinct che l'aggregazione può scrivere.</span><span class="sxs-lookup"><span data-stu-id="bb69d-143">Optionally specify the exact number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="bb69d-144">Se vengono specificate sia **Scala conteggio valori distinct** sia **Chiavi conteggio valori distinct**, **Numero di chiavi** ha priorità.</span><span class="sxs-lookup"><span data-stu-id="bb69d-144">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
 <span data-ttu-id="bb69d-145">**Fattore di estensione automatica**</span><span class="sxs-lookup"><span data-stu-id="bb69d-145">**Auto extend factor**</span></span>  
 <span data-ttu-id="bb69d-146">Consente di utilizzare un valore compreso tra 1 e 100 per specificare la percentuale di estensione possibile della memoria durante l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="bb69d-146">Use a value between 1 and 100 to specify the percentage by which memory can be extended during the aggregation.</span></span> <span data-ttu-id="bb69d-147">Il valore predefinito di questa opzione è **25%**.</span><span class="sxs-lookup"><span data-stu-id="bb69d-147">By default, the value of this option is **25%**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb69d-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb69d-148">See Also</span></span>  
 <span data-ttu-id="bb69d-149">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bb69d-149">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bb69d-150">[Editor trasformazione aggregazione &#40;scheda Aggregazioni&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span><span class="sxs-lookup"><span data-stu-id="bb69d-150">[Aggregate Transformation Editor &#40;Aggregations Tab&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span></span>  
 [<span data-ttu-id="bb69d-151">Aggregazione di valori in un set di dati utilizzando la trasformazione Aggregazione</span><span class="sxs-lookup"><span data-stu-id="bb69d-151">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>](data-flow/transformations/aggregate-values-in-a-dataset-by-using-the-aggregate-transformation.md)  
  
  
