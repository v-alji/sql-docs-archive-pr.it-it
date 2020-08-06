---
title: Correlare una traccia con i dati del log delle prestazioni di Windows (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], logs
ms.assetid: e1b3072c-8daf-49a7-9895-c8cccd2adb95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 34575cf4270d817ecfbb5b2d1824831cc99454fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628968"
---
# <a name="correlate-a-trace-with-windows-performance-log-data-sql-server-profiler"></a><span data-ttu-id="60f9a-102">Correlare una traccia e i dati dei registri di prestazioni di Windows (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="60f9a-102">Correlate a Trace with Windows Performance Log Data (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]<span data-ttu-id="60f9a-103">consente di correlare i contatori di monitoraggio di sistema di Microsoft Windows con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] gli eventi o.</span><span class="sxs-lookup"><span data-stu-id="60f9a-103">can correlate Microsoft Windows System Monitor counters with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] events.</span></span> <span data-ttu-id="60f9a-104">Con monitoraggio di sistema di Windows viene registrata l'attività del sistema per i contatori specificati nei registri di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="60f9a-104">Windows System Monitor logs system activity for specified counters in performance logs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60f9a-105">Per informazioni sulla condivisione di log tra versioni di Windows diverse, vedere la procedura descritta alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="60f9a-105">For information about sharing logs among different versions of Windows, see the procedure at the end of this topic.</span></span>  
  
### <a name="to-correlate-a-trace-with-performance-log-data"></a><span data-ttu-id="60f9a-106">Per correlare una traccia ai dati dei registri di prestazioni</span><span class="sxs-lookup"><span data-stu-id="60f9a-106">To correlate a trace with performance log data</span></span>  
  
1.  <span data-ttu-id="60f9a-107">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]aprire un file o una tabella di traccia salvata.</span><span class="sxs-lookup"><span data-stu-id="60f9a-107">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], open a saved trace file or trace table.</span></span> <span data-ttu-id="60f9a-108">Non è possibile correlare una traccia in esecuzione che sta ancora raccogliendo dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="60f9a-108">You cannot correlate a running trace that is still collecting event data.</span></span> <span data-ttu-id="60f9a-109">Per assicurare che la correlazione ai dati di monitoraggio di sistema sia corretta, è necessario che la traccia includa le due colonne di dati **StartTime** ed **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="60f9a-109">For accurate correlation with System Monitor data, the trace must contain both **StartTime** and **EndTime** data columns.</span></span>  
  
2.  <span data-ttu-id="60f9a-110">Scegliere **Importa dati prestazioni** dal menu  **File** di [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60f9a-110">On the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **File** menu, click **Import Performance Data**.</span></span>  
  
3.  <span data-ttu-id="60f9a-111">Nella finestra di dialogo **Apri** selezionare un file contenente un registro di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="60f9a-111">In the **Open** dialog box, select a file that contains a performance log.</span></span> <span data-ttu-id="60f9a-112">I dati del registro di prestazioni devono essere acquisiti quando è in corso l'acquisizione dei dati della traccia.</span><span class="sxs-lookup"><span data-stu-id="60f9a-112">The performance log data must have been captured during the same time period in which the trace data is captured.</span></span>  
  
4.  <span data-ttu-id="60f9a-113">Nella finestra di dialogo **Limite contatori prestazioni** selezionare le caselle di controllo corrispondenti agli oggetti e ai contatori di monitoraggio di sistema che si desidera visualizzare insieme alla traccia.</span><span class="sxs-lookup"><span data-stu-id="60f9a-113">In the **Performance Counters Limit** dialog box, select the check boxes that correspond to the System Monitor objects and counters that you want to display alongside the trace.</span></span> <span data-ttu-id="60f9a-114">Scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="60f9a-114">Click **OK.**</span></span>  
  
5.  <span data-ttu-id="60f9a-115">Selezionare un evento nella finestra degli eventi di traccia oppure nella finestra degli eventi di traccia scorrere alcune righe consecutive tramite i tasti di direzione.</span><span class="sxs-lookup"><span data-stu-id="60f9a-115">Select an event in the trace events window, or navigate through several adjacent rows in the trace events window by using the arrow keys.</span></span> <span data-ttu-id="60f9a-116">La barra rossa verticale visualizzata nella finestra dei **dati di monitoraggio di sistema** indica i dati del registro di prestazioni correlati all'evento di traccia selezionato.</span><span class="sxs-lookup"><span data-stu-id="60f9a-116">The vertical red bar in the **System Monitor data** window indicates the performance log data that is correlated with the selected trace event.</span></span>  
  
6.  <span data-ttu-id="60f9a-117">Fare clic sul punto desiderato nel grafico di monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="60f9a-117">Click a point of interest in the System Monitor graph.</span></span> <span data-ttu-id="60f9a-118">Verrà selezionata la riga di traccia corrispondente più prossima in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="60f9a-118">The corresponding trace row that is nearest in time is selected.</span></span> <span data-ttu-id="60f9a-119">Per eseguire lo zoom avanti su un intervallo di tempo, premere e trascinare il puntatore del mouse nel grafico di monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="60f9a-119">To zoom in on a time range, press and drag the mouse pointer in the System Monitor graph.</span></span>  
  
### <a name="to-create-performance-logs-that-can-be-shared-among-different-versions-of-windows"></a><span data-ttu-id="60f9a-120">Per creare registri di prestazioni da condividere tra versioni di Windows diverse</span><span class="sxs-lookup"><span data-stu-id="60f9a-120">To create performance logs that can be shared among different versions of Windows</span></span>  
  
1.  <span data-ttu-id="60f9a-121">Nel Pannello di controllo aprire **Strumenti di amministrazione**e quindi fare doppio clic su **Prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-121">In Control Panel, open **Administrative Tools**, and then double click **Performance**.</span></span>  
  
2.  <span data-ttu-id="60f9a-122">Nella finestra di dialogo **Prestazioni** espandere il nodo **Avvisi e registri di prestazioni**, fare clic con il pulsante destro del mouse su **Registri contatori**e quindi fare clic su **Nuove impostazioni registro**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-122">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span>  
  
3.  <span data-ttu-id="60f9a-123">Digitare un nome per il registro contatori e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-123">Type a name for the counter log, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="60f9a-124">Nella scheda **Generale** fare clic su **Aggiungi contatori**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-124">On the **General** tab, click **Add Counters**.</span></span>  
  
5.  <span data-ttu-id="60f9a-125">Nell'elenco **Oggetto prestazione** selezionare l'oggetto prestazione che si desidera monitorare.</span><span class="sxs-lookup"><span data-stu-id="60f9a-125">In the **Performance object** list, select a performance object you want to monitor.</span></span> <span data-ttu-id="60f9a-126">I nomi degli oggetti prestazioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per le istanze predefinite di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] iniziano con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e le istanze denominate iniziano con MSSQL$*instanceName*.</span><span class="sxs-lookup"><span data-stu-id="60f9a-126">The names of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] performance objects for default instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] start with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and named instances start with MSSQL$*instanceName*.</span></span>  
  
