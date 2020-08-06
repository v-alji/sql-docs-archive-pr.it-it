---
title: Attività Lettore di dati WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Data Reader task [Integration Services]
ms.assetid: dae57067-0275-4ac3-8f34-1b9d169f1112
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1d2f16a28e8b6c94c7275468dedb6d2dfec76d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625501"
---
# <a name="wmi-data-reader-task"></a><span data-ttu-id="e2f81-102">Attività Lettore di dati WMI</span><span class="sxs-lookup"><span data-stu-id="e2f81-102">WMI Data Reader Task</span></span>
  <span data-ttu-id="e2f81-103">L'attività Lettore di dati WMI esegue query che utilizzano il linguaggio di query di WMI (Windows Management Instrumentation, Strumentazione gestione Windows) per ottenere da WMI informazioni su un sistema informatico.</span><span class="sxs-lookup"><span data-stu-id="e2f81-103">The WMI Data Reader task runs queries using the Windows Management Instrumentation (WMI) Query Language that returns information from WMI about a computer system.</span></span> <span data-ttu-id="e2f81-104">È possibile utilizzare l'attività Lettore di dati WMI per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2f81-104">You can use the WMI Data Reader task for the following purposes:</span></span>  
  
-   <span data-ttu-id="e2f81-105">Eseguire query sul registro eventi di Windows di un computer locale o remoto e scrivere le informazioni ottenute in un file o in una variabile.</span><span class="sxs-lookup"><span data-stu-id="e2f81-105">Query the Windows event logs on a local or remote computer and write the information to a file or variable.</span></span>  
  
-   <span data-ttu-id="e2f81-106">Ottenere informazioni sulla presenza, lo stato o le proprietà dei componenti hardware e quindi utilizzare tali informazioni per determinare se altre attività nel flusso di controllo devono essere eseguite o meno.</span><span class="sxs-lookup"><span data-stu-id="e2f81-106">Obtain information about the presence, state, or properties of hardware components, and then use this information to determine whether other tasks in the control flow should run.</span></span>  
  
-   <span data-ttu-id="e2f81-107">Ottenere un elenco di applicazioni e determinare le versioni installate.</span><span class="sxs-lookup"><span data-stu-id="e2f81-107">Get a list of applications and determine what version of each application is installed.</span></span>  
  
 <span data-ttu-id="e2f81-108">Per configurare l'attività Lettore di dati WMI, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e2f81-108">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="e2f81-109">Specificare la gestione connessione WMI da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e2f81-109">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="e2f81-110">Specificare l'origine della query WQL.</span><span class="sxs-lookup"><span data-stu-id="e2f81-110">Specify the source of the WQL query.</span></span> <span data-ttu-id="e2f81-111">La query può essere archiviata in una proprietà dell'attività o all'esterno dell'attività, in una variabile o in un file.</span><span class="sxs-lookup"><span data-stu-id="e2f81-111">The query can be stored in a task property, or the query can be stored outside the task, in a variable or a file.</span></span>  
  
-   <span data-ttu-id="e2f81-112">Definire il formato dei risultati della query WQL.</span><span class="sxs-lookup"><span data-stu-id="e2f81-112">Define the format of the WQL query results.</span></span> <span data-ttu-id="e2f81-113">L'attività supporta le tabelle, le coppie nome/valore delle proprietà e i valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="e2f81-113">The task supports a table, property name/value pair, or property value format.</span></span>  
  
-   <span data-ttu-id="e2f81-114">Specificare la destinazione della query,</span><span class="sxs-lookup"><span data-stu-id="e2f81-114">Specify the destination of the query.</span></span> <span data-ttu-id="e2f81-115">che può essere costituita da una variabile o da un file.</span><span class="sxs-lookup"><span data-stu-id="e2f81-115">The destination can be a variable or a file.</span></span>  
  
