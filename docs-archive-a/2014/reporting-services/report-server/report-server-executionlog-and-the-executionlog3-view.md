---
title: Log di esecuzione del server di report e visualizzazione ExecutionLog3 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- logs [Reporting Services], execution
- execution logs [Reporting Services]
ms.assetid: a7ead67d-1404-4e67-97e7-4c7b0d942070
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 868f8497e61c17662cb621850cdb8aee74c82706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626008"
---
# <a name="report-server-execution-log-and-the-executionlog3-view"></a><span data-ttu-id="3bad6-102">Log di esecuzione del server di report e la vista ExecutionLog3</span><span class="sxs-lookup"><span data-stu-id="3bad6-102">Report Server Execution Log and the ExecutionLog3 View</span></span>
  <span data-ttu-id="3bad6-103">Nel log di esecuzione del server di report sono incluse informazioni sui report eseguiti in uno o più server in una distribuzione con scalabilità orizzontale in modalità nativa o in una farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3bad6-103">The report server execution log contains information about the reports that execute on the server or on multiple servers in a native mode scale-out deployment or a SharePoint farm.</span></span> <span data-ttu-id="3bad6-104">Il log consente di conoscere la frequenza con cui un report viene richiesto, i formati di output più usati e i millisecondi dedicati a ogni fase dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3bad6-104">You can use the report execution log to find out how often a report is requested, what output formats are used the most, and how many milliseconds of processing time is spent on each processing phase.</span></span> <span data-ttu-id="3bad6-105">Nel log, inoltre, sono contenute informazioni sul tempo impiegato per l'esecuzione di una query del set di dati di un report e su quello speso per l'elaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="3bad6-105">The log contains information on the length of time spent executing a report's dataset query and the time spent processing the data.</span></span> <span data-ttu-id="3bad6-106">Se si è un amministratore del server di report, è possibile esaminare le informazioni sul log, identificare le attività con esecuzione prolungata e inviare suggerimenti agli autori del report sulle aree del report, set di dati o elaborazione, che potrebbero essere migliorate.</span><span class="sxs-lookup"><span data-stu-id="3bad6-106">If you are a report server administrator, you can review the log information and identify long running tasks and make suggestions to the report authors on the areas of the report (dataset or processing) they may be able to improve.</span></span>  
  
 <span data-ttu-id="3bad6-107">Nei server di report configurati per la modalità SharePoint possono essere usati anche i log ULS di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3bad6-107">Report servers configured for SharePoint mode, can also utilize the SharePoint ULS logs.</span></span> <span data-ttu-id="3bad6-108">Per altre informazioni, vedere [Abilitare gli eventi di Reporting Services per il log di traccia di SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span><span class="sxs-lookup"><span data-stu-id="3bad6-108">For more information, see [Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md)</span></span>  
  
##  <a name="viewing-log-information"></a><a name="bkmk_top"></a> <span data-ttu-id="3bad6-109">Visualizzazione delle informazioni sul log di esecuzione</span><span class="sxs-lookup"><span data-stu-id="3bad6-109">Viewing Log Information</span></span>  
 <span data-ttu-id="3bad6-110">Nel server di report vengono registrati i dati sull'esecuzione dei report in una tabella interna del database.</span><span class="sxs-lookup"><span data-stu-id="3bad6-110">The report server execution logs data about report execution into an internal database table.</span></span> <span data-ttu-id="3bad6-111">Le informazioni della tabella sono disponibili dalle viste SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3bad6-111">The information from the table is available from SQL Server views.</span></span>  
  
 <span data-ttu-id="3bad6-112">Il log di esecuzione del report viene archiviato nel database del server di report denominato **ReportServer**per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3bad6-112">The report execution log is stored in the report server database that by default is named **ReportServer**.</span></span> <span data-ttu-id="3bad6-113">Nelle viste SQL sono incluse le informazioni sul log di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bad6-113">The SQL views provide the execution log information.</span></span> <span data-ttu-id="3bad6-114">Le viste "2" e "3" sono state aggiunte in versioni più recenti e contengono nuovi campi oppure campi con nomi più descrittivi rispetto alle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="3bad6-114">The "2" and "3" views were added in more recent releases and contain new fields or they contain fields with friendlier names than the previous releases.</span></span> <span data-ttu-id="3bad6-115">Le viste precedenti rimangono nel prodotto, così non vengono influenzate le applicazioni personalizzate basata su di esse.</span><span class="sxs-lookup"><span data-stu-id="3bad6-115">The older views remain in the product so custom applications that depend on them are not impacted.</span></span> <span data-ttu-id="3bad6-116">Se non si dispone di una dipendenza da una vista precedente, ad esempio ExecutionLog, si consiglia di usare la vista più recente, ExecutionLog**3**.</span><span class="sxs-lookup"><span data-stu-id="3bad6-116">If you do not have a dependence on an older view, for example ExecutionLog, it is recommended you use the most recent view, ExecutionLog**3**.</span></span>  
  
 <span data-ttu-id="3bad6-117">In questo argomento</span><span class="sxs-lookup"><span data-stu-id="3bad6-117">In this topic:</span></span>  
  
