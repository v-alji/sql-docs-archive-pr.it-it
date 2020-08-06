---
title: Elemento DatabaseToConnect (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DatabaseToConnect element
ms.assetid: 65153a66-3aee-4429-99b7-0816ac23c285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c21b36319e4007264677d499b84964c7cb5ea7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711328"
---
# <a name="databasetoconnect-element-dta"></a><span data-ttu-id="fa902-102">Elemento DatabaseToConnect (DTA)</span><span class="sxs-lookup"><span data-stu-id="fa902-102">DatabaseToConnect Element (DTA)</span></span>
  <span data-ttu-id="fa902-103">Specifica il primo database al quale Ottimizzazione guidata motore di database si connette durante l'ottimizzazione di un carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fa902-103">Specifies the first database to which Database Engine Tuning Advisor connects when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa902-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa902-104">Syntax</span></span>  
  
```  
  
    <TuningOptions>  
...code removed here...  
      <DatabaseToConnect>...</DatabaseToConnect>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="fa902-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="fa902-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="fa902-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="fa902-106">Characteristic</span></span>|<span data-ttu-id="fa902-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa902-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fa902-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="fa902-108">**Data type and length**</span></span>|<span data-ttu-id="fa902-109">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="fa902-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="fa902-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="fa902-110">**Default value**</span></span>|<span data-ttu-id="fa902-111">No.</span><span class="sxs-lookup"><span data-stu-id="fa902-111">None.</span></span>|  
|<span data-ttu-id="fa902-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="fa902-112">**Occurrence**</span></span>|<span data-ttu-id="fa902-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="fa902-113">Optional.</span></span> <span data-ttu-id="fa902-114">È possibile utilizzarlo una volta per ogni elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="fa902-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="fa902-115">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="fa902-115">Element Relationships</span></span>  
  
|<span data-ttu-id="fa902-116">Relazione</span><span class="sxs-lookup"><span data-stu-id="fa902-116">Relationship</span></span>|<span data-ttu-id="fa902-117">Elementi</span><span class="sxs-lookup"><span data-stu-id="fa902-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="fa902-118">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="fa902-118">**Parent element**</span></span>|[<span data-ttu-id="fa902-119">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="fa902-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="fa902-120">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="fa902-120">**Child elements**</span></span>|<span data-ttu-id="fa902-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="fa902-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa902-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fa902-122">Remarks</span></span>  
 <span data-ttu-id="fa902-123">Utilizzare `DatabaseToConnect` per specificare il nome del primo database al quale si desidera che Ottimizzazione guidata motore di database si connetta quando viene avviata la sessione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa902-123">Use `DatabaseToConnect` to specify the name of the first database to which you want Database Engine Tuning Advisor to connect when it starts the tuning session.</span></span> <span data-ttu-id="fa902-124">È possibile specificare un solo database con questo elemento.</span><span class="sxs-lookup"><span data-stu-id="fa902-124">You can specify only one database with this element.</span></span> <span data-ttu-id="fa902-125">Se vengono specificati più nomi di database, Ottimizzazione guidata motore di database restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="fa902-125">If multiple database names are specified, Database Engine Tuning Advisor returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa902-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa902-126">Example</span></span>  
 <span data-ttu-id="fa902-127">Per un esempio di uso, vedere [Esempio di file di input XML con carico di lavoro inline &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="fa902-127">For a usage example, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa902-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa902-128">See Also</span></span>  
 [<span data-ttu-id="fa902-129">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="fa902-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
