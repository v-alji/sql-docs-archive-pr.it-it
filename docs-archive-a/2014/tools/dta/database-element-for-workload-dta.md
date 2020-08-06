---
title: Elemento database per workload (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 112fca2a-37e5-4162-b2e7-b56eb8ab0c6f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2774bc7ed981c84c966a394c95347208cbc6d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711336"
---
# <a name="database-element-for-workload-dta"></a><span data-ttu-id="3218a-102">Elemento Database per Workload (DTA)</span><span class="sxs-lookup"><span data-stu-id="3218a-102">Database Element for Workload (DTA)</span></span>
  <span data-ttu-id="3218a-103">Specifica il database in cui è contenuta la tabella di traccia del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3218a-103">Specifies the database where the workload trace table is located.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3218a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3218a-104">Syntax</span></span>  
  
```  
  
<Workload>  
  <Database>  
   ...code removed here...  
  </Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="3218a-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="3218a-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="3218a-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="3218a-106">Characteristic</span></span>|<span data-ttu-id="3218a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3218a-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3218a-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="3218a-108">**Data type and length**</span></span>|<span data-ttu-id="3218a-109">No.</span><span class="sxs-lookup"><span data-stu-id="3218a-109">None.</span></span>|  
|<span data-ttu-id="3218a-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="3218a-110">**Default value**</span></span>|<span data-ttu-id="3218a-111">No.</span><span class="sxs-lookup"><span data-stu-id="3218a-111">None.</span></span>|  
|<span data-ttu-id="3218a-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="3218a-112">**Occurrence**</span></span>|<span data-ttu-id="3218a-113">Obbligatorio una sola volta se non viene specificato un altro tipo di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3218a-113">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="3218a-114">È necessario specificare un elemento figlio `EventString`, `File` o `Database` per l'elemento padre `Workload`, ma è possibile utilizzare un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="3218a-114">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="3218a-115">Se ad esempio si specifica un carico di lavoro con l'elemento `Database`, non sarà possibile specificare anche un carico di lavoro con l'elemento `File` nello stesso file di input XML.</span><span class="sxs-lookup"><span data-stu-id="3218a-115">For example, if you specify a workload with the `Database` element, you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3218a-116">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="3218a-116">Element Relationships</span></span>  
  
|<span data-ttu-id="3218a-117">Relazione</span><span class="sxs-lookup"><span data-stu-id="3218a-117">Relationship</span></span>|<span data-ttu-id="3218a-118">Elementi</span><span class="sxs-lookup"><span data-stu-id="3218a-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3218a-119">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="3218a-119">**Parent element**</span></span>|[<span data-ttu-id="3218a-120">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3218a-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="3218a-121">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="3218a-121">**Child elements**</span></span>|[<span data-ttu-id="3218a-122">Elemento Name per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3218a-122">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="3218a-123">Elemento Schema per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="3218a-123">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="3218a-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3218a-124">Remarks</span></span>  
 <span data-ttu-id="3218a-125">Questo elemento appartiene al nome **DatabaseDetailsTypecomplexType** nell'XML Schema di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="3218a-125">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="3218a-126">Questo elemento `Database` non deve essere confuso con quello il cui padre radice è l'elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="3218a-126">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="3218a-127">Vedere [Elemento Database per Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3218a-127">(See [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).)</span></span>  
  
## <a name="example"></a><span data-ttu-id="3218a-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="3218a-128">Example</span></span>  
 <span data-ttu-id="3218a-129">Per un esempio di utilizzo di questo `Database` elemento, vedere l'esempio di codice in [elemento workload &#40;DTA&#41;](workload-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3218a-129">For a usage example of this `Database` element, see the code example in [Workload Element &#40;DTA&#41;](workload-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3218a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3218a-130">See Also</span></span>  
 [<span data-ttu-id="3218a-131">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="3218a-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
