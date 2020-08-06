---
title: Elemento StorageBoundInMB (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- StorageBoundInMB element
ms.assetid: a8374910-bf68-4edb-b464-53a3a705e7f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea49b0af981b8f8d96efb087033d8f1466364c76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720664"
---
# <a name="storageboundinmb-element-dta"></a><span data-ttu-id="4acea-102">Elemento StorageBoundInMB (DTA)</span><span class="sxs-lookup"><span data-stu-id="4acea-102">StorageBoundInMB Element (DTA)</span></span>
  <span data-ttu-id="4acea-103">Specifica lo spazio massimo in megabyte che è possibile riservare all'Ottimizzazione guidata motore di database per le indicazioni di ottimizzazione, ovvero il set di indice e partizionamento.</span><span class="sxs-lookup"><span data-stu-id="4acea-103">Specifies the maximum space in megabytes that can be consumed by the Database Engine Tuning Advisor tuning recommendation (index and partitioning set).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4acea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4acea-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <StorageBoundInMB>...</ StorageBoundInMB >  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="4acea-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="4acea-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="4acea-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="4acea-106">Characteristic</span></span>|<span data-ttu-id="4acea-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4acea-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4acea-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="4acea-108">**Data type and length**</span></span>|<span data-ttu-id="4acea-109">`unsignedInt`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="4acea-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="4acea-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="4acea-110">**Default value**</span></span>|<span data-ttu-id="4acea-111">No.</span><span class="sxs-lookup"><span data-stu-id="4acea-111">None.</span></span>|  
|<span data-ttu-id="4acea-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="4acea-112">**Occurrence**</span></span>|<span data-ttu-id="4acea-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="4acea-113">Optional.</span></span> <span data-ttu-id="4acea-114">Può essere utilizzato una sola volta per l'elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="4acea-114">Can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="4acea-115">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="4acea-115">Element Relationships</span></span>  
  
|<span data-ttu-id="4acea-116">Relazione</span><span class="sxs-lookup"><span data-stu-id="4acea-116">Relationship</span></span>|<span data-ttu-id="4acea-117">Elementi</span><span class="sxs-lookup"><span data-stu-id="4acea-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="4acea-118">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="4acea-118">**Parent element**</span></span>|[<span data-ttu-id="4acea-119">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="4acea-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="4acea-120">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="4acea-120">**Child elements**</span></span>|<span data-ttu-id="4acea-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="4acea-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4acea-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4acea-122">Remarks</span></span>  
 <span data-ttu-id="4acea-123">Se si ottimizzano più database, per il calcolo dello spazio vengono considerate le indicazioni per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="4acea-123">When multiple databases are tuned, recommendations for all databases are considered for the space calculation.</span></span> <span data-ttu-id="4acea-124">Per impostazione predefinita, nell'Ottimizzazione guidata motore di database vengono utilizzate le dimensioni minori tra gli spazi di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="4acea-124">By default, Database Engine Tuning Advisor assumes the smaller of the following storage sizes:</span></span>  
  
-   <span data-ttu-id="4acea-125">Tre volte le dimensioni dei dati non elaborati correnti nei quali sono incluse le dimensioni totali di heap e indici cluster nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="4acea-125">Three times the current raw data size, which includes the total size of heaps and clustered indexes on tables.</span></span>  
  
-   <span data-ttu-id="4acea-126">Lo spazio disponibile su tutte le unità disco collegate sommato alle dimensioni dei dati non elaborati.</span><span class="sxs-lookup"><span data-stu-id="4acea-126">The free space on all attached disk drives plus the raw data size.</span></span>  
  
 <span data-ttu-id="4acea-127">Le dimensioni dello spazio di archiviazione predefinite non includono gli indici non cluster e le viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="4acea-127">The default storage size does not include nonclustered indexes and indexed views.</span></span>  
  
 <span data-ttu-id="4acea-128">Se il valore specificato per l'elemento `StorageBoundInMB` è superiore allo spazio su disco effettivo, verrà restituito un errore ma l'ottimizzazione continuerà.</span><span class="sxs-lookup"><span data-stu-id="4acea-128">If the value specified for the `StorageBoundInMB` element exceeds the actual disk space, Database Engine Tuning Advisor returns an error, but continues tuning.</span></span> <span data-ttu-id="4acea-129">Al termine dell'ottimizzazione, sarà possibile aggiungere spazio su disco per implementare le indicazioni.</span><span class="sxs-lookup"><span data-stu-id="4acea-129">After tuning is complete, you can add disk space if you decide to implement the recommendation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4acea-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="4acea-130">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="4acea-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4acea-131">Description</span></span>  
 <span data-ttu-id="4acea-132">Nell'esempio di codice seguente viene illustrata la procedura per impostare un limite di 1500 megabyte per lo spazio massimo su disco utilizzabile da un'indicazione di ottimizzazione:</span><span class="sxs-lookup"><span data-stu-id="4acea-132">The following code example shows how to set a limit of 1500 megabytes as the maximum disk space that a tuning recommendation can consume:</span></span>  
  
## <a name="code"></a><span data-ttu-id="4acea-133">Codice</span><span class="sxs-lookup"><span data-stu-id="4acea-133">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <StorageBoundInMB>1500</StorageBoundInMB>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4acea-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4acea-134">See Also</span></span>  
 [<span data-ttu-id="4acea-135">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="4acea-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
