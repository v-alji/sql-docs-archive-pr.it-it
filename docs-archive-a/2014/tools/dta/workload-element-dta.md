---
title: Elemento Workload (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Workload element
ms.assetid: 68ffd473-6546-4015-98d0-3763165de65c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20184760c3fcb5eed6c02b8f8fd9b63f5586c9af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627590"
---
# <a name="workload-element-dta"></a><span data-ttu-id="08918-102">Elemento Workload (DTA)</span><span class="sxs-lookup"><span data-stu-id="08918-102">Workload Element (DTA)</span></span>
  <span data-ttu-id="08918-103">Specifica il carico di lavoro da utilizzare per una sessione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="08918-103">Specifies the workload to be used for a tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08918-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08918-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="08918-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="08918-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="08918-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="08918-106">Characteristic</span></span>|<span data-ttu-id="08918-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08918-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="08918-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="08918-108">**Data type and length**</span></span>|<span data-ttu-id="08918-109">No.</span><span class="sxs-lookup"><span data-stu-id="08918-109">None.</span></span>|  
|<span data-ttu-id="08918-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="08918-110">**Default value**</span></span>|<span data-ttu-id="08918-111">No.</span><span class="sxs-lookup"><span data-stu-id="08918-111">None.</span></span>|  
|<span data-ttu-id="08918-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="08918-112">**Occurrence**</span></span>|<span data-ttu-id="08918-113">Obbligatorio una sola volta per ogni elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="08918-113">Required once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="08918-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="08918-114">Element Relationships</span></span>  
  
|<span data-ttu-id="08918-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="08918-115">Relationship</span></span>|<span data-ttu-id="08918-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="08918-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="08918-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="08918-117">**Parent element**</span></span>|[<span data-ttu-id="08918-118">Avviare e usare Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="08918-118">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)|  
|<span data-ttu-id="08918-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="08918-119">**Child elements**</span></span>|[<span data-ttu-id="08918-120">Elemento File &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="08918-120">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)<br /><br /> [<span data-ttu-id="08918-121">Elemento Database per Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="08918-121">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)<br /><br /> [<span data-ttu-id="08918-122">Elemento EventString &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="08918-122">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="08918-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="08918-123">Remarks</span></span>  
 <span data-ttu-id="08918-124">Un carico di lavoro è un set di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sui database che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="08918-124">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="08918-125">Ottimizzazione guidata motore di database può utilizzare come carichi di lavoro script [!INCLUDE[tsql](../../includes/tsql-md.md)] , file di traccia e tabelle di traccia.</span><span class="sxs-lookup"><span data-stu-id="08918-125">The Database Engine Tuning Advisor can use [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, trace files, and trace tables as workloads.</span></span>  
  
 <span data-ttu-id="08918-126">Se viene specificato un carico di lavoro in un file di input XML e un carico di lavoro nella riga di comando con lo strumento **dta** , per l'ottimizzazione verrà utilizzato il carico di lavoro specificato nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="08918-126">If you specify a workload in an XML input file and a workload on the command line with the **dta** tool, the workload specified on the command line will be used for tuning.</span></span> <span data-ttu-id="08918-127">Tutte le opzioni di ottimizzazione specificate nella riga di comando prevalgono su quelle specificate in un file di input XML.</span><span class="sxs-lookup"><span data-stu-id="08918-127">All tuning options specified on the command line override those that are specified in an XML input file.</span></span> <span data-ttu-id="08918-128">L'unica eccezione è rappresentata dal caso in cui una configurazione definita dall'utente venga specificata in modalità di valutazione nel file di input XML.</span><span class="sxs-lookup"><span data-stu-id="08918-128">The only exception is if a user-specified configuration is entered in the evaluate mode in the XML input file.</span></span> <span data-ttu-id="08918-129">Se, ad esempio, viene immessa una configurazione nell'elemento `Configuration` del file di input XML e anche l'elemento `EvaluateConfiguration` viene specificato come una delle opzioni di ottimizzazione, le opzioni di ottimizzazione specificate nel file di input XML prevarranno su qualsiasi opzione di ottimizzazione immessa dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="08918-129">For example, if a configuration is entered in the `Configuration` element of the XML input file and the `EvaluateConfiguration` element is also specified as one of the tuning options, the tuning options specified in the XML input file will override any tuning options entered at the command line.</span></span>  
  
 <span data-ttu-id="08918-130">È necessario specificare un carico di lavoro per ogni sessione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="08918-130">One workload must be specified for each tuning session.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08918-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="08918-131">Example</span></span>  
 <span data-ttu-id="08918-132">Nell'esempio di codice seguente viene specificata la tabella di traccia **database. MyDBOwner. TuningTable001** per l' `Workload` elemento.</span><span class="sxs-lookup"><span data-stu-id="08918-132">The following code example specifies the **MyDatabase.MyDBOwner.TuningTable001** trace table for the `Workload` element.</span></span> <span data-ttu-id="08918-133">La tabella **TuningTable001** è stata creata con il modello Tuning di SQL Server Profiler e salvando l'output della traccia come tabella.</span><span class="sxs-lookup"><span data-stu-id="08918-133">The **TuningTable001** was created by using the Tuning template with SQL Server Profiler and saving the trace output as a table.</span></span>  
  
```  
<DTAXML ...>  
  <DTAInput>  
    <Server>  
...code removed here...  
    </Server>  
    <Workload>  
      <Database>  
        <Name>MyDatabase</Name>  
        <Schema>  
          <Name>MyDBOwner</Name>  
            <Table>  
              <Name>TuningTable001</Name>  
            </Table>  
        </Schema>  
      </Database>  
    </Workload>  
...code removed here...  
  </DTAInput>  
</DTAXML>  
```  
  
## <a name="see-also"></a><span data-ttu-id="08918-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08918-134">See Also</span></span>  
 [<span data-ttu-id="08918-135">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="08918-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
