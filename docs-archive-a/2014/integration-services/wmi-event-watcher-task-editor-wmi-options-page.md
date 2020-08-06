---
title: Editor attività Monitoraggio eventi WMI (pagina Opzioni WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatcher.wmiquery.f1
helpviewer_keywords:
- WMI Event Watcher Task Editor
ms.assetid: 525f3de7-a021-4e52-9939-3a83c88f131a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d7d95501f6442df3723261c970c7a90f48cbdc87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718408"
---
# <a name="wmi-event-watcher-task-editor-wmi-options-page"></a><span data-ttu-id="68a47-102">Editor attività Monitoraggio eventi WMI (pagina Opzioni WMI)</span><span class="sxs-lookup"><span data-stu-id="68a47-102">WMI Event Watcher Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="68a47-103">Usare la pagina **Opzioni WMI** della finestra di dialogo **Editor attività Monitoraggio eventi WM** per specificare l'origine della query WQL e la modalità di risposta dell'attività Monitoraggio eventi WMI agli eventi del servizio Strumentazione Gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="68a47-103">Use the **WMI Options** page of the **WMI Event Watcher Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and how the WMI Event Watcher task responds to Microsoft Windows Instrumentation (WMI) events.</span></span>  
  
 <span data-ttu-id="68a47-104">Per ulteriori informazioni su questa attività, vedere [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span><span class="sxs-lookup"><span data-stu-id="68a47-104">To learn about this task, see [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span></span> <span data-ttu-id="68a47-105">Per altre informazioni su WQL (WMI Query Language), vedere l'argomento relativo a WMI (Windows Management Instrumentation) [Query con WQL](https://go.microsoft.com/fwlink/?LinkId=79045)in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="68a47-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="68a47-106">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="68a47-106">Static Options</span></span>  
 <span data-ttu-id="68a47-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="68a47-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="68a47-108">Selezionare una gestione connessione WMI nell'elenco oppure fare clic su \<**New WMI Connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="68a47-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="68a47-109">**Argomenti correlati:** [Gestione connessione WMI](connection-manager/wmi-connection-manager.md), [Editor gestione connessione WMI](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="68a47-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="68a47-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="68a47-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="68a47-111">Consente di selezionare il tipo di origine della query WQL eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="68a47-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="68a47-112">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="68a47-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="68a47-113">valore</span><span class="sxs-lookup"><span data-stu-id="68a47-113">Value</span></span>|<span data-ttu-id="68a47-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68a47-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68a47-115">**Input diretto**</span><span class="sxs-lookup"><span data-stu-id="68a47-115">**Direct input**</span></span>|<span data-ttu-id="68a47-116">Consente di impostare l'origine su una query WQL.</span><span class="sxs-lookup"><span data-stu-id="68a47-116">Set the source to a WQL query.</span></span> <span data-ttu-id="68a47-117">Selezionando questo valore viene visualizzata l'opzione dinamica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="68a47-117">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="68a47-118">**Connessione file**</span><span class="sxs-lookup"><span data-stu-id="68a47-118">**File connection**</span></span>|<span data-ttu-id="68a47-119">Consente di selezionare un file contenente la query WQL.</span><span class="sxs-lookup"><span data-stu-id="68a47-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="68a47-120">Selezionando questo valore viene visualizzata l'opzione dinamica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="68a47-120">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="68a47-121">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="68a47-121">**Variable**</span></span>|<span data-ttu-id="68a47-122">Consente di impostare l'origine su una variabile che definisce la query WQL.</span><span class="sxs-lookup"><span data-stu-id="68a47-122">Set the source to a variable that defines WQL query.</span></span> <span data-ttu-id="68a47-123">Selezionando questo valore viene visualizzata l'opzione dinamica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="68a47-123">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
  
 <span data-ttu-id="68a47-124">**ActionAtEvent**</span><span class="sxs-lookup"><span data-stu-id="68a47-124">**ActionAtEvent**</span></span>  
 <span data-ttu-id="68a47-125">Consente di specificare se l'evento WMI registra l'evento e inizia un'azione [!INCLUDE[ssIS](../includes/ssis-md.md)] oppure se si limita a registrare l'evento.</span><span class="sxs-lookup"><span data-stu-id="68a47-125">Specify whether the WMI event logs the event and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] action, or only logs the event.</span></span>  
  
 <span data-ttu-id="68a47-126">**AfterEvent**</span><span class="sxs-lookup"><span data-stu-id="68a47-126">**AfterEvent**</span></span>  
 <span data-ttu-id="68a47-127">Consente di specificare se l'attività ha esito positivo o negativo dopo avere ricevuto l'evento WMI oppure se deve continuare a monitorare l'evento per controllare se viene generato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="68a47-127">Specify whether the task succeeds or fails after it receives the WMI event, or if the task continues watching for the event to occur again.</span></span>  
  
 <span data-ttu-id="68a47-128">**ActionAtTimeout**</span><span class="sxs-lookup"><span data-stu-id="68a47-128">**ActionAtTimeout**</span></span>  
 <span data-ttu-id="68a47-129">Consente di specificare se l'attività registra un timeout della query WMI e inizia un evento [!INCLUDE[ssIS](../includes/ssis-md.md)] in risposta oppure se si limita a registrare il timeout.</span><span class="sxs-lookup"><span data-stu-id="68a47-129">Specify whether the task logs a WMI query time-out and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] event in response, or only logs the time-out.</span></span>  
  
 <span data-ttu-id="68a47-130">**AfterTimeout**</span><span class="sxs-lookup"><span data-stu-id="68a47-130">**AfterTimeout**</span></span>  
 <span data-ttu-id="68a47-131">Consente di specificare se l'attività ha esito positivo o negativo in risposta a un timeout oppure se deve continuare il monitoraggio per controllare se viene generato un altro timeout.</span><span class="sxs-lookup"><span data-stu-id="68a47-131">Specify whether the task succeeds or fails in response to a time-out, or if the task continues watching for another time-out to recur.</span></span>  
  
 <span data-ttu-id="68a47-132">**NumberOfEvents**</span><span class="sxs-lookup"><span data-stu-id="68a47-132">**NumberOfEvents**</span></span>  
 <span data-ttu-id="68a47-133">Consente di specificare il numero di eventi da monitorare.</span><span class="sxs-lookup"><span data-stu-id="68a47-133">Specify the number of events to watch for.</span></span>  
  
 <span data-ttu-id="68a47-134">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="68a47-134">**Timeout**</span></span>  
 <span data-ttu-id="68a47-135">Consente di specificare il numero di secondi di attesa per la generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="68a47-135">Specify the number of seconds to wait for the event to occur.</span></span> <span data-ttu-id="68a47-136">Un valore pari a 0 significa che non è attivo alcun timeout.</span><span class="sxs-lookup"><span data-stu-id="68a47-136">A value of 0 means that no time-out is in effect.</span></span>  
  
## <a name="wqlquerysource-dynamic-options"></a><span data-ttu-id="68a47-137">Opzioni dinamiche di WQLQuerySource</span><span class="sxs-lookup"><span data-stu-id="68a47-137">WQLQuerySource Dynamic Options</span></span>  
  
### <a name="wqlquerysource--direct-input"></a><span data-ttu-id="68a47-138">WQLQuerySource = Input diretto</span><span class="sxs-lookup"><span data-stu-id="68a47-138">WQLQuerySource = Direct input</span></span>  
 <span data-ttu-id="68a47-139">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="68a47-139">**WQLQuerySource**</span></span>  
 <span data-ttu-id="68a47-140">Consente di specificare una query o di immettere una query nella finestra di dialogo **Query WQL** visualizzata facendo clic sul pulsante (...).</span><span class="sxs-lookup"><span data-stu-id="68a47-140">Provide a query, or click the ellipsis button (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysource--file-connection"></a><span data-ttu-id="68a47-141">WQLQuerySource = Connessione file</span><span class="sxs-lookup"><span data-stu-id="68a47-141">WQLQuerySource = File connection</span></span>  
 <span data-ttu-id="68a47-142">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="68a47-142">**WQLQuerySource**</span></span>  
 <span data-ttu-id="68a47-143">Selezionare una gestione connessione file nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="68a47-143">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="68a47-144">**Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md), [Editor gestione connessione file](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="68a47-144">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysource--variable"></a><span data-ttu-id="68a47-145">WQLQuerySource = Variabile</span><span class="sxs-lookup"><span data-stu-id="68a47-145">WQLQuerySource = Variable</span></span>  
 <span data-ttu-id="68a47-146">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="68a47-146">**WQLQuerySource**</span></span>  
 <span data-ttu-id="68a47-147">Selezionare una variabile nell'elenco oppure fare clic su \<**New variable...**> per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="68a47-147">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="68a47-148">**Argomenti correlati:** [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Aggiungere una variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="68a47-148">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a47-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68a47-149">See Also</span></span>  
 <span data-ttu-id="68a47-150">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="68a47-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="68a47-151">[Editor attività Monitoraggio eventi WMI &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="68a47-151">[WMI Event Watcher Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="68a47-152">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="68a47-152">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="68a47-153">Attività Lettore di dati WMI</span><span class="sxs-lookup"><span data-stu-id="68a47-153">WMI Data Reader Task</span></span>](control-flow/wmi-data-reader-task.md)  
  
  
