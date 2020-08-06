---
title: Elemento DropOnlyMode (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DropOnlyMode element
ms.assetid: 80960676-7581-4074-889b-80ee665963dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b274dc394a933308cf2161cc271d09b8391900c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711324"
---
# <a name="droponlymode-element-dta"></a><span data-ttu-id="7bca7-102">Elemento DropOnlyMode (DTA)</span><span class="sxs-lookup"><span data-stu-id="7bca7-102">DropOnlyMode Element (DTA)</span></span>
  <span data-ttu-id="7bca7-103">Specifica che Ottimizzazione guidata motore di database deve considerare la rimozione degli indici, delle viste indicizzate o delle partizioni esistenti solo durante la sessione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="7bca7-103">Specifies that Database Engine Tuning Advisor should only consider dropping existing indexes, indexed views, or partitions during the tuning session.</span></span> <span data-ttu-id="7bca7-104">Se è specificata questa opzione di ottimizzazione non viene considerata alcuna nuova struttura di progettazione fisica.</span><span class="sxs-lookup"><span data-stu-id="7bca7-104">No new physical design structures are considered when this tuning option is specified.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bca7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7bca7-105">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <DropOnlyMode>...</DropOnlyMode>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="7bca7-106">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="7bca7-106">Element Characteristics</span></span>  
  
|<span data-ttu-id="7bca7-107">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="7bca7-107">Characteristic</span></span>|<span data-ttu-id="7bca7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7bca7-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7bca7-109">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="7bca7-109">**Data type and length**</span></span>|<span data-ttu-id="7bca7-110">No.</span><span class="sxs-lookup"><span data-stu-id="7bca7-110">None.</span></span>|  
|<span data-ttu-id="7bca7-111">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="7bca7-111">**Default value**</span></span>|<span data-ttu-id="7bca7-112">No.</span><span class="sxs-lookup"><span data-stu-id="7bca7-112">None.</span></span>|  
|<span data-ttu-id="7bca7-113">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="7bca7-113">**Occurrence**</span></span>|<span data-ttu-id="7bca7-114">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="7bca7-114">Optional.</span></span> <span data-ttu-id="7bca7-115">Può essere utilizzato una sola volta per ogni elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="7bca7-115">Can use only once for each `TuningOptions` element.</span></span> <span data-ttu-id="7bca7-116">Non è possibile utilizzarlo se nell'elemento `TuningOptions` sono specificati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bca7-116">Cannot be used if the following elements are specified in the `TuningOptions` element:</span></span><br /><br /> [<span data-ttu-id="7bca7-117">Elemento FeatureSet &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="7bca7-117">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="7bca7-118">Elemento Partitioning &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="7bca7-118">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> <span data-ttu-id="7bca7-119">[Elemento KeepExisting &#40;DTA&#41;](keepexisting-element-dta.md) impostato su **ALL**</span><span class="sxs-lookup"><span data-stu-id="7bca7-119">[KeepExisting Element &#40;DTA&#41;](keepexisting-element-dta.md) is set to **ALL**</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7bca7-120">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="7bca7-120">Element Relationships</span></span>  
  
|<span data-ttu-id="7bca7-121">Relazione</span><span class="sxs-lookup"><span data-stu-id="7bca7-121">Relationship</span></span>|<span data-ttu-id="7bca7-122">Elementi</span><span class="sxs-lookup"><span data-stu-id="7bca7-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7bca7-123">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="7bca7-123">**Parent element**</span></span>|[<span data-ttu-id="7bca7-124">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="7bca7-124">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="7bca7-125">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="7bca7-125">**Child elements**</span></span>|<span data-ttu-id="7bca7-126">No.</span><span class="sxs-lookup"><span data-stu-id="7bca7-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7bca7-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bca7-127">Example</span></span>  
 <span data-ttu-id="7bca7-128">Nell'esempio seguente viene illustrata la sezione `TuningOptions` di un file di input XML di Ottimizzazione guidata motore di database in cui è specificata la modalità `DropOnlyMode`.</span><span class="sxs-lookup"><span data-stu-id="7bca7-128">The following example shows the `TuningOptions` section of a Database Engine Tuning Advisor XML input file where the `DropOnlyMode` is specified.</span></span> <span data-ttu-id="7bca7-129">In questo esempio, il tempo di ottimizzazione è limitato a 24 ore (1440 minuti) e tutti gli indici esistenti cluster e non cluster verranno presi in considerazione per l'eliminazione:</span><span class="sxs-lookup"><span data-stu-id="7bca7-129">In this example the tuning time is limited to 24 hours (1440 minutes) and all existing clustered and nonclustered indexes will be considered for dropping:</span></span>  
  
```xml  
<TuningOptions  
  <TuningTimeInMin>1440</Name>  
  <KeepExisting>ALIGNED</KeepExisting>  
  <DropOnlyMode />  
</TuningOptions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bca7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bca7-130">See Also</span></span>  
 [<span data-ttu-id="7bca7-131">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="7bca7-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
