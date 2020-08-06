---
title: Elemento Issue (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- issue element
- XML output file format [ssbdiagnose], issue element
- ssbdiagnose
ms.assetid: 2246a886-686b-44ca-9771-b155cedad8be
author: stevestein
ms.author: sstein
ms.openlocfilehash: a178c1323c1c20f84e67d4d7699fc313090a4c71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711211"
---
# <a name="issue-element-ssbdiagnose"></a><span data-ttu-id="7fbb1-102">Elemento Issue (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="7fbb1-102">Issue Element (ssbdiagnose)</span></span>
  <span data-ttu-id="7fbb1-103">Segnala un problema rilevato dall'utilità **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="7fbb1-103">Reports an issue that was found by the **ssbdiagnose** utility.</span></span> <span data-ttu-id="7fbb1-104">Nel file di output XML di **ssbdiagnose** è presente un solo elemento Issue per ogni problema segnalato.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-104">The **ssbdiagnose** XML output file has one Issue element per issue reported.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fbb1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fbb1-105">Syntax</span></span>  
  
```  
  
<Issue  
    type="..."   
    code="..."   
    server="..."   
    database="..."   
    object="...">   
    ...   
</Issue>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="7fbb1-106">Attributi elemento</span><span class="sxs-lookup"><span data-stu-id="7fbb1-106">Element Attributes</span></span>  
  
|<span data-ttu-id="7fbb1-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="7fbb1-107">Attribute</span></span>|<span data-ttu-id="7fbb1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbb1-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="7fbb1-109">Identifica la categoria del problema segnalato dall'elemento Issue:</span><span class="sxs-lookup"><span data-stu-id="7fbb1-109">Identifies which category of problem the Issue element is reporting:</span></span><br /><br /> <span data-ttu-id="7fbb1-110">**"Diagnosis"** segnala un problema di configurazione rilevato quando si analizza una configurazione di [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7fbb1-110">**"Diagnosis"** Reports a configuration issue found when you analyze a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span><br /><br /> <span data-ttu-id="7fbb1-111">**"Problem"** segnala un problema che ha impedito a **ssbdiagnose** di completare l'analisi.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-111">**"Problem"** Reports an issue that has prevented **ssbdiagnose** from completing its analysis.</span></span> <span data-ttu-id="7fbb1-112">Correggere il problema ed eseguire di nuovo **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-112">Correct the problem and rerun **ssbdiagnose**.</span></span><br /><br /> <span data-ttu-id="7fbb1-113">**"Event"** segnala un evento di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] rilevato quando si esegue un controllo **-RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="7fbb1-113">**"Event"** Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event found when you run a **-RUNTIME** check.</span></span> <span data-ttu-id="7fbb1-114">Gli eventi vengono segnalati solo se è specificata l'opzione **-SHOWEVENTS** .</span><span class="sxs-lookup"><span data-stu-id="7fbb1-114">Events are only reported if **-SHOWEVENTS** is specified.</span></span>|  
|`code`|<span data-ttu-id="7fbb1-115">Identifica il numero di errore relativo al messaggio.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-115">Identifies the error number for the message.</span></span>|  
|`server`|<span data-ttu-id="7fbb1-116">Identifica l'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] in cui è stato rilevato il problema.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-116">Identifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the problem was found.</span></span> <span data-ttu-id="7fbb1-117">Se il problema si è verificato in un'istanza predefinita, l'attributo server è costituito solo del nome del computer,</span><span class="sxs-lookup"><span data-stu-id="7fbb1-117">If the problem was in a default instance, the server attribute only has the computer name.</span></span> <span data-ttu-id="7fbb1-118">mentre se il problema si è verificato in un'istanza denominata, il formato dell'attributo server è NomeComputer\NomeIstanza.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-118">If the problem was in a named instance, the server attribute is in the form ComputerName\InstanceName.</span></span>|  
|`database`|<span data-ttu-id="7fbb1-119">Identifica il nome dell'istanza del database in cui è stato rilevato il problema.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-119">Identifies the name of the database in which the problem was found.</span></span>|  
|`object`|<span data-ttu-id="7fbb1-120">Identifica il nome dell'istanza dell'oggetto in cui è stato rilevato il problema.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-120">Identifies the name of the object in which the problem was found.</span></span> <span data-ttu-id="7fbb1-121">Se il problema si è verificato a livello di istanza o di database, l'attributo dell'oggetto ripete il nome dell'istanza o del database.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-121">If the problem was an instance or database level issue, the object attribute repeats the instance or database name.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="7fbb1-122">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="7fbb1-122">Element Characteristics</span></span>  
  
|<span data-ttu-id="7fbb1-123">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="7fbb1-123">Characteristic</span></span>|<span data-ttu-id="7fbb1-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fbb1-124">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7fbb1-125">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="7fbb1-125">**Data type and length**</span></span>|<span data-ttu-id="7fbb1-126">`string`, lunghezza illimitata.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-126">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="7fbb1-127">**Valore**</span><span class="sxs-lookup"><span data-stu-id="7fbb1-127">**Value**</span></span>|<span data-ttu-id="7fbb1-128">Restituisce il testo del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-128">Returns the text of the error message.</span></span>|  
|<span data-ttu-id="7fbb1-129">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="7fbb1-129">**Occurrence**</span></span>|<span data-ttu-id="7fbb1-130">Una volta per ogni errore segnalato.</span><span class="sxs-lookup"><span data-stu-id="7fbb1-130">Once per reported error.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7fbb1-131">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="7fbb1-131">Element Relationships</span></span>  
  
|<span data-ttu-id="7fbb1-132">Relazione</span><span class="sxs-lookup"><span data-stu-id="7fbb1-132">Relationship</span></span>|<span data-ttu-id="7fbb1-133">Elementi</span><span class="sxs-lookup"><span data-stu-id="7fbb1-133">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7fbb1-134">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="7fbb1-134">**Parent element**</span></span>|[<span data-ttu-id="7fbb1-135">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="7fbb1-135">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="7fbb1-136">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="7fbb1-136">**Child elements**</span></span>|<span data-ttu-id="7fbb1-137">nessuno</span><span class="sxs-lookup"><span data-stu-id="7fbb1-137">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7fbb1-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fbb1-138">Example</span></span>  
 <span data-ttu-id="7fbb1-139">Questo elemento segnala un errore 1102 per un database che non dispone di una chiave master, in cui l'errore è stato rilevato quando è stata analizzata una configurazione di [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7fbb1-139">This element reports an 1102 error for a database that does not have a master key, where the error was found when you analyzed a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span>  
  
```  
<Issue type="Diagnosis" code="1102" server="TestComputer" database="TargetDB" object="TargetDB">The master key was not found</diagnostic>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fbb1-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fbb1-140">See Also</span></span>  
 [<span data-ttu-id="7fbb1-141">Utilità ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="7fbb1-141">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
