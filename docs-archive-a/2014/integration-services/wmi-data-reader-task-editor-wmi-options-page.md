---
title: Editor attività lettore di dati WMI (pagina Opzioni WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.wmiquery.f1
helpviewer_keywords:
- WMI Data Reader Task Editor
ms.assetid: 4b8d4716-882d-41b0-b77e-e0e2741a2cd5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfb28e7f8f352f708085bf664757391a05869752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636762"
---
# <a name="wmi-data-reader-task-editor-wmi-options-page"></a><span data-ttu-id="b5d94-102">Editor attività Lettore di dati WMI (pagina Opzioni WMI)</span><span class="sxs-lookup"><span data-stu-id="b5d94-102">WMI Data Reader Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="b5d94-103">Usare la pagina **Opzioni WMI** della finestra di dialogo **Editor attività Lettore di dati WMI** per specificare l'origine della query WQL (Windows Management Instrumentation Query Language) e la destinazione del risultato della query.</span><span class="sxs-lookup"><span data-stu-id="b5d94-103">Use the **WMI Options** page of the **WMI Data Reader Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and the destination of the query result.</span></span>  
  
 <span data-ttu-id="b5d94-104">Per ulteriori informazioni su questa attività, vedere [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span><span class="sxs-lookup"><span data-stu-id="b5d94-104">To learn about this task, see [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span></span> <span data-ttu-id="b5d94-105">Per altre informazioni su WQL (WMI Query Language), vedere l'argomento relativo a WMI (Windows Management Instrumentation) [Query con WQL](https://go.microsoft.com/fwlink/?LinkId=79045)in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="b5d94-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="b5d94-106">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="b5d94-106">Static Options</span></span>  
 <span data-ttu-id="b5d94-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="b5d94-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="b5d94-108">Selezionare una gestione connessione WMI nell'elenco oppure fare clic su \<**New WMI Connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="b5d94-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="b5d94-109">**Argomenti correlati:** [Gestione connessione WMI](connection-manager/wmi-connection-manager.md), [Editor gestione connessione WMI](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="b5d94-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="b5d94-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="b5d94-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="b5d94-111">Consente di selezionare il tipo di origine della query WQL eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="b5d94-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="b5d94-112">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b5d94-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="b5d94-113">valore</span><span class="sxs-lookup"><span data-stu-id="b5d94-113">Value</span></span>|<span data-ttu-id="b5d94-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5d94-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b5d94-115">**Input diretto**</span><span class="sxs-lookup"><span data-stu-id="b5d94-115">**Direct input**</span></span>|<span data-ttu-id="b5d94-116">Consente di impostare l'origine su una query WQL.</span><span class="sxs-lookup"><span data-stu-id="b5d94-116">Set the source to a WQL query.</span></span> <span data-ttu-id="b5d94-117">Selezionando questo valore viene visualizzata l'opzione dinamica **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="b5d94-117">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="b5d94-118">**Connessione file**</span><span class="sxs-lookup"><span data-stu-id="b5d94-118">**File connection**</span></span>|<span data-ttu-id="b5d94-119">Consente di selezionare un file contenente la query WQL.</span><span class="sxs-lookup"><span data-stu-id="b5d94-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="b5d94-120">Selezionando questo valore viene visualizzata l'opzione dinamica **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="b5d94-120">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="b5d94-121">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="b5d94-121">**Variable**</span></span>|<span data-ttu-id="b5d94-122">Consente di impostare l'origine su una variabile che definisce la query WQL.</span><span class="sxs-lookup"><span data-stu-id="b5d94-122">Set the source to a variable that defines the WQL query.</span></span> <span data-ttu-id="b5d94-123">Selezionando questo valore viene visualizzata l'opzione dinamica **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="b5d94-123">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
  
 <span data-ttu-id="b5d94-124">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="b5d94-124">**OutputType**</span></span>  
 <span data-ttu-id="b5d94-125">Consente di specificare se l'output deve essere una tabella di dati, un valore di proprietà o un nome e valore di proprietà.</span><span class="sxs-lookup"><span data-stu-id="b5d94-125">Specify whether the output should be a data table, property value, or property name and value.</span></span>  
  
 <span data-ttu-id="b5d94-126">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="b5d94-126">**OverwriteDestination**</span></span>  
 <span data-ttu-id="b5d94-127">Consente di specificare se mantenere, sovrascrivere o accodare ai dati originali nel file o nella variabile di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b5d94-127">Specifies whether to keep, overwrite, or append to the original data in the destination file or variable.</span></span>  
  
 <span data-ttu-id="b5d94-128">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="b5d94-128">**DestinationType**</span></span>  
 <span data-ttu-id="b5d94-129">Consente di selezionare il tipo di destinazione della query WQL eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="b5d94-129">Select the destination type of the WQL query that the task runs.</span></span> <span data-ttu-id="b5d94-130">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b5d94-130">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="b5d94-131">valore</span><span class="sxs-lookup"><span data-stu-id="b5d94-131">Value</span></span>|<span data-ttu-id="b5d94-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5d94-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b5d94-133">**Connessione file**</span><span class="sxs-lookup"><span data-stu-id="b5d94-133">**File connection**</span></span>|<span data-ttu-id="b5d94-134">Selezionare un file in cui salvare i risultati della query WQL.</span><span class="sxs-lookup"><span data-stu-id="b5d94-134">Select a file to save the results of the WQL query in.</span></span> <span data-ttu-id="b5d94-135">Selezionando questo valore viene visualizzata l'opzione dinamica **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="b5d94-135">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
|<span data-ttu-id="b5d94-136">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="b5d94-136">**Variable**</span></span>|<span data-ttu-id="b5d94-137">Impostare la variabile in cui archiviare i risultati della query WQL.</span><span class="sxs-lookup"><span data-stu-id="b5d94-137">Set the variable to store the results of the WQL query in.</span></span> <span data-ttu-id="b5d94-138">Selezionando questo valore viene visualizzata l'opzione dinamica **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="b5d94-138">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
  
## <a name="wqlquerysourcetype-dynamic-options"></a><span data-ttu-id="b5d94-139">Opzioni dinamiche di WQLQuerySourceType</span><span class="sxs-lookup"><span data-stu-id="b5d94-139">WQLQuerySourceType Dynamic Options</span></span>  
  
### <a name="wqlquerysourcetype--direct-input"></a><span data-ttu-id="b5d94-140">WQLQuerySourceType = Input diretto</span><span class="sxs-lookup"><span data-stu-id="b5d94-140">WQLQuerySourceType = Direct input</span></span>  
 <span data-ttu-id="b5d94-141">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="b5d94-141">**WQLQuerySource**</span></span>  
 <span data-ttu-id="b5d94-142">Consente di specificare una query o di immettere una query nella finestra di dialogo **Query WQL** visualizzata facendo clic sul pulsante con i puntini di sospensione (...).</span><span class="sxs-lookup"><span data-stu-id="b5d94-142">Provide a query, or click the ellipsis (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysourcetype--file-connection"></a><span data-ttu-id="b5d94-143">WQLQuerySourceType = Connessione file</span><span class="sxs-lookup"><span data-stu-id="b5d94-143">WQLQuerySourceType = File connection</span></span>  
 <span data-ttu-id="b5d94-144">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="b5d94-144">**WQLQuerySource**</span></span>  
 <span data-ttu-id="b5d94-145">Selezionare una gestione connessione file nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="b5d94-145">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="b5d94-146">**Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md), [Editor gestione connessione file](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="b5d94-146">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysourcetype--variable"></a><span data-ttu-id="b5d94-147">WQLQuerySourceType = Variabile</span><span class="sxs-lookup"><span data-stu-id="b5d94-147">WQLQuerySourceType = Variable</span></span>  
 <span data-ttu-id="b5d94-148">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="b5d94-148">**WQLQuerySource**</span></span>  
 <span data-ttu-id="b5d94-149">Selezionare una variabile nell'elenco oppure fare clic su \<**New variable...**> per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="b5d94-149">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="b5d94-150">**Argomenti correlati:** [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Aggiungere una variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="b5d94-150">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="destinationtype-dynamic-options"></a><span data-ttu-id="b5d94-151">Opzioni dinamiche di DestinationType</span><span class="sxs-lookup"><span data-stu-id="b5d94-151">DestinationType Dynamic Options</span></span>  
  
### <a name="destinationtype--file-connection"></a><span data-ttu-id="b5d94-152">DestinationType = Connessione file</span><span class="sxs-lookup"><span data-stu-id="b5d94-152">DestinationType = File connection</span></span>  
 <span data-ttu-id="b5d94-153">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="b5d94-153">**Destination**</span></span>  
 <span data-ttu-id="b5d94-154">Selezionare una gestione connessione file nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="b5d94-154">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="b5d94-155">**Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md), [Editor gestione connessione file](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="b5d94-155">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="destinationtype--variable"></a><span data-ttu-id="b5d94-156">DestinationType = Variabile</span><span class="sxs-lookup"><span data-stu-id="b5d94-156">DestinationType = Variable</span></span>  
 <span data-ttu-id="b5d94-157">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="b5d94-157">**Destination**</span></span>  
 <span data-ttu-id="b5d94-158">Selezionare una variabile nell'elenco oppure fare clic su \<**New variable...**> per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="b5d94-158">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="b5d94-159">**Argomenti correlati:** [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Aggiungere una variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="b5d94-159">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d94-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5d94-160">See Also</span></span>  
 <span data-ttu-id="b5d94-161">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b5d94-161">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b5d94-162">[Editor attività lettore di dati WMI &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="b5d94-162">[WMI Data Reader Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="b5d94-163">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="b5d94-163">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="b5d94-164">Attività Monitoraggio eventi WMI</span><span class="sxs-lookup"><span data-stu-id="b5d94-164">WMI Event Watcher Task</span></span>](control-flow/wmi-event-watcher-task.md)  
  
  
