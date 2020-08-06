---
title: Attività Monitoraggio eventi WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatchertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Event Watcher task [Integration Services]
ms.assetid: b5bb52e9-a77e-41e1-93f9-d4c3bc6b2c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be20624e5ccdf665e6274f647c342498e9c0f0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724835"
---
# <a name="wmi-event-watcher-task"></a><span data-ttu-id="ce6dd-102">Attività Monitoraggio eventi WMI</span><span class="sxs-lookup"><span data-stu-id="ce6dd-102">WMI Event Watcher Task</span></span>
  <span data-ttu-id="ce6dd-103">L'attività Monitoraggio eventi WMI consente di monitorare gli eventi di WMI (Windows Management Instrumentation, Strumentazione gestione Windows) utilizzando una query WQL (Management Instrumentation Query Language) per specificare gli eventi desiderati.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-103">The WMI Event Watcher task watches for a Windows Management Instrumentation (WMI) event using a Management Instrumentation Query Language (WQL) event query to specify events of interest.</span></span> <span data-ttu-id="ce6dd-104">È possibile utilizzare l'attività Monitoraggio eventi WMI per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce6dd-104">You can use the WMI Event Watcher task for the following purposes:</span></span>  
  
-   <span data-ttu-id="ce6dd-105">Attendere la notifica dell'aggiunta di file a una cartella e quindi avviare l'elaborazione dei file.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-105">Wait for notification that files have been added to a folder and then initiate the processing of the file.</span></span>  
  
-   <span data-ttu-id="ce6dd-106">Eseguire un pacchetto che elimina file quando la quantità di memoria disponibile in un server è inferiore a una percentuale specificata.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-106">Run a package that deletes files when the available memory on a server drops lower than a specified percentage.</span></span>  
  
-   <span data-ttu-id="ce6dd-107">Monitorare l'installazione di un'applicazione e quindi eseguire un pacchetto che la utilizza.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-107">Watch for installation of an application, and then run a package that uses the application.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="ce6dd-108">include un'attività che consente di leggere le informazioni di WMI.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-108">includes a task that reads WMI information.</span></span>  
  
 <span data-ttu-id="ce6dd-109">Per ulteriori informazioni su questa attività, fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="ce6dd-109">For more information about this task, click the following topic:</span></span>  
  
-   [<span data-ttu-id="ce6dd-110">Attività Lettore di dati WMI</span><span class="sxs-lookup"><span data-stu-id="ce6dd-110">WMI Data Reader Task</span></span>](wmi-data-reader-task.md)  
  
## <a name="wql-queries"></a><span data-ttu-id="ce6dd-111">Query WQL</span><span class="sxs-lookup"><span data-stu-id="ce6dd-111">WQL Queries</span></span>  
 <span data-ttu-id="ce6dd-112">WQL è un sottolinguaggio di SQL che include estensioni per supportare la notifica degli eventi WMI e altre caratteristiche specifiche di WMI.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-112">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="ce6dd-113">Per altre informazioni su WQL, vedere la documentazione di Strumentazione gestione Windows in [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="ce6dd-113">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce6dd-114">Le classi WMI variano a seconda della versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-114">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="ce6dd-115">La query seguente esegue il monitoraggio di una notifica che segnala che l'utilizzo della CPU è superiore al 40%.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-115">The following query watches for notification that the CPU use is more than 40 percent.</span></span>  
  
```  
SELECT * from __InstanceModificationEvent WITHIN 2 WHERE TargetInstance ISA 'Win32_Processor' and TargetInstance.LoadPercentage > 40  
```  
  
 <span data-ttu-id="ce6dd-116">La query seguente esegue il monitoraggio di una notifica che segnala che un file è stato aggiunto a una cartella.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-116">The following query watches for notification that a file has been added to a folder.</span></span>  
  
