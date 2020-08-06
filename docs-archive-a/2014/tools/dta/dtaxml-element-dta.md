---
title: Elemento DTAXML (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAXML element
ms.assetid: 3d9942ed-8a27-40db-a7c9-808984d914a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9f428cf996bb819ece74c13226fcd5116a19142b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719241"
---
# <a name="dtaxml-element-dta"></a><span data-ttu-id="1c4c0-102">Elemento DTAXML (DTA)</span><span class="sxs-lookup"><span data-stu-id="1c4c0-102">DTAXML Element (DTA)</span></span>
  <span data-ttu-id="1c4c0-103">L'elemento radice di un file di input o di output XML di Ottimizzazione guidata motore di database, **DTAXML** , contiene tutti gli elementi che descrivono l'input e l'output di ottimizzazione generati da Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-103">The root element of a Database Engine Tuning Advisor XML input or output file, **DTAXML** contains all elements that describe tuning input and the tuning output that Database Engine Tuning Advisor generates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c4c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c4c0-104">Syntax</span></span>  
  
```  
  
<DTAXML   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">  
    ...code removed here...  
</DTAXML>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="1c4c0-105">Attributi elemento</span><span class="sxs-lookup"><span data-stu-id="1c4c0-105">Element Attributes</span></span>  
  
|<span data-ttu-id="1c4c0-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="1c4c0-106">Attribute</span></span>|<span data-ttu-id="1c4c0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c4c0-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns:xsi`|<span data-ttu-id="1c4c0-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-108">Required.</span></span> <span data-ttu-id="1c4c0-109">Identifica lo spazio dei nomi di istanze di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-109">Identifies the XML Schema Instance namespace.</span></span> <span data-ttu-id="1c4c0-110">Gli attributi da questo spazio dei nomi sono utilizzati per fare riferimento allo schema utilizzato per convalidare il file XML di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-110">Attributes from this namespace are used to reference the schema that is used to validate the Database Engine Tuning Advisor XML file.</span></span><br /><br /> <span data-ttu-id="1c4c0-111">Valore obbligatorio: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span><span class="sxs-lookup"><span data-stu-id="1c4c0-111">Required value: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span></span>|  
|`xmlns`|<span data-ttu-id="1c4c0-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-112">Required.</span></span> <span data-ttu-id="1c4c0-113">Identifica lo spazio dei nomi di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-113">Identifies the Database Engine Tuning Advisor namespace.</span></span><br /><br /> <span data-ttu-id="1c4c0-114">Se il file XML di Ottimizzazione guidata motore di database viene modificato utilizzando l'editor XML in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], questo valore è utilizzato da F1 Guida e Guida dinamica per individuare i possibili argomenti di riferimento nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c4c0-114">If you edit the Database Engine Tuning Advisor XML file using the XML editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this value is used by F1 Help and Dynamic Help to locate possible reference topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span><br /><br /> <span data-ttu-id="1c4c0-115">Valore obbligatorio:</span><span class="sxs-lookup"><span data-stu-id="1c4c0-115">Required value:</span></span><br /><br /> <span data-ttu-id="1c4c0-116">Spazio dei nomi[XML Schema di Ottimizzazione guidata motore di database](https://go.microsoft.com/fwlink/?LinkId=43100)</span><span class="sxs-lookup"><span data-stu-id="1c4c0-116">[Database Engine Tuning Advisor XML Schema](https://go.microsoft.com/fwlink/?LinkId=43100) Namespace</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="1c4c0-117">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="1c4c0-117">Element Characteristics</span></span>  
  
|<span data-ttu-id="1c4c0-118">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="1c4c0-118">Characteristic</span></span>|<span data-ttu-id="1c4c0-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c4c0-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1c4c0-120">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="1c4c0-120">**Data type and length**</span></span>|<span data-ttu-id="1c4c0-121">No.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-121">None.</span></span>|  
|<span data-ttu-id="1c4c0-122">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="1c4c0-122">**Default value**</span></span>|<span data-ttu-id="1c4c0-123">No.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-123">None.</span></span>|  
|<span data-ttu-id="1c4c0-124">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="1c4c0-124">**Occurrence**</span></span>|<span data-ttu-id="1c4c0-125">Obbligatorio una volta per ogni file DTA XML.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-125">Required once per DTA XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="1c4c0-126">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="1c4c0-126">Element Relationships</span></span>  
  
|<span data-ttu-id="1c4c0-127">Relazione</span><span class="sxs-lookup"><span data-stu-id="1c4c0-127">Relationship</span></span>|<span data-ttu-id="1c4c0-128">Elementi</span><span class="sxs-lookup"><span data-stu-id="1c4c0-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="1c4c0-129">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="1c4c0-129">**Parent element**</span></span>|<span data-ttu-id="1c4c0-130">nessuno</span><span class="sxs-lookup"><span data-stu-id="1c4c0-130">None</span></span>|  
|<span data-ttu-id="1c4c0-131">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="1c4c0-131">**Child elements**</span></span>|[<span data-ttu-id="1c4c0-132">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="1c4c0-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)<br /><br /> <span data-ttu-id="1c4c0-133">`DTAOutput`Elemento (vedere [Ottimizzazione guidata motore di database XML Schema](https://schemas.microsoft.com/sqlserver/) per informazioni)</span><span class="sxs-lookup"><span data-stu-id="1c4c0-133">`DTAOutput` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c4c0-134">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1c4c0-134">Remarks</span></span>  
 <span data-ttu-id="1c4c0-135">Per ulteriori informazioni sugli spazi dei nomi XML, vedere [Spazi dei nomi in un documento XML](https://go.microsoft.com/fwlink/?LinkId=7341) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="1c4c0-135">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c4c0-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c4c0-136">Example</span></span>  
 <span data-ttu-id="1c4c0-137">Per esempi di elementi **DTAXML** tipici, vedere [Esempi di file di input XML &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="1c4c0-137">For examples of typical **DTAXML** elements, see [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4c0-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c4c0-138">See Also</span></span>  
 <span data-ttu-id="1c4c0-139">[Guida di riferimento ai file di input XML &#40;Ottimizzazione guidata motore di database&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="1c4c0-139">[XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="1c4c0-140">Avviare e usare Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="1c4c0-140">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)  
  
  