-   <span data-ttu-id="e2f81-116">Indicare se la destinazione della query verrà sovrascritta o mantenuta oppure se i nuovi dati verranno accodati a quelli esistenti.</span><span class="sxs-lookup"><span data-stu-id="e2f81-116">Indicate whether the query destination is overwritten, kept, or appended.</span></span>  
  
 <span data-ttu-id="e2f81-117">Se la destinazione è un file, l'attività Lettore di dati WMI utilizzerà una gestione connessione file per connettersi al file.</span><span class="sxs-lookup"><span data-stu-id="e2f81-117">If the source or destination is a file, the WMI Data Reader task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="e2f81-118">Per ulteriori informazioni, vedere [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e2f81-118">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e2f81-119">L'attività Lettore di dati WMI utilizza una gestione connessione WMI per connettersi al server da cui legge le informazioni di WMI.</span><span class="sxs-lookup"><span data-stu-id="e2f81-119">The WMI Data Reader task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="e2f81-120">Per altre informazioni, vedere [Gestione connessione WMI](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e2f81-120">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="wql-query"></a><span data-ttu-id="e2f81-121">Query WQL</span><span class="sxs-lookup"><span data-stu-id="e2f81-121">WQL Query</span></span>  
 <span data-ttu-id="e2f81-122">WQL è un sottolinguaggio di SQL che include estensioni per supportare la notifica degli eventi WMI e altre caratteristiche specifiche di WMI.</span><span class="sxs-lookup"><span data-stu-id="e2f81-122">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="e2f81-123">Per altre informazioni su WQL, vedere la documentazione di Strumentazione gestione Windows in [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span><span class="sxs-lookup"><span data-stu-id="e2f81-123">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2f81-124">Le classi WMI variano a seconda della versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e2f81-124">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="e2f81-125">La query WQL seguente restituisce le voci contenute nel registro eventi applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e2f81-125">The following WQL query returns entries in the Application log event.</span></span>  
  
```  
SELECT * FROM Win32_NTLogEvent WHERE LogFile = 'Application' AND (SourceName='SQLISService' OR SourceName='SQLISPackage') AND TimeGenerated > '20050117'  
```  
  
 <span data-ttu-id="e2f81-126">La query WQL seguente restituisce informazioni sui dischi logici.</span><span class="sxs-lookup"><span data-stu-id="e2f81-126">The following WQL query returns logical disk information.</span></span>  
  
```  
SELECT FreeSpace, DeviceId, Size, SystemName, Description FROM Win32_LlogicalDisk  
```  
  
 <span data-ttu-id="e2f81-127">La query WQL seguente restituisce un elenco degli aggiornamenti QFE (Quick Fix Engineering) applicati al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e2f81-127">The following WQL query returns a list of the quick fix engineering (QFE) updates to the operating system.</span></span>  
  
```  
Select * FROM Win32_QuickFixEngineering  
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-data-reader-task"></a><span data-ttu-id="e2f81-128">Messaggi di registrazione personalizzati disponibili nell'attività Lettore di dati WMI</span><span class="sxs-lookup"><span data-stu-id="e2f81-128">Custom Logging Messages Available on the WMI Data Reader Task</span></span>  
 <span data-ttu-id="e2f81-129">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Lettore di dati WMI.</span><span class="sxs-lookup"><span data-stu-id="e2f81-129">The following table lists the custom log entries for the WMI Data Reader task.</span></span> <span data-ttu-id="e2f81-130">Per altre informazioni, vedere [Registrazione di Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) e [Messaggi personalizzati per la registrazione](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="e2f81-130">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="e2f81-131">Voce di log</span><span class="sxs-lookup"><span data-stu-id="e2f81-131">Log entry</span></span>|<span data-ttu-id="e2f81-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2f81-132">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="e2f81-133">Indica che l'attività ha iniziato a leggere dati WMI.</span><span class="sxs-lookup"><span data-stu-id="e2f81-133">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="e2f81-134">Specifica la query WQL eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="e2f81-134">Reports the WQL query that the task ran.</span></span>|  
  
## <a name="configuration-of-the-wmi-data-reader-task"></a><span data-ttu-id="e2f81-135">Configurazione dell'attività Lettore di dati WMI</span><span class="sxs-lookup"><span data-stu-id="e2f81-135">Configuration of the WMI Data Reader Task</span></span>  
 <span data-ttu-id="e2f81-136">È possibile impostare le proprietà a livello di programmazione o tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2f81-136">You can set properties programmatically or through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="e2f81-137">Per informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2f81-137">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e2f81-138">Editor attività Lettore di dati WMI &#40;pagina Opzioni WMI&#41;</span><span class="sxs-lookup"><span data-stu-id="e2f81-138">WMI Data Reader Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-data-reader-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="e2f81-139">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="e2f81-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="e2f81-140">Per informazioni sull'impostazione di queste proprietà a livello di codice, fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="e2f81-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiDataReaderTask.WmiDataReaderTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="e2f81-141">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="e2f81-141">Related Tasks</span></span>  
 <span data-ttu-id="e2f81-142">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="e2f81-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e2f81-143">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="e2f81-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2f81-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2f81-144">See Also</span></span>  
 <span data-ttu-id="e2f81-145">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="e2f81-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="e2f81-146">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="e2f81-146">Control Flow</span></span>](control-flow.md)  
  
  