```  
SELECT * FROM __InstanceCreationEvent WITHIN 10 WHERE TargetInstance ISA "CIM_DirectoryContainsFile" and TargetInstance.GroupComponent= "Win32_Directory.Name=\"c:\\\\WMIFileWatcher\""   
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-event-watcher-task"></a><span data-ttu-id="ce6dd-117">Messaggi di registrazione personalizzati disponibili nell'attività Monitoraggio eventi WMI</span><span class="sxs-lookup"><span data-stu-id="ce6dd-117">Custom Logging Messages Available on the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="ce6dd-118">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Monitoraggio eventi WMI.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-118">The following table lists the custom log entries for the WMI Event Watcher task.</span></span> <span data-ttu-id="ce6dd-119">Per altre informazioni, vedere [Registrazione di Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) e [Messaggi personalizzati per la registrazione](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="ce6dd-119">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="ce6dd-120">Voce di log</span><span class="sxs-lookup"><span data-stu-id="ce6dd-120">Log entry</span></span>|<span data-ttu-id="ce6dd-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce6dd-121">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="ce6dd-122">Indica che si è verificato un evento monitorato dall'attività.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-122">Indicates that an event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="ce6dd-123">Indica che si è verificato il timeout dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-123">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="ce6dd-124">Indica che l'attività ha iniziato a eseguire la query WQL.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-124">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="ce6dd-125">La voce include la query.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-125">The entry includes the query.</span></span>|  
  
## <a name="configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="ce6dd-126">Configurazione dell'attività Monitoraggio eventi WMI</span><span class="sxs-lookup"><span data-stu-id="ce6dd-126">Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="ce6dd-127">Per configurare l'attività Lettore di dati WMI, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="ce6dd-127">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="ce6dd-128">Specificare la gestione connessione WMI da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-128">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="ce6dd-129">Specificare l'origine della query WQL.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-129">Specify the source of the WQL query.</span></span> <span data-ttu-id="ce6dd-130">È possibile utilizzare query con origine esterna all'attività, una variabile o un file, oppure archiviate in una proprietà dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-130">The source can be external to the task, a variable or a file, or the query can be stored in a task property.</span></span>  
  
-   <span data-ttu-id="ce6dd-131">Specificare l'operazione che deve essere eseguita dall'attività quando si verifica l'evento WMI.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-131">Specify the action that the task takes when the WMI event occurs.</span></span> <span data-ttu-id="ce6dd-132">È possibile registrare la notifica dell'evento e lo stato dopo l'evento oppure generare eventi di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personalizzati che forniscono informazioni associate all'evento WMI, la notifica e lo stato dopo l'evento.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-132">You can log the event notification and the status after the event, or raise custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] events that provide information associated with the WMI event, the notification, and the status after the event.</span></span>  
  
-   <span data-ttu-id="ce6dd-133">Definire la risposta dell'attività all'evento.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-133">Define how the task responds to the event.</span></span> <span data-ttu-id="ce6dd-134">È possibile configurare l'attività in modo da riuscire o non riuscire, a seconda dell'evento, oppure da riprendere semplicemente il monitoraggio dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-134">The task can be configured to succeed or fail, depending on the event, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="ce6dd-135">Specificare l'operazione che deve essere eseguita dall'attività al timeout della query WQL. È possibile registrare il timeout e lo stato dopo il timeout oppure generare un evento di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personalizzato che indica che si è verificato il timeout dell'evento WMI e registra il timeout e lo stato dopo il timeout.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-135">Specify the action the task takes when the WMI query times out. You can log the time-out and the status after time-out, or raise a custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] event, indicating that the WMI event timed out and logging the time-out and time-out status.</span></span>  
  
-   <span data-ttu-id="ce6dd-136">Definire la risposta dell'attività al timeout. È possibile configurare l'attività in modo da riuscire o non riuscire oppure da riprendere semplicemente il monitoraggio dell'evento.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-136">Define how the task responds to the time-out. The task can be configured to succeed or fail, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="ce6dd-137">Specificare il numero di volte per cui monitorare l'evento.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-137">Specify the number of times the task watches for the event.</span></span>  
  
-   <span data-ttu-id="ce6dd-138">Specificare il timeout.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-138">Specify the time-out.</span></span>  
  
 <span data-ttu-id="ce6dd-139">Se l'origine è un file, l'attività Monitoraggio eventi WMI utilizzerà una gestione connessione file per connettersi al file.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-139">If the source is a file, the WMI Event Watcher task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="ce6dd-140">Per ulteriori informazioni, vedere [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ce6dd-140">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="ce6dd-141">L'attività Monitoraggio eventi WMI utilizza una gestione connessione WMI per connettersi al server da cui legge le informazioni di WMI.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-141">The WMI Event Watcher task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="ce6dd-142">Per altre informazioni, vedere [Gestione connessione WMI](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ce6dd-142">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
 <span data-ttu-id="ce6dd-143">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="ce6dd-143">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ce6dd-144">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce6dd-144">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ce6dd-145">Editor attività Monitoraggio eventi WMI &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="ce6dd-145">WMI Event Watcher Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="ce6dd-146">Editor attività Monitoraggio eventi WMI &#40;pagina Opzioni WMI&#41;</span><span class="sxs-lookup"><span data-stu-id="ce6dd-146">WMI Event Watcher Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-event-watcher-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="ce6dd-147">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="ce6dd-147">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="ce6dd-148">Per altre informazioni sull'impostazione di queste proprietà in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="ce6dd-148">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="ce6dd-149">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="ce6dd-149">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="ce6dd-150">Configurazione a livello di codice dell'attività Monitoraggio eventi WMI</span><span class="sxs-lookup"><span data-stu-id="ce6dd-150">Programmatic Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="ce6dd-151">Per ulteriori informazioni sull'impostazione di queste proprietà a livello di codice, fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="ce6dd-151">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiEventWatcherTask.WmiEventWatcherTask>  
  
  