-   [<span data-ttu-id="3bad6-118">Impostazioni di configurazione per un server di report in modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="3bad6-118">Configuration Settings for a SharePoint mode Report Server</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="3bad6-119">Impostazioni di configurazione per un server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="3bad6-119">Configuration Settings for a Native Mode Report Server</span></span>](#bkmk_native)  
  
-   [<span data-ttu-id="3bad6-120">Campi del log (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="3bad6-120">Log Fields (ExecutionLog3)</span></span>](#bkmk_executionlog3)  
  
-   [<span data-ttu-id="3bad6-121">Campo AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="3bad6-121">The AdditionalInfo Field</span></span>](#bkmk_additionalinfo)  
  
-   [<span data-ttu-id="3bad6-122">Campi del log (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="3bad6-122">Log Fields (ExecutionLog2)</span></span>](#bkmk_executionlog2)  
  
-   [<span data-ttu-id="3bad6-123">Campi del log (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="3bad6-123">Log Fields (ExecutionLog)</span></span>](#bkmk_executionlog)  
  
##  <a name="configuration-settings-for-a-sharepoint-mode-report-server"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="3bad6-124">Impostazioni di configurazione per un server di report in modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="3bad6-124">Configuration Settings for a SharePoint mode Report Server</span></span>  
 <span data-ttu-id="3bad6-125">È possibile abilitare o disabilitare la registrazione per l'esecuzione del report dalle impostazioni di sistema di un'applicazione del servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bad6-125">You can turn report execution logging on or off from the system settings of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
 <span data-ttu-id="3bad6-126">Per impostazione predefinita, le voci di log vengono mantenute per 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="3bad6-126">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="3bad6-127">Ogni giorno, alle 14.00, vengono rimosse le voci antecedenti</span><span class="sxs-lookup"><span data-stu-id="3bad6-127">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="3bad6-128">.</span><span class="sxs-lookup"><span data-stu-id="3bad6-128">every day.</span></span> <span data-ttu-id="3bad6-129">In un'installazione datata saranno disponibili solo 60 giorni di informazioni in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="3bad6-129">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="3bad6-130">Non è possibile impostare limiti sul numero di righe o sul tipo di voci registrate.</span><span class="sxs-lookup"><span data-stu-id="3bad6-130">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="3bad6-131">**Per abilitare la registrazione per l'esecuzione:**</span><span class="sxs-lookup"><span data-stu-id="3bad6-131">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="3bad6-132">Nel gruppo **Gestione applicazioni** di Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio** .</span><span class="sxs-lookup"><span data-stu-id="3bad6-132">From SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="3bad6-133">Fare clic sul nome dell'applicazione del servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] da configurare.</span><span class="sxs-lookup"><span data-stu-id="3bad6-133">Click the name of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application you want to configure.</span></span>  
  
3.  <span data-ttu-id="3bad6-134">Fare clic su **Impostazioni sistema**.</span><span class="sxs-lookup"><span data-stu-id="3bad6-134">Click **System Settings**.</span></span>  
  
4.  <span data-ttu-id="3bad6-135">Selezionare **Abilita registrazione di esecuzione** nella sezione **Registrazione** .</span><span class="sxs-lookup"><span data-stu-id="3bad6-135">Select **Enable Execution Logging** in the **Logging** section.</span></span>  
  
5.  <span data-ttu-id="3bad6-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bad6-136">Click **OK**.</span></span>  
  
 <span data-ttu-id="3bad6-137">**Per abilitare la registrazione dettagliata:**</span><span class="sxs-lookup"><span data-stu-id="3bad6-137">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="3bad6-138">La registrazione deve essere abilitata come descritto nei passaggi precedenti e successivamente completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bad6-138">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="3bad6-139">Nella pagina **Impostazioni sistema** dell'applicazione del servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] trovare la sezione **Definito dall'utente** .</span><span class="sxs-lookup"><span data-stu-id="3bad6-139">From the **System Settings** page of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] services application, find the **User-defined** section.</span></span>  
  
2.  <span data-ttu-id="3bad6-140">Impostare **ExecutionLogLevel** su **verbose**(dettagliato).</span><span class="sxs-lookup"><span data-stu-id="3bad6-140">Change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="3bad6-141">Si tratta di un campo di immissione testo e i due valori possibili sono **verbose** (dettagliato) e **normal**(normale).</span><span class="sxs-lookup"><span data-stu-id="3bad6-141">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="configuration-settings-for-a-native-mode-report-server"></a><a name="bkmk_native"></a> <span data-ttu-id="3bad6-142">Impostazioni di configurazione per un server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="3bad6-142">Configuration Settings for a Native Mode Report Server</span></span>  
 <span data-ttu-id="3bad6-143">È possibile abilitare o disabilitare la registrazione per l'esecuzione del report dalla pagina Proprietà server in SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="3bad6-143">You can turn report execution logging on or off from the Server Properties page in SQL Server Management Studio.</span></span> <span data-ttu-id="3bad6-144">**EnableExecutionLogging** è la proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="3bad6-144">The **EnableExecutionLogging** is and Advanced property.</span></span>  
  
 <span data-ttu-id="3bad6-145">Per impostazione predefinita, le voci di log vengono mantenute per 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="3bad6-145">By default, log entries are kept 60 days.</span></span> <span data-ttu-id="3bad6-146">Ogni giorno, alle 14.00, vengono rimosse le voci antecedenti</span><span class="sxs-lookup"><span data-stu-id="3bad6-146">Entries that exceed this date are removed at 2:00 A.M.</span></span> <span data-ttu-id="3bad6-147">.</span><span class="sxs-lookup"><span data-stu-id="3bad6-147">every day.</span></span> <span data-ttu-id="3bad6-148">In un'installazione datata saranno disponibili solo 60 giorni di informazioni in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="3bad6-148">On a mature installation, only 60 days of information will be available at any given time.</span></span>  
  
 <span data-ttu-id="3bad6-149">Non è possibile impostare limiti sul numero di righe o sul tipo di voci registrate.</span><span class="sxs-lookup"><span data-stu-id="3bad6-149">You cannot set limits on the number of rows or on the type of entries that are logged.</span></span>  
  
 <span data-ttu-id="3bad6-150">**Per abilitare la registrazione per l'esecuzione:**</span><span class="sxs-lookup"><span data-stu-id="3bad6-150">**To enable execution logging:**</span></span>  
  
1.  <span data-ttu-id="3bad6-151">Avviare SQL Server Management Studio con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="3bad6-151">Start SQL Server Management Studio with administrative privileges.</span></span> <span data-ttu-id="3bad6-152">Ad esempio, fare clic con il pulsante destro del mouse sull'icona di Management Studio e scegliere "Esegui come amministratore".</span><span class="sxs-lookup"><span data-stu-id="3bad6-152">For example right-click the Management Studio icon and click 'Run as administrator'.</span></span>  
  
2.  <span data-ttu-id="3bad6-153">Connettersi al server di report desiderato.</span><span class="sxs-lookup"><span data-stu-id="3bad6-153">Connect to the desired report server.</span></span>  
  
3.  <span data-ttu-id="3bad6-154">Fare clic con il pulsante destro del mouse sul nome del server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3bad6-154">Right-click the server name and click **Properties**.</span></span> <span data-ttu-id="3bad6-155">Se l'opzione Proprietà è disabilitata, verificare che SQL Server Management Studio venga eseguito con i privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="3bad6-155">If the Properties option is disabled, verify you ran SQL Server Management Studio with administrative privileges.</span></span>  
  
4.  <span data-ttu-id="3bad6-156">Fare clic sulla pagina **Registrazione** .</span><span class="sxs-lookup"><span data-stu-id="3bad6-156">Click the **Logging** page.</span></span>  
  
5.  <span data-ttu-id="3bad6-157">Selezionare **Abilita la registrazione per l'esecuzione di report**.</span><span class="sxs-lookup"><span data-stu-id="3bad6-157">Select **Enable report execution Logging**.</span></span>  
  
 <span data-ttu-id="3bad6-158">**Per abilitare la registrazione dettagliata:**</span><span class="sxs-lookup"><span data-stu-id="3bad6-158">**To enable verbose logging:**</span></span>  
  
 <span data-ttu-id="3bad6-159">La registrazione deve essere abilitata come descritto nei passaggi precedenti e successivamente completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bad6-159">You need to enable logging as described in the previous steps and then complete the following:</span></span>  
  
1.  <span data-ttu-id="3bad6-160">Scegliere **Avanzate** nella finestra di dialogo **Proprietà server** .</span><span class="sxs-lookup"><span data-stu-id="3bad6-160">From the **Server Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="3bad6-161">Nella sezione **Definito dall'utente** impostare **ExecutionLogLevel** su **verbose**(dettagliato).</span><span class="sxs-lookup"><span data-stu-id="3bad6-161">In the **User-defined** section, change the **ExecutionLogLevel** to **verbose**.</span></span> <span data-ttu-id="3bad6-162">Si tratta di un campo di immissione testo e i due valori possibili sono **verbose** (dettagliato) e **normal**(normale).</span><span class="sxs-lookup"><span data-stu-id="3bad6-162">This field is a text entry field and the two possible values are **verbose** and **normal**.</span></span>  
  
##  <a name="log-fields-executionlog3"></a><a name="bkmk_executionlog3"></a> <span data-ttu-id="3bad6-163">Campi del log (ExecutionLog3)</span><span class="sxs-lookup"><span data-stu-id="3bad6-163">Log Fields (ExecutionLog3)</span></span>  
 <span data-ttu-id="3bad6-164">In questa vista è stato aggiunto un nodo di diagnostica delle prestazioni all'interno della colonna **AdditionalInfo** basata su XML.</span><span class="sxs-lookup"><span data-stu-id="3bad6-164">This view added additional performance diagnostics node inside the XML based **AdditionalInfo** column.</span></span> <span data-ttu-id="3bad6-165">La colonna AdditionalInfo contiene una struttura XML di campi aggiuntivi di informazioni in una relazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="3bad6-165">The AdditionalInfo column contains an XML structure of 1 to many additional fields of information.</span></span> <span data-ttu-id="3bad6-166">Di seguito è riportato un esempio di istruzione Transact SQL per recuperare righe dalla vista ExecutionLog3.</span><span class="sxs-lookup"><span data-stu-id="3bad6-166">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog3.</span></span> <span data-ttu-id="3bad6-167">Nell'esempio si presuppone che il database del server di report sia denominato **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="3bad6-167">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog3 order by TimeStart DESC  
```  
  
 <span data-ttu-id="3bad6-168">Nella tabella seguente vengono descritti i dati acquisiti nel log di esecuzione del report:</span><span class="sxs-lookup"><span data-stu-id="3bad6-168">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="3bad6-169">Colonna</span><span class="sxs-lookup"><span data-stu-id="3bad6-169">Column</span></span>|<span data-ttu-id="3bad6-170">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3bad6-170">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3bad6-171">InstanceName</span><span class="sxs-lookup"><span data-stu-id="3bad6-171">InstanceName</span></span>|<span data-ttu-id="3bad6-172">Nome dell'istanza del server di report tramite cui è stata gestita la richiesta.</span><span class="sxs-lookup"><span data-stu-id="3bad6-172">Name of the report server instance that handled the request.</span></span> <span data-ttu-id="3bad6-173">Se nell'ambiente è disponibile più di un server di report, è possibile analizzare la distribuzione di InstanceName per monitorare e determinare se tramite il servizio di bilanciamento del carico di rete vengono distribuite richieste attraverso i server di report come previsto.</span><span class="sxs-lookup"><span data-stu-id="3bad6-173">If your environment has more than one report server, you can analyze the InstanceName distribution to monitor and determine if your network-load balancer distributes requests across report servers as expected.</span></span>|  
|<span data-ttu-id="3bad6-174">ItemPath</span><span class="sxs-lookup"><span data-stu-id="3bad6-174">ItemPath</span></span>|<span data-ttu-id="3bad6-175">Percorso in cui viene archiviato un report o un elemento del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-175">Path of where a report or report item is stored.</span></span>|  
|<span data-ttu-id="3bad6-176">UserName</span><span class="sxs-lookup"><span data-stu-id="3bad6-176">UserName</span></span>|<span data-ttu-id="3bad6-177">Identificatore dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3bad6-177">User identifier.</span></span>|  
|<span data-ttu-id="3bad6-178">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="3bad6-178">ExecutionID</span></span>|<span data-ttu-id="3bad6-179">L'identificatore interno associato a una richiesta.</span><span class="sxs-lookup"><span data-stu-id="3bad6-179">The internal identifier associated with a request.</span></span> <span data-ttu-id="3bad6-180">Le richieste nelle sessioni dello stesso utente condividono lo stesso ID esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bad6-180">Requests on the same user sessions share the same execution id.</span></span>|  
|<span data-ttu-id="3bad6-181">RequestType</span><span class="sxs-lookup"><span data-stu-id="3bad6-181">RequestType</span></span>|<span data-ttu-id="3bad6-182">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="3bad6-182">Possible Values:</span></span><br /><span data-ttu-id="3bad6-183">**Interattivo**</span><span class="sxs-lookup"><span data-stu-id="3bad6-183">**Interactive**</span></span><br /><span data-ttu-id="3bad6-184">**Sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="3bad6-184">**Subscription**</span></span><br /><br /> <br /><br /> <span data-ttu-id="3bad6-185">L'analisi dei dati del log filtrati in base RequestType=Subscription e ordinati per TimeStart può rivelare periodi di utilizzo eccessivo della sottoscrizione ed è pertanto necessario modificare alcune delle sottoscrizioni del report a un'ora diversa.</span><span class="sxs-lookup"><span data-stu-id="3bad6-185">Analyzing log data filtered by RequestType=Subscription and sorted by TimeStart may reveal periods of heavy subscription usage and you may want to modify some of the report subscriptions to a different time.</span></span>|  
|<span data-ttu-id="3bad6-186">Format</span><span class="sxs-lookup"><span data-stu-id="3bad6-186">Format</span></span>|<span data-ttu-id="3bad6-187">Formato di rendering.</span><span class="sxs-lookup"><span data-stu-id="3bad6-187">Rendering format.</span></span>|  
|<span data-ttu-id="3bad6-188">Parametri</span><span class="sxs-lookup"><span data-stu-id="3bad6-188">Parameters</span></span>|<span data-ttu-id="3bad6-189">Valori dei parametri usati per l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-189">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="3bad6-190">ItemAction</span><span class="sxs-lookup"><span data-stu-id="3bad6-190">ItemAction</span></span>|<span data-ttu-id="3bad6-191">Valori possibili:</span><span class="sxs-lookup"><span data-stu-id="3bad6-191">Possible values:</span></span><br /><br /> <span data-ttu-id="3bad6-192">**Rendering**</span><span class="sxs-lookup"><span data-stu-id="3bad6-192">**Render**</span></span><br /><br /> <span data-ttu-id="3bad6-193">**Sort**</span><span class="sxs-lookup"><span data-stu-id="3bad6-193">**Sort**</span></span><br /><br /> <span data-ttu-id="3bad6-194">**BookMarkNavigation**</span><span class="sxs-lookup"><span data-stu-id="3bad6-194">**BookMarkNavigation**</span></span><br /><br /> <span data-ttu-id="3bad6-195">**DocumentNavigation**</span><span class="sxs-lookup"><span data-stu-id="3bad6-195">**DocumentNavigation**</span></span><br /><br /> <span data-ttu-id="3bad6-196">**GetDocumentMap**</span><span class="sxs-lookup"><span data-stu-id="3bad6-196">**GetDocumentMap**</span></span><br /><br /> <span data-ttu-id="3bad6-197">**FindString**</span><span class="sxs-lookup"><span data-stu-id="3bad6-197">**Findstring**</span></span><br /><br /> <span data-ttu-id="3bad6-198">**Eseguire**</span><span class="sxs-lookup"><span data-stu-id="3bad6-198">**Execute**</span></span><br /><br /> <span data-ttu-id="3bad6-199">**RenderEdit**</span><span class="sxs-lookup"><span data-stu-id="3bad6-199">**RenderEdit**</span></span>|  
|<span data-ttu-id="3bad6-200">TimeStart</span><span class="sxs-lookup"><span data-stu-id="3bad6-200">TimeStart</span></span>|<span data-ttu-id="3bad6-201">Ora di inizio e ora dell'arresto, che indicano la durata dell'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-201">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="3bad6-202">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="3bad6-202">TimeEnd</span></span>||  
|<span data-ttu-id="3bad6-203">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="3bad6-203">TimeDataRetrieval</span></span>|<span data-ttu-id="3bad6-204">Numero di millisecondi impiegati per il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="3bad6-204">Number of milliseconds spent retrieving the data.</span></span>|  
|<span data-ttu-id="3bad6-205">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="3bad6-205">TimeProcessing</span></span>|<span data-ttu-id="3bad6-206">Numero di millisecondi impiegati per l'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-206">Number of milliseconds spent processing the report.</span></span>|  
|<span data-ttu-id="3bad6-207">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="3bad6-207">TimeRendering</span></span>|<span data-ttu-id="3bad6-208">Numero di millisecondi impiegati per il rendering del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-208">Number of milliseconds spent rendering the report.</span></span>|  
|<span data-ttu-id="3bad6-209">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="3bad6-209">Source</span></span>|<span data-ttu-id="3bad6-210">Origine dell'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-210">Source of the report execution.</span></span> <span data-ttu-id="3bad6-211">Valori possibili:</span><span class="sxs-lookup"><span data-stu-id="3bad6-211">Possible values:</span></span><br /><br /> <span data-ttu-id="3bad6-212">**Live**</span><span class="sxs-lookup"><span data-stu-id="3bad6-212">**Live**</span></span><br /><br /> <span data-ttu-id="3bad6-213">**Cache**: indica un'esecuzione memorizzata nella cache, ad esempio, le query del set di dati non vengono eseguite in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="3bad6-213">**Cache**: Indicates a cached execution, for example, dataset queries are not executed live.</span></span><br /><br /> <span data-ttu-id="3bad6-214">**Snapshot**</span><span class="sxs-lookup"><span data-stu-id="3bad6-214">**Snapshot**</span></span><br /><br /> <span data-ttu-id="3bad6-215">**History**</span><span class="sxs-lookup"><span data-stu-id="3bad6-215">**History**</span></span><br /><br /> <span data-ttu-id="3bad6-216">**Adhoc** : indica un report drill-through basato su un modello di report generato dinamicamente o un report di Generatore report visualizzato in anteprima su un client che utilizza il server di report per l'elaborazione e il rendering.</span><span class="sxs-lookup"><span data-stu-id="3bad6-216">**AdHoc** : Indicates either a dynamically generated report model based drill through report, or a Report Builder report that is previewed on a client utilizing the report server for processing and rendering.</span></span><br /><br /> <span data-ttu-id="3bad6-217">**Session**: indica una richiesta di completamento in una sessione già stabilita.</span><span class="sxs-lookup"><span data-stu-id="3bad6-217">**Session**: Indicates a follow up request within an already established session.</span></span>  <span data-ttu-id="3bad6-218">Ad esempio la richiesta iniziale è di visualizzare la pagina 1 e la richiesta di completamento è di esportare in Excel con lo stato della sessione corrente.</span><span class="sxs-lookup"><span data-stu-id="3bad6-218">For example the initial request is to view page 1, and the follow up request is to export to Excel with the current session state.</span></span><br /><br /> <span data-ttu-id="3bad6-219">**RDCE**: indica un'estensione per la personalizzazione della definizione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-219">**Rdce**:  Indicates a Report Definition Customization Extension.</span></span> <span data-ttu-id="3bad6-220">Un'estensione personalizzata RDCE consente di personalizzare in modo dinamico la definizione di un report prima che venga passata al motore di elaborazione all'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-220">An RDCE custom extension can dynamically customize a report definition before it is passed to the processing engine upon report execution.</span></span>|  
|<span data-ttu-id="3bad6-221">Stato</span><span class="sxs-lookup"><span data-stu-id="3bad6-221">Status</span></span>|<span data-ttu-id="3bad6-222">Stato (rsSuccess oppure un codice di errore; in caso di più errori, viene registrato solo il primo).</span><span class="sxs-lookup"><span data-stu-id="3bad6-222">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="3bad6-223">ByteCount</span><span class="sxs-lookup"><span data-stu-id="3bad6-223">ByteCount</span></span>|<span data-ttu-id="3bad6-224">Dimensione dei report visualizzabili, in byte.</span><span class="sxs-lookup"><span data-stu-id="3bad6-224">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="3bad6-225">RowCount</span><span class="sxs-lookup"><span data-stu-id="3bad6-225">RowCount</span></span>|<span data-ttu-id="3bad6-226">Numero di righe restituite dalle query.</span><span class="sxs-lookup"><span data-stu-id="3bad6-226">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="3bad6-227">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="3bad6-227">AdditionalInfo</span></span>|<span data-ttu-id="3bad6-228">Contenitore di proprietà XML in cui sono incluse informazioni aggiuntive sull'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bad6-228">An XML property bag containing additional information about the execution.</span></span> <span data-ttu-id="3bad6-229">Il contenuto può essere diverso per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="3bad6-229">The contents can be different for each row.</span></span>|  
  
##  <a name="the-additionalinfo-field"></a><a name="bkmk_additionalinfo"></a> <span data-ttu-id="3bad6-230">Campo AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="3bad6-230">The AdditionalInfo Field</span></span>  
 <span data-ttu-id="3bad6-231">Il campo AdditionalInfo è un contenitore o struttura di proprietà XML contenente informazioni aggiuntive sull'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bad6-231">The AdditionalInfo field is an XML property bag or structure containing additional information about the execution.</span></span> <span data-ttu-id="3bad6-232">Il contenuto può essere diverso per ogni riga del log.</span><span class="sxs-lookup"><span data-stu-id="3bad6-232">The contents can be different for each row in the log.</span></span>  
  
 <span data-ttu-id="3bad6-233">Le tabelle seguenti sono esempi del contenuto del campo AddtionalInfo per la registrazione standard e dettagliata:</span><span class="sxs-lookup"><span data-stu-id="3bad6-233">The following tables are examples  of the contents of the AddtionalInfo field for both standard and verbose logging:</span></span>  
  
 <span data-ttu-id="3bad6-234">**Esempio di registrazione standard di AddtionalInfo**</span><span class="sxs-lookup"><span data-stu-id="3bad6-234">**Standard logging example of AddtionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>147</ConnectionOpenTime>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>642</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>63</ExecuteReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>157</TotalTimeDataRetrieval>  
          <ExecuteReaderTime>60</ExecuteReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="3bad6-235">**Esempio di registrazione dettagliata di AddtionalInfo**</span><span class="sxs-lookup"><span data-stu-id="3bad6-235">**Verbose logging example of AdditionalInfo**</span></span>  
  
```  
<AdditionalInfo>  
  <ProcessingEngine>2</ProcessingEngine>  
  <ScalabilityTime>  
    <Pagination>0</Pagination>  
    <Processing>0</Processing>  
  </ScalabilityTime>  
  <EstimatedMemoryUsageKB>  
    <Pagination>0</Pagination>  
    <Processing>6</Processing>  
  </EstimatedMemoryUsageKB>  
  <DataExtension>  
    <SQL>1</SQL>  
  </DataExtension>  
  <Connections>  
    <Connection>  
      <ConnectionOpenTime>127</ConnectionOpenTime>  
      <DataSource>  
        <Name>DataSource1</Name>  
        <DataExtension>SQL</DataExtension>  
      </DataSource>  
      <DataSets>  
        <DataSet>  
          <Name>DataSet1</Name>  
          <RowsRead>16</RowsRead>  
          <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>33</ExecuteReaderTime>  
          <DataReaderMappingTime>30</DataReaderMappingTime>  
          <DisposeDataReaderTime>1</DisposeDataReaderTime>  
        </DataSet>  
        <DataSet>  
          <Name>DataSet2</Name>  
          <RowsRead>3</RowsRead>  
          <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
          <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
          <ExecuteReaderTime>1</ExecuteReaderTime>  
          <DataReaderMappingTime>0</DataReaderMappingTime>  
          <DisposeDataReaderTime>0</DisposeDataReaderTime>  
        </DataSet>  
      </DataSets>  
    </Connection>  
  </Connections>  
</AdditionalInfo>  
  
```  
  
 <span data-ttu-id="3bad6-236">Di seguito vengono descritte alcune delle proprietà che verranno visualizzate nel campo AdditionalInfo:</span><span class="sxs-lookup"><span data-stu-id="3bad6-236">The following describes some of the properties you will see in the AdditionalInfo field:</span></span>  
  
-   <span data-ttu-id="3bad6-237">**ProcessingEngine**: 1 = SQL Server 2005, 2 = nuovo motore di elaborazione su richiesta.</span><span class="sxs-lookup"><span data-stu-id="3bad6-237">**ProcessingEngine**: 1=SQL Server 2005, 2=The new On-demand Processing Engine.</span></span> <span data-ttu-id="3bad6-238">Se nella maggior parte dei report viene ancora mostrato il valore 1, è possibile esaminare come riprogettare questi report in modo che in essi venga utilizzato il motore di elaborazione su richiesta più nuovo e più efficiente.</span><span class="sxs-lookup"><span data-stu-id="3bad6-238">If a majority of your reports are still showing the value of 1, you may investigate how to redesign them so they utilize the newer and more efficient on-demand processing engine.</span></span>  
  
     `<ProcessingEngine>2</ProcessingEngine>`  
  
-   <span data-ttu-id="3bad6-239">**ScalabilityTime**: numero di millisecondi impiegati per l'esecuzione delle operazioni correlate alla scala nel motore di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3bad6-239">**ScalabilityTime**: The number of milliseconds spent performing scale related operations in the processing engine.</span></span> <span data-ttu-id="3bad6-240">Un valore 0 indica che non è stato impiegato ulteriore tempo per operazioni di scala. Questo valore indica inoltre che la richiesta non ha determinato un utilizzo eccessivo della memoria.</span><span class="sxs-lookup"><span data-stu-id="3bad6-240">A value of 0 indicates that no additional time was spent on scale operations and a 0 also indicates the request was not under memory pressure.</span></span>  
  
    ```  
    <ScalabilityTime>  
        <Processing>0</Processing>  
    </ScalabilityTime>  
    ```  
  
-   <span data-ttu-id="3bad6-241">**EstimatedMemoryUsageKB**: stima della quantità massima di memoria, espressa in kilobyte, utilizzata da ogni componente durante una determinata richiesta.</span><span class="sxs-lookup"><span data-stu-id="3bad6-241">**EstimatedMemoryUsageKB**: An estimate of the peak amount of memory, in kilobytes, consumed by each component during a particular request.</span></span>  
  
    ```  
    <EstimatedMemoryUsageKB>  
        <Processing>38</Processing>  
    </EstimatedMemoryUsageKB>  
    ```  
  
-   <span data-ttu-id="3bad6-242">**Dataextension**: tipi di estensioni per i dati o origini dati utilizzate nel report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-242">**DataExtension**: The types of data extensions or data sources used in the report.</span></span> <span data-ttu-id="3bad6-243">Il numero è quello delle occorrenze dell'origine dati specificata.</span><span class="sxs-lookup"><span data-stu-id="3bad6-243">The number is a count of the number of occurrences of the particular data source.</span></span>  
  
    ```  
    <DataExtension>  
       <DAX>2</DAX>  
    </DataExtension>  
    ```  
  
-   <span data-ttu-id="3bad6-244">**ExternalImages** Il valore è in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="3bad6-244">**ExternalImages**The value is in miliseconds.</span></span> <span data-ttu-id="3bad6-245">Queste informazioni possono essere usate nella diagnosi dei problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3bad6-245">This data can be used to diagnose performance issues.</span></span> <span data-ttu-id="3bad6-246">Il tempo necessario a recuperare le immagini da un webserver esterno può rallentare l'esecuzione del report complessiva.</span><span class="sxs-lookup"><span data-stu-id="3bad6-246">The time needed to retrieve images from an external webserver may slow the overall report execution.</span></span> <span data-ttu-id="3bad6-247">Aggiunto in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bad6-247">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <ExternalImages>  
        <Count>3</Count>  
        <ByteCount>9268</ByteCount>  
        <ResourceFetchTime>9</ResourceFetchTime>  
    </ExternalImages>  
    ```  
  
-   <span data-ttu-id="3bad6-248">**Connections**: struttura A più livelli.</span><span class="sxs-lookup"><span data-stu-id="3bad6-248">**Connections**: A multi-leveled structure.</span></span> <span data-ttu-id="3bad6-249">Aggiunto in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bad6-249">Added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
    ```  
    <Connections>  
        <Connection>  
          <ConnectionOpenTime>127</ConnectionOpenTime>  
          <DataSource>  
            <Name>DataSource1</Name>  
            <DataExtension>SQL</DataExtension>  
          </DataSource>  
          <DataSets>  
            <DataSet>  
              <Name>DataSet1</Name>  
              <RowsRead>16</RowsRead>  
              <TotalTimeDataRetrieval>655</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>94</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>33</ExecuteReaderTime>  
              <DataReaderMappingTime>30</DataReaderMappingTime>  
              <DisposeDataReaderTime>1</DisposeDataReaderTime>  
            </DataSet>  
            <DataSet>  
              <Name>DataSet2</Name>  
              <RowsRead>3</RowsRead>  
              <TotalTimeDataRetrieval>16</TotalTimeDataRetrieval>  
              <QueryPrepareAndExecutionTime>2</QueryPrepareAndExecutionTime>  
              <ExecuteReaderTime>1</ExecuteReaderTime>  
              <DataReaderMappingTime>0</DataReaderMappingTime>  
              <DisposeDataReaderTime>0</DisposeDataReaderTime>  
            </DataSet>  
          </DataSets>  
        </Connection>  
    </Connections>  
  
    ```  
  
##  <a name="log-fields-executionlog2"></a><a name="bkmk_executionlog2"></a> <span data-ttu-id="3bad6-250">Campi del log (ExecutionLog2)</span><span class="sxs-lookup"><span data-stu-id="3bad6-250">Log Fields (ExecutionLog2)</span></span>  
 <span data-ttu-id="3bad6-251">In questa vista sono stati aggiunti alcuni campi nuovi e ne sono stati rinominati alcuni altri.</span><span class="sxs-lookup"><span data-stu-id="3bad6-251">This view added a few new fields and renamed a few others.</span></span> <span data-ttu-id="3bad6-252">Di seguito è riportato un esempio di istruzione Transact SQL per recuperare righe dalla vista ExecutionLog2.</span><span class="sxs-lookup"><span data-stu-id="3bad6-252">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog2.</span></span> <span data-ttu-id="3bad6-253">Nell'esempio si presuppone che il database del server di report sia denominato **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="3bad6-253">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog2 order by TimeStart DESC  
```  
  
 <span data-ttu-id="3bad6-254">Nella tabella seguente vengono descritti i dati acquisiti nel log di esecuzione del report:</span><span class="sxs-lookup"><span data-stu-id="3bad6-254">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="3bad6-255">Colonna</span><span class="sxs-lookup"><span data-stu-id="3bad6-255">Column</span></span>|<span data-ttu-id="3bad6-256">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3bad6-256">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3bad6-257">InstanceName</span><span class="sxs-lookup"><span data-stu-id="3bad6-257">InstanceName</span></span>|<span data-ttu-id="3bad6-258">Nome dell'istanza del server di report tramite cui è stata gestita la richiesta.</span><span class="sxs-lookup"><span data-stu-id="3bad6-258">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="3bad6-259">ReportPath</span><span class="sxs-lookup"><span data-stu-id="3bad6-259">ReportPath</span></span>|<span data-ttu-id="3bad6-260">Struttura del percorso del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-260">The path structure to the report.</span></span>  <span data-ttu-id="3bad6-261">Per un report denominato "test" nella cartella radice in Gestione report, ad esempio, ReportPath sarà "/test".</span><span class="sxs-lookup"><span data-stu-id="3bad6-261">For example a report named "test" which is the in root folder in Report Manager, would have a ReportPath of "/test".</span></span><br /><br /> <span data-ttu-id="3bad6-262">Per un report denominato "test" salvato nella cartella "samples" in Gestione report, ReportPath sarà "/Samples/test/".</span><span class="sxs-lookup"><span data-stu-id="3bad6-262">A report named "test" that is saved in the folder "samples" on Report Manager , will have a ReportPath of "/Samples/test/"</span></span>|  
|<span data-ttu-id="3bad6-263">UserName</span><span class="sxs-lookup"><span data-stu-id="3bad6-263">UserName</span></span>|<span data-ttu-id="3bad6-264">Identificatore dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3bad6-264">User identifier.</span></span>|  
|<span data-ttu-id="3bad6-265">ExecutionID</span><span class="sxs-lookup"><span data-stu-id="3bad6-265">ExecutionID</span></span>||  
|<span data-ttu-id="3bad6-266">RequestType</span><span class="sxs-lookup"><span data-stu-id="3bad6-266">RequestType</span></span>|<span data-ttu-id="3bad6-267">Tipo di richiesta (utente o sistema).</span><span class="sxs-lookup"><span data-stu-id="3bad6-267">Request type (either user or system).</span></span>|  
|<span data-ttu-id="3bad6-268">Formato</span><span class="sxs-lookup"><span data-stu-id="3bad6-268">Format</span></span>|<span data-ttu-id="3bad6-269">Formato di rendering.</span><span class="sxs-lookup"><span data-stu-id="3bad6-269">Rendering format.</span></span>|  
|<span data-ttu-id="3bad6-270">Parametri</span><span class="sxs-lookup"><span data-stu-id="3bad6-270">Parameters</span></span>|<span data-ttu-id="3bad6-271">Valori dei parametri usati per l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-271">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="3bad6-272">ReportAction</span><span class="sxs-lookup"><span data-stu-id="3bad6-272">ReportAction</span></span>|<span data-ttu-id="3bad6-273">Valori possibili: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span><span class="sxs-lookup"><span data-stu-id="3bad6-273">Possible values: Render, Sort, BookMarkNavigation, DocumentNavigation, GetDocumentMap, Findstring</span></span>|  
|<span data-ttu-id="3bad6-274">TimeStart</span><span class="sxs-lookup"><span data-stu-id="3bad6-274">TimeStart</span></span>|<span data-ttu-id="3bad6-275">Ora di inizio e ora dell'arresto, che indicano la durata dell'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-275">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="3bad6-276">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="3bad6-276">TimeEnd</span></span>||  
|<span data-ttu-id="3bad6-277">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="3bad6-277">TimeDataRetrieval</span></span>|<span data-ttu-id="3bad6-278">Numero di millisecondi dedicati al recupero dei dati, all'elaborazione del report e al rendering del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-278">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="3bad6-279">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="3bad6-279">TimeProcessing</span></span>||  
|<span data-ttu-id="3bad6-280">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="3bad6-280">TimeRendering</span></span>||  
|<span data-ttu-id="3bad6-281">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="3bad6-281">Source</span></span>|<span data-ttu-id="3bad6-282">Origine dell'esecuzione del report (1=Live, 2=Cache, 3=Snapshot, 4=History).</span><span class="sxs-lookup"><span data-stu-id="3bad6-282">Source of the report execution (1=Live, 2=Cache, 3=Snapshot, 4=History).</span></span>|  
|<span data-ttu-id="3bad6-283">Stato</span><span class="sxs-lookup"><span data-stu-id="3bad6-283">Status</span></span>|<span data-ttu-id="3bad6-284">Stato (rsSuccess oppure un codice di errore; in caso di più errori, viene registrato solo il primo).</span><span class="sxs-lookup"><span data-stu-id="3bad6-284">Status (either rsSuccess or an error code; if multiple errors occur, only the first error is recorded).</span></span>|  
|<span data-ttu-id="3bad6-285">ByteCount</span><span class="sxs-lookup"><span data-stu-id="3bad6-285">ByteCount</span></span>|<span data-ttu-id="3bad6-286">Dimensione dei report visualizzabili, in byte.</span><span class="sxs-lookup"><span data-stu-id="3bad6-286">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="3bad6-287">RowCount</span><span class="sxs-lookup"><span data-stu-id="3bad6-287">RowCount</span></span>|<span data-ttu-id="3bad6-288">Numero di righe restituite dalle query.</span><span class="sxs-lookup"><span data-stu-id="3bad6-288">Number of rows returned from queries.</span></span>|  
|<span data-ttu-id="3bad6-289">AdditionalInfo</span><span class="sxs-lookup"><span data-stu-id="3bad6-289">AdditionalInfo</span></span>|<span data-ttu-id="3bad6-290">Contenitore di proprietà XML in cui sono incluse informazioni aggiuntive sull'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bad6-290">An XML property bag containing additional information about the execution.</span></span>|  
  
##  <a name="log-fields-executionlog"></a><a name="bkmk_executionlog"></a> <span data-ttu-id="3bad6-291">Campi del log (ExecutionLog)</span><span class="sxs-lookup"><span data-stu-id="3bad6-291">Log Fields (ExecutionLog)</span></span>  
 <span data-ttu-id="3bad6-292">Di seguito è riportato un esempio di istruzione Transact SQL per recuperare righe dalla vista ExecutionLog.</span><span class="sxs-lookup"><span data-stu-id="3bad6-292">The following is a sample Transact SQL statement to retrieve rows from the view ExecutionLog.</span></span> <span data-ttu-id="3bad6-293">Nell'esempio si presuppone che il database del server di report sia denominato **ReportServer**:</span><span class="sxs-lookup"><span data-stu-id="3bad6-293">The sample assumes the report server database is named **ReportServer**:</span></span>  
  
```  
Use ReportServer  
select * from ExecutionLog order by TimeStart DESC  
  
```  
  
 <span data-ttu-id="3bad6-294">Nella tabella seguente vengono descritti i dati acquisiti nel log di esecuzione del report:</span><span class="sxs-lookup"><span data-stu-id="3bad6-294">The following table describes the data that is captured in the report execution log</span></span>  
  
|<span data-ttu-id="3bad6-295">Colonna</span><span class="sxs-lookup"><span data-stu-id="3bad6-295">Column</span></span>|<span data-ttu-id="3bad6-296">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3bad6-296">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3bad6-297">InstanceName</span><span class="sxs-lookup"><span data-stu-id="3bad6-297">InstanceName</span></span>|<span data-ttu-id="3bad6-298">Nome dell'istanza del server di report tramite cui è stata gestita la richiesta.</span><span class="sxs-lookup"><span data-stu-id="3bad6-298">Name of the report server instance that handled the request.</span></span>|  
|<span data-ttu-id="3bad6-299">ReportID</span><span class="sxs-lookup"><span data-stu-id="3bad6-299">ReportID</span></span>|<span data-ttu-id="3bad6-300">Identificatore del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-300">Report identifier.</span></span>|  
|<span data-ttu-id="3bad6-301">UserName</span><span class="sxs-lookup"><span data-stu-id="3bad6-301">UserName</span></span>|<span data-ttu-id="3bad6-302">Identificatore dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3bad6-302">User identifier.</span></span>|  
|<span data-ttu-id="3bad6-303">RequestType</span><span class="sxs-lookup"><span data-stu-id="3bad6-303">RequestType</span></span>|<span data-ttu-id="3bad6-304">Valori possibili:</span><span class="sxs-lookup"><span data-stu-id="3bad6-304">Possible values:</span></span><br /><br /> <span data-ttu-id="3bad6-305">True = Richiesta di sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="3bad6-305">True = A Subscription request</span></span><br /><br /> <span data-ttu-id="3bad6-306">False= Richiesta interattiva</span><span class="sxs-lookup"><span data-stu-id="3bad6-306">False= An Interactive request</span></span>|  
|<span data-ttu-id="3bad6-307">Formato</span><span class="sxs-lookup"><span data-stu-id="3bad6-307">Format</span></span>|<span data-ttu-id="3bad6-308">Formato di rendering.</span><span class="sxs-lookup"><span data-stu-id="3bad6-308">Rendering format.</span></span>|  
|<span data-ttu-id="3bad6-309">Parametri</span><span class="sxs-lookup"><span data-stu-id="3bad6-309">Parameters</span></span>|<span data-ttu-id="3bad6-310">Valori dei parametri usati per l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-310">Parameter values used for a report execution.</span></span>|  
|<span data-ttu-id="3bad6-311">TimeStart</span><span class="sxs-lookup"><span data-stu-id="3bad6-311">TimeStart</span></span>|<span data-ttu-id="3bad6-312">Ora di inizio e ora dell'arresto, che indicano la durata dell'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-312">Start and stop times that indicate the duration of a report process.</span></span>|  
|<span data-ttu-id="3bad6-313">TimeEnd</span><span class="sxs-lookup"><span data-stu-id="3bad6-313">TimeEnd</span></span>||  
|<span data-ttu-id="3bad6-314">TimeDataRetrieval</span><span class="sxs-lookup"><span data-stu-id="3bad6-314">TimeDataRetrieval</span></span>|<span data-ttu-id="3bad6-315">Numero di millisecondi dedicati al recupero dei dati, all'elaborazione del report e al rendering del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-315">Number of milliseconds spent retrieving the data, processing the report, and rendering the report.</span></span>|  
|<span data-ttu-id="3bad6-316">TimeProcessing</span><span class="sxs-lookup"><span data-stu-id="3bad6-316">TimeProcessing</span></span>||  
|<span data-ttu-id="3bad6-317">TimeRendering</span><span class="sxs-lookup"><span data-stu-id="3bad6-317">TimeRendering</span></span>||  
|<span data-ttu-id="3bad6-318">Source (Sorgente)</span><span class="sxs-lookup"><span data-stu-id="3bad6-318">Source</span></span>|<span data-ttu-id="3bad6-319">Origine dell'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="3bad6-319">Source of the report execution.</span></span> <span data-ttu-id="3bad6-320">Valori possibili: 1=Live, 2=Cache, 3=Snapshot, 4=History, 5=Adhoc, 6=Session, 7=RDCE.</span><span class="sxs-lookup"><span data-stu-id="3bad6-320">Possible values: (1=Live, 2=Cache, 3=Snapshot, 4=History, 5=Adhoc, 6=Session, 7=RDCE).</span></span>|  
|<span data-ttu-id="3bad6-321">Stato</span><span class="sxs-lookup"><span data-stu-id="3bad6-321">Status</span></span>|<span data-ttu-id="3bad6-322">Valori possibili: rsSuccess, rsProcessingAborted o un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="3bad6-322">Possible values: rsSuccess, rsProcessingAborted, or an error code.</span></span> <span data-ttu-id="3bad6-323">Se si verificano più errori, viene registrato solo il primo.</span><span class="sxs-lookup"><span data-stu-id="3bad6-323">If multiple errors occur, only the first error is recorded.</span></span>|  
|<span data-ttu-id="3bad6-324">ByteCount</span><span class="sxs-lookup"><span data-stu-id="3bad6-324">ByteCount</span></span>|<span data-ttu-id="3bad6-325">Dimensione dei report visualizzabili, in byte.</span><span class="sxs-lookup"><span data-stu-id="3bad6-325">Size of rendered reports in bytes.</span></span>|  
|<span data-ttu-id="3bad6-326">RowCount</span><span class="sxs-lookup"><span data-stu-id="3bad6-326">RowCount</span></span>|<span data-ttu-id="3bad6-327">Numero di righe restituite dalle query.</span><span class="sxs-lookup"><span data-stu-id="3bad6-327">Number of rows returned from queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bad6-328">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bad6-328">See Also</span></span>  
 <span data-ttu-id="3bad6-329">[Attivare gli eventi di Reporting Services per il log di traccia di SharePoint &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span><span class="sxs-lookup"><span data-stu-id="3bad6-329">[Turn on Reporting Services events for the SharePoint trace log &#40;ULS&#41;](turn-on-reporting-services-events-for-the-sharepoint-trace-log-uls.md) </span></span>  
 <span data-ttu-id="3bad6-330">[File di log e origini di Reporting Services](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="3bad6-330">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 [<span data-ttu-id="3bad6-331">Guida di riferimento a errori ed eventi &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3bad6-331">Errors and Events Reference &#40;Reporting Services&#41;</span></span>](../troubleshooting/errors-and-events-reference-reporting-services.md)  
  
  