6.  <span data-ttu-id="60f9a-127">Aggiungere il numero di contatori necessari per l'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in uso e altri valori importanti, ad esempio il tempo processore e il tempo disco.</span><span class="sxs-lookup"><span data-stu-id="60f9a-127">Add as many counters as necessary for your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and other important values, such as processor time and disk time.</span></span>  
  
7.  <span data-ttu-id="60f9a-128">Dopo aver completato questa operazione, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="60f9a-128">When you have finished adding counters, click **Close**.</span></span>  
  
8.  <span data-ttu-id="60f9a-129">Impostare i valori desiderati per l'intervallo **Campiona dati ogni** .</span><span class="sxs-lookup"><span data-stu-id="60f9a-129">Set values for the **Sample data every** interval.</span></span> <span data-ttu-id="60f9a-130">Iniziare con un intervallo breve, ad esempio 5 minuti, e modificarlo quindi in modo adeguato se necessario.</span><span class="sxs-lookup"><span data-stu-id="60f9a-130">Start with a modest sampling interval, such as 5 minutes, and then adjust the interval if necessary.</span></span>  
  
9. <span data-ttu-id="60f9a-131">Nella scheda **File di log** scegliere **File di testo (delimitato da virgole)** nell'elenco **Tipo file registro** .</span><span class="sxs-lookup"><span data-stu-id="60f9a-131">On the **Log Files** tab, choose **TextFile (Comma delimited)** from the **Log file type** list.</span></span> <span data-ttu-id="60f9a-132">I file di log in formato di testo delimitato da virgole possono essere condivisi tra versioni diverse di Windows e visualizzati successivamente in uno strumento per la creazione di report, ad esempio Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="60f9a-132">Comma-delimited text log files can be shared among different versions of Windows and can be viewed later in reporting tools such as Microsoft Excel.</span></span>  
  
10. <span data-ttu-id="60f9a-133">Nella scheda **Pianificazione** specificare una pianificazione per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="60f9a-133">On the **Schedule** tab, specify a monitoring schedule.</span></span>  
  
11. <span data-ttu-id="60f9a-134">Fare clic su **OK** . Verrà creato il registro di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="60f9a-134">Click **OK** to create the performance log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f9a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60f9a-135">See Also</span></span>  
 <span data-ttu-id="60f9a-136">[Modelli e autorizzazioni di SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="60f9a-136">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="60f9a-137">Avviare SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="60f9a-137">Start SQL Server Profiler</span></span>](../tools/sql-server-profiler/start-sql-server-profiler.md)  
  
  
