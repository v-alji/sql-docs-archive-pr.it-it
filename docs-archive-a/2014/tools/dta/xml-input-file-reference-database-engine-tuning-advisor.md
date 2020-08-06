---
title: Guida di riferimento ai file di input XML (Ottimizzazione guidata motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], XML input files
- input file reference [Database Engine Tuning Advisor]
- XML input files [Database Engine Tuning Advisor]
ms.assetid: 05e5e5f0-d6df-4336-b18e-e9bc2835a766
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3bbd38299e4921db33cbaf318883c2f0a9041d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725176"
---
# <a name="xml-input-file-reference-database-engine-tuning-advisor"></a><span data-ttu-id="597b1-102">Guida di riferimento ai file di input XML (Ottimizzazione guidata motore di database)</span><span class="sxs-lookup"><span data-stu-id="597b1-102">XML Input File Reference (Database Engine Tuning Advisor)</span></span>
  [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="597b1-103">Ottimizzazione guidata può usare un file di input XML per ottimizzare un database.</span><span class="sxs-lookup"><span data-stu-id="597b1-103">Tuning Advisor can use an XML input file to tune a database.</span></span> <span data-ttu-id="597b1-104">In questo file XML sono specificati i database, le tabelle, i file o le tabelle del carico di lavoro e le opzioni di ottimizzazione da utilizzare per la sessione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="597b1-104">This XML file designates which databases, tables, workload files or tables, and tuning options to use for the tuning session.</span></span> <span data-ttu-id="597b1-105">È inoltre possibile utilizzare questo file per definire una configurazione specificata dall'utente per eseguire un'analisi di simulazione.</span><span class="sxs-lookup"><span data-stu-id="597b1-105">You can also use this file to specify a user-specified configuration to perform "what-if" analysis.</span></span>  
  
 <span data-ttu-id="597b1-106">Un file di input XML di Ottimizzazione guidata [!INCLUDE[ssDE](../../includes/ssde-md.md)] contiene una gerarchia di elementi XML, ognuno dei quali include testo o altri elementi che specificano le impostazioni della sessione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="597b1-106">A [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file contains a hierarchy of XML elements, each containing text or other elements that specify the tuning session settings.</span></span> <span data-ttu-id="597b1-107">È necessario che il file di input XML di Ottimizzazione guidata [!INCLUDE[ssDE](../../includes/ssde-md.md)] sia conforme agli standard di correttezza del formato XML. Per tutti i nomi degli elementi viene pertanto fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="597b1-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file must conform to the standards for well-formed XML, so all element names are case sensitive.</span></span> <span data-ttu-id="597b1-108">Gli elementi vengono specificati mediante l'uso della distinzione tra maiuscole e minuscole Pascal, in base alla quale il primo carattere e la prima lettera della parola successiva concatenata sono in maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="597b1-108">Elements are specified using Pascal case, which means that the first character is uppercase and the first letter of any subsequent concatenated word is uppercase.</span></span>  
  
 <span data-ttu-id="597b1-109">Tutti i valori degli elementi devono essere conformi alle convenzioni di denominazione XML.</span><span class="sxs-lookup"><span data-stu-id="597b1-109">All element values must conform to XML naming conventions.</span></span> <span data-ttu-id="597b1-110">Per altre informazioni su queste convenzioni, vedere [Contenuto testuale XML](https://go.microsoft.com/fwlink/?LinkId=7614) in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="597b1-110">For more information about these conventions, see [XML Textual Content](https://go.microsoft.com/fwlink/?LinkId=7614) in the MSDN Library.</span></span>  
  
 <span data-ttu-id="597b1-111">Si noti che questa Guida di riferimento non è completa.</span><span class="sxs-lookup"><span data-stu-id="597b1-111">Note that this reference is not comprehensive.</span></span> <span data-ttu-id="597b1-112">Per informazioni su tutti gli elementi che è possibile utilizzare per definire l'input XML, fare riferimento all'XML Schema DTASchema.xsd di Ottimizzazione guidata [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="597b1-112">For information about all the elements you can use to define XML input, refer to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML schema, DTASchema.xsd.</span></span>  
  
## <a name="xml-declaration"></a><span data-ttu-id="597b1-113">Dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="597b1-113">XML Declaration</span></span>  
  
-   [<span data-ttu-id="597b1-114">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-114">XML Data &#40;SQL Server&#41;</span></span>](../../relational-databases/xml/xml-data-sql-server.md)  
  
## <a name="dtaxml-root-element"></a><span data-ttu-id="597b1-115">Elemento radice DTAXML</span><span class="sxs-lookup"><span data-stu-id="597b1-115">DTAXML Root Element</span></span>  
  
-   [<span data-ttu-id="597b1-116">Elemento DTAXML &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-116">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)  
  
## <a name="dtainput-elements"></a><span data-ttu-id="597b1-117">Elementi DTAInput</span><span class="sxs-lookup"><span data-stu-id="597b1-117">DTAInput Elements</span></span>  
  
-   [<span data-ttu-id="597b1-118">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)  
  
-   [<span data-ttu-id="597b1-119">Elemento Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-119">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)  
  
-   [<span data-ttu-id="597b1-120">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)  
  
-   [<span data-ttu-id="597b1-121">Elemento TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-121">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)  
  
-   [<span data-ttu-id="597b1-122">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-122">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)  
  
## <a name="server-elements"></a><span data-ttu-id="597b1-123">Elementi server</span><span class="sxs-lookup"><span data-stu-id="597b1-123">Server Elements</span></span>  
  
-   [<span data-ttu-id="597b1-124">Elemento Name per Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-124">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)  
  
-   [<span data-ttu-id="597b1-125">Elemento Database per Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-125">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)  
  
## <a name="workload-elements"></a><span data-ttu-id="597b1-126">Elementi del carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="597b1-126">Workload Elements</span></span>  
  
-   [<span data-ttu-id="597b1-127">Elemento File &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-127">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)  
  
-   [<span data-ttu-id="597b1-128">Elemento Database per Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-128">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)  
  
-   [<span data-ttu-id="597b1-129">Elemento EventString &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-129">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)  
  
## <a name="tuning-options-elements"></a><span data-ttu-id="597b1-130">Elementi delle opzioni di ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="597b1-130">Tuning Options Elements</span></span>  
  
-   [<span data-ttu-id="597b1-131">Elemento TuningTimeInMin &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-131">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)  
  
-   [<span data-ttu-id="597b1-132">Elemento StorageBoundInMB &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-132">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)  
  
-   [<span data-ttu-id="597b1-133">Elemento TestServer &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-133">TestServer Element &#40;DTA&#41;</span></span>](testserver-element-dta.md)  
  
-   [<span data-ttu-id="597b1-134">Elemento FeatureSet &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-134">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)  
  
-   [<span data-ttu-id="597b1-135">Elemento Partitioning &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-135">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)  
  
-   [<span data-ttu-id="597b1-136">Elemento DropOnlyMode &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-136">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)  
  
-   [<span data-ttu-id="597b1-137">Elemento KeepExisting &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-137">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)  
  
-   [<span data-ttu-id="597b1-138">Elemento OnlineIndexOperation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-138">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)  
  
-   [<span data-ttu-id="597b1-139">Elemento DatabaseToConnect &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-139">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)  
  
## <a name="configuration-elements"></a><span data-ttu-id="597b1-140">Elementi di configurazione</span><span class="sxs-lookup"><span data-stu-id="597b1-140">Configuration Elements</span></span>  
  
-   [<span data-ttu-id="597b1-141">Elemento Server per Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-141">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="597b1-142">Elemento Database per Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-142">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="597b1-143">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-143">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)  
  
-   [<span data-ttu-id="597b1-144">Elemento Create &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-144">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)  
  
-   [<span data-ttu-id="597b1-145">Elemento Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-145">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)  
  
-   [<span data-ttu-id="597b1-146">Elemento Name per Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-146">Name Element for Index &#40;DTA&#41;</span></span>](name-element-for-index-dta.md)  
  
-   [<span data-ttu-id="597b1-147">Elemento Column per Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-147">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)  
  
-   [<span data-ttu-id="597b1-148">Elemento Name per Column &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-148">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)  
  
-   [<span data-ttu-id="597b1-149">Elemento Filegroup per Index &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-149">Filegroup Element for Index &#40;DTA&#41;</span></span>](filegroup-element-for-index-dta.md)  
  
## <a name="database-elements"></a><span data-ttu-id="597b1-150">Elementi di database</span><span class="sxs-lookup"><span data-stu-id="597b1-150">Database Elements</span></span>  
  
-   [<span data-ttu-id="597b1-151">Elemento Name per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-151">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)  
  
-   [<span data-ttu-id="597b1-152">Elemento Schema per Database &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-152">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)  
  
-   [<span data-ttu-id="597b1-153">Elemento Name per Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-153">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="597b1-154">Elemento Table per Schema &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-154">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="597b1-155">Elemento Name per Table &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="597b1-155">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)  
  
## <a name="see-also"></a><span data-ttu-id="597b1-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="597b1-156">See Also</span></span>  
 [<span data-ttu-id="597b1-157">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="597b1-157">Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
